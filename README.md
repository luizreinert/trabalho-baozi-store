# Baozi Store — API REST

API REST desenvolvida em Java com Spring Boot para gerenciamento de clientes, produtos e pedidos de uma loja fictícia especializada em pãezinhos chineses.

## Tecnologias utilizadas

- Java 21
- Spring Boot 3.5.6
- Spring Data JPA
- MySQL
- Maven
- JSON

## Funcionalidades

A API permite cadastrar, consultar e excluir clientes, produtos e pedidos.

| Método HTTP | Endpoint | Descrição |
|---|---|---|
| POST | `/clientes` | Cadastrar cliente |
| GET | `/clientes` | Listar clientes |
| GET | `/clientes/{id}` | Buscar cliente por ID |
| DELETE | `/clientes/{id}` | Excluir cliente |
| POST | `/produtos` | Cadastrar produto |
| GET | `/produtos` | Listar produtos |
| GET | `/produtos/{id}` | Buscar produto por ID |
| DELETE | `/produtos/{id}` | Excluir produto |
| POST | `/pedidos` | Cadastrar pedido |
| GET | `/pedidos` | Listar pedidos |
| GET | `/pedidos/{id}` | Buscar pedido por ID |
| DELETE | `/pedidos/{id}` | Excluir pedido |

## Modelo de dados

**Cliente**
- `id`: identificador do cliente
- `nome`: nome do cliente
- `clienteDesde`: data de cadastro

**Produto**
- `id`: identificador do produto
- `nome`: nome do produto
- `preco`: preço do produto
- `estoque`: disponibilidade em estoque

**Pedido**
- `id`: identificador do pedido
- `clienteId`: identificador do cliente
- `produtoId`: identificador do produto
- `quantidade`: quantidade de unidades solicitadas

## Como executar o projeto

### Pré-requisitos

- Java 21
- MySQL
- Git

### 1. Clone o repositório

```bash
git clone https://github.com/luizreinert/trabalho-baozi-store.git
cd trabalho-baozi-store
```

### 2. Configure o banco de dados

Crie um banco de dados MySQL chamado `baozi_store`:

```sql
CREATE DATABASE baozi_store;
```

Configure as variáveis de ambiente no terminal PowerShell, informando o usuário e a senha do seu MySQL:

```powershell
$env:DB_USERNAME="root"
$env:DB_PASSWORD="sua_senha"
```

Não compartilhe sua senha nem a inclua no repositório.

### 3. Execute a aplicação

No Windows, execute:

```powershell
.\mvnw.cmd spring-boot:run
```

A aplicação será iniciada na porta `8080`.

## Exemplo de requisição

Para cadastrar um produto, envie uma requisição `POST` para `http://localhost:8080/produtos`, com o corpo JSON:

```json
{
  "nome": "Baozi Tradicional",
  "preco": 8.50,
  "estoque": true
}
```

## Autor

Luiz Henrique Reinert

Projeto acadêmico desenvolvido para a disciplina de Desenvolvimento Web Back-End — UNINTER.
