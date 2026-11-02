![Cabeçalho](../imagens/cabecalho.png)

# Funções

Módulo Criar aplicações em linguagem de programação Python. Neste guia passas para Python, com `def` e `return`, as funções que já escrevias em pseudocódigo. Aprendes também a testar cada função sozinha antes de a usar. Para praticar, há o [laboratório](laboratorios/06-funcoes-laboratorio.md) e a [ficha de exercícios](exercicios/06-funcoes-exercicios.md) deste tema.

Na algoritmia, escreveste funções com `Função` e `devolver`, e seguiste as chamadas à mão. Agora é o computador que as executa. Com as funções, acaba a tradução para Python de tudo o que a algoritmia deu. Por isso, o exemplo guiado fecha com o quadro completo das diferenças. As funções deste tema recebem valores e devolvem um resultado, sem mudar as listas que recebem. As funções que mudam as listas que recebem ficam para o tema 09.

Lê-se ao teu ritmo, em várias vezes, com o computador ao lado. Cada exemplo pode ser copiado para um ficheiro e corrido.

## Neste guia

1. O que vais aprender
2. O que já sabes e vais usar
3. Porque é que se escrevem funções
4. Escrever uma função com `def` e `return`
5. Chamar uma função: parâmetros e argumentos
6. O `return` entrega o valor e termina a função
7. Uma chamada dentro de outra
8. A documentação de uma função
9. As variáveis de uma função são locais
10. Uma função sem `return` devolve `None`
11. As funções que calculam devolvem, e a parte principal escreve
12. A ordem no ficheiro: constantes, funções e parte principal
13. Testar cada função sozinha
14. Exemplo guiado: o resumo das notas de um teste, em Python
15. Erros frequentes
16. Palavras novas deste guia
17. Verificar o que aprendeste
18. O que vem a seguir

## O que vais aprender

No fim deste guia, consegues:

- escrever em Python, com `def` e `return`, uma função que já sabias escrever em pseudocódigo;
- distinguir os parâmetros dos argumentos e prever o valor que uma chamada devolve, também quando a chamada está dentro de outra;
- escrever a documentação de uma função, a dizer o que ela recebe e o que devolve;
- explicar porque é que as variáveis de uma função não existem fora dela;
- reconhecer o `None` de uma função que se esqueceu do `return`, e corrigir o erro;
- arrumar um script pela ordem constantes, funções e parte principal, e testar cada função sozinha antes de a usar.

## O que já sabes e vais usar

- Correr um script no terminal ou com o botão de correr do VS Code: guia [01 Do pseudocódigo ao Python](01-do-pseudocodigo-ao-python.md).
- O `print` com vários valores separados por vírgulas, e os comentários com `#`: guia [01 Do pseudocódigo ao Python](01-do-pseudocodigo-ao-python.md).
- Os três tipos de erro e o traceback lido de baixo para cima: guia [01 Do pseudocódigo ao Python](01-do-pseudocodigo-ao-python.md).
- Desligar uma linha com um `#` no início, e a opção Toggle Line Comment do menu Edit: guia [01 Do pseudocódigo ao Python](01-do-pseudocodigo-ao-python.md).
- A rotina de cinco passos para procurar um erro: [projeto 1, Duelo de dados](../01-algoritmos/projetos-guiados/05-projeto-1-duelo-de-dados.md) da algoritmia, secção "Passo 6: depurar com a rotina da depuração".
- As variáveis, os nomes com traço baixo e as constantes em maiúsculas: guia [02 Dados e interação](02-dados-e-interacao.md).
- Os tipos `int`, `float`, `str` e `bool`, e a divisão com `/`, que dá sempre um `float`: guia [02 Dados e interação](02-dados-e-interacao.md).
- O `None`, o valor que quer dizer "nenhum valor", e o seu tipo, `NoneType`: guia [02 Dados e interação](02-dados-e-interacao.md).
- O `print`, que escreve no ecrã e devolve `None`: guia [02 Dados e interação](02-dados-e-interacao.md).
- As funções predefinidas, como o `abs`, e o `input` com a conversão por `int` e por `float`: guia [02 Dados e interação](02-dados-e-interacao.md).
- O `if`, o `elif` e o `else`, as comparações, o `and`, o `or`, o `not` e os valores de fronteira: guia [03 Seleção](03-selecao.md).
- O `while`, o `for` com `range`, o contador e o acumulador: guia [04 Ciclos while e for](04-ciclos-while-e-for.md).
- As listas, os índices, o `len`, o `for` na lista e com o índice, e a lista vazia: guia [05 Listas](05-listas.md).
- A bandeira, o `break` e o `continue`: guia [05 Listas](05-listas.md).
- As funções em pseudocódigo, com `Função`, os parâmetros e o `devolver`: guia [05 Funções e modelo integrado](../01-algoritmos/05-funcoes-e-modelo-integrado.md) da algoritmia, secções "Escrever uma função" e "`devolver`".
- Os argumentos e as quatro fases de uma chamada: o mesmo guia da algoritmia, secções "Chamar uma função" e "O que acontece numa chamada".

## Porque é que se escrevem funções

Os teus programas já fazem muita coisa, e começam a repetir-se. Pensa num programa que mostra a média dos pontos de dois jogadores, a Ana e o Rui. Com o que sabes, cada média precisa de um acumulador e de um ciclo.

Antes de correres este exemplo, tenta prever as duas médias.

```python
# repetido.py: a média dos pontos de dois jogadores, com o mesmo ciclo escrito duas vezes.
pontos_ana = [12, 7, 20, 5]
pontos_rui = [9, 15, 6]

total = 0
for pontos in pontos_ana:
    total = total + pontos
print("Média da Ana:", total / len(pontos_ana))

total = 0
for pontos in pontos_rui:
    total = total + pontos
print("Média do Rui:", total / len(pontos_rui))
```

O resultado é este:

```text
Média da Ana: 11.0
Média do Rui: 10.0
```

Leitura guiada: o programa tem dois blocos quase iguais. Cada um põe o acumulador a 0, soma a lista com um `for` e divide o total pelo número de elementos. A única coisa que muda de um bloco para o outro é a lista.

Esta repetição traz três problemas. O primeiro é o trabalho: com dez jogadores, eram dez cópias do mesmo ciclo. E se houver um erro na conta, tem de ser corrigido em cada cópia. O segundo é a leitura: quem lê o programa tem de perceber cada ciclo para descobrir que ali se calcula uma média. O terceiro é o teste: a conta da média não se consegue experimentar sozinha, separada do resto.

Na algoritmia, resolveste estes problemas com uma **função**: um bloco de código com nome, que recebe valores, faz um trabalho e devolve um resultado. O ciclo da média escrevia-se uma vez, dentro de `Função media(valores)`, e cada média passava a ser uma chamada, como `media(pontosAna)`. Em Python é igual, e só muda a forma de escrever.

Repara que já usas funções em Python, mesmo sem lhes chamares assim. O `print`, o `len`, o `abs`, o `int` e o `input` são funções que já vêm com o Python. Usas cada uma escrevendo o nome e, entre parênteses, os valores que ela recebe. O `len([12, 7, 20])` devolve 3, e o `abs(-4)` devolve 4. Não precisas de saber como estão escritas por dentro para as usar. As funções que vais escrever neste tema usam-se exatamente da mesma maneira. A diferença é que o código delas está no teu ficheiro, e foste tu que o escreveste.

