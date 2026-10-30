![Cabeçalho](../imagens/cabecalho.png)

# Coleções, strings e escolha de representação

Módulo Criar aplicações em linguagem de programação Python. Neste guia aprendes a guardar muitos valores de uma vez, em textos, listas, tuplos, dicionários e conjuntos. Aprendes também a escolher a forma de os guardar que serve cada problema. Para praticar, há o [laboratório](02-colecoes-strings-e-representacao-laboratorio.md) e a [ficha de exercícios](02-colecoes-strings-e-representacao-exercicios.md) deste tema.

No tema anterior, as listas vinham escritas no programa e nunca mudavam de tamanho. Os textos serviam só para mostrar mensagens. Neste tema, as listas crescem e encolhem enquanto o programa corre, e os textos leem-se carácter a carácter. Aparecem também três formas novas de guardar valores: os tuplos, os dicionários e os conjuntos. Este tema ainda não escreve funções que recebem e alteram coleções, nem guarda nada em ficheiros. Isso fica para os temas seguintes.

Lê-se ao teu ritmo, em várias vezes, com o computador ao lado. Cada exemplo pode ser copiado para um ficheiro, ou escrito na consola do Python, e corrido.

## Neste guia

1. O que vais aprender
2. O que já sabes e vais usar
3. O catálogo do clube de videojogos
4. Um texto é uma sequência de caracteres
5. Fatias de um texto
6. Perguntar se um texto contém outro, com `in`
7. Os métodos dos textos
8. Um texto não se altera
9. Juntar textos e valores com f-strings
10. Listas que crescem e encolhem
11. Funções predefinidas para listas
12. Tuplos: valores que andam juntos
13. Dicionários: procurar por chave
14. Percorrer um dicionário
15. Contar com um dicionário
16. Conjuntos: valores sem repetidos
17. A coleção vazia
18. Escolher a representação
19. Exemplo guiado: o resumo das sessões do clube
20. Erros frequentes
21. Palavras novas deste guia
22. Verificar o que aprendeste
23. O que vem a seguir

## O que vais aprender

No fim deste guia, consegues:

- ler um carácter de um texto pela posição, tirar-lhe uma fatia e percorrê-lo com `for`;
- usar os métodos `upper`, `lower`, `strip` e `split` para arrumar e partir textos;
- escrever mensagens que juntam textos e valores com f-strings;
- acrescentar e tirar elementos de uma lista, e usar `sum`, `max`, `min` e `sorted`;
- guardar valores que andam juntos num tuplo, e procurar valores por uma chave num dicionário;
- tirar os repetidos de uma coleção com um conjunto;
- prever como fica uma coleção depois de cada operação;
- escolher a coleção que serve um problema e explicar a escolha;
- testar um programa com valores repetidos, com uma coleção vazia e com uma chave que não existe.

## O que já sabes e vais usar

- Correr um script e usar a consola do Python: guia [01 Do pseudocódigo ao Python](01-do-pseudocodigo-ao-python.md), secção "Correr um script".
- O `print`, as variáveis e as constantes: guia [01](01-do-pseudocodigo-ao-python.md), secções "Escrever no ecrã com `print`" e "Variáveis sem tipo à frente".
- Os tipos `int`, `float`, `str` e `bool`, e o `None`: guia [01](01-do-pseudocodigo-ao-python.md), secção "Os tipos dos valores".
- As contas, com `//` e `%`: guia [01](01-do-pseudocodigo-ao-python.md), secção "Contas e divisões".
- As funções predefinidas `abs`, `max`, `min`, `round`, `int` e `type`: guia [01](01-do-pseudocodigo-ao-python.md), secção "Funções predefinidas".
- O `input`, a conversão com `int` e `str`, e o `+` entre dois textos: guia [01](01-do-pseudocodigo-ao-python.md), secção "Ler do teclado com `input`, e converter".
- O `if`, o `elif`, o `else` e o `while`: guia [01](01-do-pseudocodigo-ao-python.md), secções "Decidir com `if`, `elif` e `else`" e "Repetir com `while`".
- O `for` com o `range`, e o fim do `range` que não entra: guia [01](01-do-pseudocodigo-ao-python.md), secção "Contar voltas com `for` e `range`".
- As listas, o índice a partir de 0 e o `len`: guia [01](01-do-pseudocodigo-ao-python.md), secção "Percorrer uma lista com `for`".
- O `for` sobre uma lista e mudar um elemento pelo índice: a mesma secção do guia [01](01-do-pseudocodigo-ao-python.md).
- O `break`, o `continue` e a bandeira: guia [01](01-do-pseudocodigo-ao-python.md), secção "Parar e continuar: `break` e `continue`".
- Os três tipos de erro, o traceback e a rotina para procurar um erro: guia [01](01-do-pseudocodigo-ao-python.md), secção "Os três tipos de erro".
- O contador e o acumulador: guia [04 Repetição e arrays](../01-algoritmos/04-repeticao-e-arrays.md), secção "Contadores e acumuladores".
- A sentinela: guia [04](../01-algoritmos/04-repeticao-e-arrays.md), secção "A sentinela: ler até aparecer o valor que diz "acabou"".
- As fronteiras e os casos de teste, com o resultado esperado calculado à mão: guia [03 Decisões e validação](../01-algoritmos/03-decisoes-e-validacao.md), secção "Fronteiras e casos de teste".

## O catálogo do clube de videojogos

Neste guia, e nos temas seguintes de Python, os exemplos vêm do catálogo de um clube de videojogos de uma escola. O clube foi inventado para as aulas, e os jogos são jogos que conheces. Cada jogo do catálogo tem quatro dados:

| Código | Título | Género | Ano |
| --- | --- | --- | ---: |
| `PLA-01` | Super Mario Bros. Wonder | plataformas | 2023 |
| `PLA-02` | Celeste | plataformas | 2018 |
| `COR-01` | Forza Horizon 5 | corridas | 2021 |
| `DES-01` | Rocket League | desporto | 2015 |
| `DES-02` | EA Sports FC 25 | desporto | 2024 |
| `PUZ-01` | Tetris | puzzle | 1984 |
| `AVE-01` | Minecraft | aventura | 2011 |

O código é a forma de o clube identificar cada jogo sem enganos. As três primeiras letras dizem o género, e os dois algarismos do fim numeram os jogos desse género. O ano é o ano em que o jogo saiu.

Com o que aprendeste no tema 01, como guardavas este catálogo num programa? Uma hipótese é usar quatro listas: uma de códigos, uma de títulos, uma de géneros e uma de anos. Funciona, mas tem riscos. Se apagares um título e te esqueceres de apagar o ano, as listas desalinham-se. Daí para a frente, cada jogo fica com o ano do jogo seguinte. E, para encontrar o jogo `DES-01`, tens de percorrer a lista dos códigos até dares com ele.

Os programas guardam muitas vezes grupos de valores: os jogos de um catálogo, as letras de um nome, os sócios que vieram ao clube. Um valor que guarda outros valores chama-se **coleção**. A lista do tema 01 é uma coleção. Neste guia vais conhecer outras quatro: o texto, o tuplo, o dicionário e o conjunto. Cada uma guarda os valores de uma maneira diferente, e serve melhor certos problemas.

