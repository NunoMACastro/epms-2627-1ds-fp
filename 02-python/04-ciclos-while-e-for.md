![Cabeçalho](../imagens/cabecalho.png)

# Ciclos while e for

Módulo Criar aplicações em linguagem de programação Python. Neste guia passas para Python os ciclos do pseudocódigo, o `Enquanto` e o `Para`, e pões o computador a repetir instruções. Para praticar, há o [laboratório](04-ciclos-while-e-for-laboratorio.md) e a [ficha de exercícios](04-ciclos-while-e-for-exercicios.md) deste tema.

No tema anterior, os programas já decidiam, mas cada linha executava-se no máximo uma vez. Agora, um bloco de linhas pode repetir-se as vezes que forem precisas. Os ciclos não são novidade, porque já os aprendeste em pseudocódigo, na algoritmia. O que muda é a forma de os escrever, e o facto de ser o computador a dar as voltas. Este tema ainda não guarda vários valores numa lista. Por isso, quando um programa trabalha com uma série de valores, lê-os do teclado, um de cada vez. As listas ficam para o tema seguinte.

Lê-se ao teu ritmo, em várias vezes, com o computador ao lado. Copia cada exemplo para um ficheiro na tua pasta `fp-python` e corre-o. É assim que se aprende mais.

## Neste guia

1. O que vais aprender
2. O que já sabes e vais usar
3. Os ciclos em Python
4. Repetir com `while`
5. As três peças de um ciclo
6. Ver as voltas: a tabela de iterações prevista e observada
7. O ciclo que nunca começa
8. O ciclo que nunca acaba, e o Ctrl+C
9. Validação repetida
10. Ler até à sentinela
11. O contador e o acumulador
12. Contar só algumas voltas
13. A média, só quando há valores
14. Contar voltas com `for` e `range`
15. As duas formas do `Para` e o `range`
16. Um `for` com um número lido do teclado
17. Escolher entre `while` e `for`
18. Exemplo guiado: a tabuada à escolha
19. Erros frequentes
20. Palavras novas deste guia
21. Verificar o que aprendeste
22. O que vem a seguir
23. Para saber mais

## O que vais aprender

No fim deste guia, consegues:

- escrever um ciclo `while` a partir de um `Enquanto` e apontar as suas três peças;
- prever quantas voltas dá um ciclo e com que valores termina, e confirmá-lo no computador com uma tabela de iterações;
- reconhecer um ciclo que nunca acaba e pará-lo com Ctrl+C;
- pedir um valor outra vez, até ele ser válido;
- ler valores até aparecer uma sentinela, contá-los e somá-los, e calcular a média só quando há valores;
- escrever um ciclo `for` com `range` a partir das duas formas do `Para`, e dizer que valores toma a variável;
- escolher entre `while` e `for` para um problema.

## O que já sabes e vais usar

- O ciclo, a iteração e a volta: guia [04 Repetição e arrays](../01-algoritmos/04-repeticao-e-arrays.md), secção "Algoritmos que repetem".
- O `Enquanto` e o corpo do ciclo, marcado pela indentação: guia [04](../01-algoritmos/04-repeticao-e-arrays.md), secção "Enquanto: repetir enquanto a condição for verdadeira".
- As três peças de um ciclo: guia [04](../01-algoritmos/04-repeticao-e-arrays.md), na mesma secção.
- A tabela de iterações, o caso de zero voltas e o ciclo infinito, no papel: guia [04](../01-algoritmos/04-repeticao-e-arrays.md), na mesma secção.
- As duas formas do `Para` e a escolha entre `Enquanto` e `Para`: guia [04](../01-algoritmos/04-repeticao-e-arrays.md), secção "Para: o ciclo contado".
- O contador, o acumulador e a média calculada só quando há valores: guia [04](../01-algoritmos/04-repeticao-e-arrays.md), secção "Contadores e acumuladores".
- A sentinela e a leitura antecipada: guia [04](../01-algoritmos/04-repeticao-e-arrays.md), secção "A sentinela: ler até aparecer o valor que diz "acabou"".
- A validação repetida: guia [04](../01-algoritmos/04-repeticao-e-arrays.md), secção "Validação repetida".
- Um ciclo dentro de outro: guia [04](../01-algoritmos/04-repeticao-e-arrays.md), secção "Arrays de arrays: uma tabela".
- A validação repetida dentro de um `Para`: [projeto 2, Adivinha o número](../01-algoritmos/05-projeto-2-adivinha-o-numero.md), secção "Passo 3: as peças do algoritmo".
- Correr um script no terminal, com `python`, `py` ou `python3`, o `print` com vários valores e os comentários: guia [01 Do pseudocódigo ao Python](01-do-pseudocodigo-ao-python.md).
- Os três tipos de erro, o traceback e a rotina da depuração, em cinco passos: guia [01 Do pseudocódigo ao Python](01-do-pseudocodigo-ao-python.md).
- As variáveis, os nomes com traço baixo e as constantes em maiúsculas: guia [02 Dados e interação](02-dados-e-interacao.md).
- O `input` com a conversão por `int`: guia [02 Dados e interação](02-dados-e-interacao.md).
- A divisão com `/`, que dá sempre um `float`: guia [02 Dados e interação](02-dados-e-interacao.md).
- O `+` com o `str`, que junta um texto e um número: guia [02 Dados e interação](02-dados-e-interacao.md).
- Os erros `TypeError`, `ValueError` e `ZeroDivisionError`: guia [02 Dados e interação](02-dados-e-interacao.md).
- O `if`, o `elif` e o `else`, com os dois pontos e a indentação: guia [03 Seleção](03-selecao.md).
- As comparações, também o `!=`, e o `and`, o `or` e o `not`: guia [03 Seleção](03-selecao.md).
- Os casos de fronteira, escolhidos antes de correr: guia [03 Seleção](03-selecao.md).
- Os valores `True` e `False`, que uma comparação dá: guia [03 Seleção](03-selecao.md).

## Os ciclos em Python

Lembra-te do problema que os ciclos resolvem. Para escrever a tabuada do 7, de 7 x 1 a 7 x 10, precisavas de dez linhas quase iguais. Para ler as notas de uma turma, nem sabias quantas linhas de leitura escrever, porque cada turma tem um número de alunos diferente. Um **ciclo** resolve as duas coisas: é uma parte do programa que se executa várias vezes seguidas. A cada execução chama-se uma **iteração**, ou uma **volta**, na conversa de todos os dias. Neste guia diz-se quase sempre volta.

O pseudocódigo das aulas tinha dois ciclos, o `Enquanto` e o `Para`. O Python também tem dois, o `while` e o `for`. A palavra inglesa *while* quer dizer "enquanto", e *for* quer dizer "para". A tabela seguinte é o mapa deste guia. Cada linha tem uma secção própria, mais abaixo.

| Pseudocódigo | Python | Onde se explica |
| --- | --- | --- |
| `Enquanto condição` | `while condição:` | Repetir com `while` |
| `Para i de 1 até 10` | `for i in range(1, 11):` | Contar voltas com `for` e `range` |
| `Para i = 0, i < 10, i++` | `for i in range(0, 10):` | As duas formas do `Para` e o `range` |
| `i = i + 1`, ou `i++` | `i = i + 1` | As três peças de um ciclo |

As ideias que estão por baixo não mudam. Um ciclo continua a ter três peças, continua a poder dar zero voltas e continua a poder nunca acabar. Os padrões do guia 04 da algoritmia, o contador, o acumulador, a sentinela e a validação repetida, passam para Python quase linha a linha. O `Parar` e o `Continuar` da algoritmia também existem em Python, mas só chegam no tema seguinte, com as listas. Neste tema, um ciclo acaba sempre pela sua condição.

