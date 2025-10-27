# InterFix 🚀
## Quem somos?
A InterFix é uma empresa dedicada a transformar o suporte técnico empresarial por meio do uso de inteligência artificial. Nosso objetivo é conectar soluções inteligentes com as necessidades de nossos clientes, oferecendo assistência eficiente, personalizada e em tempo real.
<p align="center">
  
  <a href ="#desafio"> Desafio</a>  |
  <a href ="#solucao"> Solução</a>  | 
  [BackLog do Produto](https://github.com/ChristianFernandesLemos/InterFix/blob/main/Backlog/Backlog%20do%20Produto.md) | 
  <a href ="#dor">DoR</a>  |
  <a href ="#dod">DoD</a>  |
  <a href ="#sprint"> Cronograma de Sprints</a> |
  <a href ="#tecnologias">Tecnologias</a> |
  <a href ="#equipe"> Equipe</a> |
</p>

---

<p align="center"><img width="700" height="500" alt="Logo Empresa" src="https://github.com/user-attachments/assets/8aa8a096-88fa-4be4-952c-946d63ceed66">

---

# 🏅 Desafio
<a id="desafio"></a>

O desafio consiste em criar um sistema integrado para web, desktop e mobile de suporte tecnico e gestão de chamados con integração de IA. O aplicativo possuira três níveis de acesso e deve ser capaz de analisar e atribuir a prioridade do chamado, também atribuirá o chamado ao técnico que tiver a carga horária mais baixa. Além da criação e gestão de chamadas, o sistema deverá gerar e gerenciar relatórios (com filtro de tempo), disponibilizando também uma função para gerenciar os níveis de acesso (função à qual somente o administrador poderá acessar).

## 🏅 Solução 
<a id="solucao"></a>

O IMT - Interfix Management Tool permitirá que os usuários criem chamados para informar problemas internos, com o uso de inteligencia artificial para o tratamento dos chamados e atribuição do chamado para os tecnicos responsaveis, possibilitando um rapido gerenciamento de chamados para os mesmos através de um sistema intuitivo e facil de se lidar, e fazendo uma analise completa das informações armazenadas sobre os chamados através de relatórios detalhados.

---
## BackLog do Produto

[Backlog](https://github.com/ChristianFernandesLemos/InterFix/blob/main/Backlog/Backlog%20do%20Produto.md)

---

## 📅 Cronograma das Sprints
<a id="sprint"></a>
[Cronograma das Sprints](https://github.com/ChristianFernandesLemos/InterFix/blob/main/Scrum/Cronograma%20das%20Sprints/SprintPlaning.md)

---

## Tecnologias Utilizadas

<a id="tecnologias"></a>

Categoria | Tecnologia 
----------|---------------|
FrontEnd  | HTML, CSS e Figma |
BackEnd | python e C# |
Banco de dados | BrModel e SQL Server|
I.A | BlackBox AI |
Metodologia | 	Scrum |

---

# 🏗️ Arquitetura

O sistema segue o padrão **MVC (Model-View-Controller)** com as seguintes camadas:

```
├── Models/          # Modelos de dados (Funcionários, Chamados)
├── Controllers/     # Lógica de negócio
├── Forms/          # Interface do usuário (Windows Forms)
├── Data/           # Acesso a dados (SQL Server)
├── Interfaces/     # Contratos e interfaces
├── Config/         # Configurações do sistema
└── Database/       # Scripts SQL
```

---

# Como Executar, usar e testar o projeto

## 📋 Pré-requisitos

### Software Necessário:
- **Windows 10/11** ou Windows Server 2016+
- **.NET Framework 4.7.2** ou superior
- **SQL Server 2016** ou superior (Express, Standard, Enterprise)
- **Visual Studio 2019/2022** (para desenvolvimento)

### Permissões Necessárias:
- Acesso ao SQL Server com permissões de criação de banco
- Permissões de escrita na pasta de logs (`C:\Logs\SistemaChamados\`)

## 🚀 Instalação

### 1. Preparar o Banco de Dados

#### Opção A: SQL Server Express (Recomendado para desenvolvimento)
```sql
-- 1. Instalar SQL Server Express
-- 2. Conectar usando SQL Server Management Studio (SSMS)
-- 3. Criar o banco de dados
CREATE DATABASE SistemaChamados;
```

#### Opção B: SQL Server Completo
```sql
-- Conectar ao servidor SQL Server
-- Executar o script de criação
USE master;
CREATE DATABASE SistemaChamados;
```

### 2. Executar Scripts de Criação

```sql
-- Executar o arquivo: src/Database/CreateTables.sql
-- Este script criará:
-- - Tabelas (Funcionarios, Chamados, ChamadosAuditoria, Categorias)
-- - Índices para performance
-- - Constraints de integridade
-- - Triggers de auditoria
-- - Dados iniciais (usuário admin padrão)
```

### 3. Configurar String de Conexão

Edite o arquivo `App.config`:

```xml
<connectionStrings>
    <!-- Para SQL Server Express -->
    <add name="SistemaChamados" 
         connectionString="Server=.\SQLEXPRESS;Database=SistemaChamados;Integrated Security=true;" />
    
    <!-- Para SQL Server com usuário/senha -->
    <add name="SistemaChamados" 
         connectionString="Server=SEU_SERVIDOR;Database=SistemaChamados;User Id=SEU_USUARIO;Password=SUA_SENHA;" />
</connectionStrings>
```

### 4. Compilar e Executar

```bash
# No Visual Studio:
# 1. Abrir a solution
# 2. Build > Build Solution (Ctrl+Shift+B)
# 3. Debug > Start Debugging (F5)

# Ou via linha de comando:
msbuild SistemaChamados.sln /p:Configuration=Release
```

## ⚙️ Configuração

### Configurações Principais (App.config)

```xml
<appSettings>
    <!-- Segurança -->
    <add key="SessionTimeoutMinutes" value="30" />
    <add key="MaxLoginAttempts" value="3" />
    
    <!-- Logs -->
    <add key="LogPath" value="C:\Logs\SistemaChamados\" />
    <add key="EnableLogging" value="true" />
    
    <!-- Email (opcional) -->
    <add key="EnableEmailNotifications" value="false" />
    <add key="SmtpServer" value="smtp.gmail.com" />
</appSettings>
```

### Primeiro Acesso

**Usuário Administrador Padrão:**
- **Email:** `admin@sistema.com`
- **Senha:** `admin123`

⚠️ **IMPORTANTE:** Altere a senha padrão após o primeiro login!

## 📖 Uso

### 1. Login no Sistema
- Execute a aplicação
- Use as credenciais do administrador padrão
- O sistema detectará automaticamente o tipo de usuário

### 2. Funcionalidades por Perfil

#### 👨‍💼 Administrador (ADM)
- ✅ Visualizar todos os chamados
- ✅ Adicionar/remover funcionários/técnicos
- ✅ Alterar senhas de qualquer usuário
- ✅ Gerar relatórios completos
- ✅ Configurar categorias e prioridades

#### 🔧 Técnico
- ✅ Visualizar chamados atribuídos
- ✅ Marcar chamados como resolvidos
- ✅ Alterar prioridade de chamados
- ✅ Adicionar comentários/contestações
- ✅ Gerar relatórios completos

####  Funcionário Comum
- ✅ Criar novos chamados
- ✅ Visualizar status dos próprios chamados
- ✅ Adicionar comentários/contestações na criação
- ✅ Receber notificações por email (se configurado)

####  IA (Inteligência Artificial)
- ✅ Atribuir técnicos automaticamente com base na carga de trabalho
- ✅ Sugerir prioridades com base na descrição do chamado



### 3. Fluxo de Trabalho Típico

```
1. Funcionário cria chamado
2. IA atribui técnico
3. Técnico trabalha no chamado
4. Técnico marca como resolvido
5. Técnico fecha o chamado
```

---

## Equipe 👥
<a id="equipe"></a>

Função       | Nome                | Github                                                       |
------------ | --------------------| -------------------------------------------------------------|
Project Owner| Christian Fernandes | [Acessar Github](https://github.com/ChristianFernandesLemos) |
Scrum Master | Juan Vargas         | [Acessar Github](https://github.com/RenteriaJuan)            |
Dev Team     | Théo Pinto          | [Acessar Github](https://github.com/Thorphinm)               |
Dev Team     | Ana Beatriz         | [Acessar Github](https://github.com/Anasouza2802)            |
Dev Team     |Gustavo Gramacho     | [Acessar Github](https://github.com/gramachoo)               |
Dev Team     | Lukas Keiji         | [Acessar Github](https://github.com/Lucaskeiji)              |

---

## 🏃‍ DoR - Definition of Ready 
<a id="dor"></a>

* User Stories com **Critérios de Aceitação**
* Subtarefas divididas **a partir das US**
* Design no **Figma**
* Modelagem do **Banco de Dados**

## 🏆 DoD - Definition of Done
<a id="dod"></a>

* Manual de Usuário
* Manual da Aplicação
* Diagramas completos

---

# Manual de Usuario


