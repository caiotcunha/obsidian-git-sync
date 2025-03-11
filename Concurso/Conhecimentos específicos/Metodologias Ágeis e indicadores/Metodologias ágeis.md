A característica principal de processos ágeis é a adoção de **ciclos curtos e iterativos de desenvolvimento**, por meio dos quais um sistema é implementado de forma gradativa; começando por aquilo que é mais urgente para o cliente. De início, implementa-se uma primeira versão do sistema, com as funcionalidades que segundo o cliente são para ontem, isto é, possuem prioridade máxima. Em seguida, essa versão é validada pelo cliente. Se ela for aprovada, um novo ciclo — ou **iteração** — inicia-se, com mais algumas funcionalidades, também priorizadas pelos clientes. Normalmente, esses ciclos são curtos, com duração de um mês, talvez até um pouco menos. Assim, o sistema vai sendo construído de forma incremental, sendo cada incremento devidamente aprovado pelos clientes. O desenvolvimento termina quando o cliente decide que todos os requisitos estão implementados.

Características gerais de processos ágeis incluem:
- Baseado em fluxo
- **Menor ênfase em documentação**, ou seja, apenas o essencial deve ser documentado.
- **Menor ênfase em planos detalhados**, pois muitas vezes nem o cliente, nem os Engenheiros de Software têm, no início de um projeto, uma ideia clara dos requisitos que devem ser implementados. Esse entendimento vai surgir ao longo do caminho, à medida que incrementos de produto sejam produzidos e validados. Em outras palavras, o importante em desenvolvimento ágil é conseguir avançar, mesmo em ambientes com informações imperfeitas, parciais e sujeitas a mudanças.
- **Inexistência de uma fase dedicada a design** (_big design up front_). Em vez disso, o design também é incremental. Ele evolui à medida que o sistema vai nascendo, ao final de cada iteração.
- **Desenvolvimento em times pequenos**, com cerca de uma dezena de desenvolvedores. Ou, em outras palavras, times que possam ser alimentados com duas pizzas, conforme popularizado pelo CEO da Amazon, Jeff Bezos.
- Ênfase em novas práticas de desenvolvimento (pelo menos, para o início dos anos 2000), como **programação em pares**, **testes automatizados** e **integração contínua**.

## Extreme Programming (XP)

XP é um método leve recomendado para desenvolver software com requisitos vagos ou sujeitos a mudanças.XP é definido por meio de um conjunto de **valores**, **princípios** e **práticas de desenvolvimento**

### Valores
XP defende que o desenvolvimento de projetos de software seja norteado por três valores principais: comunicação, simplicidade e feedback. 
- Uma boa **comunicação** é importante em qualquer projeto, não apenas para evitar, mas também para aprender com erros. 
- O segundo valor de XP é **simplicidade**, pois em todo sistema complexo e desafiador existem sistemas ou subsistemas mais simples, que às vezes não são considerados. 
- Por último, existem riscos em todos os projetos de software: os requisitos mudam, a tecnologia muda, a equipe de desenvolvimento muda, o mundo muda, etc. Um valor que ajuda a controlar tais riscos é estar aberto ao **feedback** dos stakeholders, a fim de que correções de rota sejam implementadas o quanto antes. Em outras palavras, é difícil desenvolver o sistema de software certo em uma primeira e única tentativa.

### Princípios
- Humanidade: o principal recurso de uma empresa são seus colaboradores
- Economicidade: Software tem que gerar benefício econômico
- Benefícios mútuos: decisões tomadas devem beneficiar múltiplos stakeholders
- Melhorias contínuas: sistema que melhora a cada iteração
- Falhas acontecem: software não é uma atividade livre de riscos
- Baby Steps: fazer pouca coisa de cada vez para diminuir o risco
- Responsabilidade Pessoal: responsabilidade não deve ser transferida sem que a outra pessoa aceite

### Práticas sobre o processo de desenvolvimento
A XP recomenda envolvimentos do cliente no projeto. Uma das funções desse representante é escrever as **histórias de usuário** (_user stories_), que é o nome que XP dá para os documentos que descrevem os requisitos do sistema a ser implementado. No entanto, histórias são documentos resumidos, com apenas duas ou três sentenças, com as quais o representante dos clientes define o que ele deseja que o sistema faça, usando sua própria linguagem. Depois as histórias são avaliadas pelos desenvolvedores e recebem uma nota em story points. Não se costuma usar horas ou homem/horas.
A implementação das histórias ocorre em **iterações**, as quais têm uma duração fixa e bem definida, variando de uma a três semanas, por exemplo. As iterações, por sua vez, formam ciclos mais longos, chamados de **releases**, de dois a três meses, por exemplo. A **velocidade** de um time é o número de story points que ele consegue implementar em uma iteração. Sugere-se que o representante dos clientes escreva histórias que requeiram pelo menos uma release para serem implementadas. Ou seja, em XP, o horizonte de planejamento é uma release, isto é, alguns meses. Uma vez realizado o planejamento de uma release, começam as iterações. Antes de mais nada, o time de desenvolvimento deve se reunir para realizar o **planejamento da iteração.** O objetivo desse planejamento é decompor as histórias de uma iteração em tarefas, as quais devem corresponder a atividades de programação que possam ser alocadas para um dos desenvolvedores do time.

### Práticas de Programação

- design incremental
- Programação em pares
- Propriedade coletiva do código
- Testes automatizados
- Desenvolvimento dirigido por testes
- Build Automatizado
- Integração contínua

