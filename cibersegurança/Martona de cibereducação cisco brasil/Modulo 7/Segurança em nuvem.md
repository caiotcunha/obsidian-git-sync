
# O ambiente virtual
A virtualização beneficia uma empresa ao diminuir o número de máquinas físicas (por exemplo, servidores e estações de trabalho) necessárias no ambiente de TI.

**Máquinas virtuais**
Um hypervisor é um programa de software ou hardware que permite executar vários sistemas operacionais independentes em um sistema físico. Ele é um componente chave da virtualização. Existem dois métodos de virtualização:
- Virtualização de hardware (hypervisor tipo 1) - o sistema operacional convidado é executado diretamente em uma plataforma de hardware, sob o controle do sistema host. 
- Virtualização hospedada (hypervisor tipo II) - um aplicativo em execução na máquina host é usado para criar máquinas virtuais que consistem totalmente em software e não contêm componentes de hardware.
Os ambientes de máquinas virtuais usam um sistema operacional, portanto, eles precisam ser corrigidos. As máquinas virtuais compartilham hardware e são executadas com privilégios muito altos. Esteja ciente de que um invasor que comprometa uma máquina virtual pode comprometer a máquina host.

**Contêineres**
Ao contrário de uma máquina virtual, um contêiner consiste apenas no aplicativo e suas dependências. Um contêiner usa um mecanismo para emulação de sistema operacional. O Docker é uma plataforma aberta que usa a virtualização no SO para distribuir software em pacotes (contêineres). Você pode facilmente mover contêineres e o aplicativo será executado. Um software especializado como o Kubernetes permite gerenciar seus contêineres.
Se um usuário ou aplicativo tiver privilégios elevados em um contêiner, o sistema operacional subjacente poderá ser comprometido.

**infraestrutura de desktops virtuais (VDI)**
Os ambientes de desktop do usuário podem ser armazenados remotamente em um servidor usando thin client ou desktops virtuais. Isso torna muito fácil criar, excluir, copiar, arquivar ou baixar configurações com rapidez em uma rede. A virtualização de desktop requer alta disponibilidade e capacidade de armazenamento.

# Tecnologia na nuvem

As tecnologias baseadas em nuvem permitem que empresas como @Apollo acessem computação, armazenamento, software e servidores pela Internet. Ele move o componente de tecnologia da organização para o provedor de nuvem.
Vamos recapitular do Módulo 1 os três principais modelos de serviços de computação, conhecidos coletivamente como XaaS ("qualquer coisa como serviço").

# computação em nuvem
As classificações da computação em nuvem baseiam-se na implantação dos modelos de serviço.
- nuvem privada
- nuvem publica
- nuvem hibrida
- nuvem comunitária

**A Fog Computing (computação em neblina)** distribui a computação entre o dispositivo e o data center em nuvem. Ela desempenha um papel fundamental em aplicações onde milissegundos são importantes, como veículos autônomos, linhas aéreas e aplicações de manufatura.
Na fog computing, os dados são processados dentro de um gateway de IoT, ou fog node, que fica na rede de área local. Na **edge computing** (computação de borda), os dados são processados no dispositivo ou no sensor sem serem transferidos para um data center.

