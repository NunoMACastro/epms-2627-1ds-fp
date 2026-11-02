![Cabeçalho](../imagens/cabecalho.png)

# Seleção

Módulo Criar aplicações em linguagem de programação Python. Neste guia, os teus programas passam a decidir. Fazem uma coisa num caso e outra coisa noutro, conforme os valores que leem. Vais traduzir para Python as decisões que já escreves em pseudocódigo e testar cada caminho nas fronteiras. Para praticar, há o [laboratório](laboratorios/03-selecao-laboratorio.md) e a [ficha de exercícios](exercicios/03-selecao-exercicios.md) deste tema.

Até agora, os teus programas faziam sempre as mesmas contas e escreviam sempre as mesmas linhas, fosse qual fosse o valor lido. A partir deste tema, o que o programa faz depende dos dados. Mas ainda não repete instruções. Se a pessoa escrever um valor que não serve, o programa avisa e acaba. Voltar a pedir o valor é assunto do tema seguinte, o dos ciclos.

Lê ao teu ritmo, em várias vezes, com o computador ao lado. Cada exemplo pode ser copiado para um ficheiro e corrido, e é assim que se aprende mais.

## Neste guia

1. O que vais aprender
2. O que já sabes e vais usar
3. Programas que decidem
4. As comparações dão `True` ou `False`
5. Decidir com `if`
6. Os dois pontos e a indentação
7. Dois caminhos: `if` e `else`
8. Mais de dois caminhos: a cadeia com `elif`
9. Juntar condições com `and`, `or` e `not`
10. Validar um valor: dentro e fora de um intervalo
11. Os casos de fronteira, escolhidos antes de correr
12. Escolher entre valores certos com `match`
13. Exemplo guiado: validar e classificar a nota de um teste
14. Erros frequentes
15. Palavras novas deste guia
16. Verificar o que aprendeste
17. O que vem a seguir

## O que vais aprender

No fim deste guia, consegues:

- escrever comparações em Python e prever se dão `True` ou `False`;
- traduzir para Python o `Se`, o `Senão se` e o `Senão` do pseudocódigo, com os dois pontos e a indentação certos;
- juntar condições com `and`, `or` e `not`, e confirmar se um valor está dentro de um intervalo;
- pôr uma decisão dentro de outra, quando ela só faz sentido num dos ramos;
- escolher os casos de fronteira de uma decisão antes de correr o programa, e confirmar no computador o caminho de cada um;
- escolher entre valores fixos com `match`, e dizer quando serve e quando não serve;
- corrigir os erros mais comuns da seleção, como o `=` em vez de `==`, os dois pontos esquecidos, a indentação errada e a fronteira trocada.

## O que já sabes e vais usar

- Correr um script no terminal com o teu comando, `python`, `py` ou `python3`: guia [01 Do pseudocódigo ao Python](01-do-pseudocodigo-ao-python.md).
- A consola do Python, com o `>>>`: guia [01 Do pseudocódigo ao Python](01-do-pseudocodigo-ao-python.md).
- O `print` com vários valores separados por vírgulas, e os comentários com `#`: guia [01 Do pseudocódigo ao Python](01-do-pseudocodigo-ao-python.md).
- Os três tipos de erro, de sintaxe, de execução e de lógica: guia [01 Do pseudocódigo ao Python](01-do-pseudocodigo-ao-python.md).
- A rotina da depuração, em cinco passos: guia [01 Do pseudocódigo ao Python](01-do-pseudocodigo-ao-python.md).
- As variáveis, os nomes com traço baixo e as constantes em maiúsculas: guia [02 Dados e interação](02-dados-e-interacao.md).
- Os tipos `int`, `float`, `str` e `bool`, e a função `type`: guia [02 Dados e interação](02-dados-e-interacao.md).
- O `input`, que devolve sempre um texto, e a conversão com `int`: guia [02 Dados e interação](02-dados-e-interacao.md).
- As contas com `/`, `//` e `%`, e o erro da divisão por zero: guia [02 Dados e interação](02-dados-e-interacao.md).
- As condições e as comparações, no pseudocódigo: guia [03 Decisões e validação](../01-algoritmos/03-decisoes-e-validacao.md), secções "Condições e o tipo `bool`" e "Operadores de comparação".
- O `e`, o `ou` e o `não`: guia [03 Decisões e validação](../01-algoritmos/03-decisoes-e-validacao.md), secção "Operadores lógicos: `e`, `ou` e `não`".
- O `Se`, o `Senão se` e o `Senão`: guia [03 Decisões e validação](../01-algoritmos/03-decisoes-e-validacao.md), secções "Seleção simples", "Seleção composta" e "Seleção encadeada".
- A indentação, que mostra o que está dentro de uma decisão: guia [03 Decisões e validação](../01-algoritmos/03-decisoes-e-validacao.md), secção "A indentação mostra o que está dentro".
- Os intervalos e o contrário de um intervalo: guia [03 Decisões e validação](../01-algoritmos/03-decisoes-e-validacao.md), secção "Intervalos".
- As fronteiras e os casos de teste, com o resultado esperado escrito antes: guia [03 Decisões e validação](../01-algoritmos/03-decisoes-e-validacao.md), secção "Fronteiras e casos de teste".
- A validação de uma entrada: guia [03 Decisões e validação](../01-algoritmos/03-decisoes-e-validacao.md), secção "Casos válidos, casos inválidos e validação".
- O algoritmo da nota de um teste: guia [03 Decisões e validação](../01-algoritmos/03-decisoes-e-validacao.md), secção "Exemplo guiado: validar e classificar uma nota".

## Programas que decidem

O telemóvel mostra o aviso de bateria fraca só quando a bateria está baixa. Um jogo só te deixa passar ao nível seguinte se tiveres pontos que cheguem. A loja de aplicações só te deixa instalar um jogo se tiveres idade para ele. Em todos estes casos, o programa faz uma pergunta cuja resposta é sim ou não, e faz uma coisa diferente em cada caso.

Na algoritmia, escrevias estas decisões com `Se`, `Senão se` e `Senão`. Em Python, a ideia é a mesma, e muda só a forma de escrever. A grande diferença está noutro sítio. No papel, eras tu que seguias cada ramo, numa tabela. Agora é o computador, e podes experimentar cada caso em poucos segundos.

## As comparações dão `True` ou `False`

Antes de decidir, um programa tem de fazer uma pergunta que só tem duas respostas. "A bateria está abaixo de 20?" responde-se com sim ou não. Na algoritmia, a uma pergunta destas chamavas **condição**, e as duas respostas eram `true` e `false`.

Em Python, é igual, com uma diferença na escrita: os dois valores escrevem-se com maiúscula, `True` e `False`. São os dois únicos valores do tipo `bool`, que conheceste no guia 02. Uma comparação é uma conta cujo resultado é um destes dois valores. Tal como `7 + 3` dá `10`, `7 > 3` dá `True`.

Abre a consola do Python e experimenta. Antes de carregares em Enter em cada linha, prevê o que a consola vai responder.

```text
>>> 7 > 3
True
>>> 15 >= 18
False
>>> type(7 > 3)
<class 'bool'>
```

A consola escreve o resultado de cada comparação, como escrevia o resultado de uma conta. A terceira linha confirma o tipo: o resultado de `7 > 3` é um `bool`.

