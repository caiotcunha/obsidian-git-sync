# ACL
Uma ACL é uma série de comandos do IOS usados para filtrar pacotes com base nas informações encontradas no cabeçalho do pacote. Por padrão, um roteador não tem nenhuma ACLs configurada. Entretanto, quando uma ACL for aplicada a uma interface, o roteador executará a tarefa adicional de avaliar todos os pacotes de rede que passam pela interface para determinar se o pacote pode ser enviado. Uma ACL usa uma lista sequencial de instruções de permissão ou negação, conhecidas como entradas de controle de acesso (ACEs).
Quando o tráfego da rede passa através de uma interface configurada com uma ACL, o roteador compara as informações no pacote com cada ACE, em ordem sequencial, para determinar se o pacote corresponde a uma das ACEs. Esse processo é chamado de filtragem de pacote.
Várias tarefas executadas por roteadores exigem o uso de ACLs para identificar o tráfego como:
- limitam tráfego e aumentam o desempenho da rede
	- Uma política corporativa proíbe o tráfego de vídeo na rede para reduzir a carga da rede.
	- Uma política pode ser aplicada usando ACLs para bloquear o tráfego de vídeo.
- Fornecer controle de fluxo de tráfego
	- Uma política corporativa requer que o tráfego de protocolo de roteamento seja limitado apenas a determinados links.
	- Uma política pode ser implementada usando ACLs para restringir a entrega de atualizações de roteamento apenas para aqueles que vêm de uma fonte conhecida.
- Fornecer um nível básico de segurança para acesso à rede
	- A política corporativa exige que o acesso à rede de Recursos Humanos seja restrito apenas a usuários autorizados.
	- Uma política pode ser aplicada usando ACLs para limitar o acesso a redes especificadas.
- Filtrar o tráfego com base no tipo de tráfego
	- A política corporativa exige que o tráfego de e-mail seja permitido em uma rede, mas que o acesso Telnet seja negado.
	- Uma política pode ser implementada usando ACLs para filtrar tráfego por tipo.
- Screen hosts para permitir ou negar acesso aos serviços de rede
	- A política corporativa exige que o acesso a alguns tipos de arquivos (por exemplo, FTP ou HTTP) se limitasse aos grupos de usuários.
	- Uma política pode ser implementada usando ACLs para filtrar o acesso ao usuário aos serviços.
- Fornecer prioridade a determinadas classes de tráfego de rede
	- O tráfego corporativo especifica que o tráfego de voz seja encaminhado o mais rápido possível para evitar qualquer interrupção.
	- Uma política pode ser implementada usando serviços ACLs e QoS para identificar o tráfego de voz e processá-lo imediatamente

# Filtragem de pacote
A filtragem de pacotes controla o acesso a uma rede analisando os pacotes de entrada e / ou saída e encaminhando-os ou descartando-os com base nos critérios fornecidos. A filtragem de pacotes pode ocorrer na camada 3 ou camada 4 do modelo osi.
Os roteadores Cisco suportam dois tipos de ACLs:
- **ACLs padrão** - As ACLs filtram apenas na Camada 3 usando apenas o endereço IPv4 de origem.
- **ACLs estendidas** - Os ACLs filtram na Camada 3 usando o endereço IPv4 de origem e / ou destino. Eles também podem filtrar na Camada 4 usando TCP, portas UDP e informações de tipo de protocolo opcional para controle mais fino.

# ACLs nomeadas e numeradas

## ACLs numeradas
ACLs número 1 a 99, ou 1300 a 1999 são ACLs padrão, enquanto ACLs número 100 a 199, ou 2000 a 2699 são ACLs estendidas.

## ACLs nomeadas
ACLs nomeadas é o método preferido a ser usado ao configurar ACLs. Especificamente, as ACLs padrão e estendidas podem ser nomeadas para fornecer informações sobre a finalidade da ACL. Por exemplo, nomear uma ACL FTP-FILTER estendida é muito melhor do que ter uma ACL 100 numerada.
O comando **ip access-list** na configuração global é usado para criar uma ACL nomeada
O seguinte resume as regras a seguir para ACLs nomeadas:
- Atribua um nome para identificar o objetivo da ACL.
- Os nomes podem conter caracteres alfanuméricos.
- Os nomes não podem conter espaços ou pontuação.
- Sugerimos que o nome seja escrito em LETRAS MAIÚSCULAS.
- É possível adicionar ou excluir entradas na ACL.

