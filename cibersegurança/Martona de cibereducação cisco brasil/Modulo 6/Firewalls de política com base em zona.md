# Benefícios de um ZPF
Há dois modelos de configuração para o Cisco IOS Firewall:
- **Firewall clássico** - o modelo de configuração tradicional em que a política de firewall é aplicada em interfaces.
- **Firewall de política baseado em zona (ZPF)** - O modelo de configuração na qual as interfaces são atribuídas a zonas de segurança, e a política de firewall é aplicada ao tráfego em movimento entre as zonas.
Se uma interface adicional for adicionada à zona privada, os hosts conectados à nova interface na zona privada podem passar tráfego para todos os hosts na interface existente na mesma zona. Uma rede simples de três zonas é mostrada na figura.

As principais motivações para profissionais de segurança de rede migram para o modelo ZPF são estrutura e facilidade de uso. A abordagem estruturada é útil para documentação e comunicação. A facilidade de uso torna as implementações de segurança de rede mais acessíveis a uma comunidade maior de profissionais de segurança.

Existem vários benefícios de um ZPF:

- Não é dependente de ACL.
- A postura de segurança do roteador é bloquear a menos que explicitamente permitido.
- As políticas são fáceis de ler e pesquisar defeitos com o Cisco Common Classification Policy Language (C3PL). C3PL é um método estruturado para criar políticas de tráfego com base em eventos, condições e ações. Isto fornece a escalabilidade porque uma política afeta todo o tráfego dado, em vez de precisar de ACLs múltiplos e ações da inspeção para tipos diferentes de tráfego.
- Interfaces virtuais e físicas podem ser agrupadas em zonas.
- As políticas são aplicadas ao tráfego unidirecional entre zonas.

Ao decidir se deseja implementar o iOS Classic Firewall ou um ZPF, é importante observar que ambos os modelos de configuração podem ser ativados simultaneamente em um roteador. No entanto, os modelos não podem ser combinados em uma única interface. Por exemplo, uma interface não pode ser configurada simultaneamente como membro da zona de segurança e para inspeção de IP.

# Projeto ZPF
1. Determine as zonas: O administrador se concentra na separação da rede em zonas. Zonas estabelecem as fronteiras de segurança de uma rede. Uma zona define um limite onde o tráfego é submetido a restrições políticas à medida que cruza para outra região da rede. Por exemplo, a rede pública seria uma zona e a rede interna seria outra zona.
2. Estabelecer políticas entre zonas: Para cada par de zonas "fonte de destino" (por exemplo, da rede interna para a Internet externa), defina as sessões que os clientes nas zonas de origem podem solicitar os servidores nas zonas de destino. Essas sessões são mais frequentemente as sessões TCP e UDP, mas também podem ser sessões ICMP, como o ICMP ECHO. Para o tráfego que não é baseado no conceito de sessões, o administrador deve definir fluxos de tráfego unidirecionais da fonte para o destino e vice-versa. As políticas são unidirecionais e são definidas com base nas zonas de origem e destino, que são conhecidas como pares de zona.
3. Projetar infraestrutura fisica: Após as zonas terem sido identificadas e os requisitos de tráfego entre eles documentados, o administrador deve projetar a infraestrutura física. O administrador deve levar em conta os requisitos de segurança e disponibilidade ao projetar a infraestrutura física. Isso inclui ditar o número de dispositivos entre zonas mais seguras e menos seguras e determinar dispositivos redundantes.
4. Identififcar subconjuntos dentro de zonas e mesclar requisitos de tráfego: Para cada dispositivo de firewall no projeto, o administrador deve identificar subconjuntos de zonas que estão conectados às suas interfaces e mesclar os requisitos de tráfego para essas zonas. Por exemplo, várias zonas podem ser ligadas indiretamente a uma única interface de um firewall. Isso resultaria em uma política interzone específica do dispositivo. Embora uma consideração importante, os subconjuntos de zona de implementação estão além do escopo deste currículo.

