![Cabeçalho](../imagens/cabecalho.png)

# Laboratório: Do pseudocódigo ao Python

Laboratório do tema Do pseudocódigo ao Python, do módulo Criar aplicações em linguagem de programação Python. Vais escrever o teu primeiro script. Depois, vais passar para Python, fase a fase, o algoritmo da campanha de recolha de alimentos, que já conheces do pseudocódigo. Cada passo diz o que fazer, porquê e o que deves ver, e avanças ao teu ritmo. Tudo o que precisas está aqui; o [guia do tema](01-do-pseudocodigo-ao-python.md) tem a teoria completa, para quem quiser saber mais.

## O que vais construir

No fim, tens dois programas em Python que fazem o mesmo que dois algoritmos do guia 04 da algoritmia. O primeiro, `campanha.py`, lê do teclado os quilos de alimentos que cada turma entrega, até aparecer o -1. Depois mostra quantas turmas entregaram, o total e a média. O segundo, `campanha_turmas.py`, trabalha com os quilos das 6 turmas do 10.º ano, já guardados numa lista. Diz que turmas trouxeram mais do que a média. Vais confirmar no computador os mesmos casos que se calcularam à mão no pseudocódigo.

Pelo caminho, ficas a saber correr um script no VS Code e experimentar uma linha na consola do Python. Ficas também a saber traduzir para Python a leitura, a seleção, os ciclos e as funções do pseudocódigo. Fazes também, no caderno, o teu **quadro de tradução**: uma tabela com o que muda do pseudocódigo para o Python.

| Fase | O que muda | O que funciona no fim |
| --- | --- | --- |
| 1 | `ola.py` | O primeiro script corre no terminal |
| 2 | Nada no disco; experimentas na consola do Python | Sabes de que tipo é um valor e como o Python divide |
| 3 | `campanha.py`, a primeira versão | O programa lê os quilos de uma turma e mostra o total |
| 4 | `campanha.py`, com um ciclo `while` | O programa lê turmas até ao -1, conta-as e soma os quilos |
| 5 | `campanha.py`, com um `if` | O programa mostra a média, só quando há turmas |
| 6 | `campanha_turmas.py`, com um `for` sobre a lista | O programa calcula a média das 6 turmas |
| 7 | `campanha_turmas.py`, com um `for` e o índice | O programa diz que turmas ficaram acima da média |
| 8 | `campanha_turmas.py`, com uma função | A média é calculada por uma função, testada sozinha |

No fim, a tua pasta fica assim:

```text
fp-python/
├── ola.py
├── campanha.py
└── campanha_turmas.py
```

## Palavras que vais usar

- Script: um ficheiro de texto com instruções em Python, com o nome a acabar em `.py`. Para saber mais, vê a secção "Um programa é um algoritmo que o computador executa" do [guia](01-do-pseudocodigo-ao-python.md).
- Interpretador: o programa que lê o teu script, confirma que está bem escrito e executa as instruções por ordem. É o que se instala quando se instala o Python.
- Terminal: uma janela onde se escrevem comandos, um por linha, e se carrega em Enter.
- Comando: uma ordem escrita no terminal, como `python ola.py`.
- Consola do Python: o modo em que o Python executa uma linha de cada vez e mostra logo o resultado, a seguir ao `>>>`.
- Comentário: uma nota para quem lê o código, a seguir a `#`, que o Python ignora.
- `print`: a função que escreve valores no ecrã, o `Escreve:` do pseudocódigo.
- `input`: a função que escreve uma pergunta, lê o que a pessoa escreve e o devolve, sempre como texto.
- Converter: transformar um valor de um tipo noutro, como o texto `"12"` no número 12, com a função `int`.
- Dois pontos: o sinal no fim da linha que abre um bloco, como a de um `while` ou de um `if`.
- `while`: o `Enquanto` do Python.
- `if` e `else`: o `Se` e o `Senão` do Python.
- Lista: o array do pseudocódigo, no Python.
- `for`: o ciclo que percorre uma lista ou uma sequência de números; é o `Para cada` e o `Para`.
- `range`: a função que produz uma sequência de inteiros, do primeiro número até antes do segundo.
- `def` e `return`: a `Função` e o `devolver` do Python.
- Erro de sintaxe: um erro na escrita do código, que faz o Python recusar o programa antes de executar qualquer linha.
- Erro de execução: um erro que para o programa a meio, numa linha que não se consegue executar com aqueles valores.
- Erro de lógica: um erro que não dá mensagem nenhuma; o programa corre e dá o resultado errado.
- Traceback: a mensagem de um erro que para o programa a meio. Lê-se de baixo para cima. Para saber mais, vê a secção "Os três tipos de erro" do [guia](01-do-pseudocodigo-ao-python.md).

## O que precisas

- O Python 3, o interpretador. Para confirmares que o tens, abre o terminal, como a fase 1 explica, e escreve `python --version`. Deve aparecer uma linha como `Python 3.13.2`, que quer dizer que o Python 3 está instalado. O primeiro número tem de ser 3. No macOS, o comando é `python3 --version`.
- O VS Code, o editor de código das aulas, onde escreves os scripts e abres o terminal. Abre-se como qualquer outra aplicação do computador.
- O caderno, para o quadro de tradução.

Os resultados e as mensagens de erro deste laboratório são os do Python 3.14. Num Python mais antigo, uma mensagem pode ter outras palavras, ou apontar a linha seguinte. O tipo de erro, a palavra antes dos dois pontos, é o mesmo.

Os nomes dos menus do VS Code foram confirmados a 27 de outubro de 2026, com o VS Code em inglês. Se o teu estiver em português, os menus estão no mesmo sítio, com o nome traduzido.

## Se alguma coisa falhar

