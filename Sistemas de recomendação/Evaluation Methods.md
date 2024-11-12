Avaliação é a determinação sistemática de mérito,significância e valor de um sistema usando critérios governados por um conjunto de métricas. Podemos avaliar em sistemas de recomendação 3 métricas: Eficiência, efetividade, aplicação. A avaliação deve seguir o método científico. 
## Definindo sucesso
A métrica de sucesso vai depender do que estiver sendo avaliado. Se for a aplicação, vamos tentar medir e melhorar a experiência do usuário.  Se for a performance, vamos medir o número de vendas por exemplo.

## Método científico

### Formulando hipóteses
Deve criar uma hipótese falseável, seus testes devem ter o que provar

### Fazendo experimentos
- Componentes chave
	- setup experimental
	- análise de resultados
- Reprodutibilidade
	- devemos especificar todos os detalhes necessários para reproduzir o experimentos
- Comparações para referências (baselines)
	- métricas sem comparativo não significam nada
- Escolhendo baselines
	- vanilla baselines
		- ter o efeito proposto desligado
	- competing baselines
		- Exploit the proposed effect de uma maneira diferente
## Online evaluation
- Prospective experiments
	- como podemos prever futuras preferências?
- Benchmark utilizando interações ao vivo de usuários
	- pouco reprodutivo, mas muito realista
- Foco em feedback implícito

### Controlled experiments
- Quando diferentes variantes rodam ao mesmo tempo, somente duas coisas podem explicar a mudança nas métricas: as features e a aleatoriedade ( que pode ser contornado com testes estatísticos )
### A/B test
- O grupo de usuários é dividido aleatoriamente entre controle e teste

## Offline evaluation
- Testar com pessoas sempre é caro:
	- teste A/B pode demorar muito para convergir
	- expor suários a protótipos é arriscado
- método barado e rápido para simular o comportamento de usuários reais
- experimentos em retrospectiva
- Benchmark usando dataset estáticos
	- muito reprodutivel
	- pouco realista
- o objetivo é estimar a qualidade do recomendador
	- avaliação de alto rendimento
	- repostas para perguntas importantes da pesquisa
- Geralmente não conseguem responder se o recomendador realmente funciona
	- user-based avaliação necessária
	- conexão às métricas relacionadas ao negocio é fraca

### Como montar seu dataset
- divida os dados disponíveis em treino e teste
- divida os usuários/itens
	- aprenda de alguns
	- preveja outros
	- problema: itens/usuários cold-start
- divida por interação
	- aprenda de partes do perfil de itens e usuários
	- preveja as interações escondidas
	- a vantagem é a mistura realista de cold-start test cases
	- problema: interações não são realmente i.i.d
	- Interações futuras podem transbordar para o set de treinamento
- divida por interação temporal
	- aprenda de partes do perfil de itens e usuários
	- preveja as interações escondidas
	- a vantagem é a mistura realista de cold-start test cases
	- resolve o problema de interações futuras
	- poderia testar com janelas deslizantes diferentes para aprender desviar dos aspectos sazonais


