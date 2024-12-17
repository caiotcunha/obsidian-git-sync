- **Problema:** Como modelar interações entre usuários e itens?
- **Comparação de Modelos:**
    - **Modelos de Vizinhança:** Espaços distintos para usuários e itens.
    - **Modelos Latentes:** Espaço unificado, onde usuários e itens são representados como vetores de ddd-dimensões.
- **Desafio:** Incorporar **informação adicional**, como características de usuários (idade, gênero) e itens (descrição, imagem).
- **Solução Parcial:** Adaptações "ad hoc" e algoritmos específicos, mas essas soluções são limitadas e custosas.

### **Feature-Based Modeling**
- **Representação:**
    - Usa **vetores de características** com atributos categóricos e numéricos.
    - Exemplo: ID do usuário, ID do item, notas atribuídas.
- **Vantagens:**
    - Modela qualquer número de variáveis.
    - Permite a aplicação de abordagens de aprendizado de máquina.

### **Modelo Linear**

- **Equação Geral:** y=w0+w^t x
    - y: valor previsto (ex.: nota de recomendação).
    - w0​: viés global.
    - w: pesos das características (x).
- **Limitação:** Modelos lineares **não conseguem capturar interações** entre características.

### **Feature Interactions**

- **Problema:** Engenheiros de recursos precisam "cruzar" manualmente as características (feature crosses), o que é:
    - **Custoso:** Muitas combinações possíveis.
    - **Ineficiente:** Processo envolve "arte" e tentativa-e-erro.
- **Exemplo:** Combinar **ID de usuário** com **ID de item** para modelar interações.

### **Polynomial Regression (Interações de Grau 2)**
**Problema:** A quantidade de parâmetros cresce quadraticamente (O(p2)O(p^2)O(p2)).

- **Desafios:**
    - Alto risco de **overfitting**.
    - Não funciona bem com dados esparsos (ex.: interações usuário-item não observadas).

### **Factorization Machines (FMs)**

- **Introdução às Factorization Machines**:
    - Combina a flexibilidade dos **modelos baseados em características** com a eficácia dos **modelos de fatores latentes**.
#### **Vantagens das Factorization Machines**
- **Flexibilidade:**
    - Subsume modelos de fatoração, como **Matrix Factorization** e **Tensor Factorization**.
    - Suporta variáveis categóricas e numéricas.
- **Interações Automáticas:**
    - Detecta interações entre características sem necessidade de definições manuais.
- **Eficiência:**
    - Complexidade linear em relação ao número de características e à dimensão dos vetores (O(pd)).
- **Algoritmos:**
    - **Regressão regularizada L2:**
        - Implementada com **Stochastic Gradient Descent (SGD)** e **Alternating Least Squares (ALS)**.
    - **Ranking Regularizado (Perda Pareada):** Otimizado com SGD.
- **Eficiência:** A previsão de FMs é rápida e escalável para grandes datasets.