Leitura guiada: lê cada comparação como uma pergunta. "7 é maior do que 3?" Sim, e por isso `True`. "15 é maior ou igual a 18?" Não, e por isso `False`. A função `type` mostra de que tipo é o valor que está entre os parênteses, e aqui esse valor é o resultado da comparação.

Os sinais das comparações são os mesmos do pseudocódigo das aulas. Não tens nada de novo para decorar:

| Pseudocódigo | Python | A pergunta |
| --- | --- | --- |
| `==` | `==` | é igual a? |
| `!=` | `!=` | é diferente de? |
| `<` | `<` | é menor do que? |
| `<=` | `<=` | é menor ou igual a? |
| `>` | `>` | é maior do que? |
| `>=` | `>=` | é maior ou igual a? |
| `true`, `false` | `True`, `False` | os dois valores do tipo `bool` |

Com uma variável, a comparação usa o valor que a variável tem nesse momento. Antes de leres as respostas, prevê o que dá cada linha com `pontos` a valer 50:

```text
>>> pontos = 50
>>> pontos > 50
False
>>> pontos >= 50
True
>>> pontos != 50
False
```

A primeira linha não mostra resultado nenhum, porque é uma atribuição: guarda 50 em `pontos`. As outras três são perguntas, e a consola responde a cada uma.

Leitura guiada: repara nas linhas do `>` e do `>=`. Com 50, `pontos > 50` é falso e `pontos >= 50` é verdadeiro. Os dois sinais só dão respostas diferentes num valor, o próprio 50. Com 49 dão os dois `False`, e com 51 dão os dois `True`. Guarda esta observação, porque vais precisar dela quando escolheres os casos de teste.

Lembra-te da regra da algoritmia: um `=` dá um valor, e dois `==` perguntam. Na consola vês a diferença. `pontos = 50` não responde nada, e muda o valor da variável. `pontos == 50` responde `True` ou `False`, e não muda nada.

Os textos também se comparam. Dois textos são iguais quando têm exatamente as mesmas letras, pela mesma ordem. Prevê o que dá cada linha:

```text
>>> resposta = "sim"
>>> resposta == "sim"
True
>>> resposta == "Sim"
False
```

O segundo resultado é `False` porque o `S` maiúsculo e o `s` minúsculo são letras diferentes para o Python. Se um programa espera que a pessoa escreva `sim` e ela escreve `Sim`, a comparação falha. Por isso, as perguntas dos programas devem dizer exatamente o que se espera, como "Responde sim ou não".

Se escreveres `true` em minúsculas, como no pseudocódigo, o Python não o reconhece. Responde `NameError: name 'true' is not defined. Did you mean: 'True'?`, isto é, "o nome `true` não está definido; querias dizer `True`?". Procura uma variável chamada `true`, que não existe.

O resultado de uma comparação também se pode guardar numa variável, como o resultado de uma conta. Prevê o que a consola mostra na última linha:

```text
>>> idade = 15
>>> maior_de_idade = idade >= 18
>>> maior_de_idade
False
```

Na segunda linha, o lado direito calcula-se primeiro, como numa conta: `15 >= 18` dá `False`. Depois esse valor fica guardado em `maior_de_idade`, que passa a ser uma variável do tipo `bool`. É o mesmo que escrevias no pseudocódigo com `bool terminou = false`. Vais usar variáveis destas na secção do `and`, do `or` e do `not`.

## Decidir com `if`

Imagina que queres um programa que avisa quando a bateria do telemóvel está fraca, abaixo dos 20 por cento. O aviso só deve aparecer nesse caso. Com o que já sabias, um `print` escrevia sempre, fosse qual fosse a bateria. Falta uma forma de dizer "escreve isto só se".

No pseudocódigo das aulas, escrevias assim:

```text
const LIMITE_BATERIA_FRACA = 20
Escreve: "Bateria em percentagem?"
int bateria = ler valor
Se bateria < LIMITE_BATERIA_FRACA
    Escreve: "Bateria fraca. Liga o carregador."
Escreve: "Bateria verificada."
```

Em Python, o `Se` passa a `if`, a palavra inglesa para "se". Antes de correres, prevê o que aparece no ecrã com a bateria a 15, e depois a 50.

```python
# bateria.py: avisa quando a bateria do telemóvel está fraca.
LIMITE_BATERIA_FRACA = 20

bateria = int(input("Bateria em percentagem? "))
if bateria < LIMITE_BATERIA_FRACA:
    print("Bateria fraca. Liga o carregador.")
print("Bateria verificada.")
```

Com a bateria a 15, o ecrã fica assim:

```text
Bateria em percentagem? 15
Bateria fraca. Liga o carregador.
Bateria verificada.
```

Com a bateria a 50, fica assim:

```text
Bateria em percentagem? 50
Bateria verificada.
```

Com 15, a condição `15 < 20` dá `True`, e o aviso aparece. Com 50, `50 < 20` dá `False`, e o aviso é saltado. A última linha aparece nos dois casos.

Leitura guiada: começa pela linha do `if` e lê a condição com o valor da bateria no lugar do nome. A linha de baixo está quatro espaços mais para dentro, e por isso só se executa quando a condição dá `True`. A linha do `print("Bateria verificada.")` volta à margem do `if`, e por isso já está fora da decisão: executa-se sempre. A leitura e a constante são as do guia 02.

Uma instrução destas chama-se **seleção**: escolhe o que executar conforme uma condição. O `if` sozinho, sem mais nada, é a seleção simples da algoritmia. Executa um bloco quando a condição é verdadeira e não faz nada quando é falsa. O **bloco** são as linhas indentadas por baixo do `if`.

A tradução é quase palavra a palavra. `Se bateria < LIMITE_BATERIA_FRACA` passa a `if bateria < LIMITE_BATERIA_FRACA:`. Mudam duas coisas: a palavra `if` e os dois pontos no fim. Os dois pontos explicam-se na secção seguinte.

E com a bateria a 20, exatamente no limite? `20 < 20` dá `False`, porque 20 não é menor do que 20. O aviso não aparece. Se quisesses avisar também aos 20, a condição seria `bateria <= LIMITE_BATERIA_FRACA`. É uma decisão que se tira do enunciado, e não do código.

O erro típico desta ideia é escrever `=` numa condição, em vez de `==`. Imagina que queres uma mensagem quando a bateria está carregada, a 100. A condição certa é `if bateria == 100:`. Se, no `bateria.py`, trocares a linha 5 por `if bateria = 100:`, com um só sinal, o Python recusa o programa logo ao início:

```text
  File "C:\Users\aluno\Documents\fp-python\bateria.py", line 5
    if bateria = 100:
       ^^^^^^^^^^^^^
SyntaxError: invalid syntax. Maybe you meant '==' or ':=' instead of '='?
```

Quer dizer "erro de sintaxe: escrita inválida. Talvez quisesses `==` ou `:=` em vez de `=`". É um erro de sintaxe, e por isso nenhuma linha chega a correr. O `==` é o que querias. O `:=` é outra coisa, que não se usa nas aulas. O caminho do ficheiro, na primeira linha, muda de computador para computador. Numa condição queres sempre perguntar, e por isso o igual de uma condição é sempre `==`.

## Os dois pontos e a indentação

No pseudocódigo, era a indentação que mostrava o que estava dentro do `Se`. Em Python também é, e há mais um sinal: os **dois pontos** no fim da linha do `if`. Dizem ao Python que a seguir vem um bloco. Sem eles, o programa é recusado.

