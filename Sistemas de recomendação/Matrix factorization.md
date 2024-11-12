Diminuir a matriz sem perder informações importantes.
## Latent Factor Models
Modelos de fatores latentes são amplamente utilizados para mapear tanto usuários quanto itens para um espaço de características de dimensão reduzida. Essa representação permite capturar padrões latentes nas interações entre usuários e itens.

#### Soluções Exatas

- **Matrix Decomposition (Decomposição de Matrizes)**: Esse é um método exato, onde a matriz de interações entre usuários e itens (como uma matriz de avaliações) é decomposta em duas matrizes de fatores latentes, uma para os usuários e outra para os itens. A decomposição mais comum é a SVD (Singular Value Decomposition), mas outras variações, como a fatoração de matrizes, também são utilizadas. Essas técnicas exigem que a matriz de entrada seja densa e, portanto, precisam de uma boa quantidade de dados.
##### SVD vantagens
- A qualidade da previsão geralmente aumenta
	- ratings ruído são filtradas
	- correlações não triviais decobertas
- Pode diminuir a qualidade levando em consideração que preferências por item específico não são mais consideradas.
##### SVD desvantagens
- Falta de transparência
- Valores faltantes
	- imputar (caro)
	- ignorar
- Complexidade da computação O(m²n + n³)

#### Soluções Aproximadas

Essas soluções são usadas quando o cálculo exato da decomposição é computacionalmente custoso ou quando lidamos com matrizes esparsas.

- **Regularized Empirical Risk Minimization (Minimização de Risco Empírico Regularizado)**: Aqui, a perda do modelo é minimizada com uma penalidade de regularização para evitar overfitting. Em vez de calcular uma decomposição exata, o modelo aprende os fatores latentes de forma a minimizar uma função de erro regularizada.
    
- **Pointwise, Pairwise, Listwise Losses (Perdas ponto a ponto, par a par, e ordenadas)**:
    
    - _Pointwise_: A perda é calculada em cada interação usuário-item individualmente, visando prever corretamente cada interação.
    - _Pairwise_: Foca em pares de interações, tentando garantir que um item relevante seja classificado mais alto do que um item irrelevante.
    - _Listwise_: Considera uma lista de itens para cada usuário, otimizando a ordenação de todos os itens recomendados.
- **Negative Sampling (Amostragem Negativa)**: Em problemas de recomendação, a maioria das interações usuário-item são negativas (ausência de interação). A amostragem negativa envolve selecionar aleatoriamente interações negativas para incluir no treinamento, o que reduz a carga computacional ao evitar o cálculo para todos os itens não interagidos.

