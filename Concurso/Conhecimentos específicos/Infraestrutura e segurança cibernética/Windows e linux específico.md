# Linux

- **Syslog:** rotocolo padrão para envio de logs de eventos.
- No Linux, os comandos ifdown e ifup são utilizados para desativar e ativar interfaces de rede, respectivamente. Esses comandos são essenciais para gerenciar a conectividade de rede de uma máquina
- Para gerenciar o firewall no Linux, são utilizados comandos específicos como iptables ou firewalld (em distribuições mais modernas). Por exemplo, para ativar ou desativar o firewall no firewalld, utilizam-se comandos como systemctl start firewalld e systemctl stop firewalld.
- O **nftables** é um framework para filtragem de pacotes de rede no kernel Linux, destinado a substituir o iptables, ip6tables, arptables e ebtables. Ele permite configurar firewalls e manipular tabelas de regras para filtragem de pacotes de rede.
- Cada zona de firewall, nas políticas, é associada a um conjunto específico de regras que determinam o tráfego permitido de forma unidirecional e com monitoramento de estado, sendo o retorno do tráfego permitido implicitamente devido à filtragem com monitoramento de estado pelo firewalld.
- `tail -f /var/log/meu_arquivo.log`. Esse parâmetro faz com que o `tail` "siga" o arquivo, isto é, continue mostrando novas entradas à medida que são adicionadas ao final do arquivo de log.

# Windows
- **Event Viewer:** Armazena os logs em arquivos conhecidos como event logs
- **NTFS (New Technology File System)** é um sistema de arquivos desenvolvido pela Microsoft para o sistema operacional Windows. Ele oferece várias funcionalidades avançadas, como suporte a grandes volumes de dados, permissões de segurança avançadas, criptografia, cotas de disco, e muito mais. No entanto, é importante entender que o NTFS é um sistema de arquivos nativo do Windows.
- O comando _ipconfig /release_ tem uma função específica no ambiente Windows. Quando você executa esse comando, ele libera (ou "solta") o endereço IP atualmente atribuído ao adaptador de rede. Isso é útil em situações onde você precisa remover a configuração atual de IP, seja para solucionar problemas de rede ou para forçar o adaptador a solicitar um novo endereço IP.


# **Ferramentas Comuns**

| **Windows**                                  | **Linux**                                 |     |     |
| -------------------------------------------- | ----------------------------------------- | --- | --- |
| - **Server Manager**                         | - **systemd** (gerenciamento de serviços) |     |     |
| - **Event Viewer** (Visualizador de Eventos) | - **journalctl** (visualização de logs)   |     |     |
| - **Registry Editor** (Regedit)              | - **Vim/Nano** (editores de texto)        |     |     |
| - **Windows Defender**                       | - **UFW** (Uncomplicated Firewall)        |     |     |
| - **Remote Desktop**                         | - **SSH** (acesso remoto)                 |     |     |
