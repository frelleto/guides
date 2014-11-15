Instalação
==

Utilizo o Docker para a instalação, tudo o que precisa para começar é baixar o arquivo do [Dockerfile com R][docker_r]

Construa sua imagem com:

    sudo docker build -t rocker/r-devel .

Rode no modo interativo:

    sudo docker run -ti rocker/r-devel /bin/bash

Quando quiser sair da máquina é só dar `exit` e depois commitar, exemplo:

    sudo docker ps -a
    sudo docker commit CONTAINNER_ID rocker/r-devel

[docker_r]: https://github.com/vagnerzampieri/docker-files/blob/master/r/debian/r-devel/Dockerfile
