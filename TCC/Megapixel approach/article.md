Limitações trabalhadas do artigo anterior trabalhada pelo novo:
1) A fila de pixels ativos tem grande overhead porque o custo de computação associado a cada pixel armazenado é baixo
2) O processamento parelelo baseado em pixels leva a uma alta divergência de treads e acessos não contínuos à memoria
3) O tamanho da fila tende a ser maior ou da ordem de magnitude do domínio da imagem
4) IWPP faz uma quantidade significativa de reprocessamento

Para resolver esses problemas o artigo apresenta um algoritmo de propagação em ondas irregulares baseado em megapixels.

Contribuições
1) Baseando-se em megapixels para fazer operações morfológicas reduziram o overhead da fila de gerenciamento
2) Desenvolvimento de otimizações novas para evitar redundância de computação na propagação da onda e um nível maior de processamento de megapixel para aumentar a eficiência de propagação
3) Nós realizamos uma avaliação completa de todas as propostas, comparando nossas soluções com o estado da arte para duas operações importantes: reconstrução morfológica e preenchimento de buracos. Os resultados experimentais mostram balba bal ao mesmo tempo em que os requisitos de memória do IMWPP são reduzidos em XXX em comparação com o IWPP

# Sessão 2 (background e trabalhos relacionados)

1) Reconstrução morfológicas: A **reconstrução morfológica** é uma técnica avançada de processamento de imagens baseada em operações morfológicas (dilatação ou erosão) que, a partir de um **marcador** e de uma **máscara**, “reconstrói” regiões de interesse de forma precisa, preservando a conectividade e a forma dos objetos Ela é amplamente usada em tarefas como remoção de ruído, extração de componentes conectados, preenchimento de buracos e aprimoramento de contornos
2) Fill Holes: Tomar o complemento da imagem binária e usa reconstrução morfológica a partir de marcadores nos contornos. Complementar o resultado para obter os buracos preenchidos.


# Sessão 3 Irregular Megapixel Propagation Pattern

## GPU implementation
- Queue Design: Global write queue e Global Read queue. Durante uma iteração a GRQ é não é modificada.
- Quando a GRQ está vazia os ponteiros trocam entre ela e o GWQ.
- LWQ: Local write queue
