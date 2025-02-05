
# Exemplo de API Locadora

Este projeto é um **exemplo básico** de uma API para gerenciar filmes em uma locadora, utilizando **ASP.NET Core**, **Entity Framework Core** e **PostgreSQL**. Ele serve como um exemplo simples para se basear ao criar uma API do zero. As funcionalidades básicas de CRUD (Criar, Ler, Atualizar e Deletar) estão implementadas para manipulação de filmes.

**Este projeto é apenas um exemplo simples e básico** e pode ser expandido ou adaptado conforme necessário para projetos mais complexos.

## Requisitos

- .NET 6 ou superior
- PostgreSQL ou outro banco de dados relacional configurado
- Entity Framework Core

## Como Executar

### 1. Clonar o Repositório

Clone o repositório para a sua máquina local:

```bash
git clone https://github.com/seu-usuario/exemplo-api-locadora.git
cd exemplo-api-locadora
```

### 2. Configurar a String de Conexão

No arquivo `appsettings.json`, adicione a string de conexão para o banco de dados PostgreSQL:

```json
{
  "ConnectionStrings": {
    "DefaultConnection": "Host=localhost;Port=5432;Database=locadora;Username=seu_usuario;Password=sua_senha"
  }
}
```

Substitua `seu_usuario` e `sua_senha` com suas credenciais do PostgreSQL.

### 3. Instalar Pacotes NuGet

Instale os pacotes NuGet necessários:

```bash
dotnet restore
```

Os pacotes necessários incluem:

- `Microsoft.EntityFrameworkCore`
- `Microsoft.EntityFrameworkCore.Design`
- `Npgsql.EntityFrameworkCore.PostgreSQL`

### 4. Aplicar as Migrations

Crie as migrations e atualize o banco de dados:

```bash
dotnet ef migrations add Inicial
dotnet ef database update
```

### 5. Executar a API

Para rodar o servidor da API, use o comando:

```bash
dotnet run
```

A API estará disponível em `http://localhost:5000`.

## Funcionalidades

A API oferece os seguintes endpoints:

### `GET /api/filmes`
Retorna todos os filmes ativos.

### `GET /api/filmes/{id}`
Retorna um filme específico pelo `id`.

### `POST /api/filmes`
Cria um novo filme. Exemplo de corpo da requisição:

```json
{
  "titulo": "Filme Exemplo",
  "genero": "Ação",
  "ano": 2025
}
```

### `PUT /api/filmes/{id}`
Atualiza um filme existente.

### `DELETE /api/filmes/{id}`
Desativa um filme.

## Documentação Swagger

A documentação interativa da API está disponível via Swagger. Quando rodando a API localmente, acesse:

```
http://localhost:5000/swagger
```

## Estrutura do Projeto

- **Exemplo_Api_Locadora**: Projeto principal que contém a implementação dos serviços e controladores.
- **Data**: Contém o contexto do banco de dados e as migrations.
- **Services**: Implementação da lógica de negócios, como manipulação de filmes.
- **Interface**: Contém as interfaces usadas nos serviços, como `IFilmeService`.
