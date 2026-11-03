![Cabeçalho](../../imagens/cabecalho.png)

# Laboratório: Ciclos while e for

Laboratório do tema Ciclos while e for, do módulo Criar aplicações em linguagem de programação Python. Vais passar para Python, fase a fase, o problema da campanha de recolha de alimentos, que já conheces do pseudocódigo. Primeiro com um ciclo `while`, e depois com um ciclo `for`. Cada passo diz o que fazer, porquê e o que deves ver, e avanças ao teu ritmo. Tudo o que precisas está aqui; o [guia do tema](../04-ciclos-while-e-for.md) tem a teoria completa, para quem quiser saber mais.

## O que vais construir

Este é o problema, o mesmo do exemplo guiado do [guia 04 da algoritmia](../../01-algoritmos/04-repeticao-e-arrays.md), com uma mudança na segunda parte:

> A escola organiza uma campanha de recolha de alimentos. Cada turma entrega os alimentos que juntou, e a funcionária escreve quantos quilos a turma trouxe, um número inteiro. Uma turma pode não ter trazido nada, e nesse caso a funcionária escreve 0. Quando não há mais turmas, escreve -1. O programa mostra quantas turmas entregaram, o total de quilos e a média por turma, mas a média só se houver pelo menos uma turma.
>
> No fim da campanha, a diretora quer o resumo das 6 turmas do 10.º ano. O programa pede os quilos de cada turma, pela ordem, e mostra o total e a média. Mostra também quantas turmas chegaram à meta de cada turma, 10 kg.

A fase 6, opcional, acrescenta uma regra à segunda parte. Um número negativo é um engano, e o programa pede outra vez os quilos dessa turma.

No laboratório do tema anterior, o `balanco.py` recebia as turmas já contadas e os quilos já somados. Agora é o programa que conta e soma, à medida que as turmas entregam.

No fim, tens dois programas na tua pasta `fp-python`, um para cada parte. O primeiro, `campanha.py`, lê os quilos até aparecer o -1. Com 12, 0, 9 e -1, o ecrã fica assim:

```text
Quilos entregues pela turma (-1 para terminar)? 12
Quilos entregues pela turma (-1 para terminar)? 0
Quilos entregues pela turma (-1 para terminar)? 9
Quilos entregues pela turma (-1 para terminar)? -1
Turmas que entregaram: 3
Total: 21 kg
Média por turma: 7.0 kg
```

O segundo, `campanha_10ano.py`, pede os quilos das 6 turmas, uma a uma. Na fase 6, que é opcional, passa também a recusar os números negativos, como neste ecrã:

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

Pelo caminho, ficas a saber escrever um ciclo `while` e um ciclo `for` e ler valores até uma sentinela. Ficas a saber contar e somar dentro de um ciclo, e calcular uma média sem dividir por zero. Ficas também a saber prever quantas voltas dá um ciclo e confirmá-lo no computador, com uma **tabela de iterações prevista e observada**. E provocas de propósito os erros mais frequentes dos ciclos, para os reconheceres quando aparecerem sem querer.

| Fase | O que muda | O que funciona no fim |
| --- | --- | --- |
| 1 | `campanha.py`, com um `while` e a sentinela | O programa lê turmas até ao -1 e conta-as |
| 2 | `campanha.py`, com um acumulador e linhas de observação | O programa soma os quilos, e a tabela observada confirma a prevista |
| 3 | `campanha.py`, com um `if` depois do ciclo | O programa mostra a média, só quando há turmas |
| 4 | `campanha_10ano.py`, com um `for` e o `range` | O programa pede os quilos das 6 turmas e mostra o total e a média |
| 5 | `campanha_10ano.py`, com um contador dentro de um `if` | O programa conta as turmas que chegaram à meta |
| 6, opcional | `campanha_10ano.py`, com uma validação repetida dentro do `for` | O programa não aceita quilos negativos |

No fim, a tua pasta tem, além dos ficheiros dos laboratórios anteriores, estes dois:

```text
fp-python/
├── campanha.py
└── campanha_10ano.py
```

## Palavras que vais usar

- Ciclo: uma parte do programa que se executa várias vezes seguidas. Para saber mais, vê a secção "Os ciclos em Python" do [guia](../04-ciclos-while-e-for.md).
- Volta: cada execução do corpo de um ciclo. O nome técnico é iteração.
- Corpo do ciclo: as linhas indentadas debaixo do `while` ou do `for`, que se repetem.
- `while`: o `Enquanto` do Python. Repete o corpo enquanto a condição der `True`.
- As três peças de um ciclo: a inicialização, a condição e a atualização.
- Inicialização: o que se faz antes do ciclo, para as variáveis terem o primeiro valor.
- Condição: a pergunta da linha do `while`, que diz quando continuar.
- Atualização: a linha do corpo que muda a variável da condição e aproxima o ciclo do fim.
- Sentinela: o valor combinado que quer dizer "acabou", e que nenhum dado verdadeiro pode ter, como o -1 da campanha.
- Leitura antecipada: a leitura do primeiro valor, antes do ciclo.
- Contador: uma variável que conta quantas vezes uma coisa aconteceu, como `turmas = turmas + 1`.
- Acumulador: uma variável que vai somando valores, como `total_quilos = total_quilos + quilos`.
- Tabela de iterações: uma tabela com uma linha por cada teste da condição, com o valor das variáveis nesse momento. A **prevista** fazes tu, antes de correr; a **observada** escreve-a o computador.
- Linha de observação: um `print` provisório que mostra o valor das variáveis, para veres as voltas. Tira-se quando acabas de observar.
- Ciclo infinito: um ciclo cuja condição nunca chega a dar `False`.
- Ctrl+C: as teclas que param, no terminal, um programa que está a correr. Também no macOS é a tecla Control, e não a Cmd.
- `for`: o `Para` do Python. Dá à variável de controlo cada número de uma sequência, um por volta.
- Variável de controlo: a variável que o `for` vai mudando, um valor por volta.
- `range`: a função que produz a sequência de números do `for`. `range(1, 7)` dá 1, 2, 3, 4, 5 e 6: o início entra e o fim não entra.
- Validação repetida: pedir um valor outra vez, enquanto for inválido.
- Ciclo dentro de outro: um ciclo que fica no corpo de outro ciclo. Na fase 6, opcional, é um `while` dentro do `for`.

