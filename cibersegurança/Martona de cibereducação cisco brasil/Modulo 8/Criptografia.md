# Confidencialidade
Existem duas classes de criptografia usadas para fornecer confidencialidade de dados; assimétrico e simétrico. Essas duas classes diferem na maneira como usam as chaves.
Algoritmos de criptografia simétrica, como Data Encryption Standard (DES), 3DES e Advanced Encryption Standard (AES), baseiam-se na premissa de que cada parte que se comunica conhece a chave pré-compartilhada. A confidencialidade dos dados também pode ser garantida usando algoritmos assimétricos, incluindo Rivest, Shamir e Adleman (RSA) e a infraestrutura de chave pública (PKI).

# Criptografia simétrica
Os algoritmos simétricos usam a mesma chave pré-compartilhada para criptografar e descriptografar dados. Uma chave pré-compartilhada, também chamada de chave secreta, é conhecida pelo remetente e pelo receptor antes que qualquer comunicação criptografada possa ocorrer.

## Exemplo
Hoje, algoritmos de criptografia simétrica são comumente usados com o tráfego VPN. Isso ocorre porque os algoritmos simétricos usam menos recursos da CPU do que os algoritmos de criptografia assimétrica. Isso permite que a criptografia e a descriptografia de dados sejam rápidas ao usar uma VPN. Ao usar algoritmos de criptografia simétrica, como qualquer outro tipo de criptografia, quanto maior a chave, mais tempo levará para alguém descobrir a chave. A maioria das chaves de criptografia tem entre 112 e 256 bits. Para garantir que a criptografia é segura, um comprimento mínimo de chave de 128 bits deve ser usado. Use uma chave mais longa para comunicações mais seguras.

## Cifra de Bloco
**As cifras de bloco** transformam um bloco de texto simples de comprimento fixo em um bloco comum de texto cifrado de 64 ou 128 bits. As cifras de bloco comuns incluem DES com um tamanho de bloco de 64 bits e AES com um tamanho de bloco de 128 bits.

## Cifra de fluxo
**As cifras de fluxo** criptografam o texto simples um byte ou um bit de cada vez. As cifras de fluxo são basicamente uma cifra de bloco com um tamanho de bloco de um byte ou bit. As cifras de fluxo geralmente são mais rápidas do que as cifras de bloco porque os dados são criptografados continuamente. Exemplos de cifras de fluxo incluem RC4 e A5, que é usado para criptografar comunicações de telefone celular GSM.

## Tipos
|Algoritmos de criptografia simétrica|Descrição|
|---|---|
|Data Encryption Standard (DES)|Este é um algoritmo de criptografia simétrica legado. Ele usa um comprimento de chave curto que o torna inseguro para a maioria dos usos atuais.|
|3DES (Triple DES)|O 3DES é o substituto do DES e repete o processo do algoritmo DES três vezes. Deve ser evitado, se possível, uma vez que está programado para ser aposentado em 2023. Se implementado, use durações de chave muito curtas.|
|Advanced Encryption Standard (AES)|AES é um algoritmo de criptografia simétrica popular e recomendado. Ele oferece combinações de chaves de 128, 192 ou 256 bits para criptografar blocos de dados de 128, 192 ou 256 bits.|
|Software-Optimized Encryption Algorithm (SEAL)|O SEAL é um algoritmo de criptografia simétrica alternativo mais rápido ao AES. SEAL é uma cifra de fluxo que usa uma chave de criptografia de 160 bits e tem um impacto menor na CPU em comparação com outros algoritmos baseados em software.|
|Algorithms da série Rivest ciphers (RC)|Este algoritmo foi desenvolvido por Ron Rivest. Diversas variações foram desenvolvidas, mas o RC4 foi o mais prevalente em uso. RC4 é uma cifra de fluxo usada para proteger o tráfego da web. Verificou-se que tem múltiplas vulnerabilidades que o tornaram inseguro. O RC4 não deve ser utilizado.|

# Criptografia Assimétrica
Os algoritmos assimétricos, também chamados algoritmos de chave pública, são projetados para que a chave usada para criptografia seja diferente da chave usada para descriptografia, conforme mostrado na figura. A chave de descriptografia não pode, em uma quantidade razoável de tempo, ser calculada a partir da chave de criptografia e vice-versa.