# Ações ZPF
As políticas identificam ações que o ZPF executará no tráfego de rede. Três ações possíveis podem ser configuradas para processar o tráfego por protocolo, zonas de origem e destino (pares de zonas) e outros critérios.
- **Inspect** - Isso realiza inspeção de pacotes de estado de Cisco IOS.
- **Drop** - Isso é análogo a **deny** uma declaração em uma ACL. Opção **log** vai logar os pacotes rejeitados.
- **Pass** - Isso é análogo a uma declaração **permit** em uma ACL. A ação de aprovação não rastreia o estado das conexões ou das sessões no tráfego.

# Regras para tráfego de trânsito
As regras dependem se as interfaces de entrada e saída são membros da mesma zona:

- Se nenhuma das interfaces é um membro da zona, então a ação resultante é passar o tráfego.
- Se ambas as interfaces são membros da mesma zona, então a ação resultante é passar o tráfego.
- Se uma interface é um membro da zona, mas a outra não é, então a ação resultante é deixar cair o tráfego apesar de um zona-par existir.
- Se ambas as interfaces pertencem ao mesmo zona-par e uma política existe, então a ação resultante é inspecionar, permitir, ou cair conforme definido pela política.
A tabela resume essas regras.

|Interface de origem Membro da Zona?|Interface de destino Membro da Zona?|Zona-par existe?|Política existe?|Resultado|
|---|---|---|---|---|
|NÃO|NÃO|N/D|N/D|APROVADO|
|SIM|NÃO|N/D|N/D|DESCARTAR|
|NÃO|SIM|N/D|N/D|DESCARTAR|
|Sim (privado)|Sim (público)|N/D|N/D|APROVADO|
|Sim (privado)|Sim (público)|SIM|N/D|DESCARTAR|
|Sim (privado)|Sim (público)|Sim|NÃO|APROVADO|
|Sim (privado)|Sim (público)|Sim|Sim|INSPECIONAR|

# Regras para Tráfego para Zona Self
A **self zone** é o próprio roteador e inclui todos os endereços IP atribuídos às interfaces do roteador. Este é o tráfego que se origina no roteador ou é endereçado a uma interface de roteador. Especificamente, o tráfego é para o gerenciamento de dispositivos, por exemplo, SSH ou controle de encaminhamento de tráfego, como o tráfego de protocolo de roteamento. As regras para um ZPF (Zone-Based Policy Firewall) são diferentes para a **self zone**. Para o exemplo do tráfego da **self zone**, consulte a topologia mostrada na figura anterior.

As regras dependem se o roteador é a fonte ou o destino do tráfego, conforme mostrado na tabela. Se o roteador for a fonte ou o destino, todo o tráfego será permitido. A única exceção é se a origem e o destino são um par de zona com uma política específica de serviço. Nesse caso, a política é aplicada a todo o tráfego.

|Interface de origem Membro da Zona?|Interface de destino Membro da Zona?|Zona-par existe?|Política existe?|Resultado|
|---|---|---|---|---|
|SIM (**self zone**)|SIM|NÃO|N/D|APROVADO|
|SIM (**self zone**)|SIM|SIM|NÃO|APROVADO|
|SIM (**self zone**)|SIM|SIM|SIM|INSPECIONAR|
|SIM|SIM (**self zone**)|NÃO|N/D|APROVADO|
|SIM|SIM (**self zone**)|SIM|NÃO|APROVADO|
|SIM|SIM (**self zone**)|SIM|SIM|INSPECIONAR|

# Configurar um ZPF
Etapa 1: Crie as zonas.
Etapa 2: Identifique o tráfego com um mapa de classe.
Etapa 3: Defina uma ação com um mapa de política.
Etapa 4: Identifique um par de zonas e combine-o a um mapa de política.
Etapa 5: Atribua zonas às relações apropriadas.

## Crie zonas
O primeiro passo, é criar as zonas. No entanto, antes de criar as zonas, responda a algumas perguntas:

