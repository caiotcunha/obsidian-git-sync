# Firewalls
Um firewall é um sistema ou grupo de sistemas que aplica uma política de controle de acesso entre redes.

**Propriedades comuns do Firewall**

Todos os firewalls compartilham algumas propriedades comuns:

- Os firewalls são resistentes a ataques de rede.
- Firewalls são o único ponto de trânsito entre redes corporativas internas e redes externas porque todo o tráfego flui através do firewall.
- Firewalls reforçam a política de controle de acesso.

**Benefícios do firewall**

Existem vários benefícios do uso de um firewall em uma rede:

- Eles impedem a exposição de hosts, recursos e aplicações sensíveis a usuários não confiáveis.
- Eles sanitizam o fluxo do protocolo, o que impede a exploração de falhas no protocolo.
- Eles bloqueiam dados maliciosos de servidores e clientes.
- Eles reduzem a complexidade do gerenciamento de segurança descarregando a maior parte do controle de acesso à rede para alguns firewalls na rede.

**Limitações do Firewall**

Os firewalls também têm algumas limitações:

- Um firewall mal configurado pode ter sérias conseqüências para a rede, como se tornar um único ponto de falha.
- Os dados de muitos aplicativos não podem ser transmitidos por firewalls com segurança.
- Os usuários podem procurar proativamente maneiras de contornar o firewall para receber material bloqueado, o que expõe a rede a possíveis ataques.
- O desempenho da rede pode diminuir.
- O tráfego não autorizado pode ser encapsulado ou escondido como tráfego legítimo através do firewall.

# Tipos de firewall

## Firewall de filtragem de pacotes (sem estado)

Os firewalls de filtragem de pacotes geralmente fazem parte de um firewall de roteador, que permite ou nega tráfego com base nas informações da Camada 3 e da Camada 4. Eles são firewalls sem estado que usam uma simples pesquisa de tabela de políticas que filtra o tráfego com base em critérios específicos.

Por exemplo, os servidores SMTP escutam a porta 25 por padrão. Um administrador pode configurar o firewall de filtragem de pacotes para bloquear a porta 25 de uma estação de trabalho específica para evitar que ela transmita um vírus de e-mail.

## Firewall com monitoração de estado
**Rede**
Firewalls com estado são as tecnologias de firewall mais versáteis e mais comuns em uso. Os firewalls stateful fornecem filtragem de pacotes stateful usando informações de conexão mantidas em uma tabela de estado. Filtragem com estado é uma arquitetura de firewall classificada na camada de rede. Ele também analisa o tráfego na camada 4 da OSI e na camada 5.

## Firewall de gateway de aplicativo
Um firewall de gateway de aplicação (firewall proxy), conforme mostrado na figura, filtra as informações nas camadas 3, 4, 5 e 7 do modelo de referência OSI. A maior parte do controle e filtragem do firewall é feita em software. Quando um cliente precisa acessar um servidor remoto, ele se conecta a um servidor proxy. O servidor proxy se conecta ao servidor remoto em nome do cliente. Portanto, o servidor só vê uma conexão do servidor proxy.

## Firewall de última geração
Os firewalls de última geração (NGFW) vão além dos firewalls de estado, fornecendo:
- Prevenção de intrusão integrada
- Reconhecimento e controle de aplicativos para ver e bloquear aplicativos arriscados
- Caminhos de atualização para incluir futuros feeds de informações
- Técnicas para lidar com ameaças de segurança em evolução

Outros métodos de implementação de firewalls incluem:

- **Firewalls baseados em host** - é um PC ou servidor com software de firewall em execução nele.
- **Um firewall transparente** - filtra o tráfego IP entre um par de interfaces em ponte.
- **Firewall híbrido** - Uma combinação dos vários tipos de firewall. Por exemplo, um firewall de inspeção de aplicações combina um firewall com estado com um firewall de gateway de aplicativo.

# Benefícios e limitações do firewall de filtragem de pacotes

Os firewalls de filtragem de pacotes geralmente fazem parte de um firewall de roteador, que permite ou nega tráfego com base nas informações da Camada 3 e da Camada 4. Eles são firewalls sem estado que usam uma consulta de tabela de política simples que filtra o tráfego com base em critérios específicos. Por exemplo, os servidores SMTP escutam a porta 25 por padrão. Um administrador pode configurar o firewall de filtragem de pacotes para bloquear a porta 25 de uma estação de trabalho específica para evitar que ela transmita um vírus de e-mail.
Existem várias vantagens de usar um firewall de filtragem de pacotes:

