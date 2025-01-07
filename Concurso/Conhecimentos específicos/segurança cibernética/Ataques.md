Entre os fatores que podem tornar uma aplicação vulnerável estão o sistema operacional, o servidor web/aplicativo, o sistema de gerenciamento de banco de dados (SGBD), as API e todos os componentes, ambientes de tempo de execução e bibliotecas.

Como exemplo de melhor prática, o OWASP recomenda que os responsáveis por segurança de uma aplicação monitorem continuamente fontes como CVE (common vulnerability and exposures) e NVD (national vulnerability database) em busca de vulnerabilidades nos componentes usados na aplicação.


# Documentos



# OWASP SAMM

Na verdade, o OWASP SAMM (Software Assurance Maturity Model) é um modelo de maturidade que ajuda as organizações a formularem e implementarem uma estratégia de segurança de software adaptada aos riscos específicos do negócio. O objetivo principal do SAMM é fornecer uma estrutura para a medição e melhoria das práticas de segurança no desenvolvimento de software.

# OWASP top 10



# Ataques

## Spoofing
Esse termo refere-se a uma técnica de ataque em que o invasor finge ser outra pessoa ou dispositivo, mascarando sua identidade verdadeira. O objetivo principal do **spoofing** é enganar sistemas, usuários ou dispositivos para obter acesso não autorizado a informações ou a uma rede.
Exemplos:
- **IP Spoofing:** O invasor envia pacotes com um endereço de IP falsificado para parecer que estão vindo de uma fonte confiável.  
- **Email Spoofing:** O invasor falsifica o endereço de remetente de um email para parecer que a mensagem está vindo de uma fonte confiável.
- **ARP Spoofing:** O invasor envia mensagens ARP falsas na rede local, associando seu endereço MAC com o IP de um dispositivo legítimo.

## Leakware/doxware 
Leakware ou doxware é um ransomware que rouba, ou exfiltra, dados confidenciais e **ameaça publicá-los.**

## APT (advanced persistent threats)
Esses são ataques sofisticados e direcionados, que buscam infiltrar-se em uma rede por longos períodos para extrair informações sensíveis. Diferente de ataques comuns, eles não são rápidos e não têm como objetivo causar danos imediatos, mas sim realizar espionagem e roubo de dados de forma discreta e prolongada.

## Phising
Phishing é um tipo de ataque cibernético que usa e-mails, mensagens de texto, telefonemas ou sites fraudulentos para enganar as pessoas a compartilhar dados confidenciais, baixar malware ou se expor a crimes cibernéticos de outras formas. Ataques de phishing são uma forma de engenharia social.

Tipos de phising:
- spear phishing: tem como alvo um grupo específico ou tipo de indivíduo, como os administradores de sistema de uma empresa
- whaling: tem como alvo um CEO ou CFO de um setor ou negócio específico.