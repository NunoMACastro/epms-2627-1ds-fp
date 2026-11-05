![Cabeçalho](../imagens/cabecalho.png)

# Textos e listas que mudam

Módulo Criar aplicações em linguagem de programação Python. Neste guia aprendes a trabalhar com um texto por dentro. Vais ler cada carácter, tirar um pedaço, procurar uma palavra e arrumar o que alguém escreveu no teclado. Aprendes também a escrever mensagens exatas com f-strings, e a usar listas que ganham e perdem elementos enquanto o programa corre. Para praticar, há o [laboratório](laboratorios/07-textos-e-listas-que-mudam-laboratorio.md) e a [ficha de exercícios](exercicios/07-textos-e-listas-que-mudam-exercicios.md) deste tema.

Até aqui, os textos serviam para mostrar mensagens e para guardar o que o `input` devolvia. As listas vinham escritas no programa, com os valores todos, e só mudavam um elemento pelo índice. Neste tema, olhas para dentro de um texto, carácter a carácter. E as listas passam a crescer e a encolher: começam vazias e recebem os valores à medida que eles chegam. Este tema ainda não junta os vários dados de uma coisa num só valor, nem procura valores por um nome. Isso fica para o tema seguinte.

Lê-se ao teu ritmo, em várias vezes, com o computador ao lado. Cada exemplo pode ser copiado para um ficheiro, ou escrito na consola do Python, e corrido.

## Neste guia

1. O que vais aprender
2. O que já sabes e vais usar
3. O catálogo do clube de videojogos
4. Um texto é uma sequência de caracteres
5. Fatias de um texto
6. Um texto não se altera
7. Perguntar se um texto contém outro, com `in`
8. Os métodos dos textos
9. Juntar textos e valores com f-strings
10. Listas que crescem e encolhem
11. Os textos não mudam, as listas mudam
12. Funções predefinidas para listas
13. Exemplo guiado: a lista de jogos para experimentar
14. Erros frequentes
15. Palavras novas deste guia
16. Verificar o que aprendeste
17. O que vem a seguir

## O que vais aprender

No fim deste guia, consegues:

- ler um carácter de um texto pela posição, contar posições a partir do fim e percorrer o texto com `for`;
- tirar uma fatia de um texto e prever que caracteres ficam nela;
- perguntar se um texto contém outro, sem ligar às maiúsculas;
- arrumar um texto com os métodos `strip`, `upper`, `lower` e `replace`, partir um texto com `split` e confirmar com `isdigit` que ele tem só algarismos;
- explicar porque é que um texto não se altera, e construir um texto novo quando precisas de outro;
- escrever mensagens que juntam textos e valores com f-strings;
- acrescentar, inserir e tirar elementos de uma lista, com `append`, `insert`, `remove` e `pop`;
- usar `sum`, `max`, `min` e `sorted` numa lista, e proteger o programa de uma lista vazia.

## O que já sabes e vais usar

- Correr um script no terminal e usar a consola do Python, com o `>>>`: guia [01 Do pseudocódigo ao Python](01-do-pseudocodigo-ao-python.md).
- O `print` com vários valores separados por vírgulas, e o `print()` vazio: guia [01 Do pseudocódigo ao Python](01-do-pseudocodigo-ao-python.md).
- Os três tipos de erro, o traceback lido de baixo para cima e a rotina de cinco passos: guia [01 Do pseudocódigo ao Python](01-do-pseudocodigo-ao-python.md).
- As variáveis, as constantes em maiúsculas e os tipos `int`, `float`, `str` e `bool`: guia [02 Dados e interação](02-dados-e-interacao.md).
- As funções predefinidas, como o `max`, o `min`, o `round` e o `type`: guia [02 Dados e interação](02-dados-e-interacao.md).
- O `input`, que devolve sempre um texto, a conversão com `int` e `str`, e o `+` que junta dois textos: guia [02 Dados e interação](02-dados-e-interacao.md).
- As mensagens de erro `NameError`, `TypeError`, `ValueError` e `ZeroDivisionError`: guia [02 Dados e interação](02-dados-e-interacao.md).
- O `if`, o `elif` e o `else`, as comparações, e o `and`, o `or` e o `not`: guia [03 Seleção](03-selecao.md).
- O `while`, a validação repetida, a sentinela, o contador e o acumulador: guia [04 Ciclos while e for](04-ciclos-while-e-for.md).
- O `for` com o `range`, e o fim do `range` que não entra: guia [04 Ciclos while e for](04-ciclos-while-e-for.md).
- As listas, o índice a partir de 0 e o `len`: guia [05 Listas](05-listas.md).
- O `for` sobre a lista e com o índice, e mudar um elemento pelo índice: guia [05 Listas](05-listas.md).
- A pesquisa com uma bandeira, o `break` e a lista vazia, `[]`: guia [05 Listas](05-listas.md).
- O `IndexError`, o erro de um índice fora da lista: guia [05 Listas](05-listas.md).
- As funções com `def` e `return`, a documentação da função e o `None` que uma função sem `return` devolve: guia [06 Funções](06-funcoes.md).
- A tabela de iterações, para seguir um ciclo volta a volta: guia [04 Repetição e arrays](../01-algoritmos/04-repeticao-e-arrays.md), secção "A tabela de iterações".
- Os casos de teste, com o resultado esperado calculado à mão antes de correr: guia [03 Decisões e validação](../01-algoritmos/03-decisoes-e-validacao.md), secção "Fronteiras e casos de teste".

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

Repara que quase tudo nesta tabela são textos. O código é um texto, o título é um texto e o género também. Só o ano é um número. Para o clube, os textos não servem só para mostrar. O programa tem de tirar o género de dentro de um código e encontrar um título a partir de uma parte dele. Tem também de perceber que `pla-01` e `PLA-01` são o mesmo código. É isso que a primeira metade deste guia ensina.

Na segunda metade, aparecem as listas que mudam de tamanho. Um sócio do clube escolhe os jogos que quer experimentar, e ninguém sabe à partida se vão ser dois ou dez. A lista começa vazia e vai crescendo.

Os programas guardam muitas vezes grupos de valores: os jogos de um catálogo, os caracteres de um código, os sócios inscritos num torneio. Um valor que guarda outros valores chama-se **coleção**. A lista do tema 05 é uma coleção. Neste guia vais ver que um texto também é uma coleção, de caracteres. No tema seguinte, vais conhecer mais três.

Neste tema, cada dado do catálogo fica numa lista própria: uma lista de títulos, uma lista de anos. Juntar os quatro dados de cada jogo é o problema do tema seguinte.

## Um texto é uma sequência de caracteres

Um texto, o tipo `str`, guarda uma sequência de caracteres, por ordem. Um **carácter** é uma letra, um algarismo, um sinal ou um espaço. O código `"PLA-01"` tem seis caracteres: `P`, `L`, `A`, `-`, `0` e `1`. O título `"Rocket League"` tem treze, porque o espaço também conta.

Cada carácter tem uma posição, o **índice**, que começa em 0, como nas listas. Lê-se um carácter com o índice entre parênteses retos, como se lia um elemento de uma lista. O `len`, que já usaste com as listas, diz quantos caracteres tem o texto.

| Carácter | `P` | `L` | `A` | `-` | `0` | `1` |
| --- | --- | --- | --- | --- | --- | --- |
| Índice | 0 | 1 | 2 | 3 | 4 | 5 |

Antes de leres as respostas, olha para a tabela e tenta prever o que a consola mostra em cada linha.

```text
>>> codigo = "PLA-01"
>>> codigo[0]
'P'
>>> codigo[3]
'-'
>>> len(codigo)
6
>>> codigo[5]
'1'
```

Leitura guiada: `codigo[0]` é o primeiro carácter, e `codigo[3]` é o hífen, o quarto. A consola mostra os textos entre plicas, as aspas simples, para se ver que são textos. O `len` conta os seis caracteres. O último índice válido é 5, um a menos do que o `len`, exatamente como numa lista. Um carácter tirado de um texto é também um texto, só com um carácter.

### Contar a partir do fim

