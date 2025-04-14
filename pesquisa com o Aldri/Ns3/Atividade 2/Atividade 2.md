A presente atividade consiste na criação e execução de um cenário de redes no NS3. Este cenário deve atender as seguintes especificações:

1. Implementar uma topologia em barra com 5 nós (os nós não devem mudar de posição)
	1. N0 -- N1 -- N2 -- N3 -- N4
2. Configurar um canal de comunicação sem fio entre os nós
3. Utilize o protocolo de internet (TCP/IPv4), onde o endereço da rede deve ser 10.0.0.0 e mascara 255.0.0.0
4. Desenvolva uma aplicação simples:

1. Cada nó deve ter dois sockets (um para enviar dados e outro para ouvir)
2. O nó N0 deve enviar (pelo socket) um valor inteiro aleatório (entre 0 e 100) apenas para seu vizinho N1, este por sua vez deve imprimir o valor recebido no terminal e encaminhar o dado para N2. O procedimento deve ser repetido até alcançar N4, onde N4 deve imprimir o valor recebido no terminal, gerar um novo valor aleatório (entre 0 e 100) e enviar para o seu vizinho N3, este por sua vez deve imprimir o valor recebido no terminal e encaminhar o dado para N2. O procedimento deve ser repetido até alcançar N1, onde N1 deve imprimir o valor recebido no terminal, gerar um novo valor aleatório (entre 0 e 100) e repetir o mesmo procedimento.

6. O tempo total da simulação deve ser de 30 segundos.


- Primeiro passo é construir a topologia em barra
	- fonte: https://www.nsnam.org/docs/tutorial/html/building-topologies.html
	- Cria os nós
	- instala os o protocolo csma