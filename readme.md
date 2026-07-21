# Todo API JWT

API REST de gerenciamento de tarefas com autenticação JWT, construída com FastAPI, SQLAlchemy e MySQL.

## Stack

- FastAPI
- SQLAlchemy
- MySQL (via PyMySQL)
- JWT (python-jose)
- Passlib (bcrypt) para hash de senha

## Funcionalidades

- Registro de usuário
- Login com geração de token JWT
- CRUD de tarefas protegido por autenticação
- Cada usuário só acessa suas próprias tarefas

## Como rodar

1. Clone o repositório e entre na pasta

\`\`\`bash
git clone https://github.com/RudolfoSehnemCode/todo-api-jwt.git
cd todo-api-jwt
\`\`\`

2. Crie o ambiente virtual e instale as dependências

\`\`\`bash
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
\`\`\`

3. Crie o banco no MySQL

\`\`\`sql
CREATE DATABASE todo_db;
\`\`\`

4. Configure o `.env` com a URL de conexão e uma chave secreta própria

5. Rode a aplicação

\`\`\`bash
uvicorn main:app --reload
\`\`\`

6. Acesse a documentação interativa em `http://localhost:8000/docs`

## Endpoints

| Método | Rota | Descrição | Autenticado |
|--------|------|-----------|-------------|
| POST | /register | Cria um novo usuário | Não |
| POST | /login | Retorna o token JWT | Não |
| GET | /tasks | Lista as tarefas do usuário | Sim |
| POST | /tasks | Cria uma nova tarefa | Sim |
| PUT | /tasks/{id} | Atualiza uma tarefa | Sim |
| DELETE | /tasks/{id} | Remove uma tarefa | Sim |