1. Guardaste o ficheiro? O Python corre o que está guardado no disco, e não o que vês no ecrã. Guarda com Ctrl+S, ou Cmd+S no macOS. No VS Code, uma bola cheia no separador do ficheiro, no lugar do X, quer dizer que há alterações por guardar.
2. Estás na pasta certa? No terminal, o texto antes do cursor mostra a pasta onde estás. Tem de ter `fp-python` no fim, antes do sinal `>` no Windows, ou do `%` no macOS. Se não tiver, fecha o terminal e abre outro, no menu Terminal, com a opção New Terminal. O terminal novo abre-se na pasta que tens aberta no VS Code.
3. Estás na consola do Python sem quereres? Se a linha começa por `>>>`, escreve `exit()` e carrega em Enter, para voltares ao terminal.
4. O programa não volta ao terminal? Pode estar à espera que escrevas um valor, depois de uma pergunta. Se já escreveste o valor e continua parado, ou se repete a mesma coisa sem parar, pode ser um ciclo que nunca acaba. Carrega em Ctrl+C no terminal, para o parar.
5. Copiaste o código à mão? Confirma os dois pontos no fim das linhas do `while`, do `if`, do `else`, do `for` e do `def`, e os quatro espaços da indentação.

## Preparar o projeto

1. Cria uma pasta para os teus scripts de Python, com o nome `fp-python`, no sítio onde costumas guardar os trabalhos, por exemplo em Documentos. Uma pasta própria impede que os scripts se misturem com outros ficheiros. O nome não tem espaços nem acentos, para se escrever sem problemas no terminal.

2. Abre a pasta no VS Code. No menu File, escolhe Open Folder..., isto é, "abrir pasta", e escolhe `fp-python`. Se o VS Code perguntar se confias nos autores dos ficheiros desta pasta, responde que sim: a pasta é tua. O que deves ver: à esquerda, no painel Explorer, o nome `FP-PYTHON`, ainda sem ficheiros.

3. No caderno, faz uma tabela com três colunas, com estes títulos: "Pseudocódigo", "Python" e "O que muda". É o teu quadro de tradução. Em cada paragem, acrescentas-lhe as linhas do que acabaste de traduzir.

## Fase 1: Correr um script

Na algoritmia, quem executava os algoritmos eras tu, com a tabela de trace. Agora vais pôr o computador a fazê-lo. Para isso, escreves as instruções num ficheiro, o script, e mandas o interpretador do Python executá-lo. O `Escreve:` do pseudocódigo passa a chamar-se `print`, com o texto entre parênteses. Para saber mais, lê a secção "Correr um script" do [guia](01-do-pseudocodigo-ao-python.md).

1. Cria o primeiro script. No painel Explorer, passa o rato por cima de `FP-PYTHON` e carrega no primeiro ícone, New File..., isto é, "novo ficheiro". Escreve o nome `ola.py` e carrega em Enter. O `.py` no fim do nome diz ao VS Code e ao Python que é um script de Python. Cria `ola.py` com este conteúdo:

   ```python
   # ola.py: o primeiro script, para confirmar que o Python corre neste computador.
   print("Olá, Python!")
   print("O meu primeiro script correu.")
   ```

   Leitura guiada: a primeira linha começa com `#`, e é um comentário. Diz o nome do ficheiro e para que serve, e o Python ignora-a. As duas linhas seguintes escrevem cada uma o texto que está entre aspas, pela ordem em que estão. As aspas marcam onde o texto começa e acaba, e não aparecem no ecrã.

2. Guarda o ficheiro, com Ctrl+S, ou Cmd+S no macOS. O Python lê o ficheiro guardado no disco, e um ficheiro por guardar ainda não tem estas linhas.

3. Abre o terminal. No menu Terminal, escolhe New Terminal. O que deves ver: uma janela na parte de baixo do VS Code. Tem uma linha com o nome da pasta, `fp-python`, no fim, e o cursor à espera.

