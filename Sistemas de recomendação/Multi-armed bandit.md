## exploration vs exploitation dilemma
explore: pode perder recompensas conhecidas
exploit: pode perder ação ótima

### estratégias
#### Explore then exploit
Performa mal na parte de exploração, e pode ficar agarrado em uma ação sub-ótima para sempre

#### Epsilon Greedy
1-e -> com essa chance define se explora ou exploit
tipicamente melhor que o primeiro método
e -> fixado 

#### Decaying Epsilon Greedy
Gradualmente se move para a exploitation
Podemos usar várias funções diferentes para o decaimento dependendo da necessidade do sistema

#### Upper confidence bound policy


#### Bayesian Bandit
No contexto do **Bayesian Bandit**, o modelo utiliza a inferência bayesiana para ajustar as probabilidades de cada opção com base nas recompensas observadas. Por exemplo:
- No começo, você pode não saber muito sobre as recompensas de cada braço, então você assume uma distribuição ampla e uniforme para cada um.
- À medida que você puxa um braço e observa a recompensa, essa recompensa é usada para atualizar a distribuição sobre as recompensas futuras para aquele braço.
- O objetivo é sempre maximizar a recompensa total, escolhendo as opções que, com base nas distribuições atuais, têm maior probabilidade de oferecer boas recompensas no futuro.