## Exemplos
Algoritmos assimétricos usam uma chave pública e uma chave privada. Ambas as chaves são capazes do processo de criptografia, mas a chave emparelhada complementar é necessária para descriptografia. O processo também é reversível. Os dados criptografados com a chave pública requerem a chave privada para descriptografar. Algoritmos assimétricos alcançam confidencialidade e autenticidade usando este processo.
Como nenhuma das partes possui um segredo compartilhado, é necessário usar comprimentos de chave muito longos. A criptografia assimétrica pode usar comprimentos de chave entre 512 e 4.096 bits. Comprimentos de chave maiores ou iguais a 2.048 bits podem ser confiáveis, enquanto comprimentos de chave de 1.024 ou menores são considerados insuficientes.
Exemplos de protocolos que usam algoritmos de chave assimétrica incluem:
- **Internet Key Exchange (IKE)** - Este é um componente fundamental das VPNs IPsec.
- **Secure Socket Layer (SSL)** - Agora isso é implementado como TLS (Transport Layer Security) padrão da IETF.
- **Secure Shell (SSH)** - Este protocolo fornece uma conexão segura de acesso remoto a dispositivos de rede.
- **Pretty Good Privacy (PGP)** - Este programa de computador fornece privacidade e autenticação criptográficas. É frequentemente usado para aumentar a segurança das comunicações por email.
Os algoritmos assimétricos são substancialmente mais lentos que os algoritmos simétricos. Seu design é baseado em problemas computacionais, como fatorar números extremamente grandes ou calcular logaritmos discretos de números extremamente grandes.
Por serem lentos, algoritmos assimétricos geralmente são usados em mecanismos criptográficos de baixo volume, como assinaturas digitais e troca de chaves. No entanto, o gerenciamento de chaves de algoritmos assimétricos tende a ser mais simples que os algoritmos simétricos, porque geralmente uma das duas chaves de criptografia ou descriptografia pode ser tomada pública.
## Tipos
|Algoritmo de criptografia assimétrica|comprimento da chave|Descrição|
|---|---|---|
|Diffie-Hellman (DH)|512, 1024, 2048, 3072, 4096|O algoritmo Diffie-Hellman permite que duas partes concordem com uma chave que elas podem usar para criptografar as mensagens que desejam enviar uma para a outra. A segurança desse algoritmo depende da suposição de que é fácil aumentar um número para uma determinada potência, mas difícil calcular qual potência foi usada, dado o número e o resultado.|
|Digital Signature Standard (DSS) e Digital Signature Algorithm (DSA)|512 - 1024|O DSS especifica o DSA como o algoritmo para assinaturas digitais. DSA é um algoritmo de chave pública baseado no esquema de assinatura ElGamal. A velocidade de criação da assinatura é semelhante ao RSA, mas é 10 a 40 vezes mais lenta para verificação.|
|Algorithms de criptografia Rivest, Shamir e Adleman (RSA)|512 até 2048|O RSA é para criptografia de chave pública que se baseia na dificuldade atual de fatorar números muito grandes. É o primeiro algoritmo conhecido por ser adequado para assinatura, bem como criptografia. É amplamente utilizado em protocolos de comércio eletrônico e acredita-se ser seguro, dadas chaves suficientemente longas e o uso de implementações atualizadas.|
|ElGamal|512 - 1024|Um algoritmo de criptografia de chave assimétrica para criptografia de chave pública que se baseia no contrato de chave Diffie-Hellman. Uma desvantagem do sistema ElGamal é que a mensagem criptografada se torna muito grande, aproximadamente o dobro do tamanho da mensagem original e, por esse motivo, é usada apenas para mensagens pequenas, como chaves secretas.|
|Técnicas de curva elíptica|224 ou superior|A criptografia de curva elíptica pode ser usada para adaptar muitos algoritmos criptográficos, como Diffie-Hellman ou ElGamal. A principal vantagem da criptografia de curva elíptica é que as chaves podem ser muito menores.|

# Criptografia Assimétrica - Confidencialidade
Algoritmos assimétricos são usados para fornecer confidencialidade sem pré-compartilhar uma senha. O objetivo de confidencialidade dos algoritmos assimétricos é iniciado quando o processo de criptografia é iniciado com a chave pública.
O processo pode ser resumido usando a fórmula:
**Chave pública (criptografar) + chave privada (descriptografar) = confidencialidade**
Quando a chave pública é usada para criptografar os dados, a chave privada deve ser usada para descriptografar os dados. Apenas um host tem a chave privada; portanto, a confidencialidade é alcançada.
Se a chave privada estiver comprometida, outro par de chaves deve ser gerado para substituir a chave comprometida.

# Criptografia Assimétrica - autenticação
O objetivo de autenticação de algoritmos assimétricos é iniciado quando o processo de criptografia é iniciado com a chave privada.
O processo pode ser resumido usando a fórmula:
**Chave privada (criptografar) + chave pública (descriptografar) = autenticação**
Quando a chave privada é usada para criptografar os dados, a chave pública correspondente deve ser usada para descriptografar os dados. Como apenas um host tem a chave privada, somente esse host poderia ter criptografado a mensagem, fornecendo autenticação do remetente. Normalmente, nenhuma tentativa é feita para preservar o sigilo da chave pública, portanto, qualquer número de hosts pode descriptografar a mensagem. Quando um host descriptografa uma mensagem com êxito usando uma chave pública, é confiável que a chave privada criptografou a mensagem, o que verifica quem é o remetente. Esta é uma forma de autenticação.

# Criptografia assimétrica - integridade
Combinar os dois processos de criptografia assimétrica fornece confidencialidade, autenticação e integridade da mensagem.
O exemplo a seguir será usado para ilustrar esse processo. Neste exemplo, uma mensagem será cifrada usando a chave pública de Bob e um hash cifrado será criptografado usando a chave privada de Alice para fornecer confidencialidade, autenticidade e integridade.