# Operação ACL
As listas de acesso expressam o conjunto de regras que permitem maior controle dos pacotes que chegam às interfaces de entrada, pacotes que são retransmitidos através do roteador e pacotes que saem das interfaces do roteador. As ACLs podem ser configuradas para serem aplicadas ao tráfego de entrada e ao tráfego de saída.
Uma ACL de entrada filtra pacotes antes de serem roteados para a interface de saída. Uma ACL de entrada é eficiente porque salva a sobrecarga de pesquisas de roteamento se o pacote é descartado. Se o pacote for permitido pela ACL, ele será processado para roteamento. As ACLs de entrada são mais usadas para filtrar pacotes quando a rede conectada a uma interface de entrada é a única origem dos pacotes que precisa ser examinada.
Uma ACL de saída filtra pacotes após seu roteamento, independentemente da interface de entrada. Pacotes de entrada são roteados para a interface de saída e são processados através da ACL de saída. As ACLs de saída são mais usadas quando o mesmo filtro é aplicado aos pacotes que vêm de várias interfaces de entrada antes de saírem da mesma interface de saída.
Quando uma ACL é aplicada a uma interface, ela segue um procedimento operacional específico. Por exemplo, aqui estão as etapas operacionais usadas quando o tráfego entrou em uma interface de roteador com uma ACL IPv4 configurada no padrão de entrada .
1. O roteador extrai o endereço IPv4 de origem do cabeçalho do pacote.
2. O roteador inicia na parte superior da ACL e compara o endereço IPv4 de origem a cada ACE em uma ordem sequencial.
3. Quando houver correspondência, o roteador realizará a instrução, permitindo ou negando o pacote.
4. Se o endereço IPv4 de origem não corresponder a nenhuma ACEs na ACL, o pacote será descartado porque há uma ACE de negação implícita aplicada automaticamente a todas as ACLs.
A última instrução ACE de uma ACL é sempre uma negação implícita que bloqueia todo o tráfego. Por padrão, essa instrução é automaticamente implícita no final de uma ACL, mesmo que esteja oculta e não exibida na configuração.
**Nota**: Uma ACL deve ter pelo menos uma declaração de permissão, caso contrário, todo o tráfego será negado devido à declaração de negação ACE implícita.

# Visão geral da máscara curinga
- Máscara curinga bit 0 - Corresponde ao valor do bit correspondente no endereço
- Máscara curinga bit 1 - Ignora o valor do bit correspondente no endereço

Esta tabela mostra como máscaras curinga (wildcard masks) funcionam em redes de computadores, particularmente em protocolos como OSPF ou ACLs (Access Control Lists) em equipamentos Cisco.

| Máscara Curinga    | Último octeto (em binário)    | Significado (0 - correspondência, 1 - ignorar) |
|---|---|---|
| 0.0.0.0    | 00000000    | Combine todos os octetos.    |
| 0.0.0.63    | 00111111    | • Combine os três primeiros octetos • Combine os dois bits mais à esquerda do último octeto • Ignore os últimos 6 bits    |
| 0.0.0.15    | 00001111    | • Combine os três primeiros octetos • Combine os quatro bits mais à esquerda do último octeto • Ignore os últimos 4 bits do último octeto    |
| 0.0.0.252    | 11111100    | • Combine os três primeiros octetos • Ignore os seis bits mais à esquerda do último octeto • Combine os dois últimos bits    |
| 0.0.0.255    | 11111111    | • Combine os três primeiros octetos • Ignore o último octeto    |

# Tipos de máscara curinga
Usar máscaras curinga vai levar alguma prática. Consulte os exemplos para saber como a máscara curinga é usada para filtrar o tráfego de um host, uma sub-rede e um intervalo de endereços IPv4.
## Curinga para corresponder a um host
 a máscara curinga é usada para corresponder a um endereço IPv4 de host específico
## Curinga para corresponder a uma sub-rede IPv4
 a ACL 10 precisa de uma ACE que permita todos os hosts na rede 192.168.1.0/24. A máscara curinga 0.0.0.255 estipula que os três primeiros octetos devem corresponder exatamente, mas o quarto octeto não.
## Curinga para corresponder a um intervalo de endereços IPV4
Neste exemplo, a ACL 10 precisa de uma ACE que permita todos os hosts nas redes 192.168.16.0/24, 192.168.17.0/24,..., 192.168.31.0/24. A máscara curinga 0.0.15.255 filtraria corretamente esse intervalo de endereços.

# Cálculo da máscara curinga
Calcular as máscaras curinga pode ser um desafio. Um método de atalho é subtrair a máscara de sub-rede de 255.255.255.255. Consulte os exemplos para saber como calcular a máscara curinga usando a máscara de sub-rede.

## Exemplo 1
Suponha que você desejasse uma ACE na ACL 10 para permitir o acesso a todos os usuários na rede 192.168.3.0/24. Para calcular a máscara de curinga, subtraia a máscara de sub-rede (i.e., 255.255.255.0) de 255.255.255.255.

