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

## Token 
POST http://localhost:8000/api/token/
Ejemplo pedir los tokens para el administrador
```
Content-Type: application/json
{
  "username": "admin",
  "password": "test"
}
```
## libros 
```
GET /api/libros/ → listar libros
filtros: ?genero=Novela, ?autor__id=1, ?fecha_de_publicacion=, ?copias_disponibles=2
POST /api/libros/ → crear libro (solo admin)
GET /api/libros/{id}/ → detalle de un libro
PUT/PATCH /api/libros/{id}/ → actualizar libro (solo admin)
DELETE /api/libros/{id}/ → eliminar libro (solo admin)
```
## Autores
Ejemplo 
```
GET /api/autores/ → listar autores
POST /api/autores/ → crear autor (solo admin)
GET /api/autores/{id}/ → detalle de autor
PUT/PATCH /api/autores/{id}/ → actualizar autor (solo admin)
DELETE /api/autores/{id}/ → eliminar autor (solo admin)
```
## Prestamos 
```
POST /api/prestamos/prestamos/  (solicitar prestamos admin y lectores)
GET /api/prestamos/mis-prestamos/(para ver los prestamos que tengo activos)
```
Ejemplo pedir un prestamo 
```
POST http://localhost:8000/api/prestamos/ 
Content-Type: application/json
Authorization:  Bearer <token>
{
  "libro_id": 3,
  "start_date": "2025-09-10",
  "due_date": "2025-09-20",
  "returned": false
}
```


