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