# Diffie - Hellman

Diffie-Hellman (DH) é um algoritmo matemático assimétrico que permite que dois computadores gerem um segredo compartilhado idêntico sem terem se comunicado antes. A nova chave compartilhada nunca é realmente trocada entre o remetente e o destinatário. No entanto, como as duas partes o conhecem, a chave pode ser usada por um algoritmo de criptografia para criptografar o tráfego entre os dois sistemas.

Aqui estão dois exemplos de casos em que DH é comumente usado:

- Os dados são trocados usando uma VPN IPsec
- Dados SSH são trocados

As cores na figura serão usadas em vez de números longos complexos para simplificar o processo de contrato de chave DH. A troca de chaves DH começa com Alice e Bob concordando com uma cor comum arbitrária que não precisa ser mantida em segredo. A cor combinada em nosso exemplo é amarelo.

Em seguida, Alice e Bob selecionarão uma cor secreta. Alice escolheu vermelho enquanto Bob escolheu azul. Essas cores secretas nunca serão compartilhadas com ninguém. A cor secreta representa a chave privada secreta escolhida de cada parte.

Alice e Bob agora misturam a cor comum compartilhada (amarelo) com suas respectivas cores secretas para produzir uma cor pública. Portanto, Alice vai misturar o amarelo com sua cor vermelha para produzir uma cor pública de laranja. Bob irá misturar o amarelo e o azul para produzir uma cor pública de verde.

Alice envia sua cor pública (laranja) para Bob e Bob envia sua cor pública (verde) para Alice.

Alice e Bob misturam a cor que receberam com a sua própria cor secreta original (vermelho para Alice e azul para Bob). O resultado é uma mistura final de cor marrom que é idêntica à mistura de cor final do parceiro. A cor marrom representa a chave secreta compartilhada resultante entre Bob e Alice.

A segurança do DH se baseia-se no fato de que ele usa números muito grandes em seus cálculos. Por exemplo, um número DH 1024 bits é aproximadamente igual a um número decimal de 309 dígitos. Considerando que um bilhão é 10 dígitos decimais (1.000.000.000), pode-se facilmente imaginar a complexidade de trabalhar não com um, mas com vários números decimais de 309 dígitos.

Diffie-Hellman usa diferentes grupos DH para determinar a força da chave que é usada no processo de acordo de chave. Os números de grupo mais altos são mais seguros, mas exigem tempo adicional para calcular a chave. O seguinte identifica os grupos DH suportados pelo Cisco IOS Software e seu valor de número primo associado:

- Grupo DH 1:768 bits
- Grupo DH 2:1024 bits
- Grupo DH 5:1536 bits
- Grupo DH 14:2048 bits
- Grupo DH 15:3072 bits
- Grupo DH 16:4096 bits
Infelizmente, os sistemas de chave assimétrica são extremamente lentos para qualquer tipo de criptografia em massa. É por isso que é comum criptografar a maior parte do tráfego usando um algoritmo simétrico, como 3DES ou AES, e usar o algoritmo DH para criar chaves que serão usadas pelo algoritmo de criptografia.

# Ofuscação de dados
A tecnologia de mascaramento de dados protege dados, substituindo as informações confidenciais por uma versão pública. A versão não confidencial parece e atua como o original para que um processo organizacional possa usar dados não confidenciais sem nenhuma mudança necessária para as aplicações de suporte ou instalações de armazenamento de dados.
No caso de uso mais comum, o mascaramento limita a propagação de dados sensíveis dentro de sistemas de TI, ao distribuir conjuntos de dados substitutos para teste e análise. As informações podem ser mascaradas dinamicamente, se o sistema ou aplicativo determinar que uma solicitação de informações confidenciais feita pelo usuário é arriscada.
O mascaramento de dados pode substituir os dados sensíveis em ambientes não relativos à produção, para proteger as informações principais. Várias técnicas de mascaramento de dados podem ser usadas.
Todos os métodos abaixo garantem que os dados permaneçam significativos, mas sejam alterados o suficiente para protegê-los.
- **A substituição** troca os dados por valores que parecem autênticos para tornar os registros de dados anônimos.
- **O embaralhamento** origina um conjunto de substituição da mesma coluna de dados que um usuário deseja mascarar. Esta técnica funciona bem para informações financeiras em um banco de dados de teste, por exemplo.
- A **anulação** aplica um valor nulo a um campo específico, que impede totalmente a visibilidade dos dados.

# Esteganografia
A estenografia esconde dados (a mensagem) em outro arquivo, como um gráfico, áudio ou outro arquivo de texto.

A vantagem da estenografia em relação à criptografia é que a mensagem secreta não atrai atenção especial. Ao visualizar o arquivo de forma eletrônica ou impressa, ninguém saberá que uma imagem, na realidade, contém uma mensagem secreta.