## Escrever uma função com `def` e `return`

Uma função do pseudocódigo passa para Python quase palavra a palavra:

| Pseudocódigo | Python |
| --- | --- |
| `Função areaRetangulo(comprimento, largura)` | `def area_retangulo(comprimento, largura):` |
| `devolver comprimento * largura` | `return comprimento * largura` |
| `float area = areaRetangulo(3, 2)` | `area = area_retangulo(3, 2)` |

A palavra `def` vem do inglês *define*, "definir". A primeira linha da função chama-se **cabeçalho**, como no pseudocódigo. Tem o `def`, o nome da função e, entre parênteses, os nomes dos valores que ela vai receber. Acaba com dois pontos, como a linha de um `if` ou de um `for`.

As linhas por baixo do cabeçalho, indentadas quatro espaços, são o **corpo** da função. O corpo acaba onde a indentação acaba, como no pseudocódigo. O `devolver` passa a `return`, do inglês "devolver", e faz o mesmo: entrega um valor a quem chamou a função.

O nome da função segue as regras dos nomes das variáveis: minúsculas, sem acentos, com traço baixo entre as palavras. Diz o que a função faz ou o que devolve, como `area_retangulo` ou `contar_positivas`. Um nome como `funcao1` ou `calcular` não diz nada a quem lê.

Antes de correres este exemplo, tenta prever as duas linhas que aparecem.

```python
# area.py: calcula a área de um retângulo com uma função.


def area_retangulo(comprimento, largura):
    """Devolve a área de um retângulo.

    Recebe o comprimento e a largura, dois números maiores do que zero,
    na mesma unidade. Devolve a área, na unidade ao quadrado.
    """
    return comprimento * largura


area = area_retangulo(3, 2)
print("Área:", area)
print("Outra área:", area_retangulo(1.5, 1.5))
```

O resultado é este:

```text
Área: 6
Outra área: 2.25
```

Leitura guiada: começa pelo cabeçalho, na linha do `def`. Logo por baixo, entre aspas triplas, `"""`, está a **documentação** da função. É um texto para quem a vai usar, que diz o que ela recebe e o que devolve. O Python guarda-a, mas não a executa, e a secção "A documentação de uma função" diz o que lá se escreve. A seguir vem o corpo, que aqui é só o `return`. O programa começa a fazer coisas na linha `area = area_retangulo(3, 2)`. Nessa linha, a função recebe o 3 e o 2, calcula 6 e devolve-o, e o 6 fica em `area`. Na última linha, a chamada está dentro do `print`, com outros valores, e devolve 2.25.

As linhas encostadas à margem que vêm depois da função são a **parte principal** do programa. É o que na algoritmia se chamava o algoritmo principal: a parte que usa as funções. Entre a função e o resto do programa ficam duas linhas em branco, antes e depois. É uma convenção do Python, para se ver bem onde a função começa e onde acaba.

Uma função escrita ainda não faz nada. O `def` só cria a função e lhe dá um nome. É como uma receita escrita num livro, que só dá um bolo quando alguém a segue. Se apagares as três linhas da parte principal e correres o `area.py`, o programa acaba sem escrever nada, e sem nenhum erro. A função existiu durante a execução, mas ninguém a usou.

Com o `def` e o `return`, o `repetido.py` do início do guia fica mais curto. O ciclo da média escreve-se uma vez, numa função, e cada jogador passa a ser uma chamada. Antes de correres, tenta prever as duas linhas.

```python
# duas_medias.py: a média dos pontos de dois jogadores, com uma função.


def media(valores):
    """Devolve a média de uma lista de números.

    Recebe uma lista de números, com pelo menos um. Devolve a média, um float.
    """
    total = 0
    for valor in valores:
        total = total + valor
    return total / len(valores)


pontos_ana = [12, 7, 20, 5]
pontos_rui = [9, 15, 6]
print("Média da Ana:", media(pontos_ana))
print("Média do Rui:", media(pontos_rui))
```

O resultado é o mesmo do `repetido.py`:

```text
Média da Ana: 11.0
Média do Rui: 10.0
```

Leitura guiada: o acumulador e o `for` estão agora uma só vez, dentro da função. Na parte principal, cada média é uma linha com uma chamada, e a lista do jogador vai como argumento. Para um terceiro jogador, basta mais uma linha com outra chamada. E se a conta da média tiver um erro, corrige-se num sítio só.

## Chamar uma função: parâmetros e argumentos

Usar uma função chama-se **chamar** a função. Escreve-se o nome dela e, entre parênteses, os valores que ela vai receber. No `area.py`, `area_retangulo(3, 2)` é uma chamada.

Há duas palavras para os valores que a função recebe: uma para o lado da função e outra para o lado da chamada. Os **parâmetros** são os nomes que estão no cabeçalho, como `comprimento` e `largura`. Os **argumentos** são os valores que se escrevem na chamada, como o 3 e o 2. Pensa numa caixa com etiqueta. O parâmetro é a etiqueta, escrita uma vez, no cabeçalho. O argumento é o que se põe dentro da caixa, e muda de chamada para chamada.

Uma chamada executa-se sempre em quatro fases, as mesmas da algoritmia. Na linha `area = area_retangulo(3, 2)`, são estas:

| Fase | O que acontece |
| --- | --- |
| 1 | Os argumentos passam para os parâmetros, pela ordem: `comprimento` fica com 3 e `largura` fica com 2 |
| 2 | O programa salta para dentro da função e executa o corpo, de cima para baixo |
| 3 | O `return comprimento * largura` calcula 6 e termina a função |
| 4 | O programa volta à linha da chamada, e a chamada é trocada pelo 6: a linha passa a ser `area = 6` |

A fase 4 é a que mais se esquece. Pensa na chamada como um buraco na linha onde está escrita. O programa vai à função buscar o valor, volta e tapa o buraco com ele. Ao valor que a função entrega chama-se **valor devolvido**. Por isso, uma chamada pode aparecer em qualquer sítio onde caberia um valor: numa atribuição, numa conta, num `print` ou numa condição.

A fase 1 tem um pormenor que engana. Os argumentos passam para os parâmetros pela ordem em que estão escritos, e não pelo nome. O primeiro argumento vai para o primeiro parâmetro, e o segundo para o segundo. Esta função calcula o preço de um jogo depois de um desconto em percentagem. Antes de correres, tenta prever as duas linhas.

```python
# desconto.py: o preço de um jogo depois de um desconto em percentagem.


def preco_com_desconto(preco, percentagem):
    """Devolve o preço depois de aplicado um desconto.

    Recebe o preço, em euros, e a percentagem do desconto, de 0 a 100.
    Devolve o preço com o desconto, um float.
    """
    return preco - preco * percentagem / 100


print(preco_com_desconto(50, 10))
print(preco_com_desconto(10, 50))
```

O resultado é este:

```text
45.0
5.0
```

Leitura guiada: na primeira chamada, `preco` fica com 50 e `percentagem` com 10, e a função tira 10% a 50 euros. Na segunda, os valores trocam de parâmetro. O `preco` fica com 10 e a `percentagem` com 50, e a função tira 50% a 10 euros. As duas contas são possíveis, e por isso o Python não dá nenhum aviso. Quem trocou a ordem só dá pelo erro se comparar o resultado com o que esperava. Antes de escreveres uma chamada, confirma a ordem dos parâmetros no cabeçalho ou na documentação.

