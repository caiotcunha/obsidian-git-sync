Simula uma comunicação entre uma estação STA e um ponto de acesso AP e avalia a taxa de transmissão em função de diferentes configurações de modulação e codificação largura de canal e intervalo de guarda.

1. Modulation and Coding Scheme: é um parâmetro essencial na comunicação sem fio, como nas redes Wi-Fi e LTE. Determina a combinação de dois fatores:
	1. Modulação: Que define a quantidade de dados transmitidos por cada símbolo de sinal (ex: QPSK,16QAM,64-QAM)
	2. Codificação: Que é a taxa de codificação dos dados para proteção contra erros (ex: 1/2, 3/4)
2. Guard Interval(GI): representa o intevalo de proteção entre os pacotes de dados transmitidos em redes Wi-Fi.
	1. Evitar interferências entre símbolos (ISI)
	2. Trade-off entre eficiência e proteção: menor o valor maior a eficiência, e menor a proteção.

4. Objetivos:
	- Entenda como a rede sem fio (Camadas física e enlace) é configurada  
		- Modelos físicos Yans e Spectrum:
			- Yans:
	- Entenda como a camada de transporte (TCP/UDP) é configurada  
	    
	- Entenda como as aplicações são instaladas nos nós da rede
		- Usando o InternetStackHelper instala o protocolo de internet nos nós
		- Testa se é UDP ou TCP:
			- UDP: UdpServerHelper instala no ponto de acesso, UdpClientHelper instala nas estações.
			- TCP: PacketSinkHelper no servidor e o OnOffHelper no cliente.
		- É importante ressaltar que os atributos devem ser setados de acordo (ex:MaxPackets,Interval,PacketSize)
		- 
	- Entenda o que são throughput e goodput
		- throughput: volume de unidades de informação que um sistema pode processar em um período específico.
		- goodput: é a taxa de transferência em nível de aplicativo de uma comunicação.
		- largura de banda: maior quantidade de dados que pode ser enviada por meio de uma conexão. Geralmente em bits por segundo (bps).
4. Objetivo do código: esse código é útil para avaliar o desempenho de uma rede Wi-Fi 6 com diferentes parâmetros e imprime a capacidade de throughput de acordo com as configurações de MCS e de rede.