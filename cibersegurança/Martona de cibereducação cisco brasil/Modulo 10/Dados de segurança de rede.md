# Dados de alerta
Os dados de alerta consistem em mensagens geradas por sistemas de prevenção de intrusões (IPSs) ou sistemas de detecção de intrusões (IDSs) em resposta ao tráfego que viola uma regra ou corresponde à assinatura de uma exploração conhecida. Um IDS de rede (NIDS), como o Snort, vem configurado com regras para explorações conhecidas. Os alertas são gerados pelo Snort e são legíveis e pesquisáveis pelos aplicativos Sguil e Squert, que fazem parte do conjunto Security Onion de ferramentas NSM.
Um site de teste que é usado para determinar se o Snort está funcionando é o site tesmyids. Procure por ele na internet. Consiste em uma única página da Web que exibe apenas o seguinte texto **uid=0(root) gid=0(root) groups=0(root)**. Se o Snort estiver funcionando corretamente e um host visitar este site, uma assinatura será correspondida e um alerta será acionado. Esta é uma maneira fácil e inofensiva de verificar se o NIDS está em execução.
A regra Snort que é acionada é:
```
alert ip any any -> any any (msg:"GPL ATTACK\_RESPONSE id check returned root"; content:"uid=0|28|root|29|"; fast\_pattern:only; classtype:bad-unknown; sid:2100498; rev:8;)
```
Esta regra gera um alerta se **qualquer endereço IP** na rede receber dados de uma fonte externa que contenha conteúdo com texto correspondente ao padrão de **uid=0 (root)**. O alerta contém a mensagem **GPL ATTACK_RESPONSE id check retornou root**. O ID da regra Snort que foi acionada é **2100498**.
A linha destacada na figura exibe um alerta Sguil que foi gerado visitando o site testmyids. A regra Snort e os dados do pacote para o conteúdo recebido da página da Web testmyvids são exibidos na área inferior direita da interface Sguil.

# Dados de Sessão e Transação
1. **ts**: carimbo de data e hora
2. **uid**: ID de sessão única
3. **id.orig_h**: Endereço IP do host que originou a sessão (endereço de origem)
4. **id.orig_p**: porta de protocolo para o host de origem (porta de origem)
5. **id.resp_h**: Endereço IP do host que responde ao host de origem (endereço de destino)
6. **id.resp_p**: protocolo de host respondente (porta de destino)
7. **proto**: protocolo de camada de transporte para sessão
8. **service**: protocolo de camada de aplicativo
9. **duration**: duração da sessão
10. **orig_bytes**: bytes do host de origem
11. **resp_bytes**: bytes do host respondente
12. **orig_packets**: pacotes do host de origem
13. **resp_packets**:pacotes do host respondente

Os dados de sessão são um registro de uma conversa entre dois pontos de extremidade de rede, que geralmente são um cliente e um servidor. O servidor pode estar dentro da rede corporativa ou em um local acessado pela Internet. Dados de sessão são dados sobre a sessão, não os dados recuperados e usados pelo cliente. Os dados da sessão incluirão informações de identificação, como **as cinco tuplas** de endereços IP de origem e destino, números de porta de origem e destino, e o código IP do protocolo em uso. Os dados sobre a sessão geralmente incluem um ID de sessão, a quantidade de dados transferidos por origem e destino e informações relacionadas à duração da sessão.
Zeek, anteriormente Bro, é uma ferramenta de monitoramento de segurança de rede que você usará em laboratórios mais tarde no curso. A figura mostra uma saída parcial para três sessões HTTP a partir de um log de conexão Zeek.
Os dados de transação consistem nas mensagens que são trocadas durante sessões de rede. Essas transações podem ser exibidas em transcrições de captura de pacotes. Os logs de dispositivos mantidos por servidores também contêm informações sobre as transações que ocorrem entre clientes e servidores. Por exemplo, uma sessão pode incluir o download de conteúdo de um servidor web, como mostrado na figura. As transações que representam as solicitações e respostas seriam registradas em um log de acesso no servidor ou por um NIDS como Zeek. A sessão é todo o tráfego envolvido na elaboração da solicitação, a transação é a própria solicitação.

