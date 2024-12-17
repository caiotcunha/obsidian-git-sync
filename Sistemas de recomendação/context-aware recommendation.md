## Tipos de contexto
1. **Físico:** posição, tempo, atividade,clima, luz e temperatura
2. **Social:** Presença e posição de outras pessoas em volta do usuário
3. **Interação:** tipo de mídia e dispositivo
4. **Modal:** estado de mente, objetivos, sentimento, experiencia, cognição

- **Visão Representacional:**
	- Contexto descrito com atributos observáveis e estruturados (tempo, data, local).
	- Exemplo: Domingo → Fim de Semana.
- **Visão Interacional:**
	- Contexto é dinâmico e inferido das interações.
	- Ações do usuário influenciam e modificam o contexto.

## **Implicações da Visão Representacional**

- **Variáveis contextuais:** Precisam ser definidas **a priori**.
    - **Desafio:** Determinar quais contextos são relevantes (**problema de qualificação**).
- **Variáveis estáticas:** Difícil determinar **quando** cada contexto é aplicável.

## Formas
Podemos fazer uma filtragem pelo contexo e depois jogar os dados filtrados no recomendador.

### Pre-filtering via splitting
- Item splitting
	- Preferência por um item pode mudar em contextos diferentes
	- Podemos considerar um item como múltiplos itens, um para cada contexto
- User splitting
	- Preferência por um usuário pode mudar em contextos diferentes
	- Podemos considerar um usuário como múltiplos usuários, um para cada contexto
### **Desafios na Divisão (Splitting)**
- **Critérios de divisão:** Testar se o contexto influencia as notas.
    - Exemplo: Média de notas **em casa** vs. **no cinema**.
    - **Significância estatística:** Verificar se a diferença é relevante.
- **Granularidade do contexto:**
    - Contextos muito específicos podem ser insuficientes para treinamento.
    - Solução: **Generalizar** (exemplo: Sábado → Final de Semana).

### **Pós-filtragem Contextual**
- **Ideia:** Recomendações são geradas sem considerar o contexto, mas são ajustadas **depois**.
- **Exemplo:** Reordenar itens para promover os mais relevantes ao contexto atual (usando tags, anotações, etc.).

### **Modelagem Contextual**

- O contexto é incorporado **diretamente** no modelo de recomendação.
    - Dados: U×I×C×RU \times I \times C \times RU×I×C×R → modelo multidimensional (MD).

### **Fatoração Tensorial (Tensor Factorization)**

- **Extensão da Fatoração Matricial:**
    - Matriz 2D (usuários e itens) é expandida para uma **estrutura multi-dimensional** (tensor) com contexto.
- **Desafio:** O número de parâmetros cresce exponencialmente com o número de fatores contextuais.

### **Modelos Latentes**

- **Premissa:** Interações observadas são explicadas por variáveis contextuais **não observáveis** (latentes).
    - Exemplo: Modelagem de **tópicos** para música baseados em padrões de sequência.

### **Exemplo - Contexto via Tópicos**

- **Aplicação:** Previsão do próximo contexto em um sistema de recomendação de músicas:
    - **Entrada:** Histórico de músicas, sessões passadas.
    - **Modelo:** Extrai tópicos (como "emoção" ou "gênero") para contextualizar a recomendação.