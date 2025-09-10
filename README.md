# Biblioteca Digital - API REST

API construida con **Django + Django REST Framework** para gestionar **autores, libros y préstamos** en una biblioteca digital.  
Los usuarios pueden autenticarse como **administradores** (gestionar libros y autores) o como **lectores** (consultar y solicitar préstamos).

---

## Instalación y ejecución

### 1. Clonar el repositorio
```bash
git clone https://github.com/tu-usuario/tu-repo.git
cd tu-repo

---
```
## 2. Crear y activar entorno virtual 
python -m venv .venv
.venv\Scripts\activate     
## 3. Instalar requerimientos
pip install -r requirements.txt
## 4. Hacer la migracion
python manage.py migrate
## 5. Crear el administrador
python manage.py createsuperuser para acceder a la vista de administrador 
## 6. Iniciar servidor
python manage.py runserver

### Endpoints principales
## libros 
```
GET /api/books/ → listar libros
filtros: ?genre=Novela, ?author__id=1, ?available=true
POST /api/books/ → crear libro (solo admin)
GET /api/books/{id}/ → detalle de un libro
PUT/PATCH /api/books/{id}/ → actualizar libro (solo admin)
DELETE /api/books/{id}/ → eliminar libro (solo admin)
```
## Autores
```
GET /api/authors/ → listar autores
POST /api/authors/ → crear autor (solo admin)
GET /api/authors/{id}/ → detalle de autor
PUT/PATCH /api/authors/{id}/ → actualizar autor (solo admin)
DELETE /api/authors/{id}/ → eliminar autor (solo admin)
```
## Prestamos 


