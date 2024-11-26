O **WPA2 (Wi-Fi Protected Access 2)** é um protocolo de segurança usado para proteger redes sem fio. Ele foi introduzido em 2004 como uma melhoria ao WPA (Wi-Fi Protected Access) e é amplamente utilizado em redes Wi-Fi domésticas, comerciais e públicas.

### Características principais do WPA2:

1. **Criptografia Avançada (AES):**
    
    - O WPA2 utiliza o **AES (Advanced Encryption Standard)**, que é um padrão de criptografia mais robusto e seguro em comparação ao RC4 usado pelo WPA. O AES oferece proteção de dados de alto nível.
2. **Autenticação com 802.1X:**
    
    - O WPA2 suporta a autenticação baseada no padrão **802.1X**, que permite o uso de servidores RADIUS (Remote Authentication Dial-In User Service) para autenticar usuários e dispositivos em redes empresariais.
3. **Dois Modos de Operação:**
    
    - **Modo Pessoal (WPA2-PSK):** Utiliza uma chave pré-compartilhada (senha) para autenticação, sendo comumente usado em redes domésticas.
    - **Modo Empresarial (WPA2-Enterprise):** Utiliza autenticação com servidor RADIUS, sendo mais adequado para redes corporativas.
4. **Proteção Contra Ataques:**
    
    - WPA2 oferece proteção contra ataques como escutas não autorizadas, garantindo confidencialidade e integridade dos dados transmitidos.

### Limitações do WPA2:

Apesar de ser considerado seguro por muitos anos, o WPA2 tem vulnerabilidades, como o ataque **KRACK (Key Reinstallation Attack)**, que explora falhas no handshake de 4 vias usado para autenticação. Isso motivou o desenvolvimento do **WPA3**, que corrige essas vulnerabilidades e oferece segurança ainda maior.

O **WPA3 (Wi-Fi Protected Access 3)** é a versão mais recente do protocolo de segurança para redes sem fio, introduzido pela Wi-Fi Alliance em 2018 como uma evolução do WPA2. Ele foi projetado para corrigir vulnerabilidades conhecidas do WPA2 (como o ataque **KRACK**) e oferecer segurança aprimorada para redes Wi-Fi em diversos cenários, incluindo domésticos e corporativos.
### Principais Melhorias do WPA3

1. **Criptografia Mais Forte:**
    
    - O WPA3 adota criptografia de 192 bits em modo empresarial, atendendo aos requisitos do **CNSA (Commercial National Security Algorithm)**, tornando-o adequado para ambientes sensíveis.
    - Ele também usa o **Simultaneous Authentication of Equals (SAE)** para substituir o handshake de 4 vias do WPA2, protegendo contra ataques baseados em força bruta.
2. **Proteção Contra Ataques de Força Bruta:**
    - O SAE impede que atacantes realizem ataques offline para adivinhar senhas. Se uma tentativa falhar, é necessário realizar uma nova interação, limitando a eficácia de ataques de força bruta.
3. **Segurança Individual:**
    - O WPA3 oferece criptografia individual para cada conexão em redes abertas (como redes Wi-Fi públicas). Essa funcionalidade, chamada de **OWE (Opportunistic Wireless Encryption)**, criptografa os dados entre o dispositivo e o ponto de acesso, mesmo sem uma senha compartilhada.
4. **Configuração Simplificada:**
    - Com o recurso **Wi-Fi Easy Connect**, o WPA3 facilita a conexão de dispositivos IoT (Internet das Coisas) sem interface de usuário, permitindo emparelhamento seguro via QR Code ou outros métodos.
5. **Proteção Contra Erros do Usuário:**
    - Redes WPA3 são mais resilientes a senhas fracas, garantindo uma segurança básica mesmo quando os usuários escolhem senhas de baixa complexidade.

### Modos de Operação do WPA3

1. **WPA3-Personal:**
    
    - Voltado para redes domésticas e pequenas empresas. Ele usa SAE para autenticação e protege contra ataques offline.
2. **WPA3-Enterprise:**
    
    - Recomendado para redes corporativas. Inclui criptografia de 192 bits e autenticação aprimorada para atender às necessidades de segurança de alto nível.

### Comparação com o WPA2

| Característica                    | WPA2                       | WPA3                                  |
| --------------------------------- | -------------------------- | ------------------------------------- |
| **Autenticação**                  | Handshake de 4 vias        | Simultaneous Authentication of Equals |
| **Resiliência a Senhas**          | Vulnerável a senhas fracas | Proteção contra senhas fracas         |
| **Criptografia em Redes Abertas** | Não há criptografia        | OWE criptografa dados                 |
| **Facilidade de Configuração**    | Tradicional                | Suporte ao Wi-Fi Easy Connect         |

### Limitações do WPA3

Embora o WPA3 ofereça melhorias significativas, a adoção ainda está em andamento e enfrenta os seguintes desafios:

- **Compatibilidade:** Muitos dispositivos antigos não suportam o WPA3 e precisam de atualizações de firmware para funcionar.
- **Custos:** A implementação pode ser mais cara devido a hardware e software mais robustos.
- **Vulnerabilidades iniciais:** Algumas falhas no SAE já foram exploradas, como o ataque **Dragonblood**, mas essas vulnerabilidades foram corrigidas nas implementações mais recentes.

O WPA3 é atualmente a recomendação padrão para redes Wi-Fi, especialmente para quem busca maior segurança em um mundo cada vez mais conectado.