Às vezes interessa o fim de um texto, e não o princípio. O último algarismo de um código, por exemplo. Com o que já sabes, escrevias `codigo[len(codigo) - 1]`. Funciona, mas é comprido.

O Python aceita índices negativos. Um **índice negativo** conta a partir do fim: `-1` é o último carácter, `-2` o penúltimo, e assim por diante. Cada carácter tem assim duas posições, uma a contar do início e outra a contar do fim:

| Carácter | `P` | `L` | `A` | `-` | `0` | `1` |
| --- | --- | --- | --- | --- | --- | --- |
| Índice | 0 | 1 | 2 | 3 | 4 | 5 |
| Índice negativo | -6 | -5 | -4 | -3 | -2 | -1 |

Antes de leres as respostas, tenta prever as três linhas.

```text
>>> codigo[-1]
'1'
>>> codigo[-2]
'0'
>>> codigo[-6]
'P'
```

Leitura guiada: `codigo[-1]` é o último carácter, o mesmo que `codigo[5]`. O `-6` volta ao primeiro, porque o código tem seis caracteres. Os índices negativos dão jeito quando não sabes o tamanho do texto. O `-1` é sempre o último, seja o texto curto ou comprido. Também funcionam com as listas: numa lista, `lista[-1]` é o último elemento.

O erro típico é usar um índice que não existe. Com `codigo[6]`, ou com `codigo[-7]`, a consola responde com uma mensagem de erro que acaba nesta linha:

```text
IndexError: string index out of range
```

Quer dizer "erro de índice: índice do texto fora dos limites". É o erro das listas do tema 05, agora num texto. Num texto de 6 caracteres, os índices válidos vão de 0 a 5, e de -1 a -6. Na consola a sério, aparece o traceback inteiro; aqui mostra-se só a última linha, a que diz o tipo de erro. As mensagens de erro deste guia são as do Python 3.14. Numa versão mais antiga, algumas têm outras palavras.

### Percorrer um texto com `for`

Um texto percorre-se com `for`, como uma lista. Em cada volta, a variável do ciclo recebe o carácter seguinte, do primeiro ao último. Antes de correres este exemplo, tenta prever quantas linhas aparecem e o que tem cada uma.

```python
# soletrar.py: escreve as letras do título de um jogo, uma por linha.
titulo = "Tetris"
for letra in titulo:
    print(letra)
```

O resultado são seis linhas:

```text
T
e
t
r
i
s
```

Como é a primeira vez que um `for` percorre um texto, segue a execução volta a volta:

| Volta | `letra` | O que escreve |
| ---: | --- | --- |
| 1 | `"T"` | `T` |
| 2 | `"e"` | `e` |
| 3 | `"t"` | `t` |
| 4 | `"r"` | `r` |
| 5 | `"i"` | `i` |
| 6 | `"s"` | `s` |

Leitura guiada: é o `for` sobre uma lista, do tema 05, com um texto no lugar da lista. O ciclo dá tantas voltas quantos os caracteres do texto, seis. Em cada volta, `letra` é um texto de um carácter. O `print` escreve-o e muda de linha.

Quando precisas da posição de cada carácter, percorres o texto pelo índice, como percorrias uma lista. O `range(0, len(titulo))` dá os índices de 0 até ao último:

```python
# posicoes.py: escreve cada letra do título de um jogo com a sua posição.
titulo = "Tetris"
for i in range(0, len(titulo)):
    print(i, titulo[i])
```

Antes de correres, tenta prever a primeira e a última linha. O resultado começa em `0 T` e acaba em `5 s`, com seis linhas. A escolha é a mesma das listas: pelo valor, quando só interessa cada carácter; pelo índice, quando interessa também onde ele está.

Percorrer um texto carácter a carácter serve para contar. Este script conta os espaços de um título, e daí as palavras. Antes de o correres, tenta prever as duas linhas que aparecem.

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

O resultado é este:

```text
Espaços: 3
Palavras: 4
```

Leitura guiada: é o contador do tema 04, agora sobre os caracteres de um texto. O contador nasce a 0, antes do ciclo. O `for` dá à variável `caracter` cada carácter do título, um por volta: `S`, `u`, `p` e assim por diante, 24 voltas. O contador só aumenta quando o carácter é um espaço. Há um espaço entre cada duas palavras, por isso as palavras são uma a mais do que os espaços. O nome da variável é `caracter`, sem acento, porque os nomes que escrevemos no código não levam acentos.

## Fatias de um texto

Muitas vezes não queres um carácter, mas um pedaço do texto. Do código `"PLA-01"`, queres o género, `"PLA"`, ou o número, `"01"`. Com os índices, tinhas de ler três caracteres e juntá-los com o `+`. Há uma forma direta.

Um pedaço de um texto, tirado por posições, chama-se **fatia**. Escreve-se com dois índices separados por dois pontos, entre parênteses retos: `codigo[0:3]`. O primeiro índice entra na fatia, e o segundo não entra, como no `range`. Por isso, `codigo[0:3]` dá os caracteres dos índices 0, 1 e 2.

Uma forma de pensar nisto é imaginar os índices nos espaços entre os caracteres, e não em cima deles. A fatia `[0:3]` corta no espaço antes do `P` e no espaço antes do hífen, e fica com o que está no meio.

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
>>> codigo[-2:]
'01'
>>> codigo[4:20]
'01'
```

Leitura guiada: `codigo[0:3]` começa no índice 0 e para antes do 3, o hífen. `codigo[4:6]` dá os dois algarismos, porque o 6 já não entra. Quando falta o primeiro índice, como em `[:3]`, a fatia começa no início. Quando falta o segundo, como em `[4:]`, vai até ao fim. O `[-2:]` usa um índice negativo: começa no penúltimo carácter e vai até ao fim. A última linha mostra uma diferença em relação ao índice. Uma fatia que passa do fim do texto não dá erro: fica com os caracteres que existem.

| Fatia | O que dá | Com `"PLA-01"` |
| --- | --- | --- |
| `texto[a:b]` | do índice `a` até antes do `b` | `codigo[1:3]` dá `"LA"` |
| `texto[:b]` | do início até antes do `b` | `codigo[:3]` dá `"PLA"` |
| `texto[a:]` | do índice `a` até ao fim | `codigo[4:]` dá `"01"` |
| `texto[-n:]` | os últimos `n` caracteres | `codigo[-2:]` dá `"01"` |

Uma fatia é sempre um texto novo, mesmo com um só carácter, como `codigo[3:4]`, que dá `"-"`. Se os dois índices forem iguais, como em `codigo[2:2]`, a fatia fica vazia, `""`. O texto de onde a fatia saiu fica sempre igual.

Quantos caracteres tem uma fatia? A conta é simples: o segundo índice menos o primeiro. A fatia `[4:6]` tem 6 - 4, isto é, 2 caracteres. A fatia `[0:3]` tem 3. Esta conta ajuda a confirmar uma fatia antes de correr o programa.

### Uma fatia para caber numa etiqueta

As caixas dos jogos do clube têm uma etiqueta na lombada, onde só cabem 9 caracteres. Um título curto cabe inteiro. Um título comprido é cortado, e acaba em três pontos, para se perceber que falta o resto. Antes de correres este script, tenta prever a etiqueta de `Celeste`, de `Minecraft` e de `Rocket League`.

```python
# etiqueta.py: prepara o título de um jogo para a etiqueta da caixa,
# onde só cabem 9 caracteres.
LARGURA = 9

titulo = input("Título do jogo? ")
if len(titulo) <= LARGURA:
    etiqueta = titulo
else:
    # Ficam LARGURA - 3 caracteres do título; os três pontos ocupam os outros 3.
    etiqueta = titulo[:LARGURA - 3] + "..."