# Principais ameaças à computação em nuvem
A computação em nuvem é suscetível às muitas ameaças que afetam as redes físicas da empresa. No entanto, o ambiente de nuvem também apresenta ameaças exclusivas.
Por exemplo, se um agente de ameaça comprometer um recurso de nuvem, ele poderá fazer o seguinte:
- Use os recursos de computação em nuvem para atingir outras entidades online.
- Hospede malware em provedores de nuvem respeitados que parecerão inofensivos ou até mesmo legítimos.
- Abusa dos serviços em nuvem para lançar ataques de DDoS, hospedar conteúdo pirata, enviar spam de e-mail e realizar campanhas de phishing.
Algumas ameaças associadas à computação em nuvem:
- Violação de dados: Isso ocorre quando dados confidenciais protegidos são acessados por uma entidade não autorizada.
- Configuração incorreta de nuvem: Isso ocorre quando o recurso de computação em nuvem é configurado incorretamente, tornando-o vulnerável a ataques.
- Estratégia de arquitetura de segurança em nuvem ruim: A segurança da nuvem privada é de responsabilidade da empresa. No entanto, a segurança para nuvens públicas, nuvens híbridas e nuvens da comunidade se torna uma responsabilidade compartilhada entre a empresa e o provedor. Isso pode gerar vulnerabilidades se a arquitetura de segurança da nuvem não for totalmente compreendida ou se for implementada corretamente.
- Credenciais de contas comprometidas: Isso ocorre quando contas de usuário ou privilégios de acesso não são devidamente protegidos e são invadidas por agentes de ameaças. Isso pode levar a uma grande ameaça à segurança se a conta tiver altos privilégios. Por exemplo, em nuvens públicas, uma conta de serviço tem o maior privilégio de acessar e gerenciar ativos de nuvem. Uma conta de serviço sequestrada permitiria que um agente de ameaças controlasse todos os recursos da nuvem.
- Ameaça interna: Isso ocorre quando um funcionário, empreiteiro ou parceiro de negócios compromete o serviço em nuvem de forma mal-intencionada ou não.
- Interface de usuário de software (UI) insegura ou interface de programação de aplicativo (API): A computação em nuvem usa UIs e APIs de software para que os clientes interajam com seus serviços em nuvem. Essas interfaces são os pontos mais expostos à Internet e, portanto, são alvos dos agentes de ameaças.
- Visibilidade limitada do uso da nuvem: Isso ocorre quando o cliente de nuvem não tem visibilidade completa do serviço em nuvem, dificultando a identificação de arquivos seguros ou mal-intencionados.

# Domínios da segurança em nuvem
Há muitos recursos disponíveis que promovem a segurança da computação em nuvem. Um recurso amplamente respeitado e mencionado é o documento Guia de segurança para áreas de foco essenciais na computação em nuvem v4. Desenvolvido pela Cloud Security Alliance (CSA), ele promove as melhores práticas para oferecer garantia de segurança nos domínios da computação em nuvem. Especificamente, o documento abrange 14 domínios de segurança de nuvem.

- Conceitos e arquiteturas de Computação em Nuvem: O domínio define a terminologia da computação em nuvem e detalha as estruturas lógicas e arquitetônicas gerais usadas no documento de orientações de segurança.
- Governança e Gerenciamento de Riscos Corporativos: O domínio descreve quatro áreas afetadas pela computação em nuvem:
	- Governança
	- Gerenciamento de riscos empresariais
	- Gerenciamento de riscos de informações
	- Segurança da Informação
- Questões jurídicas, contratos e descoberta eletrônica: O domínio descreve questões legais associadas à computação em nuvem, incluindo a transferência de dados para a nuvem, a contratação de provedores de serviços em nuvem e o gerenciamento de solicitações de descoberta eletrônica em litígios.
- Gerenciamento de conformidade e auditoria: O domínio descreve os desafios de disponibilizar, medir e comunicar a conformidade quando as empresas migram dos data centers tradicionais para a nuvem.
- Governança da informação: O domínio descreve a necessidade de garantir que o uso de dados e informações esteja em conformidade com as políticas, os padrões e a estratégia da empresa, incluindo os objetivos regulatórios, contratuais e comerciais.
- Plano de gerenciamento e continuidade dos negócios: O domínio descreve a necessidade de proteger o plano de gerenciamento da computação em nuvem (ou seja, os protocolos e os recursos usados para gerenciar a nuvem). Ele também descreve a continuidade dos negócios e os procedimentos de recuperação de desastres que devem ser usados pelo provedor e pelo cliente em nuvem.
- Segurança como Serviço: O domínio abrange os serviços de segurança em constante evolução fornecidos pela nuvem.
- Segurança de infraestrutura: O domínio descreve aspectos específicos da nuvem da segurança de infraestrutura e a base para operar com segurança na nuvem.
- Virtualização e Contêineres: O domínio descreve a necessidade de proteger a tecnologia de virtualização e os ativos virtuais que são a base para a computação em nuvem.
- Resposta a incidentes: O domínio descreve os aspectos críticos da resposta a incidentes (IR), incluindo o ciclo de vida de resposta a incidentes e considerações para respondentes enquanto trabalham em um ambiente de nuvem.
- Segurança de aplicações: O domínio oferece orientação sobre como criar e implantar aplicações com segurança em ambientes de computação em nuvem, especificamente para PaaS e IaaS.
- Segurança e criptografia de dados: A segurança de dados deve ser baseada em risco, pois não é apropriado proteger tudo de forma igual. O domínio descreve os controles relacionados à proteção dos próprios dados, dos quais a criptografia é uma das mais importantes.
- Gerenciamento de identidade, direito e acesso (IAM): O domínio descreve como a identidade de nuvem é diferente do gerenciamento de identidade tradicional.
- Tecnologias relacionadas: O domínio fornece informações e recomendações para tecnologias que dependem quase exclusivamente da computação em nuvem para operar e para tecnologias que não dependem necessariamente da nuvem, mas são comumente vistas em implantações em nuvem.

