### **1. Motivação para Diversidade em Recomendações**

- **Evitar Redundância**: Sistemas de recomendação muitas vezes apresentam itens muito semelhantes, redundantes ou já conhecidos pelo usuário.
- **Resolver Ambiguidade**: Na busca e recomendação, a ambiguidade nas preferências dos usuários pode ser tratada com maior diversidade.
- **Satisfação do Usuário**: Usuários têm um desejo natural por variedade, o que contribui para maior engajamento.
- **Desempenho do Negócio**:
    - **Long Tail**: Recomendando produtos de nicho que possuem menos concorrência e margens maiores de lucro.
    - **Ampliação de Horizonte**: Expõe os usuários a novos itens, aumentando descobertas e vendas.

### **2. Problema de Diversificação**
- **Definição Formal**: Consiste em reorganizar um conjunto de itens inicialmente ranqueados para maximizar a diversidade, considerando aspectos latentes dos usuários e itens.
- **Abordagens**:
    - **Gulosa**: Selecionar iterativamente itens que cobrem mais aspectos novos.
    - **Maximal Marginal Relevance (MMR)**: Balancear relevância e novidade, promovendo itens relevantes, mas dissimilares.
    - **IA-Select**: Utiliza categorias como aspectos para modelar diversidade.

### **3. Métricas de Avaliação**
- **Diversidade**:
    - **Intra-List Diversity (ILD)**: Média das distâncias entre os itens recomendados.
    - **Unexpectedness**: Distância entre os itens recomendados e o histórico do usuário.
    - **Temporal Diversity**: Mede a variedade de itens recomendados ao longo do tempo.
- **Novidade**:
    - **Popularidade Inversa**: Mede o quão "raro" é o item no contexto geral.
    - **Surpresa**: Itens que fogem das expectativas baseadas no histórico.