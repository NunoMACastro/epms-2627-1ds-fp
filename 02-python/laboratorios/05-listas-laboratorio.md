![Cabeçalho](../../imagens/cabecalho.png)

# Laboratório: Listas

## O que vais construir

Vais construir `equipa.py`, um programa que mostra o estado de uma equipa num jogo, a partir dos pontos de vida numa lista. Um jogador com 0 pontos está fora de combate, e a poção dá 30 pontos a quem está em jogo, sem passar de 100.

No fim, o ecrã fica assim:

```text
Pontos de vida: [80, 45, 0, 100, 25]
Jogadores na equipa: 5
Primeiro jogador: 80 pontos de vida
Último jogador: 25 pontos de vida
Vida total da equipa: 250
Vida média: 50.0
Jogador 1 tem 80 pontos de vida
Jogador 2 tem 45 pontos de vida
Jogador 3 tem 0 pontos de vida
Jogador 4 tem 100 pontos de vida
Jogador 5 tem 25 pontos de vida
Primeiro jogador fora de combate: jogador 3
Depois da poção: [100, 75, 0, 100, 55]
```

1. [Fase 1: Uma lista guarda vários valores com um só nome](#fase-1-uma-lista-guarda-vários-valores-com-um-só-nome)
2. [Fase 2: O índice é a posição de cada elemento](#fase-2-o-índice-é-a-posição-de-cada-elemento)
3. [Fase 3: O `len` diz quantos elementos tem a lista](#fase-3-o-len-diz-quantos-elementos-tem-a-lista)
4. [Fase 4: Percorrer a lista pelo valor, com `for`](#fase-4-percorrer-a-lista-pelo-valor-com-for)
5. [Fase 5: Percorrer a lista pelo índice, com `range` e `len`](#fase-5-percorrer-a-lista-pelo-índice-com-range-e-len)
6. [Fase 6: Procurar um valor com uma bandeira](#fase-6-procurar-um-valor-com-uma-bandeira)
7. [Fase 7: Parar a pesquisa com `break`](#fase-7-parar-a-pesquisa-com-break)
8. [Fase 8: Mudar um elemento pelo índice](#fase-8-mudar-um-elemento-pelo-índice)
9. [Fase 9: Saltar uma volta com `continue`](#fase-9-saltar-uma-volta-com-continue)
10. [Fase 10: A lista vazia e os três casos de teste](#fase-10-a-lista-vazia-e-os-três-casos-de-teste)

## O que precisas

- A pasta `fp-python`, aberta no VS Code, e um terminal, que se abre no menu Terminal, com a opção New Terminal. Se não a tiveres, faz primeiro [Preparar o projeto](01-do-pseudocodigo-ao-python-laboratorio.md#preparar-o-projeto), no laboratório do tema 01.
- O comando que corre o Python no teu computador, `python`, `py` ou `python3`. Onde o texto diz `python`, usa o teu.

## Fase 1: Uma lista guarda vários valores com um só nome

Crias o programa e guardas os pontos de vida dos cinco jogadores numa lista. Uma lista escreve-se como um array do pseudocódigo: valores entre parênteses retos, separados por vírgulas. Rever: [Uma lista guarda vários valores com um só nome](../05-listas.md#uma-lista-guarda-vários-valores-com-um-só-nome).

1. No painel Explorer, cria um ficheiro novo, com o nome `equipa.py`, e escreve nele:

   ```python
   # equipa.py: o estado de uma equipa num jogo, a partir dos pontos de vida de cada jogador.

   pontos_de_vida = [80, 45, 0, 100, 25]
   print("Pontos de vida:", pontos_de_vida)
   ```

2. Guarda e corre o programa:

   ```bash
   python equipa.py
   ```

   O que deves ver: `Pontos de vida: [80, 45, 0, 100, 25]`. Isto quer dizer que a lista ficou guardada com um só nome. Se aparecer outra coisa, vê [Se alguma coisa falhar](#se-alguma-coisa-falhar).

### Paragem 1

O `equipa.py` mostra a lista.

Pensa antes de continuares: o que mudava se a equipa tivesse seis jogadores? A resposta: só a linha da lista, com mais um valor.

## Fase 2: O índice é a posição de cada elemento

Mostras o primeiro e o último jogador. O índice começa em 0, e por isso `pontos_de_vida[0]` é o primeiro. Rever: [O índice é a posição de cada elemento](../05-listas.md#o-índice-é-a-posição-de-cada-elemento).

1. No fim do ficheiro, acrescenta:

   ```python
   print("Primeiro jogador:", pontos_de_vida[0], "pontos de vida")
   print("Último jogador:", pontos_de_vida[4], "pontos de vida")
   ```

   Guarda e corre. O que deves ver a seguir à lista: `Primeiro jogador: 80 pontos de vida` e `Último jogador: 25 pontos de vida`. Numa lista de cinco elementos, os índices vão de 0 a 4.

2. Provoca um erro: na última linha, muda o `[4]` para `[5]`. Guarda e corre. O que deves ver no fim:

   ```text
   Traceback (most recent call last):
     File "C:\Users\aluno\Documents\fp-python\equipa.py", line 6, in <module>
       print("Último jogador:", pontos_de_vida[5], "pontos de vida")
                                ~~~~~~~~~~~~~~^^^
   IndexError: list index out of range
   ```

   Não há índice 5, porque o último válido é o 4. Volta a pôr `[4]` e guarda.

### Paragem 2

O `equipa.py` mostra a lista, o primeiro e o último jogador.

Pensa antes de continuares: se a equipa tivesse 8 jogadores, que índice tinha o último? A resposta: o 7, o número de elementos menos 1.

## Fase 3: O `len` diz quantos elementos tem a lista

O `[4]` só serve para uma equipa de cinco jogadores. O `len` devolve quantos elementos tem a lista. Rever: [O `len` diz quantos elementos tem a lista](../05-listas.md#o-len-diz-quantos-elementos-tem-a-lista).

1. A seguir à linha da lista, acrescenta:

   ```python
   numero_de_jogadores = len(pontos_de_vida)
   ```

2. A seguir ao `print` da lista, acrescenta:

   ```python
   print("Jogadores na equipa:", numero_de_jogadores)
   ```

3. Substitui a linha do último jogador por estas duas:

   ```python
   # O último índice válido é o número de elementos menos 1.
   print("Último jogador:", pontos_de_vida[numero_de_jogadores - 1], "pontos de vida")
   ```

   Guarda e corre. O que deves ver: as linhas de antes, e `Jogadores na equipa: 5`.

4. Muda a lista para `[80, 45, 0, 100, 25, 60]`. Antes de correres, prevê o que muda. Guarda e corre.

   O que deves ver: `Jogadores na equipa: 6` e `Último jogador: 60 pontos de vida`, sem mudares mais nenhuma linha. Volta a pôr a lista `[80, 45, 0, 100, 25]` e guarda.

### Paragem 3

O `equipa.py` conta os jogadores e encontra o último, seja qual for o tamanho da lista.

O ficheiro `equipa.py` completo, como deve estar agora:

```python
# equipa.py: o estado de uma equipa num jogo, a partir dos pontos de vida de cada jogador.

pontos_de_vida = [80, 45, 0, 100, 25]
numero_de_jogadores = len(pontos_de_vida)
print("Pontos de vida:", pontos_de_vida)
print("Jogadores na equipa:", numero_de_jogadores)
print("Primeiro jogador:", pontos_de_vida[0], "pontos de vida")
# O último índice válido é o número de elementos menos 1.
print("Último jogador:", pontos_de_vida[numero_de_jogadores - 1], "pontos de vida")
```

O número de jogadores calcula-se logo a seguir à lista, e as linhas de baixo usam-no. Quando a lista muda, não é preciso mudar mais nada.

Pensa antes de continuares: porque é que `pontos_de_vida[numero_de_jogadores]` daria `IndexError`? A resposta: o `len` dá 5, e o último índice é o 4.

## Fase 4: Percorrer a lista pelo valor, com `for`

Somas os pontos de todos os jogadores. O `Para cada` do pseudocódigo passa a `for`, e a variável recebe um elemento em cada volta. Rever: [Percorrer a lista pelo valor, com `for`](../05-listas.md#percorrer-a-lista-pelo-valor-com-for).

1. No fim do ficheiro, acrescenta uma linha em branco e estas linhas:

   ```python
   # A vida total soma os pontos de todos os jogadores.
   total = 0
   for vida in pontos_de_vida:
       total = total + vida
   print("Vida total da equipa:", total)
   media = total / numero_de_jogadores
   print("Vida média:", media)
   ```

2. Antes de correres, calcula de cabeça a vida total e a média. Guarda e corre. O que deves ver no fim:

   ```text
   Vida total da equipa: 250
   Vida média: 50.0
   ```

   A média aparece como `50.0`, porque a divisão com `/` dá sempre um `float`.

### Paragem 4

O `equipa.py` mostra a vida total e a vida média.

Pensa antes de continuares: o que acontecia se `total = 0` estivesse dentro do ciclo? A resposta: o total voltava a 0 em cada volta, e no fim guardava só o último jogador, 25.

## Fase 5: Percorrer a lista pelo índice, com `range` e `len`

Mostras uma linha por jogador, com o seu número. Para isso é preciso a posição, e a lista percorre-se pelo índice. Rever: [Percorrer a lista pelo índice, com `range` e `len`](../05-listas.md#percorrer-a-lista-pelo-índice-com-range-e-len).

1. No fim do ficheiro, separadas por uma linha em branco, acrescenta:

   ```python
   for i in range(0, numero_de_jogadores):
       # O i + 1 faz com que o jogador de índice 0 seja, para as pessoas, o jogador 1.
       print("Jogador", i + 1, "tem", pontos_de_vida[i], "pontos de vida")
   ```

   Guarda e corre. O que deves ver no fim: as cinco linhas, de `Jogador 1 tem 80 pontos de vida` a `Jogador 5 tem 25 pontos de vida`.

2. Provoca um erro: muda o `range(0, numero_de_jogadores)` para `range(1, numero_de_jogadores)`. Guarda e corre.

   O que deves ver: falta o jogador 1, e não há nenhuma mensagem de erro. O `range` começa no índice 1, e o elemento de índice 0 nunca é usado. Volta a pôr o 0 e guarda.

### Paragem 5

O `equipa.py` mostra cada jogador com o seu número.

Pensa antes de continuares: porque é que aqui não serve o `for vida in pontos_de_vida:`? A resposta: a variável só tem o valor de cada elemento, e não a posição.

## Fase 6: Procurar um valor com uma bandeira

Descobres se há algum jogador fora de combate. A resposta fica numa bandeira, uma variável `bool` que começa em `False` e passa a `True` quando aparece o que se procura. Rever: [Procurar um valor com uma bandeira](../05-listas.md#procurar-um-valor-com-uma-bandeira).

1. Depois de uma linha em branco, no fim do ficheiro, acrescenta:

   ```python
   # A bandeira diz, depois do ciclo, se apareceu algum jogador com 0 pontos de vida.
   alguem_fora = False
   for vida in pontos_de_vida:
       if vida == 0:
           alguem_fora = True
   if alguem_fora:
       print("Há pelo menos um jogador fora de combate.")
   else:
       print("Nenhum jogador está fora de combate.")
   ```

   Guarda e corre. O que deves ver no fim: `Há pelo menos um jogador fora de combate.`

2. Testa o outro caso: muda o 0 da lista para 10, guarda e corre. O que deves ver no fim: `Nenhum jogador está fora de combate.` Volta a pôr a lista `[80, 45, 0, 100, 25]` e guarda.

### Paragem 6

O `equipa.py` diz se há algum jogador fora de combate.

Pensa antes de continuares: porque é que a mensagem "Nenhum jogador está fora de combate." não está dentro do ciclo, num `else`? A resposta: aparecia uma vez por cada jogador em jogo, mesmo havendo um fora de combate.

## Fase 7: Parar a pesquisa com `break`

Descobres qual é o primeiro jogador fora de combate. O `Parar` do pseudocódigo escreve-se `break`, e termina o ciclo. Rever: [Parar a pesquisa com `break`](../05-listas.md#parar-a-pesquisa-com-break).

1. Substitui as linhas que acrescentaste na fase 6, do comentário da bandeira até ao fim, por estas:

   ```python
   # A bandeira diz, depois do ciclo, se apareceu algum jogador com 0 pontos de vida.
   alguem_fora = False
   for i in range(0, numero_de_jogadores):
       if pontos_de_vida[i] == 0:
           print("Primeiro jogador fora de combate: jogador", i + 1)
           alguem_fora = True
           # Já se sabe qual é o primeiro: o resto da lista não interessa.
           break
   if not alguem_fora:
       print("Nenhum jogador está fora de combate.")
   ```

   O `if not alguem_fora:` fica encostado à margem, fora do ciclo.

2. Antes de correres, prevê quantas voltas dá o ciclo. Guarda e corre. O que deves ver no fim: `Primeiro jogador fora de combate: jogador 3`. O ciclo deu três voltas, e os jogadores 4 e 5 nunca foram vistos.

3. Muda a lista para `[80, 0, 0, 100, 25]`, guarda e corre. O que deves ver no fim: `Primeiro jogador fora de combate: jogador 2`.

4. Provoca um erro, com a mesma lista: apaga a linha do `break` e o comentário de cima dela. Guarda e corre. O que deves ver no fim:

   ```text
   Primeiro jogador fora de combate: jogador 2
   Primeiro jogador fora de combate: jogador 3
   ```

   Sem o `break`, o ciclo continua e encontra o segundo. Volta a escrever o comentário e o `break`, alinhados com o `alguem_fora = True`, e volta a pôr a lista `[80, 45, 0, 100, 25]`. Guarda.

### Paragem 7

O `equipa.py` diz qual é o primeiro jogador fora de combate, ou que não há nenhum.

O ficheiro `equipa.py` completo, como deve estar agora:

```python
# equipa.py: o estado de uma equipa num jogo, a partir dos pontos de vida de cada jogador.

pontos_de_vida = [80, 45, 0, 100, 25]
numero_de_jogadores = len(pontos_de_vida)
print("Pontos de vida:", pontos_de_vida)
print("Jogadores na equipa:", numero_de_jogadores)
print("Primeiro jogador:", pontos_de_vida[0], "pontos de vida")
# O último índice válido é o número de elementos menos 1.
print("Último jogador:", pontos_de_vida[numero_de_jogadores - 1], "pontos de vida")

# A vida total soma os pontos de todos os jogadores.
total = 0
for vida in pontos_de_vida:
    total = total + vida
print("Vida total da equipa:", total)
media = total / numero_de_jogadores
print("Vida média:", media)

for i in range(0, numero_de_jogadores):
    # O i + 1 faz com que o jogador de índice 0 seja, para as pessoas, o jogador 1.
    print("Jogador", i + 1, "tem", pontos_de_vida[i], "pontos de vida")

# A bandeira diz, depois do ciclo, se apareceu algum jogador com 0 pontos de vida.
alguem_fora = False
for i in range(0, numero_de_jogadores):
    if pontos_de_vida[i] == 0:
        print("Primeiro jogador fora de combate: jogador", i + 1)
        alguem_fora = True
        # Já se sabe qual é o primeiro: o resto da lista não interessa.
        break
if not alguem_fora:
    print("Nenhum jogador está fora de combate.")
```

Cada bloco separado por uma linha em branco responde a uma pergunta sobre a equipa. Todos usam a mesma lista, e o número de jogadores calcula-se uma vez, no início.

Pensa antes de continuares: e se o `break` tivesse quatro espaços, alinhado com o `if`? A resposta: executava-se logo na primeira volta, e o programa dizia que nenhum jogador está fora de combate.

## Fase 8: Mudar um elemento pelo índice

A poção muda os pontos de vida, e por isso muda os elementos da lista. Primeiro experimentas o ciclo que já conheces. Rever: [Mudar um elemento pelo índice](../05-listas.md#mudar-um-elemento-pelo-índice).

1. Os 30 pontos e o máximo de 100 são regras do jogo, e por isso ficam em constantes. Põe o cursor no fim da linha 1 e carrega em Enter. Na linha nova, escreve:

   ```python
   VIDA_MAXIMA = 100
   CURA_DA_POCAO = 30
   ```

2. Experimenta primeiro uma versão que parece certa. No fim do ficheiro, depois de uma linha em branco, escreve:

   ```python
   # Primeira tentativa: percorrer pelo valor.
   for vida in pontos_de_vida:
       vida = vida + CURA_DA_POCAO
   print("Depois da poção:", pontos_de_vida)
   ```

   Antes de correres, prevê a lista que aparece. Guarda e corre. O que deves ver no fim: `Depois da poção: [80, 45, 0, 100, 25]`. A lista não mudou, porque a linha do corpo dá um valor novo só à variável.

3. Substitui as quatro linhas que acabaste de acrescentar por estas:

   ```python
   # A poção da equipa cura cada jogador, sem passar do máximo de pontos de vida.
   for i in range(0, numero_de_jogadores):
       pontos_de_vida[i] = pontos_de_vida[i] + CURA_DA_POCAO
       if pontos_de_vida[i] > VIDA_MAXIMA:
           pontos_de_vida[i] = VIDA_MAXIMA
   print("Depois da poção:", pontos_de_vida)
   ```

   Guarda e corre. O que deves ver no fim: `Depois da poção: [100, 75, 30, 100, 55]`. O jogador 1 ficava com 110, e o `if` pô-lo nos 100.

### Paragem 8

O `equipa.py` usa a poção e mostra a lista depois de mudada.

Pensa antes de continuares: o jogador 3 estava fora de combate e ficou com 30 pontos. Faz sentido? A resposta: num jogo, uma poção de cura não serve a quem já está fora de combate.

## Fase 9: Saltar uma volta com `continue`

A poção passa a não curar os jogadores fora de combate. O `Continuar` do pseudocódigo escreve-se `continue`, e termina só a volta atual. Rever: [Saltar uma volta com `continue`](../05-listas.md#saltar-uma-volta-com-continue).

1. No ciclo da poção, logo a seguir à linha do `for`, acrescenta:

   ```python
       if pontos_de_vida[i] == 0:
           # Quem está fora de combate não é curado: passa-se ao jogador seguinte.
           continue
   ```

2. Guarda e corre. O que deves ver no fim: `Depois da poção: [100, 75, 0, 100, 55]`. O jogador 3 continua com 0.

### Paragem 9

O `equipa.py` usa a poção só nos jogadores em jogo.

Pensa antes de continuares: como podias fazer o mesmo sem `continue`? A resposta: com as três linhas da cura dentro de um `if pontos_de_vida[i] > 0:`.

## Fase 10: A lista vazia e os três casos de teste

Testas o programa com a lista vazia, com um elemento e com vários. É assim que se encontram os erros que o caso normal esconde. Rever: [A lista vazia e os três casos de teste](../05-listas.md#a-lista-vazia-e-os-três-casos-de-teste).

1. Muda a lista para `pontos_de_vida = []`. Antes de correres, prevê o que acontece. Guarda e corre. O que deves ver no fim:

   ```text
   Traceback (most recent call last):
     File "C:\Users\aluno\Documents\fp-python\equipa.py", line 9, in <module>
       print("Primeiro jogador:", pontos_de_vida[0], "pontos de vida")
                                  ~~~~~~~~~~~~~~^^^
   IndexError: list index out of range
   ```

   Uma lista vazia não tem o índice 0.

2. Substitui as três linhas, do `print` do primeiro jogador ao `print` do último, por estas:

   ```python
   # Sem jogadores, não há primeiro nem último: a lista vazia não tem o índice 0.
   if numero_de_jogadores > 0:
       print("Primeiro jogador:", pontos_de_vida[0], "pontos de vida")
       # O último índice válido é o número de elementos menos 1.
       print("Último jogador:", pontos_de_vida[numero_de_jogadores - 1], "pontos de vida")
   ```

   Guarda e corre, ainda com a lista vazia. O que deves ver no fim:

   ```text
   Traceback (most recent call last):
     File "C:\Users\aluno\Documents\fp-python\equipa.py", line 20, in <module>
       media = total / numero_de_jogadores
               ~~~~~~^~~~~~~~~~~~~~~~~~~~~
   ZeroDivisionError: division by zero
   ```

   O primeiro erro desapareceu, e apareceu outro, porque a conta é 0 a dividir por 0.

3. Substitui as duas linhas da média por estas:

   ```python
   # Sem este if, com a equipa vazia, a conta seria 0 / 0 e o programa parava.
   if numero_de_jogadores > 0:
       media = total / numero_de_jogadores
       print("Vida média:", media)
   else:
       print("Sem jogadores, não há vida média.")
   ```

   Guarda e corre, ainda com a lista vazia. O que deves ver:

   ```text
   Pontos de vida: []
   Jogadores na equipa: 0
   Vida total da equipa: 0
   Sem jogadores, não há vida média.
   Nenhum jogador está fora de combate.
   Depois da poção: []
   ```

4. Muda a linha da lista para cada uma desta tabela, guarda e corre:

   | Lista | Jogadores | Vida média | Fora de combate | Depois da poção |
   | --- | ---: | --- | --- | --- |
   | `[]` | 0 | `Sem jogadores, não há vida média.` | nenhum | `[]` |
   | `[45]` | 1 | `45.0` | nenhum | `[75]` |
   | `[0]` | 1 | `0.0` | jogador 1 | `[0]` |
   | `[80, 45, 100, 0]` | 4 | `56.25` | jogador 4 | `[100, 75, 100, 0]` |
   | `[80, 45, 0, 100, 25]` | 5 | `50.0` | jogador 3 | `[100, 75, 0, 100, 55]` |

   O que deves ver: em cada caso, o que a tabela diz. Com a última lista, o ecrã é o de "O que vais construir".

### Paragem 10

O `equipa.py` dá o resultado certo nos três casos de teste, e com o jogador fora de combate no início, no meio e no fim.

O ficheiro `equipa.py` completo, como deve estar no fim:

```python
# equipa.py: o estado de uma equipa num jogo, a partir dos pontos de vida de cada jogador.
VIDA_MAXIMA = 100
CURA_DA_POCAO = 30

pontos_de_vida = [80, 45, 0, 100, 25]
numero_de_jogadores = len(pontos_de_vida)
print("Pontos de vida:", pontos_de_vida)
print("Jogadores na equipa:", numero_de_jogadores)
# Sem jogadores, não há primeiro nem último: a lista vazia não tem o índice 0.
if numero_de_jogadores > 0:
    print("Primeiro jogador:", pontos_de_vida[0], "pontos de vida")
    # O último índice válido é o número de elementos menos 1.
    print("Último jogador:", pontos_de_vida[numero_de_jogadores - 1], "pontos de vida")

# A vida total soma os pontos de todos os jogadores.
total = 0
for vida in pontos_de_vida:
    total = total + vida
print("Vida total da equipa:", total)
# Sem este if, com a equipa vazia, a conta seria 0 / 0 e o programa parava.
if numero_de_jogadores > 0:
    media = total / numero_de_jogadores
    print("Vida média:", media)
else:
    print("Sem jogadores, não há vida média.")

for i in range(0, numero_de_jogadores):
    # O i + 1 faz com que o jogador de índice 0 seja, para as pessoas, o jogador 1.
    print("Jogador", i + 1, "tem", pontos_de_vida[i], "pontos de vida")

# A bandeira diz, depois do ciclo, se apareceu algum jogador com 0 pontos de vida.
alguem_fora = False
for i in range(0, numero_de_jogadores):
    if pontos_de_vida[i] == 0:
        print("Primeiro jogador fora de combate: jogador", i + 1)
        alguem_fora = True
        # Já se sabe qual é o primeiro: o resto da lista não interessa.
        break
if not alguem_fora:
    print("Nenhum jogador está fora de combate.")

# A poção da equipa cura cada jogador, sem passar do máximo de pontos de vida.
for i in range(0, numero_de_jogadores):
    if pontos_de_vida[i] == 0:
        # Quem está fora de combate não é curado: passa-se ao jogador seguinte.
        continue
    pontos_de_vida[i] = pontos_de_vida[i] + CURA_DA_POCAO
    if pontos_de_vida[i] > VIDA_MAXIMA:
        pontos_de_vida[i] = VIDA_MAXIMA
print("Depois da poção:", pontos_de_vida)
```

A divisão e as linhas que usam o índice 0 estão protegidas por um `if`. Os ciclos não precisam, porque com a lista vazia não dão nenhuma volta.

Pensa antes de continuares: porque é que a lista vazia mostrou erros que as outras não mostraram? A resposta: só nela é que não há índice 0 e o número de jogadores é 0.

## Se alguma coisa falhar

1. Guardaste o ficheiro? O Python corre o que está no disco, e não o que vês no ecrã.
2. Estás na pasta certa? No terminal, o texto antes do cursor tem de ter `fp-python` no fim, antes do `>` ou do `%`.
3. Desfizeste o que mudaste para experimentar, o erro ou a lista? Antes de passares à fase seguinte, o programa tem de voltar a dar o resultado certo.

### `IndexError: list index out of range`

O programa usou um índice que não existe. O último índice válido é o número de elementos menos 1. Numa lista vazia, nem o 0 existe.

### `SyntaxError: '[' was never closed`

Falta o parêntese reto do fim da lista. Acrescenta o `]` depois do último valor.

### `SyntaxError: invalid syntax. Perhaps you forgot a comma?`

Na lista, falta uma vírgula entre dois valores, como em `[80, 45 0, 100, 25]`.

### `SyntaxError: expected ':'`

Faltam os dois pontos no fim da linha do `for` ou do `if`.

### `IndentationError: expected an indented block after ...`

A linha a seguir aos dois pontos tem de ficar quatro espaços mais para dentro do que a linha dos dois pontos.

### `NameError: name 'pontos_de_vidas' is not defined. Did you mean: 'pontos_de_vida'?`

O nome está mal escrito nessa linha, e o Python sugere o certo.

### `ZeroDivisionError: division by zero`

A divisão da média não está dentro do `if numero_de_jogadores > 0:`.

### A lista não muda depois da poção

O ciclo da poção percorre a lista pelo valor. Usa o ciclo pelo índice, com `pontos_de_vida[i]` do lado esquerdo do `=`.

### Aparecem duas linhas de "Primeiro jogador fora de combate"

Falta o `break`. Tem de estar dentro do `if`, com oito espaços.

## Desafios

Faz cada desafio num ficheiro novo, como `desafio_1.py`, com o código do programa copiado para lá. Calcula os casos de cabeça antes de correres.

1. Acrescenta, antes da poção, o código para o programa escrever uma linha a dizer que jogador tem mais pontos de vida, como `Jogador com mais vida: jogador 4 com 100 pontos de vida`. Testa também com `[100, 45, 100]`, em que há um empate, e decide qual dos dois aparece. Com a lista vazia, o programa não pode parar com um erro. Pista: guarda numa variável o maior visto até agora, e noutra a posição dele.
2. Um jogador está em perigo quando ainda está em jogo, mas tem menos de 30 pontos de vida. Acrescenta, antes da poção, o código para o programa escrever quantos estão em perigo. Com a lista do início, é 1. Testa também com `[29, 30, 1]`. Pista: a condição tem duas partes, e o `and` junta-as.
3. A poção de reviver traz de volta ao jogo o primeiro jogador fora de combate, com 50 pontos de vida. Usa-a antes da poção de cura. Com a lista do início, o jogador 3 volta com 50 e, depois da cura, fica com 80. Com `[80, 0, 0, 100, 25]`, só o jogador 2 volta. Rever: [Parar a pesquisa com `break`](../05-listas.md#parar-a-pesquisa-com-break).

## Antes de terminares

- [ ] O `equipa.py` mostra o ecrã completo de "O que vais construir" com a lista `[80, 45, 0, 100, 25]`.
- [ ] O `equipa.py` dá os resultados da tabela da fase 10, sem parar com nenhum erro.

![Rodapé](../../imagens/rodape.png)
