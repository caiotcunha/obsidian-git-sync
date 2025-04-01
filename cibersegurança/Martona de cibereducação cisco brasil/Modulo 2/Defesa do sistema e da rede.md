# Segurança física
## Cercas e barreiras físicas
Barreiras físicas são a primeira coisa que vem à mente quando se pensa em segurança física. Em muitas situações, elas são a camada mais externa da defesa e as mais visíveis. Todas as barreiras devem atender a requisitos específicos do projeto e a especificações da fábrica.

## Biometria

Biometria são as características fisiológicas ou comportamentais de um indivíduo, e há práticas de segurança baseadas na identificação e concessão de acesso usando a biometria. Sistemas de autenticação de biometria incluem medições da face, impressão digital, geometria da mão, íris, retina, assinatura e voz.
Ao selecionar sistemas biométricos, há vários fatores importantes a serem considerados, incluindo:
- Precisão
- taxa de transferência
- Aceitação para usuários
- Exclusividade do órgão biométrico e ação
- Resistência à falsificação
- Confiabilidade
- Requisitos de armazenamento de dados
- Tempo de inscrição
- Intrusão na verificação
O mais importante desses fatores é a precisão, que é expressa em tipos de erro e taxas.

## Logs de acesso e crachás

## Vigilância
Todos os controles de acesso físicos, incluindo sistemas de impedimento e de detecção dependem, em última análise, de pessoal para intervir e parar o ataque ou a invasão real.

# Segurança de aplicações

## Desenvolvimento de Aplicativos
Para manter a segurança em todas as etapas de desenvolvimento de aplicativos, um processo robusto precisa ser seguido.
1. Desenvolvimento e teste
2. Preparo e produção
3. Provisionamento e desprovisionamento

## Técnicas de codificação de segurança
1. Normalização: A normalização é usada para organizar dados em um banco de dados e ajudar a manter a integridade dos dados. A normalização converte uma sequência de entrada em sua forma mais simples conhecida para garantir que todas as sequências tenham representações binárias exclusivas e que qualquer entrada mal-intencionada seja identificada.
2. Procedimento armazenado: Um procedimento armazenado é um grupo de instruções SQL pré-compiladas armazenadas em um banco de dados que executa uma tarefa. Se você usar um procedimento armazenado para aceitar parâmetros de entrada de clientes que usam dados de entrada diferentes, reduzirá o tráfego de rede e obterá resultados mais rápidos.
3. Ofuscação e camuflagem: Um desenvolvedor pode usar a ofuscação e a camuflagem para impedir que o software seja reprojetado. A ofuscação oculta dados originais com caracteres ou dados aleatórios. A camuflagem substitui os dados confidenciais por dados fictícios realistas.
4. Reutilização de código: A reutilização de código significa usar o software atual para criar um novo software, economizando tempo e custos de desenvolvimento. É preciso ter cuidado, no entanto, para evitar a introdução de vulnerabilidades.
5. SDKs: Kits de desenvolvimento de software e bibliotecas de terceiros (SDKs) fornecem um repositório de códigos úteis para tornar o desenvolvimento de aplicativos mais rápido e mais barato. A desvantagem é que qualquer vulnerabilidade em SDKs ou bibliotecas de terceiros pode afetar muitos aplicativos.

## Validação de entrada
Controlar o processo de entrada de dados é fundamental para manter a integridade do banco de dados. Muitos ataques são executados em um banco de dados e inserem dados malformados. O ataque pode confundir, falhar ou fazer com que o aplicativo divulgue informações demais para o invasor.

## Regras de Validação
Uma regra de validação verifica se os dados estão nos parâmetros definidos pelo projetista de banco de dados. Uma regra de validação ajuda a garantir a integridade, a precisão e a consistência dos dados. Os critérios usados na regra de validação incluem o seguinte:
- Tamanho – verifica o número de caracteres em um item de dados
- Formato – verifica se os dados estão de acordo com um formato especificado
- Consistência – verifica a consistência dos códigos nos itens de dados relacionados
- Intervalo – verifica se os dados estão dentro de valores mínimo e máximo
- Dígito de verificação – efetua um cálculo extra para gerar um dígito de verificação para detecção de erros

## Verificação de integridade
Dados comprometidos podem ameaçar a segurança de seus dispositivos e sistemas. Uma **verificação de integridade** pode medir a consistência dos dados em um arquivo, imagem ou registro para garantir que eles não tenham sido corrompidos. A verificação de integridade executa uma **função hash** para obter um instantâneo de dados e, em seguida, usa esse instantâneo para garantir que os dados permaneçam inalterados. Um **checksum** é um exemplo de uma função hash.
- Checksum: Uma checksum verifica a integridade de arquivos, ou de strings de caracteres, antes e depois de serem transferidos de um dispositivo para outro por uma rede local ou pela Internet. As checksum simplesmente convertem cada conjunto de informações para um valor e soma o total. Para testar a integridade de dados, um sistema de recebimento apenas repete o processo. Se as duas somas forem iguais, os dados são válidos. Caso contrário, uma alteração ocorreu em algum lugar ao longo do caminho.
- Controle de versão: As empresas usam controle de versão para evitar alterações acidentais por usuários autorizados. O controle de versão significa que dois usuários não podem atualizar o mesmo objeto, como um arquivo, registro de banco de dados ou transação, ao mesmo tempo.
- Backups: Backups precisos ajudam a manter a integridade de dados, se os dados forem corrompidos. Uma empresa precisa verificar o seu processo para garantir a integridade do backup, antes que ocorra perda de dados.
- Autorização: A autorização determina quem tem acesso aos recursos da empresa, de acordo com a necessidade de cada um. Por exemplo, controles de acesso de usuário e permissões de arquivo garantem que apenas determinados usuários possam modificar os dados. Um administrador pode definir as permissões de um arquivo como somente leitura. Como resultado, um usuário que acessa esse arquivo não pode fazer nenhuma alteração.

