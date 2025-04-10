
# Modelos

# Protocolos

- **ICMP (Internet Control Message Protocol):** é um protocolo que os dispositivos de uma rede usam para comunicar problemas com a transmissão de dados. É um protocolo da camada de rede na arquitetura TCP/IP
- **TLS (Transport Layer Security):** Esse protocolo foi criado para aumentar a privacidade e a segurança dos dados em comunicações pela internet. Todo site que usa https usa criptografia TLS. O protocolo tem 3 funções principais: Criptografia, autenticação e integridade. Para usar o TLS o servidor de origem tem que possuir um certificado TLS. No modelo tcp/ip o TLS atua na camada de transporte.
- **IMAP (Internet Message Access Protocol):** é um protocolo usado por clientes de e-mail para acessar mensagens em um servidor de correio, e sua porta padrão é a 143. O IMAP utiliza o **protocolo TCP** na camada de transporte.
- **SMTP (Simple Mail Transfer Protocol):** é um protocolo padrão de envio de mensagens de correio eletrônico através da Internet. Atual na camada de apresentação.
- **IPsec (Internet Protocol Security):** é um conjunto de protocolos desenvolvidos para garantir a segurança das comunicações a partir do protocolo IP, proporcionando integridade, autenticação e criptografia dos dados. IPsec opera em dois modos principais: Modo de Transporte e Modo de Túnel.
	- **No modo de transporte:** o cabeçalho IP original é mantido e a segurança é aplicada ao payload (dados) do pacote IP. Ou seja, o cabeçalho IP original não é alterado, mas os dados (payload) são criptografados e um novo cabeçalho do protocolo AH (Authentication Header) ou ESP (Encapsulating Security Payload) é adicionado. Este modo é geralmente usado para comunicação de host a host.
	- **No modo túnel:** um novo cabeçalho IP é adicionado fora do cabeçalho IP original. Este novo cabeçalho IP é utilizado para rotear o pacote ao destino final, encapsulando o pacote original completo (incluindo o cabeçalho IP original) dentro do pacote IPsec. Este modo é amplamente utilizado para comunicação entre gateways (roteadores, firewalls) e VPNs, pois permite encapsular pacotes IP inteiros.
- **HTTPS:** é um protocolo de comunicação da Internet que protege a integridade e a confidencialidade dos dados durante a interação entre o computador do usuário e o site acessado. Atua na camada de aplicação.
- **Border Gateway Protocol**: It is the language spoken by routers on the Internet to determine how packets can be sent from one router to another to reach their final destination. BGP has worked extremely well and continues to the be protocol that makes the Internet work. Na prática, o BGP (Border Gateway Protocol) é o padrão para roteamento entre sistemas autônomos (SA); ele permite que cada sistema autônomo conheça quais destinos podem ser alcançados por meio de seus SA vizinhos, uma vez que os pares de roteadores trocam informações de roteamento por conexões TCP semipermanentes.
- **POP3 (Post Office Protocol version 3):** Este protocolo é utilizado para recuperar emails de um servidor de correio eletrônico para um cliente. Isso significa que o POP3 é responsável por baixar os emails do servidor para o computador local do usuário, onde eles podem ser lidos offline.
- **DHCP (Dynamic Host Configuration Protocol)**, que é responsável por atribuir endereços IP automaticamente a dispositivos em uma rede. Quando um servidor DHCP é configurado, ele tem um _pool_ de endereços IP, que é uma faixa de endereços que ele pode distribuir para os dispositivos. Um servidor DHCP pode renovar contratos de concessão de IPs já distribuídos. Isso acontece automaticamente para dispositivos que já têm um endereço IP e ainda estão ativos na rede. Normalmente, um servidor DHCP não distribui endereços de sub-redes diferentes a menos que tenha sido configurado especificamente para lidar com várias sub-redes. O tempo de lease em um servidor DHCP corresponde ao período de tempo durante o qual um dispositivo conserva um endereço IP atribuído pelo servidor.
- **TCP**: a finalização de uma conexão TCP (transmission control protocol) ocorre com a realização de dois processos two-way handshake do tipo FIN e ACK.
- **Syslog:** é um protocolo amplamente utilizado para o envio de mensagens de log em uma rede IP. Ele é muito importante para a administração de sistemas, pois permite o envio de mensagens de eventos gerados por dispositivos de rede, servidores, entre outros, para um servidor de logs centralizado. Uma característica fundamental do _Syslog_ é que ele pode utilizar tanto os protocolos **TCP (Transmission Control Protocol)** quanto **UDP (User Datagram Protocol)** para a transmissão dessas mensagens.
- **EAP-TLS (Extensible Authentication Protocol-Transport Layer Security)**: é um método de autenticação utilizado em redes sem fio que proporciona segurança robusta através do uso de **certificados digitais** para autenticar tanto o cliente quanto o servidor. Esse método é altamente seguro porque utiliza a infraestrutura de chaves públicas (PKI) para garantir a autenticidade das partes envolvidas.
- **UDP (user datagram protocol):** é um protocolo da camada de transporte que apresenta verificação de integridade dos segmentos recebidos.
- **OSPF (open shortest path first):** é um protocolo de roteamento do tipo estado de enlace que solicita aos roteadores dentro da mesma área hierárquica que enviem anúncios de estado do enlace, os quais contêm informações a respeito de métricas usadas e interfaces conectadas. O OSPF foi projetado para redes IP e suporta o IPV4 e subredes.
- **STP (Spanning Tree Protocol)** é um protocolo utilizado para evitar loops em redes com switches, não em roteadores. Em redes de computadores, loops podem ocorrer quando há múltiplos caminhos redundantes entre switches, o que pode causar sérios problemas, como tempestades de broadcast.

