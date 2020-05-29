
# Commands Docker

## BASIC COMMANDS

 - list images: `docker image list`

 - download or update images: `docker image pull python`

# inpect image
docker image inspect python

# run container
docker container run <parâmetros> <imagem> <CMD> <argumentos>

## example
docker container run -it --rm --name meu_python python bash

# map volume
docker container run -it --rm -v "<host>:<container\>" python

# map ports
docker container run -it --rm -p "<host>:<container\>" python

# set memory RAM
docker container run -it --rm -m 512M python

# define CPU: flag -c of 1 to 1024
docker container run -it --rm -c 512 python

# view containers
docker container ls <parâmetros>

# stop container
docker container stop meu_python


# --- CREATE A YOUR IMAGE ON DOCKER

# commit modified image
docker container commit containercriado meuubuntu:nginx

# verify a software is intalled
docker container run -it --rm meuubuntu:nginx dpkg -l nginx