## Um texto é uma sequência de caracteres

Um texto, o tipo `str`, também é uma coleção. Guarda uma sequência de caracteres, por ordem. Um **carácter** é uma letra, um algarismo, um sinal ou um espaço. O código `"PLA-01"` tem seis caracteres: `P`, `L`, `A`, `-`, `0` e `1`.

Cada carácter tem uma posição, o **índice**, que começa em 0, como nas listas. Lê-se um carácter com o índice entre parênteses retos, e o `len` diz quantos caracteres tem o texto:

| Carácter | `P` | `L` | `A` | `-` | `0` | `1` |
| --- | --- | --- | --- | --- | --- | --- |
| Índice | 0 | 1 | 2 | 3 | 4 | 5 |

Antes de leres as respostas, tenta prever o que a consola mostra em cada linha.

```text
>>> codigo = "PLA-01"
>>> codigo[0]
'P'
>>> codigo[3]
'-'
>>> len(codigo)
6
>>> codigo[-1]
'1'
```

Leitura guiada: `codigo[0]` é o primeiro carácter, e `codigo[3]` é o hífen, o quarto. A consola mostra os textos entre plicas, as aspas simples, para se ver que são textos. O `len` conta os seis caracteres, e o último índice válido é 5, um a menos. A última linha é nova. Um **índice negativo** conta a partir do fim: `-1` é o último carácter, `-2` o penúltimo, e assim por diante. Dá jeito quando não sabes o tamanho do texto.

Um texto percorre-se com `for`, como uma lista. Em cada volta, a variável do ciclo recebe o carácter seguinte. Antes de correres este exemplo, tenta prever as duas linhas que aparecem.

```python
# espacos.py: conta os espaços do título de um jogo, percorrendo-o carácter a carácter.
titulo = "Super Mario Bros. Wonder"
espacos = 0
for caracter in titulo:
    if caracter == " ":
        espacos = espacos + 1
print("Espaços:", espacos)
print("Palavras:", espacos + 1)
```

O resultado é este:

```text
Espaços: 3
Palavras: 4
```

Leitura guiada: é o contador do guia 04 da algoritmia, agora sobre os caracteres de um texto. O `for` dá à variável `caracter` cada carácter do título, um por volta: `S`, `u`, `p` e assim por diante, 24 voltas. O contador só aumenta quando o carácter é um espaço. Há um espaço entre cada duas palavras, por isso as palavras são uma a mais do que os espaços.

O erro típico é usar um índice que não existe. Com `codigo[6]`, a consola responde com uma mensagem de erro que acaba nesta linha:

```text
IndexError: string index out of range
```

Quer dizer "erro de índice: índice do texto fora dos limites". É o erro das listas do tema 01, agora num texto. Num texto de 6 caracteres, o último índice é 5. As mensagens de erro deste guia são as do Python 3.14, como no guia 01. Numa versão mais antiga, algumas têm outras palavras.

## Fatias de um texto

Muitas vezes não queres um carácter, mas um pedaço do texto. Do código `"PLA-01"`, queres o género, `"PLA"`, ou o número, `"01"`. Um pedaço de um texto, tirado por posições, chama-se **fatia**.

Uma fatia escreve-se com dois índices separados por dois pontos: `codigo[0:3]`. O primeiro índice entra na fatia, e o segundo não entra, como no `range`. Por isso, `codigo[0:3]` dá os caracteres dos índices 0, 1 e 2.

Antes de leres as respostas, olha para a tabela de índices da secção anterior e tenta prever cada fatia.

```text
>>> codigo = "PLA-01"
>>> codigo[0:3]
'PLA'
>>> codigo[4:6]
'01'
>>> codigo[:3]
'PLA'
>>> codigo[4:]
'01'
>>> codigo[4:20]
'01'
```

Leitura guiada: `codigo[0:3]` começa no índice 0 e para antes do 3, o hífen. `codigo[4:6]` dá os dois algarismos, porque o 6 já não entra. Quando falta o primeiro índice, como em `[:3]`, a fatia começa no início. Quando falta o segundo, como em `[4:]`, vai até ao fim. A última linha mostra uma diferença em relação ao índice. Uma fatia que passa do fim do texto não dá erro: fica com os caracteres que existem.

| Fatia | O que dá | Com `"PLA-01"` |
| --- | --- | --- |
| `texto[a:b]` | do índice `a` até antes do `b` | `codigo[1:3]` dá `"LA"` |
| `texto[:b]` | do início até antes do `b` | `codigo[:3]` dá `"PLA"` |
| `texto[a:]` | do índice `a` até ao fim | `codigo[4:]` dá `"01"` |

Uma fatia é sempre um texto novo, mesmo com um só carácter. O texto de onde saiu fica igual.

O erro típico é contar o fim como se entrasse. Quem escreve `codigo[0:2]` para tirar o género fica com `"PL"`, sem o `A`, e o Python não dá nenhum aviso. É um erro de lógica, e só o apanha quem compara o resultado com o que esperava.

## Perguntar se um texto contém outro, com `in`

Um sócio do clube lembra-se de que o jogo tinha "Mario" no título, mas não se lembra do resto. Para saber se um texto aparece dentro de outro, o Python tem o operador `in`. A expressão `"Mario" in titulo` dá `True` se o texto `"Mario"` aparecer em algum sítio de `titulo`, e `False` se não aparecer. O `not in` faz o contrário.

Antes de leres as respostas, tenta prever as três linhas.

```text
>>> "Mario" in "Super Mario Bros. Wonder"
True
>>> "mario" in "Super Mario Bros. Wonder"
False
>>> "Kart" not in "Super Mario Bros. Wonder"
True
```

Leitura guiada: a primeira dá `True`, porque o título contém "Mario". A segunda dá `False`, e é esta que surpreende. Para o Python, o `m` minúsculo e o `M` maiúsculo são caracteres diferentes. A terceira pergunta se "Kart" não está no título, e não está.

É a palavra `in` do `for`, mas com outro papel. No `for`, o `in` diz que coleção se percorre. Numa condição, pergunta se um valor está dentro de uma coleção. Vais vê-lo com este segundo papel em todas as coleções deste guia.

A segunda linha levanta um problema. O sócio pode escrever "mario", e a procura falha só por causa da maiúscula. A secção seguinte resolve-o.

## Os métodos dos textos

Os textos que vêm do teclado raramente chegam arrumados. Quem escreve um código pode escrever `" pla-01 "`, com espaços e em minúsculas. Quem procura um título pode escrever "MARIO". Antes de comparar textos, é preciso arrumá-los.

Para isso, cada texto traz consigo funções próprias. Uma função que pertence a um valor chama-se **método**. Chama-se escrevendo o valor, um ponto e o nome do método, com os parênteses: `titulo.upper()`. Os parênteses são obrigatórios, mesmo quando não levam nada lá dentro.

