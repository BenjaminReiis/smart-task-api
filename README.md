<div align="center">

# 🚀 API de Tarefas Inteligentes
### Smart Task API

[![Python](https://img.shields.io/badge/Python-3.11+-3776AB?style=flat&logo=python&logoColor=white)](https://www.python.org/)
[![FastAPI](https://img.shields.io/badge/FastAPI-0.110+-009688?style=flat&logo=fastapi&logoColor=white)](https://fastapi.tiangolo.com/)
[![Uvicorn](https://img.shields.io/badge/Uvicorn-ASGI-2A2A2A?style=flat&logo=gunicorn&logoColor=white)](https://www.uvicorn.org/)
[![Render](https://img.shields.io/badge/Deploy-Render-46E3B7?style=flat&logo=render&logoColor=white)](https://render.com/)
[![License](https://img.shields.io/badge/License-MIT-yellow.svg)](#-licença)

**Uma API REST para gerenciamento de tarefas, construída com Python e FastAPI, com foco em boas práticas de backend.**

[Demonstração](#-demonstração-da-api) •
[Sobre](#-sobre-o-projeto) •
[Instalação](#-como-executar-localmente) •
[Endpoints](#-documentação-da-api) •
[Estrutura](#-estrutura-do-projeto)

</div>

---

## 🌐 Demonstração da API

A API está disponível publicamente para testes:

| Recurso | Link |
|---|---|
| 🔗 **API Online** | [smart-task-api-ej7e.onrender.com](https://smart-task-api-ej7e.onrender.com) |
| 📚 **Documentação Interativa (Swagger UI)** | [smart-task-api-ej7e.onrender.com/docs](https://smart-task-api-ej7e.onrender.com/docs) |
| 🖥️ **Página do Projeto** | [benjaminreiis.github.io/smart-task-api](https://benjaminreiis.github.io/smart-task-api/) |

> ⚠️ **Nota:** o serviço está hospedado no plano gratuito do Render. A primeira requisição após um período de inatividade pode levar alguns segundos para responder (cold start).

A documentação Swagger permite testar **todos os endpoints diretamente pelo navegador**, sem necessidade de Postman, Insomnia ou qualquer cliente HTTP externo.

---

## 🧠 Sobre o Projeto

O objetivo deste projeto é demonstrar a construção de um backend funcional seguindo padrões reais de desenvolvimento de APIs REST.

A **Smart Task API** simula um sistema de produtividade onde é possível gerenciar tarefas através de operações completas de **CRUD** (Create, Read, Update, Delete):

- ✅ **Criar** tarefas
- 📋 **Listar** tarefas (todas ou por ID)
- ✏️ **Atualizar** tarefas existentes
- 🗑️ **Remover** tarefas

Todas as operações seguem o padrão **REST**, utilizando HTTP como interface principal de comunicação e JSON como formato de dados.

> 💡 Este é um projeto de simulação/estudo, focado em demonstrar boas práticas de arquitetura de API — validação de dados, separação de responsabilidades, documentação automática e deploy em nuvem.

---

## ⚙️ Tecnologias Utilizadas

| Tecnologia | Função no projeto |
|---|---|
| **Python** | Linguagem principal da aplicação |
| **FastAPI** | Framework web para construção da API REST |
| **Uvicorn** | Servidor ASGI responsável por executar a aplicação |
| **Pydantic** | Validação e tipagem dos dados de entrada/saída |
| **Swagger UI** | Documentação interativa gerada automaticamente pelo FastAPI |
| **Git & GitHub** | Versionamento de código e hospedagem do repositório |
| **Render** | Plataforma de deploy em nuvem |

---

## 📋 Funcionalidades

- Cadastro de novas tarefas com título, descrição e status
- Listagem de todas as tarefas cadastradas
- Busca de uma tarefa específica por ID
- Atualização parcial ou completa de uma tarefa
- Remoção de tarefas
- Validação automática de dados de entrada (tipos, campos obrigatórios)
- Documentação automática e interativa via Swagger UI (`/docs`) e ReDoc (`/redoc`)
- Tratamento de erros com mensagens HTTP padronizadas (404, 422, etc.)

---

## 📂 Estrutura do Projeto

```text
api-de-tarefas-inteligentes/
│
├── app/
│   └── main.py          # Definição da aplicação FastAPI, rotas e modelos
│
├── requirements.txt      # Dependências do projeto
└── README.md
```

---

## 🚀 Como Executar Localmente

### Pré-requisitos
- [Python 3.11+](https://www.python.org/downloads/)
- `pip` instalado

### 1. Clone o repositório
```bash
git clone https://github.com/benjaminreiis/smart-task-api.git
cd smart-task-api
```

### 2. Crie e ative um ambiente virtual
```bash
python -m venv venv

# Linux / macOS
source venv/bin/activate

# Windows
venv\Scripts\activate
```

### 3. Instale as dependências
```bash
pip install -r requirements.txt
```

### 4. Execute a aplicação
```bash
uvicorn app.main:app --reload
```

A API estará disponível em **`http://127.0.0.1:8000`**, e a documentação interativa em **`http://127.0.0.1:8000/docs`**.

---

## 📡 Documentação da API

### Modelo de Tarefa (Task)

```json
{
  "id": 1,
  "title": "Estudar FastAPI",
  "description": "Revisar documentação oficial e praticar rotas assíncronas",
  "completed": false
}
```

### Endpoints Disponíveis

| Método | Rota | Descrição |
|---|---|---|
| `POST` | `/tasks` | Cria uma nova tarefa |
| `GET` | `/tasks` | Lista todas as tarefas |
| `GET` | `/tasks/{id}` | Busca uma tarefa específica pelo ID |
| `PUT` | `/tasks/{id}` | Atualiza uma tarefa existente |
| `DELETE` | `/tasks/{id}` | Remove uma tarefa |

---

<details>
<summary><code>POST /tasks</code> — Criar nova tarefa</summary>

```http
POST /tasks
Content-Type: application/json
```

```json
// Request
{
  "title": "Estudar FastAPI",
  "description": "Revisar documentação oficial",
  "completed": false
}
```

```json
// Response 201 Created
{
  "id": 1,
  "title": "Estudar FastAPI",
  "description": "Revisar documentação oficial",
  "completed": false
}
```
</details>

<details>
<summary><code>GET /tasks</code> — Listar todas as tarefas</summary>

```json
// Response 200 OK
[
  {
    "id": 1,
    "title": "Estudar FastAPI",
    "description": "Revisar documentação oficial",
    "completed": false
  },
  {
    "id": 2,
    "title": "Configurar deploy no Render",
    "description": "Subir aplicação para produção",
    "completed": true
  }
]
```
</details>

<details>
<summary><code>GET /tasks/{id}</code> — Buscar tarefa por ID</summary>

```json
// Response 200 OK
{
  "id": 1,
  "title": "Estudar FastAPI",
  "description": "Revisar documentação oficial",
  "completed": false
}
```

```json
// Response 404 Not Found
{
  "detail": "Tarefa não encontrada"
}
```
</details>

<details>
<summary><code>PUT /tasks/{id}</code> — Atualizar tarefa</summary>

```json
// Request
{
  "title": "Estudar FastAPI avançado",
  "description": "Revisar autenticação e dependências",
  "completed": true
}
```

```json
// Response 200 OK
{
  "id": 1,
  "title": "Estudar FastAPI avançado",
  "description": "Revisar autenticação e dependências",
  "completed": true
}
```
</details>

<details>
<summary><code>DELETE /tasks/{id}</code> — Remover tarefa</summary>

```json
// Response 204 No Content
```
</details>

### Códigos de Status HTTP

| Código | Significado |
|---|---|
| `200` | Requisição bem-sucedida |
| `201` | Recurso criado com sucesso |
| `204` | Recurso removido com sucesso (sem conteúdo de retorno) |
| `404` | Tarefa não encontrada |
| `422` | Erro de validação nos dados enviados |

---

## 🧪 Testando a API

A forma mais rápida de testar todos os endpoints é através da documentação interativa do Swagger:

🔗 **[smart-task-api-ej7e.onrender.com/docs](https://smart-task-api-ej7e.onrender.com/docs)**

Também é possível testar via `curl`:

```bash
# Criar uma tarefa
curl -X POST https://smart-task-api-ej7e.onrender.com/tasks \
  -H "Content-Type: application/json" \
  -d '{"title": "Minha tarefa", "description": "Descrição da tarefa", "completed": false}'

# Listar tarefas
curl https://smart-task-api-ej7e.onrender.com/tasks
```

---

## 🗺️ Próximos Passos

- [ ] Persistência em banco de dados (SQLite/PostgreSQL)
- [ ] Autenticação de usuários (JWT)
- [ ] Filtros e paginação na listagem de tarefas
- [ ] Testes automatizados com Pytest
- [ ] Containerização com Docker

---

## 🤝 Como Contribuir

1. Faça um fork do projeto
2. Crie uma branch (`git checkout -b feature/minha-feature`)
3. Commit suas alterações (`git commit -m 'feat: adiciona minha feature'`)
4. Push para a branch (`git push origin feature/minha-feature`)
5. Abra um Pull Request

---

## 📄 Licença

Este projeto está sob a licença MIT. Veja o arquivo [LICENSE](LICENSE) para mais detalhes.

---

<div align="center">

**Desenvolvido como projeto de estudo de backend com Python e FastAPI.**

⭐ Se este projeto foi útil, considere deixar uma estrela no repositório!

</div>