## Outras práticas de segurança de aplicativos
- Assinatura de código: ajuda a provar que um código baixado é autêntico
- Cookies seguros: O uso de cookies seguros protege as informações armazenadas em cookies contra hackers

## Controle de ameaças a aplicativos
- Acesso não autorizado a data centers, salas de computador e armário de cabos: Implementar políticas, padrões e procedimentos para os funcionários e para os visitantes, para garantir que as instalações sejam seguras.
- Período de inatividade do sistema: Desenvolver um plano de continuidade de negócios para aplicativos essenciais para manter a disponibilidade das operações. Desenvolver um plano de recuperação de desastres para aplicativos e dados essenciais.
- Vulnerabilidade de software do sistema operacional de rede: 
	- Desenvolver uma política para lidar com atualizações de software de aplicativo e do sistema operacional.
	- Instale correções e atualizações regularmente.
- Acesso não autorizado a sistemas:
	- Use autenticação multifatorial
	- Monitorar arquivos de log
- Perda de dados:
	- Implementar padrões de classificação de dados.
	- Implementar procedimentos de backup.
- Vulnerabilidade de desenvolvimento de software: 
	- Realizar testes antes do lançamento do software


# Fortalecimento da rede

## Serviços de rede e de roteamento
Os criminosos usam serviços de rede vulneráveis para atacar um dispositivo ou usá-lo como parte do ataque. Para verificar os serviços de rede não protegidos, verifique se um dispositivo tem portas abertas usando um scanner de porta. Um scanner de porta envia uma mensagem para cada porta e espera por uma resposta, indicando como a porta é usada e se está aberta.
- Protocolo de Configuração Dinâmica de Host (DHCP): O DHCP usa um servidor para atribuir um endereço IP e outras informações de configuração automaticamente aos dispositivos de rede. Na realidade, o dispositivo está obtendo uma permissão do servidor DHCP para usar a rede. Os invasores podem direcionar servidores DHCP para negar o acesso a dispositivos na rede, mas medidas de segurança como rastreamento de DHCP impedem que servidores DHCP invasores forneçam endereços IP para clientes ao validar mensagens de fontes que não são confiáveis.
	- Proteja fisicamente o servidor DHCP.
	- Aplique as correções de software.
	- Localize o servidor DHCP atrás de um firewall.
	- Monitore a atividade do DHCP analisando os registros do DHCP.
	- Mantenha uma solução antivírus forte.
	- Desinstale qualquer serviço e aplicação não utilizado.
	- Feche as portas não utilizadas.
- Domain Name System (DNS): O DNS converte um URL ou endereço de site, como www.cisco.com, em um endereço IP numérico. Quando os usuários digitam um endereço da Web na barra de endereços, o servidor DNS reconhece o endereço IP. Os invasores podem direcionar os servidores DNS para negar o acesso aos recursos da rede ou redirecionar o tráfego para sites falsos. Use serviço e autenticação seguros entre servidores DNS para protegê-los contra esses ataques. As DNS Security Extensions (DNSSEC) usam assinaturas digitais para fortalecer a autenticação e proteger contra ameaças ao DNS. Uma checklist de segurança para DNS:
	- Manter softwares DNS atualizados.
	- Impeça que a string de versão revele informações.
	- Separe os servidores DNS internos e externos.
	- Restrinja as transações permitidas pelo endereço IP do cliente.
	- Use assinaturas de transação para autenticar transações.
	- Desative ou restrinja as transferências de zona e as atualizações dinâmicas o máximo possível.
	- Habilitar o log e analisar logs.
	- Use Domain Name System Security Extensions (DNSSEC).
	- Assine zonas.
- Protocolo de mensagens de controle da internet (ICMP): Dispositivos de rede usam ICMP para enviar mensagens de erro como quando um serviço solicitado não está disponível ou se o host não pode acessar o roteador. O comando ping é um utilitário de rede que usa o ICMP para testar a acessibilidade de um host em uma rede. O ping envia mensagens ICMP para o host e aguarda uma resposta. Os criminosos digitais podem alterar o uso do ICMP para executar ataques de canal secreto e reconhecimento, negação de serviço (DoS). Muitas redes filtram solicitações de ICMP para evitar esses ataques.
- Routing Information Protocol (RIP): O RIP limita o número de saltos permitidos em um caminho em uma rede do dispositivo de origem para o destino. O número máximo de saltos permitidos para o RIP é 15. O RIP é um protocolo de roteamento usado para trocar informações de roteamento sobre quais redes cada roteador pode acessar e a que distância estão essas redes. O RIP calcula a melhor rota com base na contagem de saltos, mas os criminosos digitais também podem direcionar roteadores e o protocolo RIP. Esses ataques a serviços de roteamento podem afetar o desempenho e a disponibilidade; alguns ataques podem até resultar em redirecionamento de tráfego. Use os serviços seguros com autenticação e implemente patches e atualizações de sistema para proteger serviços de roteamento como o RIP.
- Network Time Protocol (NTP): Ter o tempo correto nas redes é importante. Carimbos de data e hora corretos são necessários para rastrear com precisão os eventos da rede, como as violações de segurança. Além disso, a sincronização do relógio é fundamental para a interpretação correta dos eventos nos arquivos de dados syslog, bem como para os certificados digitais. O NTP (Network Time Protocol, Protocolo de tempo de rede) é um protocolo que sincroniza os relógios de sistemas de computadores em redes de dados. O NTP permite que os dispositivos de rede sincronizem as configurações de hora com um servidor NTP. Os criminosos virtuais atacam servidores de tempo para interromper a comunicação segura que depende de certificados digitais e esconder informações do ataque, como carimbos de data e hora. Use a autenticação NTP para verificar se o servidor é confiável.