A **indentação** é o recuo de uma linha em relação à margem. Em Python, escreve-se com quatro espaços por cada nível, como no pseudocódigo das aulas. No VS Code, quando carregas em Enter depois dos dois pontos, a linha seguinte já começa com os quatro espaços. A tecla Tab também põe os quatro espaços, e Shift+Tab tira-os.

O bloco acaba na primeira linha que volta à margem do `if`. Nenhuma palavra marca esse fim. Por isso, mudar uma linha de margem pode mudar o que o programa faz, sem nenhuma mensagem de erro.

Compara estas duas versões do `bateria.py`, que só diferem na margem da última linha. A primeira é a da secção anterior:

```python
if bateria < LIMITE_BATERIA_FRACA:
    print("Bateria fraca. Liga o carregador.")
print("Bateria verificada.")
```

Na segunda, a última linha está quatro espaços para dentro:

```python
if bateria < LIMITE_BATERIA_FRACA:
    print("Bateria fraca. Liga o carregador.")
    print("Bateria verificada.")
```

Antes de leres a tabela, prevê o que aparece em cada versão com a bateria a 15 e a 50.

| bateria | Primeira versão | Segunda versão |
| ---: | --- | --- |
| 15 | Bateria fraca. Liga o carregador. Bateria verificada. | Bateria fraca. Liga o carregador. Bateria verificada. |
| 50 | Bateria verificada. | nada |

Leitura guiada: na primeira versão, o `print("Bateria verificada.")` está na margem do `if` e fora do bloco, e executa-se sempre. Na segunda, pertence ao bloco, e só se executa quando a bateria está fraca. Com 15, as duas versões mostram o mesmo. Só o caso 50 revela a diferença.

Se querias a primeira versão e escreveste a segunda, tens um erro de lógica. O programa corre até ao fim, sem mensagem nenhuma, e com 50 não mostra nada. Só o encontras se correres um caso em que a condição é falsa e compararares com o que esperavas. É por isso que se testa cada ramo, e não só o caso em que o aviso aparece.

## Dois caminhos: `if` e `else`

Os jogos trazem uma classificação PEGI, que diz a idade mínima recomendada para os jogar. Um jogo PEGI 12 é para quem tem 12 anos ou mais. Um programa que verifique a idade tem duas mensagens, e escreve sempre uma delas.

Em pseudocódigo:

```text
const IDADE_MINIMA = 12
Escreve: "Que idade tens?"
int idade = ler valor
Se idade >= IDADE_MINIMA
    Escreve: "Podes jogar este jogo."
Senão
    Escreve: "Este jogo é para quem tem 12 anos ou mais."
```

O `Senão` passa a `else`, a palavra inglesa para "senão". Antes de correres, prevê o que aparece com 11 anos e com 12.

```python
# pegi.py: diz se a idade chega para um jogo com a classificação PEGI 12.
IDADE_MINIMA = 12

idade = int(input("Que idade tens? "))
if idade >= IDADE_MINIMA:
    print("Podes jogar este jogo.")
else:
    print("Este jogo é para quem tem 12 anos ou mais.")
```

O resultado, para três idades:

| idade | `idade >= IDADE_MINIMA` | Bloco executado | Ecrã |
| ---: | --- | --- | --- |
| 11 | `11 >= 12` dá `False` | o do `else` | Este jogo é para quem tem 12 anos ou mais. |
| 12 | `12 >= 12` dá `True` | o do `if` | Podes jogar este jogo. |
| 13 | `13 >= 12` dá `True` | o do `if` | Podes jogar este jogo. |

Com 12, o ecrã fica assim:

```text
Que idade tens? 12
Podes jogar este jogo.
```

Leitura guiada: lê primeiro a condição do `if`. Depois procura, na mesma margem, o `else` que lhe pertence. Cada um tem o seu bloco, quatro espaços mais para dentro. Para cada idade, a condição avalia-se uma vez. Se der `True`, executa-se o bloco do `if` e salta-se o do `else`. Se der `False`, salta-se o do `if` e executa-se o do `else`.

O `else` não tem condição. Apanha todos os casos em que a condição do `if` é falsa, e por isso não precisa de perguntar nada. Mas tem dois pontos, porque também abre um bloco. Escreve-se na mesma margem do `if` a que pertence.

Numa decisão com `if` e `else` executa-se sempre um dos dois blocos, e só um. Não há nenhuma idade para a qual apareçam as duas mensagens, nem nenhuma para a qual não apareça nenhuma. A cada um destes caminhos chama-se **ramo**, como na algoritmia.

### Uma conta que só se faz num dos ramos

No guia 02, o `cartas.py` repartia as 52 cartas de um baralho pelos jogadores, com `//` e `%`. Com 0 jogadores, parava com `ZeroDivisionError`, porque não se divide por zero. Agora já podes evitá-lo: as contas vão para dentro do bloco de um `if`, e só se fazem quando há jogadores. Esta versão pergunta quantos jogadores há. Antes de correres, prevê o que aparece com 5 jogadores, e depois com 0.

```python
# cartas.py: reparte as cartas de um baralho pelos jogadores, sem partir nenhuma.
CARTAS_DO_BARALHO = 52

jogadores = int(input("Quantos jogadores? "))
# Sem este if, com 0 jogadores, o // dividia por zero e o programa parava.
if jogadores > 0:
    cartas_por_jogador = CARTAS_DO_BARALHO // jogadores
    cartas_que_sobram = CARTAS_DO_BARALHO % jogadores
    print("Cada jogador recebe", cartas_por_jogador, "cartas")
    print("Sobram", cartas_que_sobram, "cartas")
else:
    print("Sem jogadores, não há cartas para repartir.")
```

Com 5 jogadores, o ecrã fica assim:

```text
Quantos jogadores? 5
Cada jogador recebe 10 cartas
Sobram 2 cartas
```

Com 0, aparece só "Sem jogadores, não há cartas para repartir.", e o programa acaba sem erro.

Leitura guiada: as duas contas e os dois `print` do guia 02 estão agora quatro espaços para dentro, no bloco do `if`. Com 5, `5 > 0` dá `True`, e as contas fazem-se. Com 0, `0 > 0` dá `False`, o bloco é saltado inteiro, e a divisão nunca chega a fazer-se. O `else` escreve a mensagem que explica porquê. Sempre que uma conta divide por um valor lido, a pergunta a fazer é esta: e se esse valor for zero?

## Mais de dois caminhos: a cadeia com `elif`

Às vezes há mais do que duas possibilidades. No guia 03 da algoritmia viste o ecrã de um jogo que muda conforme as vidas. Com 0 vidas, o jogo acabou. Com 1 ou 2, estás quase a perder. Com 3 ou mais, o jogo continua. O pseudocódigo era este:

```text
Se vidas == 0
    Escreve: "Fim do jogo"
Senão se vidas < 3
    Escreve: "Cuidado, estás quase a perder"
Senão
    Escreve: "O jogo continua"
```

Em Python, o `Senão se` passa a `elif`. A palavra junta o princípio de `else` e de `if`, e é o `Senão se` numa só palavra. Antes de correres, prevê o que aparece com 5 vidas, com 2 e com 0.

```python
# vidas.py: a mensagem do ecrã de um jogo, conforme as vidas que restam.
vidas = int(input("Quantas vidas tens? "))
if vidas == 0:
    print("Fim do jogo")
elif vidas < 3:
    print("Cuidado, estás quase a perder")
else:
    print("O jogo continua")
```