## Repetir com `while`

O `while` repete um bloco de instruções enquanto uma condição for verdadeira. É o `Enquanto` do pseudocódigo. Começa-se pelo algoritmo da tabuada do 7 do guia 04 da algoritmia, que vai só até 7 x 3, para as tabelas ficarem curtas:

```text
const NUMERO = 7
const ULTIMO = 3
int vezes = 1
Enquanto vezes <= ULTIMO
    Escreve: NUMERO, " x ", vezes, " = ", NUMERO * vezes
    vezes = vezes + 1
Escreve: "Fim da tabuada"
```

Em Python, a linha do `Enquanto` passa a `while`, com dois pontos no fim, como a linha de um `if`. O corpo do ciclo fica indentado quatro espaços, como no pseudocódigo. O **corpo do ciclo** são as instruções que se repetem. As constantes perdem o `const` e ficam só com o nome em maiúsculas. A variável nasce sem o tipo à frente. Os espaços dentro das aspas saem, porque o `print` põe um espaço entre cada dois valores, como no tema 01.

Antes de correres este exemplo, tenta prever: que linhas aparecem no ecrã, e por que ordem? Quantas vezes aparece "Fim da tabuada"?

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

O resultado é este:

```text
7 x 1 = 7
7 x 2 = 14
7 x 3 = 21
Fim da tabuada
```

São três linhas da tabuada e, no fim, uma só vez, "Fim da tabuada". O ciclo deu três voltas, e o último `print` está fora dele.

Leitura guiada: o programa começa pelas constantes e por `vezes = 1`, que se executam uma vez. Na linha do `while`, o Python avalia a condição `vezes <= ULTIMO`. Como `1 <= 3` dá `True`, executa o corpo: as duas linhas indentadas, de cima para baixo. Depois da última linha do corpo, não continua para baixo. Volta à linha do `while` e avalia outra vez a condição, agora com `vezes` a valer 2. Quando `vezes` chega a 4, `4 <= 3` dá `False`, e o Python salta o corpo e continua na primeira linha que volta à margem, o `print("Fim da tabuada")`.

O `while` segue as mesmas quatro regras do `Enquanto`:

1. Quando o programa chega à linha do `while`, avalia a condição, com os valores que as variáveis têm nesse momento.
2. Se a condição der `True`, executa o corpo, de cima para baixo, até à última linha indentada.
3. Depois da última linha do corpo, volta à linha do `while` e avalia outra vez a condição. Recomeça na regra 2.
4. Se a condição der `False`, salta o corpo e continua na primeira linha a seguir a ele.

Compara com o `if` do tema anterior. O `if` avalia a condição uma vez e segue em frente. O `while` avalia a condição, executa o corpo e, no fim, sobe outra vez para fazer a mesma pergunta. Podes pensar nele como um `if` que, quando acaba o seu bloco, volta a perguntar.

Como no `if`, não há nenhuma palavra a fechar o ciclo. É a indentação que diz onde o corpo acaba. As linhas com quatro espaços a seguir ao `while` são o corpo. A primeira linha que volta a começar na margem do `while` já está fora do ciclo, e só se executa quando ele termina. Quando carregas em Enter depois dos dois pontos, o VS Code começa sozinho a linha seguinte com os quatro espaços. Para saíres do corpo, apagas esses espaços.

## As três peças de um ciclo

Um ciclo que termina tem três peças, como no pseudocódigo. Quando um ciclo falha, é quase sempre numa delas.

A **inicialização** dá o valor inicial às variáveis de que a condição e o corpo precisam. Fica antes do ciclo, encostada à margem. Na tabuada é `vezes = 1`.

A **condição** decide se se dá mais uma volta. Fica na linha do `while` e diz em que situação se continua, e não quando se para. Na tabuada é `vezes <= ULTIMO`.

A **atualização** é a instrução do corpo que muda a variável da condição e aproxima o ciclo do fim. Na tabuada é `vezes = vezes + 1`. Em Python escreve-se sempre assim, por extenso. O `vezes++` do pseudocódigo não existe em Python, como mostram os erros frequentes, no fim do guia.

O resto do corpo é o trabalho que o ciclo faz em cada volta. Na tabuada é o `print` de cada linha.

Para cada ciclo que escreveres, responde a três perguntas, uma por peça:

1. Com que valor começa, e porquê esse?
2. Em que situação continua, e quando deixa de continuar?
3. O que muda em cada volta, e essa mudança aproxima o fim?

Na tabuada, as respostas são estas. A variável `vezes` começa em 1, porque a primeira multiplicação é a do 1. O ciclo continua enquanto `vezes` for menor ou igual a 3, e deixa de continuar quando `vezes` chegar a 4. Em cada volta, `vezes` aumenta 1, e por isso aproxima-se do 4.

Repara num pormenor da segunda resposta. Depois do ciclo, `vezes` vale 4, e não 3. O ciclo não para quando escreve a última linha da tabuada. Para quando `vezes` passa o limite, porque só aí a condição dá `False`. A secção seguinte mostra como confirmar isto no computador.

## Ver as voltas: a tabela de iterações prevista e observada

Na algoritmia, eras tu que davas as voltas, e por isso sabias o valor de cada variável em cada momento. Agora é o computador, e tu só vês o que ele escreve no ecrã. As variáveis ficam escondidas. Se o ciclo der uma volta a mais, ou terminar com um valor que não esperavas, como sabes?

Faz-se em dois passos. O primeiro é **prever**: antes de correr, fazes no caderno a tabela de iterações, como na algoritmia. Tem uma linha por cada teste da condição, com o valor das variáveis nesse momento. A esta chama-se a **tabela prevista**. Na coluna da condição, o resultado escreve-se `True` ou `False`, como o Python o mostra, no lugar do `true` e do `false` do pseudocódigo.

| Teste | vezes | Condição | Durante a volta |
| --- | ---: | --- | --- |
| 1.º | 1 | `1 <= 3` dá `True` | escreve "7 x 1 = 7" |
| 2.º | 2 | `2 <= 3` dá `True` | escreve "7 x 2 = 14" |
| 3.º | 3 | `3 <= 3` dá `True` | escreve "7 x 3 = 21" |
| 4.º | 4 | `4 <= 3` dá `False` | o ciclo termina |

O segundo passo é **observar**: pões o programa a mostrar as variáveis, com um `print` a mais. A uma linha destas chama-se uma **linha de observação**. É um `print` provisório, que escreve o valor das variáveis num sítio escolhido, e que tiras quando acabares de ver. Põe-se uma na primeira linha do corpo, que mostra o valor no início de cada volta. Põe-se outra logo a seguir ao ciclo, que mostra o valor com que ele terminou. Para não as confundires com o resto do ecrã, começam todas pela palavra "(observação)".

Antes de correres, tenta prever: quantas linhas de observação aparecem, e que valor de `vezes` mostra a última?

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

O resultado é este:

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

Aparecem quatro linhas de observação, e a última mostra `vezes = 4`.

Leitura guiada: a linha de observação do corpo executa-se no início de cada volta, logo depois de a condição dar `True`. Por isso, cada uma corresponde a uma linha da tabela prevista, a dos testes 1, 2 e 3. A linha de observação depois do ciclo executa-se uma só vez, quando a condição acabou de dar `False`. Corresponde à última linha da tabela, a do 4.º teste. Juntas, as quatro linhas são a **tabela observada**: a mesma tabela, mas feita pelo computador.

Agora compara as duas tabelas, linha a linha. Se forem iguais, o ciclo fez o que previste. Se forem diferentes, a primeira linha diferente diz-te em que volta o programa se afastou do que esperavas. É a partir daí que procuras o erro.