## Telnet, SSH e SCP
**O Secure Shell (SSH)** é um protocolo que fornece uma conexão com um dispositivo remoto de natureza segura (criptografada) e baseada em uma linha de comando. **O Telnet** é um protocolo mais antigo que usa transmissão de texto não criptografado, não protegido, tanto para autenticação de logon (nome de usuário e senha) quanto para dados transmitidos entre os dispositivos de comunicação. O SSH deve ser usado em vez do Telnet para gerenciar conexões, pois ele oferece criptografia forte. O SSH usa a porta TCP 22. Já o Telnet usa a porta 23.
**A SCP (Secure Copy, cópia segura)** , transfere, com segurança, arquivos de computador entre dois sistemas remotos. O SCP usa o SSH para a transferência de dados (incluindo o elemento de autenticação), para que o SCP garanta a autenticidade e a confidencialidade dos dados em trânsito.

## Protocolos seguros
Os invasores podem penetrar na infraestrutura de uma rede por meio de serviços, protocolos e portas abertas. Protocolos mais antigos deixam uma rede em uma posição vulnerável, então os profissionais de segurança digital precisam garantir que os protocolos atuais estejam sendo usados.
- Protocolo de Gerenciamento Simples de Rede (SNMP): O SNMP coleta estatísticas de dispositivos TCP / IP para monitorar a rede e equipamentos de computador. O SNMPv3 é o padrão atual - ele usa criptografia para evitar a espionagem e garantir que os dados não tenham sido violados durante o trânsito.
- Hypertext Transfer Protocol (HTTP): fornece conectividade básica da Web e usa a porta 80. O HTTP contém segurança interna limitada e é aberto ao monitoramento de tráfego durante a transmissão de conteúdo, deixando o computador do usuário aberto para ataques. Vamos ver como outros protocolos fornecem uma conexão mais segura:
	- A Secure Sockets Layer (SSL) gerencia a criptografia usando um handshake de SSL no início de uma sessão para fornecer confidencialidade e evitar a interceptação e a violação.
	- O Transport Layer Security (TLS) é um substituto atualizado e mais seguro para SSL.
	- O SSL / TLS criptografa a comunicação entre o cliente e o servidor. Onde for usado, o usuário verá HTTPS no campo de URL de um navegador em vez de HTTP.
- FTP: O File Transfer Protocol (FTP) oferece a capacidade de transferir arquivos entre um cliente e um servidor. No FTP, o cliente usa um nome de usuário e uma senha de texto sem formatação para se conectar. O File Transfer Protocol Secure (FTPS) é mais seguro - ele adiciona suporte a TLS e SSL para evitar a interceptação, a violação e a falsificação de mensagens trocadas.
- POP,IMAP e MIME: O e-mail usa Post Office Protocol (POP), IMAP (Internet Message Access Protocol) e MIME (Multipurpose Internet Mail Extensions) para anexar dados sem texto, como imagens ou vídeos, a uma mensagem de e-mail. Para proteger o POP (porta 110) ou IMAP (porta 143), use SSL / TLS para criptografar e-mails durante a transmissão. O protocolo Secure / Multipurpose Internet Mail Extensions (S / MIME) oferece um método seguro de transmissão. Ele envia mensagens digitalmente assinadas e criptografadas que fornecem autenticação, integridade de mensagem e não-repudiação.

# Blindagem da rede

## Redes da área local virtuais (VLANs)
As VLANs fornecem uma forma de agrupar dispositivos em uma LAN e em switches individuais. VLANs não são iguais a LANs: LANs virtuais são baseadas em conexões lógicas, enquanto LANs são baseadas em conexões físicas. Portas individuais de um switch podem ser atribuídas a uma VLAN específica. Outras portas podem ser usadas para interconectar fisicamente os switches e permitir o tráfego de várias VLANs entre os switches. Essas portas são chamadas Trunks (troncos).

Os administradores usam VLANs para segmentar redes com base em fatores como função, equipe ou aplicativo. Os dispositivos em uma VLAN atuam como se estivessem em sua própria rede independente, mesmo que compartilhem uma infraestrutura comum com outras VLANs. Uma VLAN pode separar grupos que têm dados confidenciais do resto da rede, diminuindo as chances de violações de informações confidenciais. Troncos permitem que indivíduos na VLAN do RH estejam conectados fisicamente a vários switches diferentes.

As VLANs oferecem uma maneira de limitar o tráfego de transmissão em uma rede comutada. Os hackers podem atacar também a disponibilidade e o desempenho da VLAN. Para proteger a VLAN, monitorar seu desempenho, usar configurações avançadas e instalar regularmente patches e atualizações.

## Zona Desmilitarizada (DMZ)
Uma zona desmilitarizada (DMZ) é uma pequena rede entre uma rede privada confiável e a Internet.
- Acesso a redes não confiáveis: Os servidores Web e de correio geralmente são colocados na DMZ para permitir que os usuários acessem uma rede não confiável, como a Internet, sem comprometer a rede interna.
- Zonas de risco: A maioria das redes tem de duas a quatro zonas de risco: a LAN privada confiável, a DMZ, a Internet e uma extranet.
	- Na zona de LAN, o nível de risco é baixo e o nível de confiança é alto. 
	- Na zona da extranet, o nível de risco é médio-baixo e o nível de confiança médio-alto.
	- Na DMZ, o nível de risco é médio-alto e o nível de confiança é médio-baixo.
	- Na zona da Internet, o nível de risco é alto e o nível de confiança é baixo.
