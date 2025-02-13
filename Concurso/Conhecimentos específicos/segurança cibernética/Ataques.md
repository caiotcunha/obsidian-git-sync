Entre os fatores que podem tornar uma aplicação vulnerável estão o sistema operacional, o servidor web/aplicativo, o sistema de gerenciamento de banco de dados (SGBD), as API e todos os componentes, ambientes de tempo de execução e bibliotecas.

Como exemplo de melhor prática, o OWASP recomenda que os responsáveis por segurança de uma aplicação monitorem continuamente fontes como CVE (common vulnerability and exposures) e NVD (national vulnerability database) em busca de vulnerabilidades nos componentes usados na aplicação.


# Documentos



# OWASP SAMM

Na verdade, o OWASP SAMM (Software Assurance Maturity Model) é um modelo de maturidade que ajuda as organizações a formularem e implementarem uma estratégia de segurança de software adaptada aos riscos específicos do negócio. O objetivo principal do SAMM é fornecer uma estrutura para a medição e melhoria das práticas de segurança no desenvolvimento de software.

# OWASP top 10

## Broken Access Control:
Usuários com diferentes permissões devem poder acessar coisas diferentes. Essa vulnerabilidade é relacionada a passar por uma autorização sem poder. Geralmente acontece através de IDOR (Insecure Direct Object Reference), quando o programador expõe inadequadamente um objeto.

Podem ser categorizados em dois tipos:
1. Horizontal Privilege Escalation: Ocorre quando um usuário pode fazer uma ação ou acessar dados de outro com as mesmas permissões.
2. Vertical Privilege Escalation: Ocorre quando um usuário pode fazer uma ação ou acessar dados de outro com maiores permissões.

Como prevenir:
- Exceto para recursos públicos, negue como padrão
- Implemente controles de acesso uma vez e reutilize ele ao longo da aplicação, incluindo minimizar o uso de CORS ( Cross-Origin Resource Sharing )
- O modelo de controle de acesso deve reforçar propriedade de arquivos, ao invés de todo usuário poder ler, modificar, criar ou deletar qualquer arquivo
- Modelos de aplicações devem ter limites diferentes
- Desative a listagem de diretorios em servidores web e garanta que metadata e arquivos de backup não estão presentes na raiz da web
- Alerte o admin quando tiverem muitas tentativas falhas de login
- Coloque um limite de requisições para a api para diminuir o dano de ferramentas de ataque automático
- O servidor deve invalidar as sessões depois do logout. Stateless JWT tokens devem ser de vida curta

## Criptographic Failure:
Falta ou uso inadequado da criptografia. Sem a criptografia para dados em movimento, o sistema fica vulnerável a ataques do tipo "man in the middle". Também é necessário criptografar os dados em repouso para evitar possíveis ataques.
	1. É comum dados serem armazenados em databases ou em flat-file (programas menores)
Como prevenir:
- Classify data processed, stored, or transmitted by an application. Identify which data is sensitive according to privacy laws, regulatory requirements, or business needs.
- Don't store sensitive data unnecessarily. Discard it as soon as possible or use PCI DSS compliant tokenization or even truncation. Data that is not retained cannot be stolen.
- Make sure to encrypt all sensitive data at rest.
- Ensure up-to-date and strong standard algorithms, protocols, and keys are in place; use proper key management.
- Encrypt all data in transit with secure protocols such as TLS with forward secrecy (FS) ciphers, cipher prioritization by the server, and secure parameters. Enforce encryption using directives like HTTP Strict Transport Security (HSTS).
- Disable caching for response that contain sensitive data.
- Apply required security controls as per the data classification.
- Do not use legacy protocols such as FTP and SMTP for transporting sensitive data.
- Store passwords using strong adaptive and salted hashing functions with a work factor (delay factor), such as Argon2, scrypt, bcrypt or PBKDF2.
- Initialization vectors must be chosen appropriate for the mode of operation. For many modes, this means using a CSPRNG (cryptographically secure pseudo random number generator). For modes that require a nonce, then the initialization vector (IV) does not need a CSPRNG. In all cases, the IV should never be used twice for a fixed key.
- Always use authenticated encryption instead of just encryption.
- Keys should be generated cryptographically randomly and stored in memory as byte arrays. If a password is used, then it must be converted to a key via an appropriate password base key derivation function.
- Ensure that cryptographic randomness is used where appropriate, and that it has not been seeded in a predictable way or with low entropy. Most modern APIs do not require the developer to seed the CSPRNG to get security.
- Avoid deprecated cryptographic functions and padding schemes, such as MD5, SHA1, PKCS number 1 v1.5 .
- Verify independently the effectiveness of configuration and settings.

## Injection
A aplicação interpreta um input digitado pelo usuário como comando ou parâmetro. Esse ataque depende muito de qual tecnologia é utilizada e como o programa interpreta o input.
1. SQL injection: Ocorre quando o input do usuário é passado para uma query no SQL. Então, um atacante pode manipular o resultado da query roubando dados sensíveis ou alterando dados no banco de dados.
2. Command Injection: Ocorre quando o input do usuário é passado para os comandos do sistema. Como resultado, um atacante pode executar quais comandos quiser nos servidores da aplicação, o que pode leva-los a ter acesso ao sistema.

