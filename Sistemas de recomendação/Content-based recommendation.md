### **1.Problemas resolvidos por sistemas de recomendação**
- **Cold-start:** Útil quando não há dados suficientes sobre usuários ou itens.
    - _Novo usuário_: Dificuldade em prever devido à ausência de histórico.
    - _Novo item_: Dificuldade em recomendar devido à falta de avaliações.

### **2.Características do modelo baseado em conteúdo**
- Usa características intrínsecas dos itens para recomendar itens semelhantes ao que o usuário já gostou.
- Exemplos de características:
    - Estruturadas: Título, gênero, ano (para músicas, filmes, etc.).
    - Não estruturadas: Texto, áudio, vídeo, imagens (requere técnicas específicas para extrair similaridade).

### **3.Vantagens**
- Não depende de dados de outros usuários, útil para usuários com gostos únicos.
- Recomendação de itens novos e pouco populares.
- Pode justificar recomendações com base nos atributos do conteúdo.
### **4.Desafios**
- Requer atributos bem estruturados e distribuídos entre os itens.
- Tende a propor "mais do mesmo", dificultando encontrar conexões surpreendentes ou itens complementares.
### **5.Representação do conteúdo**
- Representação matricial (itens como vetores).
    - Cada termo (característica) corresponde a uma dimensão do vetor.
    - Exemplo de vetores: `TF-IDF` para medir a importância de palavras em textos.
- Similaridade calculada usando:
    - _Cosine similarity_: Medida angular entre vetores.
    - _Distância Euclidiana_: Diferença em termos espaciais.
### **6.Representação e similaridade dos usuários**
- Cada usuário é representado como a média ponderada dos vetores dos itens que avaliou.
- As recomendações são feitas ranqueando itens pela similaridade com o vetor do usuário.

### **7.Problemas específicos**
- **Overspecialization:** Os sistemas podem se limitar a sugerir itens muito semelhantes, faltando diversidade.
- **Dependência de palavras-chave:** Nem sempre palavras-chave capturam fatores importantes como estilo, estética ou semântica.


## Rocchio

### inputs
- utility matrix: usuários x itens em que cada célula tem a avaliação do usuário sobre o item
- item termo matrix: termo x itens em que cada célula tem o peso do termo é calculado por algum algoritmo tipo tf-idf
- user-termo matrix: calculada a partir das outras duas
### recomendação
- para recomendar o item -> multiplica a coluna do usuário alvo na user-feature, pela coluna item alvo da matriz de item termo