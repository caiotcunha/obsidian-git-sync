Analistas de segurança cibernética devem se preparar para qualquer tipo de ataque. É seu trabalho proteger os ativos da rede da organização. Para fazer isso, os analistas de segurança cibernética devem primeiro identificar:

- **Ativos** - qualquer coisa de valor para uma organização que deve ser protegida, incluindo servidores, dispositivos de infraestrutura, dispositivos finais e o maior ativo, dados.
- **Vulnerabilidades** - Uma fraqueza em um sistema ou em seu design que pode ser explorada por um agente de ameaça.
- **Ameaças** - Qualquer perigo potencial para um ativo.


## identificar ativos
O gerenciamento de ativos consiste em inventários de todos os ativos e, em seguida, desenvolver e implementar políticas e procedimentos para protegê-los. Além disso, as organizações precisam identificar onde os ativos de informações essenciais estão armazenados e como o acesso é obtido a essas informações. Os ativos de informação variam, assim como as ameaças contra eles.

## Classificação dos ativos
A classificação de ativos atribui todos os recursos de uma empresa a um grupo, com base em características comuns. As informações mais importantes precisam receber o nível mais alto de proteção e ainda podem exigir um tratamento especial.

### Etapa 1
Determinar a categoria de identificação de ativos adequada:
- Ativos de informações
- Ativos de software
- Ativos físicos
- Serviços

### Etapa 2
Estabeleça a responsabilização, identificando o proprietário de todos os ativos de informações e de softwares de aplicativos:
- Identificar o proprietário de todos os ativos de informações
- Identificar o proprietário de todo o software de aplicação

### Etapa 3
Determinar os critérios de classificação:
- Confidencialidade
- Valor
- Tempo
- Direitos de acesso
- Destruição

### Etapa 4
Implemente um esquema de classificação:
- Adotar uma maneira uniforme de identificação de informações para assegurar a proteção uniforme

## Padronização dos ativos
Os padrões do ativo identificam produtos de hardware e software específicos usados e suportados pela empresa.

Quando há uma falha, a ação imediata ajuda a manter o acesso e a segurança. Se uma empresa não padronizar sua seleção de hardware, provavelmente será difícil o pessoal encontrar um componente de reposição. Além de exigirem mais conhecimento para serem gerenciados, ambientes não padronizados aumentam o custo com contratos de manutenção e inventário.

### Estágios do ciclo de vida dos ativos
1. Aquisição
2. Implantação
3. Utilização
4. Manutenção
5. Eliminação

## Identifique vulnerabilidades
A identificação de ameaças fornece a uma organização uma lista de prováveis ameaças para um ambiente específico. Ao identificar ameaças, é importante fazer várias perguntas:
- Quais são as possíveis vulnerabilidades de um sistema?
- Quem pode querer explorar essas vulnerabilidades para acessar ativos de informações específicos?
- Quais são as consequências se as vulnerabilidades do sistema forem exploradas e os ativos forem perdidos?

## Identifique ameaças
- **Roteador de borda** - A primeira linha de defesa é conhecida como um roteador de borda (R1 na figura). O roteador de borda tem um conjunto de regras especificando qual tráfego ele permite ou nega. Ele passa todas as conexões que se destinam à LAN interna para o firewall.
- **Firewall** - A segunda linha de defesa é o firewall. O firewall é um dispositivo de ponto de verificação que executa filtragem adicional e rastreia o estado das conexões. Ele nega o início de conexões de redes externas (não confiáveis) para a rede interna (confiável), enquanto permite que usuários internos estabeleçam conexões bidirecionais com as redes não confiáveis. Ele também pode executar autenticação de usuário (proxy de autenticação) para conceder aos usuários remotos externos acesso a recursos de rede interna.
- **Roteador interno** - Outra linha de defesa é o roteador interno (R2 na figura). Ele pode aplicar regras de filtragem finais no tráfego antes de ser encaminhado para seu destino.
Os roteadores e firewalls não são os únicos dispositivos que são usados em uma abordagem de defesa profunda. Outros dispositivos de segurança incluem IPS (Intrusion Prevention Systems), Proteção Avançada contra Malware (AMP), sistemas de segurança de conteúdo da Web e de e-mail, serviços de identidade, controles de acesso à rede e muito mais.

Na abordagem de segurança em camadas de defesa profunda, as diferentes camadas trabalham juntas para criar uma arquitetura de segurança na qual a falha de uma salvaguarda não afeta a eficácia das outras salvaguardas.

## Estratégias de Defesa em Profundidade
Se uma empresa tem apenas uma medida de segurança para proteger dados e informações, os criminosos digitais precisam passar por uma única defesa para roubar informações ou causar outros danos. Para garantir que as informações e os dados permaneçam disponíveis, uma empresa precisa criar diferentes camadas de proteção.

