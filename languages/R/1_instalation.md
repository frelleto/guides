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

Sempre que fizer algum exerxício, utilizarei testes.

Primeiro script
--
Para primeiro exercício farei um [fatorial][rosetta_factorial], ele vai servir para dar uma testada nas suas configurações.

Crie um arquivo `factorial.R`:

    factorial <- function(n) {
      if (n == 0) {
        return(1)
      } else {
        return(n * factorial(n - 1))
      }
    }

    # print(factorial(5))

Dando uma primeira olhada você consegue logo perceber uma semelhança com Javascript e reconhecer sua estrutura.

O script acima cria uma função recursiva para cálcular o fatorial, nesse caso o de 5, e o comentário no fim da linha é como faz para printar. A função é criada e atribuída a uma variável `factorial <- function(n)`.

Se quiser refatorar esse código pode ser feito assim:

    fact <- function(n) {
      if ( n <= 1 ) 1
      else n * fact(n-1)
    }

Só que acho uma forma pouco legível para fazer, e considero muito um código legível.

Para testar esse código, crie uma pasta `tests` e adicione o arquivo `test_factorial.R` e um outro chamado `run_tests.R`.

test_factorial.R:

    test_that("Factorial", {
      expect_that(factorial(2), equals(2))
      expect_that(factorial(3), equals(6))
      expect_that(factorial(10), equals(3628800))
    })

run_tests.R:

    library('testthat')
    source('factorial.R')
    test_dir('tests', reporter = 'Summary')

Para importar um pacote é com `library`, para carregar um arquivo é com `source` e o `test_dir` roda todos os testes de uma página em ordem alfabética.

Para rodar os testes:

    r tests/run_tests.R

Para rodar só a função:

    r factorial.R

Pacotes
--
Você pode achar a lista de pacotes de R em [cran.r-project.org][cran-r-project] e [inside-r.org][inside-r].

[docker_r]: https://github.com/vagnerzampieri/docker-files/blob/master/r/debian/r-devel/Dockerfile
[testthat]: https://github.com/hadley/testthat
[rosetta_factorial]: http://rosettacode.org/wiki/Factorial
[inside-r]: http://www.inside-r.org/packages
[cran-r-project]: http://cran.r-project.org/