print("Etiqueta:", etiqueta)
```

Os três casos dão isto:

| Título escrito | `len(titulo)` | Etiqueta |
| --- | ---: | --- |
| `Celeste` | 7 | `Celeste` |
| `Minecraft` | 9 | `Minecraft` |
| `Rocket League` | 13 | `Rocket...` |

Leitura guiada: o `if` decide se o título cabe. O `Minecraft`, com 9 caracteres, é a fronteira: cabe à justa, por causa do `<=`. Quando não cabe, a fatia `titulo[:LARGURA - 3]` é `titulo[:6]`, os seis primeiros caracteres. O `+` junta-lhes os três pontos, e a etiqueta fica com 6 mais 3, os 9 caracteres. Repara que o fim da fatia é uma conta. Entre os parênteses retos pode ir qualquer expressão que dê um número inteiro.

O erro típico das fatias é contar o fim como se entrasse. Quem escreve `codigo[0:2]` para tirar o género fica com `"PL"`, sem o `A`, e o Python não dá nenhum aviso. É um erro de lógica, e só o apanha quem compara o resultado com o que esperava. Confirma com a conta: o género tem 3 caracteres, por isso a fatia tem de ter 3, e `[0:3]` tem.

## Um texto não se altera

Imagina que o clube muda o género de um jogo e o código `"PLA-01"` deve passar a começar por `D`. A ideia natural é mudar o primeiro carácter, como se muda um elemento de uma lista. Com `codigo[0] = "D"`, a consola responde com uma mensagem que acaba nesta linha:

```text
TypeError: 'str' object does not support item assignment
```

Quer dizer "erro de tipo: um objeto `str` não aceita que se dê um valor a um elemento". Para o Python, um objeto é um valor, e `'str' object` quer dizer "um valor do tipo `str`". O Python não deixa mudar um carácter de um texto. Depois de criado, um texto nunca muda.

Um valor que não se pode alterar depois de criado diz-se **imutável**. Os textos são imutáveis. Um valor que se pode alterar diz-se **mutável**. As listas são mutáveis: no tema 05, `pontuacoes[1] = 9` mudava um elemento da lista, e a lista ficava diferente.

Então, como se muda um código? Não se muda: constrói-se um texto novo, e guarda-se na variável. Antes de leres a resposta, tenta prever o que mostra a última linha.

```text
>>> codigo = "PLA-01"
>>> codigo = "D" + codigo[1:]
>>> codigo
'DLA-01'
```

Leitura guiada: o lado direito faz-se primeiro, como em qualquer atribuição. Junta o `"D"` à fatia `"LA-01"`, e o resultado é um texto novo, `"DLA-01"`. Depois, a variável `codigo` passa a guardar esse texto. O texto `"PLA-01"` não mudou: a variável é que passou a guardar outro texto.

Uma imagem ajuda. Uma variável é como uma etiqueta com um nome, colada a um valor. Com uma lista, podes mexer no valor a que a etiqueta está colada: trocar um elemento, acrescentar outro. Com um texto, não podes mexer no valor. O que podes é fazer um texto novo e descolar a etiqueta para o colar nele.

## Perguntar se um texto contém outro, com `in`

Um sócio do clube lembra-se de que o jogo tinha "Mario" no título, mas não se lembra do resto. Para saber se um texto aparece dentro de outro, o Python tem o operador `in`. A expressão `"Mario" in titulo` dá `True` se o texto `"Mario"` aparecer em algum sítio de `titulo`, e `False` se não aparecer. O `not in` faz o contrário.

Antes de leres as respostas, tenta prever as quatro linhas.

```text
>>> "Mario" in "Super Mario Bros. Wonder"
True
>>> "mario" in "Super Mario Bros. Wonder"
False
>>> "Kart" not in "Super Mario Bros. Wonder"
True
>>> "-" in "PLA-01"
True
```

Leitura guiada: a primeira dá `True`, porque o título contém "Mario". A segunda dá `False`, e é esta que surpreende. Para o Python, o `m` minúsculo e o `M` maiúsculo são caracteres diferentes. A terceira pergunta se "Kart" não está no título, e não está. A quarta procura um só carácter, o hífen, e encontra-o. Serve, por exemplo, para confirmar que um código tem o hífen.

É a palavra `in` do `for`, mas com outro papel. No `for`, o `in` diz que coleção se percorre. Numa condição, pergunta se um valor está dentro de uma coleção, e o resultado é um `bool`. Como é uma condição, pode ir num `if` ou num `while`, como qualquer comparação.

Sem o `in`, para saber se "Mario" aparece no título, terias de comparar cada fatia de cinco caracteres do título com "Mario", uma a uma. O `in` faz essa procura por ti, e devolve só a resposta.

A segunda linha levanta um problema. O sócio pode escrever "mario", e a procura falha só por causa da maiúscula. A secção seguinte resolve-o.

## Os métodos dos textos

Os textos que vêm do teclado raramente chegam arrumados. Quem escreve um código pode escrever `" pla-01 "`, com espaços e em minúsculas. Quem procura um título pode escrever "MARIO". Antes de comparar textos, é preciso arrumá-los.

Para isso, cada texto traz consigo funções próprias. Uma função que pertence a um valor chama-se **método**. Chama-se escrevendo o valor, um ponto e o nome do método, com os parênteses: `titulo.upper()`. Os parênteses são obrigatórios, mesmo quando não levam nada lá dentro.

Um método é como uma função predefinida, com uma diferença na forma de a chamar. O `len` é uma função: serve para qualquer coleção e recebe-a entre parênteses, `len(titulo)`. O `upper` é um método dos textos: só os textos o têm, e chama-se depois do texto, com o ponto. Por isso não se escreve `upper(titulo)`, que dá `NameError`, nem `titulo.len()`. Esta segunda dá `AttributeError`, um erro que quer dizer que o texto não tem nada com o nome que vem depois do ponto. Uma pergunta ajuda a escolher a forma: de quem é a ferramenta? Do Python inteiro, ou só dos textos?

Há quatro métodos dos textos que vais usar mais. O `upper()` devolve o texto em maiúsculas: `"pla-01".upper()` dá `"PLA-01"`. O `lower()` devolve o texto em minúsculas: `"Minecraft".lower()` dá `"minecraft"`. O `strip()` devolve o texto sem os espaços do início e do fim: `"  pla-01 ".strip()` dá `"pla-01"`. O `split()` devolve uma lista com as palavras do texto: `"Super Mario Bros. Wonder".split()` dá `['Super', 'Mario', 'Bros.', 'Wonder']`. No fim desta secção, uma tabela junta todos os métodos dos textos deste guia.

O `strip` só tira os espaços das pontas. Os espaços do meio, como o de `"Rocket League"`, ficam.

O `split` merece uma explicação mais longa, porque é o único destes quatro que devolve uma lista, e não um texto. Sem nada entre os parênteses, parte o texto nos espaços, e cada pedaço fica um elemento da lista. Com um texto entre os parênteses, parte o texto nesse sinal: `"PLA-01".split("-")` dá a lista `['PLA', '01']`. O sinal onde se parte desaparece. É uma ponte entre os textos e as listas: depois do `split`, tudo o que sabes das listas serve.

Antes de leres a resposta, tenta prever o que mostra a última linha.

```text
>>> titulo = "Celeste"
>>> titulo.upper()
'CELESTE'
>>> titulo
'Celeste'
```

Leitura guiada: o `upper` devolveu `'CELESTE'`, mas a variável `titulo` ficou como estava. Um método de um texto nunca muda o texto. Devolve um texto novo, que podes mostrar ou guardar. É o que viste em "Um texto não se altera": o texto nunca muda, e o `upper` cria um texto novo. Para guardares o resultado, escreves `titulo = titulo.upper()`, e a variável passa a guardar o texto novo. Sem a atribuição, o texto novo perde-se. O mesmo vale para todos os métodos dos textos deste guia: devolvem sempre um texto novo, ou outro valor, e o texto original fica igual.

### Encadear métodos

Como cada método devolve um texto, pode chamar-se outro método sobre o resultado, logo a seguir. Chama-se encadear, e é assim que se arruma o que vem do teclado. Antes de correres este exemplo, tenta prever o que aparece se a pessoa escrever `  MARIO ` com espaços, e depois `kart`.

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

Com `  MARIO `, aparece `Aparece no título.`. Com `kart`, aparece `Não aparece no título.`.

Leitura guiada: a linha do `input` lê-se da esquerda para a direita. O `input` devolve o texto escrito. O `strip` tira-lhe os espaços, e o `lower` passa o resultado a minúsculas. Com `  MARIO `, fica `"mario"`. Na condição, o título também passa a minúsculas, só para a comparação. Assim, as maiúsculas deixam de contar dos dois lados. A variável `titulo` continua com as maiúsculas originais, para se poder mostrar como deve ser.

Esta ideia, pôr as duas formas em minúsculas antes de comparar, é o que se chama procurar sem ligar às maiúsculas. Funciona também com o `upper` dos dois lados. O que não funciona é arrumar só um dos lados: `procura.lower() in titulo` falha com "mario", porque o título tem o `M` maiúsculo.

### Dois métodos para arrumar e confirmar: `replace` e `isdigit`

O `replace`, que quer dizer "substituir", recebe dois textos: o que procura e o que põe no lugar. Devolve um texto novo, com todas as vezes que o primeiro aparece trocadas pelo segundo. Serve, por exemplo, para quem escreve um código com um traço baixo, `pla_01`, em vez do hífen.

O `isdigit`, de *is digit*, "é algarismo", pergunta se o texto tem só algarismos. Devolve `True` ou `False`. Serve para confirmar um número antes de o converter com `int`. Já sabes que `int("dois mil")` para o programa com `ValueError`. Com o `isdigit`, o programa pergunta primeiro, e não para.

Antes de leres as respostas, tenta prever cada linha. Repara bem nas três últimas.

```text
>>> "pla_01".replace("_", "-")
'pla-01'
>>> "Rocket League".replace(" ", "")
'RocketLeague'
>>> "2018".isdigit()
True
>>> "20a8".isdigit()
False
>>> " 2018".isdigit()
False
>>> "-3".isdigit()
False
>>> "".isdigit()
False
```

Leitura guiada: o primeiro `replace` troca o traço baixo pelo hífen. O segundo troca o espaço por um texto vazio, `""`, e por isso tira os espaços todos, também os do meio. Nos `isdigit`, só o `"2018"` dá `True`. O `" 2018"` dá `False` por causa do espaço, que não é um algarismo: arruma-se primeiro com o `strip`. O `"-3"` dá `False`, porque o sinal menos não é um algarismo. E o texto vazio também dá `False`, porque não tem nenhum algarismo.

O `isdigit` junta-se bem à validação repetida do tema 04. Este script pede o ano de lançamento de um jogo até a pessoa escrever um número. Antes de o correres, prevê o que aparece com estas três respostas, por ordem: `dois mil`, `20l8`, com um L no lugar do 1, e `2018`.

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

O ecrã fica assim, com o que a pessoa escreveu a seguir a cada pergunta:

```text
Ano de lançamento? dois mil
Escreve só algarismos, como 2018.
Ano de lançamento? 20l8
Escreve só algarismos, como 2018.
Ano de lançamento? 2018
O jogo saiu há 8 anos.
```

Leitura guiada: é a validação repetida, com uma leitura antes do ciclo e outra no fim do corpo. A condição `not texto.isdigit()` é verdadeira enquanto o texto tiver alguma coisa que não seja um algarismo. O `int(texto)` só se faz depois do ciclo, quando o texto já passou na validação. Por isso, com os algarismos de 0 a 9, este programa não para com `ValueError`.

A tabela junta os métodos dos textos deste guia:

| Método | O que devolve | Exemplo | Resultado |
| --- | --- | --- | --- |
| `upper()` | o texto em maiúsculas | `"Celeste".upper()` | `"CELESTE"` |
| `lower()` | o texto em minúsculas | `"Celeste".lower()` | `"celeste"` |
| `strip()` | o texto sem os espaços das pontas | `" Celeste ".strip()` | `"Celeste"` |
| `split()` | a lista das palavras | `"Forza Horizon 5".split()` | `['Forza', 'Horizon', '5']` |
| `split(s)` | a lista dos pedaços, partindo em `s` | `"Rui;Ana".split(";")` | `['Rui', 'Ana']` |
| `replace(a, b)` | o texto com cada `a` trocado por `b` | `"pla 01".replace(" ", "-")` | `"pla-01"` |
| `isdigit()` | `True` se o texto tiver só algarismos | `"01".isdigit()` | `True` |

## Juntar textos e valores com f-strings

O clube quer mostrar cada jogo assim: `Celeste (2018)`, com o ano entre parênteses e sem espaços a mais. Com o `print` e as vírgulas, isso não sai. O `print` põe um espaço entre cada dois valores. Com o `+` e o `str`, sai, mas fica comprido e fácil de errar: `titulo + " (" + str(ano) + ")"`.

Para isto, o Python tem as **f-strings**. Uma f-string é um texto com um `f` antes das aspas. Dentro dele, cada par de chavetas, `{` e `}`, marca o sítio onde entra um valor. O Python calcula o que está entre as chavetas e põe o resultado no lugar delas, já convertido em texto. O `f` vem de *formatted*, "formatado".

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

Leitura guiada: o primeiro `print` usa vírgulas, e os espaços aparecem à volta do ano. O segundo usa uma f-string, e cada par de chavetas é substituído pelo valor da variável. Os parênteses e a vírgula ficam exatamente onde os escreveste. No terceiro, as chavetas têm uma conta, `ANO_ATUAL - ano`, e o Python escreve o resultado, 8.

Entre as chavetas pode ir qualquer expressão: uma variável, uma conta, uma chamada a uma função ou a um método. Com `titulo = "Celeste"` e `media = 2013.71`, estas são todas f-strings certas:

| f-string | O que dá |
| --- | --- |
| `f"{titulo} tem {len(titulo)} letras"` | `Celeste tem 7 letras` |
| `f"Em maiúsculas: {titulo.upper()}"` | `Em maiúsculas: CELESTE` |
| `f"Média dos anos: {round(media, 1)}"` | `Média dos anos: 2013.7` |
| `f"{titulo[:3]}..."` | `Cel...` |

Com as f-strings, não precisas de converter os números com `str`, nem de cuidar dos espaços. Escreves a mensagem como a queres ver, e pões os valores nos sítios certos. O `print` com vírgulas continua certo, e usa-se quando os espaços não importam. A partir daqui, os exemplos deste guia usam as duas formas, conforme a mensagem.

Numa f-string, as chavetas estão sempre dentro de um texto com o `f` antes das aspas, e marcam só onde entra um valor. Fora de um texto, as chavetas têm outros papéis em Python, que vais conhecer no tema seguinte.

O erro típico é esquecer o `f`. Com `print("{titulo} ({ano})")`, aparece no ecrã `{titulo} ({ano})`, tal e qual. Sem o `f`, as chavetas são caracteres como os outros, e o Python não substitui nada. Não há mensagem de erro: é um erro de lógica, que se vê no ecrã.

## Listas que crescem e encolhem

No tema 05, as listas vinham escritas no programa, com os valores todos. Mas muitas vezes não se sabe quantos valores vão ser. O clube organiza um torneio de Rocket League, e os sócios inscrevem-se um a um. Podem ser três ou trinta. Alguém desiste, alguém chega atrasado e passa à frente. A lista tem de começar vazia, crescer à medida que os nomes chegam e encolher quando alguém sai.

Para isso, as listas têm métodos próprios, como os textos. Há uma diferença grande, que esta secção vai mostrando: os métodos das listas mudam a própria lista.

### Acrescentar no fim, com `append`

A lista vazia, `[]`, é a lista sem elementos, que já conheces do tema 05. Para lhe acrescentar um elemento no fim, usa-se o método `append`, que quer dizer "acrescentar". Com `inscritos.append("Rui")`, a lista ganha mais um elemento, e muda.

Este script lê nomes até a pessoa carregar em Enter sem escrever nada. O texto vazio, `""`, faz de sentinela, como o -1 do laboratório do tema 04. Antes de correres, tenta prever o que aparece com `Rui`, `Ana` e ` Bia`, com um espaço antes. No fim, a pessoa carrega em Enter sem escrever nada.

```python
# inscritos.py: junta numa lista os sócios inscritos no torneio de Rocket League do clube.
# Lê nomes até a pessoa carregar em Enter sem escrever nada.
inscritos = []
nome = input("Nome do sócio (Enter para acabar): ").strip()
while nome != "":
    inscritos.append(nome)
    nome = input("Nome do sócio (Enter para acabar): ").strip()
