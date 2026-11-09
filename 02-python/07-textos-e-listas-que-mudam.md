![Cabeçalho](../imagens/cabecalho.png)

# Textos e listas que mudam

Neste guia, trabalhas com um texto por dentro: lês cada carácter, tiras um pedaço, procuras e arrumas o que alguém escreveu. Escreves mensagens exatas com f-strings e usas listas que ganham e perdem elementos enquanto o programa corre.

Usa as listas do tema 05 e as funções do tema 06. Rever: [O índice é a posição de cada elemento](05-listas.md#o-índice-é-a-posição-de-cada-elemento), [Ler até à sentinela](04-ciclos-while-e-for.md#ler-até-à-sentinela) e [Escrever uma função com `def` e `return`](06-funcoes.md#escrever-uma-função-com-def-e-return). Para praticar: [laboratório](laboratorios/07-textos-e-listas-que-mudam-laboratorio.md) e [ficha de exercícios](exercicios/07-textos-e-listas-que-mudam-exercicios.md).

## Neste guia

1. [Um texto é uma sequência de caracteres](#um-texto-é-uma-sequência-de-caracteres)
2. [Uma fatia é um pedaço do texto](#uma-fatia-é-um-pedaço-do-texto)
3. [Um texto não se altera](#um-texto-não-se-altera)
4. [O `in` pergunta se um texto contém outro](#o-in-pergunta-se-um-texto-contém-outro)
5. [Os métodos arrumam um texto](#os-métodos-arrumam-um-texto)
6. [O `isdigit` confirma que um texto só tem algarismos](#o-isdigit-confirma-que-um-texto-só-tem-algarismos)
7. [As f-strings juntam textos e valores](#as-f-strings-juntam-textos-e-valores)
8. [O `append` faz uma lista crescer](#o-append-faz-uma-lista-crescer)
9. [O `pop` tira um elemento pela posição](#o-pop-tira-um-elemento-pela-posição)
10. [O `in` procura um elemento numa lista](#o-in-procura-um-elemento-numa-lista)
11. [O `remove` e o `insert` também mudam a lista](#o-remove-e-o-insert-também-mudam-a-lista)
12. [Os textos não mudam, as listas mudam](#os-textos-não-mudam-as-listas-mudam)
13. [O `sum`, o `max`, o `min` e o `sorted` trabalham com listas](#o-sum-o-max-o-min-e-o-sorted-trabalham-com-listas)
14. [Exemplo guiado: a lista de jogos para experimentar](#exemplo-guiado-a-lista-de-jogos-para-experimentar)

## Um texto é uma sequência de caracteres

Os exemplos deste guia vêm do catálogo do clube de videojogos de uma escola, inventado para as aulas. Cada jogo tem um título, um género, um ano e um código, como `PLA-01`: três letras do género, um hífen e dois algarismos.

Um texto guarda uma sequência de caracteres, por ordem. Um **carácter** é uma letra, um algarismo, um sinal ou um espaço. Cada carácter tem um índice, que começa em 0, como nas listas, e o `len` conta os caracteres.

| Carácter | `P` | `L` | `A` | `-` | `0` | `1` |
| --- | --- | --- | --- | --- | --- | --- |
| Índice | 0 | 1 | 2 | 3 | 4 | 5 |

```text
>>> codigo = "PLA-01"
>>> codigo[0]
'P'
>>> codigo[3]
'-'
>>> len(codigo)
6
```

A consola mostra os textos entre plicas, as aspas simples. Um carácter tirado de um texto é também um texto. Com `codigo[6]`, o programa para com `IndexError: string index out of range`, o erro das listas, agora num texto.

Um índice negativo conta a partir do fim: `codigo[-1]` é o último carácter, `'1'`, e `codigo[-2]` é o penúltimo. Seja o texto curto ou comprido, o `-1` é sempre o último. Também funciona nas listas.

Um valor que guarda outros valores chama-se **coleção**. A lista é uma coleção, e um texto também, de caracteres. Por isso, um texto percorre-se com `for`, como uma lista.

```python
# contar_espacos.py: conta os espaços do título de um jogo, percorrendo-o carácter a carácter.
titulo = "Super Mario Bros. Wonder"
espacos = 0
for caracter in titulo:
    if caracter == " ":
        espacos = espacos + 1
print("Espaços:", espacos)
print("Palavras:", espacos + 1)
```

Aparecem `Espaços: 3` e `Palavras: 4`. É o contador do tema 04, agora sobre os caracteres. Para saber também a posição, percorre-se pelo índice, com `range(0, len(titulo))`.

## Uma fatia é um pedaço do texto

Do código `"PLA-01"`, muitas vezes queres só o género ou só o número. Um pedaço de um texto, tirado por posições, chama-se **fatia**. Escreve-se com dois índices separados por dois pontos. O primeiro entra na fatia, e o segundo não entra, como no `range`.

```text
>>> codigo = "PLA-01"
>>> codigo[0:3]
'PLA'
>>> codigo[:3]
'PLA'
>>> codigo[4:]
'01'
>>> codigo[-2:]
'01'
>>> codigo[4:20]
'01'
```

Sem o primeiro índice, a fatia começa no início. Sem o segundo, vai até ao fim. A última linha mostra uma diferença em relação ao índice. Uma fatia que passa do fim do texto não dá erro, e fica com os caracteres que existem.

Dentro do texto, o número de caracteres de uma fatia é o segundo índice menos o primeiro. Quem escreve `codigo[0:2]` para tirar o género fica com `'PL'`, sem o `A`, e o Python não avisa. É um erro de lógica.

## Um texto não se altera

Se o código passar a começar por `D`, a ideia natural é mudar o primeiro carácter. Com `codigo[0] = "D"`, o programa para com `TypeError: 'str' object does not support item assignment`, isto é, um texto não aceita que se dê um valor a um elemento.

Um valor que não se pode alterar depois de criado diz-se **imutável**, e é o caso dos textos. Um valor que se pode alterar diz-se **mutável**, e é o caso das listas. Quando precisas de outro texto, constróis um novo e guardas na variável:

```text
>>> codigo = "PLA-01"
>>> codigo = "D" + codigo[1:]
>>> codigo
'DLA-01'
```

O lado direito faz-se primeiro, e o resultado é um texto novo. O `"PLA-01"` não mudou: a variável é que passou a guardar outro texto.

## O `in` pergunta se um texto contém outro

A expressão `"Mario" in titulo` dá `True` se o texto `"Mario"` aparecer em algum sítio de `titulo`. O `not in` faz o contrário. Como dá um `bool`, pode ir num `if` ou num `while`.

```text
>>> "Mario" in "Super Mario Bros. Wonder"
True
>>> "mario" in "Super Mario Bros. Wonder"
False
>>> "-" in "PLA-01"
True
```

A segunda dá `False`, porque, para o Python, o `m` minúsculo e o `M` maiúsculo são caracteres diferentes. É a palavra `in` do `for`, com outro papel: numa condição, pergunta se um valor está dentro de uma coleção.

## Os métodos arrumam um texto

Os textos que vêm do teclado raramente chegam arrumados. Uma função que pertence a um valor chama-se **método**, e escreve-se com o valor, um ponto, o nome e os parênteses, como `titulo.upper()`. O `len` é uma função, e por isso escreve-se `len(titulo)`.

| Método | O que devolve | Exemplo | Resultado |
| --- | --- | --- | --- |
| `upper()` | o texto em maiúsculas | `"Celeste".upper()` | `'CELESTE'` |
| `lower()` | o texto em minúsculas | `"Celeste".lower()` | `'celeste'` |
| `strip()` | o texto sem os espaços das pontas | `" Celeste ".strip()` | `'Celeste'` |
| `split()` | a lista das palavras | `"Forza Horizon 5".split()` | `['Forza', 'Horizon', '5']` |
| `split(s)` | a lista dos pedaços, partindo em `s` | `"PLA-01".split("-")` | `['PLA', '01']` |
| `replace(a, b)` | o texto com cada `a` trocado por `b` | `"pla_01".replace("_", "-")` | `'pla-01'` |

Um método de um texto nunca muda o texto. Depois de `titulo.upper()`, a variável `titulo` fica como estava. Para guardares o resultado, escreves `titulo = titulo.upper()`.

Como cada método devolve um valor, pode chamar-se outro método sobre o resultado. Assim se procura sem ligar às maiúsculas: põem-se os dois lados em minúsculas antes de comparar.

```python
# procurar_titulo.py: diz se uma palavra aparece no título de um jogo, sem ligar às maiúsculas.
titulo = "Super Mario Bros. Wonder"
procura = input("Que palavra procuras? ").strip().lower()
if procura in titulo.lower():
    print("Aparece no título.")
else:
    print("Não aparece no título.")
```

Com `  MARIO `, aparece `Aparece no título.`, e com `kart`, `Não aparece no título.`. A linha do `input` lê-se da esquerda para a direita. A variável `titulo` fica com as maiúsculas originais.

## O `isdigit` confirma que um texto só tem algarismos

O `isdigit()` devolve `True` se o texto tiver só algarismos. O `"-3"`, o `" 2018"` e o texto vazio dão `False`. Serve para confirmar um número antes de o converter com `int`.

```python
# ler_ano.py: pede o ano de lançamento de um jogo até a pessoa escrever só algarismos.
ANO_ATUAL = 2026

texto = input("Ano de lançamento? ").strip()
# O int() parava o programa com um texto como "dois mil"; o isdigit confirma antes.
while not texto.isdigit():
    print("Escreve só algarismos, como 2018.")
    texto = input("Ano de lançamento? ").strip()
ano = int(texto)
print("O jogo saiu há", ANO_ATUAL - ano, "anos.")
```

O ecrã, com o que a pessoa escreveu a seguir a cada pergunta:

```text
Ano de lançamento? dois mil
Escreve só algarismos, como 2018.
Ano de lançamento? 2018
O jogo saiu há 8 anos.
```

É a validação repetida do tema 04, com uma leitura antes do ciclo e outra no fim do corpo.

## As f-strings juntam textos e valores

Com o `print` e as vírgulas, não se consegue escrever `Celeste (2018)`, porque aparecem espaços a mais. Uma **f-string** é um texto com um `f` antes das aspas, em que cada par de chavetas marca o sítio onde entra um valor. O Python calcula o que está entre as chavetas e põe o resultado no lugar delas, já como texto.

```python
# ficha_jogo.py: escreve a ficha de um jogo, primeiro com vírgulas e depois com f-strings.
ANO_ATUAL = 2026

titulo = "Celeste"
ano = 2018
print(titulo, "(", ano, ")")
print(f"{titulo} ({ano})")
print(f"Saiu há {ANO_ATUAL - ano} anos, e o título tem {len(titulo)} letras")
```

O resultado é este:

```text
Celeste ( 2018 )
Celeste (2018)
Saiu há 8 anos, e o título tem 7 letras
```

Entre as chavetas pode ir uma variável, uma conta ou uma chamada. Sem o `f`, as chavetas são caracteres como os outros, e aparecem no ecrã tal e qual, sem nenhuma mensagem de erro.

## O `append` faz uma lista crescer

Muitas vezes não se sabe quantos valores vão ser. A lista começa vazia, `[]`, e o método `append` acrescenta um elemento no fim. Os métodos das listas mudam a própria lista.

```python
# inscritos.py: junta numa lista os sócios inscritos num torneio do clube.
inscritos = []
nome = input("Nome do sócio (Enter para acabar): ").strip()
while nome != "":
    inscritos.append(nome)
    nome = input("Nome do sócio (Enter para acabar): ").strip()
print(f"Inscritos: {len(inscritos)}")
print(inscritos)
```

Com `Rui`, `Ana` e Enter sem nada, aparecem `Inscritos: 2` e `['Rui', 'Ana']`. A lista nasce antes do ciclo, como um contador nasce a 0. É o ciclo da sentinela do tema 04, e o texto vazio faz de sentinela. O tamanho da lista só se sabe no fim, com o `len`.

## O `pop` tira um elemento pela posição

O `pop` tira um elemento e devolve-o, para o programa o poder usar. Sem nada entre os parênteses, tira o último. Com uma posição, tira esse. Numa fila para a consola do clube, quem chega entra com o `append`, e quem vai jogar sai com `a_jogar = fila.pop(0)`.

Os elementos que estavam depois passam uma posição para a frente. Numa lista vazia, o programa para com `IndexError: pop from empty list`. Antes do `pop`, confirma que a lista tem elementos, com `len(fila) > 0`.

## O `in` procura um elemento numa lista

O `in` também funciona com listas, e faz numa linha a procura que o tema 05 fazia com uma bandeira. Num texto, procura um pedaço. Numa lista, procura um elemento inteiro.

```text
>>> inscritos = ["Rui", "Ana", "Bia"]
>>> "Ana" in inscritos
True
>>> "ana" in inscritos
False
>>> "Mar" in "Mario"
True
>>> "Mar" in ["Mario", "Celeste"]
False
```

## O `remove` e o `insert` também mudam a lista

O `remove` recebe o valor e tira a primeira vez que ele aparece. Se o valor não estiver na lista, o programa para com `ValueError: list.remove(x): x not in list`, e por isso pergunta-se antes, com o `in`. O `insert` recebe a posição e o valor, e empurra os outros para trás.

Antes de correres estas linhas na consola, diz de cabeça como fica a lista e o que mostra a linha do `pop`.

```text
>>> inscritos = ["Rui", "Ana", "Bia"]
>>> inscritos.remove("Ana")
>>> inscritos
['Rui', 'Bia']
>>> inscritos.insert(0, "Eva")
>>> inscritos
['Eva', 'Rui', 'Bia']
>>> inscritos.pop()
'Bia'
>>> inscritos
['Eva', 'Rui']
```

Só o `pop` mostra um valor, porque o `remove` e o `insert` não devolvem nada. Se sabes o valor que sai, usas o `remove`. Se sabes a posição, usas o `pop`.

## Os textos não mudam, as listas mudam

Os métodos dos textos não mudam o texto, e devolvem um texto novo, que se guarda: `titulo = titulo.upper()`. O `append`, o `insert` e o `remove` mudam a própria lista e devolvem `None`, e por isso não têm atribuição: só `anos.append(2011)`. O `pop` também muda a lista, e devolve o elemento que tirou.

Quem aplica às listas a regra dos textos escreve `inscritos = inscritos.append("Eva")`, e a atribuição deita a lista fora. No `append` seguinte, o programa para com `AttributeError: 'NoneType' object has no attribute 'append'`.

Quando não tens a certeza, experimenta na consola: chama o método e mostra a variável a seguir.

## O `sum`, o `max`, o `min` e o `sorted` trabalham com listas

| Função | O que devolve | Com `[30, 5, 12]` |
| --- | --- | --- |
| `len(lista)` | quantos elementos tem | `3` |
| `sum(lista)` | a soma dos elementos | `47` |
| `max(lista)` | o maior elemento | `30` |
| `min(lista)` | o menor elemento | `5` |
| `sorted(lista)` | uma lista nova, ordenada | `[5, 12, 30]` |

O `sorted` deixa a lista original como estava. Com textos, usa a ordem alfabética, mas todas as maiúsculas vêm antes das minúsculas, e as letras com acento vêm depois de todas. Com o `sum` e o `len`, a média faz-se numa linha: `sum(anos) / len(anos)`.

Com a lista vazia, o `sum` dá 0, mas o `max` e o `min` não têm resposta:

```text
ValueError: max() iterable argument is empty
```

A média também falha, com `ZeroDivisionError`. Antes de pedir o maior ou o menor, confirma que a lista tem elementos:

```python
anos = []
if len(anos) == 0:
    print("Ainda não há jogos no catálogo.")
else:
    print(f"O jogo mais antigo é de {min(anos)}.")
```

Uma lista que cresce pode sempre ficar vazia, e por isso a lista vazia é sempre um dos casos de teste.

## Exemplo guiado: a lista de jogos para experimentar

### O problema

> O clube quer um programa para cada sócio escolher os jogos que quer experimentar. O sócio escreve uma parte do título, como `mine` ou `LEAGUE`. Se só um título do catálogo tiver essa parte, o jogo entra na lista do sócio, a não ser que já lá esteja. Se nenhum a tiver, o programa diz-o. Se mais do que um a tiver, diz quantos são e pede mais letras. O sócio acaba carregando em Enter sem escrever nada. No fim, o programa mostra a lista, por ordem alfabética e numerada.

### A função que procura

A procura recebe uma parte e uma lista e devolve outra lista, e por isso vai para uma função. Testa-se sozinha, antes de haver programa à volta.

```python
# experimentar.py: a lista dos jogos que um sócio do clube quer experimentar.
CATALOGO = ["Super Mario Bros. Wonder", "Celeste", "Forza Horizon 5",
            "Rocket League", "EA Sports FC 25", "Tetris", "Minecraft"]


def procurar_titulos(parte, titulos):
    """Devolve a lista dos títulos que contêm a parte dada, sem ligar às maiúsculas.

    Recebe a parte que se procura, um texto, e a lista dos títulos, que a função
    não altera. Devolve uma lista nova, vazia quando nenhum título tem a parte.
    """
    encontrados = []
    for titulo in titulos:
        # As duas formas passam a minúsculas só para a comparação.
        if parte.lower() in titulo.lower():
            encontrados.append(titulo)
    return encontrados


# Testes da função sozinha: o valor devolvido e o que se esperava.
print(procurar_titulos("mine", CATALOGO), "esperado: ['Minecraft']")
print(procurar_titulos("zelda", CATALOGO), "esperado: []")
print(procurar_titulos("5", CATALOGO), "esperado: ['Forza Horizon 5', 'EA Sports FC 25']")
```

As três linhas batem certo. O `CATALOGO` escreve-se em maiúsculas, como uma constante, porque o programa nunca o muda, e o Python deixa partir uma lista depois de uma vírgula. Com a função testada, desligam-se as linhas de teste.

### A parte principal

Primeiro o ciclo da sentinela, a seguir às linhas de teste. Lê partes do título, e o `if` decide pelo tamanho da lista devolvida:

```python
quero_jogar = []
parte = input("Parte do título (Enter para acabar): ").strip()
while parte != "":
    encontrados = procurar_titulos(parte, CATALOGO)
    if len(encontrados) == 0:
        print(f"Nenhum título tem {parte}.")
    elif len(encontrados) > 1:
        print(f"Há {len(encontrados)} títulos com {parte}. Escreve mais letras.")
    elif encontrados[0] in quero_jogar:
        print(f"{encontrados[0]} já está na tua lista.")
    else:
        quero_jogar.append(encontrados[0])
        print(f"{encontrados[0]} entrou na tua lista.")
    parte = input("Parte do título (Enter para acabar): ").strip()
```

A ordem dos ramos conta. O `encontrados[0]` só se usa depois de os dois primeiros ramos terem apanhado o zero e o "mais do que um". Com a lista vazia, parava o programa com `IndexError`.

Depois do ciclo, encostado à margem, o programa mostra a lista:

```python
print()
if len(quero_jogar) == 0:
    print("Não escolheste nenhum jogo.")
else:
    print(f"Jogos na tua lista: {len(quero_jogar)}")
    # O sorted devolve uma cópia por ordem alfabética; a lista do sócio fica como está.
    por_ordem = sorted(quero_jogar)
    for i in range(0, len(por_ordem)):
        print(f"{i + 1}. {por_ordem[i]}")
```

### Os casos de teste

Corre os casos por esta ordem, numa só execução:

| O sócio escreve | O que deve aparecer |
| --- | --- |
| `  tetris  ` | `Tetris entrou na tua lista.` |
| `mine` | `Minecraft entrou na tua lista.` |
| `o` | `Há 4 títulos com o. Escreve mais letras.` |
| `LEAGUE` | `Rocket League entrou na tua lista.` |
| `zelda` | `Nenhum título tem zelda.` |
| `MINECRAFT` | `Minecraft já está na tua lista.` |
| Enter, sem nada | `Jogos na tua lista: 3`, e os jogos Minecraft, Rocket League e Tetris, numerados |

Numa execução nova, com Enter logo à primeira, aparece `Não escolheste nenhum jogo.`. O programa mostra os títulos, mas não o ano nem o género.

## Erros frequentes

### O código escrito noutra forma

O código `"PLA-02"` está numa lista, a pessoa escreve `pla-02`, e o `in` dá `False`. Dois textos só são iguais se tiverem exatamente os mesmos caracteres. Arruma o que vem do teclado antes de procurar, com `input(...).strip().upper()`.

### Um número guardado como texto

Com `anos = ["2023", "2018", "984"]`, o `max(anos)` dá `'984'`, sem nenhuma mensagem. Os textos comparam-se carácter a carácter, e o `"9"` vem depois do `"2"`. As plicas são a pista. Converte cada valor com `int` antes de o guardar, como em `anos.append(int(texto))`.

## Palavras novas deste guia

- Carácter: uma letra, um algarismo, um sinal ou um espaço.
- Coleção: um valor que guarda outros valores, como um texto ou uma lista.
- Índice negativo: um índice que conta a partir do fim; `-1` é o último.
- Fatia: um pedaço de um texto, tirado por posições, como `codigo[0:3]`.
- Imutável: que não se pode alterar depois de criado, como um texto. Mutável é o contrário, como uma lista.
- Método: uma função que pertence a um valor e se chama com um ponto, como `titulo.upper()`.
- f-string: um texto com um `f` antes das aspas, em que cada par de chavetas recebe um valor.
- `AttributeError`: o erro que aparece quando um valor não tem o método que se pediu.

## O que vem a seguir

No tema seguinte, [Tuplos, dicionários e conjuntos](08-tuplos-dicionarios-e-conjuntos.md), guardas os quatro dados de cada jogo juntos e procuras um jogo pelo código sem percorrer a lista.

![Rodapé](../imagens/rodape.png)