# Segurança de infraestrutura
O domínio Segurança da infraestrutura descreve aspectos específicos da nuvem da segurança da infraestrutura e a base para operar com segurança na nuvem.
A infraestrutura em nuvem é a base sobre a qual os recursos de nuvem virtualizada, como computação, rede e armazenamento de dados, são construídos e implantados.
Há duas camadas principais de infraestrutura na computação em nuvem:
- A computação física e lógica (CPU, memória, etc), as redes e o armazenamento são combinados para criar uma nuvem.
- A infraestrutura virtual gerenciada por um usuário da nuvem, ou seja, a computação, a rede e os recursos de armazenamento que eles acessam nos pools de recursos.
Devido à natureza da computação em nuvem, as medidas tradicionais de segurança de infraestrutura com base no controle de caminhos de comunicação física e na inserção de dispositivos de segurança não funcionam.
Ferramentas de segurança de nuvem personalizadas incluem dispositivos virtuais e agentes de software que são usados para proteger ambientes virtuais. No entanto, essas ferramentas podem apresentar gargalos ao acessar recursos ou levar à sobrecarga do processador. Portanto, o uso de dispositivos virtuais deve ser cuidadosamente avaliado e implantado.
As redes definidas por software (SDN) permitem novos tipos de controles de segurança e proporcionam um ganho geral para a segurança de rede, incluindo:
- Fácil isolamento de rede sem restrições de hardware físico
- Firewalls SDN (grupos de segurança em computação em nuvem) aplicados a ativos com base em critérios mais flexíveis do que os firewalls de hardware

# Responsabilidades da segurança em nuvem
A computação em nuvem envolve clientes e provedores de serviços de nuvem (CSPs). Portanto, a segurança da nuvem funciona em um modelo de responsabilidade compartilhada.
Um CSP é responsável pelos serviços em nuvem para o cliente, mas o cliente é responsável pelo restante dos serviços. O compartilhamento de responsabilidades varia de acordo com o tipo de implantação da nuvem.
A tabela a seguir exibe a responsabilidade de implementação de segurança entre um cliente e um CSP em diferentes modelos de serviço em nuvem.

|**Responsabilidade de segurança**|**No local**|**IaaS**|**PaaS**|**SaaS**|
|---|---|---|---|---|
|Dados|Cliente|Cliente|Cliente|Cliente|
|Endpoints|Cliente|Cliente|Cliente|Compartilhado|
|Gerenciamento de identidades|Cliente|Cliente|Compartilhado|Compartilhado|
|Aplicação|Cliente|Cliente|Compartilhado|CSP|
|Controle de rede|Cliente|Cliente|Compartilhado|CSP|
|Controle de rede|Cliente|Cliente|CSP|CSP|
|Infraestrutura física|Cliente|CSP|CSP|CSP|

## Políticas de segurança da empresa
Uma empresa pode permitir que os usuários baixem ferramentas de software desconhecidas. Esses aplicativos não autorizados podem aumentar a produtividade dos funcionários ao permitir que eles baixem e usem suas ferramentas de software favoritas. No entanto, aplicativos não monitorados podem criar lacunas de segurança e pontos cegos.
Políticas de segurança da empresa estabelecidas e bem definidas e conscientização dos usuários são formas eficazes de gerenciar aplicativos desconhecidos.

## Segurança em camadas
Os recursos de nuvem podem ser visualizados em quatro camadas: camadas de hardware, infraestrutura, plataforma e aplicações. Estratégias de defesa em profundidade podem ser aplicadas a cada uma dessas camadas.
Algumas opções de segurança em camadas são:
- As plataformas de nuvem normalmente têm segurança integrada na plataforma para proteger os recursos de nuvem do cliente. Por exemplo, alguns CSPs fornecem serviço de DDoS integrado que os clientes não precisam configurar.
- Uma nuvem privada virtual aloca sub-redes privadas que são logicamente isoladas da Internet.
- Embora os clientes não tenham acesso para configurar dispositivos físicos de firewall, os CSPs normalmente oferecem funções equivalentes de firewall, ou firewalls virtuais, como negar e permitir regras e grupos de segurança de host.
- Os logs de fluxo são usados para monitorar o tráfego que atravessa as interfaces de rede individuais.
- As VPNs são usadas para fornecer acesso de usuário remoto aos recursos de nuvem, bem como conexões de site para site usadas em cenários de várias nuvens ou conexões entre uma nuvem e data centers locais.
- Os serviços de gerenciamento de identidade e acesso (IAM) oferecem gerenciamento de credenciais de usuário e gerenciamento de autenticação e autorização de usuário. O uso adequado do IAM é fundamental para proteger os recursos de nuvem contra abusos.

