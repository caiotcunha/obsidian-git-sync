Quando da configuração dos parâmetros do autoencoder, o tamanho do espaço latente é uma informação crucial, pois determina o tamanho do espaço onde os dados de entrada serão comprimidos.

operador cube -> usado para fazer a análise de dados, o cube gera um retorno em 3 dimensões da tabela.

Uma **trigger** é um tipo especial de procedimento armazenado que é automaticamente executado ou disparado quando certos eventos ocorrem em uma tabela ou visão. Esses eventos podem incluir operações como inserção (_INSERT_), atualização (_UPDATE_) e exclusão (_DELETE_).
- **FOR EACH ROW:** Executa a trigger para cada linha afetada pelo comando SQL. Este é o comportamento padrão na maioria dos sistemas de banco de dados.
- **FOR EACH STATEMENT:** Executa a trigger uma única vez para o comando SQL inteiro, independente do número de linhas afetadas.

Primeiramente, na **otimização de consultas**, existem algumas regras heurísticas que são comumente seguidas para transformar e otimizar as consultas. Essas regras incluem:
- **Realizar seleções e projeções o mais cedo possível**: Isso reduz o número de tuplas e colunas tratadas nas operações subsequentes, o que pode melhorar significativamente a eficiência.
- **Atrasar produtos cartesianos**: Produtos cartesianos devem ser evitados quando possível, pois são operações custosas e podem gerar um número muito grande de combinações. Devem ser realizados apenas quando necessários e, de preferência, depois que as junções apropriadas tenham sido aplicadas.
- **Usar junções no lugar de produtos cartesianos**: Sempre que possível, utilizar operações de junção em vez de produtos cartesianos, seguidas por uma seleção.

- **DDL (Data Definition Language)**: utilizada para definir e modificar a estrutura dos dados, como tabelas e índices.
- **DML (Data Manipulation Language)**: usada para manipular os dados, como inserção, atualização e exclusão.
- **DCL (Data Control Language)**: empregada para controlar o acesso aos dados, com comandos como _GRANT_ e _REVOKE_.
- **DSL (Data Query Language)**: utilizada para consultar dados, sendo o _SELECT_ o principal comando.
A cláusula with estipula uma relação temporária cuja definição está disponível apenas à consulta em que essa cláusula ocorre.

 A observabilidade não se limita a identificar a rota de dados pela rede. Ela envolve uma visão mais ampla sobre como os dados e eventos são monitorados e compreendidos dentro do sistema, utilizando métricas, logs e traços.
A questão aborda o conceito de **clusterização** em bancos de dados, que é uma técnica de armazenamento físico que visa melhorar o desempenho das consultas. Quando uma tabela é clusterizada, os registros são armazenados fisicamente no disco de maneira sequencial, baseando-se no valor de um ou mais campos, normalmente correspondendo aos de um índice. Esse índice é conhecido como **índice clusterizado**.

Ao abordarmos a arquitetura de bancos de dados e a confiabilidade das transações, precisamos entender o conceito de propriedades ACID, um acrônimo para Atomicidade, Consistência, Isolamento e Durabilidade (_Atomicity, Consistency, Isolation, Durability_). Estas são as propriedades fundamentais que garantem transações confiáveis em um sistema de banco de dados.

**Atomicidade:** Garante que todas as operações de uma transação são concluídas com sucesso ou, em caso de falha, nenhuma delas é aplicada. É tudo ou nada.

**Consistência:** Assegura que uma transação só pode alterar o estado do banco de dados de uma maneira válida, mantendo sua consistência interna e todas as suas regras e restrições.

**Isolamento:** Determina que as transações sejam executadas de forma isolada umas das outras, prevenindo que as operações concorrentes interfiram entre si, garantindo que o resultado seja o mesmo que se as transações fossem executadas sequencialmente.

**Durabilidade:** Uma vez que uma transação foi confirmada, suas alterações são permanentes e devem persistir mesmo no caso de uma falha de sistema.

A arquitetura de três esquemas divide-se em três níveis:
- **Nível interno:** é o nível mais baixo e descreve como os dados são fisicamente armazenados no sistema. Aqui, são definidos os esquemas físicos, que incluem a estrutura de armazenamento, os métodos de acesso, os índices etc.
- **Nível conceitual:** é o nível intermediário que descreve quais dados são armazenados, e suas relações. É a visão completa do banco de dados, descrevendo o que existe no banco de dados em termos de entidades, atributos e relacionamentos, sem considerar como os dados estão armazenados fisicamente. Define o esquema conceitual.
- **Nível externo:** também conhecido como nível de visão, é o nível mais alto e descreve diversas visões dos usuários. Cada visão é um esquema externo que representa uma parte do banco de dados que é relevante para um certo grupo de usuários. Permite que diferentes usuários tenham diferentes visões dos mesmos dados.

