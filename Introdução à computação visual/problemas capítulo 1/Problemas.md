1. Qual a diferença entre resolução espacial e profundidade da imagem?
	Resolução espacial está relacionada à densidade de pixels na imagem, quanto maior a densidade, maior a resolução. Já a profundidade da imagem está relacionada ao número de bits necessários para armazenar a imagem digitalizada, quanto maior o número de tons de cinza, maior o número de bits
2. Qual o tamanho de uma imagem gerada pela amostragem de uma região de 200 x 300 cm² em intervalos de 0.1mm na direção x e 0.2mm na direção y ? 20000 x 15000
3. Qual a profundidade em bits de uma imagem com 8192 níveis de cinza? 13
4. Considere um protocolo de transmissão de dados consistindo em pacotes de um bit de início, 8 bits de informação e 1 bit de parada. Qual o tempo, em segundos, para transmitir uma imagem de 1024 x 1024 pixels com 256 níveis de cinza a uma taxa de transmissão de 9600 bits/segundo? 
	- a imagem tem 2²³ bits
	- 10 bits por pacote, então 960 pacotes. Cada pacote leva 8 bits úteis, então 7680 bits por segundo
	- 2²³/7680 ≃ 1092 segundos -> arredonda pra cima 1093 segundos
5. Mostre que a distância D4 entre dois pontos p e q é igual ao caminho-4 mais curto entre esses dois pontos. Esse caminho é único?
	- a distância d4 forma um losângulo em torno do ponto, de forma que os pontos vizinhos-4 do ponto estão à 1 de distância e os pontos vizinho-8 que não são vizinhos-4 estão à 2 pontos de distância.
	- o caminho-4 sempre se move em relação aos vizinhos-4 que são os de distancia menor dentro do losângulo
	- se sempre escolher o caminho com menor distância entre os vizinhos-4, chegamos ao menor caminho entre os pontos.  Mesmo funcionamento do algoritmo de Dijkstra.
	- o caminho não é único caso o ponto q esteja localizado diagonalmente ao ponto p. Nesse caso seria possível sair de qualquer dois vizinhos-4 mais próximos de q e encontrar caminhos ótimos de mesmo custo.
6. Considere a imagem binária abaixo, onde pixels de valor 1 pertencem ao objeto e de valor 0 pertencem ao fundo. Determine o número de componentes conexos existentes na imagem com a vizinhança-4 e vizinhança-8.
	- vizinhança-4 = 6.
	- vizinhança-8 = 3.
7. Desenvolva um algoritmo para identificar componentes conexos 3D em uma imagem binária tridimensional considerando-se o conceito de vizinhança-6.
	- comece no primeiro pixel da imagem
		- se ele for 1 marque ele como visitado e pertencente ao componente conexo 1
	- visite todos os vizinhos de pixel, se o vizinho for 1 visite também todos os seus vizinhos marcando aqueles com 1 como pertencentes ao componente conexo 1
	- após a recursão terminar siga para o próximo pixel à direita do inicial, até encontrar um pixel 1 que não esteja marcado como pertencente a nenhum componente conexo
	- visite recursivamente os vizinhos-6 desse pixel marcando eles como pertencentes ao componente conexo 2
	- repita com todos os pixels da imagem
8. feita no caderno
9. Descreva os principais tipos de ruído que podem ser modelados em uma imagem:
	1. Ruído impulsivo: gerado por uma diferença muito grande entre um píxel e outro. Como no caso de um pixel branco rodeado de pixels pretos
	2. Ruído Gaussiano:  caracterizado pela ocorrência de pixels com valores de intensidade que variam conforme a distribuição Gaussiana (u é a média, sigma² é a variância)
10. pulei
11. Descreva entropia em imagens de níveis de cinza
	1. O conceito de entropia é a quantidade de informação transmitida por um canal ou gerada por uma fonte. Quanto maior o valor da entropia maior a incerteza e portanto mais informação está associada ao canal.
	2. a entropia é o somatorio das probabilidades de um pixel assumir determinado valor de intensidade vezes o log dessa probabilidade. o somatorio depois é multiplicado por -1
	3. entropia é 0 quando todos os valores da imagem são o mesmo tom de cinza e máxima quando a imagem tem a mesma quantidade de cada tom de cinza
	4. nao esta relacionada à espacialidade
12. Descreva as principais utilizações das operações de adição e subtração de imagens
	1. adição: utilizada para sobrepor uma imagem à outra. também utilizada para a remoção de ruídos
	2. subtração: usada para identificar diferenças entre as imagens
13. Qual é a função dos cones e bastonetes?
	1. cones servem para captar cores e discernir detalhes em imagens. os bastonetes são mais sensíveis à baixa intensidade de luz e permitem uma  percepção geral da imagem
14. Diferencie os conceitos de amostragem e quantização no processo de digialização da imagem
	1. A amostragem consiste em discretizar o domínio de definição da imagem nas direções x e y gerando uma matriz de n x m amostras
	2. A quantização é escolher o número inteiro L de níveis de cinza permitidos para cara ponto da imagem
15. Descreva as principais formas de representação de imagens digitais
	1. se ela for em tons de cinza geralmente é representada por uma matriz em que cada valor é a intensidade do tom de cinza do pixel correspondente. Imagens podem ser representadas em diferentes resoluções por estruturas hierárquicas em formato de pirâmide. Caso a imagem seja colorida, cada valor da matriz é associado a um vetor que possui o valor daquele pixel nas várias bandas. Uma imagem multidimensional pode ser representada por uma sequencia de imagens monocromaticas ou multibanda ao longo do eixo espacial z.