- Modelo zero-trust: Os firewalls gerenciam o tráfego de ponta a ponta (tráfego que vai entre os servidores no data center da empresa) e o tráfego de ponta a ponta (dados que entram e saem da rede da empresa). Para proteger sua rede, uma empresa pode implementar um **modelo de confiança zero**. Confiar em usuários e endpoints automaticamente na empresa pode colocar qualquer rede em risco, já que usuários confiáveis podem se mover por toda a rede para acessar dados. A rede Zero Trust monitora constantemente todos os usuários na rede, independentemente de status ou função.

## Blindagem (codificação) de dispositivos sem fio e móveis

## Segurança de dispositivos sem fio
A Wired Equivalent Privacy (WEP) foi o primeiro protocolo de segurança usado para redes sem fio. Isso foi substituído pelo Wi-Fi Protected Access (WPA), que melhorou a segurança das conexões sem fio.
- Configuração de WPA: O Wi-Fi Protected Access (WPA) foi a resposta do setor de computadores para enfraquecer a utilização do padrão WEP. A configuração mais comum de WPA é WPA-PSK (Pre-Shared Key, Chave pré-compartilhada). As chaves usadas pelo WPA são 256 bits, um aumento significativo sobre as chaves de 64 bits e 128 bits usadas no sistema WEP.
- Recursos do WPA: O padrão WPA forneceu várias melhorias de segurança. Primeiro, o WPA fornecia verificações de integridade da mensagem (Message Integrity Checks - MIC) que poderiam detectar se um invasor tinha capturado e alterado os dados transmitidos entre o ponto de acesso sem fio e um cliente sem fio. Outra melhoria importante de segurança foi o protocolo TKIP (Temporal Key Integrity Protocol, Protocolo de integridade da chave temporal). O padrão TKIP proporcionou a capacidade de tratar, proteger e alterar melhor as chaves de criptografia. O AES (Advanced Encryption Standard, Padrão de criptografia avançada) substituiu o TKIP por um melhor gerenciamento de chaves e proteção de criptografia.
- WPA2: Como resultado, o lançamento do padrão WPA2 (Wi-Fi Protected Access II, Acesso protegido por Wi-Fi II) aconteceu em 2006. Isso introduziu o uso obrigatório de algoritmos AES e substituiu o TKIP pelo modo de cifra de contador pelo protocolo de código de autenticação de mensagens de cadeia de bloco (CCMP).
- WPA3: O WPA3 adicionou mais recursos ao WPA2, como a manutenção de algoritmos criptográficos robustos e a melhoria da troca de chaves.
- Como utilizar Wi-Fi Protected Setup (WPS): A Configuração protegida por Wi-Fi (WPS) pode ser usada para configurar uma rede doméstica sem fio segura. Conectar dispositivos de IoT à rede sem fio No entanto, o WPS apresenta uma grande vulnerabilidade de segurança, pois o PIN do usuário pode ser descoberto através de um ataque de força bruta. Por isso, o WPS não deve ser usado e deve ser desativado por completo.

## Autenticação
Dispositivos móveis e sem fio se tornaram o tipo predominante de dispositivos na maioria das redes modernas. Eles oferecem mobilidade e conveniência, mas estão vulneráveis a diversos problemas de segurança digital. Essas vulnerabilidades incluem roubo, invasão e acesso remoto não autorizado, sniffing, ataques man in the middle e ataques contra o desempenho e a disponibilidade. A melhor forma de proteger uma rede sem fio é usar autenticação e criptografia.
- Autenticação de sistema aberto: Qualquer dispositivo sem fio pode se conectar à rede sem fio. Use esse método quando a segurança não for uma preocupação
- Autenticação de chave compartilhada: Fornece mecanismos para autenticar e criptografar dados entre um cliente sem fio e um AP ou roteador sem fio

## Protocolos de autenticação
O protocolo de autenticação extensível (EAP) é uma estrutura de autenticação usada em redes sem fio. Vamos descobrir como isso funciona.
1. O usuário solicita a conexão à rede sem fio através de um access point.
2. O access point solicita dados de identificação (nome de usuário) do usuário, que é então enviado para um servidor de autenticação.
3. O servidor de autenticação solicita a prova de que a ID é válida.
4. O access point solicita prova de que a ID é válida do usuário, na forma de uma senha.
5. O usuário fornece a senha ao access point. O access point envia de volta para o servidor de autenticação.
6. O servidor confirma que o nome de usuário e a senha estão corretos e passa essas informações para o access point e o usuário.
7. Conecte-se à rede sem fio.

Exemplos:
- EAP-TLS: Alta segurança dificil implementação
- PEAP: não exige certificado do cliente, segurança média
- EAP-TTLS: não exige certificado do cliente, segurança média
- EAP-FAST: não exige certificado do cliente nem do servidor, segurança média

## Autenticação mútua
- Access points não autorizados: Um access point é qualquer dispositivo de hardware que permite que outros dispositivos sem fio se conectem a uma rede com fio. Qualquer dispositivo que tenha uma interface transmissora sem fio e cabeada ligada a uma rede pode, possivelmente, agir como access point não autorizado. O access point não autorizado muitas vezes imita um access point autorizado, permitindo que os usuários se conectem à rede sem fio, mas potencialmente roubando seus dados ou realizando outras atividades nefastas no processo.
Quando você se conecta a um access point não autorizado, o impostor que o configura pode solicitar e copiar dados do seu dispositivo. Esse tipo de ataque man in the middle é muito difícil de detectar e pode resultar em credenciais de logon roubadas e dados lidos.

A autenticação mútua é a autenticação de duas vias que pode impedir access points não autorizados. É um processo no qual as duas entidades em um link de comunicação se autenticam antes de se conectarem. Isso permite que os clientes detectem access points não autorizados e evitem esses ataques MitM.