## Microssegmentação
A microssegmentação (também conhecida como hipersegregação) aproveita topologias de rede virtual para executar várias redes menores, mais isoladas e sem incorrer em custos adicionais de hardware. Como as redes são totalmente definidas em software sem muitos dos problemas de endereçamento tradicionais, é muito mais viável executar esses vários ambientes definidos por software.
As técnicas de microssegmentação permitem um controle mais granular da segurança do tráfego e dos fluxos de trabalho na nuvem.

# Desenvolvimento de aplicativos
Para manter a segurança em todas as etapas de desenvolvimento de aplicativos, um processo robusto precisa ser seguido.

**Desenvolvimento e teste**
O software é desenvolvido e atualizado em um ambiente de desenvolvimento, onde pode ser desenvolvido, testado e depurado antes de ser implantado. Um ambiente de desenvolvimento é menos restritivo do que o ambiente ativo e tem um nível de segurança mais baixo. O software de controle de versão ajuda a rastrear e gerenciar alterações no código do software. Os desenvolvedores também podem trabalhar em um ambiente de sandbox para que o código não seja substituído à medida que o desenvolve. 
Durante o teste, os desenvolvedores analisam como o código interage com o ambiente normal. A garantia de qualidade (QA) pode encontrar falhas no software. É muito mais fácil corrigir qualquer defeito encontrado nessa fase.

**Preparo e produção**
Os ambientes de preparação devem corresponder ao ambiente de produção da empresa.
Ao testar em um ambiente intermediário, os desenvolvedores podem verificar se o software é executado sob as configurações de segurança necessárias. Depois que o desenvolvedor executa e testa a segurança, o programa pode ser implantado em produção.

**Provisionamento e desprovisionamento**
Provisionamento é a criação ou atualização de software. O desprovisionamento é sua remoção.
Uma empresa pode usar um portal de autoatendimento para automatizar o desprovisionamento e o provisionamento de software.

# Protegendo técnicas de codificação

Ao codificar aplicativos, os desenvolvedores usam várias técnicas para validar se todos os requisitos de segurança foram atendidos.

- Normalização: A Normalização é usada para organizar dados em um banco de dados e ajudar a manter a integridade dos dados. A normalização converte uma string de entrada em sua forma conhecida mais simples para garantir que todas as strings tenham representações binárias exclusivas e que qualquer entrada maliciosa seja identificada.
- Procedimento armazenado: Um procedimento armazenado é um grupo de instruções SQL pré-compiladas armazenadas em um banco de dados que executam uma tarefa. Se você usar um procedimento armazenado para aceitar parâmetros de entrada de clientes que usam dados de entrada diferentes, reduzirá o tráfego de rede e obterá resultados mais rápidos.
- Ofuscação e Camuflagem: Um desenvolvedor pode usar ofuscação e camuflagem para evitar que o software seja submetido a engenharia reversa. A ofuscação oculta dados originais com caracteres ou dados aleatórios. A camuflagem substitui dados confidenciais por dados fictícios realistas.
- Reutilização de Código: A reutilização de código significa usar o software existente para criar um novo software, economizando tempo e custos de desenvolvimento. No entanto, deve-se tomar cuidado para evitar a introdução de vulnerabilidades.
- SDKs: Bibliotecas de Terceiros e Kits de Desenvolvimento de Software (SDKs) fornecem um repositório de códigos úteis para tornar o desenvolvimento de aplicações mais rápido e mais barato. A desvantagem é que quaisquer vulnerabilidades em SDKs ou bibliotecas de terceiros podem afetar potencialmente muitos aplicativos.