Como prevenir:
1. Utilizar uma lista de permitidos: utilizar uma lista de inputs ou caracteres permitidos e comparar o input do usuário a eles.
2. Quebrar o input: processar o input do usuário de forma a remover os caracteres perigosos. Acrescentando, por exemplo, caracteres de escape para os caracteres especiais

## Insecure Design
 refere-se a vulnerabilidades que são inerentes à arquitetura da aplicação. A melhor forma de impedir que isso aconteça é seguir um desenvolvimento que possua ciclos de desenvolvimento de segurança (SSDLC).

Como prevenir:
- Secure Development Lifecycle: adotar um ciclo de desenvolvimento de segurança de forma a trabalhar nela durante todo o ciclo de vida do projeto. Existem diferentes metodologias recomendadas como: OWASP SAMM
- Secure design: é uma cultura e metodologia de avaliação constante de ameaças e garantia da robustez do código
- Establish and use a secure development lifecycle with AppSec professionals to help evaluate and design security and privacy-related controls
- Establish and use a library of secure design patterns or paved road ready to use components
- Use threat modeling for critical authentication, access control, business logic, and key flows
- Integrate security language and controls into user stories
- Integrate plausibility checks at each tier of your application (from frontend to backend)
- Write unit and integration tests to validate that all critical flows are resistant to the threat model. Compile use-cases _and_ misuse-cases for each tier of your application.
- Segregate tier layers on the system and network layers depending on the exposure and protection needs
- Segregate tenants robustly by design throughout all tiers
- Limit resource consumption by user or service

## Security Misconfiguration
O software foi configurado de maneira errada deixando brechas de segurança.

## Vulnerable and Outdated Components
Componentes (ou versões de componentes) com vulnerabilidades conhecidas. Existem softwares que podem ajudar na busca por essas vulnerabilidades. Existem sites com exploits para vulnerabilidades conhecidas.

## Identification and Authentication Failures
Autenticação e identificação são usados para quase todas as aplicações web. Se um atacante conseguir achar falhas no mecanismo de autenticação ele pode ganhar acesso à conta do usuário. Credenciais e cookies de sessão fracos são vulneráveis a ataques.

Como prevenir:
- Where possible, implement multi-factor authentication to prevent automated credential stuffing, brute force, and stolen credential reuse attacks.
- Do not ship or deploy with any default credentials, particularly for admin users.
- Implement weak password checks, such as testing new or changed passwords against the top 10,000 worst passwords list.
- Align password length, complexity, and rotation policies with National Institute of Standards and Technology (NIST) 800-63b's guidelines in section 5.1.1 for Memorized Secrets or other modern, evidence-based password policies.
- Ensure registration, credential recovery, and API pathways are hardened against account enumeration attacks by using the same messages for all outcomes.
- Limit or increasingly delay failed login attempts, but be careful not to create a denial of service scenario. Log all failures and alert administrators when credential stuffing, brute force, or other attacks are detected.
- Use a server-side, secure, built-in session manager that generates a new random session ID with high entropy after login. Session identifier should not be in the URL, be securely stored, and invalidated after logout, idle, and absolute timeouts.

## Software and Data Integrity Failures
Integridade é a capacidade de certificar que um dado permanece original. Aplicações baixadas da web geralmente possuem um hash que pode ser comparado para garantir a integridade do programa.
	1. Para o caso de software podemos usar Subresource Integrity (SRI) para comparar os hashs.

## Security Loggin and Monitoring Failures
 Cada ação do usuário deve ser impressa em algum lugar. É importante ter esse controle para, no caso de um ataque, poder determinar o tamanho do dano e medidas para combater. Importante para saber se o atacante ainda tem acesso à rede.

Como prevenir:
- Use digital signatures or similar mechanisms to verify the software or data is from the expected source and has not been altered.
- Ensure libraries and dependencies, such as npm or Maven, are consuming trusted repositories. If you have a higher risk profile, consider hosting an internal known-good repository that's vetted.
- Ensure that a software supply chain security tool, such as OWASP Dependency Check or OWASP CycloneDX, is used to verify that components do not contain known vulnerabilities
- Ensure that there is a review process for code and configuration changes to minimize the chance that malicious code or configuration could be introduced into your software pipeline.
- Ensure that your CI/CD pipeline has proper segregation, configuration, and access control to ensure the integrity of the code flowing through the build and deploy processes.
- Ensure that unsigned or unencrypted serialized data is not sent to untrusted clients without some form of integrity check or digital signature to detect tampering or replay of the serialized data


## Server-Side Request Forgery (SSRF)
Ocorre quando um atacante força a aplicação web a mandar requisições para lugares arbitrários enquanto mantém controle do conteúdo delas. Geralmente relacionado a aplicações web que usam serviços terceirizados.


# Ataques

