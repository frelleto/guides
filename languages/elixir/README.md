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

Primeiro script
--
Para primeiro exercício farei um [fatorial][rosetta_factorial], ele vai servir para testar as suas configurações.

Crie um arquivo chamado `factorial.exs`:

    defmodule Factorial do
      def calc(0), do: 1
      def calc(n), do: n * calc(n - 1)
    end

    # IO.puts Factorial.calc(5)

Vou detalhar mais no futuro, mas o `defmodule` é para criar um modulo em Elixir, esses métodos `calc` são assinados com `def`, nesse caso é possível fazer tudo em uma linha, mas se quiserem fazer com `if` e `else` não tem problema.

Para printar é só usar o `IO.puts`.

Crie uma pasta `tests` com o arquivo `tests/factorial_test.exs`:

    Code.require_file "../factorial.exs", __DIR__

    ExUnit.start

    defmodule Tests do
      use ExUnit.Case

      test "factorial 2 should be 2" do
        assert Factorial.calc(2) == 2
      end

      test "factorial 5 should be 120" do
        assert Factorial.calc(5) == 120
      end

      test "factorial 15 should be 1307674368000" do
        assert Factorial.calc(15) == 1307674368000
      end
    end

O `Code.require_file "../factorial.exs", __DIR__` ele carrega o arquivo `factorial.exs`,  o `ExUnit.start`  da start na ExUnit,  o módulo `ExUnit.Case` carrega outros módulos para ser feitos os testes.

Para rodar os testes:

    elixir tests/factorial_test.exs

Para rodar só a função:

    elixir factorial.exs

Ordem de leitura dos arquivos:
--

 - Basics

[docker_elixir]: https://raw.githubusercontent.com/vagnerzampieri/docker-files/master/elixir/Dockerfile
