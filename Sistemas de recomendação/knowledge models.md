São sistemas que utilizam modelos de conhecimento explícitos para recomendar itens aos usuários com base em seus requisitos. Esses sistemas são úteis quando:

- Não há muitos dados de interações anteriores (como classificações ou cliques).
- Os itens são complexos ou difíceis de descrever.
- As preferências dos usuários podem mudar significativamente ou são baseadas em necessidades específicas.


### Métodos utilizados:

1. **Recomendação baseada em restrições**:
    - Os usuários especificam requisitos (absolutos ou relativos) que o sistema utiliza para selecionar itens de um banco de dados.
    - Exemplo: Escolher câmeras digitais com preço inferior a $200, com resistência à água e capacidade de gravação de vídeo.
    - **Consultas conjuntivas**: Uma lista de critérios combinados com operadores lógicos (e.g., "Preço < 200 AND Vídeo = sim").
    - **Tratamento de conflitos**: Quando os requisitos do usuário não podem ser atendidos, o sistema pode relaxar ou modificar restrições.
2. **Recomendação baseada em casos**:
    - Baseia-se em casos ou itens similares ao solicitado.
    - Inclui um processo de critiquing, onde o usuário ajusta critérios iterativamente (e.g., "mais barato" ou "com maior zoom").
    - **Critiquing dinâmico**: Sugestões são geradas dinamicamente com base nos itens restantes no conjunto de candidatos.
3. **Padrões de críticas**:
    - São regras que relacionam atributos de itens para facilitar comparações.
    - Exemplo: "Se uma câmera tem mais megapixels, ela deve ter maior zoom" ou "Se tem vídeo, o preço deve ser menor".

### Case-based reasoning
1. Retrieve an initial case from memory
2. Reuse the retrieved case as first guess
3. Revise the current case if wrong
4. Retain the current case if correct

