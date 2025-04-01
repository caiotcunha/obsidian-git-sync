# Controles de acesso físico
Controles de acesso físico são barreiras reais implantadas para evitar o contato direto com os sistemas. A meta é prevenir que usuários não autorizados acessem fisicamente as instalações, equipamentos e outros ativos organizacionais.

Por exemplo, o controle de acesso físico determina quem pode entrar (ou sair), onde pode entrar (ou sair) e quando pode entrar (ou sair).

Aqui estão alguns exemplos de controles de acesso físicos:

- Guardas para monitorar a instalação
- Cercas para proteger o perímetro
- Detectores de movimento para detectar objetos em movimento
- Bloqueios de laptop para proteger equipamentos portáteis
- Portas trancadas para impedir o acesso não autorizado
- Cartões de acesso para permitir o acesso a uma área restrita
- Cães de guarda para proteger a instalação
- Câmeras de vídeo para monitorar uma instalação coletando e gravando imagens
- Sistemas de entrada estilo Mantrap para escalonar o fluxo de pessoas na área protegida e prender visitantes indesejados
- Alarmes para detectar intrusão

# Controles de acesso lógicos
Controles de acesso lógico são as soluções de hardware e software usadas para gerenciar o acesso aos recursos e sistemas. Essas soluções baseadas em tecnologia incluem ferramentas e protocolos que os sistemas de computador usam para identificação, autenticação, autorização e auditoria.

Exemplos de controle de acesso lógico incluem:

- A criptografia é o processo de pegar o texto claro e criar o texto codificado.
- Os cartões inteligentes possuem um microchip integrado.
- As senhas são strings de caracteres protegidos.
- A biometria se refere às características físicas dos usuários.
- As listas de controle de acesso (ACLs) definem o tipo de tráfego permitido em uma rede.
- Os protocolos são conjuntos de regras que regem a troca de dados entre os dispositivos.
- Os firewalls impedem o tráfego de rede indesejado.
- Os roteadores conectam pelo menos duas redes.
- Os sistemas de detecção de invasão monitoram as atividades suspeitas de uma rede.
- Os níveis de corte são determinados pelos limites permitidos para erros antes de acionar uma bandeira vermelha.

# Controles de acesso Administrativos
Os controles de acesso administrativo são as políticas e procedimentos definidos pelas empresas para implementar e aplicar todos os aspectos de controle de acesso não autorizado. Os controles administrativos focam em práticas pessoais e de negócios.
- As políticas são declarações de intenções.
- Os procedimentos são os passos detalhados necessários para realizar uma atividade.
- As práticas de contratação envolvem as etapas seguidas por uma empresa para encontrar funcionários qualificados.
- As verificações de antecedentes se referem a uma triagem admissional que inclui as informações de verificação de histórico profissional, histórico de crédito e antecedentes criminais.
- A classificação de dados categoriza os dados com base na confidencialidade.
- O treinamento em segurança ensina os funcionários sobre as políticas de segurança de uma empresa
- As análises críticas avaliam o desempenho de trabalho do funcionário

# Controles de acesso administrativo em detalhes
O conceito de controles de acesso administrativo envolve três serviços de segurança: autenticação, autorização e contabilidade (AAA).
Esses serviços fornecem a estrutura principal para controlar o acesso, impedindo o acesso não autorizado a um computador, rede, banco de dados ou outro recurso de dados.
## Autenticação
O primeiro A no AAA representa a autenticação. A autenticação verifica a identidade de um usuário para evitar o acesso não autorizado. Os usuários provam sua identidade com um nome de usuário ou um ID. Além disso, os usuários precisam verificar sua identidade fornecendo um dos seguintes:
- Algo que saibam (como uma senha)
- Algo que tenham (como um token ou cartão)
- Algo que eles são (como uma impressão digital)
No caso da autenticação de dois fatores, que está se tornando cada vez mais a regra, o sistema requer uma combinação de duas das alternativas acima, em vez de apenas uma, para verificar a identidade de alguém.

## Autorização
Serviços de autorização determinam quais recursos os usuários podem acessar, juntamente com as operações que os usuários podem realizar. Alguns sistemas fazem isso usando uma lista de controle de acesso, ou uma ACL. Uma ACL determina se um usuário tem certos privilégios de acesso depois de se autenticar. A autorização também pode controlar _quando_ um usuário tem acesso a um recurso específico.

## Contabilidade
Não relacionada à contabilidade financeira, a contabilidade em AAA acompanha o que os usuários fazem – incluindo o que eles acessam, a quantidade de tempo que acessam os recursos e quaisquer alterações que fazem. O Accounting controla e monitora em tempo real.

