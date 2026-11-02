![Cabeçalho](../imagens/cabecalho.png)

# Tuplos, dicionários e conjuntos

Módulo Criar aplicações em linguagem de programação Python. Neste guia aprendes três formas novas de guardar muitos valores de uma vez: os tuplos, os dicionários e os conjuntos. Aprendes também a escolher, para cada problema, a forma de guardar os dados que o serve melhor. Para praticar, há o [laboratório](laboratorios/08-tuplos-dicionarios-e-conjuntos-laboratorio.md) e a [ficha de exercícios](exercicios/08-tuplos-dicionarios-e-conjuntos-exercicios.md) deste tema.

No tema anterior, cada dado do catálogo do clube ficava numa lista própria: os títulos numa, os anos noutra. Para mostrar o ano de um título, era preciso que as duas listas estivessem alinhadas, com os dados de cada jogo no mesmo índice. Neste tema, os dados de um jogo passam a andar juntos. Passas também a procurar um jogo pelo código, sem percorrer a lista, e a tirar os repetidos de uma coleção. Este tema ainda não escreve funções que alteram as coleções que recebem, nem guarda nada em ficheiros. Isso fica para os temas seguintes.

Lê-se ao teu ritmo, em várias vezes, com o computador ao lado. Cada exemplo pode ser copiado para um ficheiro, ou escrito na consola do Python, e corrido.

## Neste guia

1. O que vais aprender
2. O que já sabes e vais usar
3. Os dados de um jogo andam juntos
4. Tuplos: valores que andam juntos
5. Dicionários: procurar por chave
6. Percorrer um dicionário
7. Contar com um dicionário
8. Conjuntos: valores sem repetidos
9. As chavetas com três papéis
10. A coleção vazia
11. Escolher a representação
12. Exemplo guiado: o resumo das sessões do clube
13. Erros frequentes
14. Palavras novas deste guia
15. Verificar o que aprendeste
16. O que vem a seguir

## O que vais aprender

No fim deste guia, consegues:

- guardar num tuplo valores que andam juntos, e dar um nome a cada um de uma vez, desempacotando-o;
- guardar pares de chave e valor num dicionário, e procurar um valor pela chave sem o programa parar quando a chave não existe;
- percorrer um dicionário pelas chaves, pelos pares ou só pelos valores;
- contar quantas vezes aparece cada valor de uma lista, com um dicionário;
- tirar os repetidos de uma coleção com um conjunto, e explicar porque é que um conjunto não substitui sempre uma lista;
- distinguir os três papéis das chavetas;
- escolher a coleção que serve um problema e justificar a escolha;
- testar um programa com valores repetidos, com uma coleção vazia e com uma chave que não existe.

## O que já sabes e vais usar

- Correr um script, usar a consola do Python e ler um traceback de baixo para cima: guia [01 Do pseudocódigo ao Python](01-do-pseudocodigo-ao-python.md).
- A rotina de cinco passos para procurar um erro: guia [01 Do pseudocódigo ao Python](01-do-pseudocodigo-ao-python.md).
- As variáveis, as constantes, os tipos, o `input` e a conversão com `int`: guia [02 Dados e interação](02-dados-e-interacao.md).
- A divisão inteira, com `//`, e o resto, com `%`: guia [02 Dados e interação](02-dados-e-interacao.md).
- As funções predefinidas `abs`, `max`, `min` e `type`: guia [02 Dados e interação](02-dados-e-interacao.md).
- O `if`, o `elif` e o `else`, e o `not`: guia [03 Seleção](03-selecao.md).
- O contador, o acumulador e o `for` com o `range`: guia [04 Ciclos while e for](04-ciclos-while-e-for.md).
- As listas, o índice, o `len`, o `for` sobre a lista e a pesquisa com uma bandeira e o `break`: guia [05 Listas](05-listas.md).
- O catálogo do clube de videojogos, com quatro dados por jogo: guia [07 Textos e listas que mudam](07-textos-e-listas-que-mudam.md).
- Os índices, as fatias, o `in` e o `not in`: guia [07 Textos e listas que mudam](07-textos-e-listas-que-mudam.md).
- Os métodos `strip`, `upper`, `lower` e `split`: guia [07 Textos e listas que mudam](07-textos-e-listas-que-mudam.md).
- Os valores imutáveis, como os textos, e os mutáveis, como as listas: guia [07 Textos e listas que mudam](07-textos-e-listas-que-mudam.md).
- As f-strings: guia [07 Textos e listas que mudam](07-textos-e-listas-que-mudam.md).
- As listas que crescem com o `append`, o `sum`, o `sorted` e o cuidado com a lista vazia: guia [07 Textos e listas que mudam](07-textos-e-listas-que-mudam.md).
- A tabela de iterações, para seguir um ciclo volta a volta: guia [04 Repetição e arrays](../01-algoritmos/04-repeticao-e-arrays.md), secção "A tabela de iterações".
- Os casos de teste, com o resultado esperado calculado à mão antes de correr: guia [03 Decisões e validação](../01-algoritmos/03-decisoes-e-validacao.md), secção "Fronteiras e casos de teste".

## Os dados de um jogo andam juntos

Este é outra vez o catálogo do clube de videojogos, com os quatro dados de cada jogo:

| Código | Título | Género | Ano |
| --- | --- | --- | ---: |
| `PLA-01` | Super Mario Bros. Wonder | plataformas | 2023 |
| `PLA-02` | Celeste | plataformas | 2018 |
| `COR-01` | Forza Horizon 5 | corridas | 2021 |
| `DES-01` | Rocket League | desporto | 2015 |
| `DES-02` | EA Sports FC 25 | desporto | 2024 |
| `PUZ-01` | Tetris | puzzle | 1984 |
| `AVE-01` | Minecraft | aventura | 2011 |

Com o que aprendeste até agora, este catálogo guarda-se em quatro listas. Há uma de códigos, uma de títulos, uma de géneros e uma de anos. O jogo do índice 2 é o que está no índice 2 das quatro listas. Funciona, mas tem riscos.

O primeiro risco é o desalinhamento. Antes de leres a resposta, tenta prever o que escreve a última linha.

```text
>>> titulos = ["Celeste", "Tetris", "Minecraft"]
>>> anos = [2018, 1984, 2011]
>>> titulos.remove("Tetris")
>>> print(titulos[1], anos[1])
Minecraft 1984
```