# Capturas completas de pacotes
Capturas completas de pacotes são os dados de rede mais detalhados que geralmente são coletados. Devido à quantidade de detalhes, eles também são os tipos de dados mais intensos de armazenamento e recuperação usados no NSM. As capturas completas de pacotes contêm não apenas dados sobre conversas de rede, como dados de sessão. As capturas completas de pacotes também contêm o conteúdo real das conversas. As capturas completas de pacotes contêm o texto das mensagens de email, o HTML nas páginas da Web e os arquivos que entram ou saem da rede. O conteúdo extraído pode ser recuperado de capturas completas de pacotes e analisado quanto a malware ou comportamento do usuário que viola as políticas de negócios e de segurança. A ferramenta familiar Wireshark é muito popular para visualizar capturas de pacotes completos e acessar os dados associados a conversas de rede.
A figura ilustra a interface do componente Monitor de Análise de Rede do sistema Cisco Prime Infrastructure, que, como o Wireshark, pode exibir capturas completas de pacotes.

# Dados estatísticos
Como dados de sessão, dados estatísticos são sobre tráfego de rede. Os dados estatísticos são criados através da análise de outras formas de dados de rede. Podem ser feitas conclusões que descrevem ou predizem o comportamento da rede a partir dessas análises. As características estatísticas do comportamento normal da rede podem ser comparadas ao tráfego de rede atual em um esforço para detectar anomalias. As estatísticas podem ser usadas para caracterizar quantidades normais de variação nos padrões de tráfego de rede, a fim de identificar condições de rede que estão significativamente fora desses intervalos. Diferenças estatisticamente significativas devem gerar alarmes e investigação imediata.
A NBA (Network Behavior Analysis) e a Network Behavior Anomaly Detection (NBAD) são abordagens para monitoramento de segurança de rede que usam técnicas analíticas avançadas para analisar dados de telemetria de rede NetFlow ou IPFIX (Internet Protocol Flow Information Export). Técnicas como análise preditiva e inteligência artificial realizam análises avançadas de dados de sessão detalhados para detectar possíveis incidentes de segurança.
**Observação**: IPFIX é a versão padrão IETF do Cisco NetFlow versão 9.
Um exemplo de uma ferramenta NSM que utiliza análise estatística é o Cisco Cognitive Threat Analytics. Ele é capaz de encontrar atividades mal-intencionadas que ignorou os controles de segurança ou entrou na rede por meio de canais não monitorados (incluindo mídia removível) e está operando dentro do ambiente de uma organização. O Cognitive Threat Analytics é um produto baseado em nuvem que usa aprendizado de máquina e modelagem estatística de redes. Ele cria uma linha de base do tráfego em uma rede e identifica anomalias. Ele analisa o comportamento do usuário e do dispositivo e o tráfego da Web para descobrir comunicações de comando e controle, exfiltração de dados e aplicativos potencialmente indesejados que operam na infraestrutura. A figura ilustra uma arquitetura para o Cisco Cognitive Threat Analytics.

# Logs de hosts
Conforme discutido anteriormente, os sistemas de detecção de intrusão baseados em host (HIDS) são executados em hosts individuais. HIDS não só detecta intrusões, mas na forma de firewalls baseados em host, também pode impedir intrusões. Este software cria logs e os armazena no host. Isso pode dificultar a visão do que está acontecendo em hosts na empresa, pois muitas proteções baseadas em host têm uma maneira de enviar logs para servidores centralizados de gerenciamento de logs. Dessa forma, os logs podem ser pesquisados a partir de um local central usando as ferramentas NSM.