# Identificação
Um identificador único assegura a devida associação entre as atividades permitidas e os indivíduos. Um nome de usuário é o método mais comum usado para identificar um usuário. Um nome de usuário pode ser uma combinação alfanumérica, um número de identificação pessoal (PIN), um cartão inteligente ou a biometria, como uma impressão digital, escaneamento da retina ou reconhecimento de voz.
Um identificador único assegura que um sistema possa identificar cada usuário individualmente, portanto, permite que um usuário autorizado realize as ações apropriadas em um recurso específico.

# Gerenciamento de identidade federada
O gerenciamento de identidades federadas refere-se a várias empresas que permitem que seus usuários usem as mesmas credenciais de identificação para obter acesso às redes de todas as empresas do grupo. Infelizmente, isso amplia o escopo e aumenta a probabilidade de um efeito em cascata caso ocorra um ataque.
Em geral, uma identidade federada vincula a identidade eletrônica de um sujeito a sistemas de gerenciamento de identidade separados, como ser capaz de acessar vários sites usando as mesmas credenciais de login social.
O objetivo do gerenciamento de identidades federadas é compartilhar informações de identidade automaticamente entre fronteiras. Na perspectiva do usuário individual, isso significa um início de sessão universal na Web. A forma mais comum de proteger identidades federadas é vincular a habilidade de login a um dispositivo autorizado.

# Métodos de autenticação
- O que você sabe: senhas,PIN,nome de usuário
- O que você tem: catões inteligentes, chaveiros de segurança
- O que você é: reconhecimento facial, biometria

# Autenticação multifator
Como abordamos anteriormente, a autenticação multifatorial usa pelo menos dois métodos de verificação - como uma senha e algo que você tem, por exemplo, um chaveiro de segurança. Isso pode ser levado um passo adiante adicionando algo que você é, como uma verificação de impressão digital. A autenticação multifator pode reduzir a incidência de roubo de identidade online porque significa que saber uma senha não dará aos cibercriminosos acesso à conta de um usuário.

# Autorização
A autorização controla o que um usuário pode e não pode fazer na rede após a autenticação com sucesso. Depois que um usuário prova sua identidade, o sistema verifica quais recursos de rede o usuário pode acessar e o que pode fazer com os recursos.

## Quando implementar a autorização
A autorização usa um conjunto de atributos que descreve o acesso do usuário à rede para responder à pergunta: "Quais privilégios de leitura, cópia, edição, criação e exclusão esse usuário tem?"
A autorização é automática e não exige que os usuários executem etapas adicionais após a autenticação. Os administradores do sistema configuraram a rede para implementar a autorização imediatamente após a autenticação do usuário.

## Usando autorização
Definir as regras de autorização é a primeira etapa no controle de acesso. Uma política de autorização estabelece essas regras. Uma política de associação baseada em grupo define a autorização com base nos membros de um grupo específico. Uma política de nível de autoridade define as permissões de acesso com base na posição de um funcionário na organização.

# Implementação de Auditabilidade
A auditabilidade rastreia uma ação de volta a uma pessoa ou processo que faz essa mudança em um sistema. A auditabilidade então coleta essas informações e relata os dados de uso. A empresa pode usar esses dados para determinadas finalidades, como auditoria ou cobrança. Os dados coletados podem incluir a hora de login para um usuário, independentemente de o login de usuário ter sido bem ou malsucedido ou quais recursos de rede o usuário acessou. Isso permite que uma empresa rastreie as ações, erros e erros durante uma auditoria ou investigação.
A implementação da auditabilidade consiste em tecnologias, políticas, procedimentos e educação. Os arquivos de log fornecem as informações de detalhes com base nos parâmetros escolhidos. As políticas e procedimentos da empresa determinam quais ações devem ser registadas e como os arquivos de log são gerados, revisados e armazenados.
A retenção de dados, eliminação de mídia e requisitos de conformidade geram auditabilidade. Muitas leis exigem a implementação de medidas para proteger diferentes tipos de dados. Essas leis orientam uma empresa sobre o caminho certo para manusear, armazenar e eliminar dados. A educação e conscientização das políticas, procedimentos e leis relacionadas de uma empresa também contribuem com a auditabilidade.

