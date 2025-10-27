## 📋 Índice

- [Instalação](#instalação)
- [Configuração](#configuração)
- [Uso](#uso)


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
