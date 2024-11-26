## Hash Function
São diferentes de criptografar, não tem chave e são feitas para serem quase impossíveis de ir do output de volta para o input. Um algoritmo de hash vai ser relativamente rápido para computar. O output de uma função hash são bytes puros, que estão codificados. Codificações comuns são base64 ou hexadecimal. Decodificar não vai trazer nada útil.
Hash é usado frequentemente em ciberssegurança. Geralmente usado para verificar senhas e a integridade dos dados.

### Cracking hash
Existem diferentes ferramentas para fazer o crack de um hash. Geralmente usamos GPUs para esse trabalho, pois elas são melhores em alguns cálculos necessários.

### HMACs
É um método para usar uma função hash de criptografia para verificar a autenticidade e integridade de um arquivo.

## MD5
O **MD5 (Message-Digest Algorithm 5)** é uma função de hash criptográfica projetada por Ronald Rivest em 1991. Ele é usado para gerar um resumo (digest) fixo de 128 bits a partir de uma entrada arbitrária. O MD5 foi amplamente utilizado no passado em várias aplicações, como verificação de integridade de arquivos e autenticação de mensagens. No entanto, ele não é mais considerado seguro para aplicações criptográficas.
### **Como o MD5 funciona:**

1. **Entrada:** O algoritmo aceita mensagens de qualquer comprimento.
2. **Padding:** A mensagem é preenchida para que seu comprimento seja congruente a 448 bits (mod 512). É adicionado um único bit "1", seguido de zeros até atingir o comprimento correto. Nos últimos 64 bits, é armazenado o comprimento original da mensagem.
3. **Processamento em blocos:** A mensagem é dividida em blocos de 512 bits, que são processados em 4 etapas principais (rodadas).
4. **Saída:** O resultado final é um hash de 128 bits.
### **Fraquezas do MD5:**

1. **Colisões:**
    
    - Uma colisão ocorre quando duas entradas diferentes produzem o mesmo hash.
    - Em 2004, Xiaoyun Wang e Hongbo Yu demonstraram como encontrar colisões no MD5 de forma prática.
    - Em 2012, ataques práticos foram demonstrados para forjar certificados SSL/TLS usando colisões no MD5.
2. **Ataques de Preimage:**
    
    - Embora ainda seja computacionalmente difícil encontrar uma entrada que corresponda a um hash específico, a segurança do MD5 contra preimages é inferior à de algoritmos mais modernos.
3. **Velocidade:**
    
    - A rapidez do MD5, embora útil para algumas aplicações, também facilita ataques de força bruta.

### **Aplicações legadas:**

Embora o MD5 tenha caído em desuso em aplicações de segurança, ele ainda é usado para:

- **Verificação de integridade:** Confirmar que um arquivo não foi corrompido durante a transferência (mas não garante autenticidade ou resistência a adulterações).
- **Checksums:** Em sistemas onde a segurança criptográfica não é um requisito crítico.


## SHA
**SHA (Secure Hash Algorithm)** é uma família de funções hash criptográficas que geram uma saída (hash) de comprimento fixo a partir de uma entrada de qualquer tamanho. Elas são projetadas para produzir um valor único e representativo (o hash) para um conjunto de dados de forma eficiente e segura, sendo amplamente usadas em segurança de sistemas, como em assinaturas digitais, armazenamento de senhas e verificações de integridade.

A principal característica de um algoritmo SHA é que ele é **determinístico**, ou seja, a mesma entrada sempre gerará a mesma saída, e **não reversível**, o que significa que não é possível, de forma prática, recuperar a entrada original a partir do hash.
### **Principais versões do SHA:**

1. **SHA-1 (Secure Hash Algorithm 1):**
    
    - Produz um hash de 160 bits (20 bytes).
    - Foi amplamente usado no passado em várias aplicações de segurança, como SSL/TLS, assinaturas digitais e verificações de integridade.
    - No entanto, **SHA-1 tem falhas de segurança** e foi considerado vulnerável a colisões (quando duas entradas diferentes produzem o mesmo hash). Devido a essas vulnerabilidades, seu uso tem sido desaconselhado, e muitas organizações migraram para versões mais seguras.
2. **SHA-2 (Secure Hash Algorithm 2):**
    
    - Um conjunto de funções hash que inclui vários algoritmos com saídas de diferentes tamanhos: SHA-224, SHA-256, SHA-384, SHA-512 e suas variantes.
    - A versão mais comum é o **SHA-256**, que produz um hash de 256 bits (32 bytes) e é amplamente utilizado em sistemas modernos devido à sua maior segurança em comparação com o SHA-1.
    - O SHA-2 é mais seguro e eficiente que o SHA-1 e é usado em muitos protocolos de segurança, como TLS/SSL, Bitcoin, certificados digitais, entre outros.
3. **SHA-3 (Secure Hash Algorithm 3):**
    
    - Introduzido em 2015, SHA-3 não é uma continuação do SHA-2, mas sim uma **família independente de funções hash**.
    - SHA-3 foi projetado para ser mais resistente a certos tipos de ataques e melhorar a resistência à colisão.
    - Embora o SHA-2 seja ainda amplamente utilizado, o SHA-3 está sendo adotado em novas implementações de segurança.