Quando acabares de observar, tira as linhas de observação. Podes apagá-las, ou pôr um `#` no início de cada uma, para ficarem como comentários. Assim, se precisares delas outra vez, basta tirar o `#`.

## O ciclo que nunca começa

Se a condição der `False` logo no primeiro teste, o corpo não se executa nenhuma vez. Diz-se que o ciclo dá **zero voltas**.

Às vezes é um erro. Quem escreve a condição a pensar em quando o ciclo deve parar, e não em quando deve continuar, escreve-a ao contrário. Antes de correres, tenta prever o que aparece no ecrã com a condição trocada.

```python
# tabuada_nunca_comeca.py: a condição ao contrário. Este programa tem um erro, de propósito.
NUMERO = 7
ULTIMO = 3

vezes = 1
while vezes > ULTIMO:
    print(NUMERO, "x", vezes, "=", NUMERO * vezes)
    vezes = vezes + 1
print("Fim da tabuada")
```

O resultado é só esta linha:

```text
Fim da tabuada
```

Leitura guiada: no primeiro teste, `vezes` vale 1, e `1 > 3` dá `False`. O Python salta o corpo inteiro e passa logo ao `print` final. Não há mensagem de erro, porque o programa está bem escrito. É um erro de lógica: o programa faz outra coisa do que devia. Para o corrigir, pergunta-te "em que situação quero continuar?" e escreve essa situação no `while`.

Outras vezes, zero voltas é exatamente o que deve acontecer. Um programa que soma as vendas de um dia, num dia sem vendas, não deve dar nenhuma volta, e a resposta certa é 0. Vais ver um caso destes na sentinela. Por isso, testa sempre o caso de zero voltas, e confirma que o programa dá uma resposta com sentido.

## O ciclo que nunca acaba, e o Ctrl+C

Um **ciclo infinito** é um ciclo cuja condição nunca chega a dar `False`. A causa mais frequente é a atualização: falta, ou ficou fora do corpo por causa da indentação. Na algoritmia, o trace mostrava a mesma fotografia em todas as linhas. No computador, vê-se de outra maneira.

Antes de correres, tenta prever o que acontece quando tiras a atualização à tabuada.

```python
# tabuada_infinita.py: a tabuada sem a atualização. Este programa tem um erro, de propósito.
NUMERO = 7
ULTIMO = 3

vezes = 1
while vezes <= ULTIMO:
    print(NUMERO, "x", vezes, "=", NUMERO * vezes)
print("Fim da tabuada")
```

O ecrã enche-se de linhas iguais, a correr muito depressa, e o programa não volta ao terminal:

```text
7 x 1 = 7
7 x 1 = 7
7 x 1 = 7
7 x 1 = 7
```

Leitura guiada: sem a linha `vezes = vezes + 1`, a variável `vezes` vale sempre 1. A condição `1 <= 3` dá sempre `True`, e o corpo repete-se sem fim. "Fim da tabuada" nunca aparece, porque o programa nunca sai do ciclo. O Python não sabe que isto é um erro, porque um programa pode querer repetir para sempre.

Para parar um programa que não acaba, carrega em **Ctrl+C** no terminal: segura a tecla Ctrl e carrega na tecla C. Primeiro clica dentro do terminal, para ser ele a receber as teclas. No macOS também é Ctrl+C, com a tecla Control, e não com a Cmd. O programa para, e o fim do ecrã fica parecido com isto:

```text
7 x 1 = 7
7 x 1 = 7
^CTraceback (most recent call last):
  File "C:\Users\aluno\Documents\fp-python\tabuada_infinita.py", line 7, in <module>
    print(NUMERO, "x", vezes, "=", NUMERO * vezes)
    ~~~~~^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
KeyboardInterrupt
```

O `^C` é o terminal a mostrar que carregaste em Ctrl+C. A última linha, `KeyboardInterrupt`, quer dizer "interrupção pelo teclado". É um traceback como os do tema 01, lido de baixo para cima, mas aqui não aponta para o erro. Aponta só para a linha onde o programa estava quando o paraste. Pode ser outra linha do ciclo, conforme o momento em que carregaste.

Depois de parares o programa, procura a peça do ciclo que falha, com as três perguntas da secção "As três peças de um ciclo". A terceira é a que apanha os ciclos infinitos: o que muda em cada volta, e essa mudança aproxima o fim? Aqui, nada muda. A atualização também pode existir e andar no sentido errado, como `vezes = vezes - 1`: a variável muda, mas afasta-se da saída.

Há ciclos infinitos que não escrevem nada, porque o corpo não tem `print`. Aí o programa parece parado. Antes de carregares em Ctrl+C, olha para a última linha do ecrã. Se for uma pergunta, o programa está só à espera que escrevas um valor e carregues em Enter. Se já respondeste e nada acontece, é provável que seja um ciclo infinito.

## Validação repetida

No tema anterior, um `if` validava um valor: se fosse inválido, o programa escrevia uma mensagem e terminava. Quem se enganava tinha de correr o programa outra vez. Com um ciclo, faz-se melhor: o programa pede o valor outra vez, e outra, até ele ser válido. A isto chama-se **validação repetida**.

Este é o algoritmo da validação repetida do guia 04 da algoritmia:

```text
const NOTA_MINIMA = 0
const NOTA_MAXIMA = 20
Escreve: "Nota do teste (inteiro de 0 a 20)?"
int nota = ler valor
Enquanto nota < NOTA_MINIMA ou nota > NOTA_MAXIMA
    Escreve: "Nota inválida. Escreve um inteiro de 0 a 20."
    nota = ler valor
Escreve: "Nota aceite: ", nota
```

Em Python, cada par de `Escreve:` e `ler valor` junta-se num `input`, como no tema 02. Dentro do corpo, a mensagem de erro passa a ser a própria pergunta do `input`. O `ou` passa a `or`.

Antes de correres, tenta prever: quantas voltas dá o ciclo se a pessoa escrever 25, depois -3 e depois 14?

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

O ecrã fica assim, com cada valor que a pessoa escreveu a seguir à pergunta:

```text
Nota do teste (inteiro de 0 a 20)? 25
Nota inválida. Escreve um inteiro de 0 a 20: -3
Nota inválida. Escreve um inteiro de 0 a 20: 14
Nota aceite: 14
```

São duas voltas, as mesmas da tabela de iterações do guia 04 da algoritmia:

| Teste | nota | Condição | Durante a volta |
| --- | ---: | --- | --- |
| 1.º | 25 | `25 < 0 or 25 > 20` dá `True` | pede outra vez e lê -3 |
| 2.º | -3 | `-3 < 0 or -3 > 20` dá `True` | pede outra vez e lê 14 |
| 3.º | 14 | `14 < 0 or 14 > 20` dá `False` | o ciclo termina |

Leitura guiada: lê-o pelas três peças. A inicialização é a primeira leitura, antes do ciclo. A condição é a da nota inválida, com `or`, a mesma do tema anterior. A atualização é a leitura dentro do corpo, que troca o valor inválido por um novo. Se a pessoa escrever logo 14, a condição dá `False` no primeiro teste e o ciclo dá zero voltas. Está certo, porque não há nada a corrigir.

O mais útil deste padrão está no que vem depois do ciclo. Quando o programa chega ao `print` final, a condição do ciclo acabou de dar `False`. Por isso, a nota está de certeza entre 0 e 20, e o resto do programa pode usá-la sem voltar a verificar.

Para testar uma validação repetida, escolhe os casos como no tema anterior. Precisas de um valor válido logo à primeira, para as zero voltas. Precisas de valores inválidos dos dois lados da escala, como -3 e 25. E precisas das fronteiras: o 0 e o 20 têm de ser aceites, e o -1 e o 21 recusados.

