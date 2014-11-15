Basic objects
==

Em R,
> Tudo o que existe é um objeto. Tudo o que acontece é uma função. - John Chambers

Por exemplo, quando fazemos as estatísticas, muitas vezes alimentamos uma tabela de dados a uma equação de regressão linear e obtemos um grupo de coeficientes lineares.

O que basicamente acontece no R quando praticamos esse procedimento é que nós fornecemos um *objeto* chamado **data frame** que detém a tabela de dados, levá-lo para a *função* de modelo linear e pegar outro *objeto* chamado **list** consiste nas propriedades dos resultados da regressão, e extraindo em outro *objeto* chamado **numeric vector** na *list* para representar os coeficientes lineares.

Cada procedimento envolve diferentes tipos de objetos. Isto é exatamente o que acontece no mundo real.

Diferentes objetos tem diferentes objetivos e comportamentos. Isto é importante para entender como estes *objetos básicos* trabalham em ordem para resolver problemas do mundo real, com código mais elegante e poucos passos. Mais importante, este entendimento permitirá que gaste mais tempo na lógica da solução certa, em vez de o problema para produzir o código certo.

###Ordem de leitura dos arquivos:

 - Vector

