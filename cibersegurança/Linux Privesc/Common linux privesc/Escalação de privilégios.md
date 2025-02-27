# Tipos
- Horizontal: entre usuários com as mesmas permissões
- Vertical: entre usuários com permissões diferentes

# LinEnum
bash script que perfoma comandos comuns relacionados a escalação de privilégios

[LinEnum/LinEnum.sh at master · rebootuser/LinEnum](https://github.com/rebootuser/LinEnum/blob/master/LinEnum.sh)

**chmod +x FILENAME.sh** para dar permissão de execução

# SUID/GUID bit set

- **SUID binary** (ou binário com SUID): é um arquivo executável no Linux/Unix que possui o bit **SUID (Set User ID)** ativado. Esse bit permite que o programa seja executado com os privilégios do dono do arquivo, em vez dos privilégios do usuário que o executa.
	- As permissões para SUID são: ``rws-rwx-rwx``

- **GUID binary** (ou binário com GUID): é um arquivo executável no Linux/Unix que possui o bit **GUID (Set Group ID)** ativado. Esse bit faz com que o programa seja executado com os privilégios do **grupo dono** do arquivo, em vez dos privilégios do usuário que o executa. 
	- As permissões para GUID são: ``rwx-rws-rwx``

Para encontrar SUID files podemos usar:
``find / -perm -u=s -type f 2>/dev/null``


# Binários mal configurados e GTFOBins
[GTFOBins](https://gtfobins.github.io/)


# Cron Tabs
É um processo de execução longa que executa comandos em datas e tempos específicos. Podemos usar isso para agendar atividades. Para encontrar os jobs agendados use ``cat /etc/crontab``

## Formato

``# = ID``  
``m = Minute``
``h = Hour``
``dom = Day of the month``
``mon = Month``
``dow = Day of the week``
``user = What user the command will run as `` 
``command = What command should be run``

 Exemplo:
``#  m   h dom mon dow user  command``  
``17 *   1  *   *   *  root  cd / && run-parts --report /etc/cron.hourly``

# PATH variable
É uma variável de ambiente que especifica quais diretórios mantem programas executáveis

``echo $PATH``

## Como explorar
Digamos que temos um binário com SUID. Ao executá-lo, percebemos que ele chama o shell do sistema para realizar um processo simples, como listar processos usando `ps`. 

Podemos reescrever a variável `PATH` para apontar para um local de nossa escolha. Dessa forma, quando o binário SUID chamar o shell do sistema para executar um programa, ele executará um que nós criamos em vez do original.

Como acontece com qualquer arquivo SUID, esse comando será executado com os mesmos privilégios do dono do arquivo SUID. Se esse dono for o usuário root, esse método nos permitirá executar qualquer comando como root.


# Checklists
Listas são boas para padronizar a exploração e garantir que você não está perdendo nada
- [https://github.com/netbiosX/Checklists/blob/master/Linux-Privilege-Escalation.md](https://github.com/netbiosX/Checklists/blob/master/Linux-Privilege-Escalation.md)
- [https://github.com/swisskyrepo/PayloadsAllTheThings/blob/master/Methodology%20and%20Resources/Linux%20-%20Privilege%20Escalation.md](https://github.com/swisskyrepo/PayloadsAllTheThings/blob/master/Methodology%20and%20Resources/Linux%20-%20Privilege%20Escalation.md)
- [https://sushant747.gitbooks.io/total-oscp-guide/privilege_escalation_-_linux.html](https://sushant747.gitbooks.io/total-oscp-guide/privilege_escalation_-_linux.html)[](https://sushant747.gitbooks.io/total-oscp-guide/privilege_escalation_-_linux.html)
- [https://payatu.com/blog/a-guide-to-linux-privilege-escalation/](https://payatu.com/blog/a-guide-to-linux-privilege-escalation/)