Os sistemas HIDS podem usar agentes para enviar logs para servidores de gerenciamento. O OSSEC, um HIDS de código aberto popular, inclui uma funcionalidade robusta de coleta e análise de logs. Pesquise OSSEC na internet para saber mais. O Microsoft Windows inclui vários métodos para coleta e análise automatizadas de logs de host. Tripwire oferece um HIDS para Linux que inclui funcionalidade semelhante. Todos podem ser dimensionados para grandes empresas.

Os logs de host do Microsoft Windows são visíveis localmente pelo Visualizador de Eventos. O Visualizador de Eventos mantém cinco tipos de logs:

- **Logs de aplicativos** — Eles contêm eventos registrados por vários aplicativos.
- **Registros do sistema** — Isso inclui eventos relacionados à operação de drivers, processos e hardware.
- **Registros de instalação** — Estes registram informações sobre a instalação de software, incluindo atualizações do Windows.
- **Registros de segurança** — Esses eventos registram relacionados à segurança, como tentativas de logon e operações relacionadas ao gerenciamento e acesso de arquivos ou objetos.
- **Logs da linha de comando** - Os invasores que obtiveram acesso a um sistema e alguns tipos de malware executam comandos da interface de linha de comando (CLI) em vez de uma GUI. A execução da linha de comando em log fornecerá visibilidade para esse tipo de incidente.

Vários logs podem ter diferentes tipos de eventos. Os logs de segurança consistem apenas em mensagens de falha ou êxito de auditoria. Em computadores Windows, o log de segurança é realizado pelo Local Security Authority Subsystem Service (LSASS), que também é responsável por impor diretivas de segurança em um host Windows. O LSASS é executado como lsass.exe. Ele é frequentemente falsificado por malware. Ele deve estar sendo executado a partir do diretório System32 do Windows. Se um arquivo com esse nome, ou um nome camuflado, como 1sass.exe, estiver em execução ou em execução a partir de outro diretório, ele pode ser malware.

Os Eventos do Windows são identificados por números de ID e descrições breves. Uma enciclopédia de IDs de eventos de segurança, algumas com detalhes adicionais, está disponível no Ultimate Windows Security na Web.
A tabela explica o significado dos cinco tipos de eventos de log de host do Windows.

| Tipo de evento        | Descrição |
|-----------------------|-----------|
| Erro | Um erro é um evento que indica um problema significativo, como perda de dados ou perda de funcionalidade. Por exemplo, se um serviço falhar ao carregar durante a inicialização, um evento de erro será registrado. |
| Aviso | Um aviso é um evento que não é necessariamente significativo, mas pode indicar um possível problema futuro. Por exemplo, quando o espaço em disco é baixo, um evento de aviso é registrado. Se um aplicativo pode se recuperar de um evento sem perda de funcionalidade ou dados, ele geralmente pode classificar o evento como um evento de aviso. |
| Informações | Um evento informativo descreve a operação bem-sucedida de um aplicativo, driver ou serviço. Por exemplo, quando um driver de rede é carregado com êxito, pode ser apropriado registrar um evento de informações. Observe que geralmente é inapropriado para um aplicativo de área de trabalho registrar um evento cada vez que ele é iniciado. |
| Sucesso na Auditoria | Uma auditoria bem-sucedida é um evento que registra uma tentativa de acesso de segurança auditada com êxito. For example, a user's successful attempt to log on to the system is logged as a success audit event. |
| Falha na Auditoria | Uma auditoria de falha é um evento que registra uma tentativa de acesso de segurança auditada que falha. Por exemplo, se um usuário tentar acessar uma unidade de rede e falhar, a tentativa é registrada como um evento de auditoria de falha. |

