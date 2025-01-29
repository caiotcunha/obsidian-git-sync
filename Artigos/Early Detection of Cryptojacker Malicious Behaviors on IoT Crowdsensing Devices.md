

- Qual o tema ou assunto do texto?
	- mineração de criptomoedas em dispositivos iot
- Qual o problema tratado?
	- com o monero, cryptojackers começaram a explorar vulnerabilidades conhecidas de dispositivos IoT para usa-los na mineração
	- soluções existentes são boas para detectar a fase de mineração
	- no entanto o artigo propõe uma forma de detecção antecipada de modo a evitar a disseminação do malware e uso de recursos
- Qual a dificuldade e relevância do problema tratado?
- Qual a solução dada ao problema?
	- Um framework que combina behavioral fingerprinting and machine learning para detectar as fases preparatórias dos cryptojackers
- Qual a ideia principal/ideia defendida pelo autor?
- Como o autor defende sua ideia?
	- The framework has been deployed in a crowdsensing IoT spectrum sensor, Raspberry Pi, infected by a recent cryptojacker called Linux.MulDrop.14. Promising detection results demonstrate the framework’s suitability while detecting early phases of cryptojackers.
- Qual foi a argumentação do autor?
- O autor demonstra/prova o que foi proposto? Ele consegue alcançar o que foi proposto
- Como ele prova? Qual o método usado?



## Termos que que não entendi
Monero (XNR): Monero is an open-source digital payment
token that can be mined in resource-constrained devices like
IoT and single-board computers.

