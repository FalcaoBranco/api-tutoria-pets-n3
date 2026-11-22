# API REST — Sistema de Tutoria de Pets (N3)

Aplicação servidora desenvolvida para avaliação integrada (N3) das disciplinas de **Desenvolvimento Server-side** e **Banco de Dados**, implementando operações CRUD via ORM, classificação automática de porte dos animais, autenticação via JWT e objetos avançados no banco relacional (Consultas, Views, Triggers e Stored Procedures).

---

## Stack Tecnológica

* **Runtime & Linguagem:** Node.js (JavaScript)
* **Framework Web:** Express.js
* **ORM:** Sequelize (`sequelize` + `mysql2`)
* **Banco de Dados:** MariaDB
* **Autenticação & Segurança:** JSON Web Token (`jsonwebtoken`) + Hash de senha (`bcryptjs`)

---

## Arquitetura do Banco de Dados

O modelo relacional segue a 3ª Forma Normal (3FN) e é composto por três entidades principais:

* **`tutor`**: Armazena os dados cadastrais e credenciais de acesso do responsável (`cpf`, `nome`, `email`, `senha`, `total_pets`).
* **`altura_pet`**: Tabela de domínio com os três portes fixos (`1 - pequeno`, `2 - média`, `3 - alto`).
* **`pet`**: Armazena os animais vinculados a um tutor e a uma classificação de altura (`codigo_pet`, `nome_pet`, `genero_pet`, `altura_cm`, `cpf_tutor`, `id_altura`).

### Regra de Classificação de Porte
* **Pequeno (`id_altura = 1`):** `altura_cm <= 13`
* **Média (`id_altura = 2`):** `14 <= altura_cm < 40`
* **Alto (`id_altura = 3`):** `altura_cm >= 40`

---

## Como Executar Localmente

1. **Clone o repositório:**
   ```bash
   git clone [https://github.com/gGabrielnrds/api-tutoria-pets-n3.git](https://github.com/gGabrielnrds/api-tutoria-pets-n3.git)
   cd api-tutoria-pets-n3