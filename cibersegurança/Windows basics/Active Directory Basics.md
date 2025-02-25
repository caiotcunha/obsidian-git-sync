Windows domain é um grupo de usuários e computadores sob a administração de um negócio. A ideia principal em torno disso é administração de componentes comuns a uma rede de computadores windows de maneira centralizada em um repositório chamado de **Active Directory**. O servidor que roda o AD é chamado de **Domain Controller (DC)**

## Principais vantagens
- Gestão centralizada de identidades: Todos os usuários da rede podem ser configurados do AD
- Gestão de políticas de segurança: As políticas de segurança podem ser programadas direto do AD e aplicadas aos usuários e computadores conforme o necessário

## Active Directory

### Active directory domain service
Esse serviço age como um catálogo que mantém todas as informações dos "objetos" na rede

### Users
Um dos tipos de objetos mais comuns em um AD. São um dos objetos conhecidos como security principals, o que significa que podem ser autenticados pelo domínio e receber privilégios sobre recursos.
Podem ser usados para representar dois tipos de entidades:
- Pessoas
- Serviços: Todo serviço precisa de um usuário, mas usuários de serviço são diferentes dos usuários normais pelo fato de que só vão receber os privilégios necessários para rodar os serviços específicos que eles precisam

### Máquinas
Também são security principals e recebem uma conta como um usuário normal. Essa conta tem algumas limitações dentro do domínio. Geralmente, essas contas não devem ser acessadas por qualquer pessoa além da própria máquina.
Uma conta de máquina vai ter o formato ```"nome_da_máquina"$```.

### Security Groups
Podemos definir grupos com certos privilégios e associar usuários a eles. Isso facilita bastante o gerenciamento de privilégios já que cada usuário associado ao grupo recebe automaticamente os privilégios. Também são considerados security principals.
Vários grupos são criados automaticamente pelo windows.
Usados para garantir permissão sobre recursos.

### Organizational Units
Úteis para aplicar politicas à usuários e computadores. Um usuário só pode fazer parte de um OU de cada vez

## Group Policies
Group policies geralmente são ligadas as OU. As group policies tem hierarquia e as superiores afetam as inferiores.

### GPO distribution
São distribuidos pela rede por um compartilhamento de rede chamado ```SYSVOL``` que é armazenado no Domain controller. O padrão é ```C:\Windows\SYSVOL\sysvol\``` 

### Authentication Methods
Atualmente o kerberos é a authenticação padrão em redes windows.
Sumário
- **TGS:** Ticket Granting Service
- **TGT:** Ticket Granting Ticket
- **KDC:** Key distibution center


![[Pasted image 20250221131711.png]]

![[Pasted image 20250221131933.png]]

![[Pasted image 20250221132034.png]]


### Trees, Forests and Trusts
Todos esses componentes são feitos para facilitar a escalabilidade da organização do servidor.

#### Trees
Facilitam a criação de novos DC que podem ser gerenciados por outra equipe. Continuam subordinados ao DC principal. Compartilham o mesmo namespace.

#### Florests
Juntam várias Trees

#### Trusts
Ter uma relação de trust possibilita autorizar um usuário de um domínio a ter acesso aos recursos de outro domínio. Elas podem ser de mão única ou dupla dependendo da necessidade.

