**Virtualização**: Técnica que permite criar múltiplos ambientes isolados (máquinas virtuais, ou VMs) em um único hardware físico, usando um _hypervisor_ para gerenciar recursos.

**Containers**: são máquinas virtuais altamente padronizadas, que podem ser facilmente criadas, gerenciadas, movidas e copiadas. Ambientes leves e isolados que compartilham o kernel do sistema operacional host, empacotando aplicações e suas dependências para execução consistente em qualquer ambiente.

**Docker**: Plataforma líder para criação e gerenciamento de containers.

**Kubernetes**: Sistema de orquestração para gerenciar clusters de containers em escala.


Benefícios:
- Redução de custos
- Facilidade de desenvolvimento
- Facilidade de implementação

Existem várias abordagens de virtualização, como:
- **Virtualização de Servidor:** Onde um servidor físico é dividido em várias máquinas virtuais, cada uma com seu próprio sistema operacional.
- **Virtualização de Armazenamento:** Onde recursos de armazenamento são abstraídos e geridos como um todo unificado.
- **Virtualização de Rede:** Que cria redes virtuais separadas da infraestrutura de hardware física.


## Kubernets
Relacionado ao gerenciamento de cargas, orquestração, escalabilidade de containers e gerenciamento de atualização. Um pod é um grupo de containers que compartilham um espaço de rede local. O pod é a unidade de trabalho básica no Kubernetes. Services é o ponto de acesso para os pods.
**Kubernetes** é uma plataforma de orquestração de contêineres que facilita a implantação, o dimensionamento e a gestão de aplicações conteinerizadas. Um dos principais objetivos do Kubernetes é **abstrair a infraestrutura subjacente**, permitindo que os desenvolvedores foquem em configurar suas aplicações, enquanto o Kubernetes gerencia automaticamente o ambiente subjacente.

### Plano de controle

Os principais componentes do plano de controle são o etcd, um banco de dados distribuído que armazena as configurações globais do cluster, o API server, um serviço de borda para interação com os demais componentes, além do controller manager e do scheduler, que realizam tarefas administrativas relacionadas à orquestração do cluster.

### Plano de dados

O plano de dados pode ser compreendido como um conjunto dos objetos que o constituem, listados abaixo.

#### Labels e Selectors

Labels (rótulos) são nomes associados a um recurso, como o nome de um pod. Selectors (seletores) são expressões que selecionam recursos baseado em alguma regra, como todos recursos com label igual a determinado valor.
#### Pods

Um pod é um grupo de containers que compartilham um espaço de rede local. O pod é a unidade de trabalho básica no Kubernetes.

#### Nodes

Os Nodes (nodos) são os servidores físicos ou virtuais onde os pods e seus containers rodam

- **Kubelet** é responsável pelo estado de funcionamento de cada nó, garantindo que todos os recipientes no nó sejam saudáveis. Kubelet monitora o estado de uma cápsula e, se não estiver no estado desejado, a cápsula é redirecionada para o mesmo nó. O estado do nó é retransmitido a cada poucos segundos através de mensagens de batimento cardíaco para o primário. Quando o primário detecta uma falha no nó, o Controlador de Replicação observa esta mudança de estado e lança os pods em outros nós saudáveis.
- O **Kube-proxy** é uma implementação de um proxyde rede e um equilibrador de carga, e suporta a abstração do serviço junto com outras operações de rede. É responsável por rotear o tráfego para o contêiner apropriado com base no IP e número da porta do pedido recebido.
- Um **contêiner** reside dentro de uma cápsula. O contêiner é o nível mais baixo de um micro-serviço, que abriga a aplicação em funcionamento, bibliotecas e suas dependências. Os contêineres podem ser expostos ao mundo através de um endereço IP externo. A Kubernetes tem apoiado os contêineres Docker desde sua primeira versão. Em julho de 2016, o motor de contêineres rkt foi adicionado

#### Namespaces

Os namespaces são divisões lógicas dos demais recursos do plano de dados, podendo ser usados para separar, por exemplo, ambiente de testes do de produção

#### ReplicaSets

Os ReplicaSets são um recurso utilizado para definir o número de replicas de um ou mais pods, identificados através de um seletor associado ao ReplicaSet

#### Deployments

Um Deployment define o estado desejado de Pods e ReplicaSets.

#### DaemonSets

Os DaemonSets definem um ou mais pods que devem rodar em todos os nodos, sempre.