Há um erro que só aparece nos programas com duas leituras, como este. Se a leitura de dentro do corpo ficar sem o `int`, o programa funciona quando a primeira nota é válida. Com uma primeira nota inválida, como 25, a segunda leitura guarda um texto, e o teste seguinte falha:

```text
Nota do teste (inteiro de 0 a 20)? 25
Nota inválida. Escreve um inteiro de 0 a 20: 14
Traceback (most recent call last):
  File "C:\Users\aluno\Documents\fp-python\validar_nota.py", line 6, in <module>
    while nota < NOTA_MINIMA or nota > NOTA_MAXIMA:
          ^^^^^^^^^^^^^^^^^^
TypeError: '<' not supported between instances of 'str' and 'int'
```

A última linha quer dizer "erro de tipo: o `<` não funciona entre um `str` e um `int`". A mensagem aponta a linha do `while`, mas a causa está na leitura do corpo, duas linhas abaixo. Por isso, as duas leituras de um ciclo levam sempre o `int`. O teste que apanha este erro é o de um valor inválido logo à primeira.

Uma validação repetida também pode ficar dentro do corpo de outro ciclo. Já o viste na algoritmia, no projeto 2, com a validação da nota dentro de um `Para` de dois alunos. A isto chama-se um **ciclo dentro de outro**. Em Python é igual. O `while` da validação fica indentado no corpo do ciclo de fora, e as linhas do corpo dele ficam com oito espaços. Em cada volta do ciclo de fora, o `while` de dentro dá todas as suas voltas, até o valor ser válido. Só depois o ciclo de fora passa à linha seguinte.

## Ler até à sentinela

Imagina a bilheteira de um cinema. O funcionário escreve o número de bilhetes de cada venda, à medida que as vendas acontecem. No fim do dia, o programa diz quantas vendas houve. Quando o ciclo começa, ninguém sabe quantas vendas vão ser.

A solução do guia 04 da algoritmia é combinar um valor especial que quer dizer "acabou". Quem escreve os dados escreve esse valor no fim, e o programa, quando o lê, sabe que não há mais dados. A este valor chama-se **sentinela**. Não pode ser um valor que os dados verdadeiros possam ter. Na bilheteira, nenhuma venda tem 0 bilhetes, e por isso o 0 serve de sentinela. A pergunta diz qual é, para quem escreve saber como terminar.

Um ciclo com sentinela tem sempre a mesma forma. Antes do ciclo, lê-se o primeiro valor: é a **leitura antecipada**, e é a inicialização. A condição é "o valor lido não é a sentinela", com `!=`. O corpo trata o valor e, na última linha, ainda indentada, lê o valor seguinte. Essa leitura é a atualização.

Antes de correres, tenta prever: com as vendas 2, 4 e 1 e, no fim, o 0, quantas vendas conta o programa? E se a primeira coisa escrita for logo o 0?

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

Com 2, 4, 1 e 0, o ecrã fica assim:

```text
Bilhetes desta venda (0 para terminar)? 2
Bilhetes desta venda (0 para terminar)? 4
Bilhetes desta venda (0 para terminar)? 1
Bilhetes desta venda (0 para terminar)? 0
Vendas: 3
```

Com o 0 logo de início, o ciclo dá zero voltas:

```text
Bilhetes desta venda (0 para terminar)? 0
Vendas: 0
```

Leitura guiada: o valor lido vai sempre direto para o teste do `while`. Se for um dado, entra no corpo e é contado. Se for a sentinela, a condição dá `False` e o ciclo termina, sem a sentinela ser contada como venda. É por isso que se lê antes do ciclo e no fim do corpo, e não no princípio do corpo. Com o 0 logo à primeira, a resposta é 0 vendas, que é a certa para um dia sem vendas.

Também aqui as duas leituras levam o `int`, como na validação repetida. Se faltar na leitura do fim do corpo, a sentinela fica guardada como o texto `"0"`, que é diferente do número 0. A condição `"0" != 0` dá `True`, e o programa continua a perguntar, sem nenhuma mensagem de erro.

Agora o erro que esta forma existe para evitar. Quem ainda não conhece a leitura antecipada lê no princípio do corpo. Como a condição precisa de um valor no primeiro teste, inventa um valor só para entrar no ciclo, como `bilhetes_da_venda = 1`. Antes de correres, prevê quantas vendas conta esta versão, com os mesmos 2, 4, 1 e 0.

```python
# bilheteira_errada.py: lê no princípio do corpo. Este programa tem um erro, de propósito.
SENTINELA = 0

vendas = 0
bilhetes_da_venda = 1
while bilhetes_da_venda != SENTINELA:
    bilhetes_da_venda = int(input("Bilhetes desta venda (0 para terminar)? "))
    vendas = vendas + 1
print("Vendas:", vendas)
```

O ecrã mostra as mesmas quatro perguntas, mas o fim é outro:

```text
Vendas: 4
```

Leitura guiada: o 0 é lido dentro do corpo, e a linha seguinte conta-o como venda antes de a condição o poder testar. Só no teste seguinte o ciclo termina. Com o 0 logo à primeira, esta versão conta 1 venda num dia sem vendas. O valor inventado, `bilhetes_da_venda = 1`, que não vem de lado nenhum, já era um sinal de alarme. Usa sempre a leitura antecipada, antes do ciclo, e a leitura no fim do corpo.

## O contador e o acumulador

A bilheteira já conta as vendas. A variável `vendas` é um **contador**: uma variável que conta quantas vezes uma coisa aconteceu. Começa em 0, antes do ciclo, e aumenta 1 em cada volta: `vendas = vendas + 1`. Responde à pergunta "quantos?".

Falta saber quantos bilhetes se venderam. Para isso não basta contar, é preciso somar. Um **acumulador** é uma variável que vai somando valores ao longo das voltas. Começa em 0, antes do ciclo, e em cada volta soma o valor dessa volta: `bilhetes = bilhetes + bilhetes_da_venda`. Responde à pergunta "quanto?". Os dois só se leem depois do ciclo, porque durante o ciclo guardam uma contagem a meio.

Este é o algoritmo da bilheteira do guia 04 da algoritmia, completo:

```text
const SENTINELA = 0
int vendas = 0
int bilhetes = 0
Escreve: "Bilhetes desta venda (0 para terminar)?"
int bilhetesDaVenda = ler valor
Enquanto bilhetesDaVenda != SENTINELA
    vendas = vendas + 1
    bilhetes = bilhetes + bilhetesDaVenda
    Escreve: "Bilhetes desta venda (0 para terminar)?"
    bilhetesDaVenda = ler valor
Escreve: "Vendas: ", vendas
Escreve: "Bilhetes vendidos: ", bilhetes
```

Antes de correres a tradução, tenta prever o total de bilhetes com 2, 4, 1 e o 0.

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

Depois das quatro perguntas, o fim do ecrã é este:

```text
Vendas: 3
Bilhetes vendidos: 7
```

Esta é a tabela de iterações, sem as perguntas:

| Teste | bilhetes_da_venda | vendas | bilhetes | Condição | Durante a volta |
| --- | ---: | ---: | ---: | --- | --- |
| 1.º | 2 | 0 | 0 | `2 != 0` dá `True` | conta, soma 2 e lê 4 |
| 2.º | 4 | 1 | 2 | `4 != 0` dá `True` | conta, soma 4 e lê 1 |
| 3.º | 1 | 2 | 6 | `1 != 0` dá `True` | conta, soma 1 e lê 0 |
| 4.º | 0 | 3 | 7 | `0 != 0` dá `False` | o ciclo termina |