# Segurança Zero Trust
Zero Trust é uma abordagem abrangente para proteger todo o acesso em redes, aplicações e ambientes. Essa abordagem ajuda a proteger o acesso de usuários, dispositivos de usuário final, APIs, IoT, microsserviços, contêineres e muito mais. Ele protege a força de trabalho, as cargas de trabalho e o local de trabalho de uma organização. O princípio de uma abordagem de confiança zero é: “Nunca confie, sempre verifique”. Assumir confiança zero sempre que alguém ou algo solicitar acesso a ativos. Uma estrutura de segurança de confiança zero ajuda a impedir acesso não autorizado, conter violações e reduzir o risco de movimento lateral de um invasor através de uma rede.
Tradicionalmente, o perímetro da rede, ou borda, era o limite entre dentro e fora, ou confiável e não confiável. Em uma abordagem de confiança Zero, qualquer lugar em que uma decisão de controle de acesso seja necessária deve ser considerado um perímetro. Isso significa que, embora um usuário ou outra entidade possa ter passado com êxito o controle de acesso anteriormente, eles não são confiáveis para acessar outra área ou recurso até que sejam autenticados. Em alguns casos, os usuários podem ser obrigados a autenticar várias vezes e de maneiras diferentes, para obter acesso a diferentes camadas da rede.
## Confiança zero para a força de trabalho
Este pilar consiste em pessoas (por exemplo, funcionários, prestadores de serviços, parceiros e fornecedores) que acessam aplicativos de trabalho usando seus dispositivos pessoais ou gerenciados por empresas. Esse pilar garante que apenas os usuários certos e dispositivos seguros possam acessar aplicativos, independentemente da localização.

## Confiança zero para cargas de trabalho
Esse pilar está preocupado com aplicativos que estão sendo executados na nuvem, em data centers e outros ambientes virtualizados que interagem uns com os outros. Ele se concentra no acesso seguro quando uma API, um microsserviço ou um contêiner está acessando um banco de dados dentro de um aplicativo.

## Confiança zero para o local de trabalho
Este pilar se concentra no acesso seguro para qualquer e todos os dispositivos, inclusive na Internet das Coisas (IoT), que se conectam a redes empresariais, como terminais de usuário, servidores físicos e virtuais, impressoras, câmeras, sistemas de AVAC, quiosques, bombas de infusão, sistemas de controle industrial e muito mais.

# Modelos de controle de acesso
Uma organização deve implementar controles de acesso adequados para proteger seus recursos de rede, recursos do sistema de informações e informações.
Um analista de segurança deve entender os diferentes modelos básicos de controle de acesso para ter uma melhor compreensão de como os invasores podem quebrar os controles de acesso.
Outro modelo de controle de acesso é o princípio do privilégio mínimo, que especifica uma abordagem limitada, conforme necessário, para conceder direitos de acesso ao usuário e ao processo a informações e ferramentas específicas. O princípio do privilégio mínimo afirma que os usuários devem receber a quantidade mínima de acesso necessária para desempenhar sua função de trabalho.
Uma exploração comum é conhecida como escalação de privilégios. Nesta exploração, vulnerabilidades em servidores ou sistemas de controle de acesso são exploradas para conceder a um usuário não autorizado, ou processo de software, níveis de privilégio mais altos do que deveriam ter. Depois que o privilégio é concedido, o agente de ameaça pode acessar informações confidenciais ou assumir o controle de um sistema.
## Discretionary access control (DAC)
- Este é o modelo menos restritivo e permite que os usuários controlem o acesso aos seus dados como proprietários desses dados.
- O DAC pode usar ACLs ou outros métodos para especificar quais usuários ou grupos de usuários têm acesso às informações.
Em sistemas que empregam controles de acesso discricionários, o proprietário de um objeto pode decidir quais usuários podem acessar esse objeto e qual acesso específico eles podem ter.
Permissões e listas de controle de acesso podem ser usadas para implementar o controle de acesso discricionário. O proprietário de um arquivo pode especificar quais permissões (como ler, gravar ou executar) outros usuários podem ter. Uma lista de controle de acesso usa regras para determinar qual tráfego pode entrar ou sair de uma rede.

## Controle de acesso obrigatório (MAC)
- Isso aplica o controle de acesso mais rigoroso e é normalmente usado em aplicações militares ou de missão crítica.
- Ele atribui rótulos de nível de segurança às informações e permite que os usuários tenham acesso com base em sua autorização de nível de segurança.
O controle de acesso obrigatório restringe as ações que um usuário pode realizar em um objeto (como um arquivo, uma porta ou um dispositivo). Uma regra de autorização impõe se um usuário pode acessar o objeto.
As organizações usam o controle de acesso obrigatório onde existem diferentes níveis de classificações de segurança. Cada objeto tem uma etiqueta e cada usuário tem uma autorização. Um sistema de controle de acesso obrigatório restringe um usuário com base na classificação de segurança do objeto e na etiqueta anexada ao usuário.

