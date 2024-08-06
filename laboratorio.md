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

# Laboratorio Docker #2

## Output de los comandos - building images

### docker build -t ubuntu-updated:latest .
[+] Building 8.6s (6/6) FINISHED                                                                                docker:default
 => [internal] load build definition from dockerfile                                                                      0.1s
 => => transferring dockerfile: 96B                                                                                       0.0s
 => [internal] load metadata for docker.io/library/ubuntu:latest                                                          0.0s
 => [internal] load .dockerignore                                                                                         0.1s
 => => transferring context: 2B                                                                                           0.0s
 => [1/2] FROM docker.io/library/ubuntu:latest                                                                            0.1s
 => [2/2] RUN apt-get update && apt-get upgrade -y                                                                        7.4s
 => exporting to image                                                                                                    0.6s
 => => exporting layers                                                                                                   0.5s
 => => writing image sha256:28a00ff051707baf1ac994f840c599ec7ff9fa059e8f3b5215ad4cf79c16f779                              0.0s
 => => naming to docker.io/library/ubuntu-updated:latest                                                                  0.0s

### docker build -f docker/nginx/dockerfile -t my-nginx:latest .
[+] Building 14.8s (6/6) FINISHED                                                                               docker:default
 => [internal] load build definition from dockerfile                                                                      0.1s
 => => transferring dockerfile: 137B                                                                                      0.0s
 => [internal] load metadata for docker.io/library/ubuntu:latest                                                          0.0s
 => [internal] load .dockerignore                                                                                         0.1s
 => => transferring context: 2B                                                                                           0.0s
 => CACHED [1/2] FROM docker.io/library/ubuntu:latest                                                                     0.0s
 => [2/2] RUN apt-get update && apt-get install -y nginx                                                                 13.2s
 => exporting to image                                                                                                    1.1s
 => => exporting layers                                                                                                   0.9s
 => => writing image sha256:cbd740e804635c1c741c5b854ff43f39cb54c1db0eea9842b4581aa5d6804ce6                              0.0s
 => => naming to docker.io/library/my-nginx:latest                                                                        0.0s

 ### docker run -d -p 80:80 my-nginx:latest
 9bd89bd029067b9066b7242ec06682e57715dc286beaaedeaade30c048d37170

 ### docker build -f docker/nginx/dockerfile -t my-nginx:latest .
[+] Building 0.5s (6/6) FINISHED                                                                                docker:default
 => [internal] load build definition from dockerfile                                                                      0.0s
 => => transferring dockerfile: 147B                                                                                      0.0s
 => [internal] load metadata for docker.io/library/ubuntu:latest                                                          0.0s
 => [internal] load .dockerignore                                                                                         0.0s
 => => transferring context: 2B                                                                                           0.0s
 => [1/2] FROM docker.io/library/ubuntu:latest                                                                            0.0s
 => CACHED [2/2] RUN apt-get update && apt-get install -y nginx                                                           0.0s
 => exporting to image                                                                                                    0.1s
 => => exporting layers                                                                                                   0.0s
 => => writing image sha256:67bc6c498dffebf2e0ae36104f30e284727d53cb53181fffea22c3690b259654                              0.0s
 => => naming to docker.io/library/my-nginx:latest                                                                        0.0s