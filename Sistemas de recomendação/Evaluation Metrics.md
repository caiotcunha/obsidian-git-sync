- Acurácia da Predição
- Suporte de decisão
- Acurácia do ranking

Podemos ter métricas mais específicas como: diversidade, novelty e serendipity. Também métricas para avaliações holísticas (da página inteira). As métricas são escolhidas de acordo com a tarefa proposta.

## Accuracy metrics
- Acurácia de uma precisão: proximidade de uma preferência verdadeira
	- a preferência verdadeira fica escondida no modelo de avaliação offline e é desconhecida no modelo online
	- geralmente medida por métricas de erro
- Erro absoluto remove direção
- Erro absoluto quadrado penaliza mais erros maiores
- Média das médias de usuários para tirar o bias de diferença no número de avaliações entre usuários
- RMSE é o melhor
- diferentes escalas de rating não podem ser comparadas
- Erros podem ser dominados por usuários/itens populares

## Além da acurácia
### Precisão
- Porcentagem dos itens recomendados que são relevantes
- é sobre ter a maior quantidade de coisas úteis em uma recomendação

### Recall
- Porcentagem dos itens relevantes que são recomendados
- é sobre não perder coisas importantes em uma recomendação

## Position blindness
- A posição de uma recomendação em um ranking deve ser levada em conta, pois itens em posições mais visíveis são mais importantes

## Avarage precision (AP)
Média dos valores de precisão no ranking de posições onde itens relevantes foram encontrados.

## Reciprocal rank (RR)
Mede o quão fundo o usuário tem q procurar por um item relevante. Divide pela posição do item no ranking

## Discounted cumulative gain (DCG)
Mede a utilidade do item em cada posição.
$$
\mathrm{DCG}(R, G) = \sum_{c=1}^{k} \frac{r_{ui_c}}{\log_2(c+1)} \quad \text{(linear gain, e.g., in a graded scale)} \quad \text{(position-based discount)}
$$
também pode enfatizar maiores ganhos usando uma função quadrática em cima.

## Norm. discounted cumulative gain (nDCG)

$$
\mathrm{DCG}(R, G) =\frac{{DCG}(R, G)}{{iDCG}(R, G)}
$$
- na prática costumamos usar a média dess norma para todos os usuários

## Business metrics
### Coverage
Mede a porcentagem de produtos para os quais o recomendador pode fazer uma predição. Ou uma predição personalizada, ou uma predição acima do nível de confiança estipulado. O interesse do sistema é chegar ao catálogo todo.

### Diversity
Mede o quão diferente as recomendações são. Ajuda a aumentar a diversidade nas vendas.

### Serendipity
Mede a ocorrência de eventos fortuitos. Tipicamente baseado em raridade.
