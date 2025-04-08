# Testes Automatizados com Robot Framework – Projeto Mark85

Este repositório contém os testes automatizados desenvolvidos durante o curso [Robot eXpress – Automação de Testes com Robot Framework](https://www.udemy.com/course/robot-express/) da Udemy.

O projeto utiliza o **Robot Framework** com a biblioteca **Browser**, aplicando os conceitos abordados ao longo do curso para validar as funcionalidades da aplicação **Mark85**, que simula um gerenciador de tarefas. Foram utilizados dados dinâmicos, acesso ao banco de dados e integração com arquivos JSON.

## 🧪 Tecnologias Utilizadas

- [Robot Framework](https://robotframework.org/)
- [Robot Framework Browser](https://github.com/MarketSquare/robotframework-browser)
- [Python](https://www.python.org/)
- [MongoDB](https://www.mongodb.com/) – utilizado como banco de dados da aplicação
- [Node.js + React] – fornecidos no curso para fins de prática (não detalhados neste repositório)

## ✅ Funcionalidades Testadas

- Validação de campos obrigatórios
- Cadastro de novos usuários
- Login com sucesso e falha
- Criação, listagem, edição e remoção de tarefas
- Restrições de regras de negócio (senha curta, e-mail inválido, limite de tags)
- Mensagens de alerta e boas-vindas

## 🚀 Como Executar

### Pré-requisitos

- Python 3.10+
- Node.js (para rodar o backend e frontend)
- MongoDB local ou Atlas com IP liberado
- Navegador Chrome

Instalar as dependências:

```bash
pip install -r requirements.txt
rfbrowser init
```

### Rodando os testes

```bash
robot -d logs tests
```

> Os resultados serão salvos no diretório `logs/` com arquivos `log.html`, `report.html` e `output.xml`.

---

## 🖼️ Screenshots da Aplicação

### 👤 Cadastro de Usuário

![Cadastro de usuário](./screenshots-projeto/cadastro-usuario.png)

---

### 🔐 Tela de Login

![Tela de Login](./screenshots-projeto/login.png)

---

### ➕ Cadastro de Tarefas

![Cadastrar tarefa](./screenshots-projeto/cadastrando-task.png)

---

### 📝 Tarefa Cadastrada

![Tarefa Cadastrada](./screenshots-projeto/task-cadastrada.png)

---

### **Clonando o repositório**

```sh
git clone https://github.com/amandaresende/automated-tests-robot-framework
cd automated-tests-robot-framework

```

## 🔒 Segurança no Acesso ao Banco de Dados

Por questões de segurança, **a string de conexão com o MongoDB não foi incluída diretamente no código-fonte**. Em vez disso, recomenda-se utilizar **variáveis de ambiente**.

### Exemplo seguro com variável de ambiente:

```python
from robot.api.deco import keyword
from pymongo import MongoClient
import bcrypt

client = MongoClient('MONGO_URI')

db = client['markdb']
```

### Como configurar:

1. Crie um arquivo `.env` na raiz do projeto contendo:

```env
MONGO_URI=mongodb+srv://usuario:senha@cluster.mongodb.net/markdb
```