## Controle de acesso baseado em funções (RBAC)
- As decisões de acesso são baseadas nas funções e responsabilidades de um indivíduo dentro da organização.
- Diferentes funções recebem privilégios de segurança e indivíduos são atribuídos ao perfil RBAC para a função.
- As funções podem incluir diferentes posições, classificações de cargo ou grupos de classificações de emprego.
- Também conhecido como um tipo de **controle de acesso não discricionário.**

O controle de acesso baseado em função depende da função ou função de trabalho do usuário. Funções específicas exigem permissões para executar determinadas operações e os usuários adquirem permissões por meio de sua função.
O controle de acesso por função pode funcionar em combinação com controles de acesso discricionários ou obrigatórios, aplicando as políticas de qualquer um deles. O controle de acesso baseado em função ajuda a implementar a administração de segurança em grandes organizações com centenas de usuários e milhares de permissões possíveis. As organizações aceitam amplamente o uso de controle de acesso baseado em função para gerenciar permissões de computador em um sistema ou aplicativo como uma prática recomendada.
## Controle de acesso baseado em atributos (ABAC)
O ABAC permite o acesso com base em atributos do objeto (recurso) a ser acessado, o sujeito (usuário) acessando o recurso e fatores ambientais sobre como o objeto deve ser acessado, como a hora do dia.
## Controle de acesso baseado em regras (RBAC)
- A equipe de segurança de rede especifica conjuntos de regras ou condições associadas ao acesso a dados ou sistemas.
- Essas regras podem especificar endereços IP permitidos ou negados, ou determinados protocolos e outras condições.
- Também conhecido como **RBAC Baseado em Regras.**
O controle de acesso baseado em regras usa listas de controle de acesso para ajudar a determinar se o acesso deve ser concedido. Uma série de regras está contida na lista de controle de acesso e a decisão de conceder acesso depende dessas regras. Por exemplo, uma regra que determina que nenhum funcionário pode ter acesso ao arquivo da folha de pagamento fora do expediente ou nos finais de semana.
Assim como no controle de acesso obrigatório, os usuários não podem alterar as regras de acesso. É importante ressaltar que as organizações podem combinar o controle de acesso baseado em regras com outras estratégias para implementar restrições de acesso. Por exemplo, métodos obrigatórios de controle de acesso podem utilizar uma abordagem baseada em regras para implementação.

## Controle de acesso baseado em tempo (TAC)
TAC Permite o acesso a recursos de rede com base na hora e no dia.

# Sistemas de controle de acesso à rede (NAC)
Network Access Control (NAC) são compatíveis com o gerenciamento de acesso ao aplicar políticas organizacionais relacionadas às pessoas e aos dispositivos que estão tentando acessar a rede. Os sistemas NAC permitem que profissionais de cyberscurity monitorem os usuários e dispositivos conectados à rede e controlem manualmente o acesso conforme necessário.
Os sistemas de controle de acesso à rede oferecem os seguintes recursos:
- Aplicação rápida de políticas de acesso que foram criadas para diferentes condições operacionais.
- Reconhecer e criar perfis de usuários e dispositivos conectados para evitar que softwares mal-intencionados em sistemas não compatíveis causem danos.
- Fornecer acesso seguro aos convidados da rede, geralmente através de portais de registro.
- Avaliar a conformidade do dispositivo com as políticas de segurança por tipo de usuário, tipo de dispositivo e sistema operacional antes de permitir o acesso à rede.
- Atenuar os incidentes de segurança ao bloquear, isolar ou reparar dispositivos não compatíveis.
Como as redes BYOD e IoT expandem muito a superfície de ataque da rede, os recursos de automação do sistema NAC tornam prático o controle focado do acesso à rede por esses dispositivos. O sistema NAC está configurado para impor políticas organizacionais. As políticas relevantes são decretadas para permitir ou negar o acesso à rede de acordo com uma ampla gama de fatores que o sistema NAC detecta nos dispositivos que estão tentando acessar. Sem os sistemas NAC, seria impossível para o pessoal de segurança cibernética avaliar os milhares de dispositivos que poderiam tentar acessar a rede. O NAC é um componente importante de uma arquitetura de segurança de tolerância zero que reforça a conformidade com as políticas de segurança com todos os dispositivos e usuários que tentam acessar a rede.


# Tipos de conta
Uma empresa não deve compartilhar contas de usuários, administradores ou aplicativos privilegiados. A conta de administrador só deve ser usada para administrar um sistema. Se um usuário acessar um site infectado por malware ou abrir um e-mail mal-intencionado enquanto estiver usando a conta de administrador, isso colocaria a empresa em risco. Os administradores devem estar cientes do grupo padrão e das contas de usuário que podem ser instaladas por um sistema operacional. Conhecer essas contas ajudará um administrador a decidir qual delas deve ser permitida e qual delas deve ser desativada. Isso ocorre porque contas padrão, como a conta de convidado ou administrador, podem representar um risco à segurança de sistemas mais antigos, já que os invasores estão familiarizados com as configurações padrão usadas. Para melhorar a segurança, sempre substitua as contas padrão e verifique se todos os tipos de conta exigem uma senha.