Leitura guiada: o Tetris saiu da lista dos títulos, mas o ano dele ficou na lista dos anos. O Minecraft passou do índice 2 para o 1, e agora aparece com o ano do Tetris. O Python não dá nenhum aviso, porque, para ele, são duas listas sem nada a ver uma com a outra. É um erro de lógica. Daí para a frente, cada jogo fica com o ano do jogo que estava antes dele, e o último ano fica sem título.

O segundo risco é a procura. Para encontrar o jogo `DES-01`, percorre-se a lista dos códigos até dar com ele, e depois lê-se o mesmo índice nas outras três. Num catálogo de mil jogos, podem ser mil comparações para encontrar um.

Os dois riscos têm a mesma origem: os quatro dados de um jogo andam sempre juntos, e o programa guarda-os separados. Neste guia vais conhecer três coleções novas. O tuplo junta os dados de um jogo num só valor. O dicionário encontra um jogo pelo código, sem percorrer nada. E o conjunto guarda valores sem repetidos, como os géneros que há no catálogo.

## Tuplos: valores que andam juntos

Um jogo do catálogo não é um valor, são quatro, e não faz sentido ter o título de um jogo com o ano de outro. Para guardar um grupo de valores que andam juntos, o Python tem o **tuplo**.

Um tuplo escreve-se com os valores entre parênteses curvos, separados por vírgulas: `("Celeste", "plataformas", 2018)`. Como numa lista, cada valor tem um índice, a partir de 0, e o `len` diz quantos são. Os valores de um tuplo podem ser de tipos diferentes, como dois textos e um número. A diferença para a lista é que um tuplo é imutável: depois de criado, não muda, como um texto.

Antes de leres as respostas, tenta prever as cinco linhas.

```text
>>> jogo = ("Celeste", "plataformas", 2018)
>>> jogo[0]
'Celeste'
>>> jogo[-1]
2018
>>> len(jogo)
3
>>> "plataformas" in jogo
True
>>> jogo[2] = 2019
```

As quatro primeiras dão `'Celeste'`, `2018`, `3` e `True`. O índice negativo e o `in` funcionam como nas listas e nos textos. A última para com uma mensagem que acaba assim:

```text
TypeError: 'tuple' object does not support item assignment
```

Quer dizer "erro de tipo: um objeto `tuple` não aceita que se dê um valor a um elemento". É a mensagem dos textos, com outro tipo. Um tuplo também não tem o `append` nem o `remove`. Com `jogo.append(1)`, a mensagem acaba em `'tuple' object has no attribute 'append'`, isto é, o tuplo não tem nenhum `append` depois do ponto.

Porque é que se quer uma coleção que não muda? Porque o tuplo protege o grupo. O ano de um jogo não muda por engano a meio do programa, e ninguém lhe acrescenta um quinto valor sem querer. Se for mesmo preciso outro ano, faz-se o que se fazia com os textos: constrói-se um tuplo novo, e guarda-se na variável. Com `jogo = (jogo[0], jogo[1], 2019)`, a variável passa a guardar um tuplo novo, com os dois primeiros valores do antigo e o ano novo.

### Desempacotar um tuplo

Para usar os valores de um tuplo, podes ler cada um pelo índice. Mas `jogo[0]` não diz o que é, e `jogo[2]` obriga a lembrar a ordem. Há uma forma mais clara, que dá um nome a cada valor de uma vez:

```python
titulo, genero, ano = jogo
```

À esquerda do `=` estão três variáveis, e à direita um tuplo com três valores. O primeiro valor vai para a primeira variável, o segundo para a segunda e o terceiro para a terceira. Dar a cada valor de uma coleção uma variável própria, numa só linha, chama-se **desempacotar**. Depois desta linha, `titulo` vale `"Celeste"`, `genero` vale `"plataformas"` e `ano` vale `2018`.

É como abrir uma encomenda com três coisas lá dentro e pôr cada uma na sua gaveta. Se tiveres duas gavetas para três coisas, ou quatro gavetas para três, alguma coisa não bate certo.

O número de variáveis tem de ser igual ao número de valores. Com `titulo, genero = jogo`, o programa para com esta mensagem:

```text
ValueError: too many values to unpack (expected 2, got 3)
```

Quer dizer "erro de valor: valores a mais para desempacotar; esperavam-se 2 e vieram 3". Com variáveis a mais, como `codigo, titulo, genero, ano = jogo`, a mensagem acaba em `not enough values to unpack (expected 4, got 3)`, isto é, "valores a menos". Antes do Python 3.14, a primeira mensagem acaba em `(expected 2)`, sem o `got 3`.

### Uma lista de tuplos

Um tuplo guarda um jogo. Para guardar o catálogo, junta-se um tuplo por jogo numa lista. Cada elemento da lista é um tuplo, e o desempacotar funciona no próprio `for`. Em cada volta, o tuplo do jogo desempacota-se nas variáveis do ciclo.

Antes de correres este exemplo, tenta prever que jogos aparecem.

```python
# jogos_antigos.py: escreve os jogos do catálogo que saíram antes de 2016.
ANO_LIMITE = 2016

jogos = [("Celeste", 2018), ("Rocket League", 2015), ("Tetris", 1984), ("Minecraft", 2011)]
for titulo, ano in jogos:
    if ano < ANO_LIMITE:
        print(f"{titulo} ({ano})")
```

O resultado é este:

```text
Rocket League (2015)
Tetris (1984)
Minecraft (2011)
```

Como é a primeira vez que um `for` desempacota tuplos, segue a execução volta a volta:

| Volta | Tuplo da volta | `titulo` | `ano` | `ano < ANO_LIMITE` |
| ---: | --- | --- | ---: | --- |
| 1 | `("Celeste", 2018)` | `"Celeste"` | 2018 | `False` |
| 2 | `("Rocket League", 2015)` | `"Rocket League"` | 2015 | `True` |
| 3 | `("Tetris", 1984)` | `"Tetris"` | 1984 | `True` |
| 4 | `("Minecraft", 2011)` | `"Minecraft"` | 2011 | `True` |

Leitura guiada: o `for` percorre a lista, como no tema 05, e cada elemento é um tuplo com dois valores. Por isso, o `for` tem duas variáveis, separadas por uma vírgula, e cada volta desempacota o tuplo nelas. O resto é um `if` como os outros. O título e o ano de cada jogo nunca se desalinham, porque viajam no mesmo tuplo.