## Métodos de comunicação
- wifi e bluetooth
- comunicações de campo próximo
- infravermelho
- USB

## Gerenciamento de dispositivos móveis
Um dispositivo móvel emitido por uma empresa pode conter dados pessoais e organizacionais; ele pode ser de propriedade da corporação ou habilitado pessoalmente (COPE).
Uma empresa também pode ter uma opção de consumerização de TI (BYOD). As políticas de segurança e proteção de dados precisam ser aplicadas quando houver informações corporativas confidenciais no dispositivo do usuário.

### Segmentação e conteinerização do armazenamento
A segmentação do armazenamento e a conteinerização permitem separar o conteúdo pessoal e do trabalho em um dispositivo. Ele fornece uma área autenticada e criptografada que separa as informações confidenciais da empresa dos dados pessoais do usuário.
A conteinerização também nos permite:
- Isolar os aplicativos.
- Controle as funções do aplicativo.
- Exclua as informações do container.
- Bloqueie ou limpe o dispositivo remotamente.

### Gerenciamento de conteúdo
Uma empresa precisa considerar os riscos de segurança envolvidos no uso de aplicativos que compartilham dados, por exemplo, Dropbox, Box, Google Drive e iCloud. Um sistema de segurança de gerenciamento de identidades pode ser usado para controlar quais dados um usuário pode acessar.

### Gerenciamento de aplicativos
A lista de permissão permite que você **assine digitalmente** as aplicações para que você possa autorizar as aplicações que os usuários podem instalar. Isso ajuda a garantir que as aplicações instaladas sejam provenientes de fontes confiáveis.
A autenticação usando senhas fortes é uma prática recomendada para os aplicativos que exigem credenciais de usuário.

## Proteções de dispositivo móvel
Não importa se um dispositivo móvel é de propriedade da empresa ou é um dispositivo pessoal usado para o trabalho, medidas precisam ser implementadas para mantê-lo protegido contra ameaças digitais.
Jailbreaking, root e sideload são formas de contornar as limitações de um dispositivo para fazer coisas que o dispositivo está impedido de fazer. Os usuários podem tentar fazer o **jailbreak** (dispositivos da Apple) ou **root** (dispositivos Android) para executar um aplicativo que não está autorizado ou não está disponível na loja.
O jailbreak remove a restrição de que apenas aplicativos autorizados pela Apple podem ser executados no dispositivo. O enraizamento ignora a arquitetura de segurança do Android para permitir acesso administrativo completo ao dispositivo. Ambos representam um risco para a empresa. 
Há soluções disponíveis que podem detectar um dispositivo com "jailbroken" ou "rooteado". Um dispositivo é então marcado como não compatível e removido da rede ou tem o acesso negado a aplicativos organizacionais.
As lojas de aplicativos de terceiros também podem representar um risco para as empresas porque os aplicativos aos quais elas fornecem acesso não foram avaliados corretamente. O **sideloading (carregamento lateral)** ocorre quando o usuário percorre as configurações de aplicativo aprovado para instalar aplicativos não aprovados. Isso é menos invasivo do que fazer jailbreaking ou rooting, mas ainda é um risco.

As proteções contra ameaças a dispositivos móveis incluem:
- Os **bloqueios de tela** exigem uma senha, um PIN ou um padrão para acessar o dispositivo.
- A **autenticação biométrica** usa uma característica física exclusiva (impressão digital, face, íris ou voz).
- A **autenticação com reconhecimento de contexto** usa aprendizado de máquina para determinar o acesso com base no comportamento normal do usuário.
- A **limpeza remota** exclui os dados do dispositivo, caso ele seja roubado ou perdido.
- A **criptografia completa** do dispositivo pode criptografar todos os dados em um dispositivo móvel.

## Rastreamento de GPS
O GPS (Global Positioning System, Sistema de posicionamento Global) usa satélites e computadores para determinar a localização de um dispositivo. A tecnologia de GPS é um recurso padrão em smartphones e oferece rastreamento de posição em tempo real que normalmente pode localizar um local a aproximadamente 5 metros. Muitos aplicativos de celular usam rastreamento por GPS para rastrear a localização do telefone. Alguns aplicativos usam a delimitação geográfica ou geolocalização, que usa a identificação por radiofrequência (RFID) para determinar uma área geográfica.
As notificações por push às vezes também usam geolocalização e delimitação geográfica. Isso permite que as empresas locais “enviem” mensagens publicitárias com base nas configurações de localização de um usuário. Infelizmente, os invasores digitais cada vez mais experientes começaram a usar notificações push para capturar dados.

# Resiliência de cybersegurança

## Alta disponibilidade
O termo alta disponibilidade descreve sistemas concebidos para evitar períodos de inatividade. A disponibilidade contínua de sistemas de informação é imprescindível, não só para as empresas, mas para a vida moderna, já que todos nós usamos e dependemos de computadores e sistemas de informação mais do que nunca. Sistemas de alta disponibilidade normalmente incluem estes três princípios de projeto:
- Eliminar pontos únicos de falha: O primeiro princípio que define os sistemas de alta disponibilidade começa com a identificação de todos os dispositivos e componentes do sistema cuja falha resultaria em falha em todo o sistema. Os métodos para eliminação de pontos únicos de falhas incluem dispositivos de hot standby, componentes redundantes e várias conexões ou caminhos.
- Fornecer transição confiável: Fontes de alimentação redundantes, sistemas de energia de backup e sistemas de comunicação de backup proporcionam transição confiável.
- Detectar falhas à medida que ocorrem: O monitoramento ativo do dispositivo e do sistema detecta vários tipos de eventos, incluindo falhas do dispositivo e do sistema. Os sistemas de monitoramento podem até acionar o sistema de backup em caso de falha.

