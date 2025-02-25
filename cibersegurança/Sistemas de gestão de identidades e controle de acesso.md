Existem 3 modelos para a implementação para implementar um sistema de gerência de identidade e controle de acesso. Os modelos são: isolado, centralizado, federado. As duas principais funções desse sistema são: autenticação(associada à identidade) e autorização(associada ao acesso).Quanto mais tipos de métodos de autenticação, mais seguro e mais custoso.

## Modelos de sistema de gerência de identidade e controle de acesso
### Isolado
Baseado em cada serviço controlar a sua própria base de identidades. Se o usuário precisar usar mais de um serviço ele vai ter que se cadastrar em cada um dos serviços. Esse tipo de sistema não é muito escalável e gera uma experiência ruim para o usuário final que precisa se cadastrar em cada um dos serviços. A falta de sincronia entre os serviços torna dificil de gerenciar. Tambem cada um dos serviços vai ter que resolver a sua autenticação, o que pode gerar maior trabalho de manutenção.
#### caracteristicas
- Self-Contained: Cada aplicação gerencia as suas próprias identidades
- No Shared Resources: sem uma base de dados centralizada de identidades

### Centralizado
Uma base de dados única que mantem as credenciais. Ao logar você tem acesso a todos os serviços relacionados.
#### Características
- Baseado no conceito de Single Sign-On (SSO)
- Single Repository: Uma única credencial para todas as aplicações
#### Contras
- Único ponto de falha (se a base central falha o sistema cai)
- Somente dentro de uma instituição

### Federado
Instituições concordam em compartilhar as credenciaise outras caracteristicas (bancos de dados) de forma que um usuário com a mesma credencial possa se autenticar entre diferentes sistemas. Por exemplo utilizar o login do google para entrar em redes sociais. As instituições utilizam a autenticação feita por outro sistema e controlam apenas a autorização.
Modelos populares de protocolos federados: SAML, OAuth 2.0, OpenID Connect.

#### Contras
- Precisa compartilhar as credenciais e outras características -> problemas de segurança e privacidade.
## Tipos de métodos de autorização:
- Mandatory Access Control (MAC)
- Discretionary Access Control (DAC)
- Role-Based Access Control (RBAC)
- Attribute-Based Access Control (ABAC)