# Validação de entrada
Controlar o processo de entrada de dados é fundamental para manter a integridade do banco de dados. Muitos ataques são executados em um banco de dados e inserem dados malformados. Esses ataques podem confundir, travar ou fazer com que o aplicativo divulgue muitas informações ao invasor. Role para baixo para ver um exemplo – neste caso, um ataque de entrada automatizado.
Por exemplo, os usuários preenchem um formulário usando um aplicativo da Web para assinar uma newsletter. Um aplicativo de banco de dados gera e envia automaticamente confirmações por e-mail para os clientes. Quando os usuários recebem as confirmações de e-mail com um link URL, para confirmar a assinatura, os invasores modificam o link URL. 
Essas modificações podem alterar o nome de usuário, endereço de e-mail ou status de assinatura dos clientes quando eles clicam para confirmar sua assinatura. Dessa forma, quando o e-mail é retornado ao servidor host, ele recebe informações falsas, das quais pode não estar ciente se não verificar cada endereço de e-mail em relação às informações de assinatura.
Os hackers podem automatizar o ataque para inundar o aplicativo da Web com milhares de assinantes inválidos no banco de dados da newsletter.

# Regras de Validação
Uma regra de validação verifica se os dados estão nos parâmetros definidos pelo projetista de banco de dados. Uma regra de validação ajuda a garantir a integridade, a precisão e a consistência dos dados. Os critérios usados na regra de validação incluem o seguinte:
- Tamanho – verifica o número de caracteres em um item de dados
- Formato – verifica se os dados estão de acordo com um formato especificado
- Consistência – verifica a consistência dos códigos nos itens de dados relacionados
- Intervalo – verifica se os dados estão dentro de valores mínimo e máximo
- Dígito de verificação – efetua um cálculo extra para gerar um dígito de verificação para detecção de erros
Dados comprometidos podem ameaçar a segurança de seus dispositivos e sistemas.
Uma **verificação de integridade** pode medir a consistência dos dados em um arquivo, imagem ou registro para garantir que eles não tenham sido corrompidos. A verificação de integridade executa uma **função hash** para obter um instantâneo de dados e, em seguida, usa esse instantâneo para garantir que os dados permaneçam inalterados. Um **checksum** é um exemplo de uma função hash.

# Os estados dos dados
Os Estados do Data Domain descrevem controles relacionados à proteção dos dados, dos quais criptografia e hash são os mais importantes.
Os dados do cliente devem ser protegidos nos três estados a seguir:
- em repouso: Refere-se a dados armazenados. Os dados estão nesse estado quando nenhum usuário ou processo os acessa, solicita ou altera. Os dados inativos podem ser armazenados em dispositivos locais, como um disco rígido em um computador ou uma rede centralizada, como um servidor da empresa. Na computação em nuvem, os dados inativos podem ser armazenados em uma nuvem e podem ser acessados em qualquer computador conectado à Internet, geralmente com assinatura. Todos os dados que não estão em trânsito nem em andamento são considerados dados inativos.
- em trânsito: Refere-se aos dados que estão sendo transmitidos. Portanto, os dados não estão inativos nem estão sendo processados. A transmissão pode ocorrer em um único servidor ao longo das linhas de barramento da placa-mãe, entre dispositivos em uma única rede ou entre redes e, possivelmente, através da Internet. Usar a criptografia e o hash para proteger dados em trânsito é essencial para a computação em nuvem.
- em processamento: Esse estado se refere aos dados durante a entrada inicial, a modificação, o cálculo ou a saída. Os dados estão nesse estado quando não estão em trânsito nem em repouso. Portanto, são os dados que estão sendo processados.

# Criptografia
A criptografia é a ciência de criar e quebrar códigos.
Ao armazenar e transmitir dados criptografados, apenas o destinatário pretendido pode lê-los ou processá-los e somente se eles tiverem o conhecimento adequado do segredo usado no algoritmo de criptografia.
A encriptação é o processo de embaralhamento de dados para impedir que uma pessoa não autorizada leia os dados com facilidade.
Ao habilitar a encriptação, os dados legíveis são chamados de texto simples ou texto claro, enquanto a versão criptografada é chamada de texto criptografado ou texto cifrado. A criptografia converte a mensagem legível de texto claro em texto codificado, que é a mensagem ilegível disfarçada. A descriptografia reverte o processo.
A encriptação também precisa de uma chave, que desempenha um papel crítico para criptografar e descriptografar uma mensagem. A pessoa que possui a chave pode descriptografar o texto codificado para texto claro.
Há duas classes de algoritmos de criptografia:
- Os algoritmos simétricos usam a mesma chave pré-compartilhada para criptografar e descriptografar dados, um método também conhecido como criptografia com chave privada. O Advanced Encryption Standard (AES) é um algoritmo de criptografia simétrica que possui um tamanho de bloco fixo de 128 bits com um tamanho de chave de 128, 192 ou 256 bits. O governo norte-americano usa o AES para proteger as informações confidenciais.
- A criptografia assimétrica, também chamada de criptografia de chave pública, utiliza uma chave de criptografia que é diferente da chave usada para descriptografia. Os algoritmos de criptografia assimétrica incluem Rivest-Shamir-Adleman (RSA), Diffie-Hellman, EIGamal e Elliptic Curve Cryptography (ECC).