É importante gerenciar as contas corretamente para manter a segurança.
- Ao contratar um novo funcionário, crie um perfil de identidade, registre o computador e os dispositivos móveis do funcionário e permita o acesso à rede da empresa. Como provedor de identidade (IdP), a empresa é responsável por autenticar sua identidade.
- Desative ou desative as contas que não são mais necessárias e recupere dados organizacionais ou aplicativos dos dispositivos do usuário.
- Conceda a um usuário o acesso necessário para executar tarefas atribuídas (privilégio mínimo).
- Analise o acesso do usuário para identificar os ajustes de controle de acesso que precisam ser feitos.
- Use as restrições de horário do dia para controlar quando um usuário pode fazer login.
- Use restrições de local para controlar de onde um dispositivo ou usuário pode fazer login.
	- A delimitação geográfica é usada para acionar uma ação quando um usuário entra ou sai de um limite geográfico.
	- A localização geográfica identifica um dispositivo com base em sua localização geográfica.
	- A marcação geográfica adiciona um identificador a algo com base na localização (como uma foto tirada em um smartphone marcada com as coordenadas de onde a foto foi tirada).

## Contas privilegiadas
Os criminosos digitais têm como alvo contas privilegiadas. Por quê? Porque essas são as contas mais poderosas da empresa com acesso elevado e irrestrito aos sistemas. Os administradores usam essas contas para implantar e gerenciar sistemas operacionais, aplicativos e dispositivos de rede.
As organizações devem adotar práticas robustas para proteger contas privilegiadas.
- Identificar e reduzir o número de contas com privilégios
- Aplicação do princípio do privilégio mínimo. O princípio significa que usuários, sistemas e processos só têm acesso a recursos (redes, sistemas e arquivos) que são absolutamente necessários para executar a função atribuída.
- Revogar os direitos de acesso quando os funcionários deixarem ou mudarem de emprego.
- Eliminar contas compartilhadas com senhas que não expiram
- Proteger o armazenamento de senha.
- Eliminar as credenciais compartilhadas por vários administradores
- Alterar automaticamente as senhas de contas com privilégio a cada 30 ou 60 dias
- Registro de sessões com privilégios
- Implementar um processo para alterar senhas incorporadas para scripts e contas de serviço
- Registrar todas as atividades do usuário
- Gerar alertas para comportamento incomum
- Desativar contas inativas com privilégios
- Use a autenticação de vários fatores para todos os acessos administrativos
- Implemente um gateway entre o usuário final e os ativos confidenciais para limitar a exposição da rede a malware.
Proteger e bloquear continuamente contas privilegiadas é fundamental para a segurança da organização. Avalie regularmente esse processo e faça ajustes para melhorar a proteção.

# Controle de acesso de arquivos
Permissões são regras configuradas para limitar o acesso a pastas ou arquivos para um indivíduo ou grupo. Permissões são regras definidas para limitar o acesso a um indivíduo ou grupo. Por exemplo, não devem poder acessar todos os arquivos de um servidor se só precisarem acessar uma única pasta. Pode ser mais fácil fornecer acesso a toda a unidade, mas é mais seguro limitar o acesso apenas à pasta necessária. Esse é o princípio do **menor privilégio** e intimamente ligado ao conceito de acesso "preciso saber". Limitar o acesso aos recursos também impede que os cibercriminosos acessem esses recursos se o computador do usuário for infectado.

## Controle Total
Os usuários podem:
- Veja o conteúdo de um arquivo ou pasta.
- Alterar e excluir arquivos e pastas existentes.
- Criar novos arquivos e pastas.
- Executar programas em uma pasta.

## Modificar
Os usuários podem alterar e excluir os arquivos e as pastas existentes, mas não podem criar novos.
## Ler e executar
Os usuários podem visualizar o conteúdo de arquivos e pastas existentes e podem executar programas em uma pasta.
## Gravação
Os usuários podem criar novos arquivos e pastas e fazer alterações nos arquivos e pastas existentes.
## Leitura
Os usuários podem visualizar o conteúdo de uma pasta e abrir arquivos e pastas.

- Os dados movidos para o mesmo volume manterão as permissões originais. 
- Os dados copiados para o mesmo volume herdarão novas permissões. 
- Os dados movidos para um volume diferente herdarão novas permissões.
- Os dados copiados para um volume diferente herdarão novas permissões.

