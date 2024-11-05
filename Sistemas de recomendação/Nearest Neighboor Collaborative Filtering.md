Basicamente dividido em uma abordagem baseada em usuários e uma abordagem baseada em itens. Explora as similiaridades entre intens e usuários para gerar uma melhor recomendação.

## User Based Collaborative Filtering
Usuários similares produzem um sinal melhor. Podemos usar as avaliações de usuários similares ao usuário alvo para fazer recomendações. As similaridades entre usuários são instáveis e seus vetores extremamente esparsos.
### passos
- Normalizing ratings:
	- As avaliações dadas por cada usuário não significam a mesma coisa. É necessário normalizar as avaliações do usuário por suas próprias avaliações. Em geral isso é feito normalizando em torno da média, ou seja, tira a média das avaliações do usuário e diminui de cada uma das suas avalizações.
- Seleção de vizinhos:
	- Devemos pensar de que forma devemos definir os vizinhos do usuário alvo. Existem várias abordagens para isso como: todos os usuários, usuários aleatórios, usuários acima de um limiar de similaridade e os primeiros k usuários em um ranking de similaridade. As últimas opções costumam funcionar melhor.
	- Em teoria quanto maior melhor, mas o custo computacional aumenta. Na prática mais vizinhos gera mais ruído, menos vizinhos gera menor cobertura.
- Computar as similaridades:
	- A princípio qualquer similaridade funciona (Jaccard, pearson, cosine). Empiricamente algumas performam melhor.
	- Pearson correlation:
		- faz automaticamente a centralização pela média
		- computada em cima de avaliações em comum
		- e para usuários com poucos dados?
			- coloca um peso por confiança
	- Cosine similarity
		- tem um peso por confiança já implementado
		- precisa de centralização pela média (adjusted cosine) para performar como pearson
- Agregar as notas:
	- Na prática só faz a media ponderada com a similaridade.

### Análise da performance
Em geral, O(m²n) sendo m usuários e n itens. O problema é m e n da ordem de 10⁷

### Otimizações
- Explorar a simetria da matriz
- Explorar a esparsidade da matriz
- Pre computar similaridades offline
	- gera o problema de ser pouco atualizada, menos dinâmica

## Item based collaborative filtering
Recomendar itens similares à itens consumidos pelo usuário alvo. Segue os mesmos passos de uma abordagem por usuários, mas dessa vez utilizando itens. Pode deixar pré computado a similaridade de todos os pares de itens, mas essa operação é cara computacionalmente. Em geral, se computa a similaridade entre os itens comprados pelo usuário alvo e decide a nota agregando os ratings com média ponderada. O modelo pode manter uma lista de itens que são vizinhos do item alvo, de forma que o recomendador possa consultar.

### Vantagens sobre o de usuário
- Vetores de similaridade menos instáveis (melhor para calcular offline)
- Custo menor, pois em geral um site de sucesso tem menos itens que usuários
- Vetores de itens são geralmente menos esparsos
- Seleção de vizinhos pode ser mais flexivel: itens avaliados pelo usuário, itens vistos pelo usuário, itens no carrinho do usuário, etc

### Análise da performance
Em geral, O(n²m) sendo m usuários e n itens. O problema é m e n da ordem de 10⁷.

## Escolha entre os tipos
Para se escolher entre os dois tipos de algoritmos é necessário levar em conta as demandas específicas do sistema em algumas areas como:
- Acurácia: Esse aspecto depende da razão entre número de usuários e o número de itens no sistema. Em geral, um pequeno número de vizinhos de alta confiança é de longe preferível a muitos vizinhos de baixa confiança. No caso de sistemas de grande sucesso, ou seja, com um número de usuários muito maior do que o de itens, a abordagem de itens pode produzir uma recomendação mais acurada. Ao contrário sistemas com menos usuários que itens (ex: recomendação de artigos) se beneficiam mais de uma abordagem baseada em usuários
- Eficiência: Esse aspecto depende da razão entre número de usuários e o número de itens no sistema. Sistemas com mais usuários tornam a abordagem baseada em itens mais eficiênte, dado o menor custo para computar as similaridades.
- Estabilidade: A escolha entre uma abordagem baseada em itens ou usuários depende da frequência das mudanças nos itens e nos usuários do sistema. Em um sistema em que a lista de itens é relativamente estável a abordagem por itens é preferível, já que as similaridades podem ser computadas de maneira offline de maneira infrequente.
- Justificabilidade: Uma vantagem da estratégia baseada em itens é que os próprios itens podem ser usados para justificar a recomendação. Ao apresentar uma lista com os vizinhos ao usuário e permitir que ele altere essa lista é possível permitir que o usuário participe ativamante do processo de recomendação. Isso não é tão fácil em uma abordagem baseada em usuários.
- Serendipity (sorte): Recomendações baseadas em itens são muito mais seguras e não favorecem o descobrimento pelo usuário de novos interesses. Já recomendações baseadas em usuário tem muito mais potencial para recomendar coisas diferentes, mas que o usuário pode gostar.