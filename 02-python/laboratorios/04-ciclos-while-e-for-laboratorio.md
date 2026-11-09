![Cabeçalho](../../imagens/cabecalho.png)

# Laboratório: Ciclos while e for

## O que vais construir

Vais passar para Python o problema da campanha de recolha de alimentos da escola. O `campanha.py` lê os quilos de cada turma até aparecer o -1, e o `campanha_10ano.py` pede os quilos das 6 turmas do 10.º ano.

No fim, com 12, 0, 9 e -1, o `campanha.py` mostra:

```text
Quilos entregues pela turma (-1 para terminar)? 12
Quilos entregues pela turma (-1 para terminar)? 0
Quilos entregues pela turma (-1 para terminar)? 9
Quilos entregues pela turma (-1 para terminar)? -1
Turmas que entregaram: 3
Total: 21 kg
Média por turma: 7.0 kg
```

1. [Fase 1: Ler até à sentinela](#fase-1-ler-até-à-sentinela)
2. [Fase 2: O ciclo que nunca acaba, e o Ctrl+C](#fase-2-o-ciclo-que-nunca-acaba-e-o-ctrlc)
3. [Fase 3: O contador e o acumulador](#fase-3-o-contador-e-o-acumulador)
4. [Fase 4: Ver as voltas com linhas de observação](#fase-4-ver-as-voltas-com-linhas-de-observação)
5. [Fase 5: A média, só quando há valores](#fase-5-a-média-só-quando-há-valores)
6. [Fase 6: Contar voltas com `for` e `range`](#fase-6-contar-voltas-com-for-e-range)
7. [Fase 7: As duas formas do `Para` e o `range`](#fase-7-as-duas-formas-do-para-e-o-range)
8. [Fase 8: Contar só algumas voltas](#fase-8-contar-só-algumas-voltas)
9. [Fase 9, opcional: A validação repetida pede o valor outra vez](#fase-9-opcional-a-validação-repetida-pede-o-valor-outra-vez)

## O que precisas

- A pasta `fp-python`, aberta no VS Code, e um terminal, que se abre no menu Terminal, com a opção New Terminal. Se não a tiveres, faz primeiro [Preparar o projeto](01-do-pseudocodigo-ao-python-laboratorio.md#preparar-o-projeto), no laboratório do tema 01.
- O comando que corre o Python no teu computador, `python`, `py` ou `python3`. Onde o texto diz `python`, usa o teu.

## Fase 1: Ler até à sentinela

O programa lê os quilos de cada turma com um `while`, o `Enquanto` do pseudocódigo, até aparecer o -1, a sentinela. Por agora, só conta as turmas. Rever: [Ler até à sentinela](../04-ciclos-while-e-for.md#ler-até-à-sentinela).

1. No painel Explorer, cria um ficheiro novo, com o nome `campanha.py`, e escreve nele:

   ```python
   # campanha.py: a campanha de recolha de alimentos da escola.
   SENTINELA = -1

   turmas = 0
   quilos = int(input("Quilos entregues pela turma (-1 para terminar)? "))
   while quilos != SENTINELA:
       turmas = turmas + 1
       # Ler o valor seguinte é a atualização: sem esta linha, o ciclo nunca acabava.
       quilos = int(input("Quilos entregues pela turma (-1 para terminar)? "))
   print("Turmas que entregaram:", turmas)
   ```

2. Vais testar zero voltas, uma volta e várias voltas. Antes de correres, prevê quantas voltas dá o ciclo em cada caso. Guarda e corre o programa uma vez por caso:

   ```bash
   python campanha.py
   ```

   | Valores escritos, por ordem | Voltas | O que aparece no fim |
   | --- | ---: | --- |
   | -1 | 0 | `Turmas que entregaram: 0` |
   | 15, -1 | 1 | `Turmas que entregaram: 1` |
   | 12, 0, 9, -1 | 3 | `Turmas que entregaram: 3` |

   O programa escreve a pergunta e fica à espera. Clica no terminal, escreve cada valor e carrega em Enter. O que deves ver: em cada caso, o que está na última coluna da tabela. O -1 nunca é contado, e o 0 conta como turma. Se aparecer outra coisa, vê [Se alguma coisa falhar](#se-alguma-coisa-falhar).

### Paragem 1

O `campanha.py` lê turmas até ao -1 e conta-as.

Pensa antes de continuares: o que acontecia se a sentinela fosse o 0? A resposta: com 12, 0, 9, -1, o programa parava no 0 e contava só 1 turma. O 0 é um dado verdadeiro, o de uma turma que não trouxe nada.

## Fase 2: O ciclo que nunca acaba, e o Ctrl+C

Tiras de propósito a atualização, para veres um ciclo infinito e aprenderes a pará-lo. Sem atualização, a condição nunca chega a dar `False`. Rever: [O ciclo que nunca acaba, e o Ctrl+C](../04-ciclos-while-e-for.md#o-ciclo-que-nunca-acaba-e-o-ctrlc).

1. Na linha 9, a do `input` no fim do corpo, põe um `#` antes do `quilos`, para ela passar a comentário. Guarda, corre e escreve `12`.

   O que deves ver: depois do 12, não aparece mais nada, e o terminal não fica pronto para outro comando. Está a dar voltas sem fim, muito depressa, porque `quilos` vale sempre 12 e a condição dá sempre `True`.

2. Clica no terminal e carrega em Ctrl+C: segura a tecla Ctrl (no macOS, a Control, e não a Cmd) e carrega na tecla C. O que deves ver no fim do ecrã:

   ```text
   Traceback (most recent call last):
     File "C:\Users\aluno\Documents\fp-python\campanha.py", line 7, in <module>
       turmas = turmas + 1
       ^^^^^^
   KeyboardInterrupt
   ```

   A mensagem diz em que linha ia o programa quando o paraste, e não aponta um erro. O erro é a linha que falta.

3. Tira o `#` que puseste, guarda e corre com 15 e -1, para confirmares que o programa volta a terminar. O que deves ver: `Turmas que entregaram: 1`.

### Paragem 2

Sabes reconhecer um ciclo infinito e pará-lo.

Pensa antes de continuares: e se, com a linha 9 em comentário, escrevesses logo -1? A resposta: o ciclo dava zero voltas, e o programa terminava com `Turmas que entregaram: 0`.

## Fase 3: O contador e o acumulador

O programa passa a somar os quilos. A variável `turmas` conta, e um acumulador soma o valor de cada volta. Rever: [O contador e o acumulador](../04-ciclos-while-e-for.md#o-contador-e-o-acumulador).

1. O acumulador nasce antes do ciclo, com 0. A seguir à linha `turmas = 0`, acrescenta:

   ```python
   total_quilos = 0
   ```

2. Cada volta soma os quilos da turma, antes de ler os da seguinte. A seguir à linha `turmas = turmas + 1`, acrescenta, com quatro espaços:

   ```python
       total_quilos = total_quilos + quilos
   ```

3. No fim do ficheiro, acrescenta:

   ```python
   print("Total:", total_quilos, "kg")
   ```

   Guarda e corre com 12, 0, 9 e -1. O que deves ver no fim: `Turmas que entregaram: 3` e `Total: 21 kg`.

### Paragem 3

O `campanha.py` conta as turmas e soma os quilos.

Pensa antes de continuares: porque é que a soma vem antes da leitura seguinte? A resposta: tem de usar os quilos desta volta, e não os da próxima.

## Fase 4: Ver as voltas com linhas de observação

Prevês a tabela de iterações e confirma-la no computador. As linhas de observação são `print` provisórios, que mostram as variáveis. Rever: [Ver as voltas com linhas de observação](../04-ciclos-while-e-for.md#ver-as-voltas-com-linhas-de-observação).

1. Antes de correres, prevê a tabela de iterações para 12, 0, 9 e -1. Tem uma linha por cada teste da condição, com o valor das variáveis nesse momento. A resposta:

   | Teste | `quilos` | `turmas` | `total_quilos` | Condição |
   | --- | ---: | ---: | ---: | --- |
   | 1.º | 12 | 0 | 0 | `12 != -1` dá `True` |
   | 2.º | 0 | 1 | 12 | `0 != -1` dá `True` |
   | 3.º | 9 | 2 | 12 | `9 != -1` dá `True` |
   | 4.º | -1 | 3 | 21 | `-1 != -1` dá `False` |

2. Logo a seguir à linha do `while`, acrescenta, com quatro espaços:

   ```python
       # Linha de observação: tira-a quando acabares de ver as voltas.
       print("(observação) quilos =", quilos, "turmas =", turmas, "total =", total_quilos)
   ```

3. Logo a seguir ao ciclo, antes do primeiro `print` do resultado, encostado à margem, acrescenta:

   ```python
   # Linha de observação: o estado no teste que deu False.
   print("(observação) quilos =", quilos, "turmas =", turmas, "total =", total_quilos)
   ```

4. Guarda, corre e escreve 12, 0, 9 e -1. O que deves ver:

   ```text
   Quilos entregues pela turma (-1 para terminar)? 12
   (observação) quilos = 12 turmas = 0 total = 0
   Quilos entregues pela turma (-1 para terminar)? 0
   (observação) quilos = 0 turmas = 1 total = 12
   Quilos entregues pela turma (-1 para terminar)? 9
   (observação) quilos = 9 turmas = 2 total = 12
   Quilos entregues pela turma (-1 para terminar)? -1
   (observação) quilos = -1 turmas = 3 total = 21
   Turmas que entregaram: 3
   Total: 21 kg
   ```

   As quatro linhas de observação são a tabela observada. Compara-as com as da tabela prevista.

5. Provoca um erro: apaga a linha `total_quilos = 0`. Põe o cursor no fim da linha do `while`, carrega em Enter e escreve-a na linha nova, com quatro espaços. Guarda, corre e escreve os mesmos valores.

   O que deves ver: `Total: 9 kg`, e não 21, sem nenhuma mensagem de erro. As linhas de observação mostram o total a voltar a 0 no início de cada volta. Dentro do ciclo, a linha apaga a soma das voltas anteriores. Apaga-a e volta a escrevê-la a seguir a `turmas = 0`, encostada à margem.

6. Apaga as duas linhas de observação e os seus comentários. Guarda e corre com 12, 0, 9 e -1, para confirmares `Total: 21 kg`.

### Paragem 4

As linhas de observação já saíram, e a tabela observada coincidiu com a prevista.

Pensa antes de continuares: com o acumulador dentro do ciclo, o caso 15, -1 dava o total certo. Porquê? A resposta: com uma só volta, o último valor é também a soma. É por isso que se testam várias voltas.

## Fase 5: A média, só quando há valores

O programa passa a mostrar a média, só quando há turmas. Com zero turmas, a conta seria 0 a dividir por 0. Rever: [A média, só quando há valores](../04-ciclos-while-e-for.md#a-média-só-quando-há-valores).

1. No fim do ficheiro, acrescenta, com a indentação que mostram:

   ```python
   # Sem este if, com zero turmas, a conta seria 0 / 0 e o programa parava.
   if turmas > 0:
       media = total_quilos / turmas
       print("Média por turma:", media, "kg")
   else:
       print("Não houve entregas, por isso não há média.")
   ```

2. Antes de correres, prevê como aparece a média de 21 quilos por 3 turmas. Guarda e corre com cada linha desta tabela:

   | Valores escritos | A última linha do ecrã |
   | --- | --- |
   | 12, 0, 9, -1 | `Média por turma: 7.0 kg` |
   | 15, -1 | `Média por turma: 15.0 kg` |
   | -1 | `Não houve entregas, por isso não há média.` |

   O que deves ver: em cada caso, a linha da tabela. A média é `7.0`, porque a divisão com `/` dá sempre um `float`.

### Paragem 5

O `campanha.py` está completo.

O ficheiro `campanha.py` completo, como deve estar agora:

```python
# campanha.py: a campanha de recolha de alimentos da escola.
SENTINELA = -1

turmas = 0
total_quilos = 0
quilos = int(input("Quilos entregues pela turma (-1 para terminar)? "))
while quilos != SENTINELA:
    turmas = turmas + 1
    total_quilos = total_quilos + quilos
    # Ler o valor seguinte é a atualização: sem esta linha, o ciclo nunca acabava.
    quilos = int(input("Quilos entregues pela turma (-1 para terminar)? "))
print("Turmas que entregaram:", turmas)
print("Total:", total_quilos, "kg")
# Sem este if, com zero turmas, a conta seria 0 / 0 e o programa parava.
if turmas > 0:
    media = total_quilos / turmas
    print("Média por turma:", media, "kg")
else:
    print("Não houve entregas, por isso não há média.")
```

O ciclo trata uma turma de cada vez, e o que vem depois dele usa a contagem completa.

Pensa antes de continuares: porque é que o `if` não pode ficar dentro do ciclo? A resposta: calculava e escrevia uma média em cada volta, com a contagem a meio.

## Fase 6: Contar voltas com `for` e `range`

O 10.º ano tem 6 turmas, e já se sabe que o ciclo vai dar 6 voltas. É o `Para` do pseudocódigo, o `for` do Python, e `range(1, 7)` dá de 1 a 6, porque o fim não entra. Rever: [Contar voltas com `for` e `range`](../04-ciclos-while-e-for.md#contar-voltas-com-for-e-range).

1. Cria um ficheiro novo, `campanha_10ano.py`, com esta primeira versão:

   ```python
   # campanha_10ano.py: os quilos das 6 turmas do 10.º ano, no fim da campanha.
   NUMERO_DE_TURMAS = 6

   total_quilos = 0
   # O fim do range não entra: para ir da turma 1 à turma 6, o fim tem de ser 7.
   for turma in range(1, NUMERO_DE_TURMAS + 1):
       quilos = int(input("Quilos da turma " + str(turma) + "? "))
       total_quilos = total_quilos + quilos
   print("Total do 10.º ano:", total_quilos, "kg")
   # A média por turma divide o total pelas 6 turmas.
   media = total_quilos / NUMERO_DE_TURMAS
   print("Média por turma:", media, "kg")
   ```

2. Guarda, corre com `python campanha_10ano.py` e escreve 12, 0, 9, 15, 6 e 18. O que deves ver:

   ```text
   Quilos da turma 1? 12
   Quilos da turma 2? 0
   Quilos da turma 3? 9
   Quilos da turma 4? 15
   Quilos da turma 5? 6
   Quilos da turma 6? 18
   Total do 10.º ano: 60 kg
   Média por turma: 10.0 kg
   ```

3. Provoca um erro: na linha do `for`, tira o `+ 1`. Guarda, corre e escreve 12, 0, 9, 15 e 6.

   O que deves ver: só 5 perguntas, `Total do 10.º ano: 42 kg` e `Média por turma: 7.0 kg`, sem nenhuma mensagem de erro. O `range(1, 6)` para antes do 6, e a turma 6 ficou de fora. Volta a pôr o `+ 1` e guarda.

### Paragem 6

O `campanha_10ano.py` pede os quilos das 6 turmas e mostra o total e a média.

Pensa antes de continuares: porque é que esta média não precisa de um `if`? A resposta: o número de turmas é sempre 6, e a divisão nunca é por zero.

## Fase 7: As duas formas do `Para` e o `range`

Experimentas a forma do `Para` que começa em 0 e vês porque é que aqui não serve. O `range(6)` é o mesmo que `range(0, 6)`. Rever: [As duas formas do `Para` e o `range`](../04-ciclos-while-e-for.md#as-duas-formas-do-para-e-o-range).

1. Muda a linha do `for` para `for turma in range(NUMERO_DE_TURMAS):`. Antes de correres, prevê o número da primeira e da última pergunta. Guarda, corre e responde com 12, 0, 9, 15, 6 e 18.

   O que deves ver: de `Quilos da turma 0?` até `Quilos da turma 5?`. Dá 6 voltas, mas na escola não há turma 0.

2. Volta a pôr a linha `for turma in range(1, NUMERO_DE_TURMAS + 1):`, guarda, corre com os mesmos valores e confirma que as perguntas vão de 1 a 6.

### Paragem 7

O programa voltou a perguntar as turmas de 1 a 6.

Pensa antes de continuares: quantas voltas dá `range(2, 7)`? A resposta: 5, porque 7 menos 2 são 5.

## Fase 8: Contar só algumas voltas

O programa passa a contar as turmas que chegaram à meta de 10 kg. Este contador só aumenta nas voltas em que a condição do `if` dá `True`. Rever: [Contar só algumas voltas](../04-ciclos-while-e-for.md#contar-só-algumas-voltas).

1. Põe o cursor no fim da linha `NUMERO_DE_TURMAS = 6` e carrega em Enter. Na linha nova, escreve:

   ```python
   META = 10
   ```

2. O contador nasce antes do ciclo. A seguir à linha `total_quilos = 0`, acrescenta:

   ```python
   na_meta = 0
   ```

3. No corpo do `for`, a seguir à soma, acrescenta estas linhas, com a indentação que mostram:

   ```python
       # Dentro do if, o contador só aumenta nas voltas em que a turma chegou à meta.
       if quilos >= META:
           na_meta = na_meta + 1
   ```

4. No fim do ficheiro, acrescenta:

   ```python
   print("Turmas que chegaram à meta:", na_meta)
   ```

   Guarda, corre e escreve 12, 0, 9, 15, 6 e 18. O que deves ver no fim: `Turmas que chegaram à meta: 3`, as turmas 1, 4 e 6.

5. Antes de correres, prevê o resultado com 10, 9, 10, 11, 0 e 20: uma turma com 10 kg exatos chegou à meta? Corre.

   O que deves ver: `Turmas que chegaram à meta: 4`. As duas turmas com 10 kg contam, porque a condição usa `>=`.

6. Provoca um erro: muda a condição para `quilos > META`. Guarda e corre com 12, 0, 9, 15, 6 e 18, e depois com 10, 9, 10, 11, 0 e 20.

   O que deves ver: no primeiro caso, 3, igual ao de antes. No segundo, 2, quando deviam ser 4. Só o caso com o 10 apanhou o erro. Volta a pôr o `>=` e guarda.

### Paragem 8

O `campanha_10ano.py` conta as turmas que chegaram à meta.

O ficheiro `campanha_10ano.py` completo, como deve estar agora:

```python
# campanha_10ano.py: os quilos das 6 turmas do 10.º ano, no fim da campanha.
NUMERO_DE_TURMAS = 6
META = 10

total_quilos = 0
na_meta = 0
# O fim do range não entra: para ir da turma 1 à turma 6, o fim tem de ser 7.
for turma in range(1, NUMERO_DE_TURMAS + 1):
    quilos = int(input("Quilos da turma " + str(turma) + "? "))
    total_quilos = total_quilos + quilos
    # Dentro do if, o contador só aumenta nas voltas em que a turma chegou à meta.
    if quilos >= META:
        na_meta = na_meta + 1
print("Total do 10.º ano:", total_quilos, "kg")
# A média por turma divide o total pelas 6 turmas.
media = total_quilos / NUMERO_DE_TURMAS
print("Média por turma:", media, "kg")
print("Turmas que chegaram à meta:", na_meta)
```

O corpo do `for` lê, soma e, só às vezes, conta. Depois do ciclo, o programa escreve o que acumulou.

Pensa antes de continuares: se a linha do aumento ficasse com quatro espaços, alinhada com o `if`, o que acontecia? A resposta: o `if` ficava sem nenhuma linha dentro, e o Python recusava o programa com `IndentationError`.

## Fase 9, opcional: A validação repetida pede o valor outra vez

O programa passa a recusar quilos negativos, com um `while` dentro do `for`. Em cada volta do `for`, o `while` pergunta outra vez até o valor ser válido. Rever: [A validação repetida pede o valor outra vez](../04-ciclos-while-e-for.md#a-validação-repetida-pede-o-valor-outra-vez).

1. Logo a seguir à linha do `input` que está dentro do `for`, acrescenta, com a indentação que mostram:

   ```python
       # Validação repetida: um número negativo é um engano, e a pergunta repete-se.
       while quilos < 0:
           quilos = int(input("Não pode ser negativo. Quilos da turma " + str(turma) + "? "))
   ```

2. Guarda, corre e escreve 12, -5, 0, 9, 15, 6 e 18. O que deves ver:

   ```text
   Quilos da turma 1? 12
   Quilos da turma 2? -5
   Não pode ser negativo. Quilos da turma 2? 0
   Quilos da turma 3? 9
   Quilos da turma 4? 15
   Quilos da turma 5? 6
   Quilos da turma 6? 18
   Total do 10.º ano: 60 kg
   Média por turma: 10.0 kg
   Turmas que chegaram à meta: 3
   ```

   O -5 foi recusado, e a pergunta repetida não conta como turma nova. Neste programa, o -1 também seria recusado: não é sentinela.

### Paragem 9

O `campanha_10ano.py` recusa os negativos.

O ficheiro `campanha_10ano.py` completo, como deve estar agora:

```python
# campanha_10ano.py: os quilos das 6 turmas do 10.º ano, no fim da campanha.
NUMERO_DE_TURMAS = 6
META = 10

total_quilos = 0
na_meta = 0
# O fim do range não entra: para ir da turma 1 à turma 6, o fim tem de ser 7.
for turma in range(1, NUMERO_DE_TURMAS + 1):
    quilos = int(input("Quilos da turma " + str(turma) + "? "))
    # Validação repetida: um número negativo é um engano, e a pergunta repete-se.
    while quilos < 0:
        quilos = int(input("Não pode ser negativo. Quilos da turma " + str(turma) + "? "))
    total_quilos = total_quilos + quilos
    # Dentro do if, o contador só aumenta nas voltas em que a turma chegou à meta.
    if quilos >= META:
        na_meta = na_meta + 1
print("Total do 10.º ano:", total_quilos, "kg")
# A média por turma divide o total pelas 6 turmas.
media = total_quilos / NUMERO_DE_TURMAS
print("Média por turma:", media, "kg")
print("Turmas que chegaram à meta:", na_meta)
```

O `while` fica dentro do `for`, antes da soma, e por isso só um valor válido chega às contas.

Pensa antes de continuares: o que acontecia se o `while` ficasse depois da soma? A resposta: o -5 era somado antes de ser recusado, e o total dava 55.

## Se alguma coisa falhar

1. Guardaste o ficheiro? O Python corre o que está no disco, e não o que vês no ecrã.
2. Estás na pasta certa? No terminal, o texto antes do cursor tem de ter `fp-python` no fim, antes do `>` ou do `%`.
3. Estás na consola do Python sem quereres? Se a linha começa por `>>>`, escreve `exit()` e carrega em Enter.

### O programa não termina

Olha para o cursor. À frente de uma pergunta, o programa está à espera da tua resposta. Numa linha vazia, ou com o ecrã a encher-se com a mesma linha, é um ciclo infinito. Clica no terminal, carrega em Ctrl+C e procura a atualização que falta.

### `SyntaxError: expected ':'`

Faltam os dois pontos no fim da linha do `while`, do `for`, do `if` ou do `else`.

### `IndentationError: expected an indented block after ...`

A linha a seguir aos dois pontos tem de ficar quatro espaços mais para dentro do que a linha dos dois pontos.

### `IndentationError: unexpected indent`

Uma linha acima desta ficou encostada à margem. Compara as margens com as da última paragem.

### `ValueError: invalid literal for int() with base 10`

Carregaste em Enter sem escrever nada, escreveste uma letra ou um número com casas decimais. Corre outra vez e escreve só números inteiros.

### Escrevo -1 e o programa continua a perguntar

Falta o `int` na leitura do fim do corpo do `while`. O -1 fica guardado como texto, e um texto nunca é igual a um número.

### `TypeError: unsupported operand type(s) for +: 'int' and 'str'`

Numa das leituras, falta o `int`. A mensagem aponta a linha da soma, mas a causa está na leitura.

### `ZeroDivisionError: division by zero`

A divisão da média não está dentro do `if turmas > 0:`.

### O resultado está errado e não aparece nenhuma mensagem

Acrescenta linhas de observação e compara a tabela observada com a prevista, linha a linha.

## Desafios

Faz cada desafio num ficheiro novo, como `desafio_1.py`, com o código do programa copiado para lá. Calcula os casos à mão antes de correres.

1. No `campanha.py`, conta também as turmas que não trouxeram nada, e escreve o número delas depois de `Turmas que entregaram`. Testa com 12, 0, 9, -1, que deve dar 1, e com um caso só de turmas sem nada. Rever: [Contar só algumas voltas](../04-ciclos-while-e-for.md#contar-só-algumas-voltas).
2. No `campanha_10ano.py`, pergunta primeiro quantas turmas tem o 10.º ano, e aceita só um número de 1 a 10. Depois pede os quilos de cada uma. Testa com 0, 11 e 1, e com 6 e 12, 0, 9, 15, 6 e 18. Pista: o número lido vai para o `range` e para a divisão da média. A média precisa do `if`? Rever: [A validação repetida pede o valor outra vez](../04-ciclos-while-e-for.md#a-validação-repetida-pede-o-valor-outra-vez).
3. No `campanha.py`, não aceites quilos negativos, exceto o -1, que continua a ser a sentinela. Com 12, -5, 0, 9 e -1, o programa recusa o -5, pergunta outra vez, e no fim mostra 3 turmas e 21 kg. Pista: há duas leituras, e as duas têm de ser validadas. Que condição é verdadeira para o -5 e falsa para o -1? Rever: [A validação repetida pede o valor outra vez](../04-ciclos-while-e-for.md#a-validação-repetida-pede-o-valor-outra-vez).

## Antes de terminares

- [ ] O `campanha.py` dá o resultado certo nos três casos: -1; 15 e -1; 12, 0, 9 e -1.
- [ ] O `campanha_10ano.py` pergunta as turmas de 1 a 6. Com 12, 0, 9, 15, 6 e 18, dá 60 kg, 10.0 kg e 3 turmas na meta.
- [ ] As linhas de observação já saíram do `campanha.py`.

![Rodapé](../../imagens/rodape.png)