#### Services

Um Service (serviço) no Kubernetes é uma entidade lógica constituida de um ou mais pods, selecionados através de um seletor. O serviço possui um endereço de IP associado a si, publicado através do serviço de DNS do Kubernetes, permitindo assim a sua descoberta por demais serviços do cluster ou externos a ele. Além disso, o Kubernetes realiza o balanceamento das conexões recebidas entre os pods que constituem esse serviço. No exemplo abaixo um serviço é definido, expondo uma porta para os pods selecionados através do seletor.

#### Volumes

O armazenamento dos containers é efêmero, isto é, ele deixa de existir quando os containers param de rodar. Os Volumes no Kubernetes são unidades lógicas de armazenamento que podem ser efêmeras ou persistentes, e que são acessíveis por todos containers de um pod.

#### ConfigMaps

ConfigMaps são objetos lógicos que armazenam informação no formato chave-valor, informações essas que podem ser acessadas através de variáveis de ambientes, arquivos em um volume, ou através de uma API.

#### Secrets

Secrets são como ConfigMaps, mas são feitos para armazenar dados sensíveis como senhas.
#### Helm charts

Helm charts são pacotes para o Kubernetes, e Helm é o software que os gerencia. Os pacotes (charts) são nada mais nada menos que arquivos no formato YML dispostos em uma certa estrutura de diretórios, e que descrevem objetos com os descritos nas seções acima, além de um arquivo Chart.yml que descreve o pacote em si. O Helm por sua vez faz a gerência destes pacotes, como controle de versão e empacotamento, interação com o Kubernetes para aplicar os recursos descritos no pacote, entre outros.

**Nó master** é o componente central do Kubernetes responsável por gerenciar o estado desejado dos contêineres e pods no cluster. Ele inclui vários componentes principais, como:
- **API Server:** Interface de comunicação com o cluster.
- **Scheduler:** Responsável por alocar pods nos nós worker.
- **Controller Manager:** Gerencia os controladores que regulam o estado do cluster.
- **etcd:** Banco de dados chave-valor que armazena todos os dados de configuração persistente do cluster.
  
Os **nós worker** são as máquinas onde os contêineres são realmente executados. Esses nós contêm os seguintes componentes:
- **Kubelet:** Agente que garante que os contêineres estão rodando conforme especificado.
- **Container Runtime:** Software que executa os contêineres, como Docker.
- **Kube-proxy:** Gerencia a rede no nó worker.
## Docker
Mais relacionado à execução de containers de forma independente. O termo _build_ no contexto do Docker refere-se ao processo de criação de uma imagem Docker a partir de um `Dockerfile`. Portanto, _build_ não é um sistema de arquivos, mas sim uma ação ou um processo.

Para **otimizar o tamanho das imagens**, a prática recomendada é ordenar as instruções no Dockerfile de modo que as camadas menos prováveis de serem alteradas venham antes das mais prováveis. Isso maximiza a reutilização do cache, minimizando o tempo de construção da imagem. Portanto, a afirmação da questão inverte a lógica correta.

## Contêiners

**Contêineres** são uma tecnologia de virtualização que permite executar aplicativos de forma isolada do sistema operacional subjacente. Eles são amplamente utilizados para promover a portabilidade, eficiência e escalabilidade das aplicações.

O uso de contêineres torna as aplicações portáteis de modo que o mesmo código possa ser executado em qualquer dispositivo; a máquina virtual, por sua vez, é uma cópia digital de uma máquina física.

**Clusters** de alta disponibilidade são sistemas projetados para prover um alto nível de continuidade operacional. Eles fazem isso através do agrupamento (_clustering_) de dois ou mais computadores que trabalham juntos, de modo que, se um falhar, outro possa assumir suas funções, minimizando a interrupção dos serviços. Isso é essencial em ambientes onde a continuidade dos serviços é crítica.


### **Comparação: Virtualização vs. Containers**

|**Característica**|**Virtualização**|**Containers**|
|---|---|---|
|**Isolamento**|Nível de hardware (SO completo)|Nível de processo (kernel compartilhado)|
|**Overhead**|Alto (cada VM tem SO próprio)|Baixo (só o necessário para a app)|
|**Boot Time**|Minutos|Segundos|
|**Uso típico**|Servidores dedicados, legacy apps|Microserviços, CI/CD, cloud-native|