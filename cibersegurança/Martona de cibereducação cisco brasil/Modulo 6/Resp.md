Não depende de ACLs.

Uma zona estabelece uma borda de segurança de uma rede.

determinar as zonas

Por padrão, o tráfego pode fluir entre interfaces que são membros da mesma zona.

Passe, inspecione e as opções de gota só podem ser aplicadas entre duas zonas.
Para permitir o tráfego para uma interface de membro da zona, uma política permitindo ou inspecionar o tráfego deve ser configurada entre essa zona e qualquer outra zona.
Se o tráfego for fluir entre todas as interfaces em um roteador, cada interface deve ser membro de uma zona.

O próprio roteador, incluindo todas as interfaces com endereços IP atribuídos

DESCARTAR

Uma zona deve ser configurada com o comando global **zone security antes de poder ser usado **no comando** zone-member security**.

A ação de passagem funciona em apenas uma direção.

Inspecionar lista
DESCARTAR

Configurando mapas de classe.

O tráfego deve corresponder a todos os critérios de correspondência especificados na declaração.