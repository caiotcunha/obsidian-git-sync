
**Conceito**: Computação em nuvem é o fornecimento de serviços de computação, incluindo servidores, armazenamento, banco de dados, rede, software, etc pela internet para oferecer inovações mais rápidas, recursos flexíveis e economias de escala.

Tipos de nuvem:
- **Nuvem Pública**: Pertencem a provedores de serviços de nuvem terceirizados e são administradas por eles. Eles também fornecem recursos de computação. Ex: microsoft azure
- **Nuvem Privada**: Se refere aos recursos de computação em nuvem usados exclusivamente por uma única empresa ou organização.
- **Nuvem Híbrida**: combinam nuvens públicas e privadas ligadas por uma tecnologia que permite que dados e aplicativos sejam compartilhados entre elas. 


Tipos de serviço de nuvem:
- **IaaS (infraestrutura como serviço):** A categoria mais básica de serviços de computação em nuvem. Esse tipo de serviço permite o aluguel de infraestruturas de TI, incluindo servidores, máquinas virtuais, armazenamento, redes e sistemas operacionais, de um provedor de nuvem. No caso das IaaS, a empresa é responsável por proteger o hardware e outros recursos de computação armazenamento e rede física, enquanto o cliente é responsável pela proteção dos dados e aplicativos, e as redes virtuais.
- **PaaS (Plataforma como serviço):** se refere aos serviços de computação em nuvem que fornecem um ambiente sob demanda para desenvolvimento, teste, fornecimento e gerenciamento de aplicativos de software. A PaaS foi criada para facilitar aos desenvolvedores criarem aplicativos móveis ou Web rapidamente, sem se preocupar com a configuração ou gerenciamento de infraestrutura subjacente de servidores, armazenamento, rede e banco de dados. Nesse caso, o provedor tem responsabilidade pela segurança quase integral.
- **SaaS (software como serviço):** é um método para fornecer aplicativos pela internet sob demanda. Nesse caso O fornecedor é o maior responsável pela segurança, sendo o cliente muito pouco participativo.
- **IaC (Infraestrutura como Código):** é uma prática da engenharia de software que promove a gestão e provisionamento de infraestrutura de TI através de scripts de código. Esta prática está altamente alinhada com os princípios da automação e os processos de DevOps, que buscam aumentar a eficiência e reduzir a possibilidade de erro humano na configuração e no gerenciamento de servidores e sistemas operacionais. Na prática de IaC, busca-se predominantemente uma **infraestrutura imutável**. Isso significa que, para realizar atualizações ou mudanças, cria-se uma nova instância da infraestrutura com as alterações necessárias, em vez de modificar a infraestrutura existente. Este modelo traz mais previsibilidade, estabilidade e facilidade no gerenciamento de configurações e rollback, caso necessário.


Benefícios:
- **Elasticidade**: habilidade de alocar ou desalocar recursos de forma dinâmica e automática para atender à demanda variável, mantendo o desempenho e a eficiência. Isso é importante para lidar com flutuações no uso sem a necessidade de uma intervenção manual extensa.

**Regiões** são locais geográficos distintos que contêm várias zonas de disponibilidade. Cada região é independente das outras, garantindo a separação física de dados.

**Zonas de disponibilidade** são locais distintos dentro de uma região que estão conectados por redes de baixa latência. Essas zonas são projetadas para serem isoladas umas das outras em termos de falhas físicas e, portanto, oferecem uma alta disponibilidade e tolerância a falhas.

**Escalabilidade horizontal (→)**: Adição de **mais máquinas/servidores**, distribuindo a carga de trabalho entre eles.

**Escalabilidade Vertical (↑)**: **Upgrade nas máquinas já existentes**, a fim de melhorar a performance, sem precisar acrescentar novos dispositivos.

## Máquinas Virtuais do Azure

O windows server é uma plataforma para compilar uma infraestrutura de aplicativos, redes e serviços Web conectados, do grupo de trabalho ao data center. Ele faz a ponte entre os ambientes locais e o Azure, adicionando mais camadas de segurança enquanto ajuda você a modernizar seus aplicativos e sua infraestrutura.

As VMs (máquinas virtuais) do Azure são um dos vários tipos de [recursos de computação sob demanda escalonáveis](https://learn.microsoft.com/pt-br/azure/architecture/guide/technology-choices/compute-decision-tree) oferecidos pelo Azure. Normalmente, você escolhe uma máquina virtual quando precisa de mais controle sobre o ambiente de computação do que as outras opções oferecem.

Máquinas virtuais do Azure podem ser usadas de várias maneiras. Alguns exemplos são:

- **Desenvolvimento e teste** – as máquinas virtuais do Azure oferecem uma maneira rápida e fácil de criar um computador com configurações específicas, necessárias para codificar e testar um aplicativo.
- **Aplicativos na nuvem** – como a demanda por seu aplicativo pode variar, pode fazer sentido, em termos econômicos, executá-lo em uma máquina virtual no Azure. Você paga por máquinas virtuais extras quando precisa delas e as desliga quando não são mais necessárias.
- **Datacenter estendido** – as máquinas virtuais em uma rede virtual do Azure podem ser facilmente conectadas à rede de sua organização.


Cloud computing allows control over resource allocation