Os argumentos não têm de ser números escritos à mão. Podem ser variáveis ou contas, como em `preco_com_desconto(preco_do_jogo, 25)`. O nome da variável do argumento não tem de ser igual ao do parâmetro. Na fase 1, o parâmetro `preco` fica com o valor de `preco_do_jogo`, e dentro da função só existe o nome `preco`.

## O `return` entrega o valor e termina a função

O `return` faz duas coisas ao mesmo tempo. Entrega o valor e termina a função. As linhas do corpo que estiverem por baixo dele, no mesmo caminho, já não se executam.

Por isso, uma função pode ter vários `return`, um em cada caminho de um `if`. Em cada chamada, executa-se só um deles. Esta é a função `maior` da algoritmia, em Python. Antes de correres, tenta prever as três linhas.

```python
# maior.py: o maior de dois números, com dois return.


def maior(a, b):
    """Devolve o maior de dois números.

    Recebe dois números, a e b. Se forem iguais, devolve esse valor.
    """
    if a > b:
        return a
    else:
        return b


print(maior(3, 8))
print(maior(8, 3))
print(maior(5, 5))
```

O resultado é este:

```text
8
8
5
```

Leitura guiada: em `maior(3, 8)`, a condição `3 > 8` é falsa, e a função segue pelo `else` e devolve `b`, que vale 8. Em `maior(8, 3)`, a condição é verdadeira, e a função devolve `a`, também 8. Em `maior(5, 5)`, a condição `5 > 5` é falsa, e a função devolve `b`, que vale 5. Em cada chamada, a função chega a exatamente um `return`.

Uma função também pode devolver `True` ou `False`. São as funções que respondem a uma pergunta de sim ou não, e usam-se diretamente num `if` ou num `while`. Um jogo com a classificação PEGI 12 é recomendado a partir dos 12 anos. Esta função diz se uma idade chega para ele. Antes de correres, tenta prever o que aparece se escreveres 11, e se escreveres 12.

```python
# pegi_funcao.py: diz se um jogo com classificação PEGI 12 se recomenda para uma idade.

IDADE_MINIMA = 12


def pode_jogar(idade):
    """Diz se um jogo PEGI 12 se recomenda para uma idade.

    Recebe a idade, um int. Devolve True se a idade for 12 ou mais,
    e False se for menor.
    """
    return idade >= IDADE_MINIMA


idade = int(input("Que idade tens? "))
if pode_jogar(idade):
    print("Este jogo é recomendado para a tua idade.")
else:
    print("Este jogo é recomendado a partir dos", IDADE_MINIMA, "anos.")
```

Com 11, o ecrã fica assim:

```text
Que idade tens? 11
Este jogo é recomendado a partir dos 12 anos.
```

Com 12, a segunda linha passa a ser `Este jogo é recomendado para a tua idade.`

Leitura guiada: a condição `idade >= IDADE_MINIMA` já dá `True` ou `False`, e por isso a função devolve-a diretamente, sem `if`. Com 11, `11 >= 12` dá `False`; com 12, `12 >= 12` dá `True`. Na parte principal, a chamada `pode_jogar(idade)` está no sítio da condição do `if`. O buraco é tapado com `True` ou `False`, e a linha lê-se como uma frase: se pode jogar, escreve a primeira mensagem. Repara que a função usa a constante `IDADE_MINIMA`, escrita no início do ficheiro.

Há uma regra que todas as funções que calculam um valor têm de cumprir. Em todos os caminhos possíveis, a função tem de chegar a um `return`. Pensa numa função que, para algum valor, chegasse ao fim do corpo sem passar por nenhum `return`. A linha que a chamou ficava com um buraco por tapar. A secção "Uma função sem `return` devolve `None`" mostra o que o Python faz nesse caso.

## Uma chamada dentro de outra

Já escreveste chamadas dentro de outras sem dar por isso. Em `print(len(pontos))`, a chamada ao `len` está dentro da chamada ao `print`. O Python tapa primeiro o buraco de dentro, com o valor que o `len` devolve. Só depois chama o `print`, com esse valor.

Com as tuas funções é igual. Para calcular uma chamada, o Python calcula primeiro os argumentos, da esquerda para a direita. Se um argumento for outra chamada, essa chamada faz as suas quatro fases primeiro. Só quando todos os argumentos são valores é que a chamada de fora começa.

Antes de correres este exemplo, tenta prever as três linhas. Faz as contas no caderno, de dentro para fora.

```python
# chamadas.py: chamadas de funções dentro de outras chamadas.


def dobro(numero):
    """Devolve o dobro de um número.

    Recebe um número, int ou float.
    """
    return numero * 2


def area_retangulo(comprimento, largura):
    """Devolve a área de um retângulo.

    Recebe o comprimento e a largura, dois números maiores do que zero,
    na mesma unidade. Devolve a área, na unidade ao quadrado.
    """
    return comprimento * largura


print(dobro(dobro(5)))
print(area_retangulo(dobro(2), 3))
print(area_retangulo(3, 2) + area_retangulo(1, 1))
```

O resultado é este:

```text
20
12
7
```

Leitura guiada: na primeira linha, a chamada de dentro é `dobro(5)`, que devolve 10. A linha passa a `print(dobro(10))`, e a chamada que sobra devolve 20. A segunda linha segue os passos desta tabela:

| Passo | O que se calcula | A linha passa a ser |
| ---: | --- | --- |
| 1 | `dobro(2)` devolve 4 | `print(area_retangulo(4, 3))` |
| 2 | `area_retangulo(4, 3)` devolve 12 | `print(12)` |
| 3 | o `print` escreve o 12 | nada mais para calcular |

Na terceira linha, há duas chamadas na mesma conta. A da esquerda devolve 6 e a da direita devolve 1, e só depois se faz a soma, que dá 7.

Quando uma chamada tiver várias camadas, lê-a sempre de dentro para fora, e reescreve a linha depois de cada passo, como na tabela. É assim que se prevê o valor de uma chamada que nunca viste.

Uma chamada também pode estar dentro do corpo de outra função. Uma função tua pode chamar outra função tua, como chama o `len`. Aqui, a `media` usa a `soma` para fazer a conta. Antes de correres, tenta prever o número que aparece.

```python
# soma_e_media.py: uma função tua que chama outra função tua.


def soma(numeros):
    """Devolve a soma dos números de uma lista.

    Recebe uma lista de números. Com a lista vazia, devolve 0.
    """
    total = 0
    for numero in numeros:
        total = total + numero
    return total


def media(numeros):
    """Devolve a média de uma lista de números.

    Recebe uma lista de números, com pelo menos um. Devolve a média, um float.
    """
    return soma(numeros) / len(numeros)


print(media([12, 7, 20, 5]))
```

O resultado é `11.0`.

Leitura guiada: a parte principal chama `media([12, 7, 20, 5])`, e a lista passa para o parâmetro `numeros`. No corpo da `media`, o `return` tem duas chamadas. A `soma(numeros)` faz as suas quatro fases e devolve 44, e o `len(numeros)` devolve 4. A conta passa a `44 / 4`, e a `media` devolve 11.0, que o `print` escreve. A `soma` está escrita por cima da `media`, para o ficheiro se ler de cima para baixo. Quando a chamada acontece, as duas já existem.

## A documentação de uma função

