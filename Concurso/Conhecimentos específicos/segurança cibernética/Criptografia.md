## Hash Function
São diferentes de criptografar, não tem chave e são feitas para serem quase impossíveis de ir do output de volta para o input. Um algoritmo de hash vai ser relativamente rápido para computar. O output de uma função hash são bytes puros, que estão codificados. Codificações comuns são base64 ou hexadecimal. Decodificar não vai trazer nada útil.
Hash é usado frequentemente em ciberssegurança. Geralmente usado para verificar senhas e a integridade dos dados. Hash possui tamanho fixo independente da quantidade de dados.

**Colisões** ocorrem quando dois dados diferentes produzem o mesmo valor de _hash_. Isso é problemático porque, se um invasor conseguir criar um arquivo diferente que resulte no mesmo valor de _hash_ que o arquivo original, ele pode passar pelo processo de verificação de integridade como se fosse o arquivo legítimo, comprometendo a segurança.

O salt é uma sequência aleatória de caracteres única para cada senha. Ele é combinado com a senha antes de aplicar o hash, garantindo que senhas iguais resultem em hashes diferentes.

Conforme a premissa do hashing uniforme simples, cada chave tem igual probabilidade de passar para qualquer das m posições por uma operação de hash, independentemente da posição que qualquer outra chave tenha ocupado após o hash. No método de divisão para criar funções hash, é mapeada uma chave k para uma de m posições, tomando-se o resto da divisão de k por m, de modo que a função hash é h(k) = k mod m.

## Criptografia de curva elíptica
A **criptografia de curva elíptica (ECC, Elliptic Curve Cryptography)** é um tipo de criptografia assimétrica que utiliza as propriedades matemáticas das curvas elípticas para oferecer segurança equivalente a outros métodos, como RSA, mas com **chaves muito menores**. Isso a torna mais eficiente em termos de armazenamento, processamento e transmissão de dados.
Em criptografia de curva elíptica, para ser considerada uma curva elíptica, a equação y2 = x3 + ax + b deve ser satisfeita.

## Criptografia de chave pública (assimétrica)
Criptografia de chave pública (ou criptografia assimétrica) não é a técnica mais eficiente e rápida quando comparada à criptografia de chave privada (simétrica) para o armazenamento de grandes quantidades de dados. A criptografia assimétrica utiliza um par de chaves (pública e privada) e, embora ofereça maior segurança em algumas situações, é significativamente mais lenta e consome mais recursos computacionais.É neste contexto que entram o **RSA (Rivest-Shamir-Adleman)** e o **ECC (Elliptic Curve Cryptography)**.

### RSA
O algoritmo RSA utiliza a função matemática Totiente de Euler para gerar chaves criptográficas assimétricas públicas e privadas.


## Criptografia simétrica
Em criptografia simétrica, é utilizado um único **chave** para tanto _criptografar_ quanto _descriptografar_ a informação. Esse tipo de criptografia é amplamente utilizado devido à sua eficiência em termos de velocidade, especialmente em grandes volumes de dados.

Dentro da criptografia simétrica, existem dois tipos principais de algoritmos: **cifras de fluxo** e **cifras de bloco**.

  
- **Cifras de fluxo**: Operam sobre os dados de forma contínua, ou seja, bit a bit, ou byte a byte. Elas são geralmente mais rápidas e adequadas para transmissões de dados em tempo real.
  
- **Cifras de bloco**: Operam em blocos de dados fixos (por exemplo, 64 ou 128 bits). Cada bloco é criptografado de forma independente, o que pode trazer um nível adicional de segurança.
  

Ambos os tipos de cifras são válidos para a criptografia simétrica, e a escolha entre uma cifra de fluxo ou uma cifra de bloco depende das características internas do algoritmo e das necessidades específicas da aplicação.

Exemplos de algoritmos simétricos incluem o AES (Advanced Encryption Standard) e o DES (Data Encryption Standard).

### AES
O **AES (Advanced Encryption Standard)** é um dos algoritmos de criptografia mais seguros e amplamente utilizados no mundo.
#### **Características principais do AES:**

1. **Tipo de criptografia:**
    - Simétrica, ou seja, a mesma chave é usada tanto para criptografar quanto para descriptografar os dados.
2. **Blocos de dados:**
    - Opera em blocos de 128 bits (16 bytes).
3. **Tamanhos de chave:**
    - AES permite chaves de:
        - **128 bits**
        - **192 bits**
        - **256 bits** (quanto maior a chave, mais segura é a criptografia, mas também mais lento é o processamento).
4. **Aplicações:**
    - Segurança de redes Wi-Fi (WPA2/WPA3).
    - Transações financeiras e bancárias.
    - Protocolos de comunicação seguros, como TLS e VPNs.
    - Criptografia de discos e armazenamento de dados.

