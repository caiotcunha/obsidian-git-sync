- Medidas que podem ser utilizadas para avaliar a similaridade de uma imagem tansformada g em relação à original f
- Erro máximo
	- não leva em conta a proporção do ruído na imagem toda -> ruim
	- Maior diferença absoluta entre cada ponto
		- ME = max |f(x,y)-g(x,y)|
- Erro médio absoluto
	- média da soma da diferença absoluta de cada ponto
	- leva em conta a média
- qual a razão de elevar ao quadrado uma diferença?
	- penalizar mais as diferenças maiores
	- por isso usamos quadrado ao invés de módulo
	- sistema visual percebe mais diferenças maiores
- erro médio quadrático
	- erro medio absoluto sem módulo e com quadrado
	- não é robusto à diferença de brilho
- coeficiente de correlação
	- maneira de medir que é robusta a mudança de brilho
	- normaliza e joga fora a média
	- mede a relação linear de uma função com a outra
	- somente linear