# Configurando uma Instância de Banco de Dados no Microsoft Azure

Este guia explica como criar e configurar um banco de dados SQL no Microsoft Azure.

## Pré-requisitos
- Conta ativa no Azure ([crie uma gratuitamente](https://azure.microsoft.com/free/))
- Acesso ao [Portal Azure](https://portal.azure.com)
- Permissões para criar recursos na assinatura

## Passo a Passo para Criação do Banco de Dados

### 1. Acessar o Portal Azure
1. Faça login no [Portal Azure](https://portal.azure.com)
2. Clique em "Criar um recurso" no menu esquerdo

### 2. Selecionar Banco de Dados SQL
1. Na página "Novo", pesquise por "Banco de Dados SQL"
2. Clique em "Criar"

### 3. Configurar Básicos
Preencha as informações básicas:
- **Assinatura**: Selecione sua assinatura
- **Grupo de recursos**: Crie um novo ou selecione existente
- **Nome do banco de dados**: (ex: db-app-prod-01)
- **Servidor**: Crie um novo servidor lógico
  - Nome do servidor (ex: sql-server-demo)
  - Localização: Selecione a região mais próxima
  - Método de autenticação: Use autenticação SQL
  - Credenciais do administrador (login e senha)

### 4. Configurar Opções Adicionais
Na aba "Rede":
- **Método de conectividade**: Ponto de extremidade público ou privado
- **Permitir serviços e recursos do Azure acessarem este servidor**: Sim
- **Adicionar endereço IP atual**: Sim (para acesso local)

Na aba "Configurações adicionais":
- **Usar dados existentes**: Nenhum (ou backup se aplicável)
- **Conjunto de bancos de dados elásticos**: Opcional

### 5. Selecionar Tipo e Tamanho
- **Tipo de computação**: Provisionado ou sem servidor
- **Camada de serviço**: Básico, Standard, Premium ou Hiperescala
- **Tamanho da computação**: Selecione conforme necessidade (ex: Gen5, 2 vCores)

### 6. Revisar e Criar
1. Revise todas as configurações
2. Clique em "Criar" para iniciar a implantação

## Conectando ao Banco de Dados

### Via SQL Server Management Studio (SSMS)
1. Baixe e instale o [SSMS](https://docs.microsoft.com/sql/ssms/download-sql-server-management-studio-ssms)
2. Use as credenciais do servidor:
   - Nome do servidor: `sql-server-demo.database.windows.net`
   - Autenticação: SQL Server Authentication
   - Login e senha configurados anteriormente

### Via Azure Data Studio
1. Instale o [Azure Data Studio](https://docs.microsoft.com/sql/azure-data-studio/download-azure-data-studio)
2. Adicione uma nova conexão com os detalhes do servidor

## Gerenciamento Básico

### Monitoramento
- **Métricas**: Acesse a seção "Monitoramento" para ver desempenho
- **Consultas caras**: Use o Query Performance Insight

### Manutenção
- **Backups automáticos**: Configurados por padrão (PITR - Point in Time Restore)
- **Exportar banco de dados**: Crie um arquivo BACPAC para backup

### Segurança
- **Firewall**: Gerencie regras na seção "Firewalls e redes virtuais"
- **Auditoria**: Habilite na seção "Auditoria"
- **Criptografia**: Transparent Data Encryption (TDE) ativado por padrão

## Boas Práticas
✔️ Use sempre a menor camada necessária para economizar custos  
✔️ Configure alertas para monitorar uso de recursos  
✔️ Habilite a auditoria para requisitos de compliance  
✔️ Considere pools elásticos para múltiplos bancos com padrão de uso variável  

## Limpeza de Recursos
Para evitar cobranças indesejadas:
1. Vá para o Grupo de Recursos
2. Selecione o servidor SQL e o banco de dados
3. Clique em "Excluir" e confirme

## Suporte e Ajuda
- [Documentação Oficial do Azure SQL](https://docs.microsoft.com/azure/azure-sql/)
- [Fórum de Suporte Azure](https://azure.microsoft.com/support/forums/)
- [Calculadora de Custos Azure SQL](https://azure.microsoft.com/pricing/calculator/)
- [Boas Práticas de Segurança](https://docs.microsoft.com/azure/azure-sql/database/security-best-practice)