O resultado:

| vidas | `vidas == 0` | `vidas < 3` | Bloco executado | Ecrã |
| ---: | --- | --- | --- | --- |
| 5 | `False` | `False` | o do `else` | O jogo continua |
| 2 | `False` | `True` | o do `elif` | Cuidado, estás quase a perder |
| 0 | `True` | não é avaliada | o do `if` | Fim do jogo |

Leitura guiada: lê a cadeia de cima para baixo, uma condição de cada vez, e para na primeira que der `True`. Se nenhuma der `True`, desces até ao `else`, que não pergunta nada e apanha o que sobra. Na tabela, "não é avaliada" mostra onde a execução parou de perguntar.

Repara no 0. A segunda condição também seria verdadeira, porque 0 é menor do que 3. Mas nunca chega a ser avaliada. Por isso, quem perdeu todas as vidas vê "Fim do jogo", e não o aviso.

Uma cadeia de `if`, `elif` e `else` funciona com as três regras da seleção encadeada da algoritmia:

1. As condições avaliam-se por ordem, de cima para baixo.
2. A primeira condição verdadeira ganha. Executa-se o seu bloco, e o programa continua na primeira linha depois da cadeia. As condições de baixo nem chegam a ser avaliadas.
3. Se nenhuma condição for verdadeira, executa-se o bloco do `else`. Se não houver `else`, não se executa nada.

Pode haver tantos `elif` quantos forem precisos. O `if` e os `elif` e o `else` escrevem-se todos na mesma margem, cada um com os seus dois pontos. É esse alinhamento que mostra que são partes de uma só cadeia.

Destas regras resulta uma coisa útil. Quando o Python chega ao `elif vidas < 3`, já sabe que as vidas não são 0. Se fossem, tinha entrado no primeiro ramo. Por isso, a segunda condição não precisa de perguntar também se as vidas são mais do que 0.

### A ordem das condições conta

Imagina que alguém escreveu a mesma cadeia por outra ordem, com o aviso primeiro:

```python
if vidas < 3:
    print("Cuidado, estás quase a perder")
elif vidas == 0:
    print("Fim do jogo")
else:
    print("O jogo continua")
```

Antes de leres a explicação, prevê o que esta versão escreve com 0 vidas.

Escreve "Cuidado, estás quase a perder". A primeira condição pergunta se 0 é menor do que 3, e é. Pela regra 2, a primeira condição verdadeira ganha. O `elif vidas == 0` nunca dá `True`. Só chegam lá os valores de 3 ou mais, e nenhum deles é 0. A mensagem "Fim do jogo" nunca aparece.

O programa corre sem nenhuma mensagem de erro. É um erro de lógica, e só o caso 0 o revela: com 2 e com 5, as duas versões dão o mesmo. A regra para a ordem é esta. Quando uma condição está contida noutra, como "ter 0 vidas" está contida em "ter menos de 3", a mais estreita vem primeiro.

## Juntar condições com `and`, `or` e `not`

Muitas decisões dependem de mais do que uma pergunta. Na algoritmia, juntavas condições com `e` e `ou`, e trocavas o valor de uma condição com `não`. Em Python, as três palavras passam para inglês, em minúsculas:

| Pseudocódigo | Python | Quando dá verdadeiro |
| --- | --- | --- |
| `e` | `and` | só quando as duas condições são verdadeiras |
| `ou` | `or` | quando pelo menos uma das duas é verdadeira, também quando são as duas |
| `não` | `not` | troca o valor: `not True` dá `False`, e `not False` dá `True` |

As tabelas de verdade são as do guia 03 da algoritmia. Podes confirmá-las na consola, com os valores escritos diretamente:

```text
>>> True and False
False
>>> True or False
True
>>> not False
True
```

O torneio de jogos online da escola é para alunos dos 12 aos 17 anos, incluindo os 12 e os 17. Para entrar, a idade tem de cumprir as duas condições ao mesmo tempo: ser 12 ou mais, e ser 17 ou menos. Antes de leres as respostas, prevê o que dá a condição com 14 anos, e depois com 19:

```text
>>> idade = 14
>>> idade >= 12 and idade <= 17
True
>>> idade = 19
>>> idade >= 12 and idade <= 17
False
```

Com 14, as duas comparações dão `True`, e o `and` dá `True`. Com 19, a primeira dá `True` e a segunda dá `False`. Basta uma ser falsa para o `and` dar `False`.

Leitura guiada: o Python calcula primeiro cada comparação, à esquerda e à direita do `and`, e só depois junta os dois resultados. Com 19, faz `19 >= 12`, que dá `True`, depois `19 <= 17`, que dá `False`, e por fim `True and False`, que dá `False`.

O `or` serve quando basta uma das condições. Na cantina, pagas com dinheiro ou com cartão. As variáveis seguintes guardam valores do tipo `bool`, como viste na secção das comparações. Prevê os resultados:

```text
>>> tem_dinheiro = False
>>> tem_cartao = True
>>> tem_dinheiro or tem_cartao
True
>>> not tem_dinheiro
True
```

O `or` dá `True` porque uma das duas variáveis é `True`. O `not` troca o `False` de `tem_dinheiro` por `True`: "não tem dinheiro" é verdade.

O `not` também se põe antes de uma comparação, entre parênteses. Lembra-te da armadilha da algoritmia. O contrário de "a idade é 12 ou mais" não é "a idade é 12 ou menos". É "a idade é menos de 12". Confirma-o na consola, com a idade a 14:

```text
>>> idade = 14
>>> not (idade >= 12)
False
>>> idade < 12
False
```

As duas linhas dizem o mesmo e dão o mesmo resultado, para qualquer idade. Quando trocas o sentido de uma comparação, o limite muda de lado. A segunda forma é mais fácil de ler, e é a que se usa nas aulas.

### Quando se misturam `and` e `or`

Na algoritmia, quando misturavas `e` com `ou`, usavas parênteses para mostrar o que se avalia primeiro. Em Python faz-se o mesmo. Com a piscina do guia 03, entra quem paga e traz touca, ou quem tem menos de 6 anos. Prevê o que dá cada condição para uma criança de 4 anos, sem bilhete e sem touca:

```text
>>> paga = False
>>> touca = False
>>> idade = 4
>>> (paga and touca) or idade < 6
True
>>> paga and (touca or idade < 6)
False
```

Só a primeira segue a regra. Os parênteses mudaram o resultado, e por isso escrevem-se sempre que se mistura `and` com `or`.

## Validar um valor: dentro e fora de um intervalo

As pessoas enganam-se a escrever. Quem quer escrever 4 pode escrever 44, ou -4. Um programa que aceita esses valores sem os confirmar dá respostas erradas com ar de certas. A isso responde a validação. **Validar** um valor é confirmar que ele serve antes de o usar. Na algoritmia, a validação vinha sempre antes do resto, e em Python também.

Um jogo de tabuleiro joga-se com 2 a 6 jogadores, incluindo os extremos. Os valores aceites formam um **intervalo**: todos os inteiros de 2 a 6. Em Python, como no pseudocódigo, escreve-se com duas comparações ligadas por `and`:

```python
jogadores >= 2 and jogadores <= 6
```

O contrário, um valor fora do intervalo, escreve-se com `or`. Um valor está fora quando fica abaixo do limite de baixo ou acima do limite de cima:

```python
jogadores < 2 or jogadores > 6
```

