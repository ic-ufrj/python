---
title: "04. Variáveis, atribuição, e strings"
---

Nós já compreendemos que algoritmos são sequências de ações destinadas a alcançar um objetivo. Até agora, os algoritmos que discutimos eram bastante simples, envolvendo principalmente a avaliação de expressões seguida ocasionalmente por testes (avaliação de expressões booleanas) que determinam qual expressão deve ser avaliada para calcular o valor a ser retornado pela função. Os cálculos realizados até o momento foram todos bastante diretos. No entanto, em muitas situações, os cálculos desejados podem ser complexos, e expressá-los em uma única expressão pode comprometer a clareza do código. Além disso, em alguns casos, o mesmo cálculo pode ser necessário várias vezes na resolução do problema. Para lidar com essas situações, é crucial ter a capacidade de armazenar o resultado de um cálculo para uso futuro, semelhante ao que fazemos ao resolver problemas em um caderno. As linguagens de programação fornecem o recurso de "anotar resultados" para uso posterior por meio das variáveis. Nesta aula, exploraremos o conceito e a utilização de variáveis, como atribuir valores a elas e como as variáveis simplificam a construção de funções, tornando-as mais legíveis. Além disso, abordaremos o tipo str (strings) em Python e introduziremos um novo tipo de dado: as tuplas.

### 1. Variáveis
Vamos começar abordando o conceito de variáveis. Durante a criação de códigos, é comum que as informações geradas necessitem ser armazenadas para uso posterior. Essas informações são mantidas na memória do computador, a qual é dividida em blocos onde os dados das soluções computacionais são armazenados e acessados por meio de operações de escrita e leitura. A identificação desses blocos de memória ocorre através de endereços, embora lidar diretamente com a memória do computador possa ser desafiador. Por isso, linguagens de programação como o Python oferecem uma abordagem simplificada para armazenar e acessar informações na memória, conhecida como variáveis. As variáveis representam uma maneira simbólica de referenciar dados armazenados na memória do computador.

No vídeo a seguir, vamos ver o que são variáveis e como utilizá-las.
{{< youtube id="p2ntlAcKnlQ" title="4- Variáveis e Atribuição, Strings: variáveis" >}}

Toda variável engloba os seguintes aspectos, semelhantes aos parâmetros de uma função:
- Nome (identificador): é a representação simbólica da variável, que será utilizada pelo
programador para fazer referência aos dados que ela armazena
- Valor: o que de fato está armazenado
- Tipo: o “tipo de dado” do dado que está armazenado nela

Observe agora os códigos das funções calcula_tinta e calcula_tinta2 a seguir. Estas funções foram ambas desenvolvidas para calcular a quantidade de latas de tinta necessária para pintar uma área, dados:
- a área a ser pintada, em metro quadrados,
- o rendimento da tinta (que área um litro de tinta pinta),
- a capacidade da lata (quantos litros tem em uma lata).

Elas fazem, de fato, a mesma coisa? Qual delas você acha mais fácil de entender?

```python
import math

def calcula_tinta(area, rendimento_tinta, capacidade_lata):
    """ quantidade de latas de tinta necessária para pintar uma área dado:
    a área a ser pintada, em metros quadrados,
    o rendimento da tinta (que área 1 litro de tinta pinta),
    a capacidade da lata (quantos litros tem em uma lata),
    float, float, float -> float """

    litros = area / rendimento_tinta
    quant_latas = math.ceil(litros / capacidade_lata)

    return quant_latas
```

```python
import math

def calcula_tinta2(area, rendimento_tinta, capacidade_lata):
    """ quantidade de latas de tinta necessária para pintar uma área dado:
    a área a ser pintada, em metros quadrados,
    o rendimento da tinta (que área 1 litro de tinta pinta),
    a capacidade da lata (quantos litros tem em uma lata),
    float, float, float -> float """

    return math.ceil(area / rendimento_tinta litros / capacidade_lata)
```
### 2. Comandos de atribuição

Conforme mencionado anteriormente, em Python, variáveis são criadas por meio de comandos de atribuição, onde o símbolo utilizado é o sinal de igual (=). É fundamental observar que à esquerda do operador de atribuição, apenas o nome (identificador) da variável deve estar presente. À direita, uma expressão é necessária, cujo valor será calculado e armazenado na variável. Essa expressão pode ser composta por operações aritméticas ou lógicas, utilizadas para realizar "cálculos", e pode incluir chamadas de outras funções.

Exemplos de atribuições:

```python
X = 500/2
```

```python
Cor = “vermelho”
```

```python
Mensagem = Cor + “ é uma cor viva.” 
# onde o uso do identificador Cor no lado direito da atribuição representa o valor armazenado na variável (no caso, a string “vermelho”)
```

```python
Y = f(X) 
# onde f é uma função definida como recebendo um argumento numérico para realizar sua função, seja ela qual for, e X representa o valor armazenado na variável (no caso, o float 250.0)
```