Uma função é escrita uma vez e usada muitas vezes, às vezes por outra pessoa, às vezes por ti, semanas depois. Quem a usa precisa de saber três coisas. Precisa de saber o que a função faz, que valores tem de lhe dar, e por que ordem, e o que ela devolve. Ler o corpo inteiro para o descobrir é lento, e nem sempre chega.

É para isso que serve a documentação. Em Python, a documentação de uma função escreve-se logo por baixo do cabeçalho, como um texto entre aspas triplas, `"""`. Chama-se **docstring**, do inglês *documentation string*, "texto de documentação". Com as aspas triplas, o texto pode ocupar várias linhas.

Nas aulas, a documentação tem sempre esta forma:

1. Na primeira linha, uma frase que diz o que a função faz ou o que devolve.
2. Uma linha em branco.
3. O que a função recebe: cada parâmetro, com o tipo e o que quer dizer.
4. O que a função devolve, com o tipo.
5. O que é preciso saber para a usar sem adivinhar, como um caso que ela não aceita ou o que faz com a lista vazia.

Esta é a documentação da função do desconto. Repara em cada parte:

```python
def preco_com_desconto(preco, percentagem):
    """Devolve o preço depois de aplicado um desconto.

    Recebe o preço, em euros, e a percentagem do desconto, de 0 a 100.
    Devolve o preço com o desconto, um float.
    """
    return preco - preco * percentagem / 100
```

A primeira linha diz o que a função devolve. A terceira diz o que é cada parâmetro e a ordem deles: primeiro o preço, depois a percentagem. Também diz entre que valores fica a percentagem. A quarta diz o que vem de volta, e de que tipo. Com estas linhas, quem usa a função não precisa de ler o `return`.

A documentação não é um comentário. Um comentário, com `#`, explica uma linha a quem lê o código. A documentação explica a função inteira a quem a vai usar. As aspas triplas têm de estar indentadas, como o corpo, porque a documentação faz parte da função. No VS Code, a extensão de Python é a que dá o botão de correr. Com ela, se passares o rato por cima do nome da função numa chamada, aparece uma caixa com a documentação.

Uma documentação vaga não serve. "Faz a conta" ou "Função do desconto" não diz o que entra nem o que sai. Pensa assim: um colega que só leia a documentação tem de conseguir escrever uma chamada certa e prever o resultado.

Nos exemplos de erros deste guia, as funções erradas têm só a primeira linha da documentação. É para o erro se ver melhor, e não um modelo a seguir.

## As variáveis de uma função são locais

Dentro de uma função nascem variáveis, como um acumulador. Pode acontecer que a parte principal tenha uma variável com o mesmo nome. A pergunta é se mexer numa mexe na outra.

Antes de correres este exemplo, tenta prever as duas linhas. Repara que há um `total` dentro da função e outro na parte principal.

```python
# locais.py: as variáveis de uma função só existem dentro dela.


def soma(numeros):
    """Devolve a soma dos números de uma lista.

    Recebe uma lista de números. Com a lista vazia, devolve 0.
    """
    total = 0
    for numero in numeros:
        total = total + numero
    return total


total = 100
resultado = soma([20, 30])
print("Resultado da soma:", resultado)
print("O total da parte principal:", total)
```

O resultado é este:

```text
Resultado da soma: 50
O total da parte principal: 100
```

Leitura guiada: a parte principal põe 100 em `total` e chama `soma([20, 30])`. Dentro da função, nasce outro `total`, que começa em 0 e chega a 50. A função devolve 50, que fica em `resultado`. O `total` da parte principal continua com 100, porque ninguém lhe mexeu. São duas variáveis diferentes, com o mesmo nome, em sítios diferentes.

Os parâmetros e as variáveis que nascem dentro de uma função chamam-se **variáveis locais** da função. Existem só enquanto a função se executa. Nascem em cada chamada e desaparecem quando a função devolve o seu valor. É por isso que, no guia 05 da algoritmia, cada chamada tinha a sua tabela de trace própria.

O contrário também acontece: uma variável local não se vê fora da função. Neste programa, a parte principal tenta escrever a variável que nasceu dentro da função:

```python
# locais_erro.py: tentar usar fora da função uma variável que nasceu lá dentro.


def soma(numeros):
    """Devolve a soma dos números de uma lista.

    Recebe uma lista de números. Com a lista vazia, devolve 0.
    """
    resultado = 0
    for numero in numeros:
        resultado = resultado + numero
    return resultado


soma([20, 30])
print("Resultado da soma:", resultado)
```

O programa para com esta mensagem:

```text
Traceback (most recent call last):
  File "C:\Users\aluno\Documents\fp-python\locais_erro.py", line 16, in <module>
    print("Resultado da soma:", resultado)
                                ^^^^^^^^^
NameError: name 'resultado' is not defined
```

Quer dizer "erro de nome: o nome `resultado` não está definido". O caminho do ficheiro, na linha `File`, é o do computador onde o programa correu, e no teu é outro. O `in <module>` quer dizer que a linha está fora de qualquer função, nas linhas encostadas à margem. A variável `resultado` existiu, mas só dentro da função, e desapareceu quando a função acabou. O valor 50 foi devolvido, mas a linha `soma([20, 30])` não o guardou em lado nenhum. A correção é guardá-lo: `resultado = soma([20, 30])`. Uma chamada a uma função que devolve um valor fica sempre dentro de alguma coisa: uma atribuição, uma conta, um `print` ou uma condição.

Daqui sai uma regra das aulas, a mesma do guia 05 da algoritmia. Uma função só usa os seus parâmetros, as suas variáveis locais, as constantes e outras funções, as tuas e as do Python. Tudo aquilo de que precisa chega-lhe pelos parâmetros, e tudo o que tem para dar sai pelo `return`. As constantes são a exceção, porque são regras do problema, que não mudam, e escrevem-se no início do ficheiro, antes das funções. O Python deixa uma função ler uma variável da parte principal, mas nas aulas não se faz. Uma função assim deixa de se poder testar sozinha, porque o resultado dela depende de uma coisa que a chamada não mostra.

## Uma função sem `return` devolve `None`

Um erro frequente com funções é a função que calcula, mas não devolve. Num trace à mão, nota-se pela falta de uma linha com o valor devolvido. No Python, vê-se no ecrã. Antes de correres este exemplo, tenta prever o que aparece.

```python
# sem_return.py: uma função que calcula mas se esquece de devolver.


def area_retangulo(comprimento, largura):
    """Devia devolver a área de um retângulo, mas falta-lhe o return."""
    resultado = comprimento * largura


area = area_retangulo(3, 2)
print("Área:", area)
print("O dobro da área:", area * 2)
```

O resultado é este:

```text
Área: None
Traceback (most recent call last):
  File "C:\Users\aluno\Documents\fp-python\sem_return.py", line 11, in <module>
    print("O dobro da área:", area * 2)
                              ~~~~~^~~
TypeError: unsupported operand type(s) for *: 'NoneType' and 'int'
```

Leitura guiada: a função calcula 6 e guarda-o em `resultado`, uma variável local, que desaparece quando a função termina. Como não há `return`, a função chega ao fim do corpo sem entregar nada. Nesse caso, o Python devolve o `None`, o valor que quer dizer "nenhum valor", que já conheces do `print`. É esse `None` que fica em `area` e que o primeiro `print` escreve. Na linha seguinte, a conta `area * 2` tenta multiplicar `None` por 2, e o programa para. A mensagem quer dizer "erro de tipo: o `*` não funciona entre um `NoneType` e um `int`". O `NoneType` é o tipo do `None`, como o `int` é o tipo do 2.

