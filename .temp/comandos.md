Fazer build
docker build -t kubernetes_ubuntu_lab .


docker run -it --name meu-kuber -v /var/run/docker.sock:/var/run/docker.sock kubernetes_ubuntu_lab bash


docker run -it --name teste-kuber kubernetes_ubuntu_lab bash

