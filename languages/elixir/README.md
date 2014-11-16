Elixir
==

Instalação
--
Utilizo o Docker para a instalação, tudo o que precisa para começar é baixar o [Dockerfile][docker_elixir].

Construa a sua imagem com:

    sudo docker build -t elixir .

Rode no modo interativo:

    sudo docker run -ti elixir /bin/bash

Quando quiser sair da máquina é só dar `exit` e depois commitar, exemplo:

    sudo docker ps -a
    sudo docker commit CONTAINNER_ID elixir

Console
--
Para entrar no console do Elixir é só digitar `iex`,  para sair aperte `Ctrl+c` duas vezes.

    # iex
    Erlang/OTP 17 [erts-6.2] [source] [64-bit] [smp:4:4] [async-threads:10] [kernel-poll:false]

    Interactive Elixir (1.1.0-dev) - press Ctrl+C to exit (type h() ENTER for help)
    iex(1)>

Testes
--
Para a execução dos testes vou usar o próprio `ExUnit` que é nativo do Elixir.

[docker_elixir]: https://raw.githubusercontent.com/vagnerzampieri/docker-files/master/elixir/Dockerfile