A lista é mutável, e o tuplo não. Numa lista de tuplos, podes acrescentar um jogo com o `append`, ou trocar um tuplo inteiro pelo índice, como `jogos[0] = ("Celeste", 2019)`. O que não podes é mudar um valor dentro de um tuplo, como `jogos[0][1] = 2019`, que dá o `TypeError` dos tuplos.

### Tuplo ou lista?

As duas guardam valores por ordem, com índice. Escolhe-se pela forma de os valores se relacionarem:

- Uma lista guarda muitos valores do mesmo tipo, que podem aumentar ou diminuir. São exemplos os anos dos jogos e os nomes na fila para a consola.
- Um tuplo guarda um grupo fixo de valores com significados diferentes, que descrevem uma só coisa. São exemplos o título, o género e o ano de um jogo, ou o x e o y de uma posição num mapa.

Uma regra prática: se faz sentido acrescentar mais um elemento, é uma lista. Se acrescentar um elemento mudava o significado do grupo, é um tuplo. Acrescentar mais um ano à lista dos anos é normal. Acrescentar um quinto valor ao tuplo de um jogo já não diz o que é.

## Dicionários: procurar por chave

O clube guarda quantas cópias tem de cada jogo. Com o que sabes, isso dava duas listas alinhadas, uma de títulos e outra de cópias. Para saber quantas cópias há de "Celeste", percorria-se a lista dos títulos até o encontrar, e lia-se o número com o mesmo índice. Antes de leres a resposta, tenta prever o que escreve este script:

```python
# copias_listas.py: procura quantas cópias o clube tem de um jogo, com duas listas.
titulos = ["Minecraft", "Tetris", "Celeste", "Rocket League"]
copias = [2, 1, 3, 2]

procura = "Celeste"
for i in range(0, len(titulos)):
    if titulos[i] == procura:
        print(procura, "tem", copias[i], "cópias")
```

Funciona, e escreve `Celeste tem 3 cópias`. Mas obriga a um ciclo só para encontrar um valor, e as duas listas têm de ficar sempre alinhadas.

No dia a dia, procuramos muitas coisas por um nome, e não por uma posição. Num dicionário de português, procuras a palavra e lês o significado. Na lista de contactos do telemóvel, procuras o nome e lês o número. Ninguém pergunta "qual é o número do contacto na posição 37?".

Um **dicionário** é uma coleção de pares. Cada par tem uma **chave**, que é o que se procura, e um **valor**, que é o que se encontra. Escreve-se entre chavetas, com cada par na forma `chave: valor`, e os pares separados por vírgulas:

```python
copias = {"Minecraft": 2, "Tetris": 1, "Celeste": 3, "Rocket League": 2}
```

Aqui, as chavetas não estão dentro de uma f-string: abrem e fecham o dicionário. As chaves são os títulos, e os valores são as cópias. Para ler um valor, escreve-se a chave entre parênteses retos, como se escrevia o índice de uma lista: `copias["Celeste"]` dá `3`, sem ciclo nenhum.

Num dicionário, cada chave aparece uma só vez. Não pode haver dois "Celeste", tal como uma palavra não aparece duas vezes num dicionário de português. Os valores, esses, podem repetir-se: há dois jogos com 2 cópias.

Repara na diferença para a lista. Numa lista, o que está entre os parênteses retos é uma posição, que o Python escolhe: 0, 1, 2. Num dicionário, é uma chave, que és tu que escolhes: um título, um código, um nome. É por isso que um dicionário serve para procurar.

### Acrescentar e alterar

Um dicionário é mutável, como uma lista. Dar um valor a uma chave faz uma de duas coisas. Se a chave ainda não existe, acrescenta o par. Se já existe, substitui o valor antigo.

Antes de correres este exemplo, tenta prever as três linhas que aparecem.

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

Leitura guiada: o primeiro `print` lê o valor da chave `"Celeste"`. A linha seguinte é uma atribuição como as outras. O lado direito lê o 1 e soma-lhe 1, e o 2 passa a ser o valor de `"Tetris"`. A seguir, `"Portal 2"` ainda não existia, e por isso entra como um par novo, no fim. O `print` mostra o dicionário inteiro, entre chavetas, com as chaves entre plicas. O `len` de um dicionário conta os pares, que agora são 5.

A mesma linha, `copias[chave] = valor`, acrescenta ou substitui, conforme a chave já exista ou não. É prático, e também é um perigo. Quem quer acrescentar um jogo novo pode apagar, sem dar por isso, um jogo que já lá estava com a mesma chave. O laboratório trata este caso num dos desafios.

### A chave que não existe

O que acontece quando se procura uma chave que não está no dicionário? Este script pergunta um título e mostra as cópias. Antes de o correres, tenta prever o que acontece se a pessoa escrever `Portal 2`.

```python
# copias_erro.py: procura um jogo que não está no dicionário.
copias = {"Minecraft": 2, "Tetris": 1, "Celeste": 3, "Rocket League": 2}
titulo = input("Que jogo procuras? ")
print(titulo, "tem", copias[titulo], "cópias")
```

O programa para com esta mensagem:

```text
Traceback (most recent call last):
  File "C:\Users\aluno\Documents\fp-python\copias_erro.py", line 4, in <module>
    print(titulo, "tem", copias[titulo], "cópias")
                         ~~~~~~^^^^^^^^
KeyError: 'Portal 2'
```

Leitura guiada: lê-se de baixo para cima. `KeyError` quer dizer "erro de chave", e a seguir vem a chave que não existe, `'Portal 2'`. Os sinais `~` e `^` apontam para `copias[titulo]`. É o `IndexError` dos dicionários: em vez de um índice fora dos limites, uma chave que não está lá. O caminho do ficheiro, a seguir a `File`, muda de computador para computador.

Tal como antes de um `remove`, a solução é perguntar primeiro, com o `in`. Num dicionário, o `in` pergunta se uma chave existe:

```python
# procurar_copias.py: diz quantas cópias o clube tem de um jogo, se o jogo existir.
copias = {"Minecraft": 2, "Tetris": 1, "Celeste": 3, "Rocket League": 2}

titulo = input("Que jogo procuras? ").strip()
if titulo in copias:
    print(f"{titulo}: {copias[titulo]} cópias")
else:
    print(f"O clube não tem {titulo}.")
```