No tema 02, o `None` era o que o `print` devolvia. Agora aparece também quando uma função tua se esquece do `return`. Não é o número 0, nem um texto vazio. É a ausência de valor, e quase nenhuma conta ou comparação o aceita.

O erro deixa duas pistas, e convém reconhecer as duas. A primeira é ver `None` no ecrã, onde esperavas um número ou um texto. A segunda é uma mensagem com `NoneType`, numa linha que usa o valor devolvido. As duas querem dizer o mesmo: a função não chegou a um `return`. Repara que a linha que a mensagem aponta é a da conta, mas a causa está na função, que não devolveu. A correção é acrescentar `return resultado` como última linha do corpo, ou escrever logo `return comprimento * largura`.

## As funções que calculam devolvem, e a parte principal escreve

Há outra forma de uma função parecer certa e não devolver nada: escrever o resultado com `print` em vez de o devolver. Esta função devia calcular a média de uma lista, e o programa devia dizer se a turma passou. Antes de correres, tenta prever o que aparece.

```python
# escreve.py: uma função que escreve a média em vez de a devolver.


def media(valores):
    """Devia devolver a média de uma lista de números, mas escreve-a."""
    total = 0
    for valor in valores:
        total = total + valor
    print("Média:", total / len(valores))


media_do_teste = media([12, 15, 9])
if media_do_teste >= 10:
    print("A turma passou")
```

O resultado é este:

```text
Média: 12.0
Traceback (most recent call last):
  File "C:\Users\aluno\Documents\fp-python\escreve.py", line 13, in <module>
    if media_do_teste >= 10:
       ^^^^^^^^^^^^^^^^^^^^
TypeError: '>=' not supported between instances of 'NoneType' and 'int'
```

Leitura guiada: a média aparece no ecrã, e por isso a função parece certa. Mas o `print` só mostra o valor a quem está a olhar para o ecrã. O valor não volta para a parte principal. A função acaba sem `return` e devolve `None`, que fica em `media_do_teste`. Na linha do `if`, a comparação `None >= 10` não se consegue fazer, e o programa para. A mensagem quer dizer "o `>=` não funciona entre um `NoneType` e um `int`".

Já viste no tema 02 que o próprio `print` não devolve nada que sirva: escreve no ecrã e devolve `None`. Uma função que acaba num `print` herda o mesmo problema. Mostra o valor, mas não o entrega.

Daqui sai a regra da algoritmia, que continua a valer: as funções que calculam devolvem, e quem escreve no ecrã é a parte principal. Na função da média, o `print` dá lugar a `return total / len(valores)`. A parte principal guarda o valor numa variável e decide o que fazer com ele: escrevê-lo, compará-lo ou usá-lo noutra conta. Uma função que devolve serve para tudo isto. Uma função que só escreve serve só para escrever, sempre com a mesma frase.

Pela mesma razão, uma função que calcula também não lê do teclado. É a parte principal que pergunta, com o `input`, e que passa o valor à função como argumento. Assim, a função testa-se com qualquer valor, sem ninguém ter de o escrever.

## A ordem no ficheiro: constantes, funções e parte principal

Um script com funções arruma-se sempre pela mesma ordem, de cima para baixo:

1. o comentário do topo, que diz o que o programa faz;
2. as constantes;
3. as funções, cada uma com a sua documentação e com duas linhas em branco antes e depois;
4. as linhas de teste das funções, desligadas com `#`, quando as há;
5. a parte principal, encostada à margem, que usa as funções.

A ordem não é só uma convenção. O Python executa o ficheiro de cima para baixo, uma linha de cada vez. A linha do `def` é a que cria a função. Antes de o Python passar por ela, a função ainda não existe. Neste programa, a chamada aparece antes do `def`:

```python
# ordem.py: a chamada aparece antes do def.

area = area_retangulo(3, 2)
print("Área:", area)


def area_retangulo(comprimento, largura):
    """Devolve a área de um retângulo.

    Recebe o comprimento e a largura, dois números maiores do que zero,
    na mesma unidade. Devolve a área, na unidade ao quadrado.
    """
    return comprimento * largura
```

O programa para logo na linha 3:

```text
Traceback (most recent call last):
  File "C:\Users\aluno\Documents\fp-python\ordem.py", line 3, in <module>
    area = area_retangulo(3, 2)
           ^^^^^^^^^^^^^^
NameError: name 'area_retangulo' is not defined
```

Quer dizer "erro de nome: o nome `area_retangulo` não está definido". Na linha 3, o Python ainda não chegou ao `def` da linha 7, e por isso não conhece o nome. A função está escrita no ficheiro, mas ainda não foi criada. Corrige-se pondo a função antes da parte principal.

As constantes ficam no início por clareza: são as regras do problema, e quem lê o ficheiro vê-as logo. Para o Python, basta que uma constante exista antes da primeira chamada da função que a usa. O corpo da função só corre quando ela é chamada. A parte principal vem no fim porque é ela que usa tudo o resto. As funções têm de estar criadas antes das linhas que as chamam.

## Testar cada função sozinha

Um programa com três funções e uma parte principal pode falhar em quatro sítios. Se só o testares inteiro, e o resultado vier errado, não sabes por onde começar. A solução é testar cada função sozinha, com poucos casos, antes de a usar. O guia 05 da algoritmia fazia-o à mão, e em Python é o computador que faz as contas.

Testar uma função sozinha é chamá-la com valores escolhidos e comparar o que ela devolve com o que esperavas. Faz-se por esta ordem:

1. Escreve a função, com a documentação.
2. Escolhe os casos de teste a partir da documentação, antes de olhar para o corpo. Para cada fronteira, o valor de baixo, o da fronteira e o de cima. Para uma função que recebe uma lista, a lista vazia, se a função a aceitar, uma lista com um elemento e uma com vários.
3. Calcula à mão o que a função deve devolver em cada caso.
4. Escreve as **linhas de teste**: um `print` com a chamada e o valor esperado, depois das funções e antes da parte principal.
5. Corre o programa e compara, linha a linha, o devolvido com o esperado.

Esta é a função do PEGI, com as três linhas de teste da fronteira dos 12 anos. Antes de correres, escreve no caderno o que esperas em cada linha.

```python
# pegi_testes.py: a função do PEGI, testada sozinha na fronteira dos 12 anos.

IDADE_MINIMA = 12


def pode_jogar(idade):
    """Diz se um jogo PEGI 12 se recomenda para uma idade.

    Recebe a idade, um int. Devolve True se a idade for 12 ou mais,
    e False se for menor.
    """
    return idade >= IDADE_MINIMA


# Testes da função sozinha: o valor devolvido e o que se esperava.
print(pode_jogar(11), "esperado: False")
print(pode_jogar(12), "esperado: True")
print(pode_jogar(13), "esperado: True")
```

O resultado é este:

```text
False esperado: False
True esperado: True
True esperado: True
```

Leitura guiada: cada linha de teste escreve primeiro o valor que a função devolveu, e depois o texto com o que se esperava. Basta comparar as duas metades de cada linha. Aqui, as três batem certo. O 12, a fronteira, é o caso que mais interessa: é o que apanha um `>` escrito no lugar do `>=`.