## Exemplo 3
Neste exemplo, suponha que você precisava de uma ACE na ACL 10 para permitir somente redes  
192.168.10.0 e 192.168.11.0. Essas duas redes podem ser resumidas como 192.168.10.0/23,  
que é uma máscara de sub-rede de 255.255.254.0. Novamente, subtrair a máscara de sub-rede  
255.255.254.0 de 255.255.255.255, conforme mostrado na tabela.

Esta solução produz a máscara curinga 0.0.1.255. Portanto, o ACE seria access-list 10 permit 192.168.10.0 0.0.1.255  

|Valor inicial|255.255.255.255|
|---|---|
|Subtrair a máscara de sub-rede|- 255.255.254.0|
|Máscara curinga resultante|0.0.1.255|

# Palavras-chave máscara curinga
Trabalhar com representações decimais de bits binários de máscara curinga pode ser entediante. Para simplificar esta tarefa, o Cisco IOS fornece duas palavras-chave para identificar os usos mais comuns do mascaramento de curinga. As palavras-chave reduzem os pressionamentos de teclas da ACL, mas, mais importante, as palavras-chave facilitam a leitura da ACE.
As duas palavras-chave são:
- **host** - Esta palavra-chave substitui a máscara 0.0.0.0. Essa máscara indica que todos os bits do endereço IPv4 precisam corresponder para filtrar apenas um endereço de host.
- **any**- Esta palavra-chave substitui a máscara 255.255.255.255. Essa máscara instrui o sistema a ignorar todo o endereço IPv4 ou a aceitar qualquer endereço.

# Criar uma ACL

```
Router(config)# access-list access-list-number {deny | permit | remark text} source [source-wildcard] [log]
```

| Parâmetro           | Descrição                                                                                   |
|---------------------|---------------------------------------------------------------------------------------------|
| access-list-number  | • Este é o número decimal da ACL. <br> • O intervalo de números ACL padrão é de 1 a 99 ou 1300 a 1999. |
| deny                | Isto nega o acesso se as condições corresponderem.                                           |
| permit              | Isto permite o acesso se as condições corresponderem.                                        |
| remark text         | • (Opcional) Isso adiciona uma entrada de texto para fins de documentação. <br> • Comentários são extremamente úteis, especialmente em ACLs mais longas ou mais complexas. <br> • Cada comentário é limitado a 100 caracteres. |
| source              | • Identifica o endereço de origem de host ou de rede a ser filtrado. <br> • Use `any` para especificar todas as redes. <br> • Use `host` com o `ip-address` ou digite apenas o `ip-address` (sem `host`) para identificar um IP específico. |
| source-wildcard     | (Opcional) Máscara curinga de 32 bits aplicada à origem. Se omitida, assume `0.0.0.0`.       |
| log                 | • (Opcional) Gera uma mensagem informacional sempre que a ACE é acionada. <br> • A mensagem inclui: número da ACL, condição (ex: permitido/negado), endereço de origem e número de pacotes. <br> • Registra apenas o primeiro pacote correspondente. <br> • **Atenção**: O uso intensivo do `log` pode sobrecarregar a CPU e afetar o desempenho. Recomendado apenas para troubleshooting ou segurança crítica. |

# Sintaxe nomeada da ACL ipv4 padrão

```
Router(config)# ip access-list standard access-list-name
```
Esse comando entra no modo de configuração padrão nomeado onde você configura as ACL ACEs.

Os nomes das ACLs são alfanuméricos, diferenciam maiúsculas de minúsculas e devem ser exclusivos. Não é necessário nomear as ACLs com letras maiúsculas, porém dessa forma elas se destacam na exibição da saída running-config. Isso torna menos provável a criação acidental de duas ACLs diferentes com o mesmo nome, mas com uso diferente de maiúsculas e minúsculas.

**Nota:** Use o comando **no ip access-list standard** access-list-name global configuration para remover uma ACL IPv4 padrão nomeada.

# Sintaxe numerada da ACL IPv4 padrão

```
Router(config)# **access-list** _access-list-number_ {**deny** | **permit** | **remark** _text_} _protocol source source-wildcard_ [ _operator_ {_port_}] _destination destination-wildcard_ [_operator_ {_port_}] [**established**] [**log**]
```

# Protocolos e números de porta

**Opções de Protocolo**
Os quatro protocolos destacados são as opções mais populares.
**Nota:** Use a **?** para obter ajuda ao inserir uma ACE mais complexa.
**Note:** Se um protocolo da internet não estiver listado, o número do protocolo IP pode ser especificado. Por exemplo, o protocolo ICMP usa o número 1, TCP é 6 e UDP é 17.

