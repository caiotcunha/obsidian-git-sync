

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