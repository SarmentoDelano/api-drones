# API de Drones - Django REST Framework

Sistema backend para gerenciamento de drones, pilotos e competições, construído com Django e Django REST Framework. Esta API permite o cadastro, listagem, filtro e ordenação de drones, pilotos e competições.

---

## ⚙️ Tecnologias Utilizadas

- Python 3.11+
- Django 4+
- Django REST Framework
- Django Filter
- Token Authentication
- SQLite (ou outro banco compatível)
- Django Admin personalizado

---

## 🔐 Autenticação

Algumas rotas requerem autenticação via Token.  
Use o endpoint de obtenção de token para autenticar-se.

```bash
# Obter token (exemplo com curl)
curl -X POST -d "username=seu_usuario&password=sua_senha" http://localhost:8000/api-token-auth/
🔄 Endpoints Principais

Recurso	Métodos	Descrição
/drones/	GET, POST	Lista e cria drones
/drones/<id>/	GET, PUT, DELETE	Detalhes de um drone
/pilots/	GET, POST	Lista e cria pilotos (requer token)
/pilots/<id>/	GET, PUT, DELETE	Detalhes de um piloto (requer token)
/competitions/	GET, POST	Lista e cria competições
/competitions/<id>/	GET, PUT, DELETE	Detalhes de uma competição
/drone-categories/	GET, POST	Listagem e criação via ViewSet (router DRF)
🔍 Filtros Disponíveis
Competitions

from_achievement_date, to_achievement_date

min_distance_in_feet, max_distance_in_feet

drone_name, pilot_name

Drones

drone_category

has_it_competed

Pilots

gender

races_count

🧪 Testes Automatizados
Rode os testes com:

bash
Copiar
Editar
python manage.py test drones
Os testes cobrem:

Criação de categorias de drones

Validação de nomes duplicados

Filtro por nome

Atualização de categoria

Operações com pilotos (com e sem autenticação)

🛠️ Permissões
IsAuthenticatedOrReadOnly: acesso público para leitura, alterações apenas autenticado.

IsCurrentUserOwnerOrReadOnly: recursos como Drone só podem ser alterados por seu criador.

🧭 Paginação
Paginação customizada com LimitOffsetPagination e limite máximo de 8 registros por requisição.

📷 Admin Customizado
Miniaturas das imagens dos drones são exibidas na interface administrativa.

Filtros avançados por categoria, status de competição e publicação.

Edição inline de categoria e status de publicação.

✍️ Autor
Desenvolvido por Delano Sarmento
📧 delanosarmento1@gmail.com
📱 +55 (71)99309-9382

📌 Licença
Este projeto está licenciado sob os termos da licença MIT.
