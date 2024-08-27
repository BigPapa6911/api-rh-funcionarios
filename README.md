# api-rh-funcionarios
Este projeto é uma API Web ASP.NET Core que gerencia funcionários e grava logs das operações realizadas em uma tabela do Azure Table Storage.

#Funcionalidades
Obter Funcionário por ID: Recupera um funcionário do banco de dados SQL com base no ID fornecido.
Criar Funcionário: Adiciona um novo funcionário ao banco de dados SQL e registra a inclusão na tabela do Azure Table Storage.
Atualizar Funcionário: Atualiza os dados de um funcionário existente no banco de dados SQL e registra a atualização na tabela do Azure Table Storage.
Deletar Funcionário: Remove um funcionário do banco de dados SQL e registra a remoção na tabela do Azure Table Storage.
Detalhes da Implementação
Controller: FuncionarioController
Dependências:
RHContext para interagir com o banco de dados SQL.
Configuração de conexão com o Azure Table Storage através de IConfiguration.
Endpoints:
GET /funcionario/{id}: Obtém um funcionário pelo ID.
POST /funcionario: Cria um novo funcionário e registra o log de inclusão.
PUT /funcionario/{id}: Atualiza um funcionário existente e registra o log de atualização.
DELETE /funcionario/{id}: Remove um funcionário e registra o log de remoção.

Azure Table Storage
Tabela: FuncionarioLog
Armazenamento: Logs das operações realizadas sobre os funcionários, incluindo inserções, atualizações e remoções.

Configuração
Connection String: A string de conexão para o Azure Table Storage é configurada no arquivo de configuração (appsettings.json) sob a chave ConnectionStrings:SAConnectionString.
Nome da Tabela: O nome da tabela Azure é configurado sob a chave ConnectionStrings:AzureTableName.

Exemplo de Uso

Criar Funcionário:

POST /funcionario
Content-Type: application/json

{
    "Nome": "João Silva",
    "Endereco": "Rua Exemplo, 123",
    "Ramal": "1234",
    "EmailProfissional": "joao.silva@exemplo.com",
    "Departamento": "TI",
    "Salario": 5000.00,
    "DataAdmissao": "2024-08-01T00:00:00Z"
}

Atualizar Funcionário:

Copiar código
PUT /funcionario/{id}
Content-Type: application/json

{
    "Nome": "João Silva",
    "Endereco": "Rua Exemplo, 456",
    "Ramal": "5678",
    "EmailProfissional": "joao.silva@exemplo.com",
    "Departamento": "TI",
    "Salario": 5500.00,
    "DataAdmissao": "2024-08-01T00:00:00Z"
}
Deletar Funcionário:

DELETE /funcionario/{id}

Requisitos
.NET 6.0 ou superior
Biblioteca Azure.Data.Tables para interagir com o Azure Table Storage

Contribuições
Contribuições são bem-vindas! Para colaborar, faça um fork do repositório, crie uma branch com suas alterações e envie um pull request.

