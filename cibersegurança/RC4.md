É essencial conhecer dois componentes fundamentais do RC4: o **algoritmo de agendamento de chaves (KSA - Key Scheduling Algorithm)** e o **algoritmo de geração pseudoaleatória (PRGA - Pseudo-Random Generation Algorithm)**.

Primeiro, vamos discutir cada um desses componentes:

**1. Algoritmo de Agendamento de Chaves (KSA):** Este algoritmo é responsável por inicializar e permutar a matriz de estado S a partir da chave secreta fornecida. É uma etapa crucial para garantir que a matriz esteja em um estado adequado antes da geração dos números pseudoaleatórios.

**2. Algoritmo de Geração Pseudoaleatória (PRGA):** Após a inicialização feita pelo KSA, o PRGA utiliza a matriz de estado S para gerar uma sequência de bytes pseudoaleatórios. Esses bytes são então combinados com os bytes do texto claro para produzir o texto cifrado, ou invertidos para decifrar o texto cifrado.