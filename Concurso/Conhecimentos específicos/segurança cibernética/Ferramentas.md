
# Yara
A regra YARA é utilizada para encontrar e classificar amostras de Malware a partir de características que podemos definir através de: binários, hashs, padrões hexadecimais, clean text, base64, entre outros. Depois da criação você terá diversas formas de executar esta regra, seja simplesmente procurando um padrão de texto único ou também criando condições com regras regex para que dê match no que realmente é malicioso. A sintaxe das regras se assemelha à linguagem C.


# JWT
O **JWT** (JSON Web Token) é uma forma compacta e autossuficiente de transmitir informações entre partes como um objeto JSON. Essas informações podem ser verificadas e confiáveis porque são assinadas digitalmente. O JWT é amplamente utilizado em autenticação e autorização.

Dentro do JWT, o **payload** contém as **_claims_**, que são declarações sobre uma entidade (normalmente, o usuário) e dados adicionais. Existem diferentes tipos de claims:
- **_Registered Claims_**: São um conjunto de claims predefinidas que não são obrigatórias, mas recomendadas, para fornecer um conjunto de informações padrão. Exemplos incluem _**iss**_ (emissor), _**exp**_ (expiração) e _**sub**_ (assunto).
- **_Public Claims_**: São claims que podem ser definidas livremente pela aplicação, mas devem ser registradas no IANA JSON Web Token Registry ou ser definidas de forma a evitar colisões de nomes. A questão menciona que _public claims_ são usadas para compartilhar informações entre aplicações, mas isso está incorreto, pois a principal característica dessas claims é que são definidas e compartilhadas publicamente, mas não necessariamente entre diferentes aplicações.
- **_Private Claims_**: São claims customizadas e definidas por aplicações específicas para compartilhar informações privadas. Essas claims não são registradas publicamente e são usadas exclusivamente dentro do contexto particular de uma aplicação.