print(f"Inscritos: {len(inscritos)}")
print(inscritos)
```

O ecrã fica assim, com o que a pessoa escreveu a seguir a cada pergunta:

```text
Nome do sócio (Enter para acabar): Rui
Nome do sócio (Enter para acabar): Ana
Nome do sócio (Enter para acabar):  Bia
Nome do sócio (Enter para acabar): 
Inscritos: 3
['Rui', 'Ana', 'Bia']
```

Como é a primeira vez que uma lista cresce num ciclo, segue a execução volta a volta:

| Teste | `nome` | `nome != ""` | Durante a volta | `inscritos` depois da volta |
| --- | --- | --- | --- | --- |
| 1.º | `"Rui"` | `True` | acrescenta o nome e lê o seguinte | `['Rui']` |
| 2.º | `"Ana"` | `True` | acrescenta o nome e lê o seguinte | `['Rui', 'Ana']` |
| 3.º | `"Bia"` | `True` | acrescenta o nome e lê o texto vazio | `['Rui', 'Ana', 'Bia']` |
| 4.º | `""` | `False` | o ciclo termina | `['Rui', 'Ana', 'Bia']` |

Leitura guiada: a lista nasce vazia, antes do ciclo, como um contador nasce a 0. É o ciclo da sentinela do tema 04: uma leitura antes do ciclo e outra no fim do corpo. Em cada volta, o `append` acrescenta o nome lido ao fim da lista. A Bia entra sem o espaço, por causa do `strip`. O último `print` mostra a lista inteira, com os parênteses retos e cada texto entre plicas. Se a pessoa carregar logo em Enter, o ciclo dá zero voltas, e aparecem `Inscritos: 0` e `[]`.

Repara na diferença para o tema 05. Lá, o tamanho da lista estava escrito no programa. Aqui, só se sabe no fim, com o `len`. Por isso, com listas que crescem, o `len` passa a ser muito usado. É ele que diz quantos elementos a lista tem naquele momento.

### Perguntar se um valor está na lista

O `in` da secção dos textos também funciona com listas. A expressão `"Ana" in inscritos` dá `True` se a Ana for um dos elementos da lista. Antes de leres as respostas, tenta prever as três linhas.

```text
>>> inscritos = ["Rui", "Ana", "Bia"]
>>> "Ana" in inscritos
True
>>> "ana" in inscritos
False
>>> "Eva" not in inscritos
True
```

Leitura guiada: o `in` compara o valor com cada elemento da lista, e dá `True` se algum for igual. A segunda linha dá `False` pela mesma razão dos textos: `"ana"` e `"Ana"` são textos diferentes. A terceira confirma que a Eva não está inscrita.

No tema 05, para saber se um valor estava numa lista, escrevias um ciclo com uma bandeira, e um `break` quando o encontravas. O `in` faz essa procura numa linha. O ciclo com a bandeira continua a servir quando precisas de mais do que um sim ou um não, como a posição do valor.

Há uma diferença entre o `in` dos textos e o das listas. Num texto, procura um pedaço: `"Mar" in "Mario"` dá `True`. Numa lista, procura um elemento inteiro: `"Mar" in ["Mario", "Celeste"]` dá `False`, porque nenhum elemento é exatamente `"Mar"`.

### Tirar um valor, com `remove`

Para tirar um elemento, há o método `remove`, que quer dizer "remover". Recebe o valor, e não o índice, e tira a primeira vez que esse valor aparece. Se a Ana desistir, `inscritos.remove("Ana")` deixa `['Rui', 'Bia']`. Os elementos que estavam depois dela passam uma posição para a frente: a Bia, que estava no índice 2, passa para o índice 1.

E se o valor não estiver na lista? Com `inscritos.remove("Eva")`, o programa para com uma mensagem que acaba assim:

```text
ValueError: list.remove(x): x not in list
```

Quer dizer "erro de valor: o `x` não está na lista". Antes de remover, pergunta-se se o valor lá está, com o `in`:

```python
nome = input("Quem desiste? ").strip()
if nome in inscritos:
    inscritos.remove(nome)
    print(f"{nome} saiu do torneio.")