# Syslog
O Syslog inclui especificações para formatos de mensagem, uma estrutura de aplicativos cliente-servidor e protocolo de rede. Muitos tipos diferentes de dispositivos de rede podem ser configurados para usar o padrão syslog para registrar eventos em servidores syslog centralizados.
Syslog é um protocolo cliente / servidor. O Syslog foi definido dentro do grupo de trabalho Syslog do IETF (RFC 5424) e é suportado por uma grande variedade de dispositivos e receptores em várias plataformas.
O remetente do Syslog envia uma pequena mensagem de texto (menos de 1 KB) para o receptor do Syslog. O receptor Syslog é comumente chamado de “syslogd”, “Syslog daemon” ou “Syslog server.“ As mensagens do Syslog podem ser enviadas via UDP (porta 514) e/ou TCP (normalmente, porta 5000). Embora existam algumas exceções, como wrappers SSL, esses dados são normalmente enviados em texto simples pela rede.
O formato completo de uma mensagem Syslog que é visto na rede tem três partes distintas, como mostrado na figura.
- PRI (prioridade)
- HEADER
- MSG (texto da mensagem)
O PRI consiste em dois elementos, a Facilidade e a Gravidade da mensagem, que são ambos valores inteiros. O recurso consiste em amplas categorias de fontes que geraram a mensagem, como o sistema, o processo ou a aplicação. O valor Facility pode ser usado por servidores de log para direcionar a mensagem para o arquivo de log apropriado. A gravidade é um valor de 0 a 7 que define a gravidade da mensagem.

**severidade**

| Nível | Descrição                                                                                                               |
| ----- | ----------------------------------------------------------------------------------------------------------------------- |
| 0     | Emergência: sistema está inutilizável                                                                                   |
| 1     | Alerta: a ação deve ser tomada imediatamente                                                                            |
| 2     | Crítico: condições críticas que devem ser corrigidas imediatamente e indica falha em um sistema                         |
| 3     | Erro: uma falha que não é urgente, deve ser resolvida dentro de um determinado tempo                                    |
| 4     | Aviso: um erro não existe atualmente; no entanto, um erro ocorrerá no futuro se a condição não for resolvida            |
| 5     | Aviso: Qual ferramenta está incluída no Security Onion que é usada pelo Snort para baixar automaticamente novas regras? |
| 6     | Informativo: mensagens emitidas relativas ao funcionamento normal                                                       |
| 7     | Depuração: mensagens de interesse para desenvolvedores                                                                  |
O valor de Prioridade (PRI) é calculado multiplicando o valor de Facilidade por 8 e, em seguida, adicionando-o ao valor de Gravidade, conforme mostrado abaixo.

**Prioridade = (Facilidade * 8) + Severidade**

O valor Prioridade é o primeiro valor em um pacote e ocorre entre colchetes angulados **<>**.

A seção **HEADER** da mensagem contém o carimbo de data/hora no formato **MMM DD HH:MM:SS**. Se o carimbo de data/hora for precedido pelos símbolos de ponto (.) ou asterisco (\*), um problema é indicado com NTP. A seção HEADER também inclui o nome do host ou endereço IP do dispositivo que é a origem da mensagem.

A parte **MSG** contém o significado da mensagem syslog. Isso pode variar entre os fabricantes de dispositivos e pode ser personalizado. Portanto, essa parte da mensagem é a mais significativa e útil para o analista de segurança cibernética.

# Logs do servidor
Os logs do servidor são uma fonte essencial de dados para o monitoramento da segurança da rede. Os servidores de aplicativos de rede, como servidores de e-mail e Web, mantêm registros de acesso e erros. Os logs do servidor proxy DNS que documentam todas as consultas DNS e respostas que ocorrem na rede são especialmente importantes. Os logs de proxy DNS são úteis para identificar hosts que possam ter visitado sites perigosos e para identificar a exfiltração de dados DNS e conexões a servidores de comando e controle de malware. Muitos servidores UNIX e Linux usam syslog. Outros podem usar o registro proprietário. O conteúdo dos eventos do arquivo de log depende do tipo de servidor.
Dois arquivos de log importantes para se familiarizar são os logs de acesso do servidor web Apache e os logs de acesso do Microsoft Internet Information Server (IIS). Exemplos de cada um são mostrados abaixo.