Antes de correres, tenta prever o que aparece com `Celeste`, com `Portal 2` e com `celeste`, em minúsculas.

Com `Celeste`, aparece `Celeste: 3 cópias`. Com `Portal 2`, aparece `O clube não tem Portal 2.`. Com `celeste`, aparece `O clube não tem celeste.`, porque a chave é `"Celeste"`, com maiúscula, e para o Python são textos diferentes.

Leitura guiada: o `in` só pergunta pelas chaves, e nunca pelos valores. `3 in copias` dá `False`, mesmo havendo um jogo com 3 cópias. A leitura com `copias[titulo]` só acontece no bloco do `if`, quando a chave existe de certeza. Por isso, este programa nunca para com `KeyError`.

### Um valor pode ser qualquer valor

Os valores de um dicionário podem ser de qualquer tipo, também um tuplo. As chaves costumam ser textos ou números. É assim que se guarda o catálogo inteiro do clube. A chave é o código, e o valor é um tuplo com o título, o género e o ano.

```python
catalogo = {
    "PLA-02": ("Celeste", "plataformas", 2018),
    "PUZ-01": ("Tetris", "puzzle", 1984)
}
titulo, genero, ano = catalogo["PLA-02"]
```

O `catalogo["PLA-02"]` dá o tuplo do jogo, e a linha desempacota-o nas três variáveis. Para ler só o título, sem desempacotar, escreve-se `catalogo["PLA-02"][0]`. Lê-se da esquerda para a direita: primeiro a chave dá o tuplo, e depois o índice 0 dá o primeiro valor do tuplo.

Repara na forma. Quando um dicionário não cabe numa linha, escreve-se um par por linha, indentado. A chaveta que fecha fica sozinha na última linha. Entre dois pares há sempre uma vírgula, e só o último par não a leva.

Com o catálogo assim, os dois riscos do início do guia desaparecem. Os quatro dados de um jogo não se desalinham, porque estão no mesmo par. E encontrar um jogo pelo código é uma linha, sem ciclo.

## Percorrer um dicionário

Muitas vezes é preciso passar por todos os pares de um dicionário: para os mostrar, para os somar ou para escolher alguns. Há três maneiras, conforme o que interessa em cada volta.

Um `for` sobre um dicionário dá as chaves, uma por volta, pela ordem em que os pares entraram. Para ter as chaves e os valores, usa-se o método `items`, que quer dizer "itens". Em cada volta, ele dá um tuplo com a chave e o valor. O tuplo desempacota-se nas duas variáveis do `for`, como numa lista de tuplos. Para ter só os valores, usa-se o método `values`, que quer dizer "valores".

Antes de correres este exemplo, tenta prever as linhas que aparecem.

```python
# listar_copias.py: escreve os títulos, as cópias de cada jogo e o total de cópias do clube.
copias = {"Minecraft": 2, "Tetris": 1, "Celeste": 3, "Rocket League": 2}

for titulo in copias:
    print(titulo)
print()
print("Cópias de cada jogo:")
for titulo, quantas in copias.items():
    print(f"{titulo}: {quantas}")
print("Total de cópias:", sum(copias.values()))
```

O resultado é este:

```text
Minecraft
Tetris
Celeste
Rocket League

Cópias de cada jogo:
Minecraft: 2
Tetris: 1
Celeste: 3
Rocket League: 2
Total de cópias: 8
```

Leitura guiada: o primeiro `for` percorre o dicionário diretamente, e a variável recebe só as chaves, os títulos. O segundo usa o `items`, e em cada volta o tuplo da chave e do valor desempacota-se em `titulo` e `quantas`. A última linha usa o `values`, que dá só os valores, 2, 1, 3 e 2, e o `sum` soma-os.

| Forma | O que a variável recebe em cada volta |
| --- | --- |
| `for chave in dicionario:` | a chave |
| `for chave, valor in dicionario.items():` | a chave e o valor |
| `for valor in dicionario.values():` | só o valor |
| `for chave in sorted(dicionario):` | a chave, por ordem |

A última linha da tabela serve para percorrer as chaves por ordem. Num dicionário, o `sorted` devolve uma lista com as chaves, ordenadas: `sorted(copias)` dá `['Celeste', 'Minecraft', 'Rocket League', 'Tetris']`. Para ter o valor de cada chave dentro desse ciclo, lê-se com `copias[chave]`, que existe de certeza, porque a chave veio do próprio dicionário.

O dicionário guarda os pares pela ordem em que entraram, e é por essa ordem que o `for` os percorre. Mas num dicionário procura-se pela chave, e não pela posição: `copias[0]` não é o primeiro par. É a chave `0`, que não existe, e dá `KeyError: 0`.

## Contar com um dicionário

O clube faz uma votação para o jogo do mês, e cada sócio vota num título. No fim, quer saber quantos votos teve cada jogo. Sem um dicionário, precisavas de um contador por jogo, e de saber à partida em que jogos se ia votar. Com um dicionário, cada jogo votado é uma chave, e o valor é o seu contador. Os contadores vão nascendo à medida que os jogos aparecem.

O padrão é este. Para cada valor da coleção que se conta, há dois casos:

- se o valor já é uma chave do dicionário, soma-se 1 ao seu contador;
- se ainda não é, é a primeira vez que aparece, e entra no dicionário com o contador a 1.

O dicionário começa vazio. O `{}`, as chavetas sem nada lá dentro, é um dicionário vazio, sem pares. Antes de correres este exemplo, tenta prever quantas chaves fica o dicionário a ter, e o valor de cada uma.

