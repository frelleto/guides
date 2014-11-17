Basics
==

Assignments
--

    iex()> a = 2
    2

    iex()> 2 = a
    2

    iex()> a
    2

    iex()> 3 = a
    ** (MatchError) no match of right hand side value: 2

Em Elixir o sinal de `=` não é sinal de assignment e sim de assertion. Isso quer dizer que o Elixir faz o lado esquerdo ser igual ao lado direito e com isso o sucesso da operação, assim chamando `=` como um *match operator*.

More Complex Matches
--

    iex()> list = [1, 2, 3]
    [1, 2, 3]

    iex()> list = [1, 2, 3, [4, 5]]
    [1, 2, 3, [4, 5]]

    iex()> [a, 2, b, d] = list
    [1, 2, 3, [4, 5]]

    iex()> a
    1

    iex()> b
    3

    iex()> d
    [4, 5]

    iex()> [a, 2, b, d] == list
    true

O mais interessante ao falar sobre listas é evidênciar o que já foi dito sobre match e como atribuir para uma variável valores que vieram de um array.

No Elixir deve se montar um array para receber os valores `[a, 2, b, d] = list`, porém, o número `2` não vai receber a variável, mas vai comparar com o que estiver na lista, se tivesse o valor `3` por exemplo, iria dar erro `** (MatchError) no match of right hand side value: [1, 2, 3, [4, 5]]`.

Ignorando um valor com _(underscore)
--

    iex()> [a, _, _] = [1, 2, 3]
    [1, 2, 3]

    iex()> a
    1

Se você quiser ignorar outros valores que vem em um array é só usar o `_`.