Repara no que mudou de uma para a outra. O `and` passou a `or`. E cada comparação passou ao seu contrário, com o limite a mudar de lado: `>= 2` passou a `< 2`, e `<= 6` passou a `> 6`. Para estar dentro, um valor tem de cumprir as duas comparações. Para estar fora, basta falhar uma.

Este programa valida o número de jogadores antes de começar. Antes de correres, prevê o que aparece com 1, com 2, com 6 e com 7.

```python
# jogadores.py: confirma o número de jogadores de um jogo de tabuleiro, de 2 a 6.
MINIMO_JOGADORES = 2
MAXIMO_JOGADORES = 6

jogadores = int(input("Quantos jogadores (2 a 6)? "))
if jogadores < MINIMO_JOGADORES or jogadores > MAXIMO_JOGADORES:
    print("Esse número não dá. O jogo é para 2 a 6 jogadores.")
else:
    print("Jogo para", jogadores, "jogadores. Boa sorte!")
```

O resultado:

| jogadores | `jogadores < 2` | `jogadores > 6` | Com `or` | Ecrã |
| ---: | --- | --- | --- | --- |
| 1 | `True` | `False` | `True` | Esse número não dá. O jogo é para 2 a 6 jogadores. |
| 2 | `False` | `False` | `False` | Jogo para 2 jogadores. Boa sorte! |
| 6 | `False` | `False` | `False` | Jogo para 6 jogadores. Boa sorte! |
| 7 | `False` | `True` | `True` | Esse número não dá. O jogo é para 2 a 6 jogadores. |

Leitura guiada: o `if` pergunta primeiro se o valor é inválido. Se for, o programa avisa e não faz mais nada, porque o `else` é saltado. Só os valores que passam a validação chegam ao bloco do `else`. A pergunta do `input` diz o intervalo, para quem usa o programa saber o que se espera dele. Os limites são constantes, porque são regras do jogo.

O erro típico desta ideia é ligar as duas comparações de fora com `and`. Com `jogadores < MINIMO_JOGADORES and jogadores > MAXIMO_JOGADORES`, a condição pede um número que seja ao mesmo tempo menor do que 2 e maior do que 6. Nenhum número é as duas coisas, e a condição dá sempre `False`. Com 7, o ecrã fica assim:

```text
Quantos jogadores (2 a 6)? 7
Jogo para 7 jogadores. Boa sorte!
```

O programa aceita qualquer valor, e os valores válidos continuam a dar o resultado certo. Por isso, este erro passa despercebido a quem só testa valores do meio, como o 4. Corrige-se com `or`, porque para estar fora basta falhar um dos lados.

O Python aceita também uma forma mais curta, `2 <= jogadores <= 6`, que lê como na matemática. Nas aulas continuamos a escrever duas comparações ligadas por `and`, como na algoritmia. É assim que a condição se escreve no C, que vais aprender a seguir, e assim lê-se da mesma maneira nas duas linguagens.

### Uma decisão dentro de outra

Às vezes, o que o programa faz com um valor válido tem mais do que uma linha, e até outra decisão. Imagina que, com 6 jogadores, o jogo quer avisar que a mesa ficou cheia. Esse aviso só faz sentido para um número válido. Por isso, a decisão nova vai para dentro do bloco do `else`.

Antes de correres, prevê o que aparece com 6, com 4 e com 7.

```python
# jogadores.py: confirma o número de jogadores de um jogo de tabuleiro, de 2 a 6.
MINIMO_JOGADORES = 2
MAXIMO_JOGADORES = 6

jogadores = int(input("Quantos jogadores (2 a 6)? "))
if jogadores < MINIMO_JOGADORES or jogadores > MAXIMO_JOGADORES:
    print("Esse número não dá. O jogo é para 2 a 6 jogadores.")
else:
    print("Jogo para", jogadores, "jogadores. Boa sorte!")
    # Este if está dentro do else: só se avalia com um número válido.
    if jogadores == MAXIMO_JOGADORES:
        print("Mesa cheia: já não entra mais ninguém.")
```

Com 6, aparecem duas linhas:

```text
Quantos jogadores (2 a 6)? 6
Jogo para 6 jogadores. Boa sorte!
Mesa cheia: já não entra mais ninguém.
```

Com 4, aparece só "Jogo para 4 jogadores. Boa sorte!". Com 7, aparece só o aviso de que o número não dá.

Leitura guiada: o `if` de dentro está quatro espaços mais para dentro do que o `else`, porque pertence ao seu bloco. O `print` da mesa cheia está oito espaços para dentro, porque está dentro de dois blocos. Com 7, o programa entra no primeiro ramo e salta o `else` inteiro, também o `if` que está lá dentro. Dentro de um bloco pode estar qualquer instrução, também outro `if`, e a indentação diz sempre a que bloco pertence cada linha.

### Um texto que não é número

A validação com `if` só funciona depois de o `int` ter convertido o texto num número. Se a pessoa escrever `dois` em vez de `2`, o programa para antes de chegar ao `if`, com o erro que conheceste no guia 02:

```text
ValueError: invalid literal for int() with base 10: 'dois'
```

Quer dizer "erro de valor: escrita inválida para um `int` na base 10". Por agora, quem usa o programa tem de escrever um número inteiro. Neste tema, um valor inválido trata-se com um `if` que avisa, e o programa acaba. Voltar a pedir o valor até ele ser válido é do tema seguinte, com os ciclos. Tratar o texto que não é número sem o programa parar fica para mais tarde, quando aprenderes a apanhar erros de execução.

## Os casos de fronteira, escolhidos antes de correr

Viste na secção das comparações que `>` e `>=` só dão respostas diferentes num valor, o da própria fronteira. Uma **fronteira** é o sítio onde a resposta de uma decisão muda. No `bateria.py`, a resposta muda entre 19 e 20: com 19 aparece o aviso, e com 20 já não aparece. Um programa testado só com 5 e com 50 pode ter o sinal errado sem tu dares por isso.

A regra para escolher os casos de teste é a da algoritmia. Para cada fronteira, testas o valor imediatamente abaixo, o próprio valor da fronteira e o valor imediatamente acima. Com números inteiros, os vizinhos são os valores a uma unidade de distância. Para a fronteira do 20, são o 19, o 20 e o 21.

A parte mais importante é a ordem do trabalho. Os resultados esperados escrevem-se antes de correr, a partir do enunciado, e não a partir do que o programa mostra. Se escreveres o esperado depois de correr, copias o que o programa fez, certo ou errado, e o teste deixa de servir para nada.

No caderno, uma tabela de casos de teste tem esta forma. As duas primeiras colunas preenchem-se antes de correr. A terceira preenche-se depois, uma linha de cada vez:

| Caso | Resultado esperado | Resultado obtido |
| ---: | --- | --- |
| 19 | Bateria fraca. Liga o carregador. Bateria verificada. | |
| 20 | Bateria verificada. | |
| 21 | Bateria verificada. | |

Para cada caso, prevês também o ramo por onde a execução vai seguir. Com 19, entra no bloco do `if`. Com 20 e com 21, salta-o. É esse o raciocínio que mostra que percebeste a decisão, e não apenas que acertaste no resultado.

Num programa sem repetições, cada execução testa um caso. Para testar três casos, corres o programa três vezes. No terminal, a seta para cima do teclado volta a escrever o último comando, e assim não tens de o escrever outra vez. Carregas na seta, em Enter, e escreves o valor do caso seguinte.