```python
# votos.py: conta os votos dos sócios do clube para o jogo do mês.
votos = ["Minecraft", "Tetris", "Minecraft", "Celeste", "Tetris", "Minecraft"]

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

O resultado é este:

```text
Minecraft: 3
Tetris: 2
Celeste: 1
```

Como é a primeira vez que este padrão aparece, segue-o volta a volta.

| Volta | `jogo` | Já é chave? | `votos_por_jogo` depois da volta |
| ---: | --- | --- | --- |
| antes | | | `{}` |
| 1 | Minecraft | não | `{'Minecraft': 1}` |
| 2 | Tetris | não | `{'Minecraft': 1, 'Tetris': 1}` |
| 3 | Minecraft | sim | `{'Minecraft': 2, 'Tetris': 1}` |
| 4 | Celeste | não | `{'Minecraft': 2, 'Tetris': 1, 'Celeste': 1}` |
| 5 | Tetris | sim | `{'Minecraft': 2, 'Tetris': 2, 'Celeste': 1}` |
| 6 | Minecraft | sim | `{'Minecraft': 3, 'Tetris': 2, 'Celeste': 1}` |

Leitura guiada: o dicionário nasce vazio, antes do ciclo, como um contador nasce a 0. Em cada volta, o `if` pergunta se o jogo já tem contador. Na volta 1, ainda não tem, e o `else` cria-o com 1. Na volta 3, o Minecraft já tem, e o `if` soma-lhe 1. No fim, o segundo `for` mostra cada par, pela ordem em que os jogos apareceram pela primeira vez.

Repara no que o dicionário não tem. Se nenhum sócio votou no Tetris, o Tetris não aparece com 0: simplesmente não é uma chave. Um dicionário de contagens só tem as chaves dos valores que apareceram.

O erro típico é tirar o `if` e deixar só a soma. Na primeira volta, `votos_por_jogo["Minecraft"] + 1` lê uma chave que ainda não existe, e o programa para com `KeyError: 'Minecraft'`.

## Conjuntos: valores sem repetidos

O clube regista o nome de cada sócio, de cada vez que ele vem. No fim da semana, a lista tem os nomes repetidos: o Rui veio três vezes. A pergunta é outra: quantos sócios diferentes vieram, e quem foram?

No dia a dia, há coleções em que cada valor só conta uma vez. Os países carimbados num passaporte: ir duas vezes a Espanha não dá dois países. Os cromos diferentes de uma caderneta: um repetido não preenche nenhum espaço novo.

Um **conjunto** é uma coleção sem repetidos e sem ordem. Cada valor está lá ou não está, uma só vez. Cria-se de duas maneiras. A função `set`, que quer dizer "conjunto" em inglês, recebe uma lista e devolve o conjunto dos seus valores, sem os repetidos. Ou escrevem-se os valores entre chavetas, separados por vírgulas, sem os dois pontos dos dicionários: `{"puzzle", "aventura"}`.

Antes de correres este exemplo, tenta prever as quatro linhas.

```python
# presencas.py: os sócios que vieram ao clube esta semana, sem repetidos.
presencas = ["Rui", "Ana", "Rui", "Bia", "Ana", "Rui"]

socios = set(presencas)
print("Presenças:", len(presencas))
print("Sócios diferentes:", len(socios))
print(sorted(socios))
if "Bia" in socios:
    print("A Bia veio esta semana.")