# Hashing
O hash é uma ferramenta que garante a integridade dos dados ao considerar dados binários (por exemplo, uma mensagem) e produzir uma representação de comprimento fixo chamada de valor de hash (por exemplo, um message digest).
Hashes são usados para verificar e garantir a integridade dos dados. A ferramenta de hash também pode verificar a autenticação. Ele funciona usando uma função de hash criptográfico para substituir senhas de texto simples ou chaves de criptografia.
Uma função hash criptográfica tem as seguintes propriedades:
- A entrada pode ser de qualquer comprimento.
- A saída tem um comprimento fixo.
- A função hash é unidirecional e não é reversível.
- Dois valores de entrada diferentes quase nunca resultarão no mesmo hash.
O Instituto Nacional de Padrões e Tecnologia (NIST) dos EUA desenvolveu o SHA, o algoritmo especificado no padrão hash seguro (SHS). O NIST publicou o SHA-1 em 1994.
**Observação:** o Message Digest 5 (MD5) foi outro algoritmo de hash popular que não é mais considerado seguro.
O SHA-2 substituiu o SHA-1 com quatro funções hash adicionais para formar a família de SHA:
- SHA-224 (224 bits)
- SHA-256 (256 bits)
- SHA-384 (384 bits)
- SHA-512 (512 bits)
O SHA-2 é um algoritmo mais forte e está substituindo o MD5. SHA-256, SHA-384 e SHA-512 são os algoritmos de próxima geração.

# Proteção de máquinas virtuais
Máquinas virtuais (VMs ou instâncias de VM), como um computador físico, exigem correções, atualizações e medidas antimalware para protegê-las contra ameaças externas. A nuvem oferece opções de segurança adicionais, dependendo das ferramentas específicas disponíveis em uma plataforma em nuvem, para proteger as VMs.

- Planeje o posicionamento da sub-rede: Escolha com cuidado a sub-rede de cada instância para que ela tenha apenas o acesso necessário ao mundo exterior.
- Desative serviços e porta desnecessários: Ative apenas as portas e os serviços necessários para reduzir a exposição desnecessária a ambientes externos.
- Aplique o gerenciamento de contas e políticas: O sistema operacional em uma VM tem uma conta de usuário padrão. Desative todas as contas de usuário padrão e crie contas de usuário com políticas de gerenciamento de conta de práticas recomendadas, como complexidade de senha e acesso com menos privilégios.
- Instale o software antivírus/antimalware e mantenha-o atualizado: Isso pode ser feito através do SO da VM ou estar disponível como um serviço na plataforma de nuvem.
- Instale o firewall/software do host e o IDP/IPS: Isso pode ser feito através do SO da VM ou estar disponível como um serviço na plataforma de nuvem.

# Proteção de VMs contra ataques de propagação de VM

É um processo relativamente fácil criar instâncias de VM na nuvem. No entanto, isso pode levar a um problema de expansão de VM, em que uma empresa tem muitas instâncias de VM que não são gerenciadas corretamente. Por exemplo, é prática comum criar várias instâncias de VM quando um projeto é iniciado apenas para tentar opções diferentes. Algumas dessas VMs podem não ser mais usadas, mas deixadas em execução. Se essas instâncias em execução não forem monitoradas e mantidas, elas poderão se tornar desatualizadas e vulneráveis a ataques.

Um cliente de computação em nuvem deve implementar políticas para registrar e auditar os recursos de nuvem que estão sendo usados. A expansão de VM não apenas apresenta riscos potenciais, mas também consome serviços em nuvem desnecessariamente, como instâncias de VM, armazenamento e endereços IP públicos não atribuídos. Ao registrar o uso de recursos de nuvem, monitorar as VMs em execução e auditar o uso real, uma empresa pode gerenciar e proteger melhor as VMs de que realmente precisa.