O processo de atribuição em Python segue um padrão consistente: avalia o resultado da expressão à direita do operador de atribuição e associa esse resultado à variável especificada à esquerda. No entanto, existe uma exceção conhecida como alias, que se refere a um sinônimo. Se a expressão à direita consistir apenas em outra variável, por exemplo, "var2 = var1", não ocorrerá uma avaliação separada da expressão "var1". Em vez disso, Python faz com que "var2" e "var1" apontem para a mesma posição na memória. Isso implica que ambas as variáveis compartilham o mesmo valor até que uma delas seja utilizada como lado esquerdo em outra atribuição, momento em que passam a apontar para diferentes posições na memória.

Assista agora ao segundo vídeo para ver um pouco mais sobre o armazenamento e leitura de valores na memória através de variáveis
{{< youtube id="uq1PUEkFutY" title="4- Variáveis e Atribuição, Strings: atribuição" >}}

### 3. Uso de variáveis

No próximo vídeo, exploraremos, por meio de um exemplo prático, como o uso de variáveis pode significativamente simplificar o código de um programa. Além disso, abordaremos a obtenção da data e hora atual em Python utilizando o módulo datetime. Estaremos focados em demonstrar como a implementação eficiente de variáveis pode tornar o código mais legível e fácil de manter, enquanto simultaneamente exploramos funcionalidades essenciais para lidar com tempo e data em Python.
{{< youtube id="E37uW-lsmQc" title="4- Variáveis e Atribuição, Strings: variáveis na simplificação de Funções" >}}

### 4. Tipos e escopo de variáveis

Python é uma linguagem de programação dinamicamente tipada, onde o tipo da variável é atribuído de acordo com o valor atribuído a ela, eliminando a necessidade de declaração prévia do tipo. Essa abordagem implica que o tipo de uma variável é determinado pelo tipo de dado que ela armazena. Em relação ao escopo de uma variável, este está associado tanto ao seu "tempo de vida" quanto à sua "visibilidade". Variáveis definidas dentro de uma função são destruídas quando a função é concluída e são criadas novamente a cada nova execução da função. Portanto, o "tempo de vida" de uma variável está vinculado ao período em que a função está em execução. A "visibilidade" de uma variável refere-se às partes do código onde é possível fazer referência a ela, ou seja, utilizá-la para acessar valores, limitando-se ao corpo da função onde foi definida.

**Resumindo:** Uma variável existe apenas dentro da função onde foi definida e não pode ser acessada fora da função.

Observe o código da produtoSomaDiferenca a seguir:

```python
def produtoSomaDiferenca(a,b):
    """ produto da soma pela diferença
    float, float -> float """
    x = a + b
    y = a - b 
    return x * y
```

Neste exemplo, as variáveis "x" e "y" são locais, confinadas ao escopo da função "produtoSomaDiferenca". Após a conclusão da função, essas variáveis são destruídas, limitando seu alcance ao contexto da função. Qualquer tentativa de referenciar essas variáveis fora da função resultaria em um erro. O próximo vídeo abordará minuciosamente os conceitos de tipo e escopo de variáveis, proporcionando uma compreensão mais aprofundada desses elementos na programação em Python.
{{< youtube id="V81Ri0Ovpf8" title="4- Variáveis e Atribuição, Strings: tipos e escopos de variáveis" >}}

**Atividade:** Vamos agora treinar um pouco com exercícios de fixação. Responda as perguntas da atividade “Variáveis ”. Fique atento ao prazo de entrega dessa atividade!

### 5. String
String é o termo frequentemente usado em programação para se referir a uma sequência de caracteres. Em Python, o nome do tipo de dados correspondente é str. Já sabemos como realizar algumas operações com o tipo str: concatenação e replicação. Para concatenar strings usamos o operador de concatenação, que é representado pelo símbolo “+”. Já o operador de replicação é representado pelo símbolo “*”.

Nesta aula estudaremos um pouco mais sobre strings em Python. Por exemplo, é possível fazer algum tipo de verificação sobre qual é o primeiro caractere de uma string? Ou o segundo? Ou o último? Sim. Isso é possível. Para isso, Python provê um mecanismo de indexação de elementos do tipo str. O primeiro caractere tem índice 0, o segundo, índice 1, e assim por diante. A sintaxe para requisitar o valor atribuído a um índice i de uma sequência S é S[i]. Assim, você pode, por exemplo, escrever uma expressão booleana para verificar se o primeiro caractere de S é ‘A’, por exemplo: S[0] == ‘A’.

Para saber o tamanho (a quantidade de caracteres) de uma string usamos a função len( ). Esta função recebe uma string como argumento e retorna o número de caracteres que essa string contém.

Outro operador interessante que pode ser usado com strings é o operador **in**. Ele é um operador que lembra o operador de pertinência de conjuntos da matemática (∈), ou seja, serve para verificar se a string que está à esquerda aparece "dentro" da string que está à direita (se uma é substring da outra), devolvendo o booleano True, caso apareça, e False, caso contrário. O operador **not in** corresponde à negação do **in**, devolvendo o booleano True, caso **não** apareça, e False, caso apareça. Aqui vamos exemplificar seu uso com strings.

