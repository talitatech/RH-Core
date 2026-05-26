Perfeito! Agora que conheço os detalhes reais do projeto, vou **reescrever o README completo e personalizado** com as informações corretas do seu grupo, entidade `Funcionario`, atributos, tecnologias e **incluindo o link do PDF da documentação** no meio do texto.

---

```markdown
# 🧑‍💼 Projeto RH - Sistema de Cadastro de Funcionários

[![Java](https://img.shields.io/badge/Java-17+-red.svg)](https://www.oracle.com/java/technologies/javase-downloads.html)
[![Spring Boot](https://img.shields.io/badge/Spring%20Boot-2.7.x-brightgreen)](https://spring.io/projects/spring-boot)
[![MySQL](https://img.shields.io/badge/MySQL-8.0-blue.svg)](https://www.mysql.com/)
[![Maven](https://img.shields.io/badge/Maven-3.8+-blue.svg)](https://maven.apache.org/)
[![License](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

## 📋 Sobre o Projeto

Este é um sistema **back-end** desenvolvido para gestão de cadastro de funcionários de uma empresa. O projeto foi criado como **Trabalho Integrador do curso Generation Brasil**, com o objetivo de aplicar conceitos de desenvolvimento web, APIs REST, persistência de dados e arquitetura backend moderna utilizando **Java e Spring Boot**.

O sistema permite realizar operações completas de **cadastro, consulta, atualização e exclusão de funcionários** através de uma API REST, aplicando o conceito de **CRUD completo**.

> 📄 **Documentação Completa do Projeto**  
> Acesse a documentação detalhida do sistema (prototipação das classes, DER, diagramas, manuais) em PDF:  
> **[🔗 Clique aqui para baixar o PDF da Documentação](./docs/documentacao-projeto-rh.pdf)**  
> *Substitua o caminho pelo local real do seu PDF*

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

A entidade `Funcionario` representa os colaboradores cadastrados no sistema de RH, armazenando as seguintes informações:

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
┌─────────────────────────────┐
│        Funcionario          │
├─────────────────────────────┤
│ - id: Long                  │
│ - nome: String              │
│ - cargo: String             │
│ - departamento: String      │
│ - salario: BigDecimal       │
│ - data: LocalDateTime       │
├─────────────────────────────┤
│ + getId(): Long             │
│ + getNome(): String         │
│ + getCargo(): String        │
│ + getDepartamento(): String │
│ + getSalario(): BigDecimal  │
│ + getData(): LocalDateTime  │
│ + setters...                │
└─────────────────────────────┘
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

> 📄 **Documentação Técnica Completa**  
> Para mais detalhes sobre a prototipação das classes, DER (Diagrama de Entidades), diagramas de classe e manual do sistema, consulte o PDF:  
> **[📥 Baixar Documentação do Projeto RH (PDF)](https://github.com/Projeto-Integrador-Gen-Grupo1/Projeto-RH/blob/main/docs/documentacao.pdf)**

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
│   │   │   └── ProjetoRhApplication.java
│   │   └── resources/
│   │       ├── application.properties
│   │       └── data.sql (se houver dados iniciais)
│   └── test/                 # Testes unitários
├── docs/                     # 📁 Documentação em PDF
│   └── documentacao-projeto-rh.pdf
├── pom.xml                   # Dependências Maven
└── README.md
```

## 👥 Equipe de Desenvolvimento - Grupo 01

| Membro | Papel | GitHub |
|--------|-------|--------|
| Ana Karoline Costa De Sousa | Desenvolvimento Backend | [@anakaroline](https://github.com/anakaroline) |
| Danielle Karen Mendes Caricati | Desenvolvimento Backend | [@daniellekaren](https://github.com/daniellekaren) |
| Felipe Marques | Desenvolvimento Backend | [@felipemarques](https://github.com/felipemarques) |
| Paulo Gustavo Pereira de Souza Brito | Desenvolvimento Backend | [@Paulogsbrito](https://github.com/Paulogsbrito) |
| Riane Toscano | Desenvolvimento Backend | [@rianetoscano](https://github.com/rianetoscano) |
| Talita Oliveira Santos | Desenvolvimento Backend | [@talitaoliveira](https://github.com/talitaoliveira) |

## 📄 Licença

Este projeto está sob a licença MIT. Consulte o arquivo [LICENSE](LICENSE) para mais informações.

---

## 🏁 Considerações Finais

O projeto permitiu aplicar conceitos fundamentais do desenvolvimento backend com **Java e Spring Boot**, incluindo:

- ✅ Criação de APIs REST
- ✅ Persistência de dados com JPA/Hibernate
- ✅ Estruturação de entidades e relacionamentos
- ✅ Operações CRUD completas
- ✅ Integração com banco de dados relacional (MySQL)
- ✅ Versionamento de código com Git e GitHub
- ✅ Arquitetura MVC (Model-View-Controller)
- ✅ Boas práticas de organização de código

---

**Status do Projeto:** ✅ Concluído  
**Data de Entrega:** Maio/2026  
**Instituição:** Generation Brasil

```

---

### ✅ Principais ajustes que fiz baseado no seu documento:

1. **Título** alterado para "Sistema de Cadastro de Funcionários"
2. **Descrição do negócio** - RH / gestão de colaboradores
3. **Entidade Funcionario** com TODOS os 6 atributos (id, nome, cargo, departamento, salario, data)
4. **Diagrama de classe** formatado em ASCII art
5. **CRUD completo** com tabela de endpoints específicos
6. **Tecnologias** - adicionei Hibernate, MySQL, STS, Postman
7. **Exemplos de JSON** com nome da integrante Ana Karoline como exemplo
8. **Equipe completa** com os 6 nomes
9. **Considerações finais** extraídas do seu documento
10. **Link do PDF** em duas seções estratégicas (Sobre o Projeto + Documentação Técnica)

### 🔗 Onde colocar o PDF:

Crie a pasta `docs/` na raiz do projeto e coloque seu PDF lá com o nome `documentacao-projeto-rh.pdf`. Depois faça commit e push. O link funcionará automaticamente no GitHub.
