![Cabeçalho](../imagens/cabecalho.png)

# Funções

Neste guia, passas para Python, com `def` e `return`, as funções que já escrevias em pseudocódigo, e testas cada função sozinha antes de a usar. A forma de pensar é a da algoritmia. O que é novo é a forma de escrever, a documentação e o computador a confirmar as contas.

Usa as funções da algoritmia e as listas do tema 05. Rever: [Escrever uma função](../01-algoritmos/05-funcoes-e-modelo-integrado.md#escrever-uma-função), [Chamar uma função](../01-algoritmos/05-funcoes-e-modelo-integrado.md#chamar-uma-função), [`devolver`](../01-algoritmos/05-funcoes-e-modelo-integrado.md#devolver) e [Percorrer a lista pelo valor, com `for`](05-listas.md#percorrer-a-lista-pelo-valor-com-for). Para praticar: [laboratório](laboratorios/06-funcoes-laboratorio.md) e [ficha de exercícios](exercicios/06-funcoes-exercicios.md).

## Neste guia

1. [Escrever uma função com `def` e `return`](#escrever-uma-função-com-def-e-return)
2. [Chamar uma função: parâmetros e argumentos](#chamar-uma-função-parâmetros-e-argumentos)
3. [A documentação diz o que a função recebe e devolve](#a-documentação-diz-o-que-a-função-recebe-e-devolve)
4. [Testar cada função sozinha](#testar-cada-função-sozinha)
5. [Uma função pode chamar outra](#uma-função-pode-chamar-outra)
6. [O `return` entrega o valor e termina a função](#o-return-entrega-o-valor-e-termina-a-função)
7. [Os argumentos passam pela ordem dos parâmetros](#os-argumentos-passam-pela-ordem-dos-parâmetros)
8. [As variáveis de uma função são locais](#as-variáveis-de-uma-função-são-locais)
9. [Uma função sem `return` devolve `None`](#uma-função-sem-return-devolve-none)
10. [As funções que calculam devolvem, e a parte principal escreve](#as-funções-que-calculam-devolvem-e-a-parte-principal-escreve)
11. [A ordem no ficheiro: constantes, funções e parte principal](#a-ordem-no-ficheiro-constantes-funções-e-parte-principal)
12. [Exemplo guiado: o resumo das notas de um teste](#exemplo-guiado-o-resumo-das-notas-de-um-teste)

## Escrever uma função com `def` e `return`

Com a mesma conta em dois sítios do programa, trabalhas a dobrar, e um erro tem de ser corrigido nos dois. Uma função escreve a conta uma vez, com um nome, e cada uso passa a ser uma chamada. O pseudocódigo passa para Python quase palavra a palavra:

| Pseudocódigo | Python |
| --- | --- |
| `Função areaRetangulo(comprimento, largura)` | `def area_retangulo(comprimento, largura):` |
| `devolver comprimento * largura` | `return comprimento * largura` |
| `float area = areaRetangulo(3, 2)` | `area = area_retangulo(3, 2)` |

O **`def`**, do inglês *define*, definir, começa o cabeçalho, que acaba com dois pontos, como a linha de um `if`. O corpo vai indentado quatro espaços. O `return` é o `devolver`: entrega um valor a quem chamou a função. O nome da função segue as regras dos nomes das variáveis e diz o que ela faz ou devolve.

```python
# area.py: calcula a área de um retângulo com uma função.


def area_retangulo(comprimento, largura):
    """Devolve a área de um retângulo.

    Recebe o comprimento e a largura, dois números maiores do que zero,
    na mesma unidade. Devolve a área, um número, na unidade ao quadrado.
    """
    return comprimento * largura


area = area_retangulo(3, 2)
print("Área:", area)
print("Outra área:", area_retangulo(1.5, 1.5))
```

Aparecem `Área: 6` e `Outra área: 2.25`. Por baixo do cabeçalho, entre aspas triplas, está a documentação da função, um texto para quem a vai usar, que o Python não executa. As duas linhas em branco antes e depois da função são uma convenção do Python, para se ver onde ela começa e acaba.

As linhas encostadas à margem, depois da função, são a **parte principal** do programa, o que na algoritmia se chamava o algoritmo principal. É aí que o programa começa a fazer coisas. O `def` só cria a função: se apagares a parte principal, o programa acaba sem escrever nada e sem nenhum erro.

Um parâmetro também pode receber uma lista. Aqui, a mesma função calcula a média dos pontos de dois jogadores.

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

Aparecem `Média da Ana: 11.0` e `Média do Rui: 10.0`. O ciclo está escrito uma só vez. Para um terceiro jogador, basta outra chamada, e um erro na conta corrige-se num sítio só.

## Chamar uma função: parâmetros e argumentos

Como na algoritmia, os parâmetros são os nomes que estão no cabeçalho, como `comprimento` e `largura`. Os argumentos são os valores que se escrevem na chamada, como o 3 e o 2. Uma chamada executa-se em quatro fases. Em `area = area_retangulo(3, 2)`, são estas:

1. Os argumentos passam para os parâmetros: `comprimento` fica com 3 e `largura` fica com 2.
2. O programa salta para dentro da função e executa o corpo.
3. O `return comprimento * largura` calcula 6 e termina a função.
4. O programa volta à linha da chamada, e a chamada é trocada pelo 6: a linha passa a ser `area = 6`.

Por causa da fase 4, uma chamada pode aparecer onde caberia um valor: numa atribuição, numa conta, num `print` ou numa condição. Já o fazias com o `len` e o `abs`. As funções que escreves usam-se da mesma maneira.

Os argumentos podem ser valores, variáveis ou contas, e o nome de uma variável não tem de ser igual ao do parâmetro. Em `media(pontos_ana)`, a lista passa para o parâmetro `valores`, e dentro da função só existe o nome `valores`.

## A documentação diz o que a função recebe e devolve

Quem usa uma função precisa de saber o que ela faz, que valores lhe dar e o que ela devolve. Em Python, isso escreve-se logo por baixo do cabeçalho, entre aspas triplas. A esse texto chama-se **docstring**, do inglês *documentation string*, texto de documentação. Nas aulas, tem sempre esta forma:

1. uma frase que diz o que a função faz ou o que devolve;
2. uma linha em branco;
3. o que a função recebe: cada parâmetro, com o tipo e o que quer dizer;
4. o que a função devolve, com o tipo;
5. o que é preciso saber para a usar sem adivinhar, como um caso que ela não aceita.

A documentação da `media` avisa que a lista tem de ter pelo menos um número. Com a lista vazia, a conta seria 0 a dividir por 0.

Um comentário, com `#`, explica uma linha a quem lê o código. A documentação explica a função inteira a quem a vai usar, e por isso fica indentada, como o corpo. "Faz a conta" não serve. Um colega que só leia a documentação tem de conseguir escrever uma chamada certa e prever o resultado. Nos exemplos com erros deste guia, as funções têm só a primeira linha da documentação, para o erro se ver melhor.

## Testar cada função sozinha

Um programa com três funções e uma parte principal pode falhar em quatro sítios. Testar cada função sozinha, antes de a usar, diz-te onde procurar. Chamas a função com valores escolhidos e comparas o que ela devolve com o que calculaste à mão.

Os casos escolhem-se a partir da documentação, antes de olhar para o corpo. Para uma fronteira, o valor de baixo, o da fronteira e o de cima. Para uma lista, a lista vazia, se a função a aceitar, uma com um elemento e uma com vários. Cada caso é uma **linha de teste**: um `print` com a chamada e o valor esperado, depois das funções e antes da parte principal.

```python
# soma_testes.py: a função soma, testada sozinha.


def soma(numeros):
    """Devolve a soma dos números de uma lista.

    Recebe uma lista de números. Devolve a soma, ou 0 com a lista vazia.
    """
    total = 0
    for numero in numeros:
        total = total + numero
    return total


# Testes da função sozinha: o valor devolvido e o que se esperava.
print(soma([]), "esperado: 0")
print(soma([7]), "esperado: 7")
print(soma([20, 30, 5]), "esperado: 55")
```

O resultado é este:

```text
0 esperado: 0
7 esperado: 7
55 esperado: 55
```

Cada linha mostra o devolvido e o esperado, lado a lado. Quando todas batem certo, a função está pronta a usar, e escreve-se a parte principal.

As linhas de teste guardam-se para quando mudares a função. Desligam-se com um `#` no início de cada uma. No VS Code, selecionas as linhas e escolhes a opção Toggle Line Comment, no menu Edit. Essa opção põe ou tira o `#` de todas ao mesmo tempo.

Quando uma linha não bate certo, ou a função está errada, ou o esperado foi mal calculado. Refaz a conta à mão. Se estiver certa, procura o erro dentro da função, com a rotina de depuração e o caso que falhou.

## Uma função pode chamar outra

Para fazer uma chamada, o Python calcula primeiro os argumentos. Se um argumento for outra chamada, faz essa primeiro. Antes de leres o resultado, faz de cabeça as contas das duas últimas linhas, de dentro para fora.

```python
# chamadas.py: chamadas de funções dentro de outras chamadas.


def dobro(numero):
    """Devolve o dobro de um número.

    Recebe um número, int ou float. Devolve um número do mesmo tipo.
    """
    return numero * 2


def area_retangulo(comprimento, largura):
    """Devolve a área de um retângulo.

    Recebe o comprimento e a largura, dois números maiores do que zero,
    na mesma unidade. Devolve a área, um número, na unidade ao quadrado.
    """
    return comprimento * largura


print(dobro(dobro(5)))
print(area_retangulo(dobro(2), 3))
```

Aparecem 20 e 12. A chamada `area_retangulo(dobro(2), 3)` segue estes passos:

| Passo | O que se calcula | A linha passa a ser |
| ---: | --- | --- |
| 1 | `dobro(2)` devolve 4 | `print(area_retangulo(4, 3))` |
| 2 | `area_retangulo(4, 3)` devolve 12 | `print(12)` |
| 3 | o `print` escreve o 12 | nada mais para calcular |

Uma chamada também pode estar dentro do corpo de outra função. Aqui, a `media` usa a `soma`.

```python
# soma_e_media.py: uma função tua que chama outra função tua.


def soma(numeros):
    """Devolve a soma dos números de uma lista.

    Recebe uma lista de números. Devolve a soma, ou 0 com a lista vazia.
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

O resultado é `11.0`. No corpo da `media`, a `soma(numeros)` devolve 44, o `len(numeros)` devolve 4, e a conta passa a `44 / 4`.

Se mudares a última linha para `print(media([]))`, o programa para. O traceback tem duas linhas `File`, porque o erro aconteceu dentro de uma função:

```text
Traceback (most recent call last):
  File "C:\Users\aluno\Documents\fp-python\soma_e_media.py", line 23, in <module>
    print(media([]))
          ~~~~~^^^^
  File "C:\Users\aluno\Documents\fp-python\soma_e_media.py", line 20, in media
    return soma(numeros) / len(numeros)
           ~~~~~~~~~~~~~~^~~~~~~~~~~~~~
ZeroDivisionError: division by zero
```

Lê-se de baixo para cima. A linha `File` de baixo diz onde o Python parou, dentro da `media`. A de cima, com `in <module>`, diz quem chamou a função, a linha 23, na parte principal. O erro vê-se na função, mas a causa está na chamada, que lhe deu uma lista que ela não aceita.

## O `return` entrega o valor e termina a função

O `return` faz duas coisas: entrega o valor e termina a função. As linhas que estiverem por baixo dele, no mesmo caminho, já não se executam. Por isso, uma função pode ter vários `return`, um em cada caminho de um `if`.

```python
# maior.py: o maior de dois números, com dois return.


def maior(a, b):
    """Devolve o maior de dois números.

    Recebe dois números, a e b. Devolve o maior, um número.
    Se forem iguais, devolve esse valor.
    """
    if a > b:
        return a
    else:
        return b


print(maior(3, 8))
print(maior(5, 5))
```

Aparecem 8 e 5. Em cada chamada, a função chega a exatamente um `return`. Em todos os caminhos possíveis, tem de chegar a um.

Uma função também pode devolver `True` ou `False`, para responder a uma pergunta de sim ou não. Um jogo PEGI 12 é recomendado a partir dos 12 anos.

```python
# pegi_testes.py: diz se um jogo PEGI 12 se recomenda para uma idade, com a função testada.
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

As três linhas batem certo. A condição já dá `True` ou `False`, e por isso a função devolve-a diretamente, sem `if`. O 12 é o caso que mais interessa, porque apanha um `>` escrito no lugar do `>=`. Uma chamada destas usa-se no sítio de uma condição, como em `if pode_jogar(idade):`.

## Os argumentos passam pela ordem dos parâmetros

O primeiro argumento vai para o primeiro parâmetro, e o segundo para o segundo, sejam quais forem os nomes. Esta função calcula o preço de um jogo depois de um desconto.

```python
# desconto.py: o preço de um jogo depois de um desconto em percentagem.


def preco_com_desconto(preco, percentagem):
    """Devolve o preço depois de aplicado um desconto.

    Recebe dois números: o preço, em euros, e a percentagem, de 0 a 100.
    Devolve o preço com o desconto, um float.
    """
    return preco - preco * percentagem / 100


print(preco_com_desconto(50, 10))
print(preco_com_desconto(10, 50))
```

Aparecem `45.0` e `5.0`. Na primeira chamada, a função tira 10% a 50 euros. Na segunda, tira 50% a 10 euros. As duas contas são possíveis, e por isso o Python não avisa. Antes de escreveres uma chamada, confirma a ordem no cabeçalho ou na documentação.

## As variáveis de uma função são locais

Pode haver uma variável com o mesmo nome dentro de uma função e na parte principal.

```python
# locais.py: as variáveis de uma função só existem dentro dela.


def soma(numeros):
    """Devolve a soma dos números de uma lista.

    Recebe uma lista de números. Devolve a soma, ou 0 com a lista vazia.
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

Aparecem 50 e 100. São duas variáveis diferentes, com o mesmo nome, em sítios diferentes. Os parâmetros e as variáveis que nascem dentro de uma função são as suas variáveis locais. Nascem em cada chamada e desaparecem quando a função acaba.

Uma variável local não se vê fora da função. Com `print(numero)` na parte principal, o programa para com `NameError: name 'numero' is not defined`. O que sai da função é só o valor do `return`, e guarda-se onde a chamada está, como em `resultado = soma([20, 30])`.

Nas aulas, uma função só usa os seus parâmetros, as suas variáveis locais, as constantes e outras funções. O Python deixa-a ler uma variável da parte principal, mas assim ela deixa de se poder testar sozinha.

## Uma função sem `return` devolve `None`

Um erro frequente é a função que calcula, mas não devolve.

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

A função calcula 6, mas chega ao fim do corpo sem entregar nada. Nesse caso, o Python devolve o `None`, o valor que já conheces do `print`. O `None` não é o número 0, e as contas não o aceitam. O `NoneType` é o tipo dele.

Quando vires `None` no ecrã, onde esperavas um valor, ou uma mensagem com `NoneType`, procura uma função que não chegou a um `return`. A linha apontada é a da conta, mas a causa está na função. A correção é acrescentar `return resultado` no fim do corpo.

## As funções que calculam devolvem, e a parte principal escreve

Uma função que escreve o resultado com `print`, em vez de o devolver, parece certa, mas não entrega nada.

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

A média aparece no ecrã, mas o valor não volta para a parte principal. A função devolve `None`, e a comparação não se consegue fazer. O `print` dá lugar a `return total / len(valores)`.

É a regra da algoritmia: as funções que calculam devolvem, e quem escreve no ecrã é a parte principal. Uma função que devolve serve para escrever, comparar ou fazer outra conta. Pela mesma razão, uma função que calcula não lê do teclado. É a parte principal que pergunta, com o `input`, e passa o valor como argumento.

## A ordem no ficheiro: constantes, funções e parte principal

Um script com funções arruma-se sempre por esta ordem:

1. o comentário do topo, que diz o que o programa faz;
2. as constantes;
3. as funções, cada uma com a sua documentação;
4. as linhas de teste, desligadas com `#`;
5. a parte principal.

O Python executa o ficheiro de cima para baixo, e é a linha do `def` que cria a função. Neste programa, a chamada aparece antes do `def`:

```python
# ordem.py: a chamada aparece antes do def.

area = area_retangulo(3, 2)
print("Área:", area)


def area_retangulo(comprimento, largura):
    """Devolve a área de um retângulo."""
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

A função está escrita no ficheiro, mas o Python ainda não chegou ao `def`. Corrige-se pondo a função antes da parte principal.

## Exemplo guiado: o resumo das notas de um teste

### O problema

Este problema está resolvido em pseudocódigo no [exemplo guiado do guia 05 da algoritmia](../01-algoritmos/05-funcoes-e-modelo-integrado.md#exemplo-guiado-o-resumo-das-notas-de-um-teste):

> Um professor guardou numa lista as notas de um teste, todas inteiras: `notas = [14, 9, 17, 10, 6, 16]`. Quer um programa que confirme que todas as notas estão na escala de 0 a 20. Se houver alguma fora da escala, o programa escreve "Há notas inválidas" e não calcula mais nada. Se estiverem todas certas, escreve a média da turma e quantas notas são positivas, ou seja, 10 ou mais.

O algoritmo tem três funções: `notaValida`, `media` e `contarPositivas`. Em Python, escrevem-se e testam-se primeiro as funções, e só depois a parte principal.

### As funções, testadas sozinhas

Começa-se pelas constantes e pela primeira função, com os três valores de cada fronteira:

```python
# resumo_notas.py: confirma as notas de um teste e mostra a média e quantas são positivas.
NOTA_MINIMA = 0
NOTA_MAXIMA = 20
LIMIAR_POSITIVA = 10


def nota_valida(nota):
    """Diz se uma nota está na escala.

    Recebe uma nota, um int. Devolve True se ela estiver entre 0 e 20,
    incluindo os extremos, e False se não estiver.
    """
    return nota >= NOTA_MINIMA and nota <= NOTA_MAXIMA


# Testes das funções sozinhas: o valor devolvido e o que se esperava.
print(nota_valida(-1), "esperado: False")
print(nota_valida(0), "esperado: True")
print(nota_valida(1), "esperado: True")
print(nota_valida(19), "esperado: True")
print(nota_valida(20), "esperado: True")
print(nota_valida(21), "esperado: False")
```

As seis linhas batem certo. A seguir à `nota_valida`, antes das linhas de teste, escrevem-se as outras duas funções:

```python
def media(valores):
    """Calcula a média de uma lista de números.

    Recebe uma lista de números, com pelo menos um. Devolve a média, um float.
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
```

A `media` conta os elementos com um contador, como no pseudocódigo, e o `len` dava o mesmo. Por baixo dos testes da `nota_valida`, juntam-se os das outras duas. A `media` não aceita a lista vazia, e por isso não se testa com ela.

```python
print(media([10]), "esperado: 10.0")
print(media([0, 20]), "esperado: 10.0")
print(media([14, 9, 17, 10, 6, 16]), "esperado: 12.0")
print(contar_positivas([]), "esperado: 0")
print(contar_positivas([9]), "esperado: 0")
print(contar_positivas([10]), "esperado: 1")
print(contar_positivas([11]), "esperado: 1")
print(contar_positivas([14, 9, 17, 10, 6, 16]), "esperado: 4")
```

As oito linhas batem certo. Os valores da `media` vêm com o ponto zero, porque a divisão com `/` dá sempre um `float`. Com as funções testadas, desligam-se as linhas de teste.

### A parte principal

A parte principal escreve-se a seguir às linhas de teste, encostada à margem:

```python
notas = [14, 9, 17, 10, 6, 16]
todas_validas = True
for nota in notas:
    if not nota_valida(nota):
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

Aparecem `Média: 12.0` e `Positivas: 4`. O `not nota_valida(nota)` traduz o `== false` do pseudocódigo. As funções de cálculo só são chamadas quando já se sabe que as notas são válidas. Quem escreve é a parte principal.

### Os casos de teste

Para correr cada caso, muda-se a linha `notas = [...]`.

| Notas | Esperado, calculado à mão | O que o Python mostra |
| --- | --- | --- |
| `[14, 9, 17, 10, 6, 16]` | Média 12; 4 positivas | `Média: 12.0` e `Positivas: 4` |
| `[10]` | Média 10; 1 positiva | `Média: 10.0` e `Positivas: 1` |
| `[9]` | Média 9; 0 positivas | `Média: 9.0` e `Positivas: 0` |
| `[0, 20]` | Média 10; 1 positiva | `Média: 10.0` e `Positivas: 1` |
| `[12, 21, 8]` | Há notas inválidas | `Há notas inválidas` |

Como as funções já estavam testadas, um erro aqui só podia estar na parte principal.

<details>
<summary>Para ires mais longe: o quadro completo do pseudocódigo para o Python</summary>

Com as funções, traduziste para Python tudo o que a algoritmia deu.

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

</details>

## Erros frequentes

### O `return` dentro do ciclo

Com o `return` indentado oito espaços, dentro do `for`, a função termina na primeira volta, sem nenhuma mensagem. Na `contar_positivas`, `[14, 9, 17]` dá 1 em vez de 2, e a lista vazia dá `None`. O `return` fica com quatro espaços, alinhado com o `for`.

### A chamada sem parênteses

Com `print("Média:", media)`, aparece `Média: <function media at 0x104217480>`, com outro número no teu computador. Sem os parênteses, não há chamada, e o `print` escreve a própria função. A chamada leva sempre os parênteses: `media(notas)`.

### O número de argumentos errado

Com `area_retangulo(3)`, aparece `TypeError: area_retangulo() missing 1 required positional argument: 'largura'`, porque falta um argumento. Com `area_retangulo(3, 2, 5)`, aparece `TypeError: area_retangulo() takes 2 positional arguments but 3 were given`. Cada parâmetro recebe exatamente um argumento.

## Palavras novas deste guia

- `def`: a palavra que começa o cabeçalho de uma função em Python; é a `Função` do pseudocódigo.
- `return`: entrega um valor a quem chamou a função e termina a função; é o `devolver` do pseudocódigo.
- Parte principal: as linhas encostadas à margem, depois das funções, que usam as funções.
- Docstring: o texto entre aspas triplas, por baixo do cabeçalho, que diz o que a função faz, recebe e devolve.
- Linha de teste: um `print` com uma chamada e o valor esperado, que se desliga com um `#` quando a função passa.

## O que vem a seguir

No tema seguinte, [Textos e listas que mudam](07-textos-e-listas-que-mudam.md), percorres um texto letra a letra e acrescentas elementos a uma lista. As funções continuam a arrumar esse trabalho.

![Rodapé](../imagens/rodape.png)