# Políticas de conta no Windows
Na maioria das redes que usam computadores Windows, um administrador configura o Active Directory com domínios em um servidor Windows. Os computadores Windows que ingressam no domínio se tornam membros do domínio.
O administrador configura uma **política de segurança de domínio** que se aplica a todos os computadores que ingressam no domínio. Por exemplo, as políticas de conta são definidas automaticamente quando um usuário faz login no Windows.
Quando um computador não faz parte de um domínio do Active Directory, o usuário configura políticas por meio da Política de Segurança Local do Windows Em todas as versões do Windows exceto na Home Edition, digite secpol. msc no comando Executar para abrir a ferramenta de Política de Segurança Local.

## Política de senhas
Um administrador pode configurar políticas de conta de usuário, como políticas de senha e políticas de bloqueio.

## Política de bloqueio de conta
Uma política de bloqueio de conta bloqueia uma conta por um período definido quando ocorrem muitas tentativas de login incorretas.

## Política de auditoria
Mais configurações de segurança estão disponíveis selecionando a pasta 'políticas locais' no Windows. Uma política de auditoria cria um arquivo de log de segurança usado para rastrear os seguintes eventos:
- Eventos de login da conta.
- Gestão de contas de auditoria.
- Acesso ao serviço de diretório.
- Acesso a objetos.
- Mudanças de política.
- Privilégio de utilização.
- Acompanhamento de processos.
- Eventos do sistema.

# Gerenciamento de Autenticação
O gerenciamento de autenticação tem como objetivo garantir a entrada segura, proporcionando facilidade de uso.
- Uma **solução de logon único (SSO)** permite que o usuário use um conjunto de credenciais de login para autenticar em vários aplicativos. Dessa forma, o usuário só precisa lembrar uma senha forte. 
- **OAuth** é um padrão que permite que as informações de conta de um usuário sejam usadas por serviços de terceiros, como o Facebook ou o Google.  
- Um **cofre de senha** pode proteger e armazenar as credenciais do usuário com uma única senha forte necessária para acessá-las.
- Muitas empresas implementam a **autenticação baseada em conhecimento (KBA)** para fornecer uma redefinição de senha caso um usuário esqueça sua senha. A KBA é baseada em informações pessoais conhecidas pelo usuário ou em uma série de perguntas.

# Código de autenticação de mensagem baseado em hash (HMAC)
O Código de autenticação de mensagem com base em hash (HMAC) usa uma chave de criptografia com uma função de hash para autenticar um usuário da Web. Muitos serviços da Web usam a autenticação básica, que não criptografa o nome de usuário e a senha durante a transmissão. Usando o HMAC, o usuário envia um identificador com chave privada e um HMAC. O servidor procura a chave privada do usuário e cria um HMAC. O HMAC do usuário deve ser compatível com o calculado pelo servidor.
As VPNs que usam IPsec contam com as funções HMAC para autenticar a origem de cada pacote e fornecer a verificação de integridade de dados.

Os produtos da Cisco usam hash para fins de autenticação de entidade, integridade de dados e autenticidade de dados.
- Os roteadores Cisco IOS usam o hash com chaves secretas de maneira semelhante ao HMAC, para adicionar informações de autenticação às atualizações do protocolo de roteamento.
- Os IPsec gateways e clientes usam os algoritmos hash, como MD5 e SHA-1 no modo de HMAC, para proporcionar a integridade e a autenticidade do pacote.
- As imagens de software Cisco na página da Cisco.com disponibilizam uma soma de verificação de MD5, para que os clientes possam verificar a integridade das imagens baixadas.

# Protocolos e tecnologias de autenticação
Um protocolo de autenticação autentica os dados entre duas entidades para impedir o acesso não autorizado. Um protocolo descreve o tipo de informação que precisa ser compartilhada para se autenticar e se conectar.