---

#### **Funcionamento do AES:**

O AES é baseado em um **cifra de bloco** chamada Rijndael. O processo de criptografia e descriptografia consiste em várias etapas organizadas em **rodadas**. O número de rodadas depende do tamanho da chave:

- 10 rodadas para chave de 128 bits.
- 12 rodadas para chave de 192 bits.
- 14 rodadas para chave de 256 bits.

#### **Etapas principais em cada rodada:**

1. **SubBytes (Substituição):**
    - Substitui os bytes de entrada usando uma tabela de substituição (S-Box) não-linear, projetada para resistir a criptoanálises.
2. **ShiftRows (Deslocamento):**
    - Realiza um deslocamento cíclico nas linhas da matriz de estado, criando uma mistura de posições.
3. **MixColumns (Mistura):**
    - Multiplica cada coluna da matriz de estado por uma matriz fixa, misturando os dados de forma linear.
4. **AddRoundKey (Adição de Chave):**
    - Combina a matriz de estado com uma subchave derivada da chave principal, utilizando XOR.

A última rodada omite o passo **MixColumns**.

---

#### **Vantagens do AES:**

- **Segurança comprovada:** Amplamente analisado e considerado resistente contra ataques práticos, como força bruta.
- **Desempenho:** Altamente eficiente em hardware e software.
- **Flexibilidade:** Suporta diferentes tamanhos de chave e implementações otimizadas.

#### **Modos de operação do AES:**

O AES é frequentemente usado em combinação com **modos de operação** para processar dados maiores que um único bloco de 128 bits. Exemplos:

- **ECB (Electronic Codebook):** Simples, mas inseguro para dados com padrões repetidos.
- **CBC (Cipher Block Chaining):** Adiciona encadeamento entre blocos, aumentando a segurança.
- **GCM (Galois/Counter Mode):** Combina criptografia com autenticação, ideal para redes seguras.
- **CTR (Counter Mode):** Transforma o AES em uma cifra de fluxo.


### Blowfish
Blowfish é uma cifra simétrica de blocos que utiliza chave com tamanho variável de 32 bits a 448 bits e que foi criada como alternativa gratuita e rápida aos algoritmos criptográficos existentes.

# Políticas
- **SPF (Sender Policy Framework)**: é um sistema que evita que outros domínios, enviem e-mails não autorizados em nome de um domínio. Ele funciona por meio da **validação de endereços IP** autorizados a enviar e-mails em nome de um domínio.
- **DKIM (DomainKeys Identified Mail)**: utiliza **criptografia de chave pública** para adicionar assinaturas digitais aos e-mails. Essas assinaturas permitem verificar matematicamente a autenticidade do remetente.


## Certificado digital
O certificado digital é a identidade eletrônica de uma pessoa ou empresa. Ele funciona como uma carteira de identificação virtual e permite assinar documentos à distância com o mesmo valor jurídico da assinatura feita de próprio punho no papel, mas sem precisar reconhecer firma em cartório.

**Componentes de um Certificado Digital:**
- **Chave Privada:** Utilizada para criptografar dados que atestam a identidade do titular. Apenas o proprietário do certificado tem acesso a essa chave.
- **Chave Pública:** Disponibilizada para quem precisa decodificar as informações criptografadas pela chave privada, confirmando a identidade do titular.

**Emissão e Autoridades Certificadoras:**
No Brasil, os certificados digitais são emitidos por Autoridades Certificadoras (AC) credenciadas pela Infraestrutura de Chaves Públicas Brasileira (ICP-Brasil). Essas entidades são responsáveis por verificar a identidade dos solicitantes e emitir os certificados correspondentes.

## Assinatura digital

A **assinatura digital** é um mecanismo eletrônico que permite a autenticação de documentos digitais, assegurando sua integridade e a identidade do signatário. Ela utiliza técnicas de criptografia avançada para garantir que o documento não seja alterado após a assinatura e que o autor seja devidamente identificado.

**Como Funciona:**
- **Criptografia Assimétrica:** A assinatura digital baseia-se em um par de chaves criptográficas: uma chave privada, conhecida apenas pelo signatário, e uma chave pública, disponível para quem precisa verificar a assinatura. Ao assinar um documento, o signatário utiliza sua chave privada para criar um código único, que é anexado ao documento. Qualquer alteração no documento invalida a assinatura, garantindo sua integridade.
- **Certificado Digital:** Para que a assinatura digital tenha validade jurídica, é necessário um certificado digital emitido por uma Autoridade Certificadora (AC) reconhecida. No Brasil, as ACs são regulamentadas pela Infraestrutura de Chaves Públicas Brasileira (ICP-Brasil).