**Exemplo:**
```python
 'a' in 'Maria'
 # o resultado deve ser True
```

```python
 'j' not in 'Maria'
 # o resultado deve ser True
```

```python
'a' not in 'Maria'
# o resultado deve ser False
```

Todo caractere de uma string é indexado, começando do primeiro caractere (índice 0) à esquerda. Por exemplo, a string “Amanda” possui os seguintes índices:

------ DESENHAR TABELA

Logo para acessarmos o caractere “n” desta string, basta informar: “Amanda”[3], pois o valor contido nesta posição indexada é “n”. Existe uma segunda maneira de fazer acesso a uma posição que será abordada no vídeo a seguir.
{{< youtube id="yP5ebC-yx7Y" title="4- Variáveis e Atribuição, Strings: Strings" >}}

### 6. Imutabilidade

Um detalhe importante é que não é possível usar o comando de atribuição botando à esquerda uma parte da string, ou seja, uma string indexada. Ou seja, assumindo que uma variável s tem o valor “pedro”, não é permitido escrever s[0] = “P”. Não podemos fazer uma atribuição a uma posição específica de uma string. 

As strings, assim como os dados numéricos, são dados imutáveis: uma vez criados, não se modificam, ou seja, não podemos mudar um pedaço dela (assim como não podemos mudar um pedaço de um número). Porém, as strings, assim como os dados numéricos, podem ser manipulados a fim de gerar novos dados (através de operações e funções). Assim como ao somar 1+1 obtemos um novo dado (o inteiro 2), operações com strings geram novas strings.

### 7. Operação de fatiamento

Já vimos como acessar um caractere em uma posição específica de uma dada string através da indexação. Mas podemos também gerar sub-strings (trechos da string original) de uma string fornecida e fazemos isto por meio da operação de fatiamento. No exemplo a seguir, podemos observar a operação de fatiamento.

```python
nome = "Amanda Pereira"
len(nome)
# o resultado deve ser 14
```

```python
sub_s1 = nome[0:6]
sub_s1
# o resultado deve ser 'Amanda'
```

A variável sub_s1 está recebendo a sub-string “Amanda” a partir da string contida na variável nome. O vídeo a seguir explica com maiores detalhes esta operação que é bastante usada.

Veja no vídeo a seguir mais informações sobre fatiamento de strings e imutabilidade.
{{< youtube id="bxHFR-Jf6vA" title="4- Variáveis e Atribuição, Strings: fatiamento e imutabilidade" >}}

### 8. Tuplas

Assim como as strings, uma tupla (tuple, em Python) é um tipo de dado do Python. Formalmente, uma tupla, assim como na matemática, é um elemento do produto cartesiano de dois ou mais conjuntos, ou seja, uma sequência ordenada de dados. Os dados em uma tupla podem ser de diferentes tipos: inteiros, floats, strings e até mesmo outras tuplas. Tuplas têm as mesmas propriedades de imutabilidade, indexação e fatiamento das strings. 

No Python, a sintaxe para representar a tupla é uma sequência de valores separados por vírgulas, podendo ou não estar entre parênteses. 

No vídeo a seguir, este novo tipo de dado será abordado.
{{< youtube id="49Yf2Sh0DAs" title="4- Variáveis e Atribuição, Strings, Tuplas: Tuplas" >}}

Agora que você já sabe o que é uma tupla, assista o próximo vídeo que traz mais alguns exemplos de uso deste tipo de dado. Repare que as tuplas e as strings têm muito em comum quanto à sua manipulação, incluindo as operações de indexação e fatiamento. Outra coisa em comum é que ambas tuplas e strings são tipos de dados imutáveis.
{{< youtube id="b_XxocPvadw" title="4 - Variáveis e Atribuição, Strings, Tuplas: Tuplas (mais exemplos)" >}}


Muito bem. Nesta aula falamos sobre variáveis, atribuições, tipo e escopo de uma variável. Aprendemos a usar strings de maneira mais sofisticada e vimos um novo tipo de dados: Tuplas, cujas formas de manipulação tem muito em comum com as strings. Discutimos sobre a operação de fatiamento e o conceito de imutabilidade. A seguir é apresentado um vídeo sobre erros comuns relacionados a alguns temas aqui abordados.
{{< youtube id="zkeCGBzdHTU" title="4- Variáveis e Atribuição, Strings, Tuplas: erros comuns" >}}

**Atividade:** Vamos agora treinar um pouco com exercícios de fixação. Procure se lembrar de todos os conceitos que você adquiriu ao longo desta aula e responda as perguntas da atividade “Manipulando strings e tuplas”. Fique atento ao prazo de entrega dessa atividade! Se tiver dúvidas, comente sobre elas na aula síncrona ou nos plantões de monitoria.