Existem vários componentes envolvidos na ocultação de dados. Primeiro, existem os dados integrados que compõem a mensagem secreta. O texto de capa (ou imagem de capa ou áudio de capa) oculta os dados integrados, produzindo o estego-texto (ou estego-imagem ou estego-áudio). Uma estego-chave (stego-key) controla o processo de ocultação.

## Técnicas de estenografia
A abordagem usada para integrar dados em uma imagem de capa é o uso de Bits Menos Significativos (LSB). Esse método usa os bits de cada pixel na imagem.
- Um pixel é a unidade básica de cor programável em uma imagem de computador.
- A cor específica de um pixel é uma mistura de três cores - vermelho, verde e azul (RGB).
- Três bytes de dados especificam a cor de um pixel (um byte para cada cor). Um sistema de cores de 24 bits usa todos os três bytes.
- O LSB usa um pouco de cada um dos componentes das cores vermelho, verde e azul. Cada pixel pode armazenar 3 bits.
A figura mostra três pixels de uma imagem colorida de 24 bits. Uma das letras na mensagem secreta é a letra T e a inserção do caractere T muda somente dois bits da cor. O olho humano não consegue reconhecer as alterações efetuadas nos bits menos significativos.
Em média, no máximo, metade dos bits de uma imagem precisará ser alterada para ocultar uma mensagem secreta eficazmente.

## estenografia social
A estenografia social oculta informações de visão simples, criando uma mensagem que pode ser lida de certa forma pela pessoa que receber a mensagem.
As outras pessoas que visualizarem a mensagem de modo normal não a verão. Os adolescentes nas redes sociais usam essa tática para se comunicar com seus amigos mais próximos, evitando que as outras pessoas, como seus pais, percebam o que a mensagem realmente significa. Por exemplo, a frase "ir ao cinema" pode significar "ir à praia".
As pessoas que vivem em países que censuram a mídia também usam a estenografia social para enviar mensagens, digitando as palavras incorretamente de propósito ou fazendo referências imprecisas. Na verdade, eles se comunicam com diferentes públicos simultaneamente, enviando duas mensagens diferentes: a mensagem aparente e a mensagem secreta.

## Detecção
A esteganoanálise é a descoberta de que existem informações ocultas. O objetivo da esteganoanálise é descobrir as informações ocultas.
Os padrões da estego-imagem levantam suspeita. Por exemplo, um disco pode ter áreas reservadas ainda não utilizadas, que são reservadas porque ocultam informações. As utilidades de análise do disco podem relatar informações ocultas em clusters não utilizados de dispositivos de armazenamento. Os filtros podem capturar pacotes de dados que contêm informações ocultas nos cabeçalhos dos pacotes. Esses dois métodos usam usando assinaturas de estenografia.
Ao comparar uma imagem original à estego-imagem, um analista pode buscar padrões de repetição visual.

# Comunicações seguras
As organizações devem fornecer suporte para proteger os dados à medida que eles viajam pelos links. Isso pode incluir tráfego interno, mas é mais importante proteger os dados que viajam para fora da organização para as filiais, locais de trabalho remoto, e parceiros.
Estes são os quatro elementos das comunicações seguras:
- **Integridade de dados** - Garante que a mensagem não foi alterada. Quaisquer alterações nos dados em trânsito serão detectadas. A integridade é garantida pela implementação de um dos algoritmos Secure Hash (SHA-2 ou SHA-3). O algoritmo de resumo de mensagens MD5 ainda está amplamente em uso, no entanto, é inerentemente inseguro e cria vulnerabilidades em uma rede. O uso de MD5 deve ser evitado.
- **Autenticação de origem** - Garante que a mensagem não é uma falsificação e realmente vem de quem é declarada. Muitas redes modernas garantem autenticação com algoritmos como código de autenticação de mensagem baseado em hash (HMAC).
- **Confidencialidade dos dados** - Garante que apenas usuários autorizados possam ler a mensagem. Se a mensagem for interceptada, ela não poderá ser decifrada dentro de um razoável período de tempo. A confidencialidade dos dados é implementada usando algoritmos de criptografia simétrica e assimétrica.
- **Não Repúdio de Dados** - Garante que o remetente não pode repudiar ou refutar a validade de uma mensagem enviada. O não repúdio depende do fato de que apenas o remetente possui as características ou a assinatura exclusivas de como essa mensagem é tratada.
A criptografia pode ser usada em praticamente qualquer lugar em que haja comunicação de dados. De fato, a tendência é que toda comunicação seja criptografada.

# Funções criptográficas de hash
Hashes são usados para verificar e garantir a integridade dos dados. O hash é baseado em uma função matemática unilateral que é relativamente fácil de calcular, mas significativamente mais difícil de reverter. A moagem de café é uma boa analogia de função unidirecional. É fácil moer grãos de café, mas é quase impossível unir novamente todos os pedaços para reconstruir os grãos originais. A função de hash criptográfico também pode ser usada para verificar a autenticação.
Com funções hash, é computacionalmente inviável que dois conjuntos diferentes de dados apresentem a mesma saída hash. Cada vez que os dados são modificados ou alterados, o valor de hash também muda. Por isso, muitas vezes os valores criptográficos de hash são chamados de impressões digitais. Eles podem ser usados para detectar arquivos de dados duplicados, alterações de versão de arquivo e aplicativos semelhantes. Esses valores são usados para proteger contra uma alteração acidental ou intencional dos dados ou corrupção acidental dos dados.
A função hash criptográfico é aplicada em muitas situações diferentes para autenticação de entidade, integridade de dados e fins de autenticidade de dados.