## O que precisas

- A pasta `fp-python`, aberta no VS Code, a mesma dos laboratórios anteriores. Se não a tiveres, cria-a, por exemplo em Documentos, e abre-a no menu File, com a opção Open Folder....
- O terminal do VS Code, no menu Terminal, com a opção New Terminal. O texto antes do cursor deve acabar em `fp-python`.
- O Python 3. Confirma com `python --version`, ou `python3 --version` no macOS: o primeiro número tem de ser 3.

Neste laboratório, onde o texto diz `python`, usa o comando que funciona no teu computador. No Windows, se o `python` não funcionar, é `py`. No macOS, é `python3`.

Os resultados e as mensagens de erro deste laboratório são os do Python 3.14. Num Python mais antigo, uma mensagem pode ter outras palavras, ou não ter os sinais por baixo da linha. O nome do erro, a palavra antes dos dois pontos na última linha, é o mesmo. O caminho do ficheiro nas mensagens, como `C:\Users\aluno\Documents\fp-python\campanha.py`, muda de computador para computador.

## Se alguma coisa falhar

1. Guardaste o ficheiro? O Python corre o que está guardado no disco, e não o que vês no ecrã. Guarda com Ctrl+S, ou Cmd+S no macOS, antes de cada vez que corres.
2. Estás na pasta certa? O texto antes do cursor, no terminal, tem de acabar em `fp-python`. Se não acabar, abre um terminal novo, no menu Terminal, com a opção New Terminal.
3. O programa não volta ao terminal? Olha para a última linha do ecrã. Se for uma pergunta, está à espera que escrevas um número e carregues em Enter. Se já respondeste e nada acontece, ou se o ecrã se enche com a mesma linha, pode ser um ciclo infinito. Clica no terminal e carrega em Ctrl+C. Se escreves -1 e o programa volta a perguntar, falta o `int` na leitura do fim do corpo, como dizem os problemas frequentes.
4. Copiaste o código à mão? Confirma os dois pontos no fim das linhas do `while`, do `for`, do `if` e do `else`. Confirma também os quatro espaços de cada nível de indentação.

## Fase 1: Repetir até à sentinela, com `while`

A funcionária não sabe quantas turmas vão entregar. Por isso, o programa lê valores até aparecer o -1, a sentinela, o valor combinado que quer dizer "acabou". O 0 não pode ser a sentinela, porque uma turma pode não trazer nada. Um ciclo assim é um `while`, o `Enquanto` do Python: repete o corpo enquanto a condição der `True`. Nesta fase, o programa só conta as turmas.

No pseudocódigo, esta parte era assim:

```text
const SENTINELA = -1
int turmas = 0
Escreve: "Quilos entregues pela turma (-1 para terminar)?"
int quilos = ler valor
Enquanto quilos != SENTINELA
    turmas = turmas + 1
    Escreve: "Quilos entregues pela turma (-1 para terminar)?"
    quilos = ler valor
Escreve: "Turmas que entregaram: ", turmas
```

Em Python, o `Enquanto` passa a `while`, com dois pontos no fim da linha. As linhas do corpo ficam indentadas quatro espaços, como no pseudocódigo. Cada par de `Escreve:` e `ler valor` junta-se num `input`, com o `int` a converter o texto lido num número. Para saber mais, lê a secção "Repetir com `while`" do [guia](../04-ciclos-while-e-for.md).

1. No painel Explorer, cria um ficheiro novo, com o nome `campanha.py`, como nos laboratórios anteriores. Escreve nele este conteúdo, que é o ficheiro completo:

   ```python
   # campanha.py: a campanha de recolha de alimentos da escola.
   # Lê os quilos de cada turma até aparecer a sentinela -1 e conta as turmas.

   SENTINELA = -1

   turmas = 0
   quilos = int(input("Quilos entregues pela turma (-1 para terminar)? "))
   while quilos != SENTINELA:
       turmas = turmas + 1
       # Ler o valor seguinte é a atualização: sem esta linha, o ciclo nunca acabava.
       quilos = int(input("Quilos entregues pela turma (-1 para terminar)? "))
   print("Turmas que entregaram:", turmas)
   ```

   Leitura guiada: lê-o pelas três peças do ciclo. A inicialização são as duas linhas antes do `while`. O contador `turmas` começa em 0, e o primeiro valor lê-se antes do ciclo: é a leitura antecipada. A condição é `quilos != SENTINELA`, "os quilos lidos não são o -1". O corpo são as duas instruções indentadas. A primeira conta a turma, e a última lê os quilos da turma seguinte. O `print` final está encostado à margem, fora do ciclo, e só se executa quando o ciclo termina. Quando carregas em Enter depois dos dois pontos do `while`, o VS Code começa sozinho a linha seguinte com os quatro espaços.