O Monero usa um [ledger](https://pt.wikipedia.org/wiki/Ledger "Ledger") público (uma _[blockchain](https://pt.wikipedia.org/wiki/Blockchain "Blockchain")_) para registrar todas as transações que são realizadas na rede. No entanto, ao contrário do Bitcoin, o Monero protege por padrão a privacidade de seus usuários ao ofuscar o remetente, o destinatário e a quantia envolvida em cada transação.[[3]](https://pt.wikipedia.org/wiki/Monero#cite_note-CoindeskMining-3) Em função disso, ela é considerada uma moeda anônima e não rastreável.

Monero utiliza um processo de mineração de prova-de-trabalho para criar as novas unidades da moeda, que é otimizado para ser mais eficiente em processadores comuns ([CPUs](https://pt.wikipedia.org/wiki/Unidade_central_de_processamento "Unidade central de processamento")). Isso permitiu que a moeda fosse minerada de maneira rentável em computadores comuns, tornando possível a mineração de maneira distribuída. O processo de mineração igualitário do Monero acabou abrindo novas fontes de rendimento para os mineradores, tanto legítimas quanto maliciosas

A arquitetura de Monero é baseada no [algoritmo de hash](https://pt.wikipedia.org/w/index.php?title=Algoritmo_de_hash&action=edit&redlink=1 "Algoritmo de hash (página não existe)") de prova-de-trabalho [CryptoNight](https://pt.wikipedia.org/w/index.php?title=CryptoNight&action=edit&redlink=1 "CryptoNight (página não existe)"), que vem do protocolo [CryptoNote](https://pt.wikipedia.org/wiki/CryptoNote "CryptoNote").[[7]](https://pt.wikipedia.org/wiki/Monero#cite_note-7) O Monero é projetado para ser resistente à mineração com circuitos integrados para aplicações específicas (ASICs), que é comumente usada para minerar outras moedas como o [Bitcoin](https://pt.wikipedia.org/wiki/Bitcoin "Bitcoin").[[8]](https://pt.wikipedia.org/wiki/Monero#cite_note-CoinCentralVs-8) O [algoritmo](https://pt.wikipedia.org/wiki/Algoritmo "Algoritmo") de mineração RandomX foi desenvolvido para ser extremamente eficiente em processadores comuns (CPUs), em detrimento aos chips encontrados em [placas de vídeo](https://pt.wikipedia.org/wiki/Placa_de_v%C3%ADdeo "Placa de vídeo") (GPUs) e aos ASICs.

However, these approaches are not valid for some IoT-oriented application scenarios like crowdsensing, where single-board devices are connected to private networks that cannot be monitored. First, most solutions detecting cryptojackers are focused on powerful devices, and their feasibility is not evaluated in resource-constrained and single-board devices. Second, most solutions focus on detecting the cryptojacker mining phase, which is easily detected due to the significant impact on the GPU or CPU consumption of the device. However, it has not been explored if preliminary and preparatory phases needed to set up and execute the mining could be detected. Last but not least, the resource consumption evaluation of ML-based solutions detecting cryptojackers is missing.

In [cryptography](https://en.wikipedia.org/wiki/Cryptography "Cryptography"), a **ring signature** is a type of [digital signature](https://en.wikipedia.org/wiki/Digital_signature "Digital signature") that can be performed by any member of a set of users that each have [keys](https://en.wikipedia.org/wiki/Key_(cryptography) "Key (cryptography)"). Therefore, a message signed with a ring signature is endorsed by someone in a particular set of people. One of the security properties of a ring signature is that it should be computationally infeasible to determine _which_ of the set's members' keys was used to produce the signature. Ring signatures are similar to [group signatures](https://en.wikipedia.org/wiki/Group_signature "Group signature") but differ in two key ways: first, there is no way to revoke the anonymity of an individual signature; and second, any set of users can be used as a signing set without additional setup.

Monero uses Dandelion++, a protocol which obscures the [IP address](https://en.wikipedia.org/wiki/IP_address "IP address") of devices producing transactions.

# Roteiro

## introdução
Boa tarde, meu nome é caio teles essa é a caroline carvalho e hoje vamos apresentar o trabalho Early detection of Cryptojacker Malicious Behaviors on IoT Crowdsensing Devices

Bom pra começar precisamos entender alguns conceitos para conseguir acompanhar a ideia proposta no artigo e a relevância dela. Mais especificamente precisamos entender o conceito de cryptojacker, o que são iot crowdsensing Devices e como essas duas coisas se relacionam

Então cryptojacking é o ato de explorar um dispositivo para mineirar cryptomoedas. 

As criptomoedas são uma moeda digital projetada para não ser dependente de uma autoridade central, como um governo ou banco. A validade de cada moeda é proveniente da blockchain

O processo de adicionar novos blocos na blockchain gera as moedas e é chamado de mineração. Nesse processo basicamente o minerador pega as informações do bloco anterior da blockchain, contidos no block header, e junta com um número nonce passa por uma função hash. Se o hash for o esperado o minerador consegue adicionar um bloco à blockchain e receber a recompensa.

O que é importante ressaltar é que esse processo é lento e existem hardwares específicos para essa função que são muito mais eficientes na mineração, são chamados de ASICs. As empresas que detém esses hardwares dominam a mineração de bitcoins. Como foi mostrado na apresentação do samuel na semana passada.

Aquele ali é a logo do bitcoin a criptomoeda mais famosa.
Esse é um hardware específico da bitmain uma marca famosa. Esse custa 4.500 dolares

O próximo conceito é crowdsensing que é uma técnica onde um grupo grande de dispositivos IoT coleta dados de maneira colaborativa com o objetivo de extrair alguma informação de interesse. No caso do artigo eles analisam especificamente a coleta de dados de frequência de rádio por sua aplicabilidade em redes de rádio cognitivo. Essas redes  são sistemas que monitoram o espectro de frequencias em tempo real e realocam os usuários para frequências livres ou subutilizadas melhorando a eficiência da rede.

Bom e como essas coisas se conectam? 

Eu tinha dito que a mineração é um processo computacionalmente caro e que existem hardwares específicos pra isso, então pra que se preocupar em proteger dispostivos IoT de sensoriamento, já que esses dispositivos geralmente possuem poder de computação baixo, limitações em termo de memória e de consumo de energia?

De fato esses dispositivos não estavam na mira dos criptojackers inicialmente, mas tudo isso mudou em 2014 com a criação da criptomoeda monero.

O algoritmo de mineração randomX usado no monero foi desenvolvido para ser extremamente eficiente em processadores comuns como CPUs em detrimento das GPUs e ASICs geralmente usados na mineração de bitcoin. 

Os principais pilares do monero são anonimidades e privacidade. Todos os detalhes das transações são ofuscados, ao contrário do bitcon. Perfeito pra quem quer praticar atos ilegais, quer dizer manter a privacidade.

Isso permitiu que a moeda fosse minerada em processadores de IoT. Segundo os criadores do monero essa decisão visava fomentar a distribuição da mineração. Como vimos na apresentação do samuel a mineração de bitcoin é concentrada em grandes empresas

O esforço para proteger esses dispositivos, então começou a crescer significativamente. Apesar de soluções anteriores de identificação de criptojackers obterem bons resultados o artigo aponta algumas limitações nos trabalhos anteriores.

A maior parte das soluções de detecção de criptojackers são focadas em dispositivos com maior poder computacional

A maior parte das soluções relacionadas à dispositivos com limitações de recursos focam na análise do tráfico de rede, mas essas soluções não são válidas para algumas aplicações de IoT como o crowdsensing, pois os dispositivos são conectados à redes privadas que não podem ser monitoradas

A maior parte das soluções focam em identificar na fase da mineração, já que o consumo de GPU ou CPU aumenta significativamente tornando mais fácil de identificar

A avaliação do consumo de soluções baseadas em ML não é apresentada. Isso é importante em um cenário de IoT porque os recursos são limitados.

Para melhorar os desafios citados anteriormente, o artigo propoe e implementa um framework orientado a IoT e baseado em ML que usa a impressão digital para detectar e classificar as fases preparatórias dos cryptojackers maliciosos.

## Trabalhos relacionados
(4) análise das assinaturas estáticas -> bom resultado, mas não funciona com criptojackers novos e é afetado por ténicas de ofuscação

(6) Combina uma análise estática com dinâmica. A parte estática é o monitoramento dos system calls e a parte dinâmica monitora a sequência de execução

(1) Os autores usam métodos estatísticos e um conjunto específico de features para treinar um modelo de machine learning capaz de diferenciar cryptojackers de aplicativos comuns

(5) Usam debuggers para monitorar os OPcodes executados pela CPU em cada tempo de execução

(11) e (17)  focam em detectar browser-based cryptojackers

(9) Detecta verificando a utilização de CPU

(10) detecta uma variedade de ataques em Raspberries Pi combinando eventos de kernel e aprendizado supervisionado e não supervisionado

## Cenário
ElectroSense é uma plataforma open source que analisa o espectro de frequência de rádio e implanta sensores que usam hardware simples. 
O modelo utilizado como sensor nesse trabalho é um raspberry Pi 3 modelo B

Essa plataforma é composta por 3 partes: os sensores, o backend da plataforma e o site que oferece diferentes serviços

Esse backend gerencia algumas funcionalidades dos sensores, passa para os usuários os dados coletados e decodifica algumas transmissões específicas.


o sensor foi infectado com um trojan com comportamento de cryptojacker. Esse trojan foi executado usando acesso SSH, seria o caso de algum hacker conseguisse o acesso ao rapyberry com uma técnica de bruteforce nas senhas.

1) Cria um backdoor e ganha acesso ao dispositivo via irc(Internet Relay Chat). Executa a si mesmo e tenta eliminar qualquer outro malware presente no dispositivo
2) Baixa as dependências necessárias para o minerador, acaba se conectando a 5 endereços de servidor
3) Instala e builda o cryptominer. Um mineirador multithread chamado de minerd
4) Tenta espalhar o cryptojacker pela rede. Baixa um network sacnner basico e tenta conectar na porta 22 de todos os dispositivos encontrados com o usuário e senha padrão do raspyberry
5) Começa a mineração da criptomoeda, nesse caso se junta a uma pool de mineradores. Usa o site minergate


Apesar dessas fases serem específicas desse malware, os malwares desse mesmo tipo costumam seguir os mesmos passos. São bem documentados em knowledge bases de cyberattacks ATT&CK proposed by MITRE