Leitura guiada: o contador e o acumulador nascem antes do ciclo, com 0. Dentro do corpo, o contador soma 1 e o acumulador soma o valor lido. A diferença entre os dois está só no que se soma. O contador soma sempre 1, seja qual for o valor. O acumulador soma o próprio valor. A tradução muda só o nome `bilhetesDaVenda`, que em Python se escreve com traço baixo, `bilhetes_da_venda`.

Os contadores e os acumuladores começam sempre antes do ciclo. Se a linha `bilhetes = 0` passar para dentro do corpo, o total recomeça em cada volta. No fim, guarda só o último valor: com 2, 4, 1 e o 0, o programa escreve `Bilhetes vendidos: 1`. A regra a fixar é a da algoritmia: o que se inicializa dentro do ciclo recomeça em cada volta.

## Contar só algumas voltas

O contador da bilheteira aumenta em todas as voltas, porque conta todas as vendas. Mas há casos em que só interessa contar as voltas em que acontece uma coisa. Por exemplo, o cinema quer saber quantas vendas foram de grupo, com 4 bilhetes ou mais.

Para isso, a linha que aumenta o contador vai para dentro de um `if`, com oito espaços. Quatro espaços põem-na dentro do ciclo, e os outros quatro põem-na dentro do `if`. Assim, só se executa nas voltas em que a condição do `if` dá `True`. É a indentação que decide o que conta.

Antes de correres, tenta prever: com as vendas 2, 4, 1 e 6 e o 0, quantas são de grupo? A venda de 4 bilhetes conta?

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

Depois das cinco perguntas, o fim do ecrã é este:

```text
Vendas: 4
Vendas de grupo: 2
Bilhetes vendidos: 13
```

Leitura guiada: em cada volta, o corpo faz três coisas. Conta a venda, soma os bilhetes e, só se a venda tiver 4 bilhetes ou mais, conta-a como venda de grupo. Com o 4 e com o 6, `bilhetes_da_venda >= GRUPO` dá `True`. Com o 2 e com o 1, dá `False`, e a linha do aumento é saltada. A venda de 4 conta, porque a condição usa `>=`. É a fronteira do tema anterior, agora dentro de um ciclo. Repara também que a leitura do valor seguinte volta à margem do corpo, com quatro espaços. Se ficasse dentro do `if`, numa venda que não é de grupo não se lia nenhum valor novo, e o ciclo nunca acabava.

## A média, só quando há valores

Com um contador e um acumulador no mesmo ciclo, calcula-se uma média: o total a dividir pelo número de valores. Na bilheteira, é o número médio de bilhetes por venda.

A média tem um cuidado, que já conheces do guia 04 da algoritmia. Num dia sem vendas, o ciclo dá zero voltas, e `vendas` e `bilhetes` ficam a 0. Calcular a média seria fazer 0 / 0, e não se pode dividir por zero. Em Python, isso para o programa com `ZeroDivisionError`. Por isso, a média calcula-se depois do ciclo, só dentro de um `if vendas > 0:`.

Antes de correres, tenta prever o que aparece com 2, 4, 3 e o 0. E o que aparece com o 0 logo à primeira?

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

Com 2, 4, 3 e o 0, o fim do ecrã é este:

```text
Vendas: 3
Bilhetes vendidos: 9
Bilhetes por venda, em média: 3.0
```

Com o 0 logo à primeira:

```text
Vendas: 0
Bilhetes vendidos: 0
Não houve vendas, por isso não há média.
```

Leitura guiada: o `if` está encostado à margem, depois do ciclo. Por isso, só se avalia uma vez, quando a contagem e a soma estão completas. Se estivesse dentro do ciclo, calculava uma média em cada volta, com contas a meio. A média aparece como `3.0`, e não como 3, porque a divisão com `/` dá sempre um `float`. Com o 0 logo à primeira, `0 > 0` dá `False`, e o programa escreve a mensagem sem chegar à divisão.

Uma divisão pode dar muitas casas decimais. Com 2, 4, 1 e o 0, a média é 7 / 3, e o Python escreve `2.3333333333333335`. Se quiseres menos casas, usa o `round` do tema 02: `round(media, 1)` dá `2.3`.

Imagina que tiras o `if`, o `else` e o comentário de cima, e deixas a divisão e o `print` da média encostados à margem. O programa dá a média certa sempre que há vendas. O erro só aparece a quem testa o dia sem vendas, e aparece assim:

```text
Bilhetes desta venda (0 para terminar)? 0
Vendas: 0
Bilhetes vendidos: 0
Traceback (most recent call last):
  File "C:\Users\aluno\Documents\fp-python\bilheteira_media.py", line 13, in <module>
    media = bilhetes / vendas
            ~~~~~~~~~^~~~~~~~
ZeroDivisionError: division by zero
```

A última linha quer dizer "erro de divisão por zero". Sempre que dividires por um contador, pergunta-te o que acontece se ele ficar a 0, e põe a conta dentro de um `if contador > 0:`.

## Contar voltas com `for` e `range`

Na tabuada, sabe-se antes de o ciclo começar quantas voltas vai haver: três, ou dez. A um ciclo assim chama-se **ciclo contado**. Com o `while`, um ciclo contado obriga a escrever as três peças à mão, com três oportunidades de errar. O pseudocódigo tinha o `Para` para estes casos. Em Python, é o `for`, com a ajuda de uma função predefinida, o `range`.

O **`range`** produz uma sequência de números inteiros. `range(1, 4)` produz 1, 2 e 3. O primeiro número entra na sequência, e o segundo não entra: a sequência para logo antes dele. O `for` dá à sua variável cada um desses números, um por volta, e executa o corpo com ele. Essa variável, que o `for` vai mudando, é a **variável de controlo**, como no `Para`.

Este é o `Para` da tabuada do guia 04 da algoritmia:

```text
const NUMERO = 7
const ULTIMO = 3
Para vezes de 1 até ULTIMO
    Escreve: NUMERO, " x ", vezes, " = ", NUMERO * vezes
Escreve: "Fim da tabuada"
```

Antes de correres a tradução, tenta prever: o ecrã é igual ao do `while`? Porque é que o `range` acaba em `ULTIMO + 1`?

```python
# tabuada_for.py: escreve a tabuada do 7, de 7 x 1 a 7 x 3, com um ciclo for.
NUMERO = 7
ULTIMO = 3

for vezes in range(1, ULTIMO + 1):
    print(NUMERO, "x", vezes, "=", NUMERO * vezes)
print("Fim da tabuada")
```

O resultado é igual ao do `while`:

```text
7 x 1 = 7
7 x 2 = 14
7 x 3 = 21
Fim da tabuada
```

Leitura guiada: a linha do `for` lê-se "para `vezes` em cada número do `range` de 1 a 3". O `range(1, ULTIMO + 1)` é `range(1, 4)`, que dá 1, 2 e 3. O `+ 1` está lá porque o fim do `range` não entra, e o "até ULTIMO" do pseudocódigo inclui o 3. O corpo, indentado, executa-se uma vez por cada número. A última linha está encostada à margem, e por isso está fora do ciclo, como no `while`.

As três peças estão lá, mas o `for` escreve-as sozinho. A inicialização é o início do `range`, o 1. A condição é o fim do `range`: o ciclo continua enquanto houver números na sequência. A atualização não se escreve, porque é o `for` que passa ao número seguinte. Por isso, num ciclo contado, o `for` é mais seguro do que o `while`: não há atualização para esquecer.

| Peça | Com `while` | Com `for` |
| --- | --- | --- |
| Inicialização | `vezes = 1`, antes do ciclo | o 1, o início do `range` |
| Condição | `vezes <= ULTIMO`, na linha do `while` | o fim do `range`, `ULTIMO + 1`, que não entra |
| Atualização | `vezes = vezes + 1`, no fim do corpo | não se escreve: o `for` passa ao número seguinte |