Quando todas as linhas batem certo, a função está pronta a usar, e escreve-se a parte principal. As linhas de teste já não fazem falta na saída do programa, mas é bom guardá-las. Se um dia mudares a função, voltas a ligá-las e confirmas que tudo continua certo. Para as desligar, põe um `#` no início de cada uma, e o Python passa a tratá-las como comentários. No VS Code, selecionas as linhas e escolhes, no menu Edit, a opção Toggle Line Comment, isto é, "ligar ou desligar o comentário da linha". O VS Code põe ou tira o `#` de todas ao mesmo tempo. O atalho de teclado que faz o mesmo aparece ao lado da opção, no menu.

Quando uma linha não bate certo, há duas hipóteses: a função está errada, ou o valor esperado foi mal calculado. Volta ao enunciado e refaz a conta à mão. Se o esperado estiver certo, segue a rotina de cinco passos dentro da função. Usa o caso que falhou, que já é o caso mais curto.

## Exemplo guiado: o resumo das notas de um teste, em Python

### Passo 1: o problema

Este problema é o do exemplo guiado do guia 05 da algoritmia, onde está resolvido em pseudocódigo:

> Um professor guardou numa lista as notas de um teste, todas inteiras: `notas = [14, 9, 17, 10, 6, 16]`. Quer um programa que, antes de mais nada, confirme que todas as notas estão na escala de 0 a 20. Se houver alguma nota fora da escala, o programa escreve "Há notas inválidas" e não calcula mais nada. Se estiverem todas certas, escreve a média da turma e quantas notas são positivas, ou seja, 10 ou mais.

O pseudocódigo do passo 2 já resolve o problema. Falta traduzi-lo, testar as funções sozinhas e pôr o computador a confirmar os resultados que se calculam à mão.

### Passo 2: o pseudocódigo

Este é o algoritmo, com três funções e o algoritmo principal. A função `notaValida` diz se uma nota está na escala. A `media` calcula a média de uma lista, e a `contarPositivas` conta as notas de 10 ou mais.

```text
const NOTA_MINIMA = 0
const NOTA_MAXIMA = 20
const LIMIAR_POSITIVA = 10

Função notaValida(nota)
    devolver nota >= NOTA_MINIMA e nota <= NOTA_MAXIMA

Função media(valores)
    int quantidade = 0
    int total = 0
    Para cada valor em valores
        quantidade = quantidade + 1
        total = total + valor
    devolver total / quantidade

Função contarPositivas(notas)
    int positivas = 0
    Para cada nota em notas
        Se nota >= LIMIAR_POSITIVA
            positivas = positivas + 1
    devolver positivas

notas = [14, 9, 17, 10, 6, 16]
bool todasValidas = true
Para cada nota em notas
    Se notaValida(nota) == false
        todasValidas = false
        Parar
Se todasValidas
    float mediaDaTurma = media(notas)
    int positivas = contarPositivas(notas)
    Escreve: "Média: ", mediaDaTurma
    Escreve: "Positivas: ", positivas
Senão
    Escreve: "Há notas inválidas"
```

### Passo 3: traduzir linha a linha

Cada tipo de linha do pseudocódigo tem a sua tradução, e todas estão neste guia e nos dos temas anteriores:

| No pseudocódigo | No Python | O que muda |
| --- | --- | --- |
| `const NOTA_MINIMA = 0` | `NOTA_MINIMA = 0` | sem `const`; as maiúsculas dizem que é constante |
| `Função notaValida(nota)` | `def nota_valida(nota):` | `def`, o nome com traço baixo e os dois pontos |
| `devolver nota >= NOTA_MINIMA e nota <= NOTA_MAXIMA` | `return nota >= NOTA_MINIMA and nota <= NOTA_MAXIMA` | `return` e `and` |
| `int quantidade = 0` | `quantidade = 0` | sem o tipo |
| `Para cada valor em valores` | `for valor in valores:` | `for`, `in` e os dois pontos |
| `Se nota >= LIMIAR_POSITIVA` | `if nota >= LIMIAR_POSITIVA:` | `if` e os dois pontos |
| `bool todasValidas = true` | `todas_validas = True` | sem o tipo; `True` com maiúscula; o nome com traço baixo |
| `Parar` | `break` | só a palavra |
| `Senão` | `else:` | `else` e os dois pontos |
| `Escreve: "Média: ", mediaDaTurma` | `print("Média:", media_da_turma)` | sem o espaço dentro das aspas |

E há uma coisa que no algoritmo não se escrevia: a documentação de cada função, por baixo do cabeçalho.

### Passo 4: as funções, testadas sozinhas

Primeiro escrevem-se as constantes e as três funções, e as linhas de teste. A parte principal ainda não existe. Os casos de teste escolhem-se pela documentação. Para `nota_valida`, são os três valores de cada uma das duas fronteiras, a do 0 e a do 20. Para `media`, que não aceita a lista vazia, são uma lista com um elemento e listas com vários. Para `contar_positivas`, que aceita a lista vazia, são a lista vazia, os valores à volta da fronteira do 10 e a lista do enunciado. Antes de correres, confirma no caderno, à mão, cada valor esperado.

```python
# resumo_notas.py: confirma que as notas de um teste estão na escala de 0 a 20
# e, se estiverem, mostra a média da turma e quantas notas são positivas.

NOTA_MINIMA = 0
NOTA_MAXIMA = 20
LIMIAR_POSITIVA = 10


def nota_valida(nota):
    """Diz se uma nota está na escala.

    Recebe uma nota, um int. Devolve True se ela estiver entre 0 e 20,
    incluindo os extremos, e False se não estiver.
    """
    return nota >= NOTA_MINIMA and nota <= NOTA_MAXIMA


def media(valores):
    """Calcula a média de uma lista de números.

    Recebe uma lista de números, com pelo menos um: com a lista vazia,
    a conta seria 0 / 0, e o programa parava com um erro.
    Devolve a média, um float.
    """
    quantidade = 0
    total = 0
    for valor in valores:
        quantidade = quantidade + 1
        total = total + valor
    return total / quantidade


def contar_positivas(notas):
    """Conta as notas positivas de uma lista de notas válidas.

    Recebe uma lista de notas, ints de 0 a 20. Devolve quantas são
    10 ou mais, um int. Com a lista vazia, devolve 0.
    """
    positivas = 0
    for nota in notas:
        if nota >= LIMIAR_POSITIVA:
            positivas = positivas + 1
    return positivas


# Testes das funções sozinhas: o valor devolvido e o que se esperava.
print(nota_valida(-1), "esperado: False")
print(nota_valida(0), "esperado: True")
print(nota_valida(1), "esperado: True")
print(nota_valida(19), "esperado: True")
print(nota_valida(20), "esperado: True")
print(nota_valida(21), "esperado: False")
print(media([10]), "esperado: 10.0")
print(media([0, 20]), "esperado: 10.0")
print(media([14, 9, 17, 10, 6, 16]), "esperado: 12.0")
print(contar_positivas([]), "esperado: 0")
print(contar_positivas([9]), "esperado: 0")
print(contar_positivas([10]), "esperado: 1")
print(contar_positivas([11]), "esperado: 1")
print(contar_positivas([14, 9, 17, 10, 6, 16]), "esperado: 4")
```

O resultado é este:

```text
False esperado: False
True esperado: True
True esperado: True
True esperado: True
True esperado: True
False esperado: False
10.0 esperado: 10.0
10.0 esperado: 10.0
12.0 esperado: 12.0
0 esperado: 0
0 esperado: 0
1 esperado: 1
1 esperado: 1
4 esperado: 4
```

