# Creacion de la app


## Backend

* Creamos un entorno virtual
python -m venv <nombre> 

* Procedemos a instalar django
pip install django

* creamos una plantilla del proyecto 
django-admin startproject <nombre>

* Ejecutamos el proyecto
python manage.py runserver

* Creamos una app 
python manage.py startapp tasks

* agregamos la app en settings.py

* migramos la app para que todo funcione correctamente
python manage.py migrate

**Como vamos a crear una API de backend vamos a utilizar un framework que se llama django-rest-framework**
* pip install djangorestframework -> sirve para crear API al instante

* instalamos la comunicacion del front con el back
pip install django-cors-headers

* agregamos las app de corsheaders y rest_framework al setting en la sesiion de app
el corsheader tambien se agrega en la session de middleware  "corsheaders.middleware.CorsMiddleware",
antes de 'django.middleware.common.CommonMiddleware',


* se agrega este comando al final de setting
para decidir que servidores se pueden conectar
CORS_ALLOWED_ORIGINS = [
    
]



## Modelo de tareas o creacion de tablas
Vamos a la app task y entramos al models

creo el modelo 
class Task(models.Model):
    title = models.CharField(max_length=200)
    descripcion = models.TextField(blank=True)
    done = models.BooleanField(default=False)


* creamos el archivo que ejecuta codigo sql 
python manage.py makemigrations tasks

* migramos el codigo pa que se cree la tabla
python manage.py migrate tasks


* creamos un super usuario
python manage.py createsuperuser

name: jorge
correo: jalheno2010@hotmail.com
password: dinero1234


agregamos esto a admin para que nos permita manejar el modelo desde el usuario
    from .models import Task
    # Register your models here.
    admin.site.register(Task)


agregamos este str a model para que nos permita ver el titulo desde admin
def __str__(self):
        return self.title

