# 🍽️ SQL Projeto Restaurante

![MySQL](https://img.shields.io/badge/MySQL-8.0+-blue)
![SQL](https://img.shields.io/badge/SQL-Database-orange)
![Status](https://img.shields.io/badge/Status-Concluído-success)

## 📖 Sobre o Projeto

Este projeto consiste na modelagem e implementação de um banco de dados relacional para gerenciamento de um restaurante utilizando **MySQL**.

O objetivo é demonstrar, de forma prática, os principais conceitos de SQL, desde a criação da estrutura do banco de dados até consultas analíticas avançadas utilizando filtros, agregações, JOINs e Views.

O cenário simula operações reais de um restaurante, contemplando o gerenciamento de clientes, funcionários, produtos, pedidos e informações complementares dos produtos.

---

## 🎯 Objetivos

* Desenvolver uma estrutura relacional completa para um restaurante.
* Aplicar conceitos de modelagem de dados.
* Utilizar comandos DDL e DML.
* Realizar consultas utilizando filtros e ordenações.
* Explorar funções de agregação para análise de dados.
* Implementar relacionamentos através de JOINs.
* Criar Views para facilitar consultas analíticas.

---

## 🗂️ Modelo de Dados

O banco de dados **restaurante** é composto pelas seguintes tabelas:

| Tabela             | Descrição                           |
| ------------------ | ----------------------------------- |
| 👨‍🍳 funcionarios | Cadastro de funcionários            |
| 👥 clientes        | Cadastro de clientes                |
| 🍔 produtos        | Catálogo de produtos                |
| 📋 info_produtos   | Informações adicionais dos produtos |
| 🧾 pedidos         | Registro dos pedidos realizados     |

### 🔗 Relacionamentos

```text
funcionarios ──┐
               ├──► pedidos ◄──── clientes
produtos ──────┘         │
    │                    │
info_produtos ◄──────────┘
```

---

## 📂 Estrutura do Projeto

```text
SQL_Projeto_Restaurante/
│
├── 1_criando_tabelas_colunas.sql
├── 2_inserindo_dados.sql
├── 3_filtrando_ordenando_backup.sql
├── 4_filtros_condicionais.sql
├── 5_agregacoes_organizacao.sql
├── 6_joins.sql
└── 7_consultas_avancadas.sql
```

### 📌 Descrição dos Arquivos

| Arquivo                  | Conteúdo                            |
| ------------------------ | ----------------------------------- |
| 1️⃣ Criação das tabelas  | Database, tabelas e relacionamentos |
| 2️⃣ Inserção de dados    | População das tabelas               |
| 3️⃣ Filtros e ordenação  | WHERE e ORDER BY                    |
| 4️⃣ Filtros condicionais | LIKE, IN, BETWEEN, AND e OR         |
| 5️⃣ Agregações           | COUNT, AVG, SUM, MIN e MAX          |
| 6️⃣ JOINs                | Relacionamentos entre tabelas       |
| 7️⃣ Consultas avançadas  | Views e análises complexas          |

---

## 💡 Conceitos Aplicados

### 🏗️ DDL (Data Definition Language)

* CREATE DATABASE
* CREATE TABLE
* PRIMARY KEY
* FOREIGN KEY
* Tipos de dados:

  * INT
  * VARCHAR
  * DECIMAL
  * DATE

### ✍️ DML (Data Manipulation Language)

* INSERT INTO
* UPDATE
* DELETE

### 🔍 Consultas

* SELECT
* WHERE
* ORDER BY
* LIKE
* IN
* BETWEEN
* YEAR()

### 📊 Agregações

* COUNT()
* COUNT(DISTINCT)
* AVG()
* SUM()
* MIN()
* MAX()
* GROUP BY
* HAVING

### 🔗 JOINs

* INNER JOIN
* Relacionamentos entre 2, 3 e 4 tabelas

### 🖼️ Views

* CREATE VIEW
* CREATE OR REPLACE VIEW
* Consultas analíticas utilizando Views

---

## 🚀 Como Executar

### Pré-requisitos

* MySQL Server 8.0+
* MySQL Workbench, DBeaver ou terminal MySQL

### 1️⃣ Clone o Repositório

```bash
git clone https://github.com/AlderARS/SQL_Projeto_Restaurate.git
cd SQL_Projeto_Restaurate
```

### 2️⃣ Conecte-se ao MySQL

```bash
mysql -u root -p
```

### 3️⃣ Execute os Scripts

```sql
SOURCE 1_criando_tabelas_colunas.sql;
SOURCE 2_inserindo_dados.sql;
SOURCE 3_filtrando_ordenando_backup.sql;
SOURCE 4_filtros_condicionais.sql;
SOURCE 5_agregacoes_organizacao.sql;
SOURCE 6_joins.sql;
SOURCE 7_consultas_avancadas.sql;
```

⚠️ Execute os arquivos na ordem apresentada, pois cada etapa depende da anterior.

---

## 🔎 Exemplos de Consultas

### 🍔 Produtos com preço acima de R$ 30

```sql
SELECT nome, categoria
FROM produtos
WHERE preco > 30;
```

### 👥 Clientes nascidos antes de 1985

```sql
SELECT nome, telefone, data_nascimento
FROM clientes
WHERE YEAR(data_nascimento) < 1985;
```

### 🥩 Produtos contendo "carne" na descrição

```sql
SELECT id_produto, descricao
FROM produtos
WHERE descricao LIKE '%carne%';
```

### 🧾 Pedidos com dados dos clientes

```sql
SELECT pe.id_pedido,
       pe.quantidade,
       pe.data_pedido,
       cl.nome,
       cl.email
FROM pedidos pe
INNER JOIN clientes cl
ON pe.id_cliente = cl.id_cliente;
```

### 📈 Resumo de Pedidos com View

```sql
CREATE VIEW resumo_pedido AS
SELECT
    pe.id_pedido,
    pe.data_pedido,
    cl.nome AS nome_cliente,
    func.nome AS nome_funcionario,
    pr.nome AS nome_produto,
    pr.preco
FROM pedidos pe
JOIN clientes cl ON cl.id_cliente = pe.id_cliente
JOIN funcionarios func ON func.id_funcionario = pe.id_funcionario
JOIN produtos pr ON pr.id_produto = pe.id_produto;
```

---

## 🛠️ Tecnologias Utilizadas

| Tecnologia | Finalidade                      |
| ---------- | ------------------------------- |
| 🐬 MySQL 8 | Banco de Dados Relacional       |
| 📜 SQL     | Manipulação e consulta de dados |

---

## 📚 Competências Desenvolvidas

✅ Modelagem de Banco de Dados

✅ SQL Avançado

✅ Relacionamentos entre Tabelas

✅ Consultas Analíticas

✅ Views

✅ Funções de Agregação

✅ JOINs Complexos

✅ Manipulação e Organização de Dados

---

## 👨‍💻 Autor

**AlderARS**

Projeto desenvolvido para prática de conceitos de Banco de Dados Relacional e SQL aplicados a um cenário real de gestão de restaurantes.

⭐ Se este projeto foi útil para você, considere deixar uma estrela no repositório.
