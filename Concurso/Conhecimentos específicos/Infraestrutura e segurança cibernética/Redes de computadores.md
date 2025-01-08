
# Modelos




# Protocolos

- **ICMP (Internet Control Message Protocol):** é um protocolo que os dispositivos de uma rede usam para comunicar problemas com a transmissão de dados. É um protocolo da camada de rede na arquitetura TCP/IP
- **TLS (Transport Layer Security):** Esse protocolo foi criado para aumentar a privacidade e a segurança dos dados em comunicações pela internet. Todo site que usa https usa criptografia TLS. O protocolo tem 3 funções principais: Criptografia, autenticação e integridade. Para usar o TLS o servidor de origem tem que possuir um certificado TLS. No modelo tcp/ip o TLS atua na camada de transporte.
- **IMAP (Internet Message Access Protocol):** é um protocolo usado por clientes de e-mail para acessar mensagens em um servidor de correio, e sua porta padrão é a 143.
- **SMTP (Simple Mail Transfer Protocol):** é um protocolo padrão de envio de mensagens de correio eletrônico através da Internet. Atual na camada de apresentação.
- **IPsec (Internet Protocol Security):** é um conjunto de protocolos desenvolvidos para garantir a segurança das comunicações a partir do protocolo IP, proporcionando integridade, autenticação e criptografia dos dados. IPsec opera em dois modos principais: Modo de Transporte e Modo de Túnel.
	- **No modo de transporte:** o cabeçalho IP original é mantido e a segurança é aplicada ao payload (dados) do pacote IP. Ou seja, o cabeçalho IP original não é alterado, mas os dados (payload) são criptografados e um novo cabeçalho do protocolo AH (Authentication Header) ou ESP (Encapsulating Security Payload) é adicionado. Este modo é geralmente usado para comunicação de host a host.
	- **No modo túnel:** um novo cabeçalho IP é adicionado fora do cabeçalho IP original. Este novo cabeçalho IP é utilizado para rotear o pacote ao destino final, encapsulando o pacote original completo (incluindo o cabeçalho IP original) dentro do pacote IPsec. Este modo é amplamente utilizado para comunicação entre gateways (roteadores, firewalls) e VPNs, pois permite encapsular pacotes IP inteiros.
- **HTTPS:** é um protocolo de comunicação da Internet que protege a integridade e a confidencialidade dos dados durante a interação entre o computador do usuário e o site acessado. Atua na camada de aplicação.



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
O protocolo de segurança WPA2 aumentou a complexidade do predecessor (WPA) e tem sido o padrão para segurança de rede há mais de uma década. Ele usa a cifra AES.WPA2 também tem suas falhas de segurança  em relação a um ataque krack.

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

