## Backlog do Produto

Quem?        | O que?               | Para                                                        | Prioridade      | Status
------------ | --------------------| -------------------------------------------------------------|-----------------|--------|
Funcionario  | Quer criar chamados de suporte com descrição a categoria detalhadas. | Relatar problemas técnicos de forma organizada.| P1 | Em andamento ⏳ |
Funcionario  | Quero ver o status de meus chamados anteriores. | Fazer um acompanhamento sem entrar em contato com a area de TI.  |  P2 | Em andamento ⏳ |
Sistema      | Como um sistema de IA, devo analisar a descrição do tíquete | Atribuição de prioridade (baixa/média/alta) com base em palavras-chave históricas. | P1 | Em andamento ⏳ |
Sistema      | Como um sistema de IA, devo atribuir chamados ao técnico | Que o técnico designado resolva o chamado. |P1|Em andamento ⏳ |
Técnico    |Quero Exbir chamados atribuídos | Saber quais chamados estão pendentes para serem resolvidos. |P1|Em andamento ⏳ |
Técnico     | Quero gerenciar meus chamados asginados | Ser mais organizado em meu trabalho diário. | P2 |Em andamento ⏳ |
Administrador | Desejo poder gerenciar os níveis de acesso | que os usuários possam ter sua função atribuída a eles. |P1|Em andamento ⏳ |
Administrador | Desejo poder gerenciar os chamados| Conhecer quais problemas existem na empresa e que prioridade está sendo dada a eles. | P1 |Em andamento ⏳ |

## Requisitos

Prioridade 1:

ReF001: Usuários devem ser capazes de criar chamados, estes chamados devem ter descrição, categoria (software e hardware) e quem ele afeta, se o problema afeta apenas o funcionário, a equipe ou a empresa.

ReF002: Tratamento de Chamados via I.A, O sistema deve analisar os chamados por meio de uma I.A, e após a análise deve atribuir um nível de prioridade com base na descrição, categoria e quem o chamado afeta os enviar para o responsável técnico, e caso necessário recategorizar o chamado.

ReNF1: O banco de dados deve ser MS SQL server hospedado em Windows Server.

ReNF2: Desktop: Interface em C# com Windows Forms, WPF para gestão administrativa do sistema, Blazor etc.

ReNF3: Web: ASP.NET e C# para a aplicação web responsiva.

Prioridade 2:

ReF003: Gerenciamento de chamados, Os chamados pendentes e concluídos poderão ser acessados pelo(s) responsável técnico, e podem ser marcados como concluídos após o problema ser resolvido.

ReF004: Criação de Relatórios: O sistema deve ser capaz de criar relatórios semanais e mensais sobre os chamados criados, resolvidos e pendentes.

Prioridade 3:

ReF005: Níveis de acesso: O Sistema deve possuir níveis de acesso (funcionário, responsável técnico e administrador).