Se um caso der um resultado diferente do esperado, segues a rotina da depuração, os cinco passos que aprendeste no guia 01. Primeiro, escreves o caso que falhou, o esperado e o obtido, e dizes que tipo de erro é. Depois, formulas uma hipótese, verifica-la com os valores, corriges a causa e voltas a correr todos os casos. No exemplo guiado vais ver a rotina aplicada a uma fronteira trocada.

## Escolher entre valores certos com `match`

Imagina o menu de um jogo. A pessoa escolhe 1 para jogar, 2 para ver as instruções e 3 para sair. Com o que já sabes, escreve-se uma cadeia de `if`, em que cada condição compara a mesma variável com um número diferente:

```python
# menu_if.py: o menu de um jogo, com if, elif e else.
opcao = int(input("1 Jogar, 2 Instruções, 3 Sair. Escolhe: "))
if opcao == 1:
    print("A começar o jogo.")
elif opcao == 2:
    print("Adivinha o número secreto em 10 tentativas ou menos.")
elif opcao == 3:
    print("Até à próxima!")
else:
    print("Essa opção não existe.")
```

Está certa, mas repete `opcao ==` em todas as condições. Para este caso, em que se compara um só valor com vários valores fixos, o Python tem uma forma mais curta, o `match`:

```python
# menu.py: o menu de um jogo, com uma mensagem para cada opção.
opcao = int(input("1 Jogar, 2 Instruções, 3 Sair. Escolhe: "))
match opcao:
    case 1:
        print("A começar o jogo.")
    case 2:
        print("Adivinha o número secreto em 10 tentativas ou menos.")
    case 3:
        print("Até à próxima!")
    case _:
        print("Essa opção não existe.")
```

Antes de correres, prevê o que aparece se a pessoa escrever 2, e se escrever 7.

Com 2, aparece "Adivinha o número secreto em 10 tentativas ou menos.". Com 7, aparece "Essa opção não existe.". Com 2, o ecrã fica assim:

```text
1 Jogar, 2 Instruções, 3 Sair. Escolhe: 2
Adivinha o número secreto em 10 tentativas ou menos.
```

As duas versões dão sempre o mesmo resultado, para qualquer número que a pessoa escreva. Experimenta as duas com 1, 2, 3 e 7, e confirma.

Leitura guiada: a linha `match opcao:` diz que valor se vai comparar. Cada `case` traz um valor fixo. O Python compara a `opcao` com cada um, de cima para baixo, e executa o bloco do primeiro que for igual. O `case _:`, com o traço baixo, apanha qualquer outro valor, como o `else` de uma cadeia de `if`. Os `case` ficam indentados debaixo do `match`, e os blocos de cada `case` ficam mais quatro espaços para dentro. Cada linha de `match` e de `case` acaba em dois pontos.

O `case _` fica sempre no fim. Se viesse primeiro, apanhava todos os valores, e os outros `case` nunca seriam usados. O Python recusa um programa assim, com um erro de sintaxe.

Os valores de um `case` também podem ser textos, entre aspas. No fim de um jogo, o programa pergunta se a pessoa quer jogar outra vez, e ela responde `s` ou `n`. A resposta é um texto, e por isso não se converte com `int`. Antes de correres, prevê o que aparece com `s`, e depois com `sim`.

```python
# outra_vez.py: no fim de um jogo, pergunta se a pessoa quer jogar outra vez.
resposta = input("Queres jogar outra vez (s/n)? ")
match resposta:
    case "s":
        print("Nova partida a começar.")
    case "n":
        print("Obrigado por jogares.")
    case _:
        print("Responde só s ou n.")
```

Com `s`, o ecrã fica assim:

```text
Queres jogar outra vez (s/n)? s
Nova partida a começar.
```

Com `sim`, aparece "Responde só s ou n.".

Leitura guiada: o `input` não tem `int` à volta, e por isso `resposta` guarda o texto que a pessoa escreveu. Cada `case` traz um texto entre aspas, e o Python compara-o com a resposta, letra a letra, como viste na secção das comparações. O texto `sim` não é igual a `s`, nem a `n`, e cai no `case _`. Com `S` maiúsculo, acontece o mesmo, porque `"S"` e `"s"` são valores diferentes. As aspas nos `case` fazem falta: sem elas, `s` seria o nome de uma variável, e não a letra, e o Python recusa o programa.

Nas aulas, o `match` usa-se só para comparar um valor com valores fixos, como números ou textos. Para uma condição como `nota >= 10`, ou para juntar condições com `and` e `or`, usa-se o `if`. O pseudocódigo das aulas não tinha nada parecido. O `match` é uma forma mais curta de uma cadeia de `Se` que compara sempre a mesma variável com `==`. Quando não tens a certeza, a cadeia de `if` serve sempre.

O `match` só existe a partir da versão 3.10 do Python. Numa versão mais antiga, o programa é recusado com um erro de sintaxe na linha do `match`. Para saberes que versão tens, escreve no terminal:

```bash
python --version
```

No Windows, se o teu comando for `py`, escreve `py --version`. No macOS, escreve `python3 --version`. Aparece uma linha como `Python 3.13.2`. Para usares o `match`, o número a seguir ao 3 tem de ser 10 ou mais.

## Exemplo guiado: validar e classificar a nota de um teste

No guia 03 da algoritmia escreveste o algoritmo que valida e classifica a nota de um teste, e testaste-o à mão nas fronteiras. Agora vais traduzi-lo para Python e pôr o computador a correr os mesmos casos. O pensamento já está feito. O que este exemplo treina é a tradução e o teste no computador.

### Passo 1: o enunciado

> Um professor quer um algoritmo que o ajude a classificar os testes. O algoritmo lê a nota de um teste, que é um número inteiro na escala de 0 a 20. Se a nota for igual ou superior a 10, escreve "Positiva". Se for inferior a 10, escreve "Negativa". Se a nota escrita não pertencer à escala, o algoritmo escreve "Nota inválida" e não a classifica.

### Passo 2: os casos de teste, antes do programa

Há três fronteiras. A primeira fica entre -1 e 0, no extremo de baixo da escala. A segunda fica entre 9 e 10, no limiar de positiva. A terceira fica entre 20 e 21, no extremo de cima. Para cada uma, testas o valor de baixo, o da fronteira e o de cima. Os resultados esperados vêm do enunciado, e escrevem-se agora, antes de haver programa. É a tabela que fizeste no guia 03:

| Nota | Resultado esperado | Porque é que este caso foi escolhido |
| ---: | --- | --- |
| -1 | Nota inválida | Imediatamente abaixo da escala |
| 0 | Negativa | O extremo de baixo da escala, que é válido |
| 1 | Negativa | Imediatamente acima do extremo de baixo |
| 9 | Negativa | Imediatamente abaixo do limiar |
| 10 | Positiva | O próprio limiar, que o enunciado diz ser positiva |
| 11 | Positiva | Imediatamente acima do limiar |
| 19 | Positiva | Imediatamente abaixo do extremo de cima |
| 20 | Positiva | O extremo de cima da escala, que é válido |
| 21 | Nota inválida | Imediatamente acima da escala |

### Passo 3: o pseudocódigo

Este é o algoritmo do guia 03, na forma das aulas:

