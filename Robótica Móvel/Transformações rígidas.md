- utilizamos um vetor para representar os pontos
- o sistema de coordenadas no qual ele foi definido também deve aparecer
![[Pasted image 20240320134510.png]]
- Um sistema de coordenadas (referêncial,frame) é representado por uma letra maiúscula entre chaves {A}
- vetor unitário possui apenas direção
- cada corpo vai ter um sistema de coordenadas afixado nele
- Matriz de rotação {B} em relação a {A}
	- ![[Pasted image 20240320135315.png]]
	- Vetores unitários de {B} descritos em termos do sistema {A}
- ![[Pasted image 20240320135623.png]]
- Referencial: sistemas de coordenadas que, além  da orientação, possui o vetor posição de origem em relação à outro frame
	- ![[Pasted image 20240320135847.png]]
- Posição: frame em que a matriz de rotação é a identidade 
- Orientação: frame onde o vetor posição é nulo
- Como descrever a posição de um ponto  em relação ao referencial {A}, dado a descrição dele no referencial {B}
**Translação**
- Tendo referenciais com a mesma orientação, mas origens diferentes, basta somar
- ![[Pasted image 20240320141213.png]]
**Rotação**
- Considerando referenciais com a mesma origem, mas orientações diferentes
- Componentes são as projeções do vetor sobre os eixos (vetores unitarios) de seus sistema de referência (frame)
- ![[Pasted image 20240320142104.png]]
- ![[Pasted image 20240320142237.png]]
- ![[Pasted image 20240320142604.png]]
Quando temos as duas (rotação e translação), criamos um referencial intermediário que foi somente rotacionado, calculamos ele e depois prosseguimos normalmente com a translação