2. Guarda. Vais correr o programa três vezes, com os três casos que a algoritmia manda testar num ciclo: zero voltas, uma volta e várias voltas. Antes de correres, prevê, para cada linha desta tabela, quantas voltas dá o ciclo e o que aparece no fim:

   | Valores escritos, por ordem | Voltas previstas | Turmas que entregaram | Porque é que este caso foi escolhido |
   | --- | ---: | ---: | --- |
   | -1 | | | Zero voltas: ninguém entregou |
   | 15, -1 | | | Uma só volta |
   | 12, 0, 9, -1 | | | Várias voltas, com uma turma que trouxe 0 |

   A resposta: 0 voltas e 0 turmas; 1 volta e 1 turma; 3 voltas e 3 turmas. O ciclo dá uma volta por turma, e o -1 nunca é contado.

3. Corre o programa com o terceiro caso:

   ```bash
   python campanha.py
   ```

   O programa escreve a pergunta e fica à espera. Escreve `12` e carrega em Enter. Faz o mesmo com `0`, com `9` e com `-1`. O que deves ver:

   ```text
   Quilos entregues pela turma (-1 para terminar)? 12
   Quilos entregues pela turma (-1 para terminar)? 0
   Quilos entregues pela turma (-1 para terminar)? 9
   Quilos entregues pela turma (-1 para terminar)? -1
   Turmas que entregaram: 3
   ```

   Os números a seguir a cada pergunta são os que tu escreveste. Isto quer dizer que o ciclo deu três voltas, uma por turma, e terminou no -1, que não foi contado. O 0 foi contado como turma, como o enunciado pede.

4. Corre outra vez, com o segundo caso, 15 e -1. O que deves ver no fim: `Turmas que entregaram: 1`. Depois corre com o primeiro caso, só -1. O que deves ver:

   ```text
   Quilos entregues pela turma (-1 para terminar)? -1
   Turmas que entregaram: 0
   ```

   O ciclo deu zero voltas, porque a condição `-1 != -1` deu `False` logo no primeiro teste. Confirma que as voltas observadas são as que previste.

5. Provoca um erro de propósito: tira a atualização. Na última linha do corpo, a do `input`, põe um `#` antes do `quilos`, para ela passar a comentário. Guarda e corre, e escreve `12`. O que deves ver: depois do 12, não aparece mais nada, e o programa não volta ao terminal. Parece parado, mas está a dar voltas sem fim, muito depressa. Sem a atualização, `quilos` vale sempre 12, e a condição `12 != -1` dá sempre `True`. É um ciclo infinito.

   Clica dentro do terminal e carrega em Ctrl+C: segura a tecla Ctrl e carrega na tecla C. O que deves ver no fim do ecrã:

   ```text
   Quilos entregues pela turma (-1 para terminar)? 12
   ^CTraceback (most recent call last):
     File "C:\Users\aluno\Documents\fp-python\campanha.py", line 9, in <module>
       turmas = turmas + 1
       ^^^^^^
   KeyboardInterrupt
   ```

   O `^C` mostra que carregaste em Ctrl+C. A última linha, `KeyboardInterrupt`, quer dizer "interrupção pelo teclado". A mensagem aponta a linha onde o programa estava quando o paraste, a 9 ou a 8, e não a linha do erro. O erro é a linha que falta. Para corrigir, tira o `#` que puseste, guarda e corre outra vez com 15 e -1, para confirmares que o programa voltou a terminar.

### Paragem 1

O `campanha.py` lê turmas até ao -1 e conta-as. Os três casos dão as voltas que previste.

Pensa antes de continuares: o que acontecia se a sentinela fosse o 0? A resposta: com 12, 0, 9, -1, o programa parava no 0 e contava só 1 turma. O 9 nunca era lido, e o -1 ficava sem sentido. O 0 é um dado verdadeiro, o de uma turma que não trouxe nada, e por isso não pode querer dizer "acabou".

## Fase 2: Somar os quilos, e observar as voltas

Falta o total de quilos. Para isso não basta contar, é preciso somar. Um acumulador é uma variável que vai somando valores ao longo das voltas. Começa em 0, antes do ciclo, e em cada volta soma o valor dessa volta. O contador soma sempre 1; o acumulador soma o próprio valor. Nesta fase vais também confirmar as voltas com uma tabela de iterações prevista e observada. Para saber mais, lê as secções "O contador e o acumulador" e "Ver as voltas: a tabela de iterações prevista e observada" do [guia](../04-ciclos-while-e-for.md).