- Os filtros de pacote implementam conjuntos de regras de permissão simples ou negam.
- Os filtros de pacotes têm um baixo impacto no desempenho da rede.
- Os filtros de pacotes são fáceis de implementar e são suportados pela maioria dos roteadores.
- Os filtros de pacote fornecem um grau inicial de segurança na camada de rede.
- Os filtros de pacotes executam quase todas as tarefas de um firewall high-end a um custo muito menor.

Os filtros de pacotes não representam uma solução de firewall completa, mas são um elemento importante de uma política de segurança de firewall. Existem várias desvantagens de usar um firewall de filtragem de pacotes:

- Os filtros de pacote de informação são suscetíveis à falsificação de IP. Os atores de ameaça podem enviar pacotes arbitrários que atendem aos critérios ACL e passam pelo filtro.
- Os filtros de pacotes não filtram de forma confiável pacotes fragmentados. Como os pacotes IP fragmentados carregam o cabeçalho TCP no primeiro fragmento e filtro de filtros de pacote na informação de cabeçalho TCP, todos os fragmentos após o primeiro fragmento são passados incondicionalmente. As decisões de usar filtros de pacote supõem que o filtro do primeiro fragmento impõe com precisão a política.
- Os filtros de pacotes usam ACLs complexas, que podem ser difíceis de implementar e manter.
- Os filtros de pacotes não podem filtrar dinamicamente determinados serviços. Por exemplo, as sessões que usam negociações de porta dinâmica são difíceis de filtrar sem abrir o acesso a toda uma variedade de portas.

Os filtros de pacotes são sem estado. Eles examinam cada pacote individualmente em vez de no contexto do estado de uma conexão.

## Vantagens e limitações do Firewall de estado

Existem vários benefícios em usar um firewall com estado em uma rede:
- Firewalls com estado são frequentemente usados como um meio primário de defesa, flitrando tráfego indesejado ou desnecessário.
- Firewalls com estado fortalecem a filtragem de pacotes fornecendo um controle mais rigoroso sobre a segurança.
- Firewalls com estado melhoram o desempenho em relação aos filtros de pacotes ou servidores proxy.
- Firewalls com estado se defendem contra ataques de falsificação e DoS, determinando se os pacotes pertencem a uma conexão existente ou são de uma origem não autorizada.
- Firewalls com estado fornecem mais informações de log do que um firewall de filtragem de pacotes.

Os firewalls com estado também apresentam algumas limitações:
- Firewalls com estado não podem evitar ataques à camada de aplicativo porque não examinam o conteúdo real da conexão HTTP.
- Nem todos os protocolos são stateful. Por exemplo, o UDP e o ICMP não geram informações de conexão para uma tabela de estado e, portanto, não conseguem tanto suporte para filtragem.
- É difícil rastrear conexões que usam negociação de porta dinâmica. Algumas aplicações abrem várias conexões. Isso requer uma nova gama de portas que devem ser abertas para permitir esta segunda conexão.
- Firewalls com estado não suportam autenticação de usuário.

# Arquiteturas comuns de segurança
O design do firewall é principalmente sobre interfaces de dispositivo que permitem ou negam tráfego com base na origem, no destino e no tipo de tráfego. Alguns designs são tão simples quanto designar uma rede externa e uma rede interna, que são determinados por duas interfaces em um firewall.

## Privado e público
A rede pública (ou rede externa) não é confiável e a rede privada (ou rede interna) é confiável.
Normalmente, um firewall com duas interfaces é configurado da seguinte forma:
- O tráfego proveniente da rede privada é permitido e inspecionado à medida que viaja em direção à rede pública. É permitido o tráfego inspecionado que retorna da rede pública e associado ao tráfego originado da rede privada.
- O tráfego originado da rede pública e que viaja para a rede privada geralmente é bloqueado.

