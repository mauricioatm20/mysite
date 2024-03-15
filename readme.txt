1. crear proyecto django
2. ejecutar comando en terminal --  python manage.py startapp polls --
3. en le archivo polls/views.py

    from django.http import HttpResponse
    def index(request):
    return HttpResponse("Hello, world. You're at the polls index.")

4. crear un archivo urls.py dentro la carpeta polls y escribir

    from django.urls import path
    from . import views

    urlpatterns = [
    path('', views.index, name='index'),
]

5.en la carpeta mysite en el archivo urls.py escribir

    from django.contrib import admin
    from django.urls import include, path

    urlpatterns = [
        path('polls/', include('polls.urls')),
        path('admin/', admin.site.urls),
]

6.crear una base de datos "Mysql"

7.en mysite el archivo settings.py cambiar la configuracion de DATABASE

    'default': {
            'ENGINE': 'django.db.backends.mysql',
            'NAME': 'users',
            'USER': 'root',
            'PASSWORD': 'root',
            'HOST': 'localhost',
            'PORT': '3306',
        }

8.ejecutar comando     pip install mysqlclient
9.ejecutar             python manage.py migrate
                        crea las tablas por defecto que tiene predefinidas en la base de datos

10. ejecutar el codigo    python manage.py makemigrations polls
11. ejecutar codigo       python manage.py sqlmigrate polls 0001
12. ejecutar codigo       python manage.py migrate
    crea un super usuario         python manage.py createsuperuser

13. Cada ves que se modifique el models.py  ejecutar los codigos
    python manage.py makemigrations polls
    python manage.py sqlmigrate polls 0001
    python manage.py migrate

14. Ejecutar python manage.py createsuperuser
       añadimos usuario,email,pasword

15 Ejecutamos  python manage.py runserver
16. buscamos   http://127.0.0.1:8000/admin/

17. Hacer que la aplicación de encuesta sea modificable en el administrado
        en polls/admin/ agregamos  admin.site.register(Question


18 buscar en localhost:8000/polls/admin