4. Antes de correres, prevê: o que aparece no terminal, e por que ordem? Depois, no terminal, corre:

   ```bash
   python ola.py
   ```

   No macOS e no Linux, o comando é `python3 ola.py`.

   O que deves ver:

   ```text
   Olá, Python!
   O meu primeiro script correu.
   ```

   Isto quer dizer que o interpretador encontrou o ficheiro e executou as duas instruções, de cima para baixo. Se o Windows responder que não conhece o `python`, ou se abrir a Microsoft Store, fecha a loja e experimenta `py ola.py`, que faz o mesmo. Se aparecer outra coisa, vê os [problemas frequentes](#problemas-frequentes).

5. Provoca um erro de propósito: apaga a aspa que fecha o texto da terceira linha, para ficar `print("O meu primeiro script correu.)`. Guarda e corre outra vez o mesmo comando. O que deves ver:

   ```text
     File "C:\Users\aluno\fp-python\ola.py", line 3
       print("O meu primeiro script correu.)
             ^
   SyntaxError: unterminated string literal (detected at line 3)
   ```

   A primeira linha mostra o caminho do ficheiro no teu computador, e muda de computador para computador. A mensagem quer dizer "erro de sintaxe: texto por terminar, detetado na linha 3". Repara que o "Olá, Python!" da linha 2, que estava certa, também não apareceu. Um erro de sintaxe faz o Python recusar o programa inteiro, antes de executar qualquer linha. Para corrigir, volta a pôr a aspa, guarda e corre outra vez, até veres as duas linhas.

### Paragem 1

O `ola.py` corre e escreve as duas linhas. Sabes criar um script, guardá-lo e corrê-lo no terminal.

Pensa antes de continuares: porque é que, com o erro na linha 3, nem o "Olá, Python!" da linha 2 apareceu? A resposta: antes de executar, o interpretador lê o ficheiro todo e confirma que está bem escrito. Ao encontrar um erro de sintaxe, recusa o programa e não executa nenhuma linha, nem as que estão antes do erro.

Acrescenta ao teu quadro de tradução:

| Pseudocódigo | Python | O que muda |
| --- | --- | --- |
| `Escreve: "Olá"` | `print("Olá")` | o texto vai entre parênteses |
| não havia | `# comentário` | uma nota que o Python ignora |

## Fase 2: Experimentar na consola do Python

Às vezes só queres saber quanto dá uma conta, ou de que tipo é um valor, sem criar um ficheiro. Para isso há a consola do Python: executa uma linha de cada vez e mostra logo o resultado. É aqui que vais ver como o Python divide, o que vai explicar um pormenor das médias das fases seguintes. Para saber mais, lê as secções "Os tipos dos valores" e "Contas e divisões" do [guia](01-do-pseudocodigo-ao-python.md).

1. No terminal, escreve só `python`, sem nome de ficheiro, e carrega em Enter. No macOS, é `python3`. O que deves ver: umas linhas com a versão do Python e, na última, `>>>`. Isto quer dizer que estás na consola do Python, à espera de uma linha.

2. Antes de escreveres cada linha, prevê o resultado. Depois escreve-a a seguir ao `>>>` e carrega em Enter:

   ```text
   >>> 21 / 3
   7.0
   >>> 7 / 2
   3.5
   >>> 7 // 2
   3
   >>> 7 % 2
   1
   ```

   Na consola, o Python mostra sozinho o valor de cada linha, sem `print`. A primeira linha é a que surpreende: `21 / 3` dá `7.0`, e não `7`. No Python, a divisão com `/` dá sempre um número com parte decimal, um `float`, mesmo quando a conta é exata. O `div` do pseudocódigo escreve-se `//`, e o `resto` escreve-se `%`.

3. Agora vê de que tipo são os valores, com a função `type`. Prevê, escreve e confirma:

   ```text
   >>> type(12)
   <class 'int'>
   >>> type(7.0)
   <class 'float'>
   >>> type("12")
   <class 'str'>
   ```

   O nome entre as aspas, a seguir a `class`, é o tipo. `12` é um inteiro, `int`. `7.0` tem parte decimal, `float`. `"12"`, entre aspas, é um texto, e o tipo dos textos no Python chama-se `str`, a abreviatura de string. O número 12 e o texto `"12"` são valores diferentes.

4. Experimenta o que acontece quando se juntam textos e números. Prevê cada resultado antes de carregares em Enter:

   ```text
   >>> "12" + "3"
   '123'
   >>> int("12") + 3
   15
   ```

   Entre dois textos, o `+` não soma: junta-os, e dá o texto `'123'`. A função `int` converte o texto `"12"` no número 12, e aí o `+` já soma. Vais precisar disto na fase seguinte.

5. Sai da consola: escreve `exit()` e carrega em Enter. O que deves ver: a linha do terminal outra vez, com `fp-python` no fim.

### Paragem 2

Sabes abrir e fechar a consola do Python e usá-la para experimentar uma linha. Não ficou nenhum ficheiro novo na pasta, porque o que se escreve na consola não se guarda.

Pensa antes de continuares: quando a campanha tiver 21 quilos em 3 turmas, como vai aparecer a média no ecrã? A resposta: `7.0`, porque a média faz-se com `/`, e a divisão com `/` dá sempre um `float`.

Acrescenta ao teu quadro de tradução:

| Pseudocódigo | Python | O que muda |
| --- | --- | --- |
| `21 / 3` dá 7 | `21 / 3` dá `7.0` | o `/` dá sempre um `float` |
| `7 div 2` | `7 // 2` | outro sinal |
| `7 resto 2` | `7 % 2` | outro sinal |
| `string` | `str` | o nome abreviado |

## Fase 3: Ler um valor e convertê-lo

Este é o problema que vais passar para Python nas fases 3 a 5, do guia 04:

> A escola organiza uma campanha de recolha de alimentos. Cada turma entrega os alimentos que juntou, e a funcionária escreve quantos quilos a turma trouxe, um número inteiro. Uma turma pode não ter trazido nada, e nesse caso a funcionária escreve 0. Quando não há mais turmas, escreve -1. O algoritmo mostra quantas turmas entregaram, o total de quilos e a média por turma, mas a média só se houver pelo menos uma turma.

Antes do ciclo, começa-se pela leitura de um só valor. No pseudocódigo, uma leitura levava duas linhas, a pergunta e o `ler valor`:

```text
int totalQuilos = 0
Escreve: "Quilos entregues pela turma?"
int quilos = ler valor
totalQuilos = totalQuilos + quilos
Escreve: "Total: ", totalQuilos, " kg"
```

No Python, as duas juntam-se. A função `input` escreve a pergunta e espera que a pessoa escreva e carregue em Enter. Depois devolve o que ela escreveu. Mas devolve sempre um texto. Para fazer contas, é preciso converter esse texto num número, com a função `int`. Para saber mais, lê a secção "Ler do teclado com `input`, e converter" do [guia](01-do-pseudocodigo-ao-python.md).

1. No painel Explorer, cria um ficheiro novo, como na fase 1, com o nome `campanha.py`. Cria `campanha.py` com este conteúdo:

   ```python
   # campanha.py: a campanha de recolha de alimentos da escola.
   # Nesta fase, lê os quilos de uma turma e soma-os ao total.

   total_quilos = 0
   quilos = int(input("Quilos entregues pela turma? "))
   total_quilos = total_quilos + quilos
   print("Total:", total_quilos, "kg")
   ```

   Leitura guiada: as variáveis nascem sem o tipo à frente, e os nomes compostos escrevem-se com traço baixo, `total_quilos`, que é a forma do Python. A quinta linha lê-se de dentro para fora. O `input` faz a pergunta e devolve o texto escrito. O `int` converte-o num número inteiro, e só então o número fica em `quilos`. O espaço depois do ponto de interrogação separa a pergunta do que a pessoa escreve. No `print`, os espaços entre os valores não estão dentro das aspas, porque o `print` põe-nos sozinho.

2. Guarda. Antes de correres, prevê o que aparece se escreveres 12. Depois corre:

   ```bash
   python campanha.py
   ```

   No macOS e no Linux, o comando é `python3 campanha.py`.

   O programa escreve a pergunta e fica à espera. Escreve `12` e carrega em Enter. O que deves ver:

   ```text
   Quilos entregues pela turma? 12
   Total: 12 kg
   ```

   O 12 a seguir à pergunta é o que tu escreveste. Isto quer dizer que o valor foi lido, convertido e somado ao total, que começou em 0.

3. Provoca um erro de propósito: tira a conversão. Muda a quinta linha para `quilos = input("Quilos entregues pela turma? ")`, sem o `int(` e sem o último parêntese. Guarda, corre e escreve 12 outra vez. O que deves ver:

   ```text
   Quilos entregues pela turma? 12
   Traceback (most recent call last):
     File "C:\Users\aluno\fp-python\campanha.py", line 6, in <module>
       total_quilos = total_quilos + quilos
                      ~~~~~~~~~~~~~^~~~~~~~
   TypeError: unsupported operand type(s) for +: 'int' and 'str'
   ```

   Lê a mensagem de baixo para cima. A última linha quer dizer "erro de tipo: o `+` não funciona entre um `int` e um `str`". As de cima dizem onde: na linha 6, na soma. Isto acontece porque, sem a conversão, `quilos` guarda o texto `"12"`, e o Python não soma um número com um texto. Repara que a mensagem aponta a linha 6, mas a causa está na linha 5, na leitura sem `int`. É um erro de execução: o programa estava bem escrito, correu até à linha 6 e parou aí. Para corrigir, volta a pôr a linha como estava, com o `int(` e os dois parênteses no fim, guarda e corre outra vez.

### Paragem 3

O `campanha.py` lê os quilos de uma turma e mostra o total, `Total: 12 kg`.

Pensa antes de continuares: o que mostraria o programa se, com a conversão no sítio, escrevesses `doze` em vez de 12? A resposta: o programa parava com `ValueError: invalid literal for int() with base 10: 'doze'`, porque o `int` não consegue converter esse texto num número. Por agora, quem usa o programa tem de escrever um número.

Acrescenta ao teu quadro de tradução:

| Pseudocódigo | Python | O que muda |
| --- | --- | --- |
| `int totalQuilos = 0` | `total_quilos = 0` | sem o tipo; o nome com traço baixo |
| `Escreve: "Pergunta?"` e `int quilos = ler valor` | `quilos = int(input("Pergunta? "))` | uma só linha; o texto lido converte-se com `int` |
| `Escreve: "Total: ", totalQuilos, " kg"` | `print("Total:", total_quilos, "kg")` | os espaços ficam fora das aspas |

## Fase 4: Repetir até à sentinela, com `while`

A funcionária não sabe quantas turmas vão entregar. Por isso, o programa lê valores até aparecer o -1, a sentinela, o valor combinado que quer dizer "acabou". O 0 não pode ser a sentinela, porque uma turma pode não trazer nada. No pseudocódigo, esta parte era assim:

```text
const SENTINELA = -1
int turmas = 0
int totalQuilos = 0
Escreve: "Quilos entregues pela turma (-1 para terminar)?"
int quilos = ler valor
Enquanto quilos != SENTINELA
    turmas = turmas + 1
    totalQuilos = totalQuilos + quilos
    Escreve: "Quilos entregues pela turma (-1 para terminar)?"
    quilos = ler valor
Escreve: "Turmas que entregaram: ", turmas
Escreve: "Total: ", totalQuilos, " kg"
```

O `Enquanto` passa a `while`, com dois pontos no fim da linha. As linhas do corpo ficam indentadas quatro espaços, como no pseudocódigo. A constante perde o `const` e fica só com o nome em maiúsculas. Para saber mais, lê a secção "Repetir com `while`" do [guia](01-do-pseudocodigo-ao-python.md).

1. Substitui todo o conteúdo de `campanha.py` por este:

   ```python
   # campanha.py: a campanha de recolha de alimentos da escola.
   # Lê os quilos de cada turma até aparecer a sentinela -1,
   # conta as turmas e soma os quilos.

   SENTINELA = -1

   turmas = 0
   total_quilos = 0
   quilos = int(input("Quilos entregues pela turma (-1 para terminar)? "))
   while quilos != SENTINELA:
       turmas = turmas + 1
       total_quilos = total_quilos + quilos
       # A leitura do valor seguinte é a atualização: sem ela, o ciclo nunca acabava.
       quilos = int(input("Quilos entregues pela turma (-1 para terminar)? "))
   print("Turmas que entregaram:", turmas)
   print("Total:", total_quilos, "kg")
   ```

   Leitura guiada: lê-o como o pseudocódigo, pelas três peças do ciclo. A inicialização são as linhas antes do `while`: o contador `turmas` e o acumulador `total_quilos` a 0, e a primeira leitura, a leitura antecipada. A condição é `quilos != SENTINELA`, com os dois pontos no fim. O corpo são as três instruções indentadas, e a última é a atualização, a leitura seguinte. Os dois `print` estão encostados à margem, fora do ciclo, e só se executam quando ele termina. Quando carregas em Enter depois dos dois pontos do `while`, o VS Code já começa a linha seguinte com os quatro espaços.

2. Guarda. Vais correr o programa três vezes, com os três casos do guia 04. Antes de correres, prevê o que aparece em cada um, a partir desta tabela:

   | Valores escritos | Turmas | Total | Porque é que este caso foi escolhido |
   | --- | ---: | ---: | --- |
   | -1 | 0 | 0 | Zero voltas: ninguém entregou |
   | 15, -1 | 1 | 15 | Uma só volta |
   | 12, 0, 9, -1 | 3 | 21 | Várias voltas, com uma turma que trouxe 0 |

   Corre `python campanha.py` e escreve os valores do terceiro caso, um de cada vez, com Enter depois de cada um. O que deves ver:

   ```text
   Quilos entregues pela turma (-1 para terminar)? 12
   Quilos entregues pela turma (-1 para terminar)? 0
   Quilos entregues pela turma (-1 para terminar)? 9
   Quilos entregues pela turma (-1 para terminar)? -1
   Turmas que entregaram: 3
   Total: 21 kg
   ```

   Isto quer dizer que o ciclo deu três voltas, uma por turma, e terminou no -1, que não foi contado. O 0 foi contado como turma, como o enunciado pede.

3. Corre outra vez, com o segundo caso, 15 e -1. O que deves ver no fim: `Turmas que entregaram: 1` e `Total: 15 kg`. Depois corre com o primeiro caso, só -1. O que deves ver: `Turmas que entregaram: 0` e `Total: 0 kg`. O ciclo deu zero voltas, porque a condição foi falsa logo no primeiro teste.

### Paragem 4

O `campanha.py` lê turmas até ao -1, conta-as e soma os quilos. Os três casos dão o que a tabela previa.

Pensa antes de continuares: o que acontecia se apagasses a última linha do corpo do ciclo, a leitura seguinte? A resposta: o valor de `quilos` nunca mudava, a condição nunca ficava falsa, e o ciclo nunca acabava. O programa ficava a contar a mesma turma sem parar, e só o Ctrl+C o parava. No ecrã, depois do primeiro valor, não aparecia mais nada: o programa parecia parado, mas estava a dar voltas sem fim.

Acrescenta ao teu quadro de tradução:

| Pseudocódigo | Python | O que muda |
| --- | --- | --- |
| `const SENTINELA = -1` | `SENTINELA = -1` | sem `const`; as maiúsculas dizem que é constante |
| `Enquanto quilos != SENTINELA` | `while quilos != SENTINELA:` | `while` e os dois pontos |

## Fase 5: A média só quando há turmas, com `if`

Falta a média. Uma média é o total a dividir pelo número de turmas, e com zero turmas a conta é 0 / 0, que não tem resultado. No Python, uma divisão por zero para o programa com `ZeroDivisionError: division by zero`. Por isso, como no pseudocódigo, a média só se calcula se houver pelo menos uma turma:

```text
Se turmas > 0
    float media = totalQuilos / turmas
    Escreve: "Média por turma: ", media, " kg"
Senão
    Escreve: "Não houve entregas, por isso não há média."
```

O `Se` passa a `if` e o `Senão` passa a `else`, os dois com dois pontos no fim. Para saber mais, lê a secção "Decidir com `if`, `elif` e `else`" do [guia](01-do-pseudocodigo-ao-python.md).

1. Em `campanha.py`, acrescenta estas linhas no fim do ficheiro, depois do último `print`, encostadas à margem:

   ```python
   # Sem este if, com zero turmas, a conta seria 0 / 0 e o programa parava.
   if turmas > 0:
       media = total_quilos / turmas
       print("Média por turma:", media, "kg")
   else:
       print("Não houve entregas, por isso não há média.")
   ```

   Leitura guiada: o `if` está encostado à margem, depois do ciclo. Por isso, só se avalia uma vez, quando a contagem e a soma estão completas. As duas linhas do primeiro bloco executam-se só quando `turmas > 0` é verdadeiro. O `else` fica na mesma margem do `if`, e o seu bloco executa-se nos outros casos.

2. Muda a última linha do comentário do topo para `# conta as turmas, soma os quilos e mostra a média por turma.`. O comentário do topo diz sempre o que o ficheiro faz, e o ficheiro passou a mostrar a média.

3. Guarda e corre os três casos da fase 4. Antes de correres, prevê como aparece a média de 21 quilos por 3 turmas. O que deves ver no fim de cada caso:

   | Valores escritos | As últimas linhas do ecrã |
   | --- | --- |
   | 12, 0, 9, -1 | `Turmas que entregaram: 3`, `Total: 21 kg`, `Média por turma: 7.0 kg` |
   | 15, -1 | `Turmas que entregaram: 1`, `Total: 15 kg`, `Média por turma: 15.0 kg` |
   | -1 | `Turmas que entregaram: 0`, `Total: 0 kg`, `Não houve entregas, por isso não há média.` |

   A média aparece como `7.0`, e não como 7, porque a divisão com `/` dá sempre um `float`, como viste na fase 2. A lógica é a mesma do guia 04. O caso de zero turmas escreve a mensagem e nunca chega à divisão. Se aparecer `ZeroDivisionError` no caso do -1, o `if` não está no sítio certo, ou falta-lhe o `turmas > 0`.

### Paragem 5

O `campanha.py` está completo. Faz o mesmo que o algoritmo do guia 04, nos mesmos três casos. Confere o teu com este:

```python
# campanha.py: a campanha de recolha de alimentos da escola.
# Lê os quilos de cada turma até aparecer a sentinela -1,
# conta as turmas, soma os quilos e mostra a média por turma.

SENTINELA = -1

turmas = 0
total_quilos = 0
quilos = int(input("Quilos entregues pela turma (-1 para terminar)? "))
while quilos != SENTINELA:
    turmas = turmas + 1
    total_quilos = total_quilos + quilos
    # A leitura do valor seguinte é a atualização: sem ela, o ciclo nunca acabava.
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

Pensa antes de continuares: porque é que o `if` da média tem de ficar encostado à margem, e não dentro do ciclo? A resposta: dentro do ciclo, calculava uma média a cada volta, com contas a meio. A média só faz sentido quando todas as turmas estão contadas, depois do ciclo.

Acrescenta ao teu quadro de tradução:

| Pseudocódigo | Python | O que muda |
| --- | --- | --- |
| `Se turmas > 0` | `if turmas > 0:` | `if` e os dois pontos |
| `Senão` | `else:` | `else` e os dois pontos |
| `float media = totalQuilos / turmas` | `media = total_quilos / turmas` | sem o tipo; o resultado é sempre um `float` |

## Fase 6: Percorrer a lista, com `for`

A segunda parte do problema já não lê do teclado:

> No fim da campanha, os quilos das 6 turmas do 10.º ano ficaram registados num array, `quilosPorTurma = [12, 0, 9, 15, 6, 18]`. A diretora quer saber que turmas trouxeram mais do que a média dessas 6 turmas.

O array do pseudocódigo chama-se **lista** no Python, e escreve-se da mesma maneira, entre parênteses retos. O `Para cada` passa a `for`, e lê-se "para cada quilos na lista". Primeiro, soma-se a lista para calcular a média. No pseudocódigo era assim:

```text
const NUMERO_DE_TURMAS = 6
quilosPorTurma = [12, 0, 9, 15, 6, 18]
int total = 0
Para cada quilos em quilosPorTurma
    total = total + quilos
float media = total / NUMERO_DE_TURMAS
Escreve: "Média: ", media, " kg"
```

Para saber mais, lê a secção "Percorrer uma lista com `for`" do [guia](01-do-pseudocodigo-ao-python.md).

1. Cria um ficheiro novo, `campanha_turmas.py`. É um programa diferente do `campanha.py`, porque trabalha com outros dados, e por isso fica noutro ficheiro. Cria `campanha_turmas.py` com este conteúdo:

   ```python
   # campanha_turmas.py: os quilos das 6 turmas do 10.º ano, no fim da campanha.
   # Nesta fase, soma os quilos das turmas e calcula a média.

   NUMERO_DE_TURMAS = 6

   quilos_por_turma = [12, 0, 9, 15, 6, 18]
   total = 0
   for quilos in quilos_por_turma:
       total = total + quilos
   media = total / NUMERO_DE_TURMAS
   print("Média:", media, "kg")
   ```

   Leitura guiada: a lista escreve-se como o array do pseudocódigo, e o nome passa a `quilos_por_turma`. O `for` dá à variável `quilos`, em cada volta, o elemento seguinte da lista: 12, 0, 9, 15, 6 e 18. O corpo é a soma, indentada. Depois do ciclo, encostadas à margem, vêm a média e o `print`. Aqui a média não precisa de `if`, porque o enunciado garante que há 6 turmas.

2. Guarda. Antes de correres, calcula de cabeça a média das 6 turmas. Depois corre:

   ```bash
   python campanha_turmas.py
   ```

   No macOS e no Linux, o comando é `python3 campanha_turmas.py`.

   O que deves ver:

   ```text
   Média: 10.0 kg
   ```

   O total é 60, e 60 / 6 dá 10. Aparece `10.0` pela mesma razão da fase 5. Este programa não faz perguntas: os dados já estão no código.

### Paragem 6

O `campanha_turmas.py` calcula a média das 6 turmas, `10.0` quilos.

Pensa antes de continuares: o que aconteceria à linha `media = total / NUMERO_DE_TURMAS` se estivesse indentada, dentro do ciclo? A resposta: calculava uma média a cada volta, com o total a meio. O `print` continuava fora do ciclo e mostrava `10.0`, porque a última média é calculada com o total completo. Mas o programa fazia cinco contas inúteis. A indentação decide o que se repete.

Acrescenta ao teu quadro de tradução:

| Pseudocódigo | Python | O que muda |
| --- | --- | --- |
| `quilosPorTurma = [12, 0, 9]` | `quilos_por_turma = [12, 0, 9]` | chama-se lista; só muda o nome da variável |
| `Para cada quilos em quilosPorTurma` | `for quilos in quilos_por_turma:` | `for`, `in` e os dois pontos |

## Fase 7: As turmas acima da média, com o índice

Para dizer que turmas ficaram acima da média, é preciso o número de cada turma, e por isso é preciso o índice. No pseudocódigo, usava-se o `Para` com as três peças à vista:

```text
int acimaDaMedia = 0
Para i = 0, i < NUMERO_DE_TURMAS, i++
    Se quilosPorTurma[i] > media
        Escreve: "A turma ", i + 1, " trouxe mais do que a média"
        acimaDaMedia = acimaDaMedia + 1
Escreve: "Turmas acima da média: ", acimaDaMedia
```

No Python, este `Para` escreve-se com a função `range`. O `range(0, 6)` produz os números 0, 1, 2, 3, 4 e 5: começa no primeiro número e para logo antes do segundo. É exatamente o `i = 0, i < 6` do pseudocódigo. Para saber mais, lê a secção "Contar voltas com `for` e `range`" do [guia](01-do-pseudocodigo-ao-python.md).

1. Em `campanha_turmas.py`, acrescenta estas linhas no fim do ficheiro, depois do `print` da média, encostadas à margem:

   ```python
   acima_da_media = 0
   for i in range(0, NUMERO_DE_TURMAS):
       if quilos_por_turma[i] > media:
           # O i + 1 faz com que a turma de índice 0 seja, para as pessoas, a turma 1.
           print("A turma", i + 1, "trouxe mais do que a média")
           acima_da_media = acima_da_media + 1
   print("Turmas acima da média:", acima_da_media)
   ```

   Leitura guiada: o contador nasce antes do ciclo. O `for` dá a `i` os índices de 0 a 5, um por volta. Dentro, o `if` compara o elemento nessa posição, `quilos_por_turma[i]`, com a média. As duas linhas do bloco do `if` têm oito espaços, e só se executam para as turmas acima da média. O último `print` está na margem, e escreve-se uma vez, no fim.

2. Muda a segunda linha do comentário do topo para `# Calcula a média e diz que turmas trouxeram mais do que ela.`, porque o programa passou a fazer isso.

3. Guarda. Antes de correres, olha para a lista e para a média, 10, e prevê que turmas aparecem. Depois corre o programa. O que deves ver:

   ```text
   Média: 10.0 kg
   A turma 1 trouxe mais do que a média
   A turma 4 trouxe mais do que a média
   A turma 6 trouxe mais do que a média
   Turmas acima da média: 3
   ```

   As turmas 1, 4 e 6 trouxeram 12, 15 e 18 quilos, mais do que 10. É o resultado do trace do guia 04.

4. Provoca um erro de propósito: muda o `range(0, NUMERO_DE_TURMAS)` para `range(1, NUMERO_DE_TURMAS)`. Guarda e corre. O que deves ver:

   ```text
   Média: 10.0 kg
   A turma 4 trouxe mais do que a média
   A turma 6 trouxe mais do que a média
   Turmas acima da média: 2
   ```

   Não aparece nenhuma mensagem de erro, e o resultado está errado: falta a turma 1. É um erro de lógica. O `range(1, 6)` começa no índice 1, e a turma de índice 0 nunca é comparada. Só se dá por ele comparando com o resultado esperado. Volta a pôr `range(0, NUMERO_DE_TURMAS)`.

5. Provoca outro erro: muda para `range(0, NUMERO_DE_TURMAS + 1)`. Guarda e corre. O que deves ver: as três turmas certas e, a seguir, esta mensagem:

   ```text
   Traceback (most recent call last):
     File "C:\Users\aluno\fp-python\campanha_turmas.py", line 14, in <module>
       if quilos_por_turma[i] > media:
          ~~~~~~~~~~~~~~~~^^^
   IndexError: list index out of range
   ```

   Quer dizer "erro de índice: índice da lista fora dos limites". O `range(0, 7)` chega ao 6, e `quilos_por_turma[6]` não existe, porque o último índice de uma lista de 6 elementos é o 5. Desta vez é um erro de execução: o programa correu até à sétima volta e parou aí. Volta a pôr `range(0, NUMERO_DE_TURMAS)`, guarda e corre outra vez.

### Paragem 7

O `campanha_turmas.py` diz que turmas trouxeram mais do que a média, e quantas são.

Pensa antes de continuares: dos dois erros provocados, qual é o mais perigoso, e porquê? A resposta: o primeiro, o `range(1, ...)`. O segundo para o programa com uma mensagem, e não passa despercebido. O primeiro dá um resultado errado sem aviso nenhum, e só o encontra quem compara com o resultado esperado.

Acrescenta ao teu quadro de tradução:

| Pseudocódigo | Python | O que muda |
| --- | --- | --- |
| `Para i = 0, i < NUMERO_DE_TURMAS, i++` | `for i in range(0, NUMERO_DE_TURMAS):` | o `range` para antes do segundo número, como o `<` |
| `Para i de 1 até 6` | `for i in range(1, 7):` | o "até 6" inclui o 6, e o `range` precisa do 7 |

## Fase 8: Uma função para a média

A média de uma lista de números serve muitos problemas. Serve para os quilos das turmas, as notas de um teste ou as pontuações de um jogo. No guia 05 da algoritmia, escreveu-se uma função para ela:

```text
Função media(valores)
    int quantidade = 0
    int total = 0
    Para cada valor em valores
        quantidade = quantidade + 1
        total = total + valor
    devolver total / quantidade
```

No Python, a `Função` passa a `def`, com dois pontos no fim do cabeçalho, e o `devolver` passa a `return`. Por baixo do cabeçalho, escreve-se a documentação da função, entre três pares de aspas: o que ela recebe e o que devolve. Para saber mais, lê a secção "Funções com `def` e `return`" do [guia](01-do-pseudocodigo-ao-python.md).

Como na algoritmia, uma função testa-se sozinha antes de ser usada. Assim, se o programa completo falhar, já sabes que a função está certa. Por isso, primeiro escreves a função e os testes, e só depois a parte principal.

1. Substitui todo o conteúdo de `campanha_turmas.py` por este. Tem a constante, a função e, no fim, três linhas de teste provisórias:

   ```python
   # campanha_turmas.py: os quilos das 6 turmas do 10.º ano, no fim da campanha.
   # Calcula a média e diz que turmas trouxeram mais do que ela.

   NUMERO_DE_TURMAS = 6


   def media(valores):
       """Calcula a média de uma lista de números.

       A lista tem de ter pelo menos um número: com a lista vazia,
       a conta seria 0 / 0, e o programa parava com um erro.
       Devolve a média, um float.
       """
       quantidade = 0
       total = 0
       for valor in valores:
           quantidade = quantidade + 1
           total = total + valor
       return total / quantidade


   print(media([12, 0, 9, 15, 6, 18]))
   print(media([15]))
   print(media([12, 0, 9]))
   ```

   Leitura guiada: começa pela função. É a do guia 05, linha a linha, com o `def`, os dois pontos e o `return`. As duas linhas em branco antes e depois dela são a convenção do Python, para se ver bem onde começa e acaba. As três linhas do fim chamam a função com três listas, e cada `print` escreve o valor que ela devolve. A parte principal da fase 7 saiu por agora, e volta no passo 3.

2. Guarda. Antes de correres, prevê o que devolve cada chamada. Depois corre `python campanha_turmas.py`, ou `python3 campanha_turmas.py` no macOS. O que deves ver:

   ```text
   10.0
   15.0
   7.0
   ```

   São as médias das 6 turmas, de uma turma sozinha e das três turmas da fase 4. Os três valores batem com o que já calculaste, e por isso a função está pronta a usar.

3. Apaga as três linhas de teste, que eram provisórias. No lugar delas, depois das duas linhas em branco e encostada à margem, escreve a parte principal:

   ```python
   quilos_por_turma = [12, 0, 9, 15, 6, 18]
   media_das_turmas = media(quilos_por_turma)
   print("Média:", media_das_turmas, "kg")
   acima_da_media = 0
   for i in range(0, NUMERO_DE_TURMAS):
       if quilos_por_turma[i] > media_das_turmas:
           # O i + 1 faz com que a turma de índice 0 seja, para as pessoas, a turma 1.
           print("A turma", i + 1, "trouxe mais do que a média")
           acima_da_media = acima_da_media + 1
   print("Turmas acima da média:", acima_da_media)
   ```

   Leitura guiada: é a parte principal da fase 7, com uma diferença. A soma da lista saiu e deu lugar à chamada `media(quilos_por_turma)`. A lista passa para o parâmetro `valores`, a função devolve 10.0, e o valor fica em `media_das_turmas`. O resto do programa usa esse nome, em vez de `media`, porque `media` passou a ser o nome da função.

4. Guarda e corre. O que deves ver: as mesmas cinco linhas da fase 7, a começar por `Média: 10.0 kg` e a acabar em `Turmas acima da média: 3`. Isto quer dizer que a função substituiu a soma sem mudar o resultado.

5. Provoca um erro de propósito: na função, apaga a palavra `return`, e deixa só `total / quantidade` na última linha. Guarda e corre. O que deves ver: a primeira linha passa a `Média: None kg`, e a seguir aparece um `TypeError` no `if`. Sem `return`, a função faz a conta e não a entrega, e o Python devolve `None`, o valor que quer dizer "nenhum valor". A seguir, o `if` tenta comparar um número com `None`, e o programa para. Volta a pôr o `return`, guarda e corre outra vez.

### Paragem 8

O `campanha_turmas.py` usa uma função para a média, testada sozinha antes de ser usada. O resultado é o mesmo da fase 7. Confere o teu com este:

```python
# campanha_turmas.py: os quilos das 6 turmas do 10.º ano, no fim da campanha.
# Calcula a média e diz que turmas trouxeram mais do que ela.

NUMERO_DE_TURMAS = 6


def media(valores):
    """Calcula a média de uma lista de números.

    A lista tem de ter pelo menos um número: com a lista vazia,
    a conta seria 0 / 0, e o programa parava com um erro.
    Devolve a média, um float.
    """
    quantidade = 0
    total = 0
    for valor in valores:
        quantidade = quantidade + 1
        total = total + valor
    return total / quantidade


quilos_por_turma = [12, 0, 9, 15, 6, 18]
media_das_turmas = media(quilos_por_turma)
print("Média:", media_das_turmas, "kg")
acima_da_media = 0
for i in range(0, NUMERO_DE_TURMAS):
    if quilos_por_turma[i] > media_das_turmas:
        # O i + 1 faz com que a turma de índice 0 seja, para as pessoas, a turma 1.
        print("A turma", i + 1, "trouxe mais do que a média")
        acima_da_media = acima_da_media + 1
print("Turmas acima da média:", acima_da_media)
```

Pensa antes de continuares: porque é que a variável da parte principal passou a chamar-se `media_das_turmas`, e não `media`? A resposta: se se chamasse `media`, a linha `media = media(quilos_por_turma)` trocava a função pelo número. A partir daí, o nome `media` já não era a função, e uma segunda chamada dava erro.

Acrescenta ao teu quadro de tradução:

| Pseudocódigo | Python | O que muda |
| --- | --- | --- |
| `Função media(valores)` | `def media(valores):` | `def` e os dois pontos |
| `devolver total / quantidade` | `return total / quantidade` | `return` |
| não havia | o texto entre três pares de aspas | a documentação da função |

## Problemas frequentes

### O Windows diz que não conhece o `python`, ou abre a Microsoft Store

O comando `python` não está disponível com esse nome neste computador. Fecha a loja, se abriu, e usa `py` em vez de `python`, como em `py ola.py`. Se nenhum dos dois funcionar, avisa o professor: o Python pode não estar instalado.

### `can't open file` e `No such file or directory`

A mensagem quer dizer "não consigo abrir o ficheiro: não existe esse ficheiro ou pasta". O terminal não está na pasta do ficheiro, ou o nome tem um erro. Confirma que o texto antes do cursor tem `fp-python` no fim. Confirma também que o nome no comando é igual ao do painel Explorer, com o `.py`.

### `SyntaxError: invalid syntax` ao escrever `python ola.py`

Estás dentro da consola do Python, e a linha começa por `>>>`. A consola espera Python, e não comandos do terminal. Escreve `exit()`, carrega em Enter e escreve o comando outra vez.

### O programa fica parado, sem mostrar nada

Pode estar à espera que escrevas um valor. Lê a última linha do terminal: deve ter uma pergunta. Escreve o número e carrega em Enter. Se já o fizeste e continua parado, é um ciclo que nunca acaba e não escreve nada. Carrega em Ctrl+C e confirma que a última linha do corpo do `while` lê o valor seguinte.

### `SyntaxError: expected ':'`

Faltam os dois pontos no fim da linha que a mensagem mostra. As linhas do `while`, do `if`, do `else`, do `for` e do `def` acabam sempre em dois pontos.

### `IndentationError: expected an indented block`

A linha a seguir a uns dois pontos ficou encostada à margem. Recua-a quatro espaços, com a tecla Tab ou com a barra de espaços.

### O resultado não muda depois de corrigires o código

O ficheiro não foi guardado. Guarda com Ctrl+S, ou Cmd+S no macOS, e corre outra vez.

### O programa repete a mesma coisa sem parar

O ciclo não acaba, porque falta a atualização ou a condição nunca fica falsa. Carrega em Ctrl+C no terminal para o parar, e confirma que a última linha do corpo do `while` lê o valor seguinte.

## Desafios

1. Os quilos negativos. Em `campanha.py`, a funcionária pode enganar-se e escrever um número negativo que não é o -1, como -5. Muda o programa para que, nesse caso, escreva "Valor inválido: uma turma não entrega quilos negativos.". A seguir, pede o valor outra vez, sem contar a turma. Testa com 12, -5, 0, 9 e -1, que deve dar 3 turmas e 21 quilos. Pista: o `Continuar` do pseudocódigo escreve-se `continue` no Python, e salta o resto da volta. Num `while`, não pode saltar a leitura do valor seguinte.

2. A turma que trouxe mais. Em `campanha_turmas.py`, faz o programa escrever também uma linha a dizer que turma trouxe mais quilos, e quantos, como `A turma 6 trouxe mais: 18 kg`. Testa também com a lista `[18, 0, 9, 15, 6, 12]`, em que é a turma 1. Pista: guarda a posição do maior até agora, e compara cada turma com o elemento nessa posição.

3. A média com uma casa decimal. Em `campanha.py`, com os valores 1, 1, 2 e -1, a média aparece com muitas casas decimais. Muda o programa para a média aparecer só com uma, como `1.3`. Pista: a função predefinida `round` arredonda um número e deixa escolher quantas casas ficam. Vê como se usa na secção "Funções predefinidas" do [guia](01-do-pseudocodigo-ao-python.md).

## Antes de terminares

- [ ] O `ola.py` corre e escreve as duas linhas.
- [ ] O `campanha.py` dá os resultados certos nos três casos: só -1; 15 e -1; 12, 0, 9 e -1.
- [ ] O `campanha_turmas.py` mostra a média de 10.0 quilos e as turmas 1, 4 e 6, sem as linhas de teste da função.
- [ ] O teu quadro de tradução tem as linhas das oito paragens.
- [ ] Sabes dizer de que tipo foi cada erro que provocaste: de sintaxe, de execução ou de lógica.
- [ ] Consegues explicar, por palavras tuas, como se passa uma linha de pseudocódigo para Python. E porque é que a média aparece como `7.0`, e não como 7.

![Rodapé](../imagens/rodape.png)