# Operação de hash criptográfico
Matematicamente, a equação **_h = H (x)_** é usada para explicar como um algoritmo de hash opera. Como mostrado na figura, uma função hash H leva uma entrada x e retorna um valor hash string de tamanho fixo h.
- A entrada pode ser de qualquer comprimento.
- A saída tem um comprimento fixo.
- H(x) é relativamente fácil de calcular para qualquer x.
- H (x) é um caminho e não reversível.
- H(x) é livre de colisões, o que significa que dois valores de entrada diferentes resultarão em valores de hash diferentes.

Se uma função hash é difícil de inverter, ela é considerada um hash unidirecional. Difícil de inverter significa que, dado um valor de hash de _h, é computacionalmente inviável encontrar uma entrada para x tal que_ _H=h (x)._

# MD5 e SHA
As funções de hash são usadas para garantir a integridade de uma mensagem. Eles garantem que os dados não foram alterados acidentalmente ou intencionalmente. Na figura, o remetente está enviando uma transferência de dinheiro de US $ 100 para Alex. O remetente deseja garantir que a mensagem não seja alterada acidentalmente no caminho para o destinatário. Alterações deliberadas que são feitas por um ator ameaça ainda são possíveis.
Existem quatro funções hash bem conhecidas:
- **MD5 com digest de 128 bits** - Desenvolvido por Ron Rivest e usado em uma variedade de aplicações de internet, MD5 é uma função unidirecional que produz uma mensagem hash de 128 bits. MD5 é considerado um algoritmo legado e deve ser evitado e usado apenas quando não houver alternativas melhores disponíveis. Recomenda- se que SHA-2 ou SHA-3 sejam usados em vez disso.
- **SHA-1 -** Desenvolvido pela Agência de Segurança Nacional dos EUA (NSA) em 1995. É muito semelhante às funções hash MD5. Existem várias versões. O SHA-1 cria uma mensagem de 160 bits e é um pouco mais lento que o MD5. O SHA-1 possui falhas conhecidas e é um algoritmo antigo.
- **SHA-2 –** Desenvolvido pela NSA. Inclui SHA-224 (224 bits), SHA-256 (256 bits), SHA-384 (384 bits) e SHA-512 (512 bits). Se você estiver usando SHA-2, então os algoritmos SHA-256, SHA-384 e SHA-512 devem ser usados sempre que possível.
- **SHA-3**- SHA-3 é o mais novo algoritmo de hash e foi introduzido pelo NIST como uma alternativa e eventual substituição para a família SHA-2 de algoritmos de hash. SHA-3 inclui SHA3-224 (224 bits), SHA3-256 (256 bits), SHA3-384 (384 bits) e SHA3-512 (512 bits). A família SHA-3 são algoritmos de última geração e devem ser usados sempre que possível.
Embora o hashing possa ser usado para detectar alterações acidentais, ele não pode ser usado para proteger contra alterações deliberadas feitas por um agente de ameaça. Não há informações de identificação única do remetente no procedimento de hash. Isso significa que qualquer pessoa pode processar um hash para quaisquer dados, desde que tenha a função hash correta.
Por exemplo, quando a mensagem atravessa a rede, um invasor em potencial pode interceptar a mensagem, alterá-la, recalcular o hash e anexá-lo à mensagem. O dispositivo receptor só validará contra o hash que estiver anexado.
Portanto, hash é vulnerável a ataques man in the middle e não oferece segurança aos dados transmitidos. Para fornecer autenticação de integridade e origem, é necessário algo mais.