1. Em `campanha.py`, faz três alterações. Depois de `turmas = 0`, acrescenta a linha `total_quilos = 0`. Dentro do corpo, depois de `turmas = turmas + 1`, acrescenta `total_quilos = total_quilos + quilos`, com os mesmos quatro espaços. No fim do ficheiro, acrescenta `print("Total:", total_quilos, "kg")`, encostado à margem. Muda também a segunda linha do comentário do topo, porque o programa passou a somar. O ficheiro completo fica assim:

   ```python
   # campanha.py: a campanha de recolha de alimentos da escola.
   # Lê os quilos de cada turma até aparecer a sentinela -1, conta as turmas e soma os quilos.

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
   ```

   Leitura guiada: o acumulador `total_quilos` nasce antes do ciclo, ao lado do contador, com 0, porque a soma de nada é zero. Dentro do corpo, cada volta soma os quilos da turma. A soma vem antes da leitura seguinte, porque tem de usar os quilos desta volta, e não os da próxima. O total só se escreve depois do ciclo, quando todas as turmas estão somadas.

2. Antes de correres, prevê a tabela de iterações para 12, 0, 9 e -1. Tem uma linha por cada teste da condição, com o valor das variáveis no momento do teste, nestas colunas:

   | Teste | quilos | turmas | total_quilos | Condição |
   | --- | ---: | ---: | ---: | --- |

   A resposta:

   | Teste | quilos | turmas | total_quilos | Condição |
   | --- | ---: | ---: | ---: | --- |
   | 1.º | 12 | 0 | 0 | `12 != -1` dá `True` |
   | 2.º | 0 | 1 | 12 | `0 != -1` dá `True` |
   | 3.º | 9 | 2 | 12 | `9 != -1` dá `True` |
   | 4.º | -1 | 3 | 21 | `-1 != -1` dá `False` |

   No 3.º teste, o total ainda é 12. A turma que trouxe 0 foi somada durante a 2.ª volta, e somar 0 não muda nada.

3. Agora vais observar as voltas no computador, com linhas de observação: `print` provisórios que mostram as variáveis. Acrescenta uma como primeira linha do corpo, logo a seguir à linha do `while`, com quatro espaços:

   ```python
       # Linha de observação: tira-a quando acabares de ver as voltas.
       print("(observação) quilos =", quilos, "turmas =", turmas, "total =", total_quilos)
   ```

   Acrescenta outra logo a seguir ao ciclo, encostada à margem, antes do primeiro `print` do resultado:

   ```python
   # Linha de observação: o estado no teste que deu False.
   print("(observação) quilos =", quilos, "turmas =", turmas, "total =", total_quilos)
   ```

   A primeira executa-se no início de cada volta, logo depois de a condição dar `True`. A segunda executa-se uma só vez, quando a condição acabou de dar `False`. Cada uma corresponde a uma linha da tabela prevista do passo 2.

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

   As quatro linhas de observação são a tabela observada. Compara-as, uma a uma, com as quatro linhas da tabela prevista do passo 2. Se forem iguais, o ciclo fez o que previste. Se a tua previsão tinha outro valor numa linha, procura o engano: foi na previsão ou no programa?

5. Provoca um erro de propósito: o acumulador a começar dentro do ciclo. Corta a linha `total_quilos = 0` de onde está. Cola-a como primeira linha do corpo, logo a seguir à linha do `while`, com quatro espaços. Fica antes do comentário da linha de observação. Guarda, corre e escreve 12, 0, 9 e -1. O que deves ver:

   ```text
   Quilos entregues pela turma (-1 para terminar)? 12
   (observação) quilos = 12 turmas = 0 total = 0
   Quilos entregues pela turma (-1 para terminar)? 0
   (observação) quilos = 0 turmas = 1 total = 0
   Quilos entregues pela turma (-1 para terminar)? 9
   (observação) quilos = 9 turmas = 2 total = 0
   Quilos entregues pela turma (-1 para terminar)? -1
   (observação) quilos = -1 turmas = 3 total = 9
   Turmas que entregaram: 3
   Total: 9 kg
   ```

   Não aparece nenhuma mensagem de erro, mas o total é 9, e não 21. É um erro de lógica, e a tabela observada mostra onde: no início de cada volta, o total volta a 0. Dentro do ciclo, a linha `total_quilos = 0` executa-se em cada volta e apaga a soma das voltas anteriores. No fim, fica só com o último valor, o 9. Se correres agora só com -1, o ciclo dá zero voltas, e a linha `total_quilos = 0` nunca se executa. A variável nunca chega a existir, e o `print` de observação para o programa com `NameError: name 'total_quilos' is not defined`.

   Para corrigir, volta a pôr a linha `total_quilos = 0` antes do ciclo, encostada à margem, logo a seguir a `turmas = 0`.

6. Tira as duas linhas de observação e os comentários delas, ou põe um `#` no início de cada `print` de observação. Guarda e corre os três casos da fase 1. O que deves ver no fim de cada um: `Total: 0 kg` com -1; `Total: 15 kg` com 15 e -1; `Total: 21 kg` com 12, 0, 9 e -1.

### Paragem 2

O `campanha.py` conta as turmas e soma os quilos, e as linhas de observação já saíram. No caso 12, 0, 9, -1, a tabela observada coincidiu com a prevista.

Pensa antes de continuares: com o acumulador dentro do ciclo, o caso 15, -1 dava o total certo, 15. Porquê? A resposta: com uma só volta, o último valor é também a soma de todos. É por isso que se testam sempre várias voltas: um acumulador que recomeça em cada volta só se nota a partir da segunda.

