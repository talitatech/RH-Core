# 🧑‍💼 RH Core - Sistema de Cadastro de Funcionários

[![Java](https://img.shields.io/badge/Java-17+-red.svg)](https://www.oracle.com/java/technologies/javase-downloads.html)
[![Spring Boot](https://img.shields.io/badge/Spring%20Boot-2.7.x-brightgreen)](https://spring.io/projects/spring-boot)
[![MySQL](https://img.shields.io/badge/MySQL-8.0-blue.svg)](https://www.mysql.com/)
[![Maven](https://img.shields.io/badge/Maven-3.8+-blue.svg)](https://maven.apache.org/)
[![License](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![GitHub Repository](https://img.shields.io/badge/GitHub-Projeto--RH-181717?logo=github)](https://github.com/Projeto-Integrador-Gen-Grupo1/Projeto-RH)

## 📋 Sobre o Projeto

**RH Core** é um sistema backend desenvolvido para gerenciamento de funcionários e processos básicos de Recursos Humanos de uma empresa.

O projeto tem como principal objetivo permitir o **cadastro, consulta, atualização e remoção de informações de funcionários** através de uma API REST construída com **Java e Spring Boot**, aplicando o conceito de **CRUD completo**.

A aplicação foi criada com foco no aprendizado e aplicação prática de tecnologias modernas de desenvolvimento backend, utilizando arquitetura organizada em camadas, persistência de dados com banco relacional e boas práticas de programação.

> 📄 **Documentação Completa do Projeto**  
> Acesse a documentação detalhada do sistema (prototipação das classes, DER, diagramas, escopo do projeto) em PDF:  
> **[🔗 Clique aqui para baixar o PDF da Documentação](https://drive.google.com/file/d/1FdptVatAptM-iVIvtUIL8Q2yh9dNwOUi/view?usp=sharing)**

> 💻 **Código-Fonte do Projeto**  
> Acesse o repositório original no GitHub:  
> **[🔗 github.com/Projeto-Integrador-Gen-Grupo1/Projeto-RH](https://github.com/Projeto-Integrador-Gen-Grupo1/Projeto-RH)**

## 🎯 Funcionalidades Principais (CRUD)

| Operação | Funcionalidade | Endpoint |
|----------|----------------|----------|
| **CREATE** | Cadastrar novo funcionário | `POST /funcionarios` |
| **READ** | Listar todos os funcionários | `GET /funcionarios` |
| **READ** | Buscar funcionário por ID | `GET /funcionarios/{id}` |
| **UPDATE** | Atualizar dados de um funcionário | `PUT /funcionarios` |
| **DELETE** | Remover um funcionário | `DELETE /funcionarios/{id}` |

## 🏗️ Modelo de Negócio

**Sistema de Recursos Humanos (RH)** - Gestão de colaboradores da empresa.

### Entidade: `Funcionario`

A entidade `Funcionario` representa os colaboradores cadastrados no sistema RH Core, armazenando as seguintes informações:

| Atributo | Tipo | Descrição |
|----------|------|------------|
| `id` | Long | Identificador único do funcionário |
| `nome` | String | Nome completo do funcionário |
| `cargo` | String | Cargo ocupado pelo funcionário |
| `departamento` | String | Departamento da empresa |
| `salario` | BigDecimal | Salário do funcionário |
| `data` | LocalDateTime | Data de atualização do cadastro |

### Diagrama de Classe - Model `Funcionario`

```
┌─────────────────────────────────┐
│         Funcionario             │
├─────────────────────────────────┤
│ - id: Long                      │
│ - nome: String                  │
│ - cargo: String                 │
│ - departamento: String          │
│ - salario: BigDecimal           │
│ - data: LocalDateTime           │
├─────────────────────────────────┤
│ + getId(): Long                 │
│ + getNome(): String             │
│ + getCargo(): String            │
│ + getDepartamento(): String     │
│ + getSalario(): BigDecimal      │
│ + getData(): LocalDateTime      │
│ + setters...                    │
└─────────────────────────────────┘
```

## 🚀 Tecnologias Utilizadas

### Backend
- **Java 17** - Linguagem de programação
- **Spring Boot** - Framework para construção da API REST
- **Spring Data JPA** - Persistência de dados
- **Hibernate** - Mapeamento objeto-relacional (ORM)
- **Maven** - Gerenciador de dependências e build

### Banco de Dados
- **MySQL 8.0** - Banco de dados relacional

### Ferramentas
- **Spring Tool Suite (STS)** - IDE para desenvolvimento
- **Postman** - Testes de requisições HTTP
- **Git & GitHub** - Versionamento de código

## 🛠️ Como Executar o Projeto

### Pré-requisitos

- JDK 17 ou superior instalado
- MySQL 8.0 instalado e rodando
- Maven (ou use o wrapper `./mvnw`)
- Postman (opcional, para testar a API)

### Passos

1. **Clone o repositório**
   ```bash
   git clone https://github.com/Projeto-Integrador-Gen-Grupo1/Projeto-RH.git
   cd Projeto-RH
   ```

2. **Configure o banco de dados MySQL**  
   Crie um banco de dados chamado `rh_db`:
   ```sql
   CREATE DATABASE rh_db;
   ```

3. **Configure o `application.properties`**  
   Edite o arquivo `src/main/resources/application.properties`:
   ```properties
   spring.datasource.url=jdbc:mysql://localhost:3306/rh_db
   spring.datasource.username=root
   spring.datasource.password=sua_senha
   spring.datasource.driver-class-name=com.mysql.cj.jdbc.Driver
   
   spring.jpa.hibernate.ddl-auto=update
   spring.jpa.show-sql=true
   spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.MySQL8Dialect
   ```

4. **Execute a aplicação**
   ```bash
   ./mvnw spring-boot:run    # Linux/Mac
   mvnw.cmd spring-boot:run  # Windows
   ```

5. **Acesse a API**  
   A aplicação estará disponível em `http://localhost:8080`

## 📚 Exemplos de Requisições (Postman)

### ➕ Criar um Funcionário (POST)
**Endpoint:** `POST http://localhost:8080/funcionarios`

**Body (JSON):**
```json
{
  "nome": "Ana Karoline Costa De Sousa",
  "cargo": "Desenvolvedora Backend",
  "departamento": "Tecnologia",
  "salario": 6500.00
}
```

### 📋 Listar Todos os Funcionários (GET)
**Endpoint:** `GET http://localhost:8080/funcionarios`

### 🔍 Buscar Funcionário por ID (GET)
**Endpoint:** `GET http://localhost:8080/funcionarios/1`

### ✏️ Atualizar Funcionário (PUT)
**Endpoint:** `PUT http://localhost:8080/funcionarios`

**Body (JSON):**
```json
{
  "id": 1,
  "nome": "Ana Karoline Costa De Sousa",
  "cargo": "Tech Lead",
  "departamento": "Tecnologia",
  "salario": 8500.00
}
```

### ❌ Deletar Funcionário (DELETE)
**Endpoint:** `DELETE http://localhost:8080/funcionarios/1`

## 📚 Recursos e Links Úteis

| Recurso | Link |
|---------|------|
| 📄 **Documentação do Projeto (PDF)** | [Clique aqui para baixar](https://drive.google.com/file/d/1FdptVatAptM-iVIvtUIL8Q2yh9dNwOUi/view?usp=sharing) |
| 💻 **Repositório no GitHub** | [github.com/Projeto-Integrador-Gen-Grupo1/Projeto-RH](https://github.com/Projeto-Integrador-Gen-Grupo1/Projeto-RH) |
| 🧪 **Testar API no Postman** | Importe a coleção do repositório (se disponível) |

## 📂 Estrutura do Projeto

```
Projeto-RH/
├── src/
│   ├── main/
│   │   ├── java/com/example/rh/
│   │   │   ├── controller/
│   │   │   │   └── FuncionarioController.java
│   │   │   ├── model/
│   │   │   │   └── Funcionario.java
│   │   │   ├── repository/
│   │   │   │   └── FuncionarioRepository.java
│   │   │   ├── service/
│   │   │   │   └── FuncionarioService.java
│   │   │   └── RhCoreApplication.java
│   │   └── resources/
│   │       ├── application.properties
│   │       └── data.sql (se houver dados iniciais)
│   └── test/                 # Testes unitários
├── pom.xml                   # Dependências Maven
└── README.md
```

## 👥 Equipe de Desenvolvimento - Grupo 01

| Membro | GitHub |
|--------|--------|
| Ana Karoline Costa De Sousa | [@anakaroline](https://github.com/anakaroline) |
| Danielle Karen Mendes Caricati | [@daniellekaren](https://github.com/daniellekaren) |
| Felipe Marques | [@felipemarques](https://github.com/felipemarques) |
| Paulo Gustavo Pereira de Souza Brito | [@Paulogsbrito](https://github.com/Paulogsbrito) |
| Riane Toscano | [@rianetoscano](https://github.com/rianetoscano) |
| Talita Oliveira Santos | [@talitaoliveira](https://github.com/talitaoliveira) |

## 🎯 Objetivos de Aprendizagem Aplicados

O projeto RH Core permitiu desenvolver competências essenciais no ecossistema Java/Spring, incluindo:

- ✅ Desenvolvimento de APIs REST
- ✅ Modelagem de entidades
- ✅ Integração com banco de dados
- ✅ Persistência de dados com JPA/Hibernate
- ✅ Organização de arquitetura backend
- ✅ Validações de dados
- ✅ Versionamento com Git e GitHub

## 🔮 Visão do Projeto

O **RH Core** foi idealizado como uma base sólida para futuras expansões, podendo evoluir futuramente para funcionalidades mais avançadas, como:

- Autenticação de usuários
- Controle de permissões
- Gerenciamento de departamentos e cargos
- Folha de pagamento
- Relatórios administrativos

## 📄 Licença

Este projeto está sob a licença MIT. Consulte o arquivo [LICENSE](LICENSE) para mais informações.

---

**Status do Projeto:** ✅ Concluído  
**Data de Entrega:** Maio/2026  
**Instituição:** Generation Brasil

**🔗 Links Rápidos:** 
- [Documentação PDF](https://drive.google.com/file/d/1FdptVatAptM-iVIvtUIL8Q2yh9dNwOUi/view?usp=sharing) 
- [Repositório GitHub](https://github.com/Projeto-Integrador-Gen-Grupo1/Projeto-RH)
```

