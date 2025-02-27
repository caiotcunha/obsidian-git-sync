
# Readable /etc/shadow
Se esse arquivo puder ser lido por qualquer usuário podemos pegar o hash da senha do root e usar john ripper para descobrir a senha do root

# Writable /etc/shadow
Podemos trocar a senha do usuário root pela senha que quisermos. Ficam armazenadas as senhas hash.
``mkpasswd -m sha-512 newpasswordhere``
# Writable /etc/passwd
Podemos trocar a senha do usuário root pela senha que quisermos.Ficam armazenadas as senhas hash.
``openssl passwd newpasswordhere``

