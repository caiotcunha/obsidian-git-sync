- **O que são explicações?**
    - Recomendação diz o que você pode gostar.
    - Explicações dizem **por que** você pode gostar.
- Explicações são comunicações que podem:
    - Justificar uma decisão (do ponto de vista do usuário).
    - Influenciar uma decisão (do ponto de vista do sistema).

As explicações têm múltiplos objetivos:

1. **Transparência**: Revelar o processo de recomendação.
    - Exemplo: "porque você comprou XYZ antes".
2. **Validação**: Mostrar como o item atende aos requisitos.
    - Exemplo: "Zoom óptico 10x (você pediu >5x)".
3. **Confiabilidade**: Reduzir incertezas.
    - Exemplo: "Melhor câmera na faixa de preço".
4. **Persuasão**: Influenciar decisões do usuário.
    - Exemplo: "modelo mais leve, mesmo com acabamento simples".
5. **Efetividade**: Ajudar em melhores decisões.
    - Exemplo: "melhor modelo para o seu caso de uso".
6. **Eficiência**: Ajudar em decisões mais rápidas.
    - Exemplo: "único modelo que atende todos os requisitos".
7. **Educação**: Ensinar sobre o domínio.
    - Exemplo: "Estabilizador evita imagens borradas".
8. **Relevância**: Justificar necessidade de feedback adicional.
    - Exemplo: "Mais pixels? Útil para impressões grandes".

Algumas metas são interdependentes:
- Maior transparência pode aumentar a confiança.
- Persuasão excessiva pode reduzir a confiança.

### **Como explicar?**
- As explicações são um **canal de comunicação** entre o sistema e o usuário.
- Dependem dos objetivos:
    - Transparência?
    - Persuasão?
- Melhoram quando o sistema modela o receptor:
    - Exemplo: Ajustar a explicação com base no conhecimento do usuário.

### **Fatores a considerar**
- **O que explicar?**
    - Previsão? Recomendação?
- **Estado da comunicação**:
    - O que já foi mostrado ao usuário?
- **Objetivos do agente (o sistema)**:
    - Transparência? Persuasão?
- **Modelo do receptor**:
    - Quão familiarizado o usuário está com o domínio?

### **Explicações baseadas em conteúdo**
- Recomendadores baseados em conteúdo usam **atributos de itens**.
    - Exemplo: Recomendação baseada em "importância das features".
- Métodos:
    - Seleção de atributos relevantes (e.g., mínima redundância, máxima relevância).

### **Explicações baseadas em conhecimento**
- Inspiradas em **sistemas especialistas**.
    - **Por quê?** Justifica necessidade de mais informações.
    - **Como?** Mostra vantagens da recomendação.
- Exemplo:
    - Requisitos: preço < $200, adequado para esportes.
    - Resposta: Itens que cumprem requisitos ou violam parcialmente.

### **Explicações colaborativas**
- Diferentes dos anteriores, são **agnósticos ao item**.
    - Baseiam-se em interações de usuários.
    - Exemplo: "Baseado em compras de usuários similares".
#### **Métodos em sistemas colaborativos**
1. **Aquisição de feedback**:
    - Explique quais dados foram usados (e.g., cliques, compras).
2. **Identificação de vizinhos**:
    - Transparência no critério usado para agrupar usuários similares.
3. **Recomendação**:
    - Explicar como foi feita a predição.
    - Exemplo: "Ponderado pela similaridade dos vizinhos".

- Explicações baseadas em avaliações (e.g., histogramas) foram as melhores.
-  Interfaces mal projetadas ou sobrecarregadas foram piores que nenhuma explicação.
 