## Spoofing
Esse termo refere-se a uma técnica de ataque em que o invasor finge ser outra pessoa ou dispositivo, mascarando sua identidade verdadeira. O objetivo principal do **spoofing** é enganar sistemas, usuários ou dispositivos para obter acesso não autorizado a informações ou a uma rede.
Exemplos:
- **IP Spoofing:** O invasor envia pacotes com um endereço de IP falsificado para parecer que estão vindo de uma fonte confiável.  
- **Email Spoofing:** O invasor falsifica o endereço de remetente de um email para parecer que a mensagem está vindo de uma fonte confiável.
- **ARP Spoofing:** O invasor envia mensagens ARP falsas na rede local, associando seu endereço MAC com o IP de um dispositivo legítimo.
- **Access Point Spoofing:** O invasor identifica o nome da rede e se passa por ela, fazendo com que as pessoas se conectem àquele ponto de acesso malicioso e assim a rede seja invadida.

## Leakware/doxware 
Leakware ou doxware é um ransomware que rouba, ou exfiltra, dados confidenciais e **ameaça publicá-los.**

## APT (advanced persistent threats)
Esses são ataques sofisticados e direcionados, que buscam infiltrar-se em uma rede por longos períodos para extrair informações sensíveis. Diferente de ataques comuns, eles não são rápidos e não têm como objetivo causar danos imediatos, mas sim realizar espionagem e roubo de dados de forma discreta e prolongada.

## Phising
Phishing é um tipo de ataque cibernético que usa e-mails, mensagens de texto, telefonemas ou sites fraudulentos para enganar as pessoas a compartilhar dados confidenciais, baixar malware ou se expor a crimes cibernéticos de outras formas. Ataques de phishing são uma forma de engenharia social.

Tipos de phising:
- spear phishing: tem como alvo um grupo específico ou tipo de indivíduo, como os administradores de sistema de uma empresa
- whaling: tem como alvo um CEO ou CFO de um setor ou negócio específico.

## WLAN Scanners
São ataques de vigilância onde os invasores **circulam fisicamente** por regiões onde desejam realizar esses ataques e **descobrem** quais as redes que existem por ali, bem como equipamentos físicos através dos quais podem realizar as invasões posteriormente.

## cross-site scripting (XSS)
Esse ataque ocorre quando um atacante consegue injetar scripts maliciosos em páginas web visualizadas por outros usuários. A principal característica do XSS é a capacidade de executar scripts no contexto do navegador da vítima, explorando a confiança que o navegador tem no conteúdo da página web.

tipos:
- **Reflected XSS:** Os scripts maliciosos são refletidos de volta à vítima pelo servidor da web, geralmente através de links ou formulários.
- **Stored XSS:** Os scripts maliciosos são armazenados no servidor (por exemplo, em um banco de dados) e são executados quando a vítima acessa o conteúdo comprometido.
- **DOM-based XSS:** A vulnerabilidade ocorre no lado do cliente, onde scripts maliciosos são executados diretamente no navegador, manipulando o Document Object Model (DOM).

 ## Cross-Site Request Forgery (CSRF)
 é uma técnica de exploração de vulnerabilidade em que um atacante induz um usuário legítimo a executar ações indesejadas em um sistema web onde o usuário está autenticado. Este ataque tira proveito da confiança que o site alvo deposita no navegador do usuário.
 
## **DNS cache snooping**
é um tipo de ataque que explora a capacidade de um servidor DNS de responder a consultas. O objetivo é determinar se um determinado registro DNS está presente no cache do servidor, o que pode indicar que outro usuário solicitou aquela informação recentemente. Isso pode ser útil para um atacante saber quais sites são acessados por usuários de uma rede.

DAST é uma abordagem de testes de segurança que se concentra em descobrir vulnerabilidades em aplicações enquanto elas estão sendo executadas. Diferente dos testes estáticos (SAST), que analisam o código-fonte, DAST envolve a análise dinâmica dos binários e do comportamento da aplicação em tempo real.

A **lógica difusa** é uma técnica matemática usada para lidar com a incerteza e a imprecisão, sendo particularmente útil em situações onde as condições não são claramente definidas. Em testes dinâmicos, a lógica difusa pode ser aplicada para detectar padrões anômalos e potenciais falhas de segurança analisando o comportamento dos binários. Portanto, a afirmação de que "a lógica difusa é uma das técnicas utilizadas em testes dinâmicos (DAST) para tentar detectar falhas de segurança em binários" está correta.

O **STP** é um protocolo de rede usado principalmente para evitar loops em redes locais (LANs). Ele assegura que exista uma única trajetória ativa entre dois dispositivos na rede, evitando ciclos redundantes que poderiam causar quedas no desempenho ou mesmo o colapso da rede.

Os dispositivos na rede, como switches e roteadores, utilizam mensagens chamadas **Bridge Protocol Data Units (BPDUs)** para trocar informações sobre a topologia da rede. Essas mensagens são fundamentais para o funcionamento do STP.

Em um **ataque ao STP**, um invasor pode enviar BPDUs falsificadas para manipular a topologia da rede. Por exemplo, o atacante pode enviar um BPDU indicando uma mudança de configuração ou topologia, fazendo com que os switches recalculam a árvore de abrangência. Isso pode resultar na interrupção do tráfego de rede ou na criação de loops, causando degradação de serviço ou mesmo falhas totais.
