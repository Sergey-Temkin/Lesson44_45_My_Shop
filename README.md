# Lesson44_45_My_Shop

08.10.2024-00:45

## Commands schema on VScode:
pip install psycopg2-binary
pip install dj-database-url
pip freeze > requirements.txt

In Myshop/Setting under the DATABASE line paste:

DATABASES = {
    'default': dj_database_url.config(
        # Replace this value with your local database's connection string(External Database URL-In render).
        default='postgresql://my_shop_01rp_user:ObpvFuAMo6Fhu6eaoO5HrgganaeC5Czt@dpg-ct70nu52ng1s7398h1sg-a.frankfurt-postgres.render.com/my_shop_01rp',
        conn_max_age=600
    )
}

py manage.py runserver
py manage.py migrate
py manage.py createsuperuser

## Virtual Environment
python -m venv venv
source venv/Scripts/activate
pip install -r requirements.txt
pip freeze > requirements.txt
deactivate

# Django
## Initialize application:
pip install django
django-admin startproject (Name of project)  .  (Don't forget space and dot at the end!!!)
py manage.py startapp (Name of folder)
py manage.py runserver

## Rest framework
pip install djangorestframework

## Admin:
py manage.py runserver
py manage.py createsuperuser

## Migration to Database:
py manage.py makemigrations  
py manage.py migrate

## Shell,I-python commends:
py manage.py shell

## Adding to Database:
from courts.models import Court
c = Court(number1)
c.save()

from members.models import Member
m = Member(firstname='Emil', lastname='Refsnes', phone='111111')
m.save()

court = Court.objects.first()
m = Member(firstname='Emil', lastname='Refsnes', phone='111111', court=court)
m.save()
court2 = Court.objects.get(id=2)
m = Member(firstname='Emil', lastname='Refsnes', phone='111111', court=court2)
m.save()

## Delete from Database:
x = Member.objects.all()[0]       [0] --Witch index to delete
x.firstname                       Check the name of the index to delete(Optional)
x.delete()

## Delete all:
Member.objects.all().delete()

## Change id:
x = Member.objects.all()[0]
x.id                         (Lets say it's:7)
x.id = 1 
x.save()

## Reset the Auto-increment Sequence of ID in DB:
Member.objects.all().delete()
from django.db import connection
with connection.cursor() as cursor:
    cursor.execute('DELETE FROM sqlite_sequence WHERE name="@@@@"')     (change: "@@@" to the table name in DB, Example:"members_member") 

## Work with Ipython Shell
1. In main project folder, in settings folder add the line: SHELL_PLUS ='ipython'
2. pip install ipython
3. python manage.py shell
4. exit()

## VScode path
PC:
cd "C:\Users\USER\OneDrive\Computer_Science/001-Code/001-Jhon-Bryce/000-GitHub/Lesson44_45_My_Shop"
Laptop:
cd "C:\Users\sergh\OneDrive\Computer_Science/001-Code/001-Jhon-Bryce/000-GitHub/Lesson44_45_My_Shop"

## Uninstall all packages in a virtual environment
pip freeze | xargs pip uninstall -y
deactivate
pip cache purge
DELETE VENV FILE!!!

## GIT add
git add . 
git status 
git commit -m " " 
git push

## Remove last commit on GIT
git reset HEAD~1
git push -f origin main

## Requirements
pip freeze > requirements.txt 
pip install -r requirements.txt

## Packages
pip install django
pip install flask
pip install flask-cors
pip install sqlalchemy 
pip install psycopg2
pip install mysqlclient

http://127.0.0.1:500
http://127.0.0.1:5500
http://127.0.0.1:8000/