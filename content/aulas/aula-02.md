---
title: "02. Funções"
---

Na aula anterior aprendemos a definir e utilizar funções em Python. No Python, as funções são a estrutura base de organização de código de um dos estilos de programação mais simples e utilizados em nossos dias, que é a programação modular. Este estilo de programação é uma evolução surgida naturalmente a partir do paradigma de programação imperativo estruturado. Vamos entender um pouco cada um destes conceitos.

### Paradigmas e estilos de programação

O paradigma de programação determina o padrão para estruturação e execução do programa. Ele dita a visão que o programador deve adotar ao planejar a solução algorítmica para o problema sendo abordado, de forma que possa ser mais facilmente codificado na linguagem de programação. Assim sendo, o paradigma de programação a ser seguido deve ser escolhido antes da escrita do código. Uma curiosidade: algumas linguagens de programação permitem mais de um paradigma.

Neste curso será adotado o paradigma de programação **imperativo estruturado**, e o estilo **modular**. O nome "Imperativo" é uma referência ao tempo verbal imperativo, onde o programador diz ao computador, na forma de instruções ou comandos, o que deve ser feito seguindo uma ordem sequencial (faça isso, depois isso, depois aquilo...).  O termo "estruturado" refere-se ao uso de estruturas pré definidas para que o controle de execução (ou fluxo de execução) das instruções possa ser um pouco mais sofisticado do que a simples ordem sequencial. Por exemplo, o programador pode lançar mão de uma estrutura específica para que um conjunto de instruções seja repetido (veremos isso mais adiante no curso ;-).

Já o estilo se refere à maneira adotada para organizar o código, e influencia também a linha de raciocínio a ser adotada na expressão algorítmica que será construída para o problema, e posteriormente codificada na linguagem de programação desejada. No estilo modular, a construção de soluções (e consequentemente a organização de código) é norteada pela construção de módulos versáteis de código, ou seja, ao invés de um código grande pra fazer várias coisas, são feitos pequenos códigos (chamados módulos) que se destinam a fazer uma única coisa. A combinação destes módulos é que dá conta de realizar uma grande tarefa. Esse estilo é muito popular, por ter várias vantagens:
- a mais valorizada dentre as vantagens é a reutilização de código. Isso porque os módulos podem ser reutilizados na composição da solução de mais de um problema, se combinados de maneiras diferentes.

- outra vantagem importante é a possibilidade de testar cada módulo individualmente, o que é mais eficiente do que testar um código extenso só depois que ele estiver completamente escrito.

- em relação à elaboração de uma solução algorítmica (ou seja, na etapa anterior à construção do código) temos a vantagem de ser uma estratégia que ajuda a nortear o raciocínio.

Na linguagem Python, os módulos são as **funções**. Por isso estamos focando nosso estudo na construção de funções em Python.


## Uso articulado de funções

As funções são estruturas úteis não apenas para manter o código organizado, mas principalmente, para auxiliar o programador no processo de construção de soluções de programação para os problemas propostos. Usando funções, é possível atacar um problema complexo focando em partes menores deste problema, e articulando as soluções escritas para as partes menores para obter a solução do problema complexo. Veremos a seguir como escrever e utilizar uma ou mais funções para a solução de problemas simples.

Uma breve revisão do que vimos na aula passada: em programação funções são trechos de códigos com o objetivo de produzir um resultado. Assim como na matemática quando você deseja calcular uma função
```math {align="center" }
  $$f(x) = x^2$$ 
```

, na verdade você está realizando uma operação com o objetivo de saber qual é o valor do quadrado de x, uma vez que seja fornecido o valor de x. Em programação funções recebem parâmetros, podem realizar algum cálculo ou produzirem algum processamento e então retornam o valor do resultado. 

Na aula passada, construímos algumas funções para realizar operações matemáticas simples (tais como soma, sucessor, quadrado). Essas funções poderiam ser usadas, por exemplo, para a construção de um aplicativo de calculadora. No momento ainda não vamos trabalhar elementos de interface gráfica, mas você já fica sabendo que por trás de um aplicativo de calculadora com interface gráfica, estão trechos de código não muito diferentes dos que já sabemos construir. 

Vamos então ver como podemos articular o uso de funções para produzir soluções mais sofisticadas. Considere que deseja-se calcular a área da coroa circular  (anel) formada por dois círculos de raio `r1` e `r2`, respectivamente, nos quais `r1 > r2` e `Pi = 3.14`. Na geometria, coroa circular (ou anel) é uma região limitada por dois círculos concêntricos. Se denotamos por `r1` o raio da circunferência externa e por `r2` o raio da circunferência interna, a área da coroa é dada pela diferença entre a área do círculo externo e a área do círculo interno.

Vamos tentar escrever código para o problema do cálculo da coroa circular. O primeiro que temos a fazer é estudar o problema e planejar nossa solução. Já sabemos que, neste curso, atacaremos os problemas construindo uma função que retorne o resultado desejado. Vamos então planejar como será essa função:

