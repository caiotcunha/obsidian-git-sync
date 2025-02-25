A ideia principal é recomendar aquilo que já é popular entre os usuários. Essa ideia é aplicável em vários domínios como: livros, filmes, etc. Esse tipo de recomendador não leva em conta o perfil do usuário, nem seu histórico para a recomendação. Assume que preferências passadas indicam preferências futuras.

## Modelagem

Queremos saber o que os usuários consideram relevante, para isso podemos observar os ratings e as ações do usuário. Essas medidas possuem ruídos.
### Explicit feeback
- Rate, Review,vote
Esse tipo de feeback é mais escasso, mas ele tem maior confiança do que o feedback implícito. Precisamos levar em consideração que as notas, mesmo que iguais, não significam a mesma coisa para dois usuários diferentes. Também temos que pensar se o gosto do usuário muda com o tempo.

### Implicit feedback
- View, Click, Purchase
Esse tipo de feeback é mais abundante, mas ele tem menor confiança do que o feedback explícito. Não significa diretamente uma preferência. Existem diferentes tipos de sinais que podem ser captados como: Ação (clicar, skip, tocar, comprar), atenção (ler,escutar,tempo de interação) e cognitivos (eye tracking, brain imaging).

### Como aproveitar o feedback do usuário?
- unary feedback
- binary feedback
- graded feedback

### Cold Start User
Usa uma propriedade global do item como: mais recente, mais popular, mais bem avaliado. Média da nota do item para calcular avaliação.

### O que pode dar errado?
- Feedback não balanceado
	- produtos com menos feedbacks tendem a uma nota mais alta, mas indicam menos confiança
	- podemos utilizar um método para penalizar a nota de um item que tenha poucas avaliações. 
- user agnosticism
	- nem sempre os itens mais populares são adequados a todos os tipos de usuário.
	- podemos computar as estatísticas dividindo por grupos simples como: idade,gênero, localização
		- Melhor, mas ainda não personalizado
- context agnosticism
	- a predição ignora o contexto
	- poderiamos computar associações não personalizadas
		- mas quais?
			- Historical profiles: podem introduzir associações ruins
			- Transaction data: podem limitar vendas futuras
			- Time-constrained profiles: oferecem um compromisso
- 