# Autenticação de Origem
Para adicionar autenticação de origem e garantia de integridade, use um código de autenticação de mensagem hash com chave (HMAC). HMACs usam uma chave secreta adicional como entrada à função hash.
**Observação:** Outros métodos MAC (Message Authentication Code) também são usados. No entanto, o HMAC é usado em muitos sistemas, incluindo SSL, IPsec e SSH.
## Algoritmo de hash HMAC
Conforme mostrado na figura, um HMAC é calculado usando qualquer algoritmo criptográfico que combina uma função hash criptográfica com uma chave secreta. As funções de hash são a base do mecanismo de proteção dos HMACs.
Somente o remetente e o destinatário têm conhecimento da chave secreta e agora a saída da função hash depende dos dados de entrada e da chave secreta. Apenas as partes que têm acesso a essa chave secreta podem calcular o digest de uma função HMAC. Isso derrota os ataques man-in-the-middle e fornece autenticação da origem dos dados.
Se duas partes compartilharem uma chave secreta e usarem as funções HMAC para autenticação, uma mensagem HMAC adequadamente construída, a parte recebeu indica que a outra parte foi a originadora da mensagem. Isso ocorre porque a outra parte possui a chave secreta.
## Criação do valor de HMAC
Conforme mostrado na figura, o dispositivo de envio insere dados (como o pagamento de Terry Smith de US $ 100 e a chave secreta) no algoritmo de hash e calcula o HMAC Digest de comprimento fixo. Esse Digest autenticado é anexado à mensagem e enviado ao destinatário.
## Verificação do valor HMAC
Na figura, o dispositivo receptor remove o Digest da mensagem e usa a mensagem de texto sem formatação com sua chave secreta como entrada na mesma função de hash. Se o Digest calculado pelo dispositivo receptor for igual ao resumo enviado, a mensagem não foi alterada. Adicionalmente, a origem da mensagem é autenticada porque apenas o remetente possui uma cópia da chave secreta compartilhada. A função HMAC garantiu a autenticidade da mensagem.
## Cisco Router HMAC
A figura mostra como os HMACs são usados pelos roteadores Cisco configurados para usar a autenticação de roteamento Open Shortest Path First (OSPF).
R1 está enviando uma atualização de estado do link (LSU) referente a uma rota para a rede 10.2.0.0/16:
1. R1 calcula o valor do hash usando a mensagem LSU e a chave secreta.
2. O valor do hash resultante é enviado com o LSU para o R2.
3. R2 calcula o valor do hash usando o LSU e sua chave secreta. R2 aceita a atualização se os valores de hash corresponderem. Se eles não corresponderem, o R2 descartará a atualização.
# Arquivos de hash e meios de comunicação digital
A integridade assegura que os dados e informações estejam completos e inalterados no momento da aquisição. É importante saber quando um usuário baixa um arquivo da Internet ou um avaliador de computação forense está procurando evidências nos meios de comunicação digital.
Para verificar a integridade de todas as imagens IOS, a Cisco oferece checksums MD5 e SHA no site de download de software da Cisco. O usuário pode fazer uma comparação entre esse MD5 digest e o MD5 digest de uma imagem do IOS instalada em um dispositivo, como mostrado na figura. Agora o usuário pode ter certeza de que ninguém violou ou modificou o arquivo de imagem do IOS.
O campo de computação forense digital usa o hash para verificar todas as mídias digitais que contêm arquivos. Por exemplo, o avaliador cria um hash e uma cópia de bit a bit da mídia que contém os arquivos, para produzir um clone digital. O avaliador compara o hash da mídia original com a cópia. Se os dois valores forem compatíveis, as cópias são idênticas. O fato de que um conjunto de bits é idêntico ao conjunto original de bits estabelece **invariabilidade**. A invariabilidade ajuda a responder várias perguntas:
- O avaliador tem os arquivos que ele esperava?
- Os dados foram corrompidos ou alterados?
- O avaliador pode comprovar que os arquivos não estão corrompidos?
Agora o perito em computação forense pode avaliar as evidências digitais da cópia, enquanto deixa o original intacto e inalterado.

# Senhas de hash
Os algoritmos hash transformam qualquer quantidade de dados em um hash digital ou impressão digital de tamanho fixo. Ninguém pode reverter um hash digital para descobrir a entrada original. Se a entrada mudar completamente, o resultado será um hash diferente.
Isso funciona para proteger as senhas. Um sistema precisa armazenar uma senha de modo a protegê-la, mas que ainda possa verificar se a senha do usuário está correta.

# Como decifrar hashes
Para decifrar um hash, um invasor deve adivinhar a senha. O ataque de dicionário e o ataque de força bruta são os dois principais ataques usados para adivinhar senhas.
- **Ataque de dicionário:** Arquivo contendo frases e palavras comuns. O atacante converte em hash e compara com a senha.
- **Ataque força bruta:** Tenta todas as formas de determinado tamanho. É muito lento.
# Salteando
O salting torna o hash de senhas mais seguro.
Se dois usuários têm a mesma senha, eles também terão os mesmos hashes de senha. Um SALT, que é uma cadeia de caracteres aleatória, é uma entrada adicional à senha antes do hash.
Isso cria um resultado de hash diferente para as duas senhas, conforme mostrado na figura. Um banco de dados armazena o hash e o SALT. Na figura, a mesma senha gera um hash diferente porque o salt de cada caso é diferente. O salt não precisa ser confidencial porque é um número aleatório.