**Problema:** calcular a área da coroa circular formada por dois círculos concêntricos de raios `r1` e `r2`. 
- O que deve ser feito? 
Para responder essa pergunta, tenho que descobrir como é calculada a área da coroa circular. 
Pesquisando na internet, um dos links encontrados é: [Coroa circular](https://brasilescola.uol.com.br/matematica/area-coroa-circular.htm) . Através da explicação dada neste site, a área da coroa circular é feita calculando a área do círculo maior, a área do círculo menor, e subtraindo uma da outra. Isso nos faz perceber que, para resolver este problema, temos que atacar também outro problema: calcular a área de um círculo. 
- Qual o resultado esperado? (o que será retornado pela função)
O valor numérico que representa a área (essa informação também é obtida estudando as informações do link de referência sobre a coroa circular).
- Quais as entradas?
Temos que fazer o levantamento de que informações devem ser fornecidas para que possamos fazer o cálculo desejado e obter o resultado. Iremos precisar dos raios de ambos os círculos, que podemos chamar de `r1` e `r2`. 
- Como faço isso no Python?

```math {align="center" } 
$$A_{coroa} = A_{circulomario} - A_{circulomenor}$$ 
```

Considerando que o círculo maior tem raio `r1` e o círculo menor tem raio `r2`:
```math {align="center" } 
    $$A_{coroa} = (π . r_1^2) - (π . r_2^2)$$
```

Para fazer essa conta no Python, tenho que escolher um valor para π. Não será interessante pedir pro usuário que deseja saber a área da coroa fornecer como entrada o valor de  π, uma vez que esse valor é fixo e não tem a ver com a situação específica do usuário. Para este problema, vamos usar uma aproximação de π com apenas duas casas decimais: `3.14`
Assim sendo, teremos: 
```math {align="center" }
    $$(3.14 * r_1^2) - (3.14 * r_2^2)$$
```

Passamos então para a fase de codificação e vamos escrever nossa função em Python:

```python
def coroa(r1,r2):
    '''calcula a area da cora circular dados os raios r1 e r2 de dois
    círculos concentricos, sendo r1 maior que r2
    '''
    return (3.14*r1**2)-(3.14*r2**2)
```

Esta é uma boa solução. Atende ao problema. Mas será que podemos pensar em uma solução mais organizada e mais fácil de ser construída? 

No vídeo a seguir, vamos ver como podemos projetar funções utilizando outras funções já implementadas e a importância desse conceito, para que seja possível a escrita de um código mais coeso e fácil de ser testado. 

{{< youtube id="Asq58VcqwwA" title="Decomposição de Funções">}}

Reparem que, uma vez que sabemos que funções podem ser reutilizadas, podemos fazer o planejamento da solução de um problema já imaginando a construção de mais de uma função. Isso nos permite trabalhar com pequenos problemas, focando em um de cada vez, ao invés de tentar pensar direto na solução de um problema mais complexo. 

**Exercício:** baixe o arquivo areas.py, que contém, além do código da função `pi`, da área do círculo e da coroa circular, também a função `arearetangulo`, que serve para calcular a área de um retângulo. Complemente este arquivo com outras duas funções:
1.	Usando uma ou mais funções que já estão prontas nesse arquivo, faça uma função para calcular a área da superfície de um cilindro reto. 
2.	Usando uma ou mais funções que já estão prontas nesse arquivo, faça uma função para calcular a área do quadrado. 
**`IMPORTANTE:`** Não pule a etapa de planejamento da solução! Acredite, essa etapa agiliza o seu trabalho e evita erros. 

Atividade: Agora você já teve sua primeira experiência de reutilização de código :-). Após terminar este exercício, responda a algumas perguntas sobre ele na atividade “reutilizando código”. Fique atento ao prazo de entrega dessa atividade!

**Dicas para não errar**

Algumas informações importantes quando trabalhamos com o uso articulado de funções: 
-	O Python só entende que uma função existe uma vez que a definição dela já foi feita. Ou seja, você só vai conseguir usar funções que existam (parece óbvio, mas não custa dizer…). Se quiser usar uma função que ainda não existe, você terá que construí-la.
-	Uma vez que uma função foi definida, ela pode ser usada quantas vezes desejarmos. Dessa forma, **só uma definição deve existir para cada função**, mesmo que ela seja usada duas ou mais vezes, ou até mesmo que seja usada por várias outras funções diferentes. Se o Python encontra duas definições para a mesma função, ele guarda a última encontrada apenas, descartando a anterior.
-   **Os parâmetros das funções são informações com escopo local**, ou seja, são nomes que dizem respeito apenas ao código da respectiva função, mesmo que haja várias funções em um mesmo arquivo. Isso significa que duas funções distintas podem até usar o mesmo nome para seus parâmetros, porém os parâmetros de uma nada terão a ver com os parâmetros da outra. 

**Atividade:** Para fixar seus conhecimentos, faça agora a atividade “jogo dos erros”. Fique atento ao prazo de entrega dessa atividade!


##	Argumentos default
Um outro conceito importante em Python é o da utilização de argumentos default, que são valores padrão fixos para um ou mais parâmetros de uma função. Estes são informados na definição da função. O vídeo a seguir vai mostrar como pode ser interessante usar estes argumentos:


{{< youtube id="8sj6D3GA73U" title="Argumentos Default">}}


**Exercício:** Considere a função potencia vista no vídeo. O que está errado no seguinte trecho de código:

```python
def potencia(y=2,x):
	return x**y
```