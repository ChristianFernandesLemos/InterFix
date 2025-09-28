# PRIMERA SPRINT (25/08/2025)

A sprint em questão se concentrou no desenvolvimento do backlog do produto, reunindo os requisitos funcionais e requisitos não funcionais, os quais foram separados por prioridade, de modo a proporcionar uma visão clara acerca do sistema a ser implementado. 

<p align = "center">
  | <a href="requisitos">requisitos</a> |
  <a href="modelagem">modelagem</a> |
  <a href="ferramentas">ferramentas</a> |
</p>

## Backlog do Produto: 
<a id = "requisitos"></a>

Prioridade 1:

Re001: Usuários devem ser capazes de criar chamados, estes chamados devem ter descrição, categoria (software e hardware) e quem ele afeta, se o problema afeta apenas o funcionário, a equipe ou a empresa.

Re002: Tratamento de Chamados via I.A, O sistema deve analisar os chamados por meio de uma I.A, e após a análise deve atribuir um nível de prioridade com base na descrição, categoria e quem o chamado afeta os enviar para o responsável técnico, e caso necessário recategorizar o chamado.

ReNF1: O banco de dados deve ser MS SQL server hospedado em Windows Server.

ReNF2: Desktop: Interface em C# com Windows Forms, WPF para gestão administrativa do sistema, Blazor etc.

ReNF3: Web: ASP.NET e C# para a aplicação web responsiva.


Prioridade 2:

Re003: Gerenciamento de chamados, Os chamados pendentes e concluídos poderão ser acessados pelo(s) responsável técnico, e podem ser marcados como concluídos após o problema ser resolvido.

Re004: Criação de Relatórios: O sistema deve ser capaz de criar relatórios semanais e mensais sobre os chamados criados, resolvidos e pendentes.

Prioridade 3:

Re005: Níveis de acesso: O Sistema deve possuir níveis de acesso (funcionário, responsável técnico e administrador).

## Modelagem de requisitos  
<a id = "modelagem"></a>
* Os requisitos foram modelados em diagramas de [casos de uso](https://github.com/ChristianFernandesLemos/InterFix/tree/main/Diagramas), com o objetivo de oferecer ao cliente e à equipe de desenvolvimento uma visão mais clara sobre o sistema e sua respectiva implementação.

## Ferramentas utilizadas  
<a id = "ferramentas"></a>
* Astah UML

## 🏅 DoR - Definition of Ready <a id="dor"></a>

|             Critério             | Descrição                                                                                         |
| :------------------------------: | ------------------------------------------------------------------------------------------------- |
|       Clareza na Descrição       | Os casos de uso e suas descrições estão escritass de maneira clara e precisa            |
| Critérios de Aceitação Definidos | A história possui critérios objetivos que indicam o que é necessário para considerá-la concluída. |
|           Independente           | A história pode ser implementada sem depender de outra tarefa da mesma Sprint.                    |
|    Compreensão Compartilhada     | Toda a equipe (incluindo PO e devs) compreende o propósito da história.                           |
|       Documentos de Apoio        | Se necessário, fluxos ou modelos de dados estão anexados ou referenciados.               |
|   Critérios técnicos acordados   | As necessidades de Frontend e Backend foram claramente separadas.              |

## 🏅 DoD - Definition of Done <a id="dod"></a>

|                 Critério                 | Descrição                                                                            |
| :--------------------------------------: | ------------------------------------------------------------------------------------ |
|     Critérios de Aceitação atendidos     | Todos os cenários de teste da história foram executados e aprovados.                 |
|        Testes manuais realizados         | Onde aplicável (ex: US07), os dados são corretamente armazenados e recuperáveis.     |
|             Código revisado              | O código foi revisado por pelo menos um colega de equipe.                            |
|     Documentação interna atualizada      | Foi atualizado o que for necessário: API, estrutura de dados, endpoints, etc.        |
|  Integração com outras partes testadas   | As interfaces entre Frontend e Backend foram validadas.                              |
| Build/Testes automatiados (se aplicável) | A funcionalidade não quebra a aplicação e passa nos testes automatizados existentes. |
|             Validação do PO              | O Product Owner validou a entrega com base nos critérios definidos.                  |
|            Pronto para deploy            | O item está testado, validado e pode ser integrado ao produto final.                 |