```

O resultado é este:

```text
Presenças: 6
Sócios diferentes: 3
['Ana', 'Bia', 'Rui']
A Bia veio esta semana.
```

Leitura guiada: a lista tem seis nomes, e o conjunto feito a partir dela tem três, porque os repetidos ficaram uma só vez. O `sorted` devolve uma lista com os valores do conjunto por ordem alfabética, para se mostrarem sempre pela mesma ordem. O `in` pergunta se um valor está no conjunto, como nas outras coleções.

Para acrescentar um valor a um conjunto, usa-se o método `add`, que quer dizer "acrescentar". Se o valor já lá estiver, nada muda. Um conjunto é mutável: o `add` muda o próprio conjunto, como o `append` muda uma lista, e não devolve nada. Antes de leres a resposta, tenta prever o tamanho do conjunto no fim.

```text
>>> generos = {"puzzle", "aventura"}
>>> generos.add("corridas")
>>> generos.add("puzzle")
>>> len(generos)
3
```

Leitura guiada: o primeiro `add` acrescenta as corridas, e o conjunto passa a ter três géneros. O segundo `add` tenta acrescentar o puzzle, que já lá estava, e o conjunto fica igual. Não há erro nem aviso: num conjunto, acrescentar um valor que já existe não faz nada.

### Um conjunto não tem ordem

Um conjunto não guarda a ordem dos valores. Se escreveres `print(socios)`, aparece algo como `{'Rui', 'Ana', 'Bia'}`, e a ordem pode mudar de uma vez que corres o programa para a seguinte. É por isso que o exemplo acima usa o `sorted` antes de mostrar: dá uma lista, com uma ordem que não muda.

Também por isso, um conjunto não tem índices. Com `socios[0]`, o programa para com uma mensagem que acaba assim:

```text
TypeError: 'set' object is not subscriptable
```

Quer dizer "erro de tipo: um objeto `set` não aceita índices". Num conjunto, não há primeiro nem último. Só se pergunta se um valor lá está, com o `in`, ou se percorrem os valores com o `for`. A ordem do `for` não se escolhe.

### O conjunto vazio

O conjunto vazio escreve-se `set()`, e não `{}`. As chavetas vazias são um dicionário vazio, porque os dicionários vieram primeiro na linguagem. Na consola, `type({})` dá `<class 'dict'>`, e `type(set())` dá `<class 'set'>`.

O erro típico é escrever `generos = {}` para começar um conjunto. Na primeira vez que se faz `generos.add("puzzle")`, o programa para com esta mensagem:

```text
AttributeError: 'dict' object has no attribute 'add'
```

Quer dizer "erro de atributo: um objeto `dict` não tem `add`". Um atributo é o que se escreve depois do ponto, como o nome de um método. Os dicionários não têm o método `add`, porque um dicionário guarda pares, e não valores soltos. Corrige-se começando com `generos = set()`.

### Porque é que um conjunto não substitui sempre uma lista

Se o conjunto tira os repetidos, porque não usar sempre conjuntos? Porque, ao tirar os repetidos e a ordem, perde informação. Com a lista das presenças, sabes que o Rui veio três vezes e quem chegou primeiro. Com o conjunto, só sabes que o Rui veio.

Por isso, a pergunta decide. Se queres saber quem veio, serve o conjunto. Se queres saber quantas vezes veio cada um, ou por que ordem, precisas da lista, ou de um dicionário de contagens feito a partir dela. Um conjunto não serve para uma fila, nem para uma tabela de pontuações, nem para nada em que os repetidos ou a ordem contem.

## As chavetas com três papéis

As chavetas, `{` e `}`, aparecem agora em três sítios do Python, com três papéis diferentes. Convém distingui-los à primeira vista.

| Onde aparecem | Exemplo | O que são |
| --- | --- | --- |
| Dentro de um texto com um `f` antes das aspas | `f"Jogo: {titulo}"` | o sítio onde entra um valor, numa f-string |
| Fora de um texto, com pares separados por dois pontos | `{"Tetris": 1, "Celeste": 3}` | um dicionário |
| Fora de um texto, com valores soltos | `{"puzzle", "aventura"}` | um conjunto |
| Fora de um texto, sem nada lá dentro | `{}` | um dicionário vazio |

Duas perguntas resolvem quase todos os casos. Primeiro: as chavetas estão dentro de umas aspas com o `f` à frente? Se estão, é uma f-string. Se não estão, a segunda pergunta: há dois pontos lá dentro? Se há, é um dicionário; se não há, é um conjunto. As chavetas vazias são a exceção, e são um dicionário.

Antes de leres as respostas, aplica as duas perguntas a cada linha e prevê o tipo.

```text
>>> type({"Tetris": 1})
<class 'dict'>
>>> type({"puzzle", "aventura"})
<class 'set'>
>>> type({})
<class 'dict'>
>>> type(set())
<class 'set'>
```

Leitura guiada: a primeira linha tem dois pontos, e é um dicionário. A segunda tem valores soltos, e é um conjunto. A terceira são as chavetas vazias, um dicionário. A última é a forma de escrever um conjunto vazio, com a função `set`. Numa f-string, o `type` não se aplica às chavetas: elas desaparecem, e o que fica é um texto.

## A coleção vazia

Cada coleção tem a sua forma vazia. São o texto vazio, `""`, a lista vazia, `[]`, e o tuplo vazio, `()`. Há também o dicionário vazio, `{}`, e o conjunto vazio, `set()`. Todas têm `len` igual a 0. Uma coleção vazia não é um erro: é um caso que os programas encontram muitas vezes. Um sócio que ainda não escolheu jogos, uma semana em que ninguém veio ao clube, uma votação em que ninguém votou.

Com uma coleção vazia, umas operações funcionam e outras param o programa:

| Operação | Com a coleção vazia |
| --- | --- |
| `for x in colecao:` | dá zero voltas, e o corpo não se executa |
| `len(colecao)` | dá 0 |
| `x in colecao` | dá `False` |
| `sum(lista)` | dá 0 |
| `sorted(colecao)` | dá a lista vazia, `[]` |
| `max(colecao)` e `min(colecao)` | param o programa com `ValueError` |
| `sum(lista) / len(lista)` | para o programa com `ZeroDivisionError` |
| `lista[0]` | para o programa com `IndexError` |
| `dicionario[chave]` | para o programa com `KeyError` |

Por isso, a coleção vazia é sempre um dos casos de teste, como o caso de zero voltas de um ciclo. Pergunta-se se tem elementos antes do que não funciona sem eles, com `len(colecao) == 0`, que se lê como se diz: "a coleção tem zero elementos". Num dicionário, pergunta-se também se a chave existe, com o `in`, antes de a ler.

## Escolher a representação

Antes de escrever o código, escolhe-se a forma de guardar os dados. A forma escolhida chama-se **representação**. Um mesmo problema pode guardar-se de várias formas, e uma boa escolha torna o código mais curto e mais claro. Viste-o nas cópias dos jogos: com duas listas era preciso um ciclo, e com um dicionário bastava uma linha.

A escolha começa antes das coleções. Um jogo verdadeiro tem capa, preço, estúdio, idade mínima, número de jogadores e muito mais. O catálogo do clube guarda só o código, o título, o género e o ano. São os dados de que as perguntas do clube precisam. Guardar só o que o problema precisa, na forma que lhe serve, chama-se **abstração**. Abstrair é decidir o que deixar de fora, e não só o que guardar. Um mapa do metro é uma abstração. Não mostra as ruas nem as distâncias certas, só as linhas e as estações, porque é disso que precisa quem viaja. Vais voltar a esta ideia no tema seguinte, com as funções.

Depois, escolhe-se a coleção. Fazem-se quatro perguntas aos dados:

1. A ordem interessa?
2. Pode haver repetidos, e eles contam?
3. Procura-se pela posição, ou por um nome ou um código?
4. Os valores mudam depois de guardados?

A tabela resume as respostas de cada coleção:

| Coleção | Guarda a ordem? | Aceita repetidos? | Procura-se por | Muda? | Serve para |
| --- | --- | --- | --- | --- | --- |
| Texto, `str` | sim | sim | posição | não | uma sequência de caracteres |
| Lista, `list` | sim | sim | posição | sim | muitos valores do mesmo tipo, que crescem ou diminuem |
| Tuplo, `tuple` | sim | sim | posição | não | um grupo fixo de valores que descrevem uma só coisa |
| Dicionário, `dict` | a ordem de entrada | chaves não; valores sim | chave | sim | encontrar um valor por um nome ou um código |
| Conjunto, `set` | não | não | só "está ou não está" | sim | valores sem repetidos, e perguntar se um valor existe |

Os dados do clube mostram as cinco escolhas:

| Os dados | A coleção | Porquê |
| --- | --- | --- |
| O código de um jogo, `"PLA-01"` | texto | uma sequência de caracteres, que se lê por fatias |
| Os anos dos jogos, para a média | lista | valores do mesmo tipo; os repetidos contam |
| O título, o género e o ano de um jogo | tuplo | um grupo fixo que descreve um só jogo |
| O catálogo, procurado pelo código | dicionário | procura-se pelo código, e não pela posição |
| Os géneros que há no catálogo | conjunto | cada género conta uma só vez |

Uma escolha justifica-se com as quatro perguntas. "Escolhi um dicionário porque é mais fácil" não justifica nada. "Escolhi um dicionário porque o clube procura cada jogo pelo código, e não pela posição" justifica. Uma tabela assim, com os dados, a coleção escolhida e o porquê, chama-se uma tabela de decisões, e é a que vais fazer no laboratório.

Às vezes, há mais do que uma escolha certa. A ordem de chegada de uma corrida pode ser uma lista ou um tuplo. É uma lista se a corrida ainda está a decorrer e os atletas vão chegando. É um tuplo se a corrida acabou e a ordem já não muda. O que decide é o problema, e a justificação diz qual é.

## Exemplo guiado: o resumo das sessões do clube

### Passo 1: o problema

> De cada vez que alguém joga no clube, a pessoa que está de serviço regista o código do jogo, por ordem. O clube quer um programa que, no fim da semana, mostre quantas sessões se registaram e quantas sessões teve cada jogo, pelo título. Quer saber também quantos jogos diferentes se jogaram e qual foi o maior número de sessões de um só jogo. Por fim, quer saber que códigos foram registados por engano, porque não existem no catálogo, cada um uma vez.

A lista das sessões desta semana é esta:

```python
sessoes = ["AVE-01", "DES-01", "PUZ-09", "AVE-01", "PLA-02", "DES-01", "AVE-01", "PUZ-09"]
```

O catálogo é o do início deste guia, num dicionário com o código como chave e o tuplo do jogo como valor.

### Passo 2: escolher as coleções

Antes de escrever código, responde-se às quatro perguntas para cada dado.

| Os dados | A coleção | Porquê |
| --- | --- | --- |
| As sessões | lista, já dada | têm ordem, e os repetidos contam: cada sessão é uma sessão |
| O catálogo | dicionário, do código para o tuplo do jogo | procura-se cada jogo pelo código de uma sessão |
| As sessões de cada jogo | dicionário, do código para o número de sessões | é contar com um dicionário, com uma chave por jogo |
| Os códigos desconhecidos | conjunto | cada código errado mostra-se uma só vez, mesmo que apareça duas |

Falta uma pergunta: os jogos diferentes. Podia ser outro conjunto, com os códigos das sessões. Mas o dicionário das sessões de cada jogo já tem uma chave por jogo jogado, e as chaves não se repetem. O número de jogos diferentes é o `len` desse dicionário. Um conjunto a mais guardava a mesma informação duas vezes.

### Passo 3: os resultados esperados, à mão

Percorre-se a lista e conta-se cada código. O `AVE-01` aparece 3 vezes, o `DES-01` 2 vezes e o `PLA-02` 1 vez. O `PUZ-09` aparece 2 vezes, mas não está no catálogo.

| Pergunta | Esperado |
| --- | --- |
| Sessões registadas | 8 |
| Códigos desconhecidos | `PUZ-09`, uma vez |
| Jogos diferentes | 3 |
| Sessões de cada jogo | Minecraft 3, Rocket League 2, Celeste 1 |
| O maior número de sessões de um jogo | 3, as do Minecraft |

### Passo 4: o script completo

```python
# sessoes.py: o resumo das sessões de jogo do clube de videojogos.
# Conta as sessões e as sessões de cada jogo, diz o maior número de sessões
# de um só jogo e avisa dos códigos registados que não estão no catálogo.

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
        # Um código fora do catálogo é um engano no registo: guarda-se uma vez
        # e não se conta como jogo.
        desconhecidos.add(codigo)
    elif codigo in sessoes_por_jogo:
        sessoes_por_jogo[codigo] = sessoes_por_jogo[codigo] + 1
    else:
        sessoes_por_jogo[codigo] = 1