## Fase 3: A média só quando há turmas, com `if`

Falta a média: o total a dividir pelo número de turmas. Com zero turmas, a conta seria 0 / 0, que não tem resultado, e o Python parava o programa com `ZeroDivisionError: division by zero`. Por isso, como no pseudocódigo, a média calcula-se só se houver pelo menos uma turma, com o `if` e o `else` do tema anterior. O `if` fica depois do ciclo, encostado à margem, porque a média só faz sentido quando todas as turmas estão contadas. Para saber mais, lê a secção "A média, só quando há valores" do [guia](../04-ciclos-while-e-for.md).

1. Em `campanha.py`, acrescenta estas linhas no fim do ficheiro, depois do último `print`, encostadas à margem:

   ```python
   # Sem este if, com zero turmas, a conta seria 0 / 0 e o programa parava.
   if turmas > 0:
       media = total_quilos / turmas
       print("Média por turma:", media, "kg")
   else:
       print("Não houve entregas, por isso não há média.")
   ```

   Leitura guiada: o `if` está na mesma margem do `while`, e por isso está fora do ciclo: avalia-se uma só vez, quando o ciclo acabou. As duas linhas do primeiro bloco executam-se só quando `turmas > 0` dá `True`. O `else` fica na margem do `if`, e o seu bloco executa-se nos outros casos, isto é, quando não houve nenhuma turma.

2. Muda o comentário do topo, para dizer que o programa também mostra a média. Guarda.

3. Corre os três casos. Antes de correres, prevê como aparece a média de 21 quilos por 3 turmas. O que deves ver no fim de cada caso:

   | Valores escritos | As últimas linhas do ecrã |
   | --- | --- |
   | 12, 0, 9, -1 | `Turmas que entregaram: 3`, `Total: 21 kg`, `Média por turma: 7.0 kg` |
   | 15, -1 | `Turmas que entregaram: 1`, `Total: 15 kg`, `Média por turma: 15.0 kg` |
   | -1 | `Turmas que entregaram: 0`, `Total: 0 kg`, `Não houve entregas, por isso não há média.` |

   A média aparece como `7.0`, e não como 7, porque a divisão com `/` dá sempre um `float`. No caso do -1, o programa escreve a mensagem e nunca chega à divisão. Se aparecer `ZeroDivisionError` nesse caso, o `if` não está no sítio certo, ou falta-lhe o `turmas > 0`.

### Paragem 3

O `campanha.py` está completo. Faz o mesmo que o algoritmo do guia 04 da algoritmia, nos mesmos três casos. Confere o teu com este:

```python
# campanha.py: a campanha de recolha de alimentos da escola.
# Lê os quilos de cada turma até aparecer a sentinela -1, conta as turmas,
# soma os quilos e mostra a média por turma, só quando houve entregas.

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

Pensa antes de continuares: porque é que o `if` da média não pode ficar dentro do ciclo, com quatro espaços? A resposta: dentro do ciclo, calculava e escrevia uma média em cada volta, com a contagem e a soma a meio. Com 12, 0, 9, -1, apareciam três médias, e só a última estava certa. E no caso do -1, com zero voltas, não aparecia nenhuma linha sobre a média.

## Fase 4: As 6 turmas do 10.º ano, com `for`

A segunda parte do problema é diferente. O 10.º ano tem 6 turmas, e por isso, antes de o ciclo começar, já se sabe que vai dar 6 voltas. A um ciclo assim chama-se ciclo contado. Com o `while`, terias de escrever as três peças à mão. O `Para` do pseudocódigo resolvia isto, e em Python é o `for`, com o `range`. O `range(1, 7)` produz os números 1, 2, 3, 4, 5 e 6: o primeiro entra, e o segundo não entra. O `for` dá à variável `turma` cada um desses números, um por volta. Para saber mais, lê a secção "Contar voltas com `for` e `range`" do [guia](../04-ciclos-while-e-for.md).

Como estes dados são outros, e não terminam com o -1, ficam noutro programa. Assim, cada ensaio da segunda parte não obriga a passar pela primeira.

1. Cria um ficheiro novo, `campanha_10ano.py`, com este conteúdo, que é o ficheiro completo:

   ```python
   # campanha_10ano.py: os quilos das 6 turmas do 10.º ano, no fim da campanha.
   # Pede os quilos de cada turma, pela ordem, e mostra o total e a média.

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

   Leitura guiada: começa pela linha do `for`. Lê-se "para `turma` em cada número de 1 a 6". O `range(1, NUMERO_DE_TURMAS + 1)` é o `range(1, 7)`. É a tradução do `Para turma de 1 até NUMERO_DE_TURMAS`. O corpo tem duas linhas. A primeira pergunta os quilos da turma desta volta: o `str(turma)` transforma o número num texto, e o `+` junta-o ao resto da pergunta. A segunda soma os quilos ao acumulador. Não há atualização escrita, porque é o `for` que passa ao número seguinte. Depois do ciclo, a média divide pelo número de turmas, que é sempre 6.

2. Guarda. Antes de correres, prevê quantas perguntas faz o programa e qual é o número da última turma que pergunta. Prevê também o total e a média com 12, 0, 9, 15, 6 e 18. Depois corre:

   ```bash
   python campanha_10ano.py
   ```

   Escreve os seis valores, um a seguir a cada pergunta. O que deves ver:

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

   Isto quer dizer que o ciclo deu 6 voltas, com `turma` de 1 a 6. O total é 60, e a média é 60 / 6, que dá 10.0.