Para evitar loops de roteamento, os roteadores utilizam outros protocolos, como o **RIP (Routing Information Protocol)**, **OSPF (Open Shortest Path First)** e **EIGRP (Enhanced Interior Gateway Routing Protocol)**. Esses protocolos ajudam a determinar os melhores caminhos para o tráfego de dados e a evitar loops na camada de rede (Layer 3).

O **_leaky bucket_** é um algoritmo utilizado para **controlar a taxa de envio de dados em uma rede**. Ele é visualizado como um balde com um pequeno buraco no fundo, onde os dados são adicionados ao balde a uma taxa variável, mas saem a uma taxa constante, que é a taxa de transmissão da rede.


# Segurança de rede

## Firewalls
É um dispositivo na forma de programa de software ou de hardware que tem por objetivo aplicar uma política de segurança a determinado ponto da rede. Tudo que for entrar ou sair do dispositivo deve passar pelo firewall primeiro e ser autorizado.

Tipos de firewall:
- **Stateless firewall:** opera nas camadas 3 e 4 do modelo osi. Filtra os dados sem levar em conta o estado da conexão, ou seja, todo pacote será analisado de forma a garantir se ele segue a política ou não independente da conexão. Conseguem processar os dados rapidamente, mas não podem aplicar políticas complexas.
- **Stateful firewall:** Opera nas camadas 3 e 4 do modelo osi. Mantém uma tabela com as conexões que foram feitas. Assim, pode ser usado para impedir pacotes de uma determinada fonte automaticamente.
- **Proxy Firewall:** Opera nas camada 7 do modelo osi. Esse tipo de firewall age como intermediário entre as redes privadas e a internet, inspecionando o conteúdo do pacote. Também provê anonimidade para o endereço de ip interno.
- Next-Generation Firewall: Opera da camada 3 a 7 do modelo osi. Oferece inspeção detalhada de pacotes e outras funcionalidade para aumentar a segurança. Tem um IPS (intrusion prevention system) que bloqueia atividade maliciosa em tempo real. Analisa com uma heurística os padrões de ataque e bloqueiam instantaneamente. Tem SSL/TLS decryption.

Regras de firewall podem ser feitas utilizando os componentes básicos de um pacote: endereço de destino, endereço da fonte, porta, protocolo, ação, direção. Essas regras criam uma lista de conexões e interações permitidas.

O uso de firewall UTM (unified threat management) é uma das principais soluções para evitar ataques de flood e de vírus.

Denomina-se three-pronged firewall a utilização de um firewall com três pontos de rede: um para a rede privada, outro para a rede pública, e outro para a DMZ.

## IDS

Intrusion Detection System. Monitora as atividades do sistema em busca de atividades suspeitas. Ao encontrar alerta os administradores da rede.

### Modos de deploy
- Host intrusion detection System (HIDS): São instaladas individualmente nos hosts e são responsáveis por detectar atividade suspeita apenas no host em que foram instaladas. Geram um relatório detalhado das atividades do host, mas podem ser desafiadores de administrar em redes grandes já que consomem muito recurso.
- Network Intrusion Detection System (NIDS): Monitoram todo o trafico de todos os hosts em uma rede, gerando um relatório centralizado da rede como um todo.

### Modos de detecção
- Signature-Based IDS: Preservam as assinaturas dos ataques em uma tabela de forma que se o mesmo ataque acontecer no futuro seja bloqueado automaticamente.
- Anomaly-Based IDS: Aprende o comportamento normal da rede/sistema e detecta se existe algum desvio do comportamento normal. Geralmente gera muitos falsos positivos.
- Hybrid IDS: Combina os dois métodos.