```text
const NOTA_MINIMA = 0
const NOTA_MAXIMA = 20
const LIMIAR_POSITIVA = 10
Escreve: "Nota do teste (inteiro de 0 a 20)?"
int nota = ler valor
Se nota < NOTA_MINIMA ou nota > NOTA_MAXIMA
    Escreve: "Nota inválida"
Senão se nota >= LIMIAR_POSITIVA
    Escreve: "Positiva"
Senão
    Escreve: "Negativa"
```

A validação é a primeira condição da cadeia, e usa o contrário do intervalo da escala, com `ou`. A condição de positiva não precisa de dizer que a nota é menor ou igual a 20. Quando o algoritmo chega ao `Senão se`, já sabe que a nota é válida.

### Passo 4: traduzir linha a linha

Cada linha do pseudocódigo passa a uma linha de Python. A tabela mostra o que muda:

| Pseudocódigo | Python | O que muda |
| --- | --- | --- |
| `const NOTA_MINIMA = 0` | `NOTA_MINIMA = 0` | sem `const`: o nome em maiúsculas já diz que é uma constante |
| `Escreve: "Nota do teste (inteiro de 0 a 20)?"` e `int nota = ler valor` | `nota = int(input("Nota do teste (inteiro de 0 a 20)? "))` | a pergunta e a leitura juntam-se no `input`, com a conversão |
| `Se nota < NOTA_MINIMA ou nota > NOTA_MAXIMA` | `if nota < NOTA_MINIMA or nota > NOTA_MAXIMA:` | `if`, `or` e os dois pontos |
| `Senão se nota >= LIMIAR_POSITIVA` | `elif nota >= LIMIAR_POSITIVA:` | `elif` e os dois pontos |
| `Senão` | `else:` | `else` e os dois pontos |
| `Escreve: "Positiva"` | `print("Positiva")` | `print`, com a mesma indentação |

### Passo 5: o script completo

Antes de leres o script, tenta escrevê-lo tu, a partir da tabela do passo 4. Depois compara.

```python
# classificar_nota.py: valida a nota de um teste e classifica-a como positiva ou negativa.
NOTA_MINIMA = 0
NOTA_MAXIMA = 20
LIMIAR_POSITIVA = 10

nota = int(input("Nota do teste (inteiro de 0 a 20)? "))
# A validação vem primeiro: uma nota fora da escala não se classifica.
if nota < NOTA_MINIMA or nota > NOTA_MAXIMA:
    print("Nota inválida")
elif nota >= LIMIAR_POSITIVA:
    print("Positiva")
else:
    print("Negativa")
```

Leitura guiada: as constantes ficam no início, separadas do resto por uma linha em branco. A leitura converte logo o texto num `int`, porque as comparações precisam de um número. A cadeia lê-se como no pseudocódigo: o Python testa as condições por ordem e executa só o bloco da primeira que for verdadeira. Se nenhuma for, executa o bloco do `else`. Repara nos dois pontos no fim de cada uma das três linhas que abrem um bloco, e nos quatro espaços de cada `print`.

### Passo 6: correr os casos

Guarda o ficheiro como `classificar_nota.py` e corre-o com o teu comando, `python classificar_nota.py`. Escreve o primeiro caso, o -1. Depois carrega na seta para cima, em Enter, e escreve o caso seguinte, até teres corrido os nove. Antes de cada um, diz qual é o ramo que esperas.

Com 10, o ecrã fica assim:

```text
Nota do teste (inteiro de 0 a 20)? 10
Positiva
```

Na tabela seguinte, cada linha resume uma execução. Mostra o valor das duas condições, o ramo por onde a execução seguiu e o que apareceu no ecrã.

| nota | Validação, com `or` | `nota >= LIMIAR_POSITIVA` | Ramo executado | Ecrã |
| ---: | --- | --- | --- | --- |
| -1 | `True` | não é avaliada | o do `if` | Nota inválida |
| 0 | `False` | `False` | o do `else` | Negativa |
| 1 | `False` | `False` | o do `else` | Negativa |
| 9 | `False` | `False` | o do `else` | Negativa |
| 10 | `False` | `True` | o do `elif` | Positiva |
| 11 | `False` | `True` | o do `elif` | Positiva |
| 19 | `False` | `True` | o do `elif` | Positiva |
| 20 | `False` | `True` | o do `elif` | Positiva |
| 21 | `True` | não é avaliada | o do `if` | Nota inválida |

O 0 é negativa, e não inválida, porque `0 < 0` dá `False`: zero não é menor do que zero. O 10 é positiva porque o operador é `>=`, e `10 >= 10` dá `True`. O 20 é positiva, e não inválida, porque `20 > 20` dá `False`. Em cada fronteira, quem decide é um só operador.

### Passo 7: comparar com o previsto

Compara a coluna "Ecrã" com a coluna "Resultado esperado" do passo 2. Coincidem nos nove casos. O programa faz o que o enunciado pede em todas as fronteiras. É a mesma conclusão a que chegaste no guia 03, com o trace à mão. A diferença é que agora foi o computador a executar, e podes repetir os nove casos sempre que mudares o programa.

### Passo 8: o caso que apanha a fronteira trocada

Imagina que, ao escrever o script, te enganavas no limiar e escrevias `elif nota > LIMIAR_POSITIVA:`, sem o igual. Corres os casos, e os resultados batem certo até ao 9. No caso 10, o ecrã mostra isto:

```text
Nota do teste (inteiro de 0 a 20)? 10
Negativa
```

Segues a rotina da depuração, em cinco passos:

1. Observar e reproduzir. O caso que falhou é o 10. O esperado, tirado do enunciado, é "Positiva", e o obtido é "Negativa". O programa correu até ao fim, sem mensagem: é um erro de lógica.
2. Formular uma hipótese. "A condição de positiva deixa o 10 de fora."
3. Verificar a hipótese. Na consola, `10 > 10` dá `False`, e `10 >= 10` dá `True`. Com o `>`, o 10 não entra no ramo da positiva e cai no `else`.
4. Corrigir a causa. Muda-se o `>` para `>=`, porque o enunciado diz "igual ou superior a 10".
5. Voltar a testar tudo. Corres outra vez os nove casos, também os que já passavam. Agora coincidem todos.

Repara que, com o `>`, o 9 e o 11 davam o resultado certo. Só o próprio 10 mostrava o erro. É por isso que o valor da fronteira está sempre nos casos de teste.

## Erros frequentes

Os erros desta secção não ficaram em nenhuma das secções anteriores. Para cada um, ficas a saber o que aparece, porque acontece e como se corrige. Os outros estão na secção da ideia que explicam:

- o `=` em vez de `==` numa condição, em "Decidir com `if`";
- a linha que ficou dentro ou fora do bloco por engano, em "Os dois pontos e a indentação";
- a ordem da cadeia trocada, em "Mais de dois caminhos: a cadeia com `elif`";
- o `and` em vez de `or` na validação, em "Validar um valor: dentro e fora de um intervalo";
- a fronteira trocada, `>` em vez de `>=`, no passo 8 do exemplo guiado.

### A indentação em falta

O que se vê, no `bateria.py`, com a linha do aviso encostada à margem:

```text
  File "C:\Users\aluno\Documents\fp-python\bateria.py", line 6
    print("Bateria fraca. Liga o carregador.")
    ^^^^^
IndentationError: expected an indented block after 'if' statement on line 5
```

