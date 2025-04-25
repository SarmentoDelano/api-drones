```markdown
# 🚁 API de Gerenciamento de Drones

Uma API desenvolvida com Django REST Framework para gerenciar drones, categorias, pilotos e competições, permitindo o controle eficiente de dados e funcionalidades relacionadas ao universo de corridas com drones.

---

## 📦 Recursos da API

A API fornece funcionalidades para:

### ✅ Gerenciar Drones:
- Criar, visualizar, atualizar e excluir drones.
- Associar imagens, datas de fabricação e categorias.
- Controlar status de publicação e participação em competições.

### 🛫 Gerenciar Categorias:
- Criar e listar categorias de drones.

### 🧍 Gerenciar Pilotos:
- Criar, visualizar, atualizar e excluir pilotos.
- Registrar gênero e número de corridas realizadas.

### 🏁 Gerenciar Competições:
- Registrar competições entre drones e pilotos.
- Filtrar por data e distância alcançada.

---

## ⚙️ Tecnologias Utilizadas

- **Python**: Linguagem de programação principal.
- **Django**: Framework web completo.
- **Django REST Framework (DRF)**: Criação da API RESTful.
- **SQLite**: Banco de dados padrão para desenvolvimento.
- **Django Filters, Token Auth, Admin Customizado**

---

## 💻 Configuração do Ambiente

### 1. Pré-requisitos
- Python 3.11+
- Pip ou Pipenv
- Git

### 2. Clonar o repositório
```bash
git clone https://github.com/SeuUsuario/api-drones.git
cd api-drones
```

### 3. Instalar dependências
```bash
pip install -r requirements.txt
```

### 4. Executar migrações
```bash
python manage.py makemigrations
python manage.py migrate
```

### 5. Rodar o servidor
```bash
python manage.py runserver
```
A API estará disponível em: http://127.0.0.1:8000/

---

## 🔐 Autenticação

Alguns endpoints exigem autenticação com **Token**.

```bash
# Obter token
curl -X POST -d "username=usuario&password=senha" http://127.0.0.1:8000/api-token-auth/
```

---

## 🔄 Endpoints

### 🚁 Drones

| Método | Endpoint         | Descrição                             |
|--------|------------------|---------------------------------------|
| GET    | /drones/         | Lista todos os drones                 |
| POST   | /drones/         | Cria um novo drone                    |
| GET    | /drones/{id}/    | Detalha um drone específico           |
| PUT    | /drones/{id}/    | Atualiza informações de um drone      |
| DELETE | /drones/{id}/    | Remove um drone                       |

### 📦 Categorias de Drone

| Método | Endpoint                | Descrição                             |
|--------|-------------------------|---------------------------------------|
| GET    | /drone-categories/      | Lista todas as categorias de drone    |
| POST   | /drone-categories/      | Cria uma nova categoria               |
| GET    | /drone-categories/{id}/ | Detalha uma categoria específica      |
| PUT    | /drone-categories/{id}/ | Atualiza uma categoria                |
| DELETE | /drone-categories/{id}/ | Remove uma categoria                  |

### 🧍 Pilotos

| Método | Endpoint         | Descrição                             |
|--------|------------------|---------------------------------------|
| GET    | /pilots/         | Lista todos os pilotos                |
| POST   | /pilots/         | Registra um novo piloto               |
| GET    | /pilots/{id}/    | Detalha um piloto específico          |
| PUT    | /pilots/{id}/    | Atualiza informações de um piloto     |
| DELETE | /pilots/{id}/    | Remove um piloto                      |

### 🏁 Competições

| Método | Endpoint             | Descrição                                   |
|--------|----------------------|---------------------------------------------|
| GET    | /competitions/       | Lista todas as competições                  |
| POST   | /competitions/       | Registra uma nova competição                |
| GET    | /competitions/{id}/  | Detalha uma competição específica           |
| PUT    | /competitions/{id}/  | Atualiza uma competição                     |
| DELETE | /competitions/{id}/  | Remove uma competição                       |

---

## 🔍 Filtros Disponíveis

- **Competições**: por data, distância, drone ou piloto.
- **Drones**: por categoria ou status de competição.
- **Pilotos**: por gênero e número de corridas.

---

## 🧪 Testes Automatizados

Execute com:

```bash
python manage.py test drones
```

Testes disponíveis para:
- Categorias de drone (CRUD + filtro)
- Pilotos autenticados
- Validação de dados

---

## 🛠️ Permissões

- **IsAuthenticatedOrReadOnly**: leitura pública, escrita com login.
- **IsCurrentUserOwnerOrReadOnly**: só o criador pode editar ou apagar seu drone.

---

## 📷 Painel Admin

- Visualização de imagens em miniatura no admin.
- Filtros por categoria, dono, publicação e participação.
- Edição inline de campos como status de publicação.

---

## ✍️ Autor

Desenvolvido por **Delano Sarmento**  
📧 delanosarmento1@gmail.com  
📱 +55 (71) 99309-9382

---

---