Estes são os quatro métodos dos textos que vais usar mais:

| Método | O que devolve | Exemplo | Resultado |
| --- | --- | --- | --- |
| `upper()` | o texto em maiúsculas | `"pla-01".upper()` | `"PLA-01"` |
| `lower()` | o texto em minúsculas | `"Minecraft".lower()` | `"minecraft"` |
| `strip()` | o texto sem os espaços do início e do fim | `"  pla-01 ".strip()` | `"pla-01"` |
| `split()` | uma lista com as palavras do texto | `"Super Mario Bros. Wonder".split()` | `['Super', 'Mario', 'Bros.', 'Wonder']` |

O `split` merece uma linha mais. Sem nada entre os parênteses, parte o texto nos espaços. Com um texto entre os parênteses, parte o texto nesse sinal: `"PLA-01".split("-")` dá a lista `['PLA', '01']`. É uma ponte entre os textos e as listas.

Antes de leres a resposta, tenta prever o que mostra a última linha.

```text
>>> titulo = "Celeste"
>>> titulo.upper()
'CELESTE'
>>> titulo
'Celeste'
```

Leitura guiada: o `upper` devolveu `'CELESTE'`, mas a variável `titulo` ficou como estava. Um método de um texto nunca muda o texto. Devolve um texto novo, que podes mostrar ou guardar. Para guardares o resultado, escreves `titulo = titulo.upper()`. A secção seguinte explica porquê.

Os métodos podem encadear-se, e é assim que se arruma o que vem do teclado. Antes de correres este exemplo, tenta prever o que aparece se a pessoa escrever `  MARIO ` com espaços, e depois `kart`.

```python
# procurar_titulo.py: diz se uma palavra aparece no título de um jogo,
# sem ligar às maiúsculas nem aos espaços à volta.
titulo = "Super Mario Bros. Wonder"
procura = input("Que palavra procuras? ").strip().lower()
if procura in titulo.lower():
    print("Aparece no título.")
else:
    print("Não aparece no título.")
```

Com `  MARIO `, aparece "Aparece no título.". Com `kart`, aparece "Não aparece no título.".

Leitura guiada: a linha do `input` lê-se da esquerda para a direita. O `input` devolve o texto escrito. O `strip` tira-lhe os espaços, e o `lower` passa o resultado a minúsculas. Com `  MARIO `, fica `"mario"`. Na condição, o título também passa a minúsculas, só para a comparação. Assim, as maiúsculas deixam de contar dos dois lados. A variável `titulo` continua com as maiúsculas originais.

## Um texto não se altera

Imagina que o clube muda o género de um jogo e o código `"PLA-01"` deve passar a começar por `D`. A ideia natural é mudar o primeiro carácter, como se muda um elemento de uma lista. Com `codigo[0] = "D"`, a consola responde com uma mensagem que acaba nesta linha:

```text
TypeError: 'str' object does not support item assignment
```

Quer dizer "erro de tipo: um objeto `str` não aceita que se dê um valor a um elemento". Para o Python, um objeto é um valor, e `'str' object` quer dizer "um valor do tipo `str`". O Python não deixa mudar um carácter de um texto. Depois de criado, um texto nunca muda.

Um valor que não se pode alterar depois de criado diz-se **imutável**. Os textos são imutáveis. Um valor que se pode alterar diz-se **mutável**. As listas são mutáveis: no tema 01, `pontuacoes[1] = 9` mudava um elemento da lista.

Então, como se muda um código? Não se muda: constrói-se um texto novo, e guarda-se na variável. Antes de leres a resposta, tenta prever o que mostra a última linha.

```text
>>> codigo = "PLA-01"
>>> codigo = "D" + codigo[1:]
>>> codigo
'DLA-01'
```

Leitura guiada: o lado direito faz-se primeiro, como em qualquer atribuição. Junta o `"D"` à fatia `"LA-01"`, e o resultado é um texto novo, `"DLA-01"`. Depois, a variável `codigo` passa a guardar esse texto. O texto `"PLA-01"` não mudou: a variável é que passou a guardar outro texto.

É também por isso que `titulo = titulo.upper()` funciona. O `upper` não muda o texto antigo. Cria um novo, e a atribuição guarda-o na variável. Sem a atribuição, o texto novo perde-se.

## Juntar textos e valores com f-strings

O clube quer mostrar cada jogo assim: `Celeste (2018)`, com o ano entre parênteses e sem espaços a mais. Com o `print` e as vírgulas, isso não sai. O `print` põe um espaço entre cada dois valores. Com o `+` e o `str`, sai, mas fica comprido: `titulo + " (" + str(ano) + ")"`.

Para isto, o Python tem as **f-strings**. Uma f-string é um texto com um `f` antes das aspas. Dentro dele, cada par de chavetas, `{` e `}`, marca o sítio onde entra um valor. O Python calcula o que está entre as chavetas e põe o resultado no lugar delas, já convertido em texto.

Antes de correres este exemplo, tenta prever as três linhas.

```python
# ficha_jogo.py: escreve a ficha de um jogo, primeiro com vírgulas e depois com f-strings.
ANO_ATUAL = 2026

titulo = "Celeste"
genero = "plataformas"
ano = 2018
print(titulo, "(", ano, ")")
print(f"{titulo} ({ano}), um jogo de {genero}")
print(f"Saiu há {ANO_ATUAL - ano} anos")
```

O resultado é este:

```text
Celeste ( 2018 )
Celeste (2018), um jogo de plataformas
Saiu há 8 anos
```

Leitura guiada: o primeiro `print` usa vírgulas, e os espaços aparecem à volta do ano. O segundo usa uma f-string, e cada par de chavetas é substituído pelo valor da variável. Os parênteses e a vírgula ficam exatamente onde os escreveste. No terceiro, as chavetas têm uma conta, `ANO_ATUAL - ano`, e o Python escreve o resultado, 8. Entre as chavetas pode ir qualquer expressão: uma variável, uma conta ou uma chamada, como `{len(titulo)}` ou `{round(media, 1)}`.

Com as f-strings, não precisas de converter os números com `str`, nem de cuidar dos espaços. Escreves a mensagem como a queres ver, e pões os valores nos sítios certos. O `print` com vírgulas continua certo, e usa-se quando os espaços não importam.

As chavetas vão aparecer neste guia com mais dois papéis, nos dicionários e nos conjuntos. Numa f-string, estão sempre dentro de um texto com o `f` antes das aspas, e marcam só onde entra um valor.

O erro típico é esquecer o `f`. Com `print("{titulo} ({ano})")`, aparece no ecrã `{titulo} ({ano})`, tal e qual. Sem o `f`, as chavetas são caracteres como os outros, e o Python não substitui nada. Não há mensagem de erro: é um erro de lógica, que se vê no ecrã.

## Listas que crescem e encolhem

No tema 01, as listas vinham escritas no programa, com os valores todos. Mas muitas vezes não se sabe quantos valores vão ser. Um sócio do clube quer fazer a lista dos jogos que quer experimentar, e pode querer dois ou dez. A lista tem de começar vazia e crescer à medida que ele os escreve.