## Os cinco Noves
Toda empresa quer poder operar ininterruptamente, mesmo em condições extremas, como durante um ataque. Dentre as práticas mais populares de alta disponibilidade estão os cinco noves. Ela recebe esse nome do objetivo de atingir uma taxa de disponibilidade de 99,999%, ou seja, cinco noves em seguida. Isso significa que o período de inatividade é menos de 5,26 minutos por ano.
### Sistemas padronizados
A padronização dos sistemas propicia que os sistemas usem os mesmos componentes. Os inventários de peças são mais fáceis de manter, e é possível trocar componentes durante uma emergência.
Nas instalações com sistema de informação altamente seguro, guardas controlam o acesso a áreas confidenciais da empresa. O benefício do uso de guardas é que eles podem se adaptar mais do que sistemas automatizados. Guardas podem aprender e distinguir muitas condições e situações diferentes e tomar decisões imediatamente.

### Clustering
Clusters de vários dispositivos agrupados proporcionam um serviço que parece ser uma única entidade para um usuário. Se um dispositivo falhar, os outros dispositivos permanecem disponíveis.

### Sistemas de componente compartilhado
Os sistemas são criados para que um sistema completo possa substituir um que falhou.

## pontos únicos de falha
Únicos pontos de falha são links fracos na cadeia que podem provocar interrupção das operações da empresa. Um único ponto de falha é qualquer parte da operação da empresa cuja falha significa falha completa de todo o sistema - em outras palavras, se falhar, o sistema inteiro falhará.
Um ponto de falha único pode ser uma parte específica do hardware, um processo, uma parte específica de dados ou até mesmo um utilitário essencial. Geralmente, a solução para um ponto único de falha é modificar a operação crítica, de modo que esta não confie em um único elemento. A empresa também pode criar componentes redundantes na operação crítica, com o objetivo de assumir o processo, caso algum desses pontos falhem

## Redundância N+1
A redundância N+1 garante a disponibilidade do sistema, no caso de falha de um componente. Os componentes (N) precisam ter, no mínimo, um componente de backup (+1).
Uma boa maneira de pensar sobre isso é que, no caso de um piso plano, um carro tem quatro pneus (N) e um sobressalente (+1) no porta-malas.
Embora um sistema N + 1 contenha equipamento redundante, não é um sistema totalmente redundante.

## RAID
![[raid.png]]O RAID obtém os dados normalmente armazenados em um único disco e os espalha entre várias unidades. Se qualquer disco único RAID0 for perdido, o usuário poderá recuperar os dados de outros discos que também hospedam os dados.
O RAID também pode aumentar a velocidade da recuperação de dados, já que várias unidades recuperarão os dados solicitados mais rapidamente do que um disco fazendo o mesmo.
Uma solução RAID pode ser baseada em software ou hardware. Uma solução baseada em hardware requer um controlador de hardware especializado, no sistema que contenha as unidades RAID.
Os termos a seguir descrevem as várias maneiras pelas quais o RAID pode armazenar dados na matriz de discos.
- **Espelhamento** - Armazena dados duplicados em uma segunda unidade.
- **Distribuição** - Grava dados em várias unidades para que segmentos consecutivos sejam armazenados em unidades diferentes.
- **Paridade** - mais precisamente, tirar a paridade. Após a distribuição, as somas de verificação são geradas para verificar se não há erros nos dados distribuídos. Essas somas de verificação são armazenadas em uma terceira unidade.
Existem outras arquiteturas RAID, que combinam principalmente os elementos acima.

## Spanning Tree
A redundância aumenta a disponibilidade da infraestrutura da rede, protegendo-a de um ponto único de falha, como um cabo ou um switch com falha na rede.
Quando os designers projetam a redundância física em uma rede, pode haver loops e quadros duplicados. Os loops e quadros duplicados têm consequências graves para uma rede comutada.
O Spanning Tree Protocol (STP) soluciona esses problemas. A função básica do STP é prevenir loops em uma rede, quando os switches se interconectarem por vários caminhos. O STP garante que os links físicos redundantes estejam livres de loop e que apenas um caminho lógico seja executado entre todos os destinos na rede. O STP bloqueia intencionalmente os caminhos redundantes que poderiam provocar um loop.
Bloquear os caminhos redundantes é fundamental para evitar loops na rede. Os caminhos físicos ainda existirão para fornecer redundância, mas o STP desativa esses caminhos para evitar que ocorram loops. Se um cabo ou switch da rede falhar, o STP recalculará os caminhos e desbloqueará as portas necessárias, para permitir que o caminho redundante se torne ativo.

## Redundância de roteador
O gateway padrão é normalmente o roteador que proporciona acesso dos dispositivos ao resto da rede ou à Internet. Se houver somente um roteador como gateway padrão, é um ponto único de falha. A empresa pode escolher instalar um roteador de standby adicional.
o roteador de encaminhamento e o roteador standby usam um protocolo de redundância para determinar qual roteador deve assumir o papel ativo na redundância. Cada roteador está configurado com um endereço IP físico e um endereço IP do roteador virtual. Dispositivos finais usam o endereço IP virtual como o gateway padrão. O roteador de encaminhamento e o roteador standby usam seus endereços IP físicos para trocar mensagens periódicas. O objetivo dessas mensagens é ter certeza de que os dois ainda estão on-line e disponíveis. Se o roteador em espera parar de receber essas mensagens periódicas do roteador de encaminhamento, ele perceberá que é o único roteador disponível e assumirá a função de encaminhamento. Enquanto isso, como os PCs na rede ainda se comunicam com o roteador virtual em 192.0.2.100, eles permanecem on-line apesar de tudo o que aconteceu, já que o roteador virtual agora encaminha para o que era anteriormente o roteador de espera. A capacidade de uma rede de se recuperar dinamicamente da falha de um dispositivo que atua como um gateway padrão é conhecida como **redundância de primeiro salto**.

