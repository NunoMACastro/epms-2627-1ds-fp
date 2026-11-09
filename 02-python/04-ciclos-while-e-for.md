![Cabeçalho](../imagens/cabecalho.png)

# Ciclos while e for

Neste guia, passas para Python os ciclos do pseudocódigo, o `Enquanto` e o `Para`, e é o computador que dá as voltas. Vês o `while`, a sentinela, o contador e o acumulador, e o `for` com `range`.

Usa os ciclos da algoritmia. Rever: [Enquanto](../01-algoritmos/04-repeticao-e-arrays.md#enquanto-repetir-enquanto-a-condição-for-verdadeira), [Para: o ciclo contado](../01-algoritmos/04-repeticao-e-arrays.md#para-o-ciclo-contado), [Contadores e acumuladores](../01-algoritmos/04-repeticao-e-arrays.md#contadores-e-acumuladores) e [A sentinela](../01-algoritmos/04-repeticao-e-arrays.md#a-sentinela-ler-até-aparecer-o-valor-que-diz-acabou). Para praticar: [laboratório](laboratorios/04-ciclos-while-e-for-laboratorio.md) e [ficha de exercícios](exercicios/04-ciclos-while-e-for-exercicios.md).

## Neste guia

1. [Repetir com `while`](#repetir-com-while)
2. [As três peças de um ciclo](#as-três-peças-de-um-ciclo)
3. [Ver as voltas com linhas de observação](#ver-as-voltas-com-linhas-de-observação)
4. [O ciclo que nunca acaba, e o Ctrl+C](#o-ciclo-que-nunca-acaba-e-o-ctrlc)
5. [A validação repetida pede o valor outra vez](#a-validação-repetida-pede-o-valor-outra-vez)
6. [Ler até à sentinela](#ler-até-à-sentinela)
7. [O contador e o acumulador](#o-contador-e-o-acumulador)
8. [Contar só algumas voltas](#contar-só-algumas-voltas)
9. [A média, só quando há valores](#a-média-só-quando-há-valores)
10. [Contar voltas com `for` e `range`](#contar-voltas-com-for-e-range)
11. [As duas formas do `Para` e o `range`](#as-duas-formas-do-para-e-o-range)
12. [Um `for` com um número lido do teclado](#um-for-com-um-número-lido-do-teclado)
13. [Escolher entre `while` e `for`](#escolher-entre-while-e-for)
14. [Exemplo guiado: a tabuada à escolha](#exemplo-guiado-a-tabuada-à-escolha)

## Repetir com `while`

Para escrever a tabuada do 7, precisavas de uma linha por cada multiplicação. Um ciclo repete as mesmas instruções, e o `while` é o `Enquanto` do pseudocódigo: repete o corpo enquanto a condição for verdadeira. A linha acaba em dois pontos, como a de um `if`, e o corpo fica quatro espaços para dentro.

```python
# tabuada_while.py: escreve a tabuada do 7, de 7 x 1 a 7 x 3, com um ciclo while.
NUMERO = 7
ULTIMO = 3

vezes = 1
while vezes <= ULTIMO:
    print(NUMERO, "x", vezes, "=", NUMERO * vezes)
    vezes = vezes + 1
print("Fim da tabuada")
```

```text
7 x 1 = 7
7 x 2 = 14
7 x 3 = 21
Fim da tabuada
```

A tabela de iterações mostra as voltas, com uma linha por cada teste da condição.

| Teste | `vezes` | Condição | Durante a volta |
| --- | ---: | --- | --- |
| 1.º | 1 | `1 <= 3` dá `True` | escreve `7 x 1 = 7` |
| 2.º | 2 | `2 <= 3` dá `True` | escreve `7 x 2 = 14` |
| 3.º | 3 | `3 <= 3` dá `True` | escreve `7 x 3 = 21` |
| 4.º | 4 | `4 <= 3` dá `False` | o ciclo termina |

Depois da última linha do corpo, o Python não continua para baixo: volta à linha do `while` e testa outra vez a condição. Podes pensar no `while` como um `if` que, quando acaba o seu bloco, volta a perguntar. A primeira linha que volta à margem já está fora do ciclo, e só se executa quando ele termina.

## As três peças de um ciclo

Um ciclo que termina tem as três peças do pseudocódigo, e quando falha é quase sempre numa delas.

| Peça | O que faz | Na tabuada |
| --- | --- | --- |
| Inicialização | dá o valor inicial, antes do ciclo | `vezes = 1` |
| Condição | diz em que situação se continua | `vezes <= ULTIMO` |
| Atualização | muda a variável e aproxima o fim | `vezes = vezes + 1` |

A atualização escreve-se sempre por extenso: o `vezes++` do pseudocódigo não existe em Python.

Se a condição der `False` logo no primeiro teste, o ciclo dá zero voltas. Às vezes é um erro. Com `while vezes > ULTIMO:`, aparece só `Fim da tabuada`, porque `1 > 3` dá `False`. Quem pensa em quando o ciclo deve parar, e não em quando deve continuar, escreve a condição ao contrário. Outras vezes é o que deve acontecer: um dia sem vendas não dá nenhuma volta, e a resposta certa é 0. Por isso, testa sempre zero voltas, uma volta e várias voltas.

## Ver as voltas com linhas de observação

Na algoritmia, eras tu que davas as voltas, e sabias o valor de cada variável. Agora é o computador, e as variáveis ficam escondidas. Se o ciclo der uma volta a mais, como sabes?

Antes de correres, fazes de cabeça a tabela de iterações, a tabela prevista. Depois, pões o programa a mostrar as variáveis, com **linhas de observação**. Cada uma é um `print` provisório, que começa por "(observação)" e que tiras quando acabares de ver. Põe-se uma no início do corpo e outra logo a seguir ao ciclo.

Antes de leres o resultado, prevê que valor de `vezes` mostra a última linha de observação.

```python
# tabuada_observar.py: a tabuada do 7 até 7 x 3, com linhas de observação.
NUMERO = 7
ULTIMO = 3

vezes = 1
while vezes <= ULTIMO:
    # Linha de observação: mostra o valor de vezes no início de cada volta.
    print("(observação) vezes =", vezes)
    print(NUMERO, "x", vezes, "=", NUMERO * vezes)
    vezes = vezes + 1
# Linha de observação: mostra o valor com que o ciclo terminou.
print("(observação) depois do ciclo, vezes =", vezes)
print("Fim da tabuada")
```

```text
(observação) vezes = 1
7 x 1 = 7
(observação) vezes = 2
7 x 2 = 14
(observação) vezes = 3
7 x 3 = 21
(observação) depois do ciclo, vezes = 4
Fim da tabuada
```

A última linha mostra 4, e não 3: o ciclo só para quando `vezes` passa o limite. As quatro linhas de observação são a **tabela observada**: a mesma tabela, feita pelo computador. Compara-as com a prevista, linha a linha. A primeira linha diferente diz-te em que volta o programa se afastou do que esperavas.

## O ciclo que nunca acaba, e o Ctrl+C

Sem a linha `vezes = vezes + 1`, a variável vale sempre 1, e a condição dá sempre `True`. É um ciclo infinito: o ecrã enche-se de linhas iguais, e "Fim da tabuada" nunca aparece.

Para parar o programa, clica no terminal e carrega em Ctrl+C. No macOS também é Ctrl+C, com a tecla Control, e não com a Cmd. O fim do ecrã fica parecido com isto:

```text
7 x 1 = 7
7 x 1 = 7
Traceback (most recent call last):
  File "C:\Users\aluno\Documents\fp-python\tabuada_infinita.py", line 7, in <module>
    print(NUMERO, "x", vezes, "=", NUMERO * vezes)
    ~~~~~^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
KeyboardInterrupt
```

`KeyboardInterrupt` quer dizer "interrupção pelo teclado": foste tu que paraste o programa. A mensagem não aponta um erro, e só diz onde o programa ia. Depois, procura a peça que falha: o que muda em cada volta, e essa mudança aproxima o fim?

Se o programa parecer parado, olha para o cursor. À frente de uma pergunta, o programa está à espera da tua resposta. Numa linha vazia, por baixo de uma pergunta já respondida, é um ciclo que não escreve nada: para-o com Ctrl+C.

## A validação repetida pede o valor outra vez

No tema anterior, um valor inválido fazia o programa avisar e acabar. Com um ciclo, o programa pede o valor outra vez, até ele ser válido. Cada `Escreve:` e `ler valor` do pseudocódigo junta-se num `input`, e o aviso passa a ser a própria pergunta.

```python
# validar_nota.py: pede a nota de um teste até ela estar na escala de 0 a 20.
NOTA_MINIMA = 0
NOTA_MAXIMA = 20

nota = int(input("Nota do teste (inteiro de 0 a 20)? "))
while nota < NOTA_MINIMA or nota > NOTA_MAXIMA:
    # A atualização: lê um valor novo, que o while volta a testar.
    nota = int(input("Nota inválida. Escreve um inteiro de 0 a 20: "))
print("Nota aceite:", nota)
```

```text
Nota do teste (inteiro de 0 a 20)? 25
Nota inválida. Escreve um inteiro de 0 a 20: -3
Nota inválida. Escreve um inteiro de 0 a 20: 14
Nota aceite: 14
```

A primeira leitura é a inicialização, e a leitura do corpo é a atualização. Quando o programa chega ao `print`, a condição acabou de dar `False`, e por isso a nota está de certeza entre 0 e 20. Se a pessoa escrever logo 14, o ciclo dá zero voltas.

Para testar, usa um valor válido à primeira e valores inválidos dos dois lados. Usa também as fronteiras: o 0 e o 20 são aceites, e o -1 e o 21 recusados.

As duas leituras levam o `int`. Se te esqueceres dele na leitura do corpo, o primeiro valor inválido faz o corpo guardar um texto, e o programa para com `TypeError: '<' not supported between instances of 'str' and 'int'`. Quer dizer que o `<` não funciona entre um texto e um número. A mensagem aponta a linha do `while`, mas a causa está na leitura do corpo.

<details>
<summary>Para ires mais longe: um ciclo dentro de outro</summary>

Uma validação repetida pode ficar dentro do corpo de outro ciclo, como no projeto 2 da algoritmia. O `while` da validação fica indentado no corpo do ciclo de fora, e o corpo dele fica com oito espaços. Em cada volta do ciclo de fora, o de dentro dá todas as suas voltas.

</details>

## Ler até à sentinela

A bilheteira de um cinema regista os bilhetes de cada venda, e quando o ciclo começa ninguém sabe quantas vendas vão ser. Combina-se um valor que quer dizer "acabou", a sentinela, que nenhum dado verdadeiro pode ter. Nenhuma venda tem 0 bilhetes, e por isso o 0 serve.

Lê-se o primeiro valor antes do ciclo. A condição é "o valor não é a sentinela", com `!=`. O corpo trata o valor e, na última linha, lê o seguinte.

```python
# bilheteira.py: conta as vendas da bilheteira de um cinema até aparecer a sentinela 0.
SENTINELA = 0

vendas = 0
bilhetes_da_venda = int(input("Bilhetes desta venda (0 para terminar)? "))
while bilhetes_da_venda != SENTINELA:
    vendas = vendas + 1
    # Ler o valor seguinte é a atualização do ciclo, e fica no fim do corpo.
    bilhetes_da_venda = int(input("Bilhetes desta venda (0 para terminar)? "))
print("Vendas:", vendas)
```

```text
Bilhetes desta venda (0 para terminar)? 2
Bilhetes desta venda (0 para terminar)? 4
Bilhetes desta venda (0 para terminar)? 1
Bilhetes desta venda (0 para terminar)? 0
Vendas: 3
```

O valor lido vai sempre direto para o teste do `while`. A sentinela faz a condição dar `False` sem ser contada. Com o 0 logo à primeira, o ciclo dá zero voltas e escreve `Vendas: 0`.

O erro típico é ler no princípio do corpo. Como a condição precisa de um valor, inventa-se um para entrar no ciclo, como `bilhetes_da_venda = 1`. Com os mesmos valores, o programa conta 4 vendas, porque conta o 0 antes de o testar. Um valor inventado que não vem de lado nenhum é um sinal de alarme.

## O contador e o acumulador

A variável `vendas` é um contador: começa em 0, antes do ciclo, e aumenta 1 em cada volta. Falta saber quantos bilhetes se venderam, e para isso é preciso um acumulador, que soma o valor de cada volta.

```python
# bilheteira_total.py: conta as vendas e soma os bilhetes, até aparecer a sentinela 0.
SENTINELA = 0

vendas = 0
bilhetes = 0
bilhetes_da_venda = int(input("Bilhetes desta venda (0 para terminar)? "))
while bilhetes_da_venda != SENTINELA:
    vendas = vendas + 1
    bilhetes = bilhetes + bilhetes_da_venda
    bilhetes_da_venda = int(input("Bilhetes desta venda (0 para terminar)? "))
print("Vendas:", vendas)
print("Bilhetes vendidos:", bilhetes)
```

Com 2, 4, 1 e o 0, o fim do ecrã é `Vendas: 3` e `Bilhetes vendidos: 7`. A tabela não mostra as perguntas do `input`.

| Teste | `bilhetes_da_venda` | `vendas` | `bilhetes` | Condição | Durante a volta |
| --- | ---: | ---: | ---: | --- | --- |
| 1.º | 2 | 0 | 0 | `2 != 0` dá `True` | conta, soma 2 e lê 4 |
| 2.º | 4 | 1 | 2 | `4 != 0` dá `True` | conta, soma 4 e lê 1 |
| 3.º | 1 | 2 | 6 | `1 != 0` dá `True` | conta, soma 1 e lê 0 |
| 4.º | 0 | 3 | 7 | `0 != 0` dá `False` | o ciclo termina |

O contador soma sempre 1, e o acumulador soma o próprio valor. Os dois começam antes do ciclo. Se `bilhetes = 0` passar para dentro do corpo, o total recomeça em cada volta, e o programa escreve `Bilhetes vendidos: 1`.

## Contar só algumas voltas

O cinema quer saber quantas vendas foram de grupo, com 4 bilhetes ou mais. A linha que aumenta o contador vai para dentro de um `if`, com oito espaços. Só se executa nas voltas em que a condição dá `True`.

```python
# bilheteira_grupos.py: conta as vendas, as vendas de grupo e os bilhetes, até à sentinela 0.
SENTINELA = 0
GRUPO = 4

vendas = 0
vendas_de_grupo = 0
bilhetes = 0
bilhetes_da_venda = int(input("Bilhetes desta venda (0 para terminar)? "))
while bilhetes_da_venda != SENTINELA:
    vendas = vendas + 1
    bilhetes = bilhetes + bilhetes_da_venda
    # Uma venda de grupo tem GRUPO bilhetes ou mais.
    if bilhetes_da_venda >= GRUPO:
        vendas_de_grupo = vendas_de_grupo + 1
    bilhetes_da_venda = int(input("Bilhetes desta venda (0 para terminar)? "))
print("Vendas:", vendas)
print("Vendas de grupo:", vendas_de_grupo)
print("Bilhetes vendidos:", bilhetes)
```

Com 2, 4, 1, 6 e o 0, aparecem `Vendas: 4`, `Vendas de grupo: 2` e `Bilhetes vendidos: 13`. A venda de 4 conta, porque a condição usa `>=`. A leitura do valor seguinte fica com quatro espaços. Se ficasse dentro do `if`, numa venda que não é de grupo não se lia nenhum valor novo, e o ciclo nunca acabava.

## A média, só quando há valores

Com um contador e um acumulador, calcula-se uma média. Num dia sem vendas, os dois ficam a 0, e a conta seria 0 a dividir por 0. Por isso, a conta fica dentro de um `if`, depois do ciclo.

```python
# bilheteira_media.py: conta as vendas e os bilhetes até à sentinela 0, e mostra a média.
SENTINELA = 0

vendas = 0
bilhetes = 0
bilhetes_da_venda = int(input("Bilhetes desta venda (0 para terminar)? "))
while bilhetes_da_venda != SENTINELA:
    vendas = vendas + 1
    bilhetes = bilhetes + bilhetes_da_venda
    bilhetes_da_venda = int(input("Bilhetes desta venda (0 para terminar)? "))
print("Vendas:", vendas)
print("Bilhetes vendidos:", bilhetes)
# Sem este if, num dia sem vendas a conta seria 0 / 0, e o programa parava.
if vendas > 0:
    media = bilhetes / vendas
    print("Bilhetes por venda, em média:", media)
else:
    print("Não houve vendas, por isso não há média.")
```

Com 2, 4, 3 e o 0, a média é `3.0`. Com o 0 logo à primeira, aparece a mensagem de não haver vendas, sem chegar à divisão. O `if` está na margem, depois do ciclo, e por isso avalia-se uma vez, com a contagem completa.

## Contar voltas com `for` e `range`

Na tabuada, sabe-se antes de começar quantas voltas vai haver. Com o `while`, escreves as três peças à mão, com três oportunidades de errar. O `Para` do pseudocódigo passa a `for`, com o **`range`**, uma função que produz uma sequência de inteiros: `range(1, 4)` dá 1, 2 e 3. O primeiro número entra, e o segundo não entra.

```python
# tabuada_for.py: escreve a tabuada do 7, de 7 x 1 a 7 x 3, com um ciclo for.
NUMERO = 7
ULTIMO = 3

for vezes in range(1, ULTIMO + 1):
    print(NUMERO, "x", vezes, "=", NUMERO * vezes)
print("Fim da tabuada")
```

O ecrã é igual ao do `while`. O `+ 1` está lá porque o fim do `range` não entra, e o "até ULTIMO" do pseudocódigo inclui o 3.

Em cada volta, `vezes` recebe o número seguinte do `range`. O `in` quer dizer "em", como no `Para cada`. Como não há condição escrita, a tabela tem uma linha por volta, sem o teste final.

| Volta | `vezes` | Durante a volta |
| ---: | ---: | --- |
| 1.ª | 1 | escreve `7 x 1 = 7` |
| 2.ª | 2 | escreve `7 x 2 = 14` |
| 3.ª | 3 | escreve `7 x 3 = 21` |

| Peça | Com `while` | Com `for` |
| --- | --- | --- |
| Inicialização | `vezes = 1` | o início do `range` |
| Condição | `vezes <= ULTIMO` | o fim do `range`, que não entra |
| Atualização | `vezes = vezes + 1` | não se escreve: o `for` passa ao número seguinte |

Num ciclo contado, o `for` é mais seguro, porque não há atualização para esquecer. Depois do ciclo, `vezes` vale 3, e não 4 como no `while`. Com zero voltas, nem chega a existir. Por isso, não se usa depois do ciclo.

O erro típico é esquecer que o fim não entra. Com `range(1, 3)`, a tabuada acaba em `7 x 2 = 14`, sem nenhuma mensagem. Testa sempre a primeira e a última volta.

## As duas formas do `Para` e o `range`

O `Para` tinha duas formas nas aulas, e as duas passam a `range`.

| Pseudocódigo | Python | Valores da variável |
| --- | --- | --- |
| `Para i de 1 até 10` | `for i in range(1, 11):` | 1, 2, ..., 10 |
| `Para i = 0, i < 10, i++` | `for i in range(0, 10):` | 0, 1, ..., 9 |

Quando o `range` começa em 0, pode escrever-se só com o fim, e `range(10)` é o mesmo que `range(0, 10)`. Com o fim maior do que o início, o número de voltas é `fim - início`.

| `range` | Valores | Voltas |
| --- | --- | ---: |
| `range(1, 5)` | 1, 2, 3, 4 | 4 |
| `range(5)` | 0, 1, 2, 3, 4 | 5 |
| `range(3, 3)` | nenhum | 0 |

O nome `i` é a escolha habitual quando a variável só conta. Quando o número quer dizer alguma coisa, dá-lhe um nome que o diga, como `vezes` ou `ronda`.

## Um `for` com um número lido do teclado

Num ciclo contado, basta saber o número de voltas quando o ciclo começa. Num jogo, o programa pode perguntar primeiro quantas rondas jogaste.

```python
# rondas.py: pergunta quantas rondas jogaste e soma os pontos de todas.
rondas = int(input("Quantas rondas jogaste? "))
total = 0
for ronda in range(1, rondas + 1):
    pontos = int(input("Pontos da ronda " + str(ronda) + "? "))
    total = total + pontos
print("Total de pontos:", total)
```

```text
Quantas rondas jogaste? 3
Pontos da ronda 1? 12
Pontos da ronda 2? 8
Pontos da ronda 3? 15
Total de pontos: 35
```

O `input` só aceita um texto entre os parênteses, e por isso aqui não dá para usar vírgulas, como no `print`. O número junta-se com `str` e `+`, como no tema 02. Com 0 rondas, o `range(1, 1)` não dá nenhum número, e o total fica a 0.

## Escolher entre `while` e `for`

Quando o programa chega ao ciclo, já se sabe quantas voltas vai dar? Se sim, usa-se `for`. Se não, usa-se `while`.

| Situação | Ciclo | Porquê |
| --- | --- | --- |
| Escrever a tabuada do 7, de 1 a 10 | `for` | Sabe-se antes de começar: são 10 |
| Pedir os pontos das rondas, depois de perguntar quantas são | `for` | O número é lido antes do ciclo |
| Ler vendas até aparecer o 0 | `while` | Só se sabe que acabou quando o 0 aparece |
| Pedir uma nota até ela ser válida | `while` | Depende do que a pessoa escrever |

## Exemplo guiado: a tabuada à escolha

### O problema e os casos de teste

O programa pergunta de que número queres a tabuada, de 1 a 10. Se o número estiver fora, escreve "Esse número não dá. Escreve de 1 a 10:" e pergunta outra vez, até ser válido. Depois escreve a tabuada desse número, de N x 1 até N x 10.

Como o programa tem dois ciclos, os casos têm de testar os dois.

| Valores escritos | Perguntas repetidas | Primeira linha | Última linha |
| --- | ---: | --- | --- |
| 7 | 0 | `7 x 1 = 7` | `7 x 10 = 70` |
| 0, 11, 1 | 2 | `1 x 1 = 1` | `1 x 10 = 10` |
| 10 | 0 | `10 x 1 = 10` | `10 x 10 = 100` |

A primeira e a última linha são as que apanham uma volta a mais ou a menos.

### As peças dos dois ciclos

A validação é um `while`, porque não se sabe quantas voltas vai dar. A primeira leitura é a inicialização, a condição é o número estar fora de 1 a 10, e a leitura do corpo é a atualização. A tabuada é um `for`, porque são sempre 10 voltas.

### O programa, parte a parte

Começa-se pela validação:

```python
# tabuada_escolha.py: pede um número de 1 a 10 até ser válido e escreve a tabuada dele.
MINIMO = 1
MAXIMO = 10

numero = int(input("De que número queres a tabuada (1 a 10)? "))
# Validação repetida: enquanto o número estiver fora de 1 a 10, pede outra vez.
while numero < MINIMO or numero > MAXIMO:
    numero = int(input("Esse número não dá. Escreve de 1 a 10: "))
print("Número aceite:", numero)
```

Com 0, 11 e 1, escreve `Número aceite: 1`. A tabuada substitui o `print` do fim, com mais uma constante, `ULTIMO`. O programa completo fica assim:

```python
# tabuada_escolha.py: pede um número de 1 a 10 até ser válido e escreve a tabuada dele.
MINIMO = 1
MAXIMO = 10
ULTIMO = 10

numero = int(input("De que número queres a tabuada (1 a 10)? "))
# Validação repetida: enquanto o número estiver fora de 1 a 10, pede outra vez.
while numero < MINIMO or numero > MAXIMO:
    numero = int(input("Esse número não dá. Escreve de 1 a 10: "))
# Aqui o número está de certeza entre 1 e 10. O fim do range não entra, por isso é ULTIMO + 1.
for vezes in range(1, ULTIMO + 1):
    print(numero, "x", vezes, "=", numero * vezes)
```

### Prever e observar

Para o caso 0, 11, 1, a tabela do `while` prevê três testes.

| Teste | `numero` | Condição | Durante a volta |
| --- | ---: | --- | --- |
| 1.º | 0 | `0 < 1 or 0 > 10` dá `True` | pede outra vez e lê 11 |
| 2.º | 11 | `11 < 1 or 11 > 10` dá `True` | pede outra vez e lê 1 |
| 3.º | 1 | `1 < 1 or 1 > 10` dá `False` | o ciclo termina |

Com uma linha de observação no início do corpo, aparecem duas voltas, com 0 e com 11. O ciclo termina com `numero` a valer 1, como previsto. A tabuada tem 10 linhas, de `1 x 1 = 1` a `1 x 10 = 10`. Os outros dois casos também dão o que a tabela de casos previa.

## Erros frequentes

### Os dois pontos e a indentação

São os erros do tema anterior. Sem os dois pontos no fim da linha do `while` ou do `for`, aparece `SyntaxError: expected ':'`. Com a primeira linha do corpo encostada à margem, aparece `IndentationError: expected an indented block after 'while' statement on line 6`. Nos dois casos, nenhuma linha do programa se executa.

### As palavras e os sinais do pseudocódigo no Python

Um `for` escrito como no pseudocódigo dá `SyntaxError: invalid syntax`. Com `for vezes de 1 até 10:`, o `^` aponta para o `de`:

```text
  File "C:\Users\aluno\Documents\fp-python\tabuada.py", line 4
    for vezes de 1 até 10:
              ^^
SyntaxError: invalid syntax
```

Com `vezes++`, a mensagem é a mesma, e o `^` aponta para o fim da linha. Corrige-se com `for vezes in range(1, 11):` e `vezes = vezes + 1`.

## Palavras novas deste guia

- Linha de observação: um `print` provisório que mostra o valor das variáveis num sítio escolhido do programa.
- Tabela prevista: a tabela de iterações que fazes antes de correr.
- Tabela observada: a mesma tabela, feita pelo computador, com as linhas de observação.
- `KeyboardInterrupt`: a última linha da mensagem de um programa parado com Ctrl+C.
- `range`: a função que produz uma sequência de inteiros, do primeiro número até antes do segundo.

## O que vem a seguir

No tema seguinte, [Listas](05-listas.md), os valores de uma série ficam guardados juntos, como nos arrays do pseudocódigo, e o `for` percorre-os um a um.

## Para saber mais

- [O `while`, no tutorial oficial do Python](https://docs.python.org/3/tutorial/introduction.html#first-steps-towards-programming): os primeiros passos da programação em Python, com um ciclo `while`, em inglês.
- [A função `range`, no tutorial oficial do Python](https://docs.python.org/3/tutorial/controlflow.html#the-range-function): o `range` e o `for`, em inglês, com outras formas do `range` que este guia não usa.

![Rodapé](../imagens/rodape.png)