Uma **lista vazia** escreve-se com os parênteses retos sem nada lá dentro: `[]`. Para lhe acrescentar um elemento no fim, usa-se o método `append`, que quer dizer "acrescentar". Com `quero_jogar.append("PLA-02")`, a lista ganha mais um elemento, e muda. As listas são mutáveis, e os métodos das listas mudam a própria lista, ao contrário dos métodos dos textos.

Este script lê códigos até a pessoa carregar em Enter sem escrever nada. O texto vazio, `""`, faz de sentinela, como o -1 da campanha de recolha de alimentos. Antes de correres, tenta prever o que aparece se a pessoa escrever `pla-02`, `AVE-01`, ` cor-01` e, por fim, carregar em Enter sem escrever nada.

```python
# quero_jogar.py: junta numa lista os códigos dos jogos que um sócio quer experimentar.
# Lê códigos até a pessoa carregar em Enter sem escrever nada.
quero_jogar = []
codigo = input("Código do jogo (Enter para acabar): ").strip().upper()
while codigo != "":
    quero_jogar.append(codigo)
    codigo = input("Código do jogo (Enter para acabar): ").strip().upper()
print("Jogos na lista:", len(quero_jogar))
print(quero_jogar)
```

O ecrã fica assim, com o que a pessoa escreveu a seguir a cada pergunta:

```text
Código do jogo (Enter para acabar): pla-02
Código do jogo (Enter para acabar): AVE-01
Código do jogo (Enter para acabar):  cor-01
Código do jogo (Enter para acabar): 
Jogos na lista: 3
['PLA-02', 'AVE-01', 'COR-01']
```

Como é a primeira vez que uma lista cresce num ciclo, segue a execução volta a volta:

| Teste | `codigo` | `codigo != ""` | Durante a volta | `quero_jogar` depois da volta |
| --- | --- | --- | --- | --- |
| 1.º | `"PLA-02"` | `True` | acrescenta o código e lê o seguinte | `['PLA-02']` |
| 2.º | `"AVE-01"` | `True` | acrescenta o código e lê o seguinte | `['PLA-02', 'AVE-01']` |
| 3.º | `"COR-01"` | `True` | acrescenta o código e lê o texto vazio | `['PLA-02', 'AVE-01', 'COR-01']` |
| 4.º | `""` | `False` | o ciclo termina | `['PLA-02', 'AVE-01', 'COR-01']` |

Leitura guiada: a lista nasce vazia, antes do ciclo. É o ciclo da sentinela do guia 04: uma leitura antes do ciclo e outra no fim do corpo. Em cada volta, o `append` acrescenta o código lido ao fim da lista. Os códigos entram já arrumados, por causa do `strip` e do `upper`. O último `print` mostra a lista inteira, com os parênteses retos e cada texto entre plicas. Se a pessoa carregar logo em Enter, o ciclo dá zero voltas, e aparecem `Jogos na lista: 0` e `[]`.

Para tirar um elemento, há o método `remove`, que quer dizer "remover". Recebe o valor, e não o índice, e tira a primeira vez que esse valor aparece. Com a lista acima, `quero_jogar.remove("AVE-01")` deixa `['PLA-02', 'COR-01']`.

E se o valor não estiver na lista? Com `quero_jogar.remove("DES-01")`, o programa para com uma mensagem que acaba assim:

```text
ValueError: list.remove(x): x not in list
```

Quer dizer "erro de valor: o `x` não está na lista". Antes de remover, pergunta-se se o valor lá está, com o `in`, que também funciona com listas:

```python
if "DES-01" in quero_jogar:
    quero_jogar.remove("DES-01")
else:
    print("Esse jogo não está na tua lista.")
```

| Operação | O que faz à lista | Com `["PLA-02", "AVE-01"]` |
| --- | --- | --- |
| `lista.append(x)` | acrescenta `x` no fim | `append("COR-01")` dá `["PLA-02", "AVE-01", "COR-01"]` |
| `lista.remove(x)` | tira a primeira vez que `x` aparece | `remove("PLA-02")` dá `["AVE-01"]` |
| `lista[i] = x` | põe `x` no índice `i` | `lista[0] = "DES-01"` dá `["DES-01", "AVE-01"]` |
| `x in lista` | não muda nada; diz se `x` está na lista | `"AVE-01" in lista` dá `True` |

## Funções predefinidas para listas

No tema 01, o `max` e o `min` recebiam dois ou mais valores separados por vírgulas. Também podem receber uma lista, e devolvem o maior ou o menor dos elementos. Há mais duas funções predefinidas que trabalham com listas: o `sum`, que soma os elementos, e o `sorted`, que os ordena.

Esta é a lista dos anos dos jogos do catálogo. Antes de leres as respostas, tenta prever cada linha. Repara bem nas duas últimas.

```text
>>> anos = [2023, 2018, 2021, 2015, 2024, 1984, 2011]
>>> sum(anos)
14096
>>> max(anos)
2024
>>> min(anos)
1984
>>> sorted(anos)
[1984, 2011, 2015, 2018, 2021, 2023, 2024]
>>> anos
[2023, 2018, 2021, 2015, 2024, 1984, 2011]
```

Leitura guiada: o `sum` soma os sete anos, e o `max` e o `min` encontram o ano do jogo mais recente e do mais antigo. O `sorted` devolve uma lista nova, com os mesmos elementos, do menor para o maior. A última linha mostra que a lista `anos` não mudou. O `sorted` não arruma a lista. Faz uma cópia arrumada, e a original fica como estava.

Com uma lista de textos, o `sorted` usa a ordem alfabética. `sorted(["Tetris", "Minecraft", "Celeste"])` dá `['Celeste', 'Minecraft', 'Tetris']`. Atenção às maiúsculas: para o Python, todas as maiúsculas vêm antes das minúsculas.

Com o `sum` e o `len`, a média faz-se numa linha: `sum(anos) / len(anos)`. Dá `2013.714...`, e `round(sum(anos) / len(anos), 1)` dá `2013.7`.

| Função | O que devolve | Com `[30, 5, 12]` |
| --- | --- | --- |
| `len(lista)` | quantos elementos tem | `3` |
| `sum(lista)` | a soma dos elementos | `47` |
| `max(lista)` | o maior elemento | `30` |
| `min(lista)` | o menor elemento | `5` |
| `sorted(lista)` | uma lista nova, ordenada | `[5, 12, 30]` |

O `len`, o `max`, o `min` e o `sorted` servem também para os textos e para os conjuntos. O `sum` só soma números. O `len` de um texto conta os caracteres, como já viste, e o `sorted` de um texto devolve a lista dos seus caracteres por ordem.

O erro típico aparece com a lista vazia. O `sum([])` dá 0, mas o `max([])` e o `min([])` não têm resposta, porque não há nenhum elemento para escolher. O programa para com esta mensagem:

```text
ValueError: max() iterable argument is empty
```

Quer dizer "erro de valor: o argumento do `max` está vazio". No Python 3.9, a mesma situação diz `max() arg is an empty sequence`. Antes de pedir o maior, confirma que a lista tem elementos, como confirmavas que havia valores antes de calcular uma média.