## IPS
Um sistema de prevenção de intrusão (IPS) monitora o tráfego da rede em busca de possíveis ameaças e as bloqueia automaticamente, alertando a equipe de segurança, terminando conexões perigosas, removendo conteúdo malicioso ou acionando outros dispositivos de segurança. IPS filtra pacotes. 


## Identity Access Managment (IAM)

O gerenciamento de identidade fornece soluções para governança de identidade, gerenciamento de acesso e serviços de diretório. O gerenciamento de identidade ajuda as organizações a fortalecer a segurança, simplificar a conformidade, e capturar oportunidades de negócios em acesso móvel e social.

- **Governança de identidade:** gerencia o ciclo de vida da conta do usuário, incluindo direitos e provisionamento.

- Resources: These are objects within a particular service; these include users, roles, groups & policies.
- Identities: Represent certain users permitted and authorised to perform specific roles and actions.
- Entities: A subset of resources which are used for authentication purposes. It includes users & roles.
- Principals: A person or some application requesting to use Amazon resources after signing in.

## Privileged access managment (PAM)
O PAM (privileged access management) é uma solução de segurança de identidade que ajuda a proteger as organizações contra ameaças cibernéticas, monitorando, detectando e impedindo o acesso privilegiado não autorizado a recursos críticos. O PAM funciona por meio de uma combinação de pessoas, processos e tecnologia e oferece visibilidade sobre quem está usando contas privilegiadas e o que está fazendo enquanto está conectado. Limitar o número de usuários que têm acesso a funções administrativas aumenta a segurança do sistema, enquanto camadas adicionais de proteção reduzem as violações de dados por agentes de ameaças.


## Segmentação de rede
Dividir uma rede em seções menores e isoladas. Podem ser divididas por meio de hardware físico ou software.

