# 🐾 PetShop API

Sistema desenvolvido para gerenciamento de um PetShop, permitindo o controle de categorias, produtos, usuários e pedidos através de uma API REST utilizando Spring Boot.

---

# 📌 1. Apresentação do Projeto

## Nome do Projeto

**PetShop API**

## Objetivo do Sistema

Desenvolver uma aplicação backend para gerenciamento de um PetShop, permitindo o cadastro e gerenciamento de produtos, categorias, usuários e pedidos de forma organizada e escalável.

## Funcionalidades Disponíveis

* Cadastro de categorias;
* Cadastro de produtos;
* Upload e exibição de imagens dos produtos;
* Cadastro e gerenciamento de usuários;
* Login de usuários;
* Recuperação e redefinição de senha por e-mail;
* Gerenciamento de pedidos;
* Adição e remoção de itens do pedido;
* Finalização e cancelamento de pedidos;
* Busca de produtos por categoria;
* Pesquisa de produtos.

---

# 🛠️ 2. Tecnologias Utilizadas

## Backend

* Java 21
* Spring Boot 4
* Spring Web MVC
* Spring Data JPA
* Spring Security
* Spring Mail
* SpringDoc OpenAPI (Swagger)

## Banco de Dados

* MySQL
* PostgreSQL (dependência disponível)

## Gerenciamento

* Maven

## Ferramentas

* VS Code
* Eclipse
* Git / GitHub

---

# 📂 3. Estrutura do Projeto

```bash
petshop/
│
├── src/
│   ├── main/
│   │   ├── java/
│   │   │
│   │   ├── controllers/
│   │   │   ├── CategoriaController
│   │   │   ├── ProdutoController
│   │   │   ├── UsuarioController
│   │   │   ├── PedidoController
│   │   │   └── ItensPedidoController
│   │   │
│   │   ├── services/
│   │   │   └── Regras de negócio
│   │   │
│   │   ├── repositories/
│   │   │   └── Comunicação com banco
│   │   │
│   │   ├── entities/
│   │   │   └── Modelos das tabelas
│   │   │
│   │   └── resources/
│   │       └── application.properties
│
└── pom.xml
```

### Camadas

### Controller

Responsável por receber requisições HTTP.

### Service

Contém regras de negócio.

### Repository

Responsável pelo acesso ao banco.

### Entity

Representa as tabelas do banco.

---

# 🗄️ 4. Banco de Dados

## Nome do Banco

```sql
petshop_db
```

## Principais Tabelas

### categoria

Armazena categorias dos produtos.

### produto

Armazena produtos disponíveis.

### usuario

Armazena dados dos usuários.

### pedidos

Armazena pedidos realizados.

### itens_pedido

Armazena produtos vinculados aos pedidos.

## Relacionamentos

```text
Usuario
   │
   └── 1:N
       Pedido
          │
          └── 1:N
              ItensPedido
                  │
                  └── N:1
                      Produto

Categoria
   │
   └── 1:N
       Produto
```

### Arquivo SQL

O projeto possui o arquivo:

```bash
petshop_db.sql
```

Importe esse arquivo para criar o banco automaticamente.

---

# ▶️ 5. Como Executar o Projeto

## 1. Clonar o Repositório

```bash
git clone https://github.com/seuusuario/petshop.git
```

---

## 2. Entrar na Pasta

```bash
cd petshop
```

---

## 3. Criar Banco de Dados

No MySQL:

```sql
CREATE DATABASE petshop_db;
```

Importar:

```bash
petshop_db.sql
```

---

## 4. Configurar application.properties

Editar:

```properties
spring.datasource.url=jdbc:mysql://localhost:3306/petshop_db
spring.datasource.username=root
spring.datasource.password=

spring.jpa.hibernate.ddl-auto=none
spring.jpa.show-sql=true
```

Configurar e-mail:

```properties
spring.mail.username=SEU_EMAIL
spring.mail.password=SUA_SENHA
```

---

## 5. Executar Projeto

Via Maven:

```bash
mvn spring-boot:run
```

Ou executar:

```text
PetshopApplication.java
```

Servidor:

```bash
http://localhost:8080
```

---

# 🌐 6. Endpoints da API

## Categorias

| Método | Endpoint             | Função            |
| ------ | -------------------- | ----------------- |
| GET    | /api/categorias      | Listar categorias |
| GET    | /api/categorias/{id} | Buscar categoria  |
| POST   | /api/categorias      | Criar categoria   |
| PUT    | /api/categorias/{id} | Atualizar         |
| DELETE | /api/categorias/{id} | Remover           |

---

## Produtos

| Método | Endpoint                              |
| ------ | ------------------------------------- |
| GET    | /api/produtos                         |
| POST   | /api/produtos                         |
| GET    | /api/produtos/{id}                    |
| DELETE | /api/produtos/{id}                    |
| PUT    | /api/produtos/{id}                    |
| GET    | /api/produtos/categoria/{idCategoria} |
| GET    | /api/produtos/buscar                  |
| GET    | /api/produtos/{id}/imagem             |

---

## Usuários

| Método | Endpoint                        |
| ------ | ------------------------------- |
| POST   | /usuarios                       |
| GET    | /usuarios                       |
| GET    | /usuarios/{id}                  |
| PUT    | /usuarios/{id}                  |
| DELETE | /usuarios/{id}                  |
| POST   | /usuarios/login                 |
| POST   | /usuarios/solicitar-recuperacao |
| POST   | /usuarios/redefinir-senha       |

---

## Pedidos

| Método | Endpoint                          |
| ------ | --------------------------------- |
| GET    | /api/pedidos/carrinho/{usuarioId} |
| PUT    | /api/pedidos/finalizar/{idPedido} |
| GET    | /api/pedidos/usuario/{idUsuario}  |
| PUT    | /api/pedidos/{idPedido}/cancelar  |

---

## Itens do Pedido

| Método | Endpoint                                           |
| ------ | -------------------------------------------------- |
| POST   | /api/itens-pedido/adicionar                        |
| GET    | /api/itens-pedido/pedido/{idPedido}                |
| DELETE | /api/itens-pedido/{idItemPedido}/pedido/{idPedido} |

---

# ✅ 7. Funcionalidades Implementadas

* Sistema de categorias;
* Cadastro de produtos;
* Upload de imagens;
* Gerenciamento de usuários;
* Login;
* Recuperação de senha;
* Carrinho de compras;
* Controle de pedidos;
* Finalização de pedidos;
* Cancelamento de pedidos;
* Pesquisa de produtos;
* Integração com banco de dados;
* Documentação via Swagger.

---

# 👨‍💻 8. Integrantes da Equipe / Desenvolvedor

**Nome Completo:**
[SUBSTITUIR PELO SEU NOME]

---

# 📄 Licença

Projeto desenvolvido para fins acadêmicos e educacionais.