print("Sessões registadas:", len(sessoes))
for codigo in sorted(desconhecidos):
    print("Código desconhecido:", codigo)
# As chaves de um dicionário não se repetem: há uma por jogo jogado.
print("Jogos diferentes:", len(sessoes_por_jogo))
for codigo, quantas in sessoes_por_jogo.items():
    titulo = catalogo[codigo][0]
    print(f"{titulo}: {quantas}")

if len(sessoes_por_jogo) == 0:
    print("Ainda não há sessões de jogos do catálogo.")
else:
    # O max dos valores dá o maior número de sessões; sem nenhum valor, parava o programa.
    print("Mais sessões de um só jogo:", max(sessoes_por_jogo.values()))
```

Antes de correres, confere com a tabela do passo 3 o que esperas ver. O resultado é este:

```text
Sessões registadas: 8
Código desconhecido: PUZ-09
Jogos diferentes: 3
Minecraft: 3
Rocket League: 2
Celeste: 1
Mais sessões de um só jogo: 3
```

Leitura guiada: lê-se em quatro partes. A primeira são os dados: o catálogo e a lista das sessões. A segunda é o ciclo que percorre as sessões. Cada código cai num de três casos. Se não está no catálogo, vai para o conjunto dos desconhecidos. Se já tem contador, soma 1. Se é a primeira sessão desse jogo, o contador nasce a 1. A terceira parte mostra os resultados. O `sorted` dá uma ordem fixa ao conjunto, e o `catalogo[codigo][0]` vai buscar o título ao tuplo do jogo. A quarta parte mostra o maior número de sessões de um só jogo, só quando há pelo menos um jogo. O `values` dá os números de sessões, 3, 2 e 1. O `max` escolhe o maior, como o `max` de uma lista no tema 07.

### Passo 5: testar com os casos que enganam

Um programa com coleções testa-se sempre com valores repetidos, com a coleção vazia e com uma chave que não existe. Para cada caso, muda-se a linha `sessoes = [...]` e corre-se outra vez. Antes de correres cada um, escreve o que esperas.

| `sessoes` | O que testa | O que o Python mostra |
| --- | --- | --- |
| a lista do problema | repetidos e um código desconhecido repetido | as sete linhas do passo 4 |
| `[]` | a coleção vazia | `Sessões registadas: 0`, `Jogos diferentes: 0` e `Ainda não há sessões de jogos do catálogo.` |
| `["XYZ-01"]` | só uma chave que não existe | `Sessões registadas: 1`, `Código desconhecido: XYZ-01`, `Jogos diferentes: 0` e a mensagem de não haver sessões |
| `["AVE-01", "AVE-01"]` | um só jogo, repetido | `Jogos diferentes: 1`, `Minecraft: 2` e `Mais sessões de um só jogo: 2` |

Sem o `if len(sessoes_por_jogo) == 0`, o caso da lista vazia parava com `ValueError: max() iterable argument is empty`, na linha do `max`. O dicionário das sessões ficava vazio, e o `max` de nada não tem resposta. Sem o `if codigo not in catalogo`, o `PUZ-09` passava a ser um jogo, e o programa parava com `KeyError: 'PUZ-09'` ao ir buscar o título.

### Passo 6: porque não bastava um conjunto

Um conjunto feito a partir das sessões, `set(sessoes)`, dava os códigos que apareceram: quatro, contando com o `PUZ-09`. Responde a "que jogos se jogaram?", e a mais nada. Ao tirar os repetidos, deita fora o número de sessões de cada jogo, e sem ele não há o maior número de sessões. A lista das sessões guarda tudo, e o dicionário resume-a sem perder as contagens. O conjunto entrou onde a pergunta era mesmo "cada um uma vez": os códigos desconhecidos.

## Erros frequentes

Os erros desta secção não ficaram nas secções anteriores. Para cada um, ficas a saber o que aparece, porque acontece e como se corrige. Os outros estão na secção da ideia que explicam:

- o desalinhamento de duas listas, em "Os dados de um jogo andam juntos";
- mudar um tuplo e desempacotar com as variáveis erradas, em "Tuplos: valores que andam juntos";
- a chave que não existe, e o `in` que só pergunta pelas chaves, em "Dicionários: procurar por chave";
- o índice num dicionário, em "Percorrer um dicionário";
- o contador sem o `if`, em "Contar com um dicionário";
- o índice num conjunto e o `{}` como conjunto vazio, em "Conjuntos: valores sem repetidos".

### Mudar o ano de um jogo do catálogo

O que se vê, com `catalogo["PLA-02"][2] = 2019`: o programa para com `TypeError: 'tuple' object does not support item assignment`. Parece estranho, porque um dicionário é mutável.

Acontece porque a linha não mexe no dicionário. O `catalogo["PLA-02"]` dá o tuplo do jogo, e é a esse tuplo que a linha tenta mudar o índice 2. O dicionário é mutável, mas o tuplo guardado lá dentro continua a ser um tuplo, e um tuplo não muda. Como se muda o ano de um jogo do catálogo é um dos desafios do laboratório.

### O código escrito noutra forma, num dicionário

O que se vê: o código `"PLA-02"` existe no catálogo, mas a pessoa escreve `pla-02`, ou `PLA-02 ` com um espaço no fim. O `in` dá `False`, e o programa diz que não há esse jogo. Sem o `in`, para com `KeyError: 'pla-02'`.

Acontece porque uma chave só se encontra se o texto for exatamente igual. É o mesmo cuidado do tema anterior, agora com as chaves. Corrige-se arrumando o que vem do teclado antes de procurar, para ficar na forma das chaves. Para os códigos do clube, é `input(...).strip().upper()`.

## Palavras novas deste guia

- Tuplo: um grupo fixo de valores entre parênteses curvos, separados por vírgulas, que não se altera.
- Desempacotar: dar a cada valor de uma coleção uma variável própria, numa só linha, como `titulo, genero, ano = jogo`.
- Dicionário: uma coleção de pares chave e valor, em que se procura o valor pela chave.
- Chave: num dicionário, o que se procura; cada chave aparece uma só vez.
- Valor: num dicionário, o que se encontra com a chave.
- `KeyError`: o erro de procurar num dicionário uma chave que não existe.
- `items` e `values`: os métodos que dão, para percorrer, os pares de um dicionário ou só os seus valores.
- Dicionário de contagens: um dicionário em que cada chave é um valor que apareceu e o valor é quantas vezes apareceu.
- Conjunto: uma coleção sem repetidos e sem ordem.
- `set`: a função que cria um conjunto; `set()` é o conjunto vazio.
- `add`: o método que acrescenta um valor a um conjunto; se o valor já lá estiver, nada muda.
- Coleção vazia: uma coleção sem nenhum elemento, com `len` igual a 0.
- Representação: a forma escolhida para guardar os dados de um problema.
- Abstração: guardar só o que o problema precisa, na forma que lhe serve.
- Tabela de decisões: uma tabela com os dados de um problema, a coleção escolhida para cada um e porquê.

## Verificar o que aprendeste

Usa estas perguntas para te testares. Responde a cada uma sem olhar para o guia. Se não conseguires, volta à secção que explica a ideia.

1. Porque é que guardar os títulos e os anos em duas listas separadas é arriscado? Dá um exemplo de uma linha que as desalinha.
2. Com `jogo = ("Tetris", "puzzle", 1984)`, o que dá `jogo[-1]`? E `len(jogo)`? E o que acontece com `jogo[2] = 1989`?
3. O que acontece com `titulo, ano = ("Tetris", "puzzle", 1984)`? Como se corrige?
4. Porque é que o título, o género e o ano de um jogo se guardam num tuplo? E porque é que os anos de todos os jogos ficam numa lista?
5. Com `copias = {"Tetris": 1, "Celeste": 3}`, o que faz `copias["Tetris"] = 2`? E `copias["Portal 2"] = 1`? E o que dá `copias["Minecraft"]`?
6. O que dá `3 in {"Tetris": 1, "Celeste": 3}`? Porquê?
7. Num dicionário, o que dá a variável do `for` em cada volta, sem `items`? E com `items`? E com `values`?
8. Num dicionário de contagens, porque é que o `if` que pergunta se a chave existe é obrigatório?
9. Quantos elementos tem `set([5, 1, 5, 5, 2])`? Porque é que `{}` não é um conjunto vazio?
10. Dá uma situação em que um conjunto não pode substituir uma lista, e diz porquê.
11. Diz o que é cada um: `f"{nome}"`, `{"nome": 1}`, `{"nome"}` e `{}`.
12. Que operações param o programa com uma coleção vazia? Como se evita?
13. Que coleção escolhias para guardar o número de golos de cada jogador de uma equipa, para o procurar pelo nome? Justifica com as quatro perguntas.

## O que vem a seguir

Para praticar este tema, faz o [laboratório](laboratorios/08-tuplos-dicionarios-e-conjuntos-laboratorio.md). Nele constróis o programa do catálogo do clube. Guardas os jogos numa lista de tuplos e depois num dicionário, e procuras um jogo pelo código. Mostras também os géneros sem repetidos e contas os jogos de cada género. Depois faz a [ficha de exercícios](exercicios/08-tuplos-dicionarios-e-conjuntos-exercicios.md). Tem exercícios com cada coleção, um script com erros para encontrar e uma escolha de coleções para justificar.

O tema seguinte é Funções, mutabilidade e transformações legíveis. Vais escrever funções que recebem coleções e devolvem resultados, e ver quando uma função muda a coleção que recebeu. Vais também voltar à abstração, agora com as funções.

![Rodapé](../imagens/rodape.png)
