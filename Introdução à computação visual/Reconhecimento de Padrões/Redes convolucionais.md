Aprender transformações dos dados que tornam mais fácil extrair informações úteis quando construindo classificadores ou outros preditores

## DeepLearning:
- Formado pela composição de múltiplas transformações não lineares de informação para atingir representações mais abstratas e úteis

## Loss function:
- Mede a diferença entre o valor correto e o output do sistema
- A média da função Loss é o erro médio em relação a um conjunto de exemplos já classificados.
- O objtetivo é encontrar o conjunto de pesos que minimiza o erro no treinamento
- Pode gerar overfitting

## Gradient-Based Learning
- A função loss pode ser minimizada estimando o impacto de pequenas variações de parâmetros na função loss
	- medida pelo gradiente da função loss wrt the parameters
- Um conjunto de parametros W é rea e diferenciável em quase qualquer lugar
- Calcula o gradiente descendente

## From filtering to learning
Objetivo: selecionar um grupo de filtros que tenha a melhor performance em classificação
Ideia: minimizar o número de filtro com o mínimo de impacto na performance

### Multichannel filtering
- Extração de features + classificação
- input é decomposto em feature images usando o banco de filtros
- resultado: um vetor de features para cada pixel
- Cada canal de feature pode ser trocado por um neurônio

### Filtering vs Neural Network
- Filtering: smoothing after the nonlinear function
- NN: classifica um pixel baserado em uma janela MxM

Filtro receptivo para uma rede neural é menor do que filtrar com a mesma máscara

## Fully-connected
- Treinar um classificador fully-connected multi-layer network with pixels as the inputs
- Desvantagens:
	- número de pesos na primeira camada é muito grande pra imagens de tamanho grande
	- Sem invariância em relação à translação ou distorção
	- A rede pode aprender distorções, mas vai gerar redundância nos pesos
	- Precisa de muitas amostrar para treinar
	- Topologia do input é ignorada

## CNN -> Convolution Neural Networks
Ideias para a arquitetura:
Local receptive fields,shared weights, spatial sub-sampling
Alcança alguma invariancia à translação, escala e distorção
- Local receptive fields:
	- cada unidade de uma camada recebe inputs de um conjunto de unidades localizadas numa pequena vizinhança da camada anterior
	- Local fields: neurônios extraem features básicas (cantos e bordas) que são combinados com as próximas camadas para detectar features mais complexas
	- Detectores básicos: úteis em várias regiões da imagem
	- unidades em uma camada são organizadas em planos (todas as unidades tem o mesmo conjunto de pesos) - output das unidades de uma camada é o feature map
	- Receptive field MxM tem MxM + 1 (bias) parâmetros de treinamento
	- passos:
		- Scaneia a imagem com uma única unidade
		- Guarda os estados dessa unidade em cada lugar do input no feature map
		- Equivalente à convolução + additive bias + non-linear Function
	- sub-sampling
		- Depois de detectada a posição exata da feature é menos importante
		- posição precisa pode danificar o processo
		- objetivo: reduzir a resolução espacial do feature map
		- camadas de convolução e sub-sampling são alternadas
		- Cada unidade calcula a média, multiplica pelo coeficiente de treinamento, adiciona o bias e passa pela função sigmoid
		- Grande invariância geometrica é alcançada por alternar as camadas
	- convolução considera mascaras 3D ( M x M x k )
- Parameters = (Filter width x Filter height x Channels) + Bias