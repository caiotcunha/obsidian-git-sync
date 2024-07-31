learning -> minimizar a função de erro.
Para cada um dos seus valores de teste, calculamos quanto os valores de saída deveriam mudar, aumentando pra saída esperada e diminuindo para todas as outras. Ao fazer isso com todos os dados tiramos a média desses pesos, passamos por uma função de ativação (sigmoide ou ReLU) e alteramos na rede, rodando ela novamente e fazendo a mesma coisa até alcançar um mínimo local.
Por questões de rapidez na computação, não se faz os passos com todos os dados e sim com uma parcela deles repetindo várias vezes até que acabem os dados de teste.