3. Provoca um erro de propósito: o fim do `range` errado. Na linha do `for`, tira o `+ 1`, para ficar `range(1, NUMERO_DE_TURMAS)`. Antes de correres, prevê quantas perguntas aparecem. Guarda, corre e escreve 12, 0, 9, 15 e 6. O que deves ver:

   ```text
   Quilos da turma 1? 12
   Quilos da turma 2? 0
   Quilos da turma 3? 9
   Quilos da turma 4? 15
   Quilos da turma 5? 6
   Total do 10.º ano: 42 kg
   Média por turma: 7.0 kg
   ```

   O programa só perguntou 5 turmas, porque o `range(1, 6)` para antes do 6. A turma 6 ficou de fora, e a média também ficou errada: divide por 6 o total de só 5 turmas. O Python não deu nenhuma mensagem: o programa está bem escrito e faz outra coisa. É um erro de lógica, e só se vê porque confirmaste o número da última pergunta.

4. Experimenta agora a outra forma do `Para`. Muda a linha do `for` para `for turma in range(NUMERO_DE_TURMAS):`. O `range(6)` é o mesmo que `range(0, 6)`, e corresponde ao `Para turma = 0, turma < 6, turma++` do pseudocódigo. Antes de correres, prevê o número da primeira e da última pergunta. Guarda e corre. O que deves ver nas perguntas: `Quilos da turma 0?` até `Quilos da turma 5?`. Dá 6 voltas, e o total fica certo, mas a numeração começa em 0, e na escola não há turma 0. Para estas perguntas, a forma certa é a primeira, de 1 a 6.

5. Volta a pôr a linha como estava no passo 1: `for turma in range(1, NUMERO_DE_TURMAS + 1):`. Guarda e corre outra vez com os seis valores, para confirmares o ecrã do passo 2.

### Paragem 4

O `campanha_10ano.py` pede os quilos das 6 turmas, de 1 a 6, e mostra o total e a média.

Pensa antes de continuares: neste programa, a média não precisa do `if` que tinha no `campanha.py`. Porquê? A resposta: aqui o número de turmas é sempre 6, e por isso a divisão nunca é por zero. No `campanha.py`, o número de turmas dependia do que a funcionária escrevia, e podia ser 0.

## Fase 5: Contar as turmas que chegaram à meta

A diretora quer saber também quantas turmas chegaram à meta de cada turma, 10 kg ou mais. Não é a meta da campanha inteira, que se mede pelo total. É um contador, mas que não aumenta em todas as voltas. Só aumenta nas voltas em que a turma chegou à meta. Para isso, a linha do aumento vai para dentro de um `if`, com oito espaços. Quatro põem-na dentro do `for`, e os outros quatro põem-na dentro do `if`. Para saber mais, lê a secção "Contar só algumas voltas" do [guia](../04-ciclos-while-e-for.md).

1. Em `campanha_10ano.py`, faz quatro alterações. Depois de `NUMERO_DE_TURMAS = 6`, acrescenta `META = 10`. Depois de `total_quilos = 0`, acrescenta `na_meta = 0`. No fim do corpo do `for`, depois da soma, acrescenta estas três linhas, com a indentação que mostram:

   ```python
       # Dentro do if, o contador só aumenta nas voltas em que a turma chegou à meta.
       if quilos >= META:
           na_meta = na_meta + 1
   ```

   No fim do ficheiro, encostada à margem, acrescenta `print("Turmas que chegaram à meta:", na_meta)`. Muda também o comentário do topo, como está no ficheiro completo da paragem 5.

   Leitura guiada: o `if` tem quatro espaços, e por isso está dentro do `for`: avalia-se em todas as voltas, uma vez por turma. A linha do aumento tem oito espaços, e por isso só se executa quando `quilos >= META` dá `True`. O contador `na_meta` nasce antes do ciclo, com 0, como todos os contadores, e só se escreve depois do ciclo.

2. Guarda. Antes de correres, prevê quantas turmas chegam à meta com 12, 0, 9, 15, 6 e 18. Corre e escreve-os. O que deves ver no fim:

   ```text
   Total do 10.º ano: 60 kg
   Média por turma: 10.0 kg
   Turmas que chegaram à meta: 3
   ```

   São as turmas 1, 4 e 6, com 12, 15 e 18. As outras ficaram abaixo dos 10 kg.

3. Corre outra vez, com um caso que testa a fronteira: 10, 9, 10, 11, 0 e 20. Antes de correres, prevê o resultado: uma turma com 10 kg exatos chegou à meta? O que deves ver no fim: `Turmas que chegaram à meta: 4`. As duas turmas com 10 kg contam, porque a condição usa `>=`, "maior ou igual". A turma com 9 não conta.

4. Provoca um erro de propósito: a fronteira trocada. Muda a condição para `quilos > META`, sem o igual. Corre com o primeiro caso, 12, 0, 9, 15, 6 e 18. O que deves ver: `Turmas que chegaram à meta: 3`, igual ao de antes, porque nenhuma turma trouxe 10 kg exatos. O erro está lá, mas este caso não o mostra. Corre agora com o caso da fronteira. O que deves ver: `Turmas que chegaram à meta: 2`, quando deviam ser 4. Só o caso com o 10 apanhou o erro. Volta a pôr o `>=`, guarda e corre outra vez o caso da fronteira, para confirmares que voltou a dar 4.