Num `for`, a condição não está escrita. Por isso, a tabela de iterações de um `for` tem uma linha por volta, e não por teste. Cada linha mostra o valor da variável de controlo nessa volta.

Há uma diferença pequena depois do ciclo. Com o `while`, `vezes` acaba a valer 4. Com o `for`, acaba a valer 3, o último número do `range`. Por isso, num ciclo contado, não uses depois do ciclo a variável que contou as voltas. Numa validação repetida é ao contrário: o valor depois do ciclo é precisamente o que interessa.

Agora a tabuada completa, até 7 x 10. Antes de correres, tenta prever: qual é a primeira linha, qual é a última, e quantas linhas são?

```python
# tabuada.py: escreve a tabuada do 7, de 7 x 1 a 7 x 10.
NUMERO = 7

for vezes in range(1, 11):
    print(NUMERO, "x", vezes, "=", NUMERO * vezes)
```

O resultado são dez linhas:

```text
7 x 1 = 7
7 x 2 = 14
7 x 3 = 21
7 x 4 = 28
7 x 5 = 35
7 x 6 = 42
7 x 7 = 49
7 x 8 = 56
7 x 9 = 63
7 x 10 = 70
```

Leitura guiada: o `range(1, 11)` dá os números de 1 a 10, e o 11 não entra. Em cada volta, a conta `NUMERO * vezes` faz-se antes de o `print` escrever, e o `print` põe os espaços entre os cinco valores.

O erro típico é esquecer que o fim não entra. Com `range(1, 10)`, a tabuada acaba em `7 x 9 = 63`, e a linha do 10 nunca aparece. O Python não dá nenhuma mensagem, porque o programa está bem escrito: faz outra coisa, e só os testes o mostram. É um erro de lógica de uma volta a menos. Testa sempre a primeira e a última volta, e confirma que a última linha é a do 10.

## As duas formas do `Para` e o `range`

Nas aulas, o `Para` tinha duas formas, e as duas passam a `range`. A tabela liga-as:

| Pseudocódigo | Python | Valores da variável |
| --- | --- | --- |
| `Para i de 1 até 10` | `for i in range(1, 11):` | 1, 2, ..., 10 |
| `Para i = 0, i < 10, i++` | `for i in range(0, 10):` | 0, 1, ..., 9 |
| `Para i = 0, i < n, i++` | `for i in range(0, n):` | 0, 1, ..., n - 1 |

A segunda forma passa diretamente: o `range(0, 10)` para antes do 10, tal como a condição `i < 10`. A primeira forma precisa de mais 1 no fim, porque o "até 10" do pseudocódigo inclui o 10.

Quando o `range` começa em 0, pode escrever-se só com o fim: `range(10)` é o mesmo que `range(0, 10)`. Há uma conta rápida para saber o número de voltas: `range(início, fim)` dá `fim - início` voltas, quando o fim não é menor do que o início. Se for menor, como em `range(5, 2)`, dá zero voltas. O `range(1, 11)` dá 10 voltas, e o `range(5)` dá 5.

Antes de correres este exemplo, tenta prever os números que cada `range` escreve. O último `range` escreve algum número?

```python
# contar_range.py: mostra os valores que cada range dá, um por linha.
print("range(1, 5):")
for i in range(1, 5):
    print(i)
print("range(0, 5):")
for i in range(0, 5):
    print(i)
print("range(5):")
for i in range(5):
    print(i)
print("range(3, 3):")
for i in range(3, 3):
    print(i)
print("Fim")
```

O resultado é este:

```text
range(1, 5):
1
2
3
4
range(0, 5):
0
1
2
3
4
range(5):
0
1
2
3
4
range(3, 3):
Fim
```

Leitura guiada: o programa tem quatro ciclos, um a seguir ao outro, cada um com o seu título. O `range(1, 5)` dá quatro números, de 1 a 4. O `range(0, 5)` e o `range(5)` dão os mesmos cinco números, de 0 a 4. O `range(3, 3)` não dá nenhum, porque começa e acaba no mesmo número, e `3 - 3` é 0. É o caso de zero voltas do `for`: o corpo não se executa, e o programa passa logo ao `print("Fim")`.

O nome `i` é a escolha habitual para uma variável de controlo que só conta, sem outro significado. Quando o número quer dizer alguma coisa, dá-lhe um nome que o diga, como `vezes`, `ronda` ou `turma`.

## Um `for` com um número lido do teclado

Um ciclo contado não precisa de ter o número de voltas escrito no programa. Basta sabê-lo quando o ciclo começa. Num jogo com várias rondas, o programa pode perguntar primeiro quantas rondas jogaste, e depois os pontos de cada uma. Quando o `for` começa, o número de voltas já está decidido.

Antes de correres, tenta prever: com 3 rondas de 12, 8 e 15 pontos, que perguntas aparecem e que total? E se disseres que jogaste 0 rondas?

```python
# rondas.py: pergunta quantas rondas jogaste e soma os pontos de todas.
rondas = int(input("Quantas rondas jogaste? "))
total = 0
for ronda in range(1, rondas + 1):
    pontos = int(input("Pontos da ronda " + str(ronda) + "? "))
    total = total + pontos
print("Total de pontos:", total)
```

Com 3 rondas, o ecrã fica assim:

```text
Quantas rondas jogaste? 3
Pontos da ronda 1? 12
Pontos da ronda 2? 8
Pontos da ronda 3? 15
Total de pontos: 35
```

Com 0 rondas:

```text
Quantas rondas jogaste? 0
Total de pontos: 0
```

Leitura guiada: a primeira linha lê o número de voltas. O `range(1, rondas + 1)` vai de 1 até ao número lido, e o `+ 1` está lá porque o fim não entra. A pergunta de cada ronda junta três textos com `+`, e o `str(ronda)` transforma o número da ronda num texto, como no tema 02. O acumulador `total` nasce antes do ciclo e soma os pontos em cada volta. Com 0 rondas, o `range(1, 1)` não dá nenhum número, o ciclo dá zero voltas, e o total fica a 0.

No corpo de um `for` pode ficar qualquer instrução, também um `while`. Uma validação repetida dentro do `for` pede outra vez o valor da mesma volta, até ele ser válido, como na secção "Validação repetida".

## Escolher entre `while` e `for`

A escolha faz-se com a mesma pergunta da algoritmia. Quando o programa chega ao ciclo, já se sabe quantas voltas vai dar? Se sim, o ciclo é contado, e usa-se `for` com `range`. Se não, usa-se `while`. É o caso de um fim que depende de alguma coisa que só acontece durante o ciclo, como um valor lido.

| Situação | Ciclo | Porquê |
| --- | --- | --- |
| Escrever a tabuada do 7, de 1 a 10 | `for` | São 10 voltas, antes de começar |
| Pedir os pontos das rondas, depois de perguntar quantas são | `for` | O número é lido antes de o ciclo começar |
| Ler vendas até aparecer o 0 | `while` | Só se sabe que acabou quando o 0 aparece |
| Pedir uma nota até ela ser válida | `while` | Depende do que a pessoa escrever |

Todo o `for` com `range` se pode escrever como um `while`, como viste na tabuada. O contrário não é verdade. Um ciclo com sentinela não se escreve com `for` e `range`, porque não há número de voltas para pôr no `range`. Na dúvida, o `while` funciona sempre, mas obriga-te a escrever as três peças. Quando o ciclo é contado, o `for` é a escolha mais segura.

## Exemplo guiado: a tabuada à escolha

Este exemplo junta os dois algoritmos do guia 04 da algoritmia que traduziste neste guia, a validação repetida e a tabuada, num só programa. Segue o caminho completo: o problema, os casos de teste, o pseudocódigo, a tradução, a tabela prevista e a observada.