# Implementação de salting
Um Gerador Numérico Pseudo Randômico de Criptografia Segura "Cryptographically Secure Pseudo-Random Number Generator" (CSPRNG) é a melhor opção para gerar o salt.
CSPRNGs geram um número aleatório que tem um alto nível de aleatoriedade e é completamente imprevisível, portanto, é criptograficamente confiável.
As recomendações a seguir ajudarão a garantir a implementação bem-sucedida da salt:
- O salt deve ser exclusivo para cada senha de usuário.
- Nunca reutilize um salt.
- O tamanho do sal deve corresponder ao tamanho da saída da função hash.
- Sempre execute o hash no servidor em um aplicativo da Web.
O uso de uma **técnica chamada alongamento (key stretching)** de chave também ajudará a proteger contra ataques. O alongamento de chaves faz com que as tentativas de descobrir senhas trabalhem muito lentamente. Isso impede o hardware de ponta que pode calcular bilhões de hashes por segundo menos eficazes.
## Armazenar uma senha
- Use CSPRNG para gerar um salt longo e aleatório.
- Adicione salt no começo da senha.
- Execute o hash SHA-256, uma função hash criptográfica padrão.
- Salve o salt e o hash como parte do registro do banco de dados do usuário.
## Para validar uma senha
- Recupere o salt e hash de um usuário do banco de dados.
- Adicione salt à senha e faça o hash com a mesma função hash.
- Compare o hash da senha em questão ao armazenado no banco de dados.
- Se os hashes não corresponderem, a senha está incorreta.
# Como evitar ataques
- **Tabelas de pesquisa:** Uma tabela de pesquisa armazena os hashes de senhas pré-calculados em um dicionário de senha, juntamente com a senha correspondente. Uma tabela de pesquisa é uma estrutura de dados que processa centenas de pesquisas de hash por segundo.
- **Tabelas de pesquisa reversa:** Esse ataque permite que o criminoso virtual lance um ataque de dicionário ou um ataque de força bruta em vários hashes, sem a tabela de pesquisa pré-calculada. O criminoso virtual cria uma tabela de pesquisa que traça cada hash de senha a partir do banco de dados da conta violada para uma lista de usuários. O criminoso virtual executa um hash para cada palpite de senha e usa a tabela de pesquisa para obter uma lista de usuários cuja senha é compatível com o palpite do criminoso virtual, como mostrado na figura. O ataque funciona perfeitamente, pois muitos usuários têm a mesma senha.
- **Rainbow tables:** As rainbow tables sacrificam a velocidade de quebra de senha para diminuir o tamanho das tabelas de pesquisa. Uma tabela menor significa que a tabela pode armazenar as soluções para mais hashes na mesma quantidade de espaço.

# Uso de assinaturas digitais
As assinaturas digitais são uma técnica matemática usada para fornecer autenticidade, integridade e não repúdio. As assinaturas digitais têm propriedades específicas que permitem autenticação de entidade e integridade de dados. Além disso, as assinaturas digitais fornecem não repúdio da transação. Em outras palavras, a assinatura digital serve como prova legal de que o intercâmbio de dados ocorreu. As assinaturas digitais usam criptografia assimétrica.
- Autenticidade: A assinatura não pode ser falsificada e fornece prova de que o signatário, e ninguém mais, assinou o documento.
- Inalterável: Após assinar um documento, ele não pode ser alterado.
- Não reutilizável: A assinatura do documento não pode ser transferida para outro documento.
- Não repudiado: O documento assinado é considerado o mesmo que um documento físico. A assinatura é a prova de que o documento foi assinado pela pessoa real.
As assinaturas digitais são comumente usadas nas duas situações a seguir:
1. **Assinatura de código -** Isso é usado para fins de integridade de dados e autenticação. A assinatura de código é usada para verificar a integridade dos arquivos executáveis baixados do site de um fornecedor. Ela também usa certificados digitais assinados para autenticar e verificar a identidade do site que é a origem dos arquivos.
2. **Certificados digitais -** São semelhantes a um cartão de identificação virtual e usados para autenticar a identidade do sistema com o site de um fornecedor e estabelecer uma conexão criptografada para trocar dados confidenciais.
Existem três algoritmos DSS (Digital Signature Standard) que são usados para gerar e verificar assinaturas digitais:
- DSA algoritmo de assinatura digital: DSA é o padrão original para gerar pares de chaves públicas e privadas e para gerar e verificar assinaturas digitais.
- Algoritmo Rivest-Shamir Adleman: RSA é um algoritmo assimétrico comumente usado para gerar e verificar assinaturas digitais.
- Algoritmo de Assinatura Digital de Curvas Elípticas (ECDSA): ECDSA é uma variante mais recente de DSA e fornece autenticação de assinatura digital e não repúdio com os benefícios adicionais de eficiência computacional, tamanhos de assinatura pequenos e largura de banda mínima.
Na década de 1990, a RSE Security Inc. começou a publicar padrões de criptografia de chave pública (PKCS). Havia 15 PKCS, embora 1 tenha sido retirado a partir do momento em que esta escrita foi escrita. A RSE publicou estes padrões porque possuíam as patentes dos padrões e desejavam promovê-los. Os PKCS não são padrões do setor, mas são bem reconhecidos no setor de segurança e recentemente começaram a se tornar relevantes para organizações de padrões como o grupo de trabalho IETF e PKIX.

