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
python manage.py createsuperuser
## 6. Iniciar servidor
python manage.py runserver