### Passo 1: o problema e os casos de teste

> O programa pergunta de que número queres a tabuada, de 1 a 10. Se o número estiver fora, escreve "Esse número não dá. Escreve de 1 a 10:" e pergunta outra vez, até o número ser válido. Depois escreve a tabuada desse número, de N x 1 até N x 10.

Antes de qualquer código, escolhem-se os casos de teste e o resultado esperado de cada um, a partir do enunciado. Como o programa tem dois ciclos, os casos têm de testar os dois.

| Valores escritos | Perguntas repetidas | Primeira linha | Última linha | Porque é que este caso foi escolhido |
| --- | ---: | --- | --- | --- |
| 7 | 0 | `7 x 1 = 7` | `7 x 10 = 70` | Um número válido logo à primeira: zero voltas na validação |
| 0, 11, 1 | 2 | `1 x 1 = 1` | `1 x 10 = 10` | Os dois lados de fora e a fronteira de baixo, o 1 |
| 10 | 0 | `10 x 1 = 10` | `10 x 10 = 100` | A fronteira de cima, o 10 |

Em todos os casos, a tabuada tem 10 linhas. A primeira e a última linha são as que apanham uma volta a mais ou a menos.

### Passo 2: as peças dos dois ciclos

O primeiro ciclo é uma validação repetida. Não se sabe quantas voltas vai dar, porque depende do que a pessoa escrever. É um `while`.

- Inicialização: a primeira leitura do número, antes do ciclo.
- Condição: o número está fora de 1 a 10, `numero < MINIMO or numero > MAXIMO`.
- Atualização: a leitura dentro do corpo, que troca o número inválido por outro.

O segundo ciclo escreve a tabuada. Quando começa, já se sabe que dá 10 voltas. É um `for`, com a variável `vezes` de 1 a 10. Quando o `for` começa, o número já está de certeza entre 1 e 10, porque o `while` acabou de terminar.

### Passo 3: o pseudocódigo

```text
const MINIMO = 1
const MAXIMO = 10
const ULTIMO = 10
Escreve: "De que número queres a tabuada (1 a 10)?"
int numero = ler valor
Enquanto numero < MINIMO ou numero > MAXIMO
    Escreve: "Esse número não dá. Escreve de 1 a 10."
    numero = ler valor
Para vezes de 1 até ULTIMO
    Escreve: numero, " x ", vezes, " = ", numero * vezes
```

As constantes `MINIMO` e `MAXIMO` dão nome aos limites da validação. A constante `ULTIMO` dá nome à última multiplicação. São todas 1 ou 10, mas querem dizer coisas diferentes, e por isso têm nomes diferentes.

### Passo 4: traduzir linha a linha

| Pseudocódigo | Python | O que muda |
| --- | --- | --- |
| `const MINIMO = 1` | `MINIMO = 1` | sem `const`; as maiúsculas dizem que é uma constante |
| `Escreve: "De que número...?"` e `int numero = ler valor` | `numero = int(input("De que número...? "))` | uma só linha, com o `int` |
| `Enquanto numero < MINIMO ou numero > MAXIMO` | `while numero < MINIMO or numero > MAXIMO:` | `while`, `or` e os dois pontos |
| `Escreve: "Esse número não dá..."` e `numero = ler valor` | `numero = int(input("Esse número não dá. Escreve de 1 a 10: "))` | a mensagem passa a ser a pergunta |
| `Para vezes de 1 até ULTIMO` | `for vezes in range(1, ULTIMO + 1):` | o fim do `range` leva mais 1 |
| `Escreve: numero, " x ", ...` | `print(numero, "x", vezes, "=", numero * vezes)` | os espaços ficam fora das aspas |

### Passo 5: o programa completo

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

Os dois ciclos estão um a seguir ao outro, os dois encostados à margem. O `for` só começa quando o `while` termina.

### Passo 6: a tabela de iterações prevista

Para o caso 0, 11, 1, a tabela do `while` prevê três testes:

| Teste | numero | Condição | Durante a volta |
| --- | ---: | --- | --- |
| 1.º | 0 | `0 < 1 or 0 > 10` dá `True` | pede outra vez e lê 11 |
| 2.º | 11 | `11 < 1 or 11 > 10` dá `True` | pede outra vez e lê 1 |
| 3.º | 1 | `1 < 1 or 1 > 10` dá `False` | o ciclo termina |

O `for` dá 10 voltas, com `vezes` de 1 a 10. Basta prever a primeira e a última:

| Volta | vezes | Escreve |
| --- | ---: | --- |
| 1.ª | 1 | `1 x 1 = 1` |
| 10.ª | 10 | `1 x 10 = 10` |

### Passo 7: correr os casos e observar

Para observar o `while`, acrescentam-se duas linhas de observação, uma na primeira linha do corpo e outra logo depois do ciclo:

```python
while numero < MINIMO or numero > MAXIMO:
    print("(observação) volta da validação com numero =", numero)
    numero = int(input("Esse número não dá. Escreve de 1 a 10: "))
print("(observação) depois da validação, numero =", numero)
```

Com 0, 11 e 1, o ecrã fica assim:

```text
De que número queres a tabuada (1 a 10)? 0
(observação) volta da validação com numero = 0
Esse número não dá. Escreve de 1 a 10: 11
(observação) volta da validação com numero = 11
Esse número não dá. Escreve de 1 a 10: 1
(observação) depois da validação, numero = 1
1 x 1 = 1
1 x 2 = 2
1 x 3 = 3
1 x 4 = 4
1 x 5 = 5
1 x 6 = 6
1 x 7 = 7
1 x 8 = 8
1 x 9 = 9
1 x 10 = 10
```

A tabela observada é igual à prevista: duas voltas na validação, com 0 e com 11, e o ciclo terminou com `numero = 1`. A tabuada tem 10 linhas, a primeira e a última como previsto. Depois de observar, tiram-se as duas linhas de observação.

Os outros dois casos, sem as linhas de observação, dão o que a tabela do passo 1 previa. Com 7, não há perguntas repetidas, e a tabuada vai de `7 x 1 = 7` a `7 x 10 = 70`. Com 10, vai de `10 x 1 = 10` a `10 x 10 = 100`. Os três casos passam.

## Erros frequentes

Alguns erros deste guia ficaram na secção da ideia que explicam:

- a condição ao contrário, em "O ciclo que nunca começa";
- a atualização esquecida, em "O ciclo que nunca acaba, e o Ctrl+C";
- a conversão esquecida na leitura do corpo, em "Validação repetida";
- a sentinela contada como dado, em "Ler até à sentinela";
- o acumulador que começa dentro do ciclo, em "O contador e o acumulador";
- a média sem o `if`, em "A média, só quando há valores";
- o fim do `range` que não entra, em "Contar voltas com `for` e `range`".

Ficam aqui os outros.

### Os dois pontos esquecidos

O que se vê: sem os dois pontos no fim da linha do `while`, o programa não corre:

```text
  File "C:\Users\aluno\Documents\fp-python\tabuada_while.py", line 6
    while vezes <= ULTIMO
                         ^
SyntaxError: expected ':'
```

Porque acontece: a linha do `while` abre um bloco, como a do `if`. Todas as linhas que abrem um bloco acabam em dois pontos. A mensagem quer dizer "erro de sintaxe: esperava-se `:`", e o `^` aponta para o sítio onde eles faltam. Com o `for` acontece o mesmo.

Como se corrige: acrescenta os dois pontos no fim da linha. É um erro de sintaxe, e por isso nenhuma linha do programa se executou, nem as que estavam antes do ciclo.

### O corpo sem indentação

