# 🚀 Smart Task API

Uma **API REST para gerenciamento de tarefas** desenvolvida com foco em boas práticas de backend.

Este projeto simula um pequeno sistema de produtividade onde usuários podem **criar, visualizar, atualizar e remover tarefas** através de requisições HTTP.

A aplicação foi desenvolvida utilizando **Python** e o framework **FastAPI**, sendo hospedada na nuvem para acesso público.

---

# 🌐 Demonstração da API

A aplicação está **rodando publicamente na internet**.

🔗 API Online
https://smart-task-api-ej7e.onrender.com

📚 Documentação interativa
https://smart-task-api-ej7e.onrender.com/docs

A documentação permite testar todos os endpoints diretamente no navegador utilizando o Swagger UI.

---

# 🧠 Sobre o Projeto

O objetivo deste projeto é demonstrar a construção de um **backend simples porém funcional**, simulando como APIs são utilizadas em sistemas reais.

A aplicação fornece endpoints que permitem:

* Criar novas tarefas
* Listar tarefas existentes
* Atualizar tarefas
* Remover tarefas

Todos os dados são manipulados através de requisições HTTP seguindo o padrão REST.

---

# ⚙️ Tecnologias Utilizadas

* Python
* FastAPI
* Uvicorn
* Swagger UI
* Git
* GitHub
* Render (deploy em nuvem)

---

# 📂 Estrutura do Projeto

smart-task-api

app
└ main.py

requirements.txt
README.md

---

# 🔌 Endpoints da API

### Verificar se a API está rodando

GET /

Resposta:

{
"message": "Smart Task API running"
}

---

### Listar todas as tarefas

GET /tasks

Retorna todas as tarefas armazenadas na aplicação.

---

### Criar uma nova tarefa

POST /tasks

Exemplo de corpo da requisição:

{
"title": "Estudar backend",
"status": "pendente"
}

---

### Atualizar uma tarefa

PUT /tasks/{task_id}

Permite atualizar uma tarefa existente.

---

### Remover uma tarefa

DELETE /tasks/{task_id}

Remove uma tarefa do sistema.

---

# 🧪 Testando a API

Para testar a API, basta acessar a documentação interativa:

https://smart-task-api-ej7e.onrender.com/docs

A interface permite executar todas as requisições diretamente do navegador.

---

# ☁️ Deploy

A aplicação está hospedada utilizando a plataforma de cloud **Render**, que realiza:

* Build automático
* Deploy contínuo
* Execução do servidor backend

Sempre que o código é atualizado no repositório do GitHub, o serviço pode ser atualizado automaticamente.

---

# 🎯 Objetivo do Projeto

Este projeto foi desenvolvido como parte de estudos em **desenvolvimento backend**, com o objetivo de demonstrar:

* criação de APIs REST
* organização de projetos backend
* deploy de aplicações em nuvem
* integração com plataformas de versionamento

---

# 👨‍💻 Autor

Benjamin Reis

Desenvolvedor focado em backend, APIs e engenharia de software.