**Opções de palavra-chave da porta**
Selecionar um _protocolo_ influencia as opções de_porta_. Por exemplo, selecionando a opção:
- **tcp** protocol forneceria opções de portas relacionadas ao TCP
- **udp** protocol forneceria opções de portas relacionadas ao UDP
- **icmp** protocol forneceria opções de portas relacionadas ao ICMP (ex: tipo de mensagem)
Novamente, observe quantas opções de porta TCP estão disponíveis. As portas destacadas são opções populares.
Nomes de porta ou número podem ser especificados. No entanto, os nomes de portas facilitam a compreensão do propósito de uma ACE. Observe como alguns nomes de portas comuns (por exemplo, ssh e https) não estão listados. Para estes protocolos, os números de porta terão que ser especificados.

# ACL estendida estabelecida TCP
O TCP também pode executar serviços básicos de firewall stateful usando a palavra-chave TCP **stablished**. A palavra-chave permite que o tráfego interno saia da rede privada interna e permite que o tráfego de resposta retornado entre na rede privada interna.
No entanto, o tráfego TCP gerado por um host externo e tentar se comunicar com um host interno é negado.
A palavra-chave **established** pode ser usada para permitir apenas o tráfego HTTP de retorno de sites solicitados, ao negar todo o outro tráfego.
Na topologia, o design deste exemplo mostra que a ACL 110, que foi configurada anteriormente, filtrará o tráfego da rede privada interna. O ACL 120, usando a palavra-chave **established**, filtrará o tráfego que entra na rede privada interna da rede pública externa.

O parâmetro **established** permite que apenas as respostas para o tráfego originário da rede 192.168.10.0/24 retornem a essa rede. Especificamente, uma correspondência ocorre se o segmento TCP retornando tem os bits de sinalizador ACK ou redefinir (RST) definido. Isso indica que o pacote pertence a uma conexão existente. Sem o parâmetro **established** na instrução ACL, os clientes poderiam enviar tráfego para um servidor da Web e receber tráfego retornando do servidor da Web. Todo o tráfego seria permitido.

# Sintaxe da ACL IPv4 estendida nomeada
Nomear uma ACL facilita entender sua função. Para criar uma ACL estendida nomeada, use o seguinte comando de configuração global:
``Router(config)# ip access-list extended access-list-name``
Este comando entra no modo de configuração estendida nomeado. Os nomes das ACLs são alfanuméricos, diferenciam maiúsculas de minúsculas e devem ser exclusivos.
No exemplo, uma ACL estendida nomeada chamada NO-FTP-ACCESS é criada e o prompt foi alterado para o modo de configuração de ACL estendida nomeada. As instruções ACE são inseridas no modo de subconfiguração de ACL estendida nomeado.
```
R1(config)# ip access-list extended NO-FTP-ACCESS
R1(config-ext-nacl)#
```

# Dois métodos para modificar uma ACL
Depois que uma ACL é configurada, ela pode precisar ser modificada. ACLs com várias ACEs podem ser complexas de configurar. Às vezes, a ACE configurada não produz os comportamentos esperados. Por esses motivos, as ACLs podem inicialmente exigir um pouco de tentativa e erro para alcançar o resultado de filtragem desejado.
Esta seção discutirá dois métodos a serem usados ao modificar uma ACL:
- Use um editor de texto
- Use números de sequência

``configure terminal`` entra no modo de configuração global

# Guia de configurações ACL
Uma ACL é composta de uma ou mais entradas de controle de acesso (ACEs) ou instruções. Ao configurar e aplicar uma ACL, esteja ciente das diretrizes resumidas nesta lista:
- Crie um ACL globalmente e aplique-a.
- Garanta que a última declaração seja uma implícita **deny any** ou **deny ip any any**.
- Lembre-se de que a ordem da declaração é importante porque os ACLs são processados de cima para baixo.
- Assim que uma declaração é correspondida ao ACL, é saído.
- Sempre filtre o mais específico para o mais genérico. Por exemplo, negue um host específico e permita todos os outros hosts.
- Lembre-se que apenas uma ACL é permitida por interface, por protocolo, por direção.
- Lembre-se que novas declarações para uma ACL existente são adicionadas à parte inferior da ACL por padrão.
- Lembre-se que os pacotes gerados por roteador não são filtrados por ACLs de saída.
- Coloque os ACL padrão o mais próximo possível do destino.
- Coloque os ACLs estendidos o mais próximo possível da fonte.
# Aplique uma ACL
Depois de criar uma ACL, o administrador pode aplicá-lo de várias maneiras diferentes. O seguinte mostra a sintaxe de comando para aplicar uma ACL a uma interface ou para as linhas VTY.

``Router(config-if)# ip access-group {acl-# | name} {in | out}``
``Router(config-line)# ip access-class {acl-# | name} {in | out}``

Ativar o parâmetro **log** em um roteador ou switch Cisco afeta seriamente o desempenho desse dispositivo. O parâmetro de log deve ser usado somente quando a rede estiver em ataque, e um administrador está tentando determinar quem é o invasor.

ACLs estendidas são normalmente colocadas próximo à origem
ACLs padrão são normalmente colocadas próximo ao destino