## Tuplos: valores que andam juntos

Um jogo do catálogo não é um valor, são quatro: o código, o título, o género e o ano. Andam sempre juntos, e não faz sentido ter o título de um jogo com o ano de outro. Para guardar um grupo de valores que andam juntos, o Python tem o **tuplo**.

Um tuplo escreve-se com os valores entre parênteses curvos, separados por vírgulas: `("Celeste", "plataformas", 2018)`. Como na lista, cada valor tem um índice, a partir de 0, e o `len` diz quantos são. A diferença é que um tuplo é imutável: depois de criado, não muda.

Antes de leres as respostas, tenta prever as três linhas.

```text
>>> jogo = ("Celeste", "plataformas", 2018)
>>> jogo[0]
'Celeste'
>>> len(jogo)
3
>>> jogo[2] = 2019
```

As duas primeiras dão `'Celeste'` e `3`. A terceira para com uma mensagem que acaba assim:

```text
TypeError: 'tuple' object does not support item assignment
```

Quer dizer "erro de tipo: um objeto `tuple` não aceita que se dê um valor a um elemento". É a mensagem dos textos, com outro tipo. O tuplo protege o grupo: o ano de um jogo não muda por engano a meio do programa.

### Desempacotar um tuplo

Para usar os valores de um tuplo, podes ler cada um pelo índice. Mas `jogo[0]` não diz o que é, e `jogo[2]` obriga a lembrar a ordem. Há uma forma mais clara, que dá um nome a cada valor de uma vez:

```python
titulo, genero, ano = jogo
```

À esquerda do `=` estão três variáveis, e à direita um tuplo com três valores. O primeiro valor vai para a primeira variável, o segundo para a segunda e o terceiro para a terceira. Dar a cada valor de uma coleção uma variável própria, numa só linha, chama-se **desempacotar**. Depois desta linha, `titulo` vale `"Celeste"`, `genero` vale `"plataformas"` e `ano` vale `2018`.

O número de variáveis tem de ser igual ao número de valores. Com `titulo, genero = jogo`, o programa para com esta mensagem:

```text
ValueError: too many values to unpack (expected 2, got 3)
```

Quer dizer "erro de valor: valores a mais para desempacotar; esperavam-se 2 e vieram 3". No Python 3.9, a mensagem acaba em `(expected 2)`.

O desempacotar funciona também no `for`, quando cada elemento de uma lista é um tuplo. Em `for titulo, ano in [("Celeste", 2018), ("Tetris", 1984)]:`, cada volta desempacota um tuplo nas duas variáveis.

### Tuplo ou lista?

As duas guardam valores por ordem, com índice. Escolhe-se pela forma de os valores se relacionarem:

- Uma lista guarda muitos valores do mesmo tipo, que podem aumentar ou diminuir. São exemplos os anos dos jogos e os códigos que um sócio quer jogar.
- Um tuplo guarda um grupo fixo de valores com significados diferentes, que descrevem uma só coisa. São exemplos o título, o género e o ano de um jogo, ou o x e o y de um ponto num mapa.

Uma regra prática: se faz sentido acrescentar mais um elemento, é uma lista. Se acrescentar um elemento mudava o significado do grupo, é um tuplo.

## Dicionários: procurar por chave

O clube guarda quantas cópias tem de cada jogo. Com o que sabes do tema 01, isso dava duas listas alinhadas, uma de títulos e outra de cópias. Para saber quantas cópias há de "Celeste", percorria-se a lista dos títulos até o encontrar, e lia-se o número com o mesmo índice. Antes de leres a resposta, tenta prever o que escreve este script:

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

### Acrescentar e alterar

Um dicionário é mutável. Dar um valor a uma chave faz uma de duas coisas. Se a chave ainda não existe, acrescenta o par. Se já existe, substitui o valor antigo.

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

Leitura guiada: a primeira linha do `print` lê o valor da chave `"Celeste"`. A linha seguinte é uma atribuição como as outras. O lado direito lê o 1 e soma-lhe 1, e o 2 passa a ser o valor de `"Tetris"`. A seguir, `"Portal 2"` ainda não existia, e por isso entra como um par novo, no fim. O `print` mostra o dicionário inteiro, entre chavetas. O `len` de um dicionário conta os pares, que agora são 5.

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
  File "C:\Users\aluno\fp-python\copias_erro.py", line 4, in <module>
    print(titulo, "tem", copias[titulo], "cópias")
                         ~~~~~~^^^^^^^^
KeyError: 'Portal 2'
```

Leitura guiada: lê-se de baixo para cima. `KeyError` quer dizer "erro de chave", e a seguir vem a chave que não existe, `'Portal 2'`. Os sinais `~` e `^` apontam para `copias[titulo]`. É o `IndexError` dos dicionários: em vez de um índice fora dos limites, uma chave que não está lá.

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

Repara na forma. Quando um dicionário não cabe numa linha, escreve-se um par por linha, indentado. A chaveta que fecha fica sozinha na última linha.

## Percorrer um dicionário

Muitas vezes é preciso passar por todos os pares de um dicionário: para os mostrar, para os somar ou para escolher alguns. Há três maneiras, conforme o que interessa em cada volta.

Um `for` sobre um dicionário dá as chaves, uma por volta, pela ordem em que os pares entraram. Para ter as chaves e os valores, usa-se o método `items`, que quer dizer "itens". Em cada volta, ele dá um tuplo com a chave e o valor, que se desempacota nas duas variáveis do `for`. Para ter só os valores, usa-se o método `values`, que quer dizer "valores".

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

A última linha da tabela serve para percorrer as chaves por ordem. Num dicionário, o `sorted` devolve uma lista com as chaves, ordenadas: `sorted(copias)` dá `['Celeste', 'Minecraft', 'Rocket League', 'Tetris']`.

O dicionário guarda os pares pela ordem em que entraram, e é por essa ordem que o `for` os percorre. Mas num dicionário procura-se pela chave, e não pela posição: `copias[0]` não é o primeiro par. É a chave `0`, que não existe, e dá `KeyError: 0`.

## Contar com um dicionário

O clube quer saber quantos jogos tem de cada género. Sem um dicionário, precisavas de um contador por género, e de saber à partida que géneros há. Com um dicionário, cada género é uma chave, e o valor é o seu contador. Os contadores vão nascendo à medida que os géneros aparecem.

O padrão é este. Para cada valor da coleção que se conta, há dois casos:

- se o valor já é uma chave do dicionário, soma-se 1 ao seu contador;
- se ainda não é, é a primeira vez que aparece, e entra no dicionário com o contador a 1.

O dicionário começa vazio. O `{}`, as chavetas sem nada lá dentro, é um dicionário vazio, sem pares. Antes de correres este exemplo, tenta prever quantas chaves fica o dicionário a ter, e o valor de cada uma.

```python
# contar_generos.py: conta quantos jogos do catálogo há de cada género.
generos_dos_jogos = ["plataformas", "plataformas", "corridas", "desporto",
                     "desporto", "puzzle", "aventura"]