Leitura guiada: as catorze linhas batem certo. Os valores de `media` vêm com o ponto zero, porque a divisão com `/` dá sempre um `float`. É por isso que o esperado já se escreveu `10.0`. A função `media` conta os elementos com um contador, como no pseudocódigo. Agora que conheces o `len`, `len(valores)` dava o mesmo número. A tradução linha a linha é a primeira versão, e só depois se procura a forma mais curta. Com as funções testadas, desligam-se as catorze linhas de teste com um `#` no início de cada uma.

### Passo 5: a parte principal

A parte principal escreve-se a seguir às linhas de teste, já desligadas, encostada à margem. É o algoritmo principal do passo 2, traduzido com a tabela do passo 3. Antes de correres, prevê as duas linhas.

```python
notas = [14, 9, 17, 10, 6, 16]
todas_validas = True
for nota in notas:
    if nota_valida(nota) == False:
        todas_validas = False
        break
if todas_validas:
    media_da_turma = media(notas)
    positivas = contar_positivas(notas)
    print("Média:", media_da_turma)
    print("Positivas:", positivas)
else:
    print("Há notas inválidas")
```

O resultado é este:

```text
Média: 12.0
Positivas: 4
```

Leitura guiada: a bandeira `todas_validas` começa em `True`, e passa a `False` à primeira nota inválida, com o `break` a parar o ciclo. A chamada `nota_valida(nota)` está no sítio da condição do `if`, e o `== False` traduz à letra o `== false` do pseudocódigo. O `not nota_valida(nota)` fazia o mesmo. As duas funções de cálculo só são chamadas dentro do `if todas_validas`, quando já se sabe que as notas são válidas. A lista do problema tem pelo menos uma nota, e por isso a `media` nunca recebe uma lista vazia. Os valores devolvidos guardam-se em variáveis com nomes que dizem o que são, e quem os escreve é a parte principal. Repara também nos nomes. A `nota` do ciclo da parte principal, o parâmetro `nota` de `nota_valida` e a `nota` de `contar_positivas` são três variáveis diferentes. Cada uma vive no seu sítio.

O ficheiro completo fica com as partes por esta ordem:

```text
resumo_notas.py
    o comentário do topo
    as constantes: NOTA_MINIMA, NOTA_MAXIMA e LIMIAR_POSITIVA
    as funções: nota_valida, media e contar_positivas
    as linhas de teste das funções sozinhas, desligadas com #
    a parte principal
```

### Passo 6: correr os casos do problema

Os casos de teste do problema inteiro são listas diferentes. Antes de correres, calcula à mão a saída de cada um. Para correr cada caso, muda-se a linha `notas = [...]` e corre-se outra vez.

| Notas | Esperado, calculado à mão | O que o Python mostra |
| --- | --- | --- |
| `[14, 9, 17, 10, 6, 16]` | Média 12; 4 positivas | `Média: 12.0` e `Positivas: 4` |
| `[10]` | Média 10; 1 positiva | `Média: 10.0` e `Positivas: 1` |
| `[9]` | Média 9; 0 positivas | `Média: 9.0` e `Positivas: 0` |
| `[0, 20]` | Média 10; 1 positiva | `Média: 10.0` e `Positivas: 1` |
| `[12, 21, 8]` | Há notas inválidas | `Há notas inválidas` |

Os cinco casos dão o que se calculou à mão. A única diferença está na forma da média, `12.0` em vez de 12. Tem a ver com a divisão no Python, e não com a lógica. Como as funções já estavam testadas sozinhas, um erro aqui só podia estar na parte principal.

### Passo 7: o quadro das diferenças

Com as funções, traduziste para Python tudo o que a algoritmia deu. Este é o quadro completo do que muda, para teres numa página só. Vai servir em cada tradução que fizeres:

| O que muda | No pseudocódigo | No Python |
| --- | --- | --- |
| O tipo das variáveis | escreve-se onde a variável nasce | não se escreve |
| As constantes | `const` | só o nome em maiúsculas |
| Os nomes compostos | `mediaDaTurma` | `media_da_turma` |
| Os valores lógicos | `true`, `false` | `True`, `False` |
| Os operadores lógicos | `e`, `ou`, `não` | `and`, `or`, `not` |
| O início de um bloco | só a indentação | os dois pontos e a indentação |
| A escrita no ecrã | `Escreve:`, com os espaços dentro das aspas | `print`, que põe os espaços sozinho |
| A leitura | `Escreve:` e `ler valor` | `input`, e a conversão com `int` ou `float` |
| A divisão | `7 / 2` dá 3.5, e uma conta exata dá um inteiro | `/` dá sempre um `float`, como `12.0` |
| A divisão inteira e o resto | `div`, `resto` | `//`, `%` |
| A seleção | `Se`, `Senão se`, `Senão` | `if`, `elif`, `else` |
| O ciclo com condição | `Enquanto` | `while` |
| O ciclo contado | `Para i de 1 até 10` e `Para i = 0, i < 10, i++` | `for i in range(1, 11):` e `for i in range(0, 10):` |
| O array | `notas = [12, 8, 15]` | uma lista, escrita da mesma maneira |
| Percorrer o array | `Para cada nota em notas` | `for nota in notas:` |
| O `Parar` e o `Continuar` | `Parar`, `Continuar` | `break`, `continue` |
| O cabeçalho de uma função | `Função nome(parametros)` | `def nome(parametros):` |
| Devolver um valor | `devolver` | `return` |
| A documentação de uma função | não se escrevia no algoritmo | o texto entre aspas triplas, por baixo do cabeçalho |

O que não mudou é o mais importante: as decisões, os ciclos, as funções e os casos de teste. Foi isso que pensaste na algoritmia, e foi isso que o computador confirmou.

## Erros frequentes

Os erros desta secção não ficaram em nenhuma das secções anteriores. Os outros estão na secção da ideia que explicam:

- os argumentos trocados, em "Chamar uma função: parâmetros e argumentos";
- a variável local usada fora da função e o valor devolvido que se perde, em "As variáveis de uma função são locais";
- a função sem `return`, em "Uma função sem `return` devolve `None`";
- o `print` no lugar do `return`, em "As funções que calculam devolvem, e a parte principal escreve";
- a chamada antes do `def`, em "A ordem no ficheiro: constantes, funções e parte principal".

### O `return` dentro do ciclo

O que se vê: a função devolve um valor errado, sem nenhuma mensagem. Nesta versão de `contar_positivas`, o `return` ficou com oito espaços, dentro do `for`:

```python
def contar_positivas(notas):
    """Conta as notas positivas de uma lista de notas válidas."""
    positivas = 0
    for nota in notas:
        if nota >= LIMIAR_POSITIVA:
            positivas = positivas + 1
        return positivas
```

Com `[14, 9, 17]`, devolve 1 em vez de 2. Com `[9, 14, 17]`, devolve 0. Com a lista vazia, devolve `None`.

Porque acontece: o `return` termina a função. Dentro do ciclo, termina-a logo na primeira volta, depois de ver só o primeiro elemento. Com a lista vazia, o ciclo não dá nenhuma volta, a função nunca chega ao `return` e devolve `None`.

Como se corrige: o `return` fica com quatro espaços, encostado ao `for`, para se executar uma vez, depois de o ciclo acabar. Os testes com a lista vazia e com uma lista de vários elementos apanham este erro. Um teste só com um elemento não o apanha.

