A Open Web Application Security Project é uma organização sem fins lucrativos focada em entender as tecnologias web e as formas comuns de invasão. Ela provê recursos e ferramentas para melhorar a segurança de software

1. Broken Access Control: Usuários com diferentes permissões devem poder acessar coisas diferentes. Essa vulnerabilidade é relacionada a passar por uma autorização sem poder. Geralmente acontece através de IDOR (Insecure Direct Object Reference), quando o programador expõe inadequadamente um objeto.
	1. podem ser categorizados em dois tipos:
		1. Horizontal Privilege Escalation: Ocorre quando um usuário pode fazer uma ação ou acessar dados de outro com as mesmas permissões.
		2. Vertical Privilege Escalation: Ocorre quando um usuário pode fazer uma ação ou acessar dados de outro com maiores permissões.
2. Criptographic Failure: Falta ou uso inadequado da criptografia. Sem a criptografia para dados em movimento, o sistema fica vulneravel a ataques do tipo "man in the middle". Também é necessário criptografar os dados em repouso para evitar possíveis ataques.
	1. É comum dados serem armazenados em databases ou em flat-file (programas menores)
3. Injection: A aplicação interpreta um input digitado pelo usuário como comando ou parâmetro. Esse ataque depende muito de qual tecnologia é utilizada e como o programa interpreta o input.
	1. SQL injection: Ocorre quando o input do usuário é passado para uma query no SQL. Então, um atacante pode manipular o resultado da query roubando dados sensíveis ou alterando dados no banco de dados.
	2. Command Injection: Ocorre quando o input do usuário é passado para os comandos do sistema. Como resultado, um atacante pode executar quais comandos quiser nos servidores da aplicação, o que pode leva-los a ter acesso ao sistema.
	3. Soluções
		1. Utilizar uma lista de permitidos: utilizar uma lista de inputs ou caracteres permitidos e comparar o input do usuário a eles.
		2. Quebrar o input: processar o input do usuário de forma a remover os caracteres perigosos
4. Insecure Design: refere-se a vulnerabilidades que são inerentes à arquitetura da aplicação. A melhor forma de impedir que isso aconteça é seguir um desenvolvimento que possua ciclos de desenvolvimento de segurança (SSDLC).
5. Security Misconfiguration: O software foi configurado de maneira errada deixando brechas de segurança.
6. Vulnerable and Outdated Components: Componentes (ou versões de componentes) com vulnerabilidades conhecidas. Existem softwares que podem ajudar na busca por essas vulnerabilidades. Existem sites com exploits para vulnerabilidades conhecidas.
7. Identification and Authentication Failures: Autenticação e identificação são usados para quase todas as aplicações web. Se um atacante conseguir achar falhas no mecanismo de autenticação ele pode ganhar acesso à conta do usuário. Credenciais e cookies de sessão fracos são vulneráveis a ataques.
8. Software and Data Integrity Failures: Integridade é a capacidade de certificar que um dado permanece original. Aplicações baixadas da web geralmente possuem um hash que pode ser comparado para garantir a integridade do programa.
	1. Para o caso de software podemos usar Subresource Integrity (SRI) para comparar os hashs.
9. Security Loggin and Monitoring Failures: Cada ação do usuário deve ser impressa em algum lugar. É importante ter esse controle para, no caso de um ataque, poder determinar o tamanho do dano e medidas para combater. Importante para saber se o atacante ainda tem acesso à rede. 
10. Server-Side Request Forgery (SSRF): Ocorre quando um atacante força a aplicação web a mandar requisições para lugares arbitrários enquanto mantém controle do conteúdo delas. Geralmente relacionado a aplicações web que usam serviços terceirizados.