jogos_por_genero = {}
for genero in generos_dos_jogos:
    if genero in jogos_por_genero:
        jogos_por_genero[genero] = jogos_por_genero[genero] + 1
    else:
        # Primeira vez que o género aparece: ainda não há chave para somar.
        jogos_por_genero[genero] = 1
for genero, quantos in jogos_por_genero.items():
    print(f"{genero}: {quantos}")
```

O resultado é este:

```text
plataformas: 2
corridas: 1
desporto: 2
puzzle: 1
aventura: 1
```

Como é a primeira vez que este padrão aparece, segue-o volta a volta.

| Volta | `genero` | Já é chave? | `jogos_por_genero` depois da volta |
| ---: | --- | --- | --- |
| 1 | plataformas | não | `{'plataformas': 1}` |
| 2 | plataformas | sim | `{'plataformas': 2}` |
| 3 | corridas | não | `{'plataformas': 2, 'corridas': 1}` |
| 4 | desporto | não | `{'plataformas': 2, 'corridas': 1, 'desporto': 1}` |
| 5 | desporto | sim | `{'plataformas': 2, 'corridas': 1, 'desporto': 2}` |
| 6 | puzzle | não | mais `'puzzle': 1` |
| 7 | aventura | não | mais `'aventura': 1` |

Leitura guiada: o dicionário nasce vazio, antes do ciclo, como um contador nasce a 0. Em cada volta, o `if` pergunta se o género já tem contador. Na volta 1, ainda não tem, e o `else` cria-o com 1. Na volta 2, já tem, e o `if` soma-lhe 1. No fim, o segundo `for` mostra cada par.

O erro típico é tirar o `if` e deixar só a soma. Na primeira volta, `jogos_por_genero["plataformas"] + 1` lê uma chave que ainda não existe, e o programa para com `KeyError: 'plataformas'`.

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

Para acrescentar um valor a um conjunto, usa-se o método `add`, que quer dizer "acrescentar". Se o valor já lá estiver, nada muda. Um conjunto é mutável: o `add` muda o próprio conjunto. Antes de leres a resposta, tenta prever o tamanho do conjunto no fim.

```text
>>> generos = {"puzzle", "aventura"}
>>> generos.add("corridas")
>>> generos.add("puzzle")
>>> len(generos)
3
```

### Um conjunto não tem ordem

Um conjunto não guarda a ordem dos valores. Se escreveres `print(socios)`, aparece algo como `{'Rui', 'Ana', 'Bia'}`, e a ordem pode mudar de uma vez que corres o programa para a seguinte. É por isso que o exemplo acima usa o `sorted` antes de mostrar: dá uma lista, com uma ordem que não muda.

Também por isso, um conjunto não tem índices. Com `socios[0]`, o programa para com uma mensagem que acaba assim:

```text
TypeError: 'set' object is not subscriptable
```

Quer dizer "erro de tipo: um objeto `set` não aceita índices". Num conjunto, não há primeiro nem último. Só se pergunta se um valor lá está, com o `in`, ou se percorrem os valores com o `for`.

### O conjunto vazio

O conjunto vazio escreve-se `set()`, e não `{}`. As chavetas vazias são um dicionário vazio, porque os dicionários vieram primeiro na linguagem. Na consola, `type({})` dá `<class 'dict'>`, e `type(set())` dá `<class 'set'>`.

O erro típico é escrever `generos = {}` para começar um conjunto. Na primeira vez que se faz `generos.add("puzzle")`, o programa para com esta mensagem:

```text
AttributeError: 'dict' object has no attribute 'add'
```

Quer dizer "erro de atributo: um objeto `dict` não tem `add`". Um atributo é o que se escreve depois do ponto, como um método. Os dicionários não têm o método `add`, porque um dicionário guarda pares, e não valores soltos. Corrige-se começando com `generos = set()`.

### Porque é que um conjunto não substitui sempre uma lista

Se o conjunto tira os repetidos, porque não usar sempre conjuntos? Porque, ao tirar os repetidos e a ordem, perde informação. Com a lista das presenças, sabes que o Rui veio três vezes e quem chegou primeiro. Com o conjunto, só sabes que o Rui veio.

Por isso, a pergunta decide. Se queres saber quem veio, serve o conjunto. Se queres saber quantas vezes veio cada um, ou por que ordem, precisas da lista, ou de um dicionário de contagens feito a partir dela.

## A coleção vazia

Cada coleção tem a sua forma vazia. São o texto vazio, `""`, a lista vazia, `[]`, e o tuplo vazio, `()`. Há também o dicionário vazio, `{}`, e o conjunto vazio, `set()`. Todas têm `len` igual a 0. Uma coleção vazia não é um erro: é um caso que os programas encontram muitas vezes. Um sócio que ainda não escolheu jogos, ou uma semana em que ninguém veio ao clube.

Com uma coleção vazia, umas operações funcionam e outras param o programa:

| Operação | Com a coleção vazia |
| --- | --- |
| `for x in colecao:` | dá zero voltas, e o corpo não se executa |
| `len(colecao)` | dá 0 |
| `sum(lista)` | dá 0 |
| `max(lista)` e `min(lista)` | param o programa com `ValueError` |
| `sum(lista) / len(lista)` | para o programa com `ZeroDivisionError` |
| `lista[0]` | para o programa com `IndexError` |
| `x in colecao` | dá `False` |

Por isso, a coleção vazia é sempre um dos casos de teste, como o caso de zero voltas de um ciclo. Pergunta-se se tem elementos antes do que não funciona sem eles:

```python
if len(quero_jogar) == 0:
    print("Ainda não escolheste nenhum jogo.")
else:
    print("O primeiro jogo da tua lista é", quero_jogar[0])
```

A condição `len(quero_jogar) == 0` lê-se como se diz: "a lista tem zero elementos".

## Escolher a representação

Antes de escrever o código, escolhe-se a forma de guardar os dados. A forma escolhida chama-se **representação**. Um mesmo problema pode guardar-se de várias formas, e uma boa escolha torna o código mais curto e mais claro. Viste-o nas cópias dos jogos: com duas listas era preciso um ciclo, e com um dicionário bastava uma linha.

A escolha começa antes das coleções. Um jogo verdadeiro tem capa, preço, estúdio, idade mínima, número de jogadores e muito mais. O catálogo do clube guarda só o código, o título, o género e o ano. São os dados de que as perguntas do clube precisam. Guardar só o que o problema precisa, na forma que lhe serve, chama-se **abstração**. Abstrair é decidir o que deixar de fora, e não só o que guardar. Vais voltar a esta ideia no tema 03, com as funções.

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

Uma escolha justifica-se com as quatro perguntas. "Escolhi um dicionário porque é mais fácil" não justifica nada. "Escolhi um dicionário porque o clube procura cada jogo pelo código, e não pela posição" justifica.

## Exemplo guiado: o resumo das sessões do clube

### Passo 1: o problema

> De cada vez que alguém joga no clube, a pessoa que está de serviço regista o código do jogo, por ordem. O clube quer um programa que, no fim da semana, mostre quantas sessões se registaram e quantas sessões teve cada jogo, pelo título. Quer saber também quantos jogos diferentes se jogaram e qual foi o mais jogado. Por fim, quer saber que códigos foram registados por engano, porque não existem no catálogo, cada um uma vez.

A lista das sessões desta semana é esta:

```python
sessoes = ["AVE-01", "DES-01", "PUZ-09", "AVE-01", "PLA-02", "DES-01", "AVE-01", "PUZ-09"]
```

O catálogo é o do início deste guia, num dicionário com o código como chave.

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
| O mais jogado | Minecraft |

### Passo 4: o script completo

```python
# sessoes.py: o resumo das sessões de jogo do clube de videojogos.
# Conta as sessões e as sessões de cada jogo, diz qual foi o mais jogado
# e avisa dos códigos registados que não estão no catálogo.

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
    mais_jogado = ""
    maior = 0
    for codigo, quantas in sessoes_por_jogo.items():
        if quantas > maior:
            maior = quantas
            mais_jogado = codigo
    titulo = catalogo[mais_jogado][0]
    print(f"O mais jogado: {titulo}")
