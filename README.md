# CRUD-SpringBoot

API REST completa de **CRUD de Produtos** desenvolvida com **Spring Boot**, **Spring Data JPA** e **MySQL**.

O projeto permite criar, listar, buscar, atualizar e deletar produtos, além de salvar uma lista de produtos de uma só vez.

---

## Tecnologias utilizadas

- **Java 22**
- **Spring Boot 4.1.2**
- **Spring Web**
- **Spring Data JPA**
- **Hibernate**
- **MySQL**
- **Maven**
- **Bean Validation** (`@NotEmpty`)
- **Spring Boot DevTools**

---

## Funcionalidades da API

| Método   | Endpoint                  | Descrição                          |
|----------|---------------------------|------------------------------------|
| `GET`    | `/produtos`               | Lista todos os produtos            |
| `GET`    | `/produtos/{id}`          | Busca um produto pelo ID           |
| `POST`   | `/produtos`               | Cadastra um novo produto           |
| `PUT`    | `/produtos/{id}`          | Atualiza um produto existente      |
| `DELETE` | `/produtos/{id}`          | Remove um produto                  |
| `POST`   | `/produtos/salvarLista`   | Salva uma lista de produtos        |

---

## Modelo de Dados (Produto)

| Campo        | Tipo     | Descrição                       |
|--------------|----------|---------------------------------|
| `id`         | Long     | Identificador (gerado automaticamente) |
| `nome`       | String   | Nome do produto (obrigatório)   |
| `quantidade` | int      | Quantidade em estoque           |
| `preco`      | double   | Preço do produto                |
| `status`     | String   | Status do produto               |

---

## Estrutura do Projeto
src/main/java/com/produtoapi/
├── controller/
│ └── ProdutoController.java
├── model/
│ └── Produto.java
├── repository/
│ └── ProdutoRepository.java
├── service/
│ └── ProdutoService.java
├── client/
│ └── crud.html
└── ProjetoSpringApplication.java

Texto

---

## Configuração do Banco de Dados

Arquivo: `src/main/resources/application.properties`

```properties
spring.datasource.url=jdbc:mysql://localhost:3306/lojaProdutos?useSSL=false&allowPublicKeyRetrieval=true
spring.datasource.username=root
spring.datasource.password=sua_senha_aqui
spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
Importante:

Crie o banco de dados lojaProdutos no MySQL antes de rodar a aplicação.
Nunca deixe a senha real no repositório público.
Como executar o projeto
Pré-requisitos
Java 22
Maven
MySQL rodando
Passos
Clone o repositório:
Bash
git clone https://github.com/g-ssouza/CRUD-SpringBoot.git
cd CRUD-SpringBoot
Configure as credenciais do MySQL no arquivo application.properties.

Execute a aplicação:

Bash
./mvnw spring-boot:run
A API estará disponível em:
[localhost/produtos](http://localhost:8080/produtos)

Exemplos de Requisições
Cadastrar um produto
Http
POST /produtos
Content-Type: application/json

{
  "nome": "Notebook Dell",
  "quantidade": 10,
  "preco": 3499.90,
  "status": "Disponível"
}
Listar todos os produtos
Http
GET /produtos
Buscar por ID
Http
GET /produtos/1
Atualizar produto
Http
PUT /produtos/1
Content-Type: application/json

{
  "nome": "Notebook Dell Atualizado",
  "quantidade": 8,
  "preco": 3299.90,
  "status": "Disponível"
}
Deletar produto
Http
DELETE /produtos/1
Salvar lista de produtos
Http
POST /produtos/salvarLista
Content-Type: application/json

[
  {
    "nome": "Mouse Gamer",
    "quantidade": 25,
    "preco": 149.90,
    "status": "Disponível"
  },
  {
    "nome": "Teclado Mecânico",
    "quantidade": 15,
    "preco": 299.90,
    "status": "Disponível"
  }
]
Interface HTML (Client)
Existe um arquivo HTML simples em:

Texto
src/main/java/com/produtoapi/client/crud.html
Você pode abri-lo no navegador para testar o CRUD de forma visual (com a API rodando).

Autor
Desenvolvido por Gustavo Souza
