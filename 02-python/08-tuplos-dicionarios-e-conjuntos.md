![Cabeçalho](../imagens/cabecalho.png)

# Tuplos, dicionários e conjuntos

Neste guia, guardas os dados de um jogo juntos, num tuplo, e procuras um jogo pelo código, num dicionário. Tiras também os repetidos de uma coleção, com um conjunto, e aprendes a escolher a forma de guardar os dados que serve cada problema.

Usa as listas e os textos do tema 07. Rever: [O `append` faz uma lista crescer](07-textos-e-listas-que-mudam.md#o-append-faz-uma-lista-crescer), [O `in` procura um elemento numa lista](07-textos-e-listas-que-mudam.md#o-in-procura-um-elemento-numa-lista) e [O contador e o acumulador](04-ciclos-while-e-for.md#o-contador-e-o-acumulador). Para praticar: [laboratório](laboratorios/08-tuplos-dicionarios-e-conjuntos-laboratorio.md) e [ficha de exercícios](exercicios/08-tuplos-dicionarios-e-conjuntos-exercicios.md).

## Neste guia

1. [Um tuplo guarda valores que andam juntos](#um-tuplo-guarda-valores-que-andam-juntos)
2. [Um dicionário procura por chave](#um-dicionário-procura-por-chave)
3. [Percorrer um dicionário com `items` e `values`](#percorrer-um-dicionário-com-items-e-values)
4. [Contar com um dicionário](#contar-com-um-dicionário)
5. [Um conjunto guarda valores sem repetidos](#um-conjunto-guarda-valores-sem-repetidos)
6. [As chavetas têm três papéis](#as-chavetas-têm-três-papéis)
7. [A coleção vazia é sempre um caso de teste](#a-coleção-vazia-é-sempre-um-caso-de-teste)
8. [Escolher a representação](#escolher-a-representação)
9. [Exemplo guiado: o resumo das sessões do clube](#exemplo-guiado-o-resumo-das-sessões-do-clube)

## Um tuplo guarda valores que andam juntos

Com o que sabes, cada dado do catálogo do clube ficava numa lista própria, e as listas tinham de ficar alinhadas.

```text
>>> titulos = ["Celeste", "Tetris", "Minecraft"]
>>> anos = [2018, 1984, 2011]
>>> titulos.remove("Tetris")
>>> print(titulos[1], anos[1])
Minecraft 1984
```

O Minecraft ficou com o ano do Tetris, e o Python não avisa. Um **tuplo** guarda um grupo de valores que andam juntos, entre parênteses curvos. Como numa lista, cada valor tem um índice, e o `len` diz quantos são. A diferença é que um tuplo é imutável, como um texto.

```text
>>> jogo = ("Celeste", "plataformas", 2018)
>>> jogo[0]
'Celeste'
>>> jogo[-1]
2018
>>> len(jogo)
3
```

Com `jogo[2] = 2019`, o programa para com `TypeError: 'tuple' object does not support item assignment`. Para outro ano, constrói-se um tuplo novo: `jogo = (jogo[0], jogo[1], 2019)`.

Para dar um nome a cada valor de uma vez, escreve-se `titulo, genero, ano = jogo`. A isto chama-se **desempacotar**: o primeiro valor vai para a primeira variável, e assim por diante. O número de variáveis tem de ser igual ao de valores. Com `titulo, genero = jogo`, o programa para com `ValueError: too many values to unpack (expected 2, got 3)`.

Para guardar vários jogos, junta-se um tuplo por jogo numa lista, e o `for` desempacota cada um.

```python
# jogos_antigos.py: escreve os jogos do catálogo que saíram antes de 2016.
ANO_LIMITE = 2016

jogos = [("Celeste", 2018), ("Rocket League", 2015), ("Tetris", 1984), ("Minecraft", 2011)]
for titulo, ano in jogos:
    if ano < ANO_LIMITE:
        print(f"{titulo} ({ano})")
```

Aparecem `Rocket League (2015)`, `Tetris (1984)` e `Minecraft (2011)`. O título e o ano de cada jogo nunca se desalinham, porque viajam no mesmo tuplo.

Uma lista guarda muitos valores do mesmo tipo, que podem aumentar ou diminuir. Um tuplo guarda um grupo fixo de valores com significados diferentes. Se faz sentido acrescentar mais um elemento, é uma lista.

## Um dicionário procura por chave

Num dicionário de português, procuras a palavra e lês o significado. Em Python, um **dicionário** guarda pares: a **chave**, que é o que se procura, e o valor, que é o que se encontra. Escreve-se entre chavetas, com cada par na forma `chave: valor`, e lê-se um valor com a chave entre parênteses retos, sem ciclo nenhum.

```python
# copias.py: as cópias de cada jogo do clube, num dicionário.
copias = {"Minecraft": 2, "Tetris": 1, "Celeste": 3, "Rocket League": 2}
print(copias["Celeste"])
copias["Tetris"] = copias["Tetris"] + 1
copias["Portal 2"] = 1
print(copias)
print(len(copias))
```

O resultado é este:

```text
3
{'Minecraft': 2, 'Tetris': 2, 'Celeste': 3, 'Rocket League': 2, 'Portal 2': 1}
5
```

Dar um valor a uma chave substitui o valor, se a chave já existe, e acrescenta o par, se ainda não existe. Cada chave aparece uma só vez, e os valores podem repetir-se. O `len` conta os pares.

Ler uma chave que o dicionário não tem faz o programa parar com `KeyError: 'Fortnite'`, o erro parecido com o `IndexError` das listas. Por isso, pergunta-se primeiro com o `in`, que num dicionário só pergunta pelas chaves.

```python
# procurar_copias.py: diz quantas cópias o clube tem de um jogo, se o jogo existir.
copias = {"Minecraft": 2, "Tetris": 1, "Celeste": 3, "Rocket League": 2}

titulo = input("Que jogo procuras? ").strip()
if titulo in copias:
    print(f"Cópias de {titulo}: {copias[titulo]}")
else:
    print(f"O clube não tem {titulo}.")
```

Com `Celeste`, aparece `Cópias de Celeste: 3`. Com `celeste`, aparece `O clube não tem celeste.`, porque a chave tem maiúscula.

Os valores podem ser de qualquer tipo, também um tuplo. É assim que se guarda o catálogo do clube, com um par por linha:

```python
# catalogo_curto.py: dois jogos do catálogo do clube, num dicionário.
catalogo = {
    "PLA-02": ("Celeste", "plataformas", 2018),
    "PUZ-01": ("Tetris", "puzzle", 1984)
}
titulo, genero, ano = catalogo["PLA-02"]
print(catalogo["PUZ-01"][0])
```

O `catalogo["PLA-02"]` dá o tuplo do jogo, e a linha desempacota-o. A última escreve `Tetris`: a chave dá o tuplo, e o índice 0 dá o primeiro valor dele.

## Percorrer um dicionário com `items` e `values`

Um `for` sobre um dicionário dá as chaves, uma por volta, pela ordem em que os pares entraram. O método `items` dá a chave e o valor, e o `values` dá só os valores.

```python
# listar_copias.py: escreve as cópias de cada jogo e o total de cópias do clube.
copias = {"Minecraft": 2, "Tetris": 1, "Celeste": 3, "Rocket League": 2}

for titulo, quantas in copias.items():
    print(f"{titulo}: {quantas}")
print("Total de cópias:", sum(copias.values()))
```

O resultado é este:

```text
Minecraft: 2
Tetris: 1
Celeste: 3
Rocket League: 2
Total de cópias: 8
```

| Forma | O que a variável recebe em cada volta |
| --- | --- |
| `for chave in dicionario:` | a chave |
| `for chave, valor in dicionario.items():` | a chave e o valor |
| `for valor in dicionario.values():` | só o valor |
| `for chave in sorted(dicionario):` | a chave, por ordem |

Num dicionário, procura-se pela chave, e não pela posição. O `copias[0]` não é o primeiro par: dá `KeyError: 0`.

## Contar com um dicionário

Para saber quantos votos teve cada jogo do mês, cada jogo votado é uma chave, e o valor é o seu contador. O dicionário começa vazio, com `{}`. Antes de correres, diz quantas chaves ficam no fim.

```python
# votos.py: conta os votos dos sócios do clube para o jogo do mês.
votos = ["Tetris", "Minecraft", "Celeste", "Minecraft", "Tetris", "Minecraft"]

votos_por_jogo = {}
for jogo in votos:
    if jogo in votos_por_jogo:
        votos_por_jogo[jogo] = votos_por_jogo[jogo] + 1
    else:
        # Primeira vez que o jogo aparece: ainda não há chave para somar.
        votos_por_jogo[jogo] = 1
for jogo, quantos in votos_por_jogo.items():
    print(f"{jogo}: {quantos}")
```

Aparecem `Tetris: 2`, `Minecraft: 3` e `Celeste: 1`, pela ordem em que os jogos apareceram. O dicionário nasce antes do ciclo, como um contador nasce a 0. Um jogo em que ninguém votou não aparece com 0: simplesmente não é uma chave.

Só com a linha que soma, sem o `if`, a primeira volta lê uma chave que ainda não existe, e o programa para com `KeyError: 'Tetris'`.

## Um conjunto guarda valores sem repetidos

Às vezes, cada valor só conta uma vez, como os sócios diferentes que vieram ao clube numa semana. Um **conjunto** é uma coleção sem repetidos e sem ordem. A função `set` recebe uma lista e devolve o conjunto dos seus valores. Também se pode escrever entre chavetas, sem os dois pontos: `{"puzzle", "aventura"}`.

```python
# presencas.py: os sócios que vieram ao clube esta semana, sem repetidos.
presencas = ["Rui", "Ana", "Rui", "Bia", "Ana", "Rui"]

socios = set(presencas)
print("Presenças:", len(presencas))
print("Sócios diferentes:", len(socios))
print(sorted(socios))
```

O resultado é este:

```text
Presenças: 6
Sócios diferentes: 3
['Ana', 'Bia', 'Rui']
```

O `sorted` dá uma lista com uma ordem que não muda, porque o conjunto pode mostrar os valores por outra ordem de cada vez. Por não ter ordem, um conjunto não tem índices: `socios[0]` para com `TypeError: 'set' object is not subscriptable`.

O método `add` acrescenta um valor, como em `socios.add("Eva")`, e se o valor já lá estiver, nada muda. O conjunto vazio escreve-se `set()`. Com `socios = {}`, o `add` para o programa com `AttributeError: 'dict' object has no attribute 'add'`, porque as chavetas vazias são um dicionário.

Um conjunto não substitui sempre uma lista, porque perde informação. Com a lista das presenças, sabes que o Rui veio três vezes. Com o conjunto, só sabes que veio.

## As chavetas têm três papéis

| Onde aparecem | Exemplo | O que são |
| --- | --- | --- |
| Dentro de um texto com um `f` antes das aspas | `f"Jogo: {titulo}"` | o sítio onde entra um valor |
| Fora de um texto, com pares separados por dois pontos | `{"Tetris": 1, "Celeste": 3}` | um dicionário |
| Fora de um texto, com valores soltos | `{"puzzle", "aventura"}` | um conjunto |
| Fora de um texto, sem nada lá dentro | `{}` | um dicionário vazio |

Duas perguntas resolvem quase todos os casos. As chavetas estão dentro de umas aspas com um `f` antes? Então, marcam o sítio de um valor. Se não estão, há dois pontos lá dentro? Com dois pontos, é um dicionário, e sem eles, é um conjunto. As chavetas vazias são o dicionário sem pares.

## A coleção vazia é sempre um caso de teste

Cada coleção tem a sua forma vazia: `""`, `[]`, `()`, `{}` e `set()`. Com uma coleção vazia, o `for` não dá voltas, o `len` e o `sum` dão 0, o `in` dá `False` e o `sorted` dá `[]`.

Outras operações param o programa. O `max` e o `min` dão `ValueError`, a média dá `ZeroDivisionError`, o `lista[0]` dá `IndexError`, e ler uma chave dá `KeyError`. Pergunta-se antes, com `len(colecao) == 0`, ou com o `in`, num dicionário.

## Escolher a representação

Antes de escrever o código, escolhe-se a forma de guardar os dados, a **representação**. A escolha começa no que se guarda. Um jogo verdadeiro tem capa, preço e estúdio, mas o catálogo guarda só o que as perguntas do clube precisam. A isto chama-se **abstração**: guardar só o que o problema precisa, na forma que lhe serve. Um mapa do metro não mostra as ruas, só as linhas e as estações.

Depois, fazem-se quatro perguntas aos dados. A ordem interessa? Os repetidos contam? Procura-se pela posição ou por um nome? Os valores mudam depois de guardados?

| Coleção | Guarda a ordem? | Aceita repetidos? | Procura-se por | Muda? | Serve para |
| --- | --- | --- | --- | --- | --- |
| Texto | sim | sim | posição | não | uma sequência de caracteres |
| Lista | sim | sim | posição | sim | muitos valores do mesmo tipo, que crescem ou diminuem |
| Tuplo | sim | sim | posição | não | um grupo fixo de valores que descrevem uma só coisa |
| Dicionário | a ordem de entrada | chaves não; valores sim | chave | sim | encontrar um valor por um nome ou um código |
| Conjunto | não | não | só "está ou não está" | sim | valores sem repetidos |

Uma escolha justifica-se com estas perguntas. "Escolhi um dicionário porque é mais fácil" não justifica nada. "Escolhi um dicionário porque o clube procura cada jogo pelo código" justifica.

## Exemplo guiado: o resumo das sessões do clube

### O problema

> De cada vez que alguém joga no clube, regista-se o código do jogo. No fim da semana, o clube quer saber quantas sessões houve e quantas teve cada jogo, pelo título. Quer saber também qual foi o maior número de sessões de um só jogo e que códigos foram registados por engano, cada um uma vez.

### As coleções

As sessões ficam numa lista, porque têm ordem e os repetidos contam. O catálogo é um dicionário, porque se procura pelo código. As sessões de cada jogo são outro dicionário, porque se procura o contador pelo código. Os códigos desconhecidos são um conjunto, porque cada um se mostra uma só vez.

### O ciclo que conta

```python
# sessoes.py: o resumo das sessões de jogo do clube de videojogos.
catalogo = {
    "PLA-01": ("Super Mario Bros. Wonder", "plataformas", 2023),
    "PLA-02": ("Celeste", "plataformas", 2018),
    "COR-01": ("Forza Horizon 5", "corridas", 2021),
    "DES-01": ("Rocket League", "desporto", 2015),
    "DES-02": ("EA Sports FC 25", "desporto", 2024),
    "PUZ-01": ("Tetris", "puzzle", 1984),
    "AVE-01": ("Minecraft", "aventura", 2011)
}

sessoes = ["AVE-01", "DES-01", "PUZ-09", "AVE-01", "PLA-02", "DES-01", "AVE-01", "PUZ-09"]

sessoes_por_jogo = {}
desconhecidos = set()
for codigo in sessoes:
    if codigo not in catalogo:
        # Um código fora do catálogo é um engano no registo: guarda-se uma vez.
        desconhecidos.add(codigo)
    elif codigo in sessoes_por_jogo:
        sessoes_por_jogo[codigo] = sessoes_por_jogo[codigo] + 1
    else:
        sessoes_por_jogo[codigo] = 1
```

Cada código cai num de três casos: não está no catálogo, já tem contador, ou é a primeira sessão desse jogo. Esta parte ainda não escreve nada.

### Os resultados

Por baixo do ciclo, encostado à margem:

```python
print("Sessões registadas:", len(sessoes))
for codigo in sorted(desconhecidos):
    print("Código desconhecido:", codigo)
for codigo, quantas in sessoes_por_jogo.items():
    print(f"{catalogo[codigo][0]}: {quantas}")

if len(sessoes_por_jogo) == 0:
    print("Ainda não há sessões de jogos do catálogo.")
else:
    # Sem nenhum valor, o max parava o programa.
    print("Mais sessões de um só jogo:", max(sessoes_por_jogo.values()))
```

O resultado é este:

```text
Sessões registadas: 8
Código desconhecido: PUZ-09
Minecraft: 3
Rocket League: 2
Celeste: 1
Mais sessões de um só jogo: 3
```

### Os casos de teste

Para cada caso, muda-se a linha `sessoes = [...]`.

| `sessoes` | O que testa | O que deve aparecer |
| --- | --- | --- |
| `[]` | a coleção vazia | `Sessões registadas: 0` e `Ainda não há sessões de jogos do catálogo.` |
| `["XYZ-01"]` | só uma chave que não existe | `Sessões registadas: 1`, `Código desconhecido: XYZ-01` e a mensagem de não haver sessões |
| `["AVE-01", "AVE-01"]` | um só jogo, repetido | `Sessões registadas: 2`, `Minecraft: 2` e `Mais sessões de um só jogo: 2` |

## Erros frequentes

### Mudar o ano de um jogo do catálogo

Com `catalogo["PLA-02"][2] = 2019`, o programa para com o `TypeError` dos tuplos. O dicionário é mutável, mas o tuplo guardado lá dentro não muda. Um dos desafios do laboratório trata disto.

## Palavras novas deste guia

- Tuplo: um grupo fixo de valores entre parênteses curvos, que não se altera.
- Desempacotar: dar a cada valor de uma coleção uma variável própria, numa só linha.
- Dicionário: uma coleção de pares chave e valor, em que se procura o valor pela chave.
- Chave: num dicionário, o que se procura; cada chave aparece uma só vez.
- `KeyError`: o erro de procurar num dicionário uma chave que não existe.
- Conjunto: uma coleção sem repetidos e sem ordem.
- Representação: a forma escolhida para guardar os dados de um problema.
- Abstração: guardar só o que o problema precisa, na forma que lhe serve.

## O que vem a seguir

No tema seguinte, Funções, mutabilidade e transformações legíveis, escreves funções que recebem coleções e vês quando uma função muda a coleção que recebeu.

![Rodapé](../imagens/rodape.png)
