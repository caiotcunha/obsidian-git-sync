O **TLS 1.3** (Transport Layer Security 1.3) é a versão mais recente do protocolo TLS, utilizado para fornecer segurança em comunicações na Internet. Ele foi padronizado pela IETF (Internet Engineering Task Force) em 2018, com o objetivo de oferecer maior segurança e eficiência em comparação às versões anteriores (como TLS 1.2).

### **Principais características do TLS 1.3:**

1. **Segurança aprimorada:**
    
    - Remoção de algoritmos criptográficos considerados inseguros, como:
        - RC4
        - SHA-1
        - Algoritmos de chave estática Diffie-Hellman
        - CBC (Cipher Block Chaining)
    - Somente algoritmos robustos permanecem, como AEAD (Authenticated Encryption with Associated Data), incluindo AES-GCM e ChaCha20-Poly1305.
    - Uso obrigatório de Perfect Forward Secrecy (PFS) com curvas elípticas (ECDHE) ou Diffie-Hellman.
2. **Redução da latência:**
    
    - **Handshake simplificado:** Reduz o número de etapas necessárias para estabelecer uma conexão segura.
    - **Zero Round Trip Time (0-RTT):** Permite que conexões repetidas entre o cliente e o servidor reutilizem informações de sessões anteriores, eliminando o tempo de negociação inicial (com riscos mitigados por design).
3. **Privacidade de dados:**
    
    - A criptografia começa mais cedo no handshake, protegendo informações sensíveis, como os identificadores dos certificados trocados durante a negociação.
    - Certos dados, como o SNI (Server Name Indication), podem ser criptografados (em evolução com projetos como Encrypted Client Hello, ou ECH).
4. **Simplificação do protocolo:**
    
    - Remoção de recursos e extensões legados, como renegociação de handshake.
    - Melhorias no design para reduzir ambiguidades que poderiam levar a vulnerabilidades.
5. **Desempenho aprimorado:**
    
    - Melhor integração com redes modernas e maior eficiência ao lidar com conexões móveis e de baixa latência.

---

### **Handshake TLS 1.3:**

No TLS 1.3, o handshake ocorre de forma mais eficiente:

1. O cliente envia um "ClientHello" contendo os algoritmos de criptografia suportados e dados de chave pública.
2. O servidor responde com "ServerHello", seleciona os parâmetros de criptografia e fornece sua chave pública.
3. Após a troca, ambos os lados derivam a chave compartilhada e começam a comunicação criptografada.