- Segmentação física (baseada em perímetro): A segmentação física requer dispositivos de hardware — como, por exemplo, [roteadores](https://www.cloudflare.com/learning/network-layer/what-is-a-router/), [comutadores](https://www.cloudflare.com/learning/network-layer/what-is-a-network-switch/) e [firewalls](https://www.cloudflare.com/learning/security/what-is-a-firewall/) — para separar uma rede em seções distintas. Esses dispositivos controlam o tipo de tráfego que tem permissão para entrar e sair de cada seção por meio das políticas de segmentação, que podem ser configuradas de acordo com critérios específicos (como, por exemplo, origem do tráfego, destino e assim por diante).
- Segmentação lógica: A segmentação lógica, ou _segmentação de rede virtual_, usa um software para dividir uma rede em seções menores. Esses segmentos podem ser criados por meio de [sub-redes](https://www.cloudflare.com/learning/network-layer/what-is-a-subnet/), [redes virtuais locais (VLANs)](https://www.cloudflare.com/learning/network-layer/what-is-a-lan/) e esquemas de endereçamento de rede.
	- As **sub-redes** ajudam a dividir uma rede em segmentos menores, permitindo, assim, que o tráfego de rede percorra uma distância menor para chegar ao seu destino sem passar por roteadores desnecessários
	- As **VLANs** dividem o tráfego de uma única rede física em duas redes sem necessidade de diversos roteadores ou conexões de internet para rotear o tráfego de rede para destinos diferentes
	- Os **esquemas de endereçamento de rede** criam segmentos de rede dividindo os recursos de rede entre várias sub-redes [na camada 3](https://www.cloudflare.com/learning/network-layer/what-is-the-network-layer/)

### Microssegmentação
A microssegmentação, ao contrário, é um subconjunto da segmentação de rede que permite a aplicação de controles ainda mais granulares a cargas de trabalho individuais. (Uma carga de trabalho é um programa ou aplicativo — como, por exemplo, um servidor, uma [máquina virtual](https://www.cloudflare.com/learning/cloud/what-is-a-virtual-machine/) ou uma função [sem servidor](https://www.cloudflare.com/learning/serverless/what-is-serverless/) — que usam uma determinada quantidade de memória e recursos de computação.) A microssegmentação faz parte de um modelo de [segurança Zero Trust](https://www.cloudflare.com/learning/security/glossary/what-is-zero-trust/), no qual nenhum usuário ou dispositivo é confiável por padrão.

## Wifi

### Padrões de wifi

#### IEEE 802.11

- 802.11b:
	- frequência: 2,4 GHz
	- 11 Mbit/s
- 802.11g:
	- frequência: 2,4 GHz
	- 54Mbits/s




### modos de segurança de wifi

#### Wired Equivalent Privacy (WEP)
A segurança WEP criptografa com uma chave estática, um dos principais motivos pelos quais não é mais considerado seguro.

#### Wi-Fi Protected Access (WPA)
A segurança WPA (Wi-Fi Protected Access) foi projetada para resolver muitos dos problemas que surgiram com o WEP. O WPA tornou-se o padrão em 2003 e criptografa a chave de acesso à rede dinamicamente, alterando-a regularmente com TKIP (Temporal Key Integrity Protocol).O TKIP criou um ambiente de segurança dinâmico, mas ainda não foi suficiente.Como resultado, uma cifra de substituição (ou algoritmo de criptografia) para a cifra RC4 do WEP e do WPA caiu em desuso por não ser segura.

#### Wi-Fi Protected Access II (WPA2)
O protocolo de segurança WPA2 aumentou a complexidade do predecessor (WPA) e tem sido o padrão para segurança de rede há mais de uma década. Ele usa a cifra AES. WPA2 também tem suas falhas de segurança  em relação a um ataque krack.

#### Wi-Fi Protected Access III (WPA3)
Sua principal característica em comparação com os padrões anteriores é a adoção de chaves criptográficas maiores, de até 256 bits. Mais seguro do que os padrões anteriores, o WPA3 utiliza a tecnologia Simultaneous Authentication of Equals (SAE), que protege contra ataques de força bruta. O WPA3 também tem suporte a pareamento via NFC com criptografia individualizada para cada dispositivo adicionado.

#### WPA-PSK (Wi-Fi Protected Access - Pre-Shared Key)
Foi projetado para uso em redes residenciais ou pequenas empresas onde um servidor de autenticação não é necessário. No WPA-PSK, a autenticação é realizada através de uma chave pré-compartilhada, ou seja, todos os dispositivos na rede utilizam a mesma chave para acessar o ponto de acesso sem fio.

#### WPA-Enterprise
Para uso corporativo requer um servidor de autenticação, normalmente um servidor RADIUS (Remote Authentication Dial-In User Service). Este modo oferece uma segurança mais robusta, pois cada usuário possui credenciais individuais, o que facilita a gestão e a revogação de acessos.


## Tunelamento
Da mesma forma, na rede, os túneis são um método para transportar dados através de uma rede usando [protocolos](https://www.cloudflare.com/learning/network-layer/what-is-a-protocol/) que não são compatíveis com essa rede. O tunelamento funciona encapsulando pacotes: envolvendo pacotes dentro de outros [pacotes](https://www.cloudflare.com/learning/network-layer/what-is-a-packet/). (Pacotes são pequenos pedaços de dados que podem ser reagrupados em seu destino em um arquivo maior).

O tunelamento é frequentemente utilizado nas [redes privadas virtuais (VPNs)](https://www.cloudflare.com/learning/access-management/what-is-a-vpn/). Ele também pode estabelecer conexões eficientes e seguras entre redes, permitir o uso de protocolos de rede não compatíveis e, em alguns casos, permitir aos usuários contornar [firewalls](https://www.cloudflare.com/learning/security/what-is-a-firewall/).


## Security Information and Event Managment system (SIEM)
É uma ferramenta que coleta dados de vários dispositivos da rede e armazena eles em um lugar centralizado. Ele faz correlação entre esses dados investigando incidentes e respondendo a eles em tempo real.
Capacidades:
- Correlation between events from different log sources.
- Provide visibility on both Host-centric and Network-centric activities.
- Allow analysts to investigate the latest threats and timely responses.
- Hunt for threats that are not detected by the rules in place.


**Redes Definidas por Software (SDN)** são uma abordagem de redes que separa o plano de controle do plano de dados. Isso significa que as decisões sobre onde o tráfego deve ser enviado (plano de controle) são separadas do sistema que realmente move os pacotes para seus destinos (plano de dados).

# Ferramentas
- **Webhooks:** permitem conectar aplicativos e sistemas de modo que eles compartilhem dados em tempo real, por meio de funções de retorno de chamada baseadas em HTTP que viabilizam a comunicação orientada por eventos entre os sistemas.

**Serviços Integrados:** Os serviços integrados, também conhecidos como _IntServ_ (Integrated Services), são uma arquitetura utilizada para garantir a qualidade de serviço em redes IP. O principal objetivo é fornecer garantias de desempenho para aplicações que exigem uma determinada qualidade de serviço, como videoconferências e streaming de áudio e vídeo. Nos serviços do tipo integrado, a qualidade do serviço é baseada em fluxos projetados para o IP (Internet protocol).
Os principais padrões de sistemas de arquivos utilizados em mainframes são orientados a registro (record-oriented).

