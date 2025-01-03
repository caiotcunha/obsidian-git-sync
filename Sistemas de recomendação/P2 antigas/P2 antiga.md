1. Como podemos representar as preferências de um usuário para recomendação personalizada baseada em conteúdo?
	1. Podemos representar as preferências de um usuário como um vetor de características em que cada coluna representa uma característica do conteúdo. Por exemplo, no caso de filmes, podriam ser os gêneros como: romance,ação drama, etc.
2. Como representar coldStart users? 
	1. Poderíamos representar usuários novos como vetores vazios, ou vetores com números referentes as médias de cada característica.
3. Learning to rank é uma técnica tipicamente utilizada para reordenação (reranking) dos top k itens retornados por algum modelo de recomendação mais simples, em vez de diretamente sobre todos os itens disponíveis no sistema. Que fatores devem ser considerados na escolha de um valor ótimo de k?
	1. Cobertura e relevância dos itens, trade-off entre eficiência e complexidade, características do domínio, avaliação das métricas e volume de dados
4. feita no caderno