- Protocolo de autenticação extensível (EAP): Uma senha do cliente é enviada usando um hash para o servidor de autenticação. O servidor de autenticação tem um certificado (o cliente não precisa de um certificado).
- PAP (Password Authentication Protocol): Um nome de usuário e uma senha são enviados para um servidor de acesso remoto em texto sem formatação. A maioria dos servidores remotos de sistema operacional de rede é compatível com PAP.
- CHAP (Challenge Handshake Authentication Protocol): CHAP valida a identidade de clientes remotos usando uma função de hash unidirecional criada pelo cliente. O serviço também calcula o valor esperado de hash. O servidor (o autenticador) compara os dois valores. Se os valores corresponderem, a transmissão continua. CHAP também verifica periodicamente a identidade do cliente durante a transmissão.
- 802.1x: Uma empresa autentica sua identidade e autoriza o acesso à rede. Sua identidade é determinada com base em credenciais ou em um certificado confirmado por um servidor RADIUS.
- RADIUS: Quando a autenticação simples de nome de usuário/senha for necessária, use RADIUS para aceitar ou negar acesso. RADIUS criptografa apenas a senha do usuário do cliente RADIUS para o servidor RADIUS. O nome de usuário, a contabilidade e os serviços autorizados são transmitidos em texto não criptografado. Quando o RADIUS é integrado a um produto, são necessárias medidas de segurança que protegem contra ataques de repetição.
- TACACS+: TACACS + usa TCP como protocolo de transporte. TACACS + criptografa todos os dados (nome de usuário, senha, contabilidade e serviços autorizados) entre o cliente e o servidor. Como os administradores de rede podem definir ACLs, filtros e privilégios de usuário, TACACS + é a melhor escolha para redes corporativas que exigem etapas de autenticação mais sofisticadas e controle sobre atividades de autorização.
- kerberos: Kerberos usa criptografia forte, solicitando que um cliente comprove sua identidade para um servidor, com o servidor, por sua vez, se autenticando no cliente. O servidor Kerberos contém IDs de usuário e senhas com hash para todos os usuários que terão autorizações para serviços de região. O servidor Kerberos também tem chaves secretas compartilhadas com todos os servidores aos quais concederá tíquetes de acesso. A base para a autenticação em um ambiente Kerberos é o tíquete. Os tíquetes são usados em um processo de duas etapas com o cliente. O primeiro tíquete é um tíquete de concessão de tíquete emitido pelo serviço de autenticação para um cliente solicitante. O cliente pode então apresentar esse tíquete ao servidor Kerberos com uma solicitação de tíquete para acessar um servidor específico.  Esse tíquete do cliente para o servidor (também conhecido como tíquete de serviço) é usado para obter acesso ao serviço de um servidor. Como toda a sessão pode ser criptografada, isso elimina a transmissão inerentemente insegura de itens (como senhas) que podem ser interceptados na rede. Os tickets têm o carimbo de hora e expiram, portanto, qualquer tentativa de reutilização de um ticket não será bem-sucedida.

# Aplicações de Funções de Hash Criptográficas
As funções de hash de criptografia nos ajudam a garantir a integridade dos dados e verificar a autenticação. As funções de hash criptográfico são usadas nas seguintes situações:
- Para fornecer prova de autenticidade quando usado com uma chave de autenticação secreta simétrica, como segurança IP (IPsec) ou autenticação de protocolo de roteamento.
- Fornecer autenticação gerando respostas únicas e unidirecionais aos desafios nos protocolos de autenticação.
- Para fornecer prova de verificação de integridade da mensagem (como os usados em contratos assinados digitalmente) e certificados de infraestrutura de chave pública (PKI) (como os aceitos ao acessar um site seguro).
Ao escolher um algoritmo de hash, use o SHA-256 ou superior, pois são os mais seguros atualmente. Evite SHA-1 e MD5 devido a falhas de segurança que foram descobertas.

# Estratégias de controle de acesso
As estratégias de controle de acesso permitem que uma empresa conceda ou restrinja o acesso a um dispositivo ou dados de rede.

# Operação AAA
Uma rede deve ser projetada para controlar quem tem permissão para se conectar a ela e o que eles têm permissão para fazer quando estão conectados. Estes requisitos de design são identificados na política de segurança de rede. A política especifica como administradores de rede, usuários corporativos, usuários remotos, parceiros de negócios e clientes acessam recursos de rede. A política de segurança de rede também pode exigir a implementação de um sistema de contabilidade que rastreia quem iniciou sessão e quando e o que fizeram durante a sessão iniciada. Alguns regulamentos de conformidade podem especificar que o acesso deve ser registrado e os logs mantidos por um determinado período de tempo.
O protocolo AAA (Authentication, Authorization and Accounting) fornece a estrutura necessária para habilitar a segurança de acesso escalável.
Os usuários devem passar pelos 3 passos: Autenticação -> Autorização -> Accounting

# Autenticação AAA
A autenticação AAA pode ser usada para autenticar usuários para o acesso administrativo ou pode ser usada para autenticar usuários para o acesso à rede remota.
A Cisco fornece dois métodos comuns de implementação de serviços AAA.
## Autenticação AAA local
Esse método às vezes é conhecido como autenticação autônoma porque autentica usuários contra nomes de usuário e senhas armazenados localmente, como mostrado na figura. O AAA local é ideal para redes pequenas.

