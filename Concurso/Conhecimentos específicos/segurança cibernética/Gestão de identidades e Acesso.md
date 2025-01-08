O gerenciamento de identidades (autenticação) verifica uma tentativa de conexão em relação ao banco de dados de gerenciamento de identidades, que é um registro contínuo de todos que devem ter acesso. Essas informações devem ser atualizadas constantemente à medida que as pessoas entram ou saem da organização, suas funções e projetos mudam e o escopo da organização evolui.
O gerenciamento de acesso (autorização) é a segunda parte do IAM. Depois que o sistema de IAM tiver verificado que a pessoa que está tentando acessar um recurso corresponde à identidade, o gerenciamento de acesso controla quais recursos a pessoa tem permissão para acessar. A maioria das organizações concede níveis variados de acesso a recursos e dados e esses níveis são determinados por fatores como cargo, tempo de trabalho, certificado de segurança e projeto.

# Tecnologias de IAM e ferramentas

## SAML(Security Assertion Markup Language)
é uma forma padronizada de informar aos aplicativos e serviços externos que um usuário é quem ele diz ser. A SAML possibilita a tecnologia de logon único (SSO) ao fornecer uma maneira de autenticar um usuário uma única vez e, em seguida, comunicar essa autenticação a vários aplicativos. A versão mais atual da SAML é a SAML 2.0.

**Principal/titular:** é quase sempre um usuário humano que está tentando acessar um aplicativo hospedado na nuvem.

**Provedor de identidade:** um provedor de identidade (IdP) é um serviço de software em nuvem que armazena e confirma a identidade do usuário, geralmente por meio de um processo de login. Essencialmente, o papel de um IdP é dizer: "Conheço essa pessoa e aqui está o que ela pode fazer". Um sistema de SSO pode, de fato, ser separado do provedor de identidade, mas nesses casos o SSO atua, essencialmente, como um representante do IdP e portanto, para todos os efeitos, os dois são a mesma coisa em um fluxo de trabalho de SAML.

**Provedor de serviços:** esse é o aplicativo ou serviço hospedado em nuvem que o usuário deseja usar. Exemplos comuns incluem plataformas de e-mail em nuvem, como o Gmail e o Microsoft Office 365, serviços de armazenamento em nuvem como o Google Drive e a AWS S3 e aplicativos de comunicação, como o Slack e o Skype. Normalmente, um usuário simplesmente faria login nesses serviços diretamente, mas, quando um SSO é usado, o usuário faz login no SSO e a SAML é usada para fornecer acesso no lugar de um login direto.

## OAuth 2.0
OAuth 2.0, que significa "Autorização Aberta", é um padrão projetado para permitir que um site ou aplicativo acesse recursos hospedados por outros aplicativos da web em nome de um usuário. O OAuth 2.0 é um protocolo de autorização e NÃO um protocolo de autenticação. Como tal, ele foi projetado principalmente como um meio de conceder acesso a um conjunto de recursos, por exemplo, APIs remotas ou dados do usuário. Um **token de acesso** é um dado que representa a autorização para acessar recursos em nome do usuário final.

### Funções
- **Proprietário do recurso:** o usuário ou sistema que possui os recursos protegidos e pode conceder acesso a eles.
- **Cliente:** o cliente é o sistema que requer acesso aos recursos protegidos. Para acessar recursos, o Cliente deve ter o token de acesso apropriado.
- **Servidor de autorização:** este servidor recebe solicitações do Cliente para tokens de acesso e os emite mediante autenticação e consentimento bem-sucedidos do proprietário do recurso. O servidor de autorização expõe dois endpoints: o endpoint de Autorização, que lida com a autenticação e o consentimento interativos do usuário, e o endpoint de Token, que está envolvido em uma interação máquina a máquina.
- **Servidor de recursos:** um servidor que protege os recursos do usuário e recebe solicitações de acesso do Cliente. Ele aceita e valida um token de acesso do cliente e retorna os recursos apropriados para ele.
### Funcionamento
1. O Cliente solicita autorização (solicitação de autorização) do servidor de Autorização, fornecendo a ID e o segredo do cliente como identificação; ele também fornece os escopos e um URI de endpoint (URI de redirecionamento) para enviar o token de acesso ou o código de autorização.
2. O servidor de Autorização autentica o Cliente e verifica se os escopos solicitados são permitidos.
3. O proprietário do recurso interage com o servidor de autorização para conceder acesso.
4. O servidor de autorização é redirecionado de volta para o cliente com um código de autorização ou token de acesso, dependendo do tipo de concessão, como será explicado na próxima seção. Um token de atualização também pode ser retornado.
5. Com o token de acesso, o cliente solicita acesso ao recurso a partir do servidor de recursos.

No OAuth 2.0, **concessões** são o conjunto de etapas que um Cliente deve executar para obter a autorização de acesso a recursos.

## OpenID Connect
OpenID Connect is an interoperable authentication protocol based on the OAuth 2.0 framework of specifications (IETF RFC 6749 and 6750). It simplifies the way to verify the identity of users based on the authentication performed by an Authorization Server and to obtain user profile information in an interoperable and REST-like manner.