O que se vê: se a primeira linha do corpo ficar encostada à margem, o programa também não corre:

```text
  File "C:\Users\aluno\Documents\fp-python\tabuada_while.py", line 7
    print(NUMERO, "x", vezes, "=", NUMERO * vezes)
    ^^^^^
IndentationError: expected an indented block after 'while' statement on line 6
```

Porque acontece: depois dos dois pontos, o Python espera pelo menos uma linha indentada, o corpo. A mensagem quer dizer "erro de indentação: esperava-se um bloco indentado depois do `while` da linha 6". Com o `for`, diz `after 'for' statement`.

Como se corrige: põe quatro espaços no início de cada linha do corpo. Depois confirma, com o dedo por baixo do `w` do `while`, que linhas ficaram à direita, dentro do ciclo, e quais ficaram fora.

### As palavras e os sinais do pseudocódigo no Python

O que se vê: uma linha escrita como no pseudocódigo dá `SyntaxError: invalid syntax`, isto é, "erro de sintaxe: escrita inválida". Com `for vezes de 1 até 10:`, o `^` aponta para o `de`:

```text
  File "C:\Users\aluno\Documents\fp-python\tabuada.py", line 4
    for vezes de 1 até 10:
              ^^
SyntaxError: invalid syntax
```

Com `vezes++` no lugar da atualização, a mensagem é a mesma, e o `^` aponta para o fim da linha.

Porque acontece: o Python só conhece as suas palavras. Não sabe o que é `Enquanto`, `de`, `até` ou `++`. O pseudocódigo foi pensado para passar para Python quase linha a linha, mas a forma de escrever é a do Python.

Como se corrige: `Enquanto` passa a `while`, `Para vezes de 1 até 10` passa a `for vezes in range(1, 11)`, e `vezes++` passa a `vezes = vezes + 1`.

### Testar só o caso normal

O que se vê: um ciclo testado só com três ou quatro valores parece quase sempre certo.

Porque acontece: vários erros deste guia só aparecem noutros casos. O dia sem vendas revela a média sem o `if`. Uma primeira nota inválida revela a conversão esquecida na leitura do corpo. A última volta revela o fim do `range` errado. A fronteira revela um igual a mais ou a menos.

Como se corrige: testa sempre o caso de zero voltas, o de uma volta e o de várias voltas. Confirma a primeira e a última volta. E, se o programa tem uma validação, testa as fronteiras dos dois lados.

## Palavras novas deste guia

- Ciclo: uma parte do programa que se executa várias vezes seguidas.
- Volta, ou iteração: cada execução do corpo de um ciclo.
- Corpo do ciclo: as instruções indentadas debaixo do `while` ou do `for`, que se repetem.
- `while`: o ciclo que repete o corpo enquanto a condição der `True`; é o `Enquanto` do Python.
- Inicialização: a peça do ciclo que dá o valor inicial às variáveis, antes do ciclo.
- Condição de um ciclo: a peça que decide se se dá mais uma volta; diz quando continuar.
- Atualização: a instrução do corpo que muda a variável da condição e aproxima o ciclo do fim.
- Tabela prevista: a tabela de iterações que fazes no caderno antes de correr.
- Linha de observação: um `print` provisório que mostra o valor das variáveis num sítio escolhido do programa.
- Tabela observada: a tabela de iterações que o computador escreve, com as linhas de observação.
- Zero voltas: o caso em que a condição dá `False` logo no primeiro teste, e o corpo não se executa.
- Ciclo infinito: um ciclo cuja condição nunca chega a dar `False`.
- Ctrl+C: as teclas que param, no terminal, um programa que está a correr.
- `KeyboardInterrupt`: a última linha da mensagem de um programa parado com Ctrl+C; quer dizer "interrupção pelo teclado".
- Validação repetida: pedir um valor outra vez, enquanto for inválido.
- Ciclo dentro de outro: um ciclo que fica no corpo de outro ciclo, e dá todas as suas voltas em cada volta do de fora.
- Sentinela: o valor combinado que quer dizer "acabou", e que nenhum dado verdadeiro pode ter.
- Leitura antecipada: a leitura do primeiro valor, antes do ciclo, que é a inicialização de um ciclo com sentinela.
- Contador: uma variável que conta quantas vezes uma coisa aconteceu; responde a "quantos?".
- Acumulador: uma variável que vai somando valores; responde a "quanto?".
- Ciclo contado: um ciclo em que se sabe, antes de começar, quantas voltas vai dar.
- `for`: o ciclo que dá à variável de controlo cada valor de uma sequência; é o `Para` do Python.
- `range`: a função que produz uma sequência de inteiros, do primeiro número até antes do segundo.
- Variável de controlo: a variável que o `for` vai mudando, um valor por volta.

## Verificar o que aprendeste

Responde sem olhar para o guia. Se não conseguires, volta à secção que explica a ideia.

1. Num `while` que dá 4 voltas, quantas vezes se testa a condição? Porquê?
2. Neste ciclo, aponta as três peças e responde às três perguntas sobre elas: `pontos = 0`, `while pontos < 30:`, com o corpo `print(pontos)` e `pontos = pontos + 10`. Quanto vale `pontos` depois do ciclo?
3. Que linhas de observação acrescentavas ao ciclo da pergunta 2 para veres o valor de `pontos` em cada teste? Onde as punhas?
4. O teu programa não volta ao terminal e não mostra nada de novo. Que duas coisas podem estar a acontecer, e como as distingues?
5. Numa validação repetida da idade de um jogador, de 12 a 18, que casos de teste escolhes, e porquê?
6. Num programa com sentinela, porque é que a primeira leitura fica antes do ciclo e a segunda no fim do corpo?
7. Uma aplicação regista os minutos de treino de cada dia até a pessoa escrever uma sentinela. Um dia pode ter 0 minutos. Que sentinela escolhes, e porquê?
8. Qual é a diferença entre um contador e um acumulador? Dá um exemplo de cada, num jogo.
9. Porque é que a média fica dentro de `if vendas > 0:`, e porque é que esse `if` fica depois do ciclo, e não dentro?
10. Que valores toma `i` em `for i in range(2, 6):`? E em `for i in range(4):`? Quantas voltas dá `for i in range(5, 5):`?
11. Escreve em Python o `Para dia de 1 até 7` e o `Para i = 0, i < 8, i++`.
12. Escolhes `while` ou `for` para cada situação, e porquê? A primeira é pedir os pontos das 5 rondas de um jogo. A segunda é ler palpites até alguém acertar num número.

## O que vem a seguir

Para praticar este tema, faz o [laboratório](04-ciclos-while-e-for-laboratorio.md). Nele passas para Python, fase a fase, a campanha de recolha de alimentos do guia 04 da algoritmia. Primeiro com a sentinela, o contador, o acumulador e a média, e depois com o `for`, nas turmas do 10.º ano. Depois faz a [ficha de exercícios](04-ciclos-while-e-for-exercicios.md), com ciclos para prever, escrever e corrigir.

O tema seguinte é [Listas](05-listas.md). Neste tema, os valores de uma série chegaram um a um, do teclado, e cada um desapareceu quando chegou o seguinte. No tema seguinte, os valores ficam guardados juntos numa lista, como os arrays do pseudocódigo, e o `for` percorre-os um a um.

## Para saber mais

- [O `while`, no tutorial oficial do Python](https://docs.python.org/3/tutorial/introduction.html#first-steps-towards-programming): os primeiros passos da programação em Python, com um ciclo `while`, em inglês.
- [A função `range`, no tutorial oficial do Python](https://docs.python.org/3/tutorial/controlflow.html#the-range-function): o `range` e o `for`, em inglês, com outras formas do `range` que este guia não usa.

![Rodapé](../imagens/rodape.png)
