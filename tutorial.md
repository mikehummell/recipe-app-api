# Setup up
## Create a Dockerfile:
First part wich image

ENV PYTHONUNBUFFERED 1
= No buffering for python. Can create side effekt when run on docker

Requrement. All pip installation

Create a app directory. Which copy all the files from the local enviroment to dokers

Create a user (not to run as root)

## Create a requirements.txt
all the dependency
Take the last version from the major verison

## Create the app folder

# Run it:
docker build .


# Docker Compose
create a docker compose file for orchister all the services (eg Backend, DB)

docker-compose build
docker-compose run app

## Install Django
docker-compose run app sh -c "django-admin.py startproject app ." 

## Travis
Github and travis.com must be link
create a .travis.yml file
Link with flake8 (Nice cood) 

# Unittest
Django looks for a tests.py file an run it. Or folder

docker-compose run app sh -c "python manage.py test"

#Flake8
First install it on the docker: docker-compose build
run it: docker-compose run app sh -c "python manage.py test && flake8" 
# Create Main app
docker-compose run app sh -c "python manage.py startapp core"
add     'core', to setting (App)
Cleanup: 
    - Delete Test, views, 
    - Create tests folder
    - Create __init__.py

Create a modul
Link it also in the settings.py: AUTH_USER_MODEL = 'core.User'

Make migration
docker-compose run app sh -c "python manage.py makemigrations core"

# Start Server
docker-compose up