1. Sobreposição: Para garantir que as informações e os dados permaneçam disponíveis, uma empresa precisa criar diferentes camadas de proteção.Uma abordagem em camadas oferece a proteção mais abrangente porque, mesmo que os criminosos cibernéticos penetrem em uma camada, eles ainda precisam enfrentar várias outras defesas.
2. Limitação: Limitar o acesso aos dados e às informações reduz a possibilidade de uma ameaça. Uma empresa deve restringir o acesso para que os usuários tenham apenas o nível de acesso necessário para fazer o seu trabalho.
3. Diversidade: Se todas as camadas protegidas fossem as mesmas, não seria muito difícil, para os criminosos virtuais, realizar um ataque bem-sucedido. As camadas devem ser diferentes para que, se uma camada for penetrada, a mesma técnica não funcionará em todas as outras, o que comprometeria todo o sistema. Uma empresa pode usar diferentes algoritmos de criptografia ou sistemas de autenticação para proteger os dados em diferentes estados.
4. Ofuscação: A ofuscação de informações também pode proteger dados e informações. Uma empresa não deve revelar informações que os criminosos virtuais podem usar para descobrir a versão do sistema operacional em execução em um servidor ou o tipo de equipamento que ele usa.
5. Simplicidade: A complexidade não garante, necessariamente, a segurança. Se uma empresa implementar sistemas complexos que são difíceis de entender e de solucionar problemas, o “tiro pode sair pela culatra”. Se os funcionários não entenderem como configurar uma solução complexa corretamente, pode ser tão fácil quando em uma solução mais simples para os criminosos virtuais comprometerem esses sistemas.

## Gerenciamento de configurações
O gerenciamento de configuração refere-se à identificação, controle e auditoria da implementação e de quaisquer alterações feitas à linha de base estabelecida de um sistema. A configuração da linha de base inclui todas as definições definidas para um sistema que fornecem a base para todos os sistemas semelhantes, como um tipo de modelo.

## Arquivos de log
Um log registra todos os eventos que ocorrem. Entradas de log compõem um arquivo de log e uma entrada de log contém todas as informações relacionadas a um evento específico. Registros precisos e completos são muito importantes na segurança digital.

Com o aumento do número de arquivos de log gerados para fins de segurança do computador, a empresa deve considerar um processo de gerenciamento de logs. O gerenciamento de dados do log de segurança do computador deve determinar os procedimentos para o seguinte:
- Gerando arquivos de log
- Transmissão de arquivos de log
- Armazenamento de arquivos de log
- Análise de dados
- Descartando dados de log

## Registros do sistema operacional e registros de segurança do aplicativo
- Logs do sistema operacional: O sistema operacional registra eventos de registro que estão vinculados a ações relacionadas ao sistema operacional. Eventos do sistema incluem o seguinte:
	- Solicitações do cliente e respostas do servidor, como autenticações de usuário bem-sucedidas
	- Informações de uso que contêm o número e o tamanho das transações em um determinado período de tempo
- Segurança das aplicações: As empresas usam software de segurança pela rede ou pelo sistema para detectar atividade mal-intencionada. Esse software gera um log de segurança para fornecer dados de segurança do computador. Os logs são úteis para a realização de análise de auditoria e para a identificação de tendências e de problemas no longo prazo. Os logs também permitem que uma empresa forneça documentação que mostre que está em conformidade com as leis e os requisitos regulatórios.

## Analisadores de protocolo
Os packet analyzers (ou analisadores de pacotes) interceptam e registram o tráfego de rede. O packet analyzer captura cada pacote, mostra os valores de vários campos no pacote e analisa o conteúdo. Um sniffer pode capturar o tráfego em redes com e sem fio.

Packet analyzers executam as seguintes funções:
- Log de tráfego
- Análise de problemas de rede
- Detecção de uso indevido da rede
- Detecção de tentativas de invasão da rede
- Isolamento do sistema explorado

## Políticas de Negócios
Políticas de negócios são as diretrizes que são desenvolvidas por uma organização para governar suas ações. As políticas definem padrões de comportamento correto para a empresa e seus funcionários. Na rede, as políticas definem as atividades permitidas na rede. Isso define uma linha base de uso aceitável. Se um comportamento que viola a política for detectado na rede,, é possível que tenha ocorrido uma violação de segurança.
1. Políticas da empresa
2. Políticas de funcionários
3. Políticas de segurança

## Política de Segurança
![[política de segurança.png]]

## Políticas de BYOD
Importante ter regras rígidas de segurança para oferecer suporte para BYOD (Traga seu próprio dispositivo) porque, apesar das grandes vantagens para a empresa, esses dispositivos podem ser vetores de ataque.
![[byod.png]]

## Conformidade regulatória e de padrões
Há também regulamentos externos em relação à segurança da rede. Os profissionais de segurança de rede devem estar familiarizados com as leis e códigos de ética que são vinculativos para os profissionais de Segurança de Sistemas de Informação (INFOSEC). Muitas organizações são obrigadas a desenvolver e implementar políticas de segurança. Os regulamentos de conformidade definem o que as organizações são responsáveis pelo fornecimento e a responsabilidade caso não cumpram. Os regulamentos de conformidade que uma organização é obrigada a seguir dependem do tipo de organização e dos dados que a organização manipula.