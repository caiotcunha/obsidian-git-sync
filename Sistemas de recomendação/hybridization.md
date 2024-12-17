## **Modelos de Hibridização**  

### Monolíticos
Único sistema, combina diversas fontes de dados
1. Feature combination: usa features sem tratamento do recomendador contribuinte
2. Feature augmentation: o recomendador principal recebe os dados tratados pelo recomendador auxiliar

### Parallelized hybridization
Única fonte de dados, multiplos recomendadores, saída única. É o design menos invasivo, utilizando os recomendadores como caixas pretas. A saída pode ser combinada com ponderação ou switching no caso mais extremo. Os pesos para as saídas podem ser aprendidos dinâmicamente.
1. Mixed: os resultados de dois recomendadores são combinados na interface. A hibridização é usada como um problema de satisfação de restrições.
2. Weighted hybridization: As notas são combinadas de maneira linear com o vetor dos pesos. Para otimizar os pesos, minimiza a função de erro.
3. Switching: Se um recomendador não retorna um bom score troca para o outro. Depende do dado que está sendo tratado.

### Pipelined hybridization
Uma fonte de dados, múltiplos recomendadores. Os recomendadores são dispostos de maneira sequencial de modo que a saída de um é a entrada de outro. A saída é única.

1. Cascade: As recomendações são restritas pelo recomendador predecessor. As recomendações subsequentes não podem introduzir novos itens. Gera resultados bem precisos.
2. Meta-level: Recomendador baseado nos modelos do predecessor.