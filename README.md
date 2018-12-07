# Django-Quickstart-Script
#!/bin/bash
pip3 install Django==2.1.4
echo 'Enter a site name: ' && read mysite && echo 'Site name chosen: $mysite' 
django-admin startproject $mysite
cd $mysite
echo 'Enter an app name :' && read myapp && echo 'App name created: $myapp'
python3 manage.py startapp $myapp

python3 manage.py runserver &
python3 manage.py migrate

python3 manage.py makemigrations $myapp
python3 manage.py createsuperuser
