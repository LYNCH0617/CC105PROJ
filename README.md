first in the terminal type: pip install pipenv

second: pipenv shell

3rd: pipenv install Django then pipenv install pymysql

4th: pip freeze ~ ONLY TO CHECK IF IT IS ALREADY INSTALLED

5th: django-admin startproject (name)

6th: cd (name)

7th: python or (py) manage.py runserver
 
to create an app folder in the terminal

1. Django-admin startapp (name)

after that 

2. go to the settings.py and put the app name and get the config in the apps.py e.g.(aso.apps.AsoConfig)

3. then create an url file in the app folder and name it urls.py

4. inside the file put this:
	from django.urls import path
	from . import views

	urlpatterns = [
    		path('', views.index),
	]

5. in the views.py you must type this
	def index(request):
    		return render(request, 'index.html')
so that it will redirect to your html file which will be created right after

6. create a folder inside the app folder and name it templates then inside that folder put your index.html
to run that server you must put this in your terminal

1. cd (project name) 	~ so that it will go that directory

2. python or (py) manage.py runserver

3. click the localhost given

4. add the file name in here http://127.0.0.1:8000/ e.g.(http://127.0.0.1:8000/aso)

for migrations

1. Go to phpMyAdmin then add your database name there then dont add table

2. go to your settings then add this to the databases then default
	'ENGINE': 'django.db.backends.mysql',
        'NAME': '', #change it to your dbname
        'USER': 'root',
        'PASSWORD': '',
        'HOST': '127.0.0.1',
        'PORT': '3306',

3. go to your project urls.py then type this
	path('appname/', include("appname.urls")), #dont forget to add the ,include after the import

4. now go to models and create a class

5. go to projectlevel init_py then type
	import pymysql
	pymysql.install_as_MySQLdb()

6. migrate it now 
 	python manage.py makemigrations
	python manage.py migrate

(Compare it to your previous code corcrud)

7. then create a function in views 

8. a form and a table in templates

9. fix the urls in app

10.cd it

11. python or manage.py runserver
