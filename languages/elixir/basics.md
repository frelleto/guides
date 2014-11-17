Basics
==

Assignments
--

    iex(1)> a = 2
    2
    iex(2)> 2 = a
    2
    iex(3)> a
    2
    iex(4)> 3 = a
    ** (MatchError) no match of right hand side value: 2

Em Elixir o sinal de `=` não é sinal de assignment e sim de assertion. Isso quer dizer que o Elixir faz o lado esquerdo ser igual ao lado direito, assim chamando `=` como um *match operator*.
