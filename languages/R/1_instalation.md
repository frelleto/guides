R
==
Instalação
--

Utilizo o Docker para a instalação, tudo o que precisa para começar é baixar o arquivo do [Dockerfile com R][docker_r]

Construa sua imagem com:

    sudo docker build -t rocker/r-devel .

Rode no modo interativo:

    sudo docker run -ti rocker/r-devel /bin/bash

Quando quiser sair da máquina é só dar `exit` e depois commitar, exemplo:

    sudo docker ps -a
    sudo docker commit CONTAINNER_ID rocker/r-devel

Testes com testthat
--
No Dockerfile tem o [testthat][testthat], não tem a melhor das documentações, mas vou tentar detalhar sempre que possível.

O testthat é uma suite de testes que lembra a do RSpec, então quem usa Ruby não terá dificuldades.

Sempre que fizer algum exerxício, utilizarei testes.

[docker_r]: https://github.com/vagnerzampieri/docker-files/blob/master/r/debian/r-devel/Dockerfile
[testthat]: https://github.com/hadley/testthat