else:
    print(f"{nome} não está na lista de inscritos.")
```

Com a Bia, aparece `Bia saiu do torneio.`. Com a Eva, aparece `Eva não está na lista de inscritos.`, e o programa continua.

### Pôr um valor numa posição, com `insert`

O `append` põe sempre no fim. Às vezes o valor tem de ir para outro sítio. O vencedor do torneio do ano passado fica em primeiro na lista, mesmo que se inscreva no fim. Para isso há o método `insert`, que quer dizer "inserir". Recebe dois valores: a posição e o valor. Com `inscritos.insert(0, "Eva")`, a Eva entra no índice 0, e todos os outros passam uma posição para trás.

### Tirar pela posição, com `pop`

O `remove` tira pelo valor. O método `pop` tira pela posição, e devolve o valor que tirou, para o programa o poder usar. A palavra vem do inglês, e lembra o som de uma coisa a saltar para fora. Sem nada entre os parênteses, `inscritos.pop()` tira o último elemento. Com uma posição, `inscritos.pop(0)` tira o primeiro.

Imagina uma fila para a consola do clube. Quem chega entra no fim, com o `append`. Quando a consola fica livre, joga o primeiro da fila, que sai dela: `a_jogar = fila.pop(0)`. O `pop` devolve o nome, que fica em `a_jogar`, e a fila perde o primeiro elemento. Uma lista serve de fila assim, com o `append` num lado e o `pop(0)` no outro.

O `pop` também falha quando não há o que tirar. Numa lista vazia, `fila.pop(0)` para o programa com `IndexError: pop from empty list`, isto é, "erro de índice: `pop` de uma lista vazia". Antes do `pop`, confirma que a lista tem elementos, com `len(fila) > 0`.

### Seguir o estado da lista

Com listas que mudam, a pergunta mais importante passa a ser esta: como fica a lista depois de cada linha? Antes de leres as respostas, segue a sequência e diz, de cabeça, como fica a lista depois de cada linha que a muda.

```text
>>> inscritos = ["Rui", "Ana", "Bia"]
>>> inscritos.remove("Ana")
>>> inscritos
['Rui', 'Bia']
>>> inscritos.insert(0, "Eva")
>>> inscritos
['Eva', 'Rui', 'Bia']
>>> inscritos.insert(1, "Tomás")
>>> inscritos
['Eva', 'Tomás', 'Rui', 'Bia']
>>> inscritos.pop()
'Bia'
>>> inscritos
['Eva', 'Tomás', 'Rui']
>>> inscritos.pop(0)
'Eva'
>>> inscritos
['Tomás', 'Rui']
```

Leitura guiada: o `remove`, o `insert` e o `pop` mudam a lista. Repara que as linhas do `remove` e do `insert` não mostram nada na consola, porque estes métodos não devolvem nada. Só o `pop` mostra um valor, o que tirou. A tabela mostra o estado da lista ao longo da sequência:

| Linha | O que faz | `inscritos` depois | O que devolve |
| --- | --- | --- | --- |
| `inscritos = ["Rui", "Ana", "Bia"]` | cria a lista | `['Rui', 'Ana', 'Bia']` | não se aplica |
| `inscritos.remove("Ana")` | tira a Ana | `['Rui', 'Bia']` | nada |
| `inscritos.insert(0, "Eva")` | põe a Eva no índice 0 | `['Eva', 'Rui', 'Bia']` | nada |
| `inscritos.insert(1, "Tomás")` | põe o Tomás no índice 1 | `['Eva', 'Tomás', 'Rui', 'Bia']` | nada |
| `inscritos.pop()` | tira o último | `['Eva', 'Tomás', 'Rui']` | `'Bia'` |
| `inscritos.pop(0)` | tira o primeiro | `['Tomás', 'Rui']` | `'Eva'` |

A tabela seguinte junta as operações que mudam uma lista, e o `in`, que só pergunta:

| Operação | O que faz à lista | O que devolve | Com `["PLA-02", "AVE-01"]` |
| --- | --- | --- | --- |
| `lista.append(x)` | acrescenta `x` no fim | nada | `append("COR-01")` dá `["PLA-02", "AVE-01", "COR-01"]` |
| `lista.insert(i, x)` | põe `x` no índice `i` e empurra os outros | nada | `insert(0, "COR-01")` dá `["COR-01", "PLA-02", "AVE-01"]` |
| `lista.remove(x)` | tira a primeira vez que `x` aparece | nada | `remove("PLA-02")` dá `["AVE-01"]` |
| `lista.pop()` | tira o último | o elemento tirado | devolve `"AVE-01"` e deixa `["PLA-02"]` |
| `lista.pop(i)` | tira o do índice `i` | o elemento tirado | `pop(0)` devolve `"PLA-02"` e deixa `["AVE-01"]` |
| `lista[i] = x` | troca o elemento do índice `i` por `x` | não se aplica | `lista[0] = "DES-01"` dá `["DES-01", "AVE-01"]` |
| `x in lista` | não muda nada | `True` ou `False` | `"AVE-01" in lista` dá `True` |

Para escolher entre o `remove` e o `pop`, pergunta-te o que sabes. Se sabes o valor que sai, como o nome de quem desiste, é o `remove`. Se sabes a posição, como o primeiro da fila, é o `pop`.

## Os textos não mudam, as listas mudam

Esta é a ideia mais importante do tema, e merece ser vista lado a lado. Antes de leres as respostas, tenta prever o que a consola mostra quando se escreve `titulo` e quando se escreve `anos`.

```text
>>> titulo = "Celeste"
>>> titulo.upper()
'CELESTE'
>>> titulo
'Celeste'
>>> anos = [2018, 1984]
>>> anos.append(2011)
>>> anos
[2018, 1984, 2011]
```

Leitura guiada: as duas sequências são parecidas, e acabam de maneiras opostas. O `upper` devolveu um texto novo, que a consola mostrou, e o `titulo` ficou igual. O `append` não mostrou nada, porque não devolve nada, e a lista `anos` mudou.

A regra que fica tem duas partes:

- Os métodos dos textos não mudam o texto, porque os textos são imutáveis. Devolvem um texto novo, que se guarda com uma atribuição: `titulo = titulo.upper()`.
- Os métodos das listas que acrescentam ou tiram, como o `append`, o `insert` e o `remove`, mudam a própria lista. Não devolvem nada, e por isso não se escreve nenhuma atribuição: só `anos.append(2011)`. O `pop` também muda a lista, e devolve o elemento que tirou.

Quando não tens a certeza, experimenta na consola, como acima: chama o método e mostra a variável a seguir. Se a variável mudou, o método muda o valor. Se não mudou, o método devolve um valor novo, e tens de o guardar.

Nenhum dos dois comportamentos é um defeito. Um texto que não muda é seguro: podes passá-lo a qualquer parte do programa, sabendo que ninguém o estraga. Uma lista que muda é prática: cresce e encolhe sem teres de criar uma lista nova a cada passo. No tema seguinte, vais conhecer uma coleção parecida com a lista que não muda, como os textos.

## Funções predefinidas para listas

No tema 02, o `max` e o `min` recebiam dois ou mais valores separados por vírgulas. Também podem receber uma lista, e devolvem o maior ou o menor dos elementos. Há mais duas funções predefinidas que trabalham com listas: o `sum`, que soma os elementos, e o `sorted`, que os ordena. O nome `sorted` quer dizer "ordenado".

Esta é a lista dos anos dos jogos do catálogo, pela ordem da tabela. Antes de leres as respostas, tenta prever cada linha. Repara bem nas duas últimas.

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

Leitura guiada: o `sum` soma os sete anos. O `max` e o `min` encontram o ano do jogo mais recente e do mais antigo. O `sorted` devolve uma lista nova, com os mesmos elementos, do menor para o maior. A última linha mostra que a lista `anos` não mudou. O `sorted` não arruma a lista: faz uma cópia arrumada, e a original fica como estava. Para guardar a cópia, escreve-se `por_ordem = sorted(anos)`.

Com o `sum` e o `len`, a média faz-se numa linha: `sum(anos) / len(anos)`. Dá `2013.7142857142858`, e `round(sum(anos) / len(anos), 1)` dá `2013.7`. É o acumulador e o contador do tema 04, já feitos.

### Ordenar textos

Com uma lista de textos, o `sorted` usa a ordem alfabética: `sorted(["Tetris", "Minecraft", "Celeste"])` dá `['Celeste', 'Minecraft', 'Tetris']`. Atenção às maiúsculas: para o Python, todas as maiúsculas vêm antes das minúsculas. Por isso, `sorted(["tetris", "Minecraft", "Celeste"])` dá `['Celeste', 'Minecraft', 'tetris']`, com o `tetris` no fim. Numa lista em que os textos foram arrumados todos da mesma forma, isto não acontece.

### A tabela das funções

| Função | O que devolve | Com `[30, 5, 12]` |
| --- | --- | --- |
| `len(lista)` | quantos elementos tem | `3` |
| `sum(lista)` | a soma dos elementos | `47` |
| `max(lista)` | o maior elemento | `30` |
| `min(lista)` | o menor elemento | `5` |
| `sorted(lista)` | uma lista nova, ordenada | `[5, 12, 30]` |

O `len`, o `max`, o `min` e o `sorted` servem também para os textos. O `len` de um texto conta os caracteres, como já viste. O `sorted` de um texto devolve a lista dos seus caracteres por ordem: `sorted("Tetris")` dá `['T', 'e', 'i', 'r', 's', 't']`. O `sum` só soma números, e com uma lista de textos para com `TypeError`.

### A lista vazia

O erro típico aparece com a lista vazia. O `sum([])` dá 0, porque somar nada dá zero. Mas o `max([])` e o `min([])` não têm resposta, porque não há nenhum elemento para escolher. O programa para com esta mensagem:

```text
ValueError: max() iterable argument is empty
```

Quer dizer "erro de valor: o argumento do `max` está vazio". A média também falha: com a lista vazia, `sum(lista) / len(lista)` é 0 a dividir por 0, e o programa para com `ZeroDivisionError`.

Antes de pedir o maior, confirma que a lista tem elementos, como confirmavas que havia valores antes de calcular uma média:

```python
if len(anos) == 0:
    print("Ainda não há jogos no catálogo.")