### Paragem 5

O `campanha_10ano.py` conta as turmas que chegaram à meta, e o caso da fronteira dá 4. Se não fizeres a fase 6, opcional, é este o programa final. Confere o teu com este:

```python
# campanha_10ano.py: os quilos das 6 turmas do 10.º ano, no fim da campanha.
# Pede os quilos de cada turma, pela ordem, mostra o total e a média,
# e conta as turmas que chegaram à meta de 10 kg.

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

Pensa antes de continuares: se a linha `na_meta = na_meta + 1` ficasse só com quatro espaços, alinhada com o `if`, o que acontecia? A resposta: o `if` ficava sem nenhuma linha dentro, e o Python recusava o programa com `IndentationError: expected an indented block after 'if' statement on line 15`. Depois dos dois pontos, o Python espera pelo menos uma linha indentada. E se tirasses também o `if`, a linha passava a contar todas as voltas, e o resultado era sempre 6.

## Fase 6, opcional: Não aceitar quilos negativos, com uma validação repetida

Esta fase é opcional, porque traz uma ideia nova: um ciclo dentro de outro. Até aqui, cada programa tinha um só ciclo. Já o fizeste em pseudocódigo, no projeto 2 da algoritmia, com a validação da nota dentro de um `Para`.

Ninguém traz quilos negativos. Um número negativo só pode ser um engano a escrever, e o programa não o deve somar. A solução é pedir o valor outra vez, enquanto for negativo: uma validação repetida. É um `while` dentro do `for`, o ciclo dentro de outro. Em cada volta do `for`, o `while` dá todas as suas voltas: volta a perguntar os quilos da mesma turma até o valor ser válido. Só depois o valor é somado e comparado com a meta. Para saber mais, lê a secção "Validação repetida" do [guia](../04-ciclos-while-e-for.md).

1. Em `campanha_10ano.py`, logo a seguir à linha do `input` que está dentro do `for`, acrescenta estas três linhas, com a indentação que mostram. Muda também o comentário do topo, como está no ficheiro completo da paragem 6.

   ```python
       # Validação repetida: um número negativo é um engano, e a pergunta repete-se.
       while quilos < 0:
           quilos = int(input("Não pode ser negativo. Quilos da turma " + str(turma) + "? "))
   ```

   Leitura guiada: o `while` tem quatro espaços, e por isso está dentro do `for`: em cada volta, há uma validação. As três peças estão lá. A inicialização é a leitura que já existia, logo antes do `while`. A condição é `quilos < 0`, "os quilos são negativos". A atualização é a leitura dentro do `while`, com oito espaços, que pergunta outra vez pela mesma turma. Quando o `while` termina, os quilos são de certeza 0 ou mais, e só então o programa chega à soma e ao `if` da meta.

2. Guarda. Antes de correres, prevê o ecrã com 12, -5, 0, 9, 15, 6 e 18. Em que pergunta aparece o aviso, e qual é o total? Corre e escreve os valores pela ordem. O que deves ver:

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

   O -5 foi recusado, e a turma 2 foi perguntada outra vez. O total é 60, como sem o engano, porque o -5 nunca foi somado. Repara que o programa continua a fazer só 6 perguntas de turmas: a pergunta repetida não conta como turma nova.

3. Corre outra vez, com -2, -1 e depois os seis valores de sempre, 12, 0, 9, 15, 6 e 18. O que deves ver no início:

   ```text
   Quilos da turma 1? -2
   Não pode ser negativo. Quilos da turma 1? -1
   Não pode ser negativo. Quilos da turma 1? 12
   ```

   O `while` deu duas voltas na turma 1. Neste programa, o -1 não é sentinela: é só mais um número negativo, e é recusado. A sentinela é do `campanha.py`, que não sabe quantas turmas vão entregar. O `campanha_10ano.py` já sabe que são 6. O fim do ecrã é o mesmo do passo 2.

### Paragem 6

O `campanha_10ano.py` está completo. Pede os quilos das 6 turmas, recusa os negativos, e mostra o total, a média e as turmas que chegaram à meta. Confere o teu com este:

```python
# campanha_10ano.py: os quilos das 6 turmas do 10.º ano, no fim da campanha.
# Pede os quilos de cada turma, pela ordem, sem aceitar valores negativos,
# mostra o total e a média, e conta as turmas que chegaram à meta de 10 kg.

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

Pensa antes de terminares: o que acontecia se o `while` da validação ficasse depois da linha da soma, e não antes? A resposta: o -5 era somado antes de ser recusado. Com 12, -5, 0, 9, 15, 6 e 18, o total dava 55, e não 60, e a média 9.166666666666666. A validação tem de vir antes de o valor ser usado.

## Problemas frequentes

### O programa não volta ao terminal e não mostra nada de novo

Olha para a última linha do ecrã. Se for uma pergunta, o programa está à espera que escrevas um número e carregues em Enter. Se já respondeste e nada acontece, é provável que seja um ciclo infinito sem `print` no corpo. Carrega em Ctrl+C no terminal e confirma a atualização do ciclo: no `campanha.py`, é a leitura no fim do corpo.