## Redundância Local
Uma empresa pode precisar pensar em redundância de local, dependendo de suas necessidades.
- Replicação síncrona:
	- Sincroniza os dois locais em tempo real
	- Requer alta largura de banda
	- Os locais devem ser próximos um do outro, para reduzir a latência
- Replicação Assíncrona:
	- Não sincronizados em tempo real, mas muito próximo disso
	- Requer menos largura de banda
	- Os sites podem estar mais distantes, pois a latência é o menor dos problemas
- Point-in-time-Replication:
	- Atualiza periodicamente a localização dos dados de backup
	- Mais conservador em termos de largura de banda, pois não exige uma conexão constante
O equilíbrio correto entre custo e disponibilidade determinará a escolha correta para uma empresa.

## Design resiliênte
Resiliência representa os métodos e configurações usados para tornarem um sistema ou rede tolerante a falhas.

### Resiliência de aplicativo
Resiliência de aplicativo é a capacidade do aplicativo reagir a problemas em um de seus componentes sem parar de funcionar. Um administrador precisará, eventualmente, desativar aplicativos para aplicações de patches, atualizações de versão ou para implantar novas funcionalidades.
Alcançar a resiliência da infraestrutura de aplicativos significa evitar a perda de clientes, de funcionários ou de negócios devido a uma falha de aplicativo.
A figura mostra três soluções de disponibilidade para abordar a resiliência de aplicativos. À medida que o fator de disponibilidade de cada solução aumenta, a complexidade e os custos também aumentam.
- **Hardware tolerante a falhas** (mais complexo e mais caro) é um sistema projetado com a colocação de múltiplos componentes essenciais em um mesmo computador.  
- **Arquitetura de cluster** é um grupo de servidores que funcionam como se fossem um único sistema.
- **Backup e restauração** Cópias de backup de arquivos com a finalidade de poder restaurá-los se ocorrer perda de dados (menos complexo e menos caro).

**Resiliência do IOS**

O IOS (Interwork Operating System, Sistema operacional Interwork) para roteadores e switches Cisco incluem um atributo resiliente de configuração. Permite recuperação mais rápida se alguém, intencionalmente ou não, reformatar a memória flash ou apagar o arquivo de configuração de inicialização. Este atributo mantém uma cópia de trabalho segura do arquivo de imagem do IOS do roteador e uma cópia do arquivo de configuração de execução. O usuário não pode remover esses arquivos seguros, também conhecidos como o bootset primário.

Os comandos mostrados na figura protegem o arquivo de imagem IOS e o arquivo de configuração em execução.

## Sistema e backup de dados
Uma empresa pode perder dados se os criminosos digitais o roubarem, se o equipamento falhar, ou se ocorrer um desastre ou outro erro, então é importante fazer backup dos dados regularmente.
Um backup dos dados armazena uma cópia das informações de um computador na mídia de backup removível. Quando essa mídia é removível, o operador armazena essa mídia de backup em um local seguro.
Fazer backup de dados é uma das formas mais eficazes de proteção contra perda de dados. Se houver falha no hardware do computador, o usuário pode restaurar os dados do backup, depois que o sistema estiver funcional.
Uma política de segurança sólida deve incluir backups de dados regulares. Os backups de dados são, normalmente, armazenados em outro local, para proteger a mídia de backup, se algo acontecer com a instalação principal.
- frequência
- armazenamento
- segurança
- validação

## Projetar um sistema de alta disponibilidade
- Eliminação ou redução de pontos únicos de falha
- Tolerância a falhas
- Resiliência do sistema

## Potência
Uma questão crítica na proteção de sistemas de informação são os sistemas de energia elétrica e as considerações sobre energia. Um fornecimento contínuo de energia elétrica é fundamental nas enormes instalações de armazenamento de dados e de servidores atuais.
Aqui estão algumas regras gerais na construção de sistemas eficazes de alimentação elétrica:
- Data centers devem estar em uma fonte de alimentação diferente do resto do edifício.
- Fontes de alimentação redundantes: dois ou mais feeds (fontes de alimentação) provenientes de duas ou mais subestações elétricas.
- Condições de alimentação.
- Backup de sistemas de energia são, muitas vezes, necessários.
- Uma UPS deve estar disponível para sistemas de desligamento normais.

## Aquecimento, ventilação e ar-condicionado (HVAC)
Sistemas HVAC são críticos para a segurança de pessoas e sistemas de informação nas instalações da empresa. Ao projetar instalações modernas de TI, esses sistemas desempenham um papel muito importante na segurança geral.
- Sistema HVAC: controlam o ambiente, incluindo temperatura, umidade e fluxo do ar
- É necessário manter o ambiente nas condições especificadas pelos produtos (hardwares) da empresa
- Empreiteiro de sistemas de HVAC
- Riscos à segurança da empresa: Dados armazenados em diferentes lugares

## Controle de ameaças a instalações físicas
As empresas podem implementar várias medidas para controlar ameaças a instalações físicas: Por exemplo:
- Implementar controle de acesso e cobertura de circuito fechado de TV (CCTV) em todas as entradas
- Estabelecer políticas e procedimentos para os convidados que visitam as instalações
- Testar a segurança do edifício usando meios cibernéticos e físicos para obter acesso de forma secreta
- Implementar a criptografia de crachá para acesso de entrada
- Planejamento de recuperação de desastres
- Planejamento da continuidade dos negócios
- Treinamento e conscientização de segurança
- Sistema de marcação de ativos

# Sistemas embarcados e especiais