- Quais interfaces devem ser incluídas nas zonas?
- Qual será o nome para cada zona?
- Que tráfego é necessário entre as zonas e em que direção?

``Router(config)# zone security zone-name``

```
R1(config)# zone security PRIVATE

R1(config-sec-zone)# exit

R1(config)# zone security PUBLIC

R1(config-sec-zone)# exit

R1(config)#
```

## Identifique o tráfego
A segunda etapa é usar um mapa de classe para identificar o tráfego a que uma política será aplicada. Uma classe é uma maneira de identificar um conjunto de pacotes com base em seus conteúdos usando condições de "correspondência". Normalmente, você define uma classe para que você possa aplicar uma ação ao tráfego identificado que reflita uma política. Uma classe é definida com mapas de classe.

A figura mostra a sintaxe do comando **class-map** . Existem vários tipos de mapas de classe. Para uma configuração ZPF, use a palavra -chave **inspect** para definir um mapa de classe. Determine como os pacotes são avaliados quando existem vários critérios de correspondência. Os pacotes devem atender a um dos critérios de correspondência **(match-any)** ou todos os critérios de correspondência **(match-all)** para serem considerados um membro da classe.

# Definir uma ação

A terceira etapa é usar um mapa de política para definir que ação deve ser tomada para o tráfego que é um membro de uma classe. O exemplo abaixo mostra a sintaxe de comando para configurar um mapa de políticas. Uma ação é uma funcionalidade específica. É associado tipicamente a uma classe de tráfego. Por exemplo, **inspect**, **drop**, e **pass** são ações.

# Identificar um Zona-Par e combinar a uma política

A quarta etapa é identificar um par de zonas e associar esse par de zonas a um mapa de política. O exemplo abaixo mostra a sintaxe do comando. Crie uma zona-par com o comando **zone-pair security**. Use então o comando **service-policy type inspect** anexar um mapa de política e sua ação associada ao zona-par.

# Atribuir zonas a interfaces
A quinta etapa é atribuir zonas às interfaces apropriadas. Associar uma zona a uma interface aplicará imediatamente a política de serviço que foi associada à zona. Se nenhuma serviço-política é configurada ainda para a zona, todo o tráfego de trânsito será deixado cair. Use o comando **zone-member security** atribuir uma zona a uma interface.

# Verifique uma configuração do ZPF
Verifique uma configuração ZPF visualizando a configuração em execução. Observe que o mapa de classe está listado primeiro. Então o mapa de política faz uso do mapa de classe. Além disso, observe os **class class-default** destacados que vão descartar todo o outro tráfego que não é membro da classe HTTP-Traffic.

As configurações de zona seguem as configurações do mapa de política com nomeação de zona, emparelhamento de zonas e associando uma política de serviço ao par de zonas. Finalmente, as interfaces são zonas atribuídas.

# Considerações de configuração do ZPF
Ao configurar um ZPF com o CLI, há vários fatores a considerar:

- O roteador nunca filtra o tráfego entre interfaces na mesma zona.
- Uma interface não pode pertencer a várias zonas. Para criar uma união de zonas de segurança, especifique uma nova zona e um mapa de política apropriado e pares de zonas.
- O ZPF pode coexistir com o Firewall clássico embora não possa ser usado na mesma interface. Remova o comando **ip inspect** interface configuration antes de aplicar o comando **zone-member security** .
- O tráfego nunca pode fluir entre uma interface atribuída a uma zona e uma interface sem uma atribuição de zona. O comando **zone-member** sempre resulta em uma interrupção temporária de serviço até que o outro membro da zona esteja configurado.
- A política entre zonas padrão é deixar cair todo o tráfego a menos que especificamente permitido de outra forma pela serviço-política configurada para o zona-par.
- O comando **zone-member** não protege o próprio roteador (tráfego de e do roteador não é afetado), a menos que os pares de zona sejam configurados usando a zona auto predefinida.