Quer dizer "erro de indentação: esperava-se um bloco indentado depois do `if` da linha 5". Acontece quando a linha a seguir a uns dois pontos fica encostada à margem. Depois de um `if`, de um `elif`, de um `else`, de um `match` ou de um `case`, o Python exige pelo menos uma linha indentada. É um erro de sintaxe: o programa nem arranca. Corrige-se pondo quatro espaços antes da linha, com a tecla Tab.

### Os dois pontos esquecidos

O que se vê, com `if nota >= 10` sem os dois pontos:

```text
    if nota >= 10
                 ^
SyntaxError: expected ':'
```

Quer dizer "erro de sintaxe: esperavam-se os dois pontos". O sinal `^` aponta para o sítio onde eles faltam, no fim da linha. Acontece a quem traduz o pseudocódigo à letra, porque lá não havia dois pontos. Corrige-se acrescentando os dois pontos no fim da linha. Todas as linhas que abrem um bloco, `if`, `elif`, `else`, `match` e `case`, acabam em dois pontos.

### Palavras do pseudocódigo no meio do Python

O que se vê, com `if idade >= 12 e idade <= 17:`:

```text
    if idade >= 12 e idade <= 17:
                   ^
SyntaxError: invalid syntax
```

O sinal `^` aponta para o `e`. Acontece quando uma palavra do pseudocódigo fica no programa: `e`, `ou`, `não`, `Se`, `Senão`. O Python não as conhece. Com `Senão:` no lugar de `else:`, a mensagem é a mesma, e o `^` aponta para o fim dessa linha. Com `ou` e com `não`, o Python acrescenta uma sugestão, como em `invalid syntax. Did you mean 'or'?`, isto é, "querias dizer `or`?". Corrige-se com a palavra do Python, que está nas tabelas deste guia: aqui, `and`.

### Dois `if` separados em vez de uma cadeia

Imagina a validação da nota num `if` sozinho, e a classificação noutro `if` a seguir, na mesma margem:

```python
if nota < NOTA_MINIMA or nota > NOTA_MAXIMA:
    print("Nota inválida")
if nota >= LIMIAR_POSITIVA:
    print("Positiva")
else:
    print("Negativa")
```

O que se vê, com 21:

```text
Nota do teste (inteiro de 0 a 20)? 21
Nota inválida
Positiva
```

Aparecem duas mensagens, quando devia aparecer uma. Com -1, aparece "Nota inválida" e logo a seguir "Negativa". Os casos válidos continuam certos, e por isso este erro só se vê com os casos inválidos.

Acontece porque a diferença para o programa certo está numa só palavra. Onde devia estar `elif` está `if`. Um `if` encostado à margem começa uma decisão nova, que não tem nada a ver com a de cima. O segundo `if` avalia-se sempre, mesmo quando o primeiro já apanhou uma nota inválida.

Corrige-se trocando o segundo `if` por `elif`. Quando os casos são alternativas uns dos outros, e só um deve acontecer, escrevem-se numa só cadeia.

## Palavras novas deste guia

- `True` e `False`: os dois valores do tipo `bool` em Python, com maiúscula; são o `true` e o `false` do pseudocódigo.
- Condição: uma pergunta cuja resposta só pode ser `True` ou `False`.
- Comparação: uma condição que compara dois valores, com `==`, `!=`, `<`, `<=`, `>` ou `>=`.
- Seleção: uma instrução que escolhe o que executar conforme uma condição.
- `if`: o `Se` do pseudocódigo, que executa o seu bloco quando a condição é verdadeira.
- Bloco: as linhas indentadas por baixo de uma linha que acaba em dois pontos, que só se executam no seu caso.
- Dois pontos: o sinal no fim da linha que abre um bloco, como a de um `if` ou de um `case`.
- Indentação: o recuo de quatro espaços por nível, que mostra a que bloco pertence cada linha.
- `else`: o `Senão` do pseudocódigo, sem condição, que apanha todos os casos que sobram.
- Ramo: cada um dos caminhos de uma decisão, o bloco de um `if`, de um `elif` ou de um `else`.
- `elif`: o `Senão se` do pseudocódigo, numa só palavra, que acrescenta uma condição a uma cadeia.
- Cadeia: um `if` seguido de um ou mais `elif` e, se for preciso, de um `else`, em que a primeira condição verdadeira ganha.
- `and`, `or` e `not`: o `e`, o `ou` e o `não` do pseudocódigo.
- Intervalo: o conjunto dos valores entre dois limites, como os inteiros de 2 a 6.
- Validar: confirmar que um valor serve antes de o usar.
- Fronteira: o sítio onde a resposta de uma decisão muda.
- Caso de fronteira: o valor de uma fronteira ou um dos seus vizinhos, escolhido para testar a decisão.
- `match` e `case`: a forma de comparar um valor com vários valores fixos.
- `case _`: o `case` que apanha qualquer outro valor, como o `else` de uma cadeia; fica sempre no fim.

## Verificar o que aprendeste

Usa estas perguntas para te testares. Responde a cada uma sem olhar para o guia. Se não conseguires, volta à secção que explica a ideia.

1. Com `moedas = 80`, o que responde a consola a `moedas >= 80`, a `moedas > 80` e a `moedas != 80`? De que tipo são as três respostas?
2. Qual é a diferença entre `nivel = 3` e `nivel == 3`? Qual delas pode estar numa linha de `if`?
3. Traduz para Python: `Se temperatura >= 18 e temperatura < 26`, com o bloco `Escreve: "Temperatura boa"`.
4. Para que servem os dois pontos no fim da linha de um `if`? E o que diz ao Python onde acaba o bloco?
5. Num `if` com `else`, pode acontecer executarem-se os dois blocos? E nenhum? Porquê?
6. Numa cadeia, porque é que a condição mais estreita, como `vidas == 0`, tem de vir antes de uma mais larga, como `vidas < 3`?
7. Escreve a condição de "a idade está entre 13 e 17, inclusive", e o seu contrário, sem usar `not`.
8. Um colega validou a idade com `idade < 13 and idade > 17`. Que idades o programa aceita? Que caso de teste mostra o erro?
9. Para a regra "bónus a partir de 500 pontos, inclusive", que três casos de teste escolhes? Escreve o resultado esperado de cada um antes de pensares no código.
10. Porque é que os resultados esperados se escrevem antes de correr o programa, e não depois?
11. Num `match`, o que faz o `case _`? Porque é que tem de ser o último?
12. Porque é que se usa o `if`, e não o `match`, para classificar uma nota como positiva ou negativa?
13. Que versão do Python é precisa para o `match`, e como confirmas a tua?
14. Com o `>` no lugar do `>=` no `classificar_nota.py`, que caso falha? Porque é que o 9 e o 11 não mostram o erro?

## O que vem a seguir

Para praticar este tema, faz o [laboratório](laboratorios/03-selecao-laboratorio.md). Nele constróis, fase a fase, dois programas da campanha de recolha de alimentos da escola. O balanço decide o que mostrar conforme os valores lidos, e o posto de recolha usa o `match`. Depois faz a [ficha de exercícios](exercicios/03-selecao-exercicios.md).

O tema seguinte é [04 Ciclos while e for](04-ciclos-while-e-for.md). Neste tema, quando a pessoa escreve um valor inválido, o programa avisa e acaba, e é preciso corrê-lo outra vez. No tema seguinte, o programa passa a repetir instruções. Assim, pode voltar a pedir o valor até ele ser válido, e ler muitos valores seguidos, contando-os e somando-os.

![Rodapé](../imagens/rodape.png)