## Zona Desmilitarizada
Uma zona desmilitarizada (DMZ) é um projeto de firewall onde normalmente há uma interface interna conectada à rede privada, uma interface externa conectada à rede pública e uma interface DMZ, conforme mostrado na figura.
- O tráfego proveniente da rede privada é inspecionado à medida que ele viaja para a rede pública ou DMZ. Este tráfego é permitido com pouca ou nenhuma restrição. Tráfego inspecionado que retorna da DMZ ou da rede pública para a rede privada é permitido.
- O tráfego originado da rede DMZ e que viaja para a rede privada geralmente é bloqueado.
- O tráfego originado da rede DMZ e viajando para a rede pública é permitido seletivamente com base nos requisitos de serviço.
- O tráfego proveniente da rede pública e que viaja em direção à DMZ é seletivamente permitido e inspecionado. Esse tipo de tráfego normalmente é tráfego de email, DNS, HTTP ou HTTPS. O tráfego de retorno da DMZ para a rede pública é permitido dinamicamente.
- O tráfego originado da rede pública e que viaja para a rede privada está bloqueado.

## Firewalls de política baseados em zona
Os firewalls de política baseados em zona (ZPFs) usam o conceito de zonas para fornecer flexibilidade adicional. Uma zona é um grupo de uma ou mais interfaces que têm funções ou recursos semelhantes. As zonas ajudam a especificar onde uma regra ou política de firewall do Cisco IOS deve ser aplicada. Na figura, as políticas de segurança para LAN 1 e LAN 2 são semelhantes e podem ser agrupadas em uma zona para configurações de firewall. Por padrão, o tráfego entre interfaces na mesma zona não está sujeito a nenhuma política e passa livremente. No entanto, todo o tráfego de zona para zona está bloqueado. Para permitir o tráfego entre as zonas, uma política que permite ou inspeciona o tráfego deve ser configurada.

A única exceção a esta política padrão **deny any** é a zona própria do roteador. A zona auto é o próprio roteador e inclui todos os endereços IP da interface do roteador. As configurações de política que incluem a zona automática aplicar-se-iam ao tráfego destinado e proveniente do roteador. Por padrão, não há nenhuma política para esse tipo de tráfego. O tráfego que deve ser considerado ao projetar uma política para a auto zona inclui o tráfego de plano de gerenciamento e plano de controle, como SSH, SNMP e protocolos de roteamento.


# Defesa em camadas
1. **Segurança do núcleo da rede -** Protege contra software malicioso e anomalias de tráfego, impõe políticas de rede e garante capacidade de sobrevivência
2. **Segurança de perímetro -** Protege limites entre zonas
3. **Segurança das comunicações -** Fornece garantia de informação
4. **Segurança do endpoint -** Fornece identidade e conformidade com a política de segurança do dispositivo
Uma defesa em camadas usa diferentes tipos de firewalls que são combinados em camadas para adicionar profundidade à segurança de uma organização. As políticas podem ser aplicadas entre as camadas e dentro das camadas. Estes pontos de aplicação da política determinam se o tráfego é encaminhado ou descartado. Por exemplo, o tráfego que vem dentro da rede não confiável encontra primeiramente um filtro de pacote no roteador de borda. Se permitido pela política, o tráfego vai ao Firewall selecionado ou ao sistema host bastion que aplica mais regras ao tráfego e descarta pacotes suspeitos. Um host bastion é um computador endurecido que normalmente está localizado na DMZ. Então o tráfego vai para um roteador de triagem interior. O tráfego move-se para o host de destino interno somente após passar com sucesso todos os pontos de imposição da política entre o roteador externo e a rede interna. Esse tipo de configuração DMZ é chamado de configuração de sub-rede rastreada.

Uma abordagem de defesa em camadas não é tudo o que é necessário para garantir uma rede interna segura. Um administrador de rede deve considerar muitos fatores ao construir uma defesa completa em profundidade:

- Os firewalls normalmente não interrompem as intrusões provenientes de hosts dentro de uma rede ou zona.
- Firewalls não protegem contra instalações de ponto de acesso desonestos.
- Os firewalls não substituem os mecanismos de backup e recuperação de desastres resultantes de ataques ou falhas de hardware.
- Os firewalls não substituem administradores e usuários informados.

Essa lista parcial de práticas recomendadas pode servir como ponto de partida para uma política de segurança de firewall.

- Posicione firewalls nos limites de segurança. Os firewalls são uma parte crítica da segurança de rede, mas não é sensato confiar exclusivamente em um firewall para segurança.
- Negue todo o tráfego por padrão.
- Permitir apenas serviços que são necessários.
- Assegure-se de que o acesso físico ao firewall esteja controlado.
- Monitore regularmente logs de firewall.
- Pratique o gerenciamento de alterações para alterações de configuração de firewall.
- Lembre-se de que os firewalls protegem principalmente contra ataques técnicos originários do exterior.