### Práticas de gerenciamento de projetos
- Ambiente de trabalho: projetos devem ser desenvolvidos em times pequenos (até 10). Devem trabalhar fracionadamente em projetos e numa mesma sala. 
- Contratos com escopo aberto
- Métricas de processo


## Scrum
Scrum é um método ágil, iterativo e incremental para gerenciamento de projetos. Dentre os métodos ágeis, Scrum é também aquele que é melhor definido. Essa definição inclui um conjunto preciso de **papéis**, **artefatos** e **eventos**, que são listados a seguir. No resto desta seção, vamos explicar cada um deles. Mesmo com papeis diferentes, dentro de um time de scrum todos tem o mesmo nível hierárquico.
Times de scrum são auto-organizáveis, ou seja, eles têm autonomia para decidir como e por quem as histórias serão implementadas.
A escolha das ferramentas e métodos utilizados na metodologia de gestão de portfólio é etapa importante e conta com forte participação dos stakeholders envolvidos. O Scrum usa um conjunto de “padrões de processo de software”, que são adequados para projetos com prazos apertados e requisitos que mudam frequentemente.

- **Papéis**: Dono do Produto, Scrum Master, Desenvolvedor.
- **Artefatos**: Backlog do Produto, Backlog do Sprint, Quadro Scrum, Gráfico de Burndown.
- **Eventos**: Planejamento do Sprint, Sprint, Reuniões Diárias, Revisão do Sprint, Retrospectiva.

### Papéis
- Dono do produto: Ele possui a visão do produto a ser construído e escreve as histórias de usuário
- Scrum master: especialista em scrum do time. Garante que as regras do scrum estão sendo seguidas e é um facilitador dos trabalhos e removedor de impedimentos
- Times devem ser cross-funcionais, ou seja, possuem membros de todas as áreas necessárias para o desenvolvimento do produto.

### Principais artefatos e eventos
- Backlog do produto: Lista de histórias/trabalhos relevantes ordenada por prioridade.
- Sprint: interação do scrum.
- Planejamento da sprint: reuniao na qual todo time se reúne para decidir as histórias que serão implementadas na sprint.
- Backlog da Sprint: é gerado ao final do planejamento da sprint. Lista com as tarefas que serão desenvolvidas na sprint, bem como seus prazos.
- Quadro Scrum: dividido em: backlog/todo/doing/testing/done representação visual das tarefas em andamento numa sprint
- Gráfico de burndown: gráfico decrescente das horas que as tarefas a serem implementadas somam

### Outros eventos
- Daily: reuniões rápidas diarias. O que fez no dia anterior, o que pretende fazer no dia, se tem algum impedimento.
- Revisão da Sprint: Mostra os resultados da sprint.
- Retrospectiva: Última atividade de uma sprint. 
- timebox para as coisas é importante

- **Product Backlog:** seu compromisso é a meta do produto (product goal).
- **Sprint Backlog:** seu compromisso é a meta da Sprint (sprint goal).
- **Increment:** seu compromisso é a definição de pronto (definition of done).

### Valores
Os **valores do Scrum**, que guiam o comportamento do Scrum Team, são na verdade cinco: **Comprometimento, Coragem, Foco, Abertura** e **Respeito**.Transparência, inspeção e adaptação são pilares do Scrum que provêm do controle empírico de processos.

## Kanban

O Quadro Kanban é dividido em colunas, da seguinte forma:
- A primeira coluna é o backlog do produto. Como em Scrum, usuários escrevem as histórias, que vão para o Backlog.
- As demais colunas são os passos que devem ser seguidos para transformar uma história do usuário em uma funcionalidade executável. Por exemplo, pode-se ter colunas como Especificação, Implementação e Revisão de Código. A ideia, portanto, é que as histórias sejam processadas passo a passo, da esquerda para a direita, como em uma linha de montagem. Além disso, cada coluna é dividida em duas subcolunas: em execução e concluídas. Por exemplo, a coluna implementação tem duas subcolunas: tarefas em implementação e tarefas implementadas. As tarefas concluídas em um passo estão aguardando serem puxadas, por um membro do time, para o próximo passo. Por isso, Kanban é chamado de um sistema _pull_.

Como em outros métodos ágeis, times Kanban são auto-organizáveis. Isso significa que eles têm autonomia para definir qual tarefa vai ser puxada para o próximo passo. Eles também são cross-funcionais, isto é, devem incluir membros capazes de realizar todos os passos do Quadro Kanban.

Por fim, resta explicar o conceito de **Limites WIP** (_Work in Progress_). Via de regra, métodos de gerenciamento de projetos têm como objetivo garantir um ritmo sustentável de trabalho. Para isso, deve-se evitar duas situações extremas: (1) o time ficar ocioso boa parte do tempo, sem tarefa para realizar; ou (2) o time ficar sobrecarregado de trabalho e, por isso, não conseguir produzir software de qualidade. Para evitar a segunda situação — sobrecarga de trabalho — Kanban propõe um limite máximo de tarefas que podem estar em cada um dos passos de um Quadro Kanban. Esse limite é conhecido pelo nome Limite WIP, isto é, trata-se do limite máximo de cartões presentes em cada passo, contando aqueles na primeira coluna (em andamento) e aqueles na segunda coluna (concluídos) do passo. A exceção é o último passo, no qual o WIP aplica-se apenas à primeira subcoluna, já que não faz sentido aplicar um limite ao número de tarefas concluídas pelo time de desenvolvimento.

O WIP (Work in Progress) é calculado utilizando lead time, entrega do produto, e o throughput, quanta vazao o time consegue dar.

### Lei de Litle