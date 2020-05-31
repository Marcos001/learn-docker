
# Commands Docker

## BASIC COMMANDS

 - list images:
      -  `docker image list`
 - download or update images:
      -  `docker image pull python`
 - inspect image: 
      - `docker image inspect python`
 - run container:
      - `docker container run <parametros> <imagem> <CMD> <argumentos>`
     - Example: `docker container run -it --rm --name meu_python python bash`
 - map volume: 
      - `docker container run -it --rm -v "<host>:<container\>" python`
 - map ports:
      -  `docker container run -it --rm -p "<host>:<container\>" python`
 - set memory RAM:
      -  `docker container run -it --rm -m 512M python`
 - define CPU: flag -c of 1 to 1024
    - `docker container run -it --rm -c 512 python`
 - view containers: 
      - `docker container ls <parâmetros>`
 - stop container:
     -  `docker container stop meu_python`


## CREATE A YOUR IMAGE ON DOCKER

 - commit modified image: 
     - `docker container commit containercriado meuubuntu:nginx`
 - verify a software is installed:
    -  `docker container run -it --rm meuubuntu:nginx dpkg -l nginx`
- build image from Dockerfile
  - `docker image build -t meuubuntu:nginx_auto .`

## UNDERSTAND DOCKER STORAGE

 - mount volume to OS to docker
    - `docker container run -v /var/lib/container1:/var ubuntu`
- create volume in container
  - `docker create -v /dbdata --name dbdata postgres /bin/true`
- volumes from other container
  - `docker container run -d --volumes-from dbdata --name db2 postgres`
- create a volume
  -  `docker volume create --name dbdata`
- associate volume  created in container
  - `docker container run -d -v dbdata:/var/lib/data postgres`

## UNDERSTAND DOCKER NETWORK

- view network interfaces
  - `docker network ls`


### References
 - [Docker para desenvolvedores](https://leanpub.com/dockerparadesenvolvedores)
 - [Docker Docs](https://docs.docker.com/)