```

Antes de correres, confere com a tabela do passo 3 o que esperas ver. O resultado é este:

```text
Sessões registadas: 8
Código desconhecido: PUZ-09
Jogos diferentes: 3
Minecraft: 3
Rocket League: 2
Celeste: 1
O mais jogado: Minecraft
```

Leitura guiada: lê-se em quatro partes. A primeira são os dados: o catálogo e a lista das sessões. A segunda é o ciclo que percorre as sessões. Cada código cai num de três casos. Se não está no catálogo, vai para o conjunto dos desconhecidos. Se já tem contador, soma 1. Se é a primeira sessão desse jogo, o contador nasce a 1. A terceira parte mostra os resultados. O `sorted` dá uma ordem fixa ao conjunto, e o `catalogo[codigo][0]` vai buscar o título ao tuplo do jogo. A quarta parte procura o mais jogado, só quando há pelo menos um jogo.

A procura do mais jogado é nova, e segue-se volta a volta. A ideia é a de quem procura a pessoa mais alta de uma fila. Olha para cada pessoa, compara-a com a mais alta que já viu e, se esta for mais alta, passa a lembrar-se desta. No programa, `maior` guarda o maior número de sessões visto até agora, e `mais_jogado` guarda o código desse jogo. Começam em 0 e no texto vazio. Qualquer jogo do dicionário tem pelo menos uma sessão, e por isso o primeiro ganha sempre ao 0.

| Volta | `codigo` | `quantas` | `quantas > maior` | `maior` depois | `mais_jogado` depois |
| ---: | --- | ---: | --- | ---: | --- |
| antes do ciclo | | | | 0 | `""` |
| 1 | `AVE-01` | 3 | `3 > 0` dá `True` | 3 | `AVE-01` |
| 2 | `DES-01` | 2 | `2 > 3` dá `False` | 3 | `AVE-01` |
| 3 | `PLA-02` | 1 | `1 > 3` dá `False` | 3 | `AVE-01` |

No fim, `mais_jogado` é `AVE-01`, e o título que se mostra é o do Minecraft.

### Passo 5: testar com os casos que enganam

Um programa com coleções testa-se sempre com valores repetidos, com a coleção vazia e com uma chave que não existe. Para cada caso, muda-se a linha `sessoes = [...]` e corre-se outra vez. Antes de correres cada um, escreve o que esperas.

| `sessoes` | O que testa | O que o Python mostra |
| --- | --- | --- |
| a lista do problema | repetidos e um código desconhecido repetido | as sete linhas do passo 4 |
| `[]` | a coleção vazia | `Sessões registadas: 0`, `Jogos diferentes: 0` e `Ainda não há sessões de jogos do catálogo.` |
| `["XYZ-01"]` | só uma chave que não existe | `Sessões registadas: 1`, `Código desconhecido: XYZ-01`, `Jogos diferentes: 0` e a mensagem de não haver sessões |
| `["AVE-01", "AVE-01"]` | um só jogo, repetido | `Jogos diferentes: 1`, `Minecraft: 2` e `O mais jogado: Minecraft` |
| `["PLA-02", "AVE-01"]` | um empate | `Celeste: 1`, `Minecraft: 1` e `O mais jogado: Celeste` |

O último caso mostra uma decisão que o enunciado não tomou: num empate, qual é o mais jogado? Com o `>` na comparação, fica o primeiro a chegar ao máximo, o Celeste. Com `>=`, ficava o último. O programa escolheu uma regra, e a regra fica escrita, para quem o usar saber.

Sem o `if len(sessoes_por_jogo) == 0`, o caso da lista vazia parava com `KeyError: ''`, na linha que vai buscar o título do mais jogado. A variável `mais_jogado` ficava com o texto vazio, e o catálogo não tem essa chave. Sem o `if codigo not in catalogo`, o `PUZ-09` passava a ser um jogo, e o programa parava com `KeyError: 'PUZ-09'` ao ir buscar o título.

### Passo 6: porque não bastava um conjunto

Um conjunto feito a partir das sessões, `set(sessoes)`, dava os códigos que apareceram: quatro, contando com o `PUZ-09`. Responde a "que jogos se jogaram?", e a mais nada. Ao tirar os repetidos, deita fora o número de sessões de cada jogo, e sem ele não há mais jogado. A lista das sessões guarda tudo, e o dicionário resume-a sem perder as contagens. O conjunto entrou onde a pergunta era mesmo "cada um uma vez": os códigos desconhecidos.

## Erros frequentes

Os erros desta secção não ficaram nas secções anteriores. Para cada um, ficas a saber o que aparece, porque acontece e como se corrige. Os outros estão na secção da ideia que explicam:

- o índice fora do texto, em "Um texto é uma sequência de caracteres";
- o fim da fatia que não entra, em "Fatias de um texto";
- as maiúsculas no `in`, em "Perguntar se um texto contém outro, com `in`";
- mudar um carácter de um texto, em "Um texto não se altera";
- o `f` esquecido, em "Juntar textos e valores com f-strings";
- o `remove` de um valor que não está na lista, em "Listas que crescem e encolhem";
- o `max` de uma lista vazia, em "Funções predefinidas para listas";
- mudar um tuplo e desempacotar com as variáveis erradas, em "Tuplos: valores que andam juntos";
- a chave que não existe, em "Dicionários: procurar por chave";
- o contador sem o `if`, em "Contar com um dicionário";
- o índice num conjunto e o `{}` como conjunto vazio, em "Conjuntos: valores sem repetidos".

### Guardar o resultado do `append`

O que se vê, com `quero_jogar = quero_jogar.append("COR-01")`: a lista desaparece, e `print(quero_jogar)` mostra `None`. No `append` seguinte, o programa para com esta mensagem:

```text
AttributeError: 'NoneType' object has no attribute 'append'
```

Quer dizer "erro de atributo: um objeto `NoneType` não tem `append`". Acontece a quem aplica a regra dos textos às listas. O `upper` de um texto devolve um texto novo, e por isso guarda-se o resultado. O `append` de uma lista muda a própria lista e não devolve nada, isto é, devolve `None`. Guardar esse `None` na variável deita a lista fora. Corrige-se escrevendo só `quero_jogar.append("COR-01")`, sem atribuição.

### O código escrito noutra forma

O que se vê: o código `"PLA-02"` existe no catálogo, mas a pessoa escreve `pla-02`, ou `PLA-02 ` com um espaço no fim. O `in` dá `False`, e o programa diz que não há esse jogo. Sem o `in`, para com `KeyError: 'pla-02'`.

Acontece porque, para o Python, dois textos só são iguais se tiverem exatamente os mesmos caracteres. As maiúsculas e os espaços contam. Corrige-se arrumando o que vem do teclado antes de procurar, para ficar na forma das chaves. Para os códigos do clube, que estão em maiúsculas, é `input(...).strip().upper()`.

### Um número guardado como texto

O que se vê, com `anos = ["2023", "2018", "984"]`: o `max(anos)` dá `'984'`, e o `sorted(anos)` dá `['2018', '2023', '984']`. Não há mensagem de erro, mas o resultado está errado.

Acontece quando os números ficam guardados como textos, por exemplo lidos com `input` e não convertidos. Os textos comparam-se carácter a carácter, como num dicionário de português. O `"9"` vem depois do `"2"`, e por isso `"984"` fica no fim, mesmo sendo o número mais pequeno. Corrige-se convertendo cada valor com `int` antes de o guardar na lista: `anos.append(int(texto))`.

## Palavras novas deste guia

- Coleção: um valor que guarda outros valores, como um texto, uma lista, um tuplo, um dicionário ou um conjunto.
- Carácter: uma letra, um algarismo, um sinal ou um espaço; um texto é uma sequência de caracteres.
- Índice: a posição de um carácter num texto, ou de um elemento numa lista ou num tuplo, a contar do 0.
- Índice negativo: um índice que conta a partir do fim; `-1` é o último.
- Fatia: um pedaço de um texto tirado por posições, como `codigo[0:3]`; o segundo índice não entra.
- `in`: numa condição, pergunta se um valor está dentro de uma coleção; num dicionário, pergunta pelas chaves.
- Método: uma função que pertence a um valor e se chama com um ponto, como `titulo.upper()`.
- `upper` e `lower`: os métodos que devolvem um texto em maiúsculas ou em minúsculas.
- `strip`: o método que devolve um texto sem os espaços do início e do fim.
- `split`: o método que parte um texto numa lista, nos espaços ou no sinal que se indica.
- Imutável: que não se pode alterar depois de criado, como um texto ou um tuplo.
- Mutável: que se pode alterar depois de criado, como uma lista, um dicionário ou um conjunto.
- f-string: um texto com um `f` antes das aspas, em que cada par de chavetas recebe um valor.
- Lista vazia: a lista sem elementos, `[]`.
- `append`: o método que acrescenta um elemento no fim de uma lista.
- `remove`: o método que tira de uma lista a primeira vez que um valor aparece.
- `sum`: a função que soma os elementos de uma lista.
- `sorted`: a função que devolve uma lista nova, com os elementos ordenados.
- Tuplo: um grupo fixo de valores entre parênteses curvos, que não se altera.
- Desempacotar: dar a cada valor de uma coleção uma variável própria, numa só linha, como `titulo, genero, ano = jogo`.
- Dicionário: uma coleção de pares chave e valor, em que se procura o valor pela chave.
- Chave: num dicionário, o que se procura; cada chave aparece uma só vez.
- Valor: num dicionário, o que se encontra com a chave.
- `KeyError`: o erro de procurar num dicionário uma chave que não existe.
- `items` e `values`: os métodos que dão, para percorrer, os pares de um dicionário ou só os seus valores.
- Conjunto: uma coleção sem repetidos e sem ordem.
- `set`: a função que cria um conjunto; `set()` é o conjunto vazio.
- `add`: o método que acrescenta um valor a um conjunto.
- Coleção vazia: uma coleção sem nenhum elemento, com `len` igual a 0.
- Representação: a forma escolhida para guardar os dados de um problema.
- Abstração: guardar só o que o problema precisa, na forma que lhe serve.

## Verificar o que aprendeste

Usa estas perguntas para te testares. Responde a cada uma sem olhar para o guia. Se não conseguires, volta à secção que explica a ideia.

1. Com `nome = "Rocket League"`, quanto vale `len(nome)`? E `nome[0]`, `nome[-1]` e `nome[7:]`?
2. Que fatia de `"DES-02"` dá `"DES"`? E qual dá `"02"`? Porque é que `"DES-02"[0:2]` não serve?
3. O que dá `"tetris" in "Tetris"`? Como escreves a condição para dar `True`, sem mudar os textos originais?
4. Depois de `titulo = "Minecraft"` e `titulo.upper()`, quanto vale `titulo`? Porquê?
5. O que escreve `print(f"{titulo} tem {len(titulo)} letras")`, com `titulo = "Celeste"`? E sem o `f`?
6. Começas com `lista = []` e fazes `lista.append(4)`, `lista.append(9)`, `lista.append(4)` e `lista.remove(4)`. Como fica a lista?
7. O que dá `sorted([12, 3, 7])`? E como fica a lista depois?
8. Porque é que o título, o género e o ano de um jogo se guardam num tuplo? E porque é que os anos de todos os jogos ficam numa lista?
9. Com `copias = {"Tetris": 1, "Celeste": 3}`, o que faz `copias["Tetris"] = 2`? E `copias["Portal 2"] = 1`? E o que dá `copias["Minecraft"]`?
10. Num dicionário, o que dá a variável do `for` em cada volta, sem `items`? E com `items`?
11. Quantos elementos tem `set([5, 1, 5, 5, 2])`? Porque é que `{}` não é um conjunto vazio?
12. Dá uma situação em que um conjunto não pode substituir uma lista, e diz porquê.
13. Que operações param o programa com uma lista vazia? Como se evita?
14. Que coleção escolhias para guardar o número de golos de cada jogador de uma equipa, para o procurar pelo nome? Justifica com as quatro perguntas.

## O que vem a seguir

Para praticar este tema, faz o [laboratório](02-colecoes-strings-e-representacao-laboratorio.md). Nele constróis o programa do catálogo do clube: arrumas os códigos, procuras um jogo numa lista e num dicionário, e mostras os géneros sem repetidos. Depois faz a [ficha de exercícios](02-colecoes-strings-e-representacao-exercicios.md). Tem exercícios com cada coleção, um script com erros para encontrar e uma escolha de coleções para justificar.

O tema seguinte é Funções, mutabilidade e transformações legíveis. Vais escrever funções que recebem coleções e devolvem resultados, e ver quando uma função muda a coleção que recebeu. Vais também voltar à abstração, agora com as funções.

![Rodapé](../imagens/rodape.png)
