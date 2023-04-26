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
* pip install djangorestframework

* instalamos la comunicacion del front con el back
pip install django-cors-headers

* agregamos las app de corsheaders y rest_framework al setting en la sesiion de app
el corsheader tambien se agrega en la session de middleware "corsheaders.middleware.CorsMiddleware",


* se agrega este comando al final de setting
para decidir que servidores se pueden conectar
CORS_ALLOWED_ORIGINS = [
    
]