### A chamada sem parênteses

O que se vê, com `print("Média:", media)` num programa que tem a função `media`:

```text
Média: <function media at 0x104217480>
```

O número do fim muda de computador para computador, e de execução para execução.

Porque acontece: sem os parênteses, não há chamada. O `media` sozinho é a própria função, e o `print` escreve-a como `<function media at ...>`, isto é, "a função `media`, guardada neste sítio da memória". A função nunca se executou.

Como se corrige: a chamada leva sempre os parênteses, com os argumentos dentro: `print("Média:", media(notas))`.

### O número de argumentos errado

O que se vê, com `area_retangulo(3)`, que só tem um argumento para dois parâmetros:

```text
TypeError: area_retangulo() missing 1 required positional argument: 'largura'
```

Quer dizer "erro de tipo: falta à `area_retangulo` um argumento obrigatório, o `largura`". Com argumentos a mais, como `area_retangulo(3, 2, 5)`, a mensagem é outra:

```text
TypeError: area_retangulo() takes 2 positional arguments but 3 were given
```

Quer dizer "a `area_retangulo` recebe 2 argumentos, mas foram dados 3".

Porque acontece: cada parâmetro tem de receber exatamente um argumento. A chamada tem de ter tantos argumentos quantos os parâmetros do cabeçalho.

Como se corrige: confirma no cabeçalho, ou na documentação, quantos parâmetros a função tem e por que ordem. Depois escreve a chamada com um argumento para cada um.

### A média de uma lista vazia

O que se vê num ficheiro `vazia.py` com a função `media` do exemplo guiado e uma parte principal com duas linhas, `notas = []` e `print("Média:", media(notas))`:

```text
Traceback (most recent call last):
  File "C:\Users\aluno\Documents\fp-python\vazia.py", line 20, in <module>
    print("Média:", media(notas))
                    ~~~~~^^^^^^^
  File "C:\Users\aluno\Documents\fp-python\vazia.py", line 16, in media
    return total / quantidade
           ~~~~~~^~~~~~~~~~~~
ZeroDivisionError: division by zero
```

Quer dizer "erro de divisão por zero". Este traceback tem duas linhas `File`, porque o erro aconteceu dentro de uma função. Lê-se de baixo para cima. A última linha diz o erro. A linha `File` de baixo, com `in media`, diz onde o Python parou: na linha 16, dentro da função `media`. A linha `File` de cima, com `in <module>`, diz quem chamou a função: a linha 20, na parte principal.

Porque acontece: com a lista vazia, o ciclo da `media` dá zero voltas, e a conta é 0 / 0. A documentação da função avisava que a lista tem de ter pelo menos um número. O erro aparece dentro da função, mas a causa está na chamada, que lhe deu uma lista que ela não aceita.

Como se corrige: antes de chamar uma função, lê a documentação e cumpre o que ela pede. Se a lista pode estar vazia, a parte principal confirma primeiro que não está, com um `if len(notas) > 0`, e só chama `media` dentro desse `if`.

## Palavras novas deste guia

- Função: um bloco de código com nome, que recebe valores, faz um trabalho e devolve um resultado.
- `def`: a palavra que começa o cabeçalho de uma função; é a `Função` do pseudocódigo.
- Cabeçalho: a primeira linha de uma função, com o `def`, o nome, os parâmetros entre parênteses e os dois pontos.
- Corpo: as linhas indentadas por baixo do cabeçalho, que a função executa.
- `return`: entrega um valor a quem chamou a função e termina a função; é o `devolver` do pseudocódigo.
- Parte principal: as linhas encostadas à margem, depois das funções, que usam as funções; é o algoritmo principal da algoritmia.
- Chamar uma função: escrever o nome dela com os argumentos entre parênteses, para ela se executar.
- Parâmetro: o nome que a função dá, no cabeçalho, a um valor que vai receber.
- Argumento: o valor que se dá a uma função na chamada.
- Valor devolvido: o valor que a função entrega, e que tapa o buraco da chamada na linha onde ela está.
- Documentação de uma função, ou docstring: o texto entre aspas triplas, `"""`, por baixo do cabeçalho. Diz o que a função faz, recebe e devolve.
- Variável local: um parâmetro, ou uma variável que nasce dentro de uma função; só existe enquanto a função se executa.
- `None`: o valor que quer dizer "nenhum valor"; é o que devolve uma função que acaba sem passar por um `return`.
- `NoneType`: o tipo do `None`, que aparece nas mensagens de erro.
- Testar uma função sozinha: chamá-la com valores escolhidos e comparar o que devolve com o que se calculou à mão. Faz-se antes de a usar na parte principal.
- Linha de teste: um `print` com uma chamada e o valor esperado, que se desliga com um `#` quando a função passa.

## Verificar o que aprendeste

Usa estas perguntas para te testares. Responde a cada uma sem olhar para o guia. Se não conseguires, volta à secção que explica a ideia.

1. Traduz para Python, com a documentação: `Função triplo(numero)`, com o corpo `devolver numero * 3`.
2. Na linha `valor = preco_com_desconto(80, 25)`, quais são os argumentos? E os parâmetros? Quanto fica em `valor`?
3. Explica por palavras tuas as quatro fases da chamada `area_retangulo(4, 5)`.
4. Com as funções `dobro` e `area_retangulo` deste guia, o que devolve `area_retangulo(dobro(1), dobro(3))`? E `dobro(area_retangulo(2, 2)) + 1`?
5. Um ficheiro só tem uma função, sem nenhuma chamada. O que aparece no ecrã quando o corres? Porquê?
6. Uma função e a parte principal têm, cada uma, uma variável `total`. Se a função mudar o seu `total`, o que acontece ao da parte principal?
7. Viste `None` no ecrã onde esperavas um número. Que erro procuras, e onde?
8. Qual é a diferença entre escrever o resultado com `print` dentro da função e devolvê-lo com `return`? Dá um exemplo em que só a versão com `return` serve.
9. Porque é que a chamada a uma função não pode aparecer antes do `def` dessa função? Que mensagem aparece?
10. Por que ordem se arrumam as partes de um script com funções?
11. Escreve a função `idade_valida(idade)`, que devolve `True` para idades de 0 a 120, incluindo os extremos. Que seis valores escolhes para a testar sozinha, e o que esperas de cada um?
12. Um traceback tem duas linhas `File`, a de cima com `in <module>` e a de baixo com `in media`. Onde parou o programa, e de onde foi chamada a função?

## O que vem a seguir

Para praticar este tema, faz o [laboratório](laboratorios/06-funcoes-laboratorio.md). Nele constróis, função a função, o resumo das partidas de uma semana num jogo online, e testas cada função sozinha antes de a usares. Depois faz a [ficha de exercícios](exercicios/06-funcoes-exercicios.md). Tem chamadas para prever, funções para escrever e testar, um script com erros para encontrar e uma função desconhecida para explicar.

O tema seguinte é [07 Textos e listas que mudam](07-textos-e-listas-que-mudam.md). Até aqui, as listas eram dadas no programa e nunca mudavam de tamanho, e os textos usavam-se inteiros. No tema 07, vais percorrer um texto letra a letra, tirar-lhe partes e acrescentar e tirar elementos de uma lista. As funções deste tema vão continuar a arrumar esse trabalho.

![Rodapé](../imagens/rodape.png)