else:
    print(f"O jogo mais antigo é de {min(anos)}.")
```

A condição `len(anos) == 0` lê-se como se diz: "a lista tem zero elementos". Uma lista que cresce pode sempre ficar vazia, porque ninguém garante que alguém escreve alguma coisa. Por isso, a lista vazia é sempre um dos casos de teste.

## Exemplo guiado: a lista de jogos para experimentar

### Passo 1: o problema

> O clube quer um programa para cada sócio escolher os jogos do catálogo que quer experimentar. O sócio escreve uma parte do título, como `mine` ou `LEAGUE`, sem se preocupar com as maiúsculas nem com os espaços. Se só um título do catálogo tiver essa parte, o jogo entra na lista do sócio, a não ser que já lá esteja. Se nenhum título a tiver, o programa diz-o. Se mais do que um a tiver, o programa diz quantos são e pede mais letras. O sócio acaba carregando em Enter sem escrever nada. No fim, o programa mostra quantos jogos escolheu e a lista, por ordem alfabética e numerada.

Os títulos do catálogo são os sete da tabela do início deste guia, numa lista.

### Passo 2: os dados e as operações

Antes de escrever código, decide-se como se guarda cada dado e que operação resolve cada parte do problema.

| O que o problema pede | Os dados | A operação |
| --- | --- | --- |
| Ler a parte do título, sem espaços à volta | um texto | `input(...).strip()` |
| Saber se um título tem a parte, sem ligar às maiúsculas | dois textos | `parte.lower() in titulo.lower()` |
| Juntar os títulos que têm a parte | uma lista que começa vazia | `encontrados.append(titulo)` |
| Saber quantos títulos têm a parte | a lista dos encontrados | `len(encontrados)` |
| Não repetir um jogo na lista do sócio | a lista do sócio | `titulo in quero_jogar` |
| Acrescentar o jogo à lista do sócio | a lista do sócio, que começa vazia | `quero_jogar.append(titulo)` |
| Mostrar a lista por ordem alfabética | uma cópia ordenada | `sorted(quero_jogar)` |
| Mostrar cada jogo numerado | a cópia ordenada e o índice | `for i in range(0, len(por_ordem))` e `i + 1` |

A procura dos títulos que têm uma parte é uma tarefa com nome próprio: recebe uma parte e uma lista, e devolve outra lista. Por isso, vai para uma função, como as do tema 06. A função calcula e devolve, e a parte principal do programa é que escreve no ecrã.

### Passo 3: os resultados esperados, à mão

Escolhe-se uma sequência de partes que passe por todos os casos do enunciado, e calcula-se à mão o que deve aparecer.

| O sócio escreve | Títulos que têm a parte | O que deve aparecer |
| --- | --- | --- |
| `mine` | Minecraft | `Minecraft entrou na tua lista.` |
| `o` | Super Mario Bros. Wonder, Forza Horizon 5, Rocket League, EA Sports FC 25 | `Há 4 títulos com o. Escreve mais letras.` |
| `LEAGUE` | Rocket League | `Rocket League entrou na tua lista.` |
| `zelda` | nenhum | `Nenhum título tem zelda.` |
| `MINECRAFT` | Minecraft | `Minecraft já está na tua lista.` |
| `  tetris  ` | Tetris | `Tetris entrou na tua lista.` |
| Enter, sem nada | não se procura | acaba e mostra a lista: 3 jogos, Minecraft, Rocket League e Tetris |

O caso `o` merece uma conta cuidada. Passa-se cada título a minúsculas e procura-se o `o`. O "celeste", o "tetris" e o "minecraft" não têm nenhum `o`. Os outros quatro têm.

### Passo 4: o script completo

```python
# experimentar.py: a lista dos jogos que um sócio do clube quer experimentar.
# O sócio escreve uma parte do título, sem ligar às maiúsculas. Quando só um título
# do catálogo tem essa parte, o jogo entra na lista, se ainda lá não estiver.