## Autenticação AAA com base em servidor
Esse método se autentica em um servidor AAA central que contém os nomes de usuário e senhas para todos os usuários, conforme mostrado na figura. A autenticação AAA baseada em servidor é apropriada para redes de médio a grande porte.

O AAA centralizado é mais escalável e gerenciável do que a autenticação AAA local e, portanto, é a implementação AAA preferida.
Um sistema AAA centralizado pode manter bancos de dados independentemente para autenticação, autorização e contabilidade. Ele pode aproveitar o Active Directory ou o Lightweight Directory Access Protocol (LDAP) para autenticação de usuário e associação de grupo, mantendo seus próprios bancos de dados de autorização e contabilidade.
Os dispositivos se comunicam com o servidor AAA centralizado usando os protocolos RADIUS (Remote Authentication Dial-In User Service) ou Terminal Access Controller Access Control System (TACACS +).

| Funcionalidade                | TACACS+                                                                 | RADIUS                                                                 |
|-------------------------------|-------------------------------------------------------------------------|-----------------------------------------------------------------------|
| **Arquitetura AAA**           | Separa autenticação, autorização e auditoria (modular).                | Combina autenticação e autorização, mas separa auditoria (menos flexível). |
| **Padrão**                    | Principalmente com suporte Cisco.                                      | Padrão aberto/RFC.                                                   |
| **Transporte**                | Porta TCP 49.                                                          | Portas UDP 1812/1813 ou 1645/1646.                                   |
| **Protocolo CHAP**            | Desafio bidirecional (CHAP).                                           | Desafio unidirecional (resposta do servidor para o cliente).         |
| **Confidencialidade**         | Criptografa todo o corpo do pacote (exceto cabeçalho TACACS+).         | Criptografa apenas a senha; demais dados (usuário, serviços, auditoria) ficam desprotegidos. |
| **Personalização**            | Autorização de comandos de roteador por usuário/grupo.                 | Não suporta autorização granular de comandos.                        |
| **Auditoria**                 | Limitada.                                                              | Abrangente.                                                          |

# Registros de Contabilidade AAA
O AAA centralizado também permite o uso do método de contabilidade. Os registros contábeis de todos os dispositivos são enviados para repositórios centralizados, o que simplifica a auditoria das ações do usuário.
AAA Accounting coleta e relata dados de uso em registros AAA. Esses logs são úteis para auditoria de segurança. Os dados coletados podem incluir os horários de conexão inicial e final, comandos executados, número de pacotes e número de bytes.
Um uso amplamente difundido da contabilidade é combiná-lo com a autenticação AAA. Isso ajuda a gerenciar o acesso a dispositivos de interrede pela equipe administrativa da rede. Contabilidade fornece mais segurança do que apenas autenticação. Os servidores AAA mantêm um registro detalhado de exatamente o que o usuário autenticado faz no dispositivo, conforme mostrado na figura. Isso inclui todos os comandos EXEC e de configuração emitidos pelo usuário. O log contém vários campos de dados, incluindo o nome de usuário, a data e a hora, e o comando real que foi inserido pelo usuário. Esta informação é útil na solução de problemas de dispositivos. Ele também fornece evidências contra indivíduos que realizam ações maliciosas.
Tipos de informações contábeis:
- Contabilidade de Rede: A contabilidade de rede captura informações para todas as sessões PPP (Point-to-Point Protocol), incluindo contagens de pacotes e bytes.
- Contabilidade de Conexão: Contabilidade de conexão captura informações sobre todas as conexões de saída feitas a partir do cliente AAA, como por SSH.
- Contabilidade EXEC: A contabilidade EXEC captura informações sobre sessões de terminal EXEC do usuário (shells do usuário) no servidor de acesso à rede, incluindo nome de usuário, data, horas de início e parada e o endereço IP do servidor de acesso.
- Contabilidade do Sistema: A contabilidade do sistema captura informações sobre todos os eventos no nível do sistema (por exemplo, quando o sistema é reinicializado ou quando a contabilidade é ativada ou desativada).
- Contabilidade de Comando: A contabilidade de comandos captura informações sobre os comandos do shell EXEC para um nível de privilégio especificado, bem como a data e hora em que cada comando foi executado e o usuário que o executou.
- Contabilidade de Recursos: A implementação da Cisco de contabilidade AAA captura o suporte de registro de “iniciar” e “parar” para conexões que passaram pela autenticação do usuário. O recurso adicional de geração de registros de “parada” para conexões que falham na autenticação como parte da autenticação do usuário também é suportado. Esses registros são necessários para que os usuários que empregam registros contábeis gerenciem e monitorem suas redes.