# Assinaturas digitais para assinatura de código
As assinaturas digitais são comumente usadas para garantir a autenticidade e integridade do código de software. Os arquivos executáveis são empacotados em um envelope assinado digitalmente, o que permite ao usuário final verificar a assinatura antes de instalar o software.
Assinar digitalmente o código fornece várias garantias sobre o código:
- O código é autêntico e é realmente originado pela editora.
- O código não foi modificado desde que saiu do editor do software.
- A editora publicou inegavelmente o código. Isso fornece não repúdio do ato de publicação.
A Publicação 140-3 do FIPS (Federal Information Processing Standard) do Governo dos EUA especifica que o software disponível para download na internet deve ser assinado e verificado digitalmente. O objetivo do software assinado digitalmente é garantir que o software não foi adulterado e que ele foi originado da fonte confiável, conforme reivindicado. As assinaturas digitais servem como verificação de que o código não foi adulterado por agentes da ameaça e o código malicioso não foi inserido no arquivo por terceiros.

# Assinaturas digitais para certificados digitais
Um certificado digital é equivalente a um passaporte eletrônico. Ele permite que usuários, hosts e organizações troquem informações com segurança pela Internet. Especificamente, um certificado digital é usado para autenticar e verificar se um usuário que está enviando uma mensagem é quem afirma ser. Os certificados digitais também podem ser usados para fornecer confidencialidade ao receptor com os meios de criptografar uma resposta.
Os certificados digitais são semelhantes aos certificados físicos. Por exemplo, o certificado Cisco Certified Network Associate Security (CCNA-S) em papel na figura identifica para quem o certificado foi emitido, quem autorizou o certificado e por quanto tempo o certificado é válido. Os certificados digitais também fornecem informações semelhantes.
O certificado digital verifica de forma independente uma identidade. Assinaturas digitais são usadas para verificar se um artefato, como um arquivo ou mensagem, é enviado pelo indivíduo verificado. Em outras palavras, um certificado verifica a identidade, uma assinatura verifica se algo vem dessa identidade.
Esse cenário ajudará você a entender como uma assinatura digital é usada. Bob está confirmando um pedido com Alice. Alice está encomendando do site do Bob. Alice se conectou com o site de Bob, e depois que o certificado foi verificado, o certificado de Bob é armazenado no site de Alice. O certificado contém a chave pública de Bob. A chave pública é usada para verificar a assinatura digital do Bob.
Bob confirma a ordem e seu computador cria um hash da confirmação. O computador criptografa o hash com a chave privada do Bob. O hash criptografado, que é a assinatura digital, é anexado ao documento. A confirmação do pedido é então enviada para Alice através da internet.
1. O dispositivo receptor de Alice aceita a confirmação do pedido com a assinatura digital e obtém a chave pública de Bob.
2. O computador de Alice descodifica a assinatura usando a chave pública de Bob. Esta etapa revela o valor de hash assumido do dispositivo de envio.
3. O computador de Alice cria um hash do documento recebido, sem sua assinatura, e compara esse hash com o hash de assinatura descriptografado. Se os hashes corresponderem, o documento é autêntico. Isso significa que a confirmação foi enviada por Bob e que ela não mudou desde que foi assinada.

# Gerenciamento de chave Pública
O tráfego da Internet consiste no tráfego entre duas partes. Ao estabelecer uma conexão assimétrica entre dois hosts, os hosts trocarão suas informações de chave pública.
Um certificado SSL é um certificado digital que confirma a identidade de um domínio de site. Para implementar SSL em seu site, você compra um certificado SSL para seu domínio de um provedor de Certificado SSL. O empresa terceirizada de confiança faz uma investigação aprofundada antes da emissão das credenciais. Após essa investigação aprofundada, o terceiro emite credenciais (ou seja, certificado digital) que são difíceis de falsificar. Desse ponto em diante, todos os indivíduos que confiam no terceiro simplesmente aceitam as credenciais que o terceiro emite. Quando os computadores tentam se conectar a um site via HTTPS, o navegador verifica o certificado de segurança do site e verifica se ele é válido e originado com uma autoridade de certificação confiável. Isso valida que a identificação do site é verdadeira. O certificado é salvo localmente pelo navegador da Web e, em seguida, é usado em transações subsequentes. A chave pública do site está incluída no certificado e é usada para verificar futuras comunicações entre o site e o cliente.
Esses terceiros confiáveis fornecem serviços semelhantes aos escritórios de licenciamento governamentais.
A Infraestrutura de Chave Pública (PKI) consiste em especificações, sistemas e ferramentas que são usados para criar, gerenciar, distribuir, usar, armazenar e revogar certificados digitais. A autoridade de certificação (CA) é uma organização que cria certificados digitais vinculando uma chave pública a uma identificação confirmada, como um site ou indivíduo. O PKI é um sistema complexo que é projetado para proteger identidades digitais contra hackers até mesmo os atores de ameaças mais sofisticados ou estados-nação.
Alguns exemplos de Autoridades de Certificação são IDentrust, DigiCert, Sectigo, GlobalSign e GoDaddy. Essas CAs cobram por seus serviços. Let's Encrypt é uma CA sem fins lucrativos que oferece certificados gratuitamente