CATALOGO = ["Super Mario Bros. Wonder", "Celeste", "Forza Horizon 5",
            "Rocket League", "EA Sports FC 25", "Tetris", "Minecraft"]


def procurar_titulos(parte, titulos):
    """Devolve a lista dos títulos que contêm a parte dada, sem ligar às maiúsculas.

    Recebe a parte que se procura, um texto já sem espaços à volta, e a lista
    dos títulos onde se procura, que a função não altera. Devolve uma lista nova,
    que fica vazia quando nenhum título tem a parte.
    """
    encontrados = []
    for titulo in titulos:
        # As duas formas passam a minúsculas só para a comparação.
        if parte.lower() in titulo.lower():
            encontrados.append(titulo)
    return encontrados


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

Antes de correres, confere com a tabela do passo 3 o que esperas ver. Com a sequência do passo 3, o ecrã fica assim:

```text
Parte do título (Enter para acabar): mine
Minecraft entrou na tua lista.
Parte do título (Enter para acabar): o
Há 4 títulos com o. Escreve mais letras.
Parte do título (Enter para acabar): LEAGUE
Rocket League entrou na tua lista.
Parte do título (Enter para acabar): zelda
Nenhum título tem zelda.
Parte do título (Enter para acabar): MINECRAFT
Minecraft já está na tua lista.
Parte do título (Enter para acabar):   tetris  
Tetris entrou na tua lista.
Parte do título (Enter para acabar): 

Jogos na tua lista: 3
1. Minecraft
2. Rocket League
3. Tetris
```

Leitura guiada: lê-se em quatro partes. A primeira são os dados, a lista `CATALOGO`, com os sete títulos. Escreve-se em maiúsculas, como uma constante, porque o programa nunca a muda. A segunda é a função `procurar_titulos`, que só faz uma coisa: junta numa lista nova os títulos que têm a parte, e devolve-a. A terceira é o ciclo da sentinela, que lê partes até o texto vazio. Em cada volta, a função dá a lista dos encontrados, e o `if` decide pelo tamanho dela. Zero encontrados é uma mensagem; mais do que um, outra. Com exatamente um, o `encontrados[0]` é esse título, e falta só saber se já está na lista do sócio. A quarta parte mostra o resultado, com a lista vazia tratada à parte.

Repara na ordem dos ramos. O `elif encontrados[0] in quero_jogar` só se testa quando a lista tem exatamente um elemento. Os dois ramos de cima já apanharam o zero e o "mais do que um". Se esse teste viesse primeiro, com a lista dos encontrados vazia, o `encontrados[0]` parava o programa com `IndexError`.

### Passo 5: seguir uma procura

A função tem uma lista que cresce dentro de um ciclo, e vale a pena segui-la volta a volta. Esta é a chamada `procurar_titulos("LEAGUE", CATALOGO)`:

| Volta | `titulo` | `titulo.lower()` | `"league" in ...` | `encontrados` depois da volta |
| ---: | --- | --- | --- | --- |
| antes | | | | `[]` |
| 1 | Super Mario Bros. Wonder | super mario bros. wonder | `False` | `[]` |
| 2 | Celeste | celeste | `False` | `[]` |
| 3 | Forza Horizon 5 | forza horizon 5 | `False` | `[]` |
| 4 | Rocket League | rocket league | `True` | `['Rocket League']` |
| 5 | EA Sports FC 25 | ea sports fc 25 | `False` | `['Rocket League']` |
| 6 | Tetris | tetris | `False` | `['Rocket League']` |
| 7 | Minecraft | minecraft | `False` | `['Rocket League']` |

O `parte.lower()` dá `"league"` em todas as voltas. A função devolve `['Rocket League']`, uma lista com um elemento, e a parte principal acrescenta-o à lista do sócio. O título entra com as maiúsculas do catálogo, e não com as que o sócio escreveu. O que se acrescenta é o `titulo` da lista `CATALOGO`.

### Passo 6: testar com os casos que enganam

Um programa com textos e listas testa-se sempre com a lista vazia, com um valor repetido e com o texto escrito de outra forma. A sequência do passo 3 já testou o repetido, com `MINECRAFT`, e a forma diferente, com `LEAGUE` e com `  tetris  `. Faltam estes, cada um numa execução nova. Antes de correres cada um, escreve o que esperas.

| O sócio escreve | O que testa | O que o programa mostra |
| --- | --- | --- |
| Enter, logo à primeira | a lista do sócio vazia | `Não escolheste nenhum jogo.` |
| `5`, depois `forza`, depois Enter | uma parte com dois títulos, e depois um só | `Há 2 títulos com 5. Escreve mais letras.`, `Forza Horizon 5 entrou na tua lista.` e a lista com 1 jogo |
| `fc`, `celeste`, `forza`, depois Enter | a ordem alfabética, diferente da ordem de entrada | `1. Celeste`, `2. EA Sports FC 25` e `3. Forza Horizon 5` |

O último caso mostra que a lista do sócio guarda os jogos pela ordem em que entraram. É o `sorted` que dá a ordem alfabética, só para mostrar.

Sem o `if len(quero_jogar) == 0`, o primeiro caso não dava erro, mas mostrava `Jogos na tua lista: 0` e mais nada. Funciona, mas o sócio fica sem perceber se o programa acabou bem. Sem o `.strip()` da leitura, o `  tetris  ` não encontrava nenhum título, porque nenhum tem dois espaços seguidos de "tetris".

### Passo 7: o que o programa ainda não faz

O programa mostra os títulos, mas não mostra o ano nem o género de cada jogo. Com o que sabes, podias ter uma lista de anos ao lado da lista de títulos, com o ano de cada jogo no mesmo índice. Funciona, mas obriga a manter as duas listas sempre alinhadas. Se tirares um título e te esqueceres de tirar o ano, as listas desalinham-se. Cada jogo que estava depois dele fica com o ano do jogo anterior. O tema seguinte resolve isto, com formas de guardar os quatro dados de um jogo juntos.

