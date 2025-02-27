# Know Exploits

Para achar SUID/SGID executáveis:
``find / -type f -a \( -perm -u+s -o -perm -g+s \) -exec ls -l {} \; 2> /dev/null``


# Shared Object Injection
A ideia é procurar por arquivos SUID que possuam bibliotecas compartilhadas inexistentes.
podemos usar:
``strace /usr/local/bin/nome-do-arquivo 2>&1 | grep -iE "open|access|no such file"``
Se ele tiver alguma dessas apontadas para a home do usuário que estamos podemos criar um arquivo para ser acessado, assim ganharemos acesso de root.

# Environment Variables
``strings /usr/local/bin/suid-env`` busca strings de caracteres imprimíveis

Em versões do Bash anteriores a 4.2-048, é possível definir funções do shell com nomes que se assemelham a caminhos de arquivos e, em seguida, exportá-las para que sejam usadas no lugar de qualquer executável real nesse caminho de arquivo.

