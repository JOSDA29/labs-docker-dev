# Laboratorio Docker

## Output de los comandos - Pulling an image

### docker pull ubuntu:latest
latest: Pulling from library/ubuntu
9c704ecd0c69: Pull complete 
Digest: sha256:2e863c44b718727c860746568e1d54afd13b2fa71b160f5cd9058fc436217b30
Status: Downloaded newer image for ubuntu:latest
docker.io/library/ubuntu:latest

### docker pull python:3.9
3.9: Pulling from library/python
ca4e5d672725: Pull complete 
30b93c12a9c9: Pull complete 
10d643a5fa82: Pull complete 
d6dc1019d793: Pull complete 
c7d45ab0573c: Pull complete 
564d1c451ea7: Pull complete 
ddfb50ba1977: Pull complete 
91b87d81d4c8: Pull complete 
Digest: sha256:65438c2e26dbf9f5db4b5553e332747fa20722c1b7c7ccc6f8480396ff4186db
Status: Downloaded newer image for python:3.9
docker.io/library/python:3.9

## Output de los comandos - Running our container

### docker run -it ubuntu bash
root@b3e2ff90a891:/# 

### docker run -d -p 8000:80 httpd
024d239aab49adee9748de3f51237540342a144ab896c9473216ebe96788e592

## Output de los comandos - Removing containers

### docker rm b3e2ff90a891 - keen_lewin
b3e2ff90a891