### O ecrã enche-se com a mesma linha, sem parar

É um ciclo infinito com um `print` no corpo. Carrega em Ctrl+C no terminal, com a tecla Control, também no macOS. Depois procura a atualização que falta, ou que ficou fora do corpo por causa da indentação.

### `SyntaxError: expected ':'`

Faltam os dois pontos no fim da linha do `while`, do `for`, do `if` ou do `else`. O `^` da mensagem aponta para o sítio onde eles faltam.

### `IndentationError: expected an indented block after 'while' statement on line 10`

A linha a seguir ao `while` não tem os quatro espaços. Depois dos dois pontos, o Python espera pelo menos uma linha indentada. A mensagem diz em que linha está o `while`, e, com um `for` ou um `if`, diz `'for'` ou `'if'`. Põe quatro espaços no início de cada linha do corpo.

### `ValueError: invalid literal for int() with base 10: ''`

Carregaste em Enter sem escrever nenhum número. O `int` recebeu um texto vazio, `''`, e não o conseguiu converter. Com uma letra, como `doze`, a mensagem acaba em `'doze'`. Corre o programa outra vez e escreve só números inteiros. Neste laboratório, quem usa o programa tem de escrever um número.

### Escrevo -1 e o programa continua a perguntar

Na fase 1, falta o `int` na leitura do fim do corpo do `while`. O -1 fica guardado como o texto `"-1"`, e um texto nunca é igual a um número. A condição `quilos != SENTINELA` continua a dar `True`, e o programa não termina, sem nenhuma mensagem de erro. Confirma que as duas leituras têm `int(input(...))`. A partir da fase 2, o mesmo erro aparece de outra maneira, como diz o problema seguinte.

### `TypeError: unsupported operand type(s) for +: 'int' and 'str'`

Na leitura do fim do corpo do `while`, falta o `int`. Com o primeiro valor, tudo funciona, porque a leitura antes do ciclo tem o `int`. Na segunda volta, `quilos` guarda um texto, e a soma `total_quilos + quilos` falha, porque o Python não soma um número com um texto. A mensagem aponta a linha da soma, mas a causa está na leitura. Confirma que as duas leituras têm `int(input(...))`.

### `ZeroDivisionError: division by zero`

No `campanha.py`, com o -1 logo à primeira, o programa tentou calcular a média com zero turmas. Confirma que a divisão está dentro do `if turmas > 0:`, e que o `if` está depois do ciclo, encostado à margem.

### A média aparece com muitas casas decimais, como `9.166666666666666`

Não é um erro: a divisão não acaba, e o Python mostra as casas todas. Se quiseres menos casas, usa o `round` do tema 02, como `round(media, 1)`.

### O resultado está errado e não aparece nenhuma mensagem

É um erro de lógica. Acrescenta linhas de observação, uma na primeira linha do corpo e outra logo a seguir ao ciclo. Depois compara a tabela observada com a prevista, linha a linha. A primeira linha diferente diz em que volta o programa se afastou do que esperavas. Confirma também o número de voltas: o fim do `range` não entra.

## Desafios

1. No `campanha.py`, conta também as turmas que não trouxeram nada, com 0 kg, e escreve o número delas depois de `Turmas que entregaram`. Testa com 12, 0, 9, -1, que deve dar 1, e com um caso só de turmas sem nada. Pista: é um contador que não aumenta em todas as voltas.
2. No `campanha_10ano.py`, em vez das 6 turmas fixas, pergunta primeiro quantas turmas tem o 10.º ano. Aceita só um número de 1 a 10. Depois pede os quilos de cada uma. Testa com 0, 11 e 1, e com 6 e os valores de sempre. Pista: o número de turmas lido vai para o `range` e para a divisão da média. A média precisa do `if`?
3. No `campanha.py`, não aceites quilos negativos, exceto o -1, que continua a ser a sentinela. Com 12, -5, 0, 9 e -1, o programa recusa o -5, pergunta outra vez, e no fim mostra 3 turmas e 21 kg. Pista: no `campanha.py` há duas leituras, e as duas têm de ser validadas. Que condição é verdadeira para o -5 e falsa para o -1?

## Antes de terminares

- [ ] O `campanha.py` dá o resultado certo nos três casos: -1; 15 e -1; 12, 0, 9 e -1.
- [ ] O `campanha_10ano.py` pergunta as turmas de 1 a 6. Com 12, 0, 9, 15, 6 e 18, dá 60 kg, 10.0 kg e 3 turmas na meta. Se fizeste a fase 6, opcional, também recusa os negativos.
- [ ] Sabes prever a tabela de iterações do caso 12, 0, 9, -1 e confirmá-la com linhas de observação.
- [ ] Provocaste o ciclo infinito e paraste-o com Ctrl+C, e provocaste o acumulador dentro do ciclo, o fim do `range` errado e a fronteira trocada.
- [ ] As linhas de observação já saíram dos dois programas.
- [ ] Sabes dizer porque é que o `campanha.py` usa um `while` e o `campanha_10ano.py` usa um `for`.
- [ ] Consegues explicar, por palavras tuas, o que faz cada uma das três peças de um ciclo.

![Rodapé](../../imagens/rodape.png)