## Ameaças a setores importantes de indústrias
Ao longo da última década, ataques cibernéticos como Stuxnet provaram que um ataque cibernético pode destruir ou interromper infraestruturas essenciais. O ataque Stuxnet, especificamente, foi direcionado ao sistema SCADA (Supervisory Control and Data Acquisition, Controle de supervisão e aquisição de dados) e foi usado para controlar e monitorar processos industriais. O SCADA e outros sistemas de controle industrial (ICSs) são usados nos sistemas de manufatura, produção, energia e comunicação.

## O surgimento da internet das coisas
A Internet das coisas (IoT) é o conjunto de tecnologias que permitem a conexão de vários dispositivos à Internet. A evolução tecnológica associada ao advento da IoT está mudando os ambientes comerciais e de consumo.
Um dos setores mais rápidos da tecnologia da informação é o uso de sensores e dispositivos inteligentes. O setor de informática identifica esse setor como a Internet das Coisas (IoT).
Empresas e consumidores usam dispositivos de IoT para automação de processos, monitoramento de condições ambientais e sistema de alerta ao usuário sobre condições adversas. A maioria dos dispositivos de IoT se conecta a uma rede por meio de tecnologia sem fio. A maioria dos dispositivos IoT se conectam a uma rede via tecnologia sem fio e incluem câmeras, fechaduras, sensores de proximidade, luzes e outros tipos de sensores usados para coletar informações sobre o ambiente ou o status de um dispositivo. Vários fabricantes de dispositivos usam IoT para informar os usuários que precisam substituir peças, que componentes estão falhando ou que suprimentos estão acabando.

Para proteger dispositivos de IoT:

- Proteção da rede sem fio.
- Saiba exatamente quais dispositivos estão se comunicando em sua rede.
- Saiba o que cada um dos dispositivos de IoT na sua rede faz.
- Instale o software de segurança nos dispositivos sempre que possível.
- Proteja smartphones e aplicativos móveis usados para se comunicar com dispositivos de IoT.

## Sistemas integrados
Sistemas integrados capturam, armazenam e acessam dados. Eles apresentam desafios de segurança exclusivos devido à ampla adoção pelo mundo corporativo e pelo consumidor. Eles são usados em Smart TVs, sistemas de controle de HVAC, dispositivos médicos e até mesmo automóveis.

Uma técnica é usar a tecnologia **System on Chip (SoC)**. A tecnologia SoC é um módulo de hardware "Small Form Factor" (SFF). Exemplos de clientes incluem dispositivos como Raspberry Pi e Arduino. Esses dispositivos são computadores de placa única que podem ser implementados usando um "Field-Programmable Gate Array" (FGPA), um circuito integrado que pode ser programado ou modificado em campo. Isso significa que o usuário pode fazer alterações após a implantação do dispositivo.
Esses dispositivos têm um bom poder de processamento fornecido em um espaço reduzido. Isso reduz o consumo de energia, reduz os custos e oferece melhor desempenho do que os componentes tradicionais maiores. O SoC integra um microcontrolador, uma aplicação ou microprocessador e periféricos como uma GPU, um módulo de Wi-Fi ou um coprocessador. O processador pode executar um sistema operacional como Windows, Linux ou Android.
Muitos desses dispositivos de SoC têm autenticação ruim e / ou não podem ser atualizados ou corrigidos. Devido à natureza desses dispositivos, um nível de confiança implícita é necessário, pois não há nenhum programa formal para verificar os controles de segurança.

## Equipamento VoIP

Voz sobre IP (VoIP) usa redes como a Internet para fazer e receber chamadas de telefone.

**De que equipamento você precisa?**
Você precisa de uma conexão com a Internet e um telefone para VoIP. Várias opções estão disponíveis como configuração do telefone:
- Um telefone tradicional, com um adaptador (o adaptador atua como uma interface de hardware entre um telefone tradicional, analógico e uma linha digital VoIP)
- Um telefone ativado para VoIP
- Software VoIP instalado em um computador

**O VoIP é seguro?**

A maioria dos serviços de VoIP do consumidor usam a Internet para chamadas de telefone. Muitas organizações, no entanto, usam suas redes privadas porque elas fornecem mais segurança e melhor qualidade de serviço. A segurança de VoIP só é confiável se houver uma segurança de rede subjacente. Os criminosos virtuais direcionam esses sistemas para obter acesso a serviços de telefone gratuitos, espionar telefonemas, ou para afetar o desempenho e a disponibilidade.

**Como você pode proteger seu serviço de VoIP?**

Implemente as seguintes contramedidas para proteger o VoIP:
- Criptografe os pacotes de mensagens de voz para proteger contra espionagem.
- Use o SSH para proteger gateways e switches.
- Altere todas as senhas padrão.
- Use um sistema de detecção de invasão para detectar ataques, como envenenamento ARP.
- Use autenticação forte para mitigar o spoofing de registro (os criminosos virtuais roteiam todas as chamadas recebidas da vítima para eles), representação de proxy (engana a vítima para se comunicar com um proxy falso configurado pelos criminosos virtuais) e sequestro de chamadas (a chamada é interceptada e reencaminhada para um caminho diferente, antes de chegar ao destino).
- Implemente firewalls que reconhecem VoIP para monitorar os streams e filtrar sinais anormais.

## Sistemas integrados de finalidade específica
Os sistemas integrados funcionam em diversos setores. Você pode encontrar dispositivos incorporados para fins especiais em setores como o médico, automotivo e de aviação.

## Tecnologias de enganação
As empresas usam tecnologias de dissimulação para distrair os invasores das redes de produção. Eles também os usam para aprender os métodos de um invasor e para alertar sobre possíveis ataques que poderiam ser lançados contra a rede. A dissimulação adiciona uma camada falsa à infraestrutura da empresa.

- honeypots
- sinkhole DNS: impede a resolução de nomes de host para URLs específicas e pode afastar os usuários de recursos mal-intencionados