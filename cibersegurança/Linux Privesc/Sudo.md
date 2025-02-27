# Shell Escape Sequences
[GTFOBins](https://gtfobins.github.io/)
achamos sequencias de elevação de privilégios caso o user possa executar algum desses comandos com sudo
``sudo -l`` mostra o que o user pode usar como sudo

# Enviroment Variables
Sudo pode ser configurado para herdar certas variáveis do ambiente do usuário, procure por env_keep options.LD_PRELOAD and LD_LIBRARY_PATH são herdadas.

``LD_PRELOAD`` carrega um objeto compartilhado antes de qualquer outro antes do programa rodar.

``LD_LIBRARY_PATH`` provém uma lista de diretórios onde as bibliotecas são procuradas primeiro

### Mudando o PATH
você pode usar um comando que tem acesso de sudo para setar essa variável ao mesmo tempo
``sudo LD_PRELOAD=/tmp/preload.so program-name-here``


``ldd /usr/sbin/program-name-here`` mostra as bibliotecas compartilhadas pelo programa.
A partir disso você pode criar um programa com o mesmo nome de uma das bibliotecas usadas e mudar o caminho para ele. Assim, ao executar o programa com sudo, você eleva seu privilégio à root.
