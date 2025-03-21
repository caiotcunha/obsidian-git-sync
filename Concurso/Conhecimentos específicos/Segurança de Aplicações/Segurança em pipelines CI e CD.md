A segurança de CI/CD é utilizada para proteger pipelines de códigos com a automação de verificações e testes para evitar vulnerabilidades na entrega do software. Incorporar a segurança aos seus pipelines de dados ajuda a proteger os códigos de ataques, evitar vazamentos de dados, ficar em conformidade com as políticas e assegurar a qualidade.

O CI/CD é crítico para o DevSecOps porque ele automatiza e incorpora verificações de segurança no início do processo de desenvolvimento, assegurando feedback rápido sobre possíveis vulnerabilidades. Isso facilita uma abordagem da segurança proativa ao longo de todo o ciclo de vida da aplicação.

O conceito de "shift left" é um princípio fundamental em CI/CD e DevSecOps que envolve a migração de certas tarefas e atividades voltadas à segurança para o início do processo de desenvolvimento do software. Essa prática de implementar a segurança no começo inclui a automação dos teste que buscam vulnerabilidades de segurança, analisam mudanças nos códigos assim que elas são implementadas e promovem uma cultura de vigilância proativa da segurança entre as equipes de desenvolvimento e operação.

**Fase de planejamento:** é importante incluir verificações de segurança em cada fase do pipeline para assegurar que o seu código seja seguro e esteja em conformidade com os padrões de segurança. A primeira etapa é desenvolver um roadmap da solução, que vai ajudar a identificar possíveis ameaças à segurança. Isso é conhecido como modelagem de ameaças (threat modeling). Na modelagem de ameaças, possíveis vulnerabilidades são identificadas e medidas preventivas são preparadas para minimizar os riscos. 
**Código:** conforme os desenvolvedores escrevem o código, tome medidas para garantir que ele esteja em conformidade com padrões predefinidos e diretrizes de design. Utilize scanners de código-fonte para detectar partes do código que possam estar vulneráveis a ameaças de segurança.
**Compilação:** quando os desenvolvedores começarem a migrar os códigos-fonte para um repositório compartilhado, certifique-se de que os testes de automação sejam acionados para verificar se as compilações estão em conformidade com os requisitos. 
**Teste:** quando a compilação estiver concluída, teste o software para identificar bugs. Se novas funcionalidades forem adicionadas, mais testes automatizados serão realizados.

## Melhores práticas de segurança de CI/CD

- **Monitoramento e alertas**
- **Use o princípio RBAC combinado com menos privilégios:** Fornecer acesso aos recursos do sistema com base na função ou função designada de um usuário dentro de uma organização é a base do Controle de Acesso Baseado em Função ou RBAC. 
- **Mantenha a proveniência do pipeline como um registro imutável**
- **Utilize totalmente seu SBOM:** Um SBOM **é um inventário legível por máquina de um aplicativo, que identifica os pacotes usados pelo software**. O conteúdo pode incluir softwares de terceiros de fornecedores, artefatos internos e bibliotecas de código aberto. Usamos para comparar com uma lista de CVEs conhecidos e verificar possíveis vulnerabilidades no código
- **Verifique a conformidade com suas políticas**
- **Proteja o arquivo de instruções do pipeline**
- **Garanta seu resultado final**