## Erros frequentes

Os erros desta secção não ficaram nas secções anteriores. Para cada um, ficas a saber o que aparece, porque acontece e como se corrige. Os outros estão na secção da ideia que explicam:

- o índice fora do texto, em "Um texto é uma sequência de caracteres";
- o fim da fatia que não entra, em "Fatias de um texto";
- mudar um carácter de um texto, em "Um texto não se altera";
- as maiúsculas no `in`, em "Perguntar se um texto contém outro, com `in`";
- arrumar só um dos lados da comparação, em "Os métodos dos textos";
- o `f` esquecido, em "Juntar textos e valores com f-strings";
- o `remove` de um valor que não está na lista, e o `pop` de uma lista vazia, em "Listas que crescem e encolhem";
- o `max` de uma lista vazia, em "Funções predefinidas para listas".

### Guardar o resultado do `append`

O que se vê, com `inscritos = inscritos.append("Eva")`: a lista desaparece, e `print(inscritos)` mostra `None`. No `append` seguinte, o programa para com esta mensagem:

```text
AttributeError: 'NoneType' object has no attribute 'append'
```

Quer dizer "erro de atributo: um objeto `NoneType` não tem `append`". Um atributo é o que se escreve depois do ponto, como o nome de um método. O `NoneType` é o tipo do `None`, o valor que quer dizer "nenhum valor", que já viste nas funções sem `return`.

Acontece a quem aplica a regra dos textos às listas. O `upper` de um texto devolve um texto novo, e por isso guarda-se o resultado. O `append` de uma lista muda a própria lista e não devolve nada, isto é, devolve `None`. Guardar esse `None` na variável deita a lista fora. Corrige-se escrevendo só `inscritos.append("Eva")`, sem atribuição. O mesmo acontece com o `insert` e com o `remove`.

### O código escrito noutra forma

O que se vê: o código `"PLA-02"` está numa lista de códigos, mas a pessoa escreve `pla-02`, ou `PLA-02 ` com um espaço no fim. O `in` dá `False`, e o programa diz que esse jogo não existe. Não há mensagem de erro.

Acontece porque, para o Python, dois textos só são iguais se tiverem exatamente os mesmos caracteres. As maiúsculas e os espaços contam. Corrige-se arrumando o que vem do teclado antes de procurar, para ficar na mesma forma dos valores da lista. Para os códigos do clube, que estão em maiúsculas, é `input(...).strip().upper()`. Se a pessoa puder escrever um traço baixo no lugar do hífen, junta-se um `replace("_", "-")`.

### Um número guardado como texto

O que se vê, com `anos = ["2023", "2018", "984"]`: o `max(anos)` dá `'984'`, e o `sorted(anos)` dá `['2018', '2023', '984']`. Não há mensagem de erro, mas o resultado está errado. As plicas à volta de cada valor são a pista: são textos, e não números.

Acontece quando os números ficam guardados como textos, por exemplo lidos com `input` e não convertidos. Os textos comparam-se carácter a carácter, como num dicionário de português. O `"9"` vem depois do `"2"`, e por isso `"984"` fica no fim, mesmo sendo o número mais pequeno. Corrige-se convertendo cada valor com `int` antes de o guardar na lista: `anos.append(int(texto))`. O `sum` de uma lista assim nem chega a dar um resultado errado: para com `TypeError`.

## Palavras novas deste guia

- Coleção: um valor que guarda outros valores, como um texto ou uma lista.
- Carácter: uma letra, um algarismo, um sinal ou um espaço; um texto é uma sequência de caracteres.
- Índice: a posição de um carácter num texto, ou de um elemento numa lista, a contar do 0.
- Índice negativo: um índice que conta a partir do fim; `-1` é o último.
- Fatia: um pedaço de um texto, tirado por posições, como `codigo[0:3]`; o segundo índice não entra.
- `in`: numa condição, pergunta se um valor está dentro de uma coleção; num texto procura um pedaço, numa lista procura um elemento.
- Método: uma função que pertence a um valor e se chama com um ponto, como `titulo.upper()`.
- Encadear métodos: chamar um método sobre o resultado de outro, na mesma linha, como `texto.strip().lower()`.
- `upper` e `lower`: os métodos que devolvem um texto em maiúsculas ou em minúsculas.
- `strip`: o método que devolve um texto sem os espaços do início e do fim.
- `split`: o método que parte um texto numa lista, nos espaços ou no sinal que se indica.
- `replace`: o método que devolve um texto com cada pedaço indicado trocado por outro.
- `isdigit`: o método que diz se um texto tem só algarismos.
- Imutável: que não se pode alterar depois de criado, como um texto.
- Mutável: que se pode alterar depois de criado, como uma lista.
- f-string: um texto com um `f` antes das aspas, em que cada par de chavetas recebe um valor.
- `append`: o método que acrescenta um elemento no fim de uma lista.
- `insert`: o método que põe um elemento numa posição de uma lista e empurra os outros.
- `remove`: o método que tira de uma lista a primeira vez que um valor aparece.
- `pop`: o método que tira de uma lista o elemento de uma posição, o último se não se disser qual, e o devolve.
- `sum`: a função que soma os elementos de uma lista.
- `sorted`: a função que devolve uma lista nova, com os elementos ordenados.
- Atributo: o que se escreve depois do ponto num valor, como o nome de um método.

## Verificar o que aprendeste

Usa estas perguntas para te testares. Responde a cada uma sem olhar para o guia. Se não conseguires, volta à secção que explica a ideia.

1. Com `nome = "Rocket League"`, quanto vale `len(nome)`? E `nome[0]`, `nome[-1]` e `nome[7:]`?
2. Que fatia de `"DES-02"` dá `"DES"`? E qual dá `"02"`? Porque é que `"DES-02"[0:2]` não serve?
3. Que etiqueta faz o `etiqueta.py` com o título `Super Mario Bros. Wonder`? Conta os caracteres com cuidado.
4. O que dá `"tetris" in "Tetris"`? Como escreves a condição para dar `True`, sem mudar os textos originais?
5. O que dá `"Mar" in "Mario"`? E `"Mar" in ["Mario", "Celeste"]`? Porque é que as respostas são diferentes?
6. Depois de `titulo = "Minecraft"` e `titulo.upper()`, quanto vale `titulo`? Porquê?
7. O que dá `" 12".isdigit()`? E `" 12".strip().isdigit()`? Porque é que convém perguntar antes de usar o `int`?
8. O que escreve `print(f"{titulo} tem {len(titulo)} letras")`, com `titulo = "Celeste"`? E sem o `f`?
9. Começas com `lista = []` e fazes `lista.append(4)`, `lista.append(9)`, `lista.insert(0, 7)`, `lista.append(4)` e `lista.remove(4)`. Como fica a lista?
10. Com `fila = ["Rui", "Ana", "Bia"]`, o que devolve `fila.pop(0)`, e como fica a fila? E se a fila estiver vazia?
11. O que dá `sorted([12, 3, 7])`? E como fica a lista depois?
12. Porque é que `anos = anos.append(2011)` estraga a lista, e `titulo = titulo.upper()` não estraga o título?
13. Que operações param o programa com uma lista vazia? Como se evita?

## O que vem a seguir

Para praticar este tema, faz o [laboratório](laboratorios/07-textos-e-listas-que-mudam-laboratorio.md). Nele constróis dois programas do clube: um arruma e confirma o código de um jogo, e o outro gere a fila para a consola. Depois faz a [ficha de exercícios](exercicios/07-textos-e-listas-que-mudam-exercicios.md). Tem exercícios com textos e com listas, e um script com erros para encontrar.

O tema seguinte é [Tuplos, dicionários e conjuntos](08-tuplos-dicionarios-e-conjuntos.md). Vais guardar os quatro dados de cada jogo juntos, procurar um jogo pelo código sem percorrer a lista, e tirar os repetidos de uma coleção.

![Rodapé](../imagens/rodape.png)
