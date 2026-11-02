![Cabeçalho](../imagens/cabecalho.png)

# Laboratório: Seleção

Laboratório do tema Seleção, do módulo Criar aplicações em linguagem de programação Python. Vais construir dois programas para a campanha de recolha de alimentos da escola, que decidem o que escrever conforme os valores que leem. Cada passo diz o que fazer, porquê e o que deves ver, e avanças ao teu ritmo. Tudo o que precisas está aqui; o [guia do tema](03-selecao.md) tem a teoria completa, para quem quiser saber mais.

## O que vais construir

A escola organiza uma campanha de recolha de alimentos, e cada turma entrega os alimentos que juntou. No fim, quem organiza a campanha já contou as turmas e somou os quilos. Falta o balanço: a média por turma e o nível a que a campanha chegou.

O primeiro programa, `balanco.py`, faz esse balanço. Pergunta quantas turmas entregaram alimentos e quantos quilos se recolheram ao todo. Depois decide o que mostrar. A média só aparece quando houve entregas. A mensagem do nível depende dos quilos. Quando há média, diz também se cada turma trouxe, em média, 10 quilos ou mais. E, se os valores forem impossíveis, o programa avisa e não faz contas com eles. Com 6 turmas e 120 quilos, o ecrã fica assim:

```text
Quantas turmas entregaram alimentos? 6
Quantos quilos se recolheram ao todo? 120
Turmas que entregaram: 6
Total: 120 kg
Média por turma: 20.0 kg
Meta atingida!
Fim do balanço.
```

O segundo programa, `posto.py`, serve no posto de recolha. A pessoa escolhe o alimento que trouxe, por um número, e o programa diz em que caixa o deve pôr. Com o 2, o ecrã fica assim:

```text
1 Arroz e massa
2 Enlatados
3 Leite
4 Azeite e óleo
Que alimento trouxeste? 2
Vai para a caixa verde.
```

Pelo caminho, ficas a saber traduzir para Python as decisões do pseudocódigo. Vais usar o `if`, o `else`, a cadeia com `elif`, uma decisão dentro de outra, o `or` e o `match`. E testas cada decisão nas fronteiras, com os resultados esperados escritos no caderno antes de correr.

| Fase | O que muda | O que funciona no fim |
| --- | --- | --- |
| 1 | Nada no disco; experimentas na consola do Python | Sabes prever se uma comparação dá `True` ou `False` |
| 2 | `balanco.py`, com um `if` | O programa diz "Meta atingida!" só quando os quilos chegam à meta |
| 3 | `balanco.py`, com `if` e `else` | O programa mostra a média só quando houve entregas |
| 4 | `balanco.py`, com uma cadeia `elif` | O programa diz o nível da campanha, em três casos |
| 5 | `balanco.py`, com um `if` dentro de outro | O programa diz se a média por turma foi boa, só quando há média |
| 6 | `balanco.py`, com a validação | O programa avisa dos valores impossíveis antes de fazer contas |
| 7 | `posto.py`, com `if` e depois com `match` | O programa diz em que caixa vai cada alimento |

No fim, a tua pasta tem, além dos ficheiros dos temas anteriores:

```text
fp-python/
├── balanco.py
└── posto.py
```

## Palavras que vais usar

- Condição: uma pergunta cuja resposta só pode ser `True` ou `False`, como `total_quilos >= 100`. Para saber mais, vê a secção "As comparações dão `True` ou `False`" do [guia](03-selecao.md).
- `True` e `False`: os dois valores do tipo `bool`, o verdadeiro e o falso, com maiúscula.
- Comparação: uma condição que compara dois valores, com `==`, `!=`, `<`, `<=`, `>` ou `>=`. Os sinais são os mesmos do pseudocódigo.
- `if`: o `Se` do pseudocódigo. Executa o seu bloco só quando a condição é verdadeira.
- Bloco: as linhas indentadas por baixo de uma linha que acaba em dois pontos. Só se executam no seu caso.
- Indentação: o recuo de quatro espaços por nível, que mostra a que bloco pertence cada linha.
- `else`: o `Senão` do pseudocódigo. Não tem condição, e apanha os casos que sobram.
- Ramo: cada um dos caminhos de uma decisão.
- `elif`: o `Senão se` do pseudocódigo, numa só palavra.
- Cadeia: um `if` seguido de um ou mais `elif` e de um `else`, em que a primeira condição verdadeira ganha.
- `and`, `or` e `not`: o `e`, o `ou` e o `não` do pseudocódigo.
- Validar: confirmar que um valor serve antes de o usar.
- Fronteira: o sítio onde a resposta de uma decisão muda, como os 100 quilos da meta.
- `match` e `case`: a forma de comparar um valor com vários valores fixos, com `case _` para todos os outros.

## O que precisas

- A pasta `fp-python`, aberta no VS Code, e o comando que corre o Python no teu computador, `python`, `py` ou `python3`. Se não tiveres a pasta aberta, abre-a no menu File, com a opção Open Folder....
- O terminal do VS Code, no menu Terminal, com a opção New Terminal. O texto antes do cursor deve acabar em `fp-python`.
- O Python 3.10 ou mais recente, para a fase 7, que usa o `match`. Confirma a versão com `python --version`, ou com o teu comando. Deve aparecer uma linha como `Python 3.13.2`. O número a seguir ao 3 tem de ser 10 ou mais. Se for menor, faz a fase 7 até ao passo 3 e avisa o professor.
- O caderno, para as previsões e para as tabelas de casos de teste.

Os resultados e as mensagens de erro deste laboratório são os do Python 3.14. Num Python mais antigo, uma mensagem pode ter outras palavras, ou não ter os sinais `^` por baixo da linha. O nome do erro, a palavra antes dos dois pontos na última linha, é o mesmo.

Neste laboratório, onde o texto diz `python`, usa o teu comando.

## Se alguma coisa falhar

1. Guardaste o ficheiro? O Python corre o que está guardado no disco, e não o que vês no ecrã. Guarda com Ctrl+S, ou Cmd+S no macOS, antes de cada vez que corres. Uma bola cheia no separador do ficheiro, no lugar do X, quer dizer que há alterações por guardar.
2. Estás na pasta certa? O texto antes do cursor, no terminal, tem de acabar em `fp-python`. Se não acabar, abre um terminal novo, no menu Terminal, com a opção New Terminal.
3. Estás na consola do Python sem quereres? Se a linha começa por `>>>`, escreve `exit()` e carrega em Enter, para voltares ao terminal.
4. O programa parou e não volta ao terminal? Está à espera que escrevas um valor. O `balanco.py` faz duas perguntas: depois de responderes à primeira, aparece a segunda.
5. Copiaste o código à mão? Confirma os dois pontos no fim das linhas do `if`, do `elif`, do `else`, do `match` e do `case`. Confirma também os quatro espaços da indentação, e o `==` nas comparações de igualdade.

## Fase 1: As comparações dão `True` ou `False`

Para decidir, um programa faz uma pergunta que só tem duas respostas. "Os quilos chegam à meta?" responde-se com sim ou não. Em Python, a resposta é `True` ou `False`, os dois valores do tipo `bool`, com maiúscula. Uma comparação é uma conta que dá um destes dois valores, tal como `2 + 3` dá 5. Nesta fase experimentas comparações na consola, sem criar ficheiros. Para saber mais, lê a secção "As comparações dão `True` ou `False`" do [guia](03-selecao.md).

1. Entra na consola: no terminal, escreve só `python`, com o teu comando, e carrega em Enter. O que deves ver: duas linhas em inglês, a primeira com a versão do Python, e por baixo `>>>`. É a consola, à espera de uma linha de Python.

2. Prevê a resposta a cada uma destas três linhas. Depois escreve-as, uma de cada vez, a seguir ao `>>>`, e confirma:

   ```text
   >>> 120 >= 100
   True
   >>> 99 >= 100
   False
   >>> type(99 >= 100)
   <class 'bool'>
   ```

   "120 é maior ou igual a 100?" Sim, e a consola responde `True`. "99 é maior ou igual a 100?" Não, e a resposta é `False`. A terceira linha mostra que o resultado de uma comparação é do tipo `bool`. Se aparecer `NameError` numa linha que escreveste com `true` ou `false`, é a minúscula: em Python, os dois valores escrevem-se com maiúscula.

3. Agora com uma variável, como num programa. Prevê cada resposta, escreve as linhas e confirma:

   ```text
   >>> turmas = 6
   >>> turmas == 6
   True
   >>> turmas == 0
   False
   >>> turmas > 0
   True
   >>> turmas = 0
   >>> turmas > 0
   False
   ```

   As linhas com um só `=` não mostram resposta nenhuma, porque são atribuições: guardam um valor em `turmas`. As linhas com `==`, com `>` e com os outros sinais são perguntas, e a consola responde. A mesma pergunta, `turmas > 0`, deu `True` e depois `False`, porque o valor da variável mudou entre as duas.

4. Sai da consola: escreve `exit()` e carrega em Enter. O que deves ver: o terminal normal, com o texto da pasta antes do cursor.

### Paragem 1

Sabes prever se uma comparação dá `True` ou `False`, e a consola confirma-o. No caderno, faz uma tabela com duas colunas, "Pseudocódigo" e "Python", e escreve nela a primeira linha: `true` e `false` passam a `True` e `False`. Vais acrescentar uma ou duas linhas em cada paragem.

Pensa antes de continuares: qual é a diferença entre `turmas = 0` e `turmas == 0`? A resposta: a primeira guarda 0 na variável, e o valor que lá estava perde-se. A segunda pergunta se a variável vale 0, responde `True` ou `False`, e não muda nada.

## Fase 2: Decidir com `if`

A campanha tem uma meta: 100 quilos de alimentos. O programa deve escrever "Meta atingida!" quando o total chega aos 100, e não escrever nada sobre a meta nos outros casos. No pseudocódigo, escrevias `Se total_quilos >= META_QUILOS`, com a mensagem indentada por baixo. Em Python, o `Se` passa a `if`, e a linha acaba em dois pontos. As linhas indentadas por baixo, quatro espaços para dentro, são o bloco: só se executam quando a condição é verdadeira. A primeira linha que volta à margem do `if` já está fora, e executa-se sempre. Para saber mais, lê as secções "Decidir com `if`" e "Os dois pontos e a indentação" do [guia](03-selecao.md).

1. Cria o ficheiro `balanco.py`. No painel Explorer, passa o rato por cima de `FP-PYTHON` e carrega no ícone New File.... Escreve o nome `balanco.py` e carrega em Enter. Escreve nele este conteúdo, que é o ficheiro completo:

   ```python
   # balanco.py: o balanço da campanha de recolha de alimentos da escola.
   # Lê quantas turmas entregaram e o total de quilos, e mostra o resultado da campanha.
   META_QUILOS = 100

   turmas = int(input("Quantas turmas entregaram alimentos? "))
   total_quilos = int(input("Quantos quilos se recolheram ao todo? "))
   print("Turmas que entregaram:", turmas)
   print("Total:", total_quilos, "kg")
   # Esta mensagem só aparece quando a condição é verdadeira.
   if total_quilos >= META_QUILOS:
       print("Meta atingida!")
   print("Fim do balanço.")
   ```

   Quando escreves a linha do `if` e carregas em Enter depois dos dois pontos, o VS Code começa a linha seguinte com os quatro espaços. Na linha do `print("Fim do balanço.")`, apaga-os, para a linha voltar à margem.

   Leitura guiada: o programa começa pela constante da meta e pelas duas leituras, que converte logo em números inteiros, como no guia 02. Os dois `print` seguintes escrevem sempre. Depois vem a decisão. A linha do `if` tem a condição e os dois pontos, e o `print("Meta atingida!")`, quatro espaços para dentro, é o seu bloco. O último `print` está na margem, fora do bloco, e por isso aparece sempre.

2. Antes de correres, prevê o que aparece com 6 turmas e 120 quilos, e depois com 4 turmas e 99 quilos. Guarda e corre:

   ```bash
   python balanco.py
   ```

   Responde às duas perguntas com 6 e 120. O que deves ver:

   ```text
   Quantas turmas entregaram alimentos? 6
   Quantos quilos se recolheram ao todo? 120
   Turmas que entregaram: 6
   Total: 120 kg
   Meta atingida!
   Fim do balanço.
   ```

   Corre outra vez, agora com 4 e 99. Para não escreveres o comando outra vez, carrega na seta para cima do teclado, que repete o último comando, e depois em Enter. O que deves ver:

   ```text
   Quantas turmas entregaram alimentos? 4
   Quantos quilos se recolheram ao todo? 99
   Turmas que entregaram: 4
   Total: 99 kg
   Fim do balanço.
   ```

   Com 120, a condição `120 >= 100` deu `True`, e o bloco executou-se. Com 99, `99 >= 100` deu `False`, e o bloco foi saltado. O `print` da margem apareceu nos dois casos.

3. Testa a fronteira. A resposta do programa muda entre 99 e 100 quilos, e é aí que um sinal errado se esconde. Os casos de uma fronteira são o valor de baixo, o da fronteira e o de cima: 99, 100 e 101. No caderno, escreve primeiro o resultado esperado de cada um, tirado do enunciado: "Meta atingida!" a partir dos 100, incluindo os 100. Depois confere com esta tabela:

   | Quilos | "Meta atingida!" aparece? |
   | ---: | --- |
   | 99 | não |
   | 100 | sim |
   | 101 | sim |

   Corre o programa com 4 turmas e cada um dos três valores, e confirma. O que deves ver: o 100 já mostra "Meta atingida!", porque `100 >= 100` dá `True`. Se o 100 não mostrar a mensagem, confirma que o sinal é `>=`, e não `>`.

4. Experimenta a indentação. Na última linha, põe quatro espaços antes do `print("Fim do balanço.")`, para ela entrar no bloco do `if`. Antes de correres, prevê o que muda com 4 turmas e 99 quilos. Guarda e corre com esses valores. O que deves ver:

   ```text
   Quantas turmas entregaram alimentos? 4
   Quantos quilos se recolheram ao todo? 99
   Turmas que entregaram: 4
   Total: 99 kg
   ```

   A linha "Fim do balanço." desapareceu. Passou a pertencer ao bloco, e com 99 o bloco é saltado. O programa correu sem mensagem de erro: é um erro de lógica, e só um caso em que a condição é falsa o mostra. Tira os quatro espaços, guarda e corre outra vez com 99, para confirmares que a linha voltou.

5. Provoca um erro de propósito. Apaga os dois pontos no fim da linha do `if`. Antes de correres, prevê que tipo de erro vai ser. Guarda e corre. O que deves ver, sem nenhuma pergunta antes:

   ```text
     File "C:\Users\aluno\Documents\fp-python\balanco.py", line 10
       if total_quilos >= META_QUILOS
                                     ^
   SyntaxError: expected ':'
   ```

   É um erro de sintaxe: o Python recusa o programa antes de executar qualquer linha, e por isso nem faz as perguntas. A mensagem quer dizer "esperavam-se os dois pontos", e o `^` aponta para o sítio onde faltam. O caminho do ficheiro muda de computador para computador. Volta a pôr os dois pontos, guarda e corre, para confirmares que o programa funciona.

### Paragem 2

O `balanco.py` diz "Meta atingida!" só quando o total chega aos 100 quilos, e confirmaste a fronteira com 99, 100 e 101.

Acrescenta à tua tabela do caderno:

| Pseudocódigo | Python |
| --- | --- |
| `Se totalQuilos >= META_QUILOS` | `if total_quilos >= META_QUILOS:`, com os dois pontos |
| o bloco, quatro espaços para dentro | o mesmo: a indentação diz o que está dentro |

Pensa antes de continuares: porque é que o caso 100 é mais importante do que o caso 150, para testar este `if`? A resposta: com 150, o `>=` e o `>` dão os dois `True`, e o teste não distingue os sinais. Com 100, só o `>=` dá `True`. É o único caso que mostra se o sinal está certo.

## Fase 3: Dois caminhos, com `if` e `else`

O balanço deve mostrar a média por turma: o total a dividir pelo número de turmas. Mas, se nenhuma turma entregou, a conta é uma divisão por zero, que não tem resultado e para o programa. Por isso, como no pseudocódigo, a média só se calcula quando há pelo menos uma turma. Nos outros casos, o programa escreve outra mensagem. São dois caminhos, e escreve-se sempre um deles. O `Senão` do pseudocódigo passa a `else`, com os dois pontos e sem condição, na mesma margem do `if`. Para saber mais, lê a secção "Dois caminhos: `if` e `else`" do [guia](03-selecao.md).

1. Primeiro, vê o problema. Em `balanco.py`, acrescenta estas duas linhas logo a seguir ao `print("Total:", total_quilos, "kg")`, encostadas à margem:

   ```python
   media = total_quilos / turmas
   print("Média por turma:", media, "kg")
   ```

   Guarda e corre com 6 turmas e 120 quilos. O que deves ver: a linha `Média por turma: 20.0 kg`, depois do total. A média aparece como `20.0`, e não como 20, porque a divisão com `/` dá sempre um `float`, como viste no guia 02.

2. Antes de correres outra vez, prevê o que acontece com 0 turmas e 0 quilos. Corre com esses valores. O que deves ver:

   ```text
   Quantas turmas entregaram alimentos? 0
   Quantos quilos se recolheram ao todo? 0
   Turmas que entregaram: 0
   Total: 0 kg
   Traceback (most recent call last):
     File "C:\Users\aluno\Documents\fp-python\balanco.py", line 9, in <module>
       media = total_quilos / turmas
               ~~~~~~~~~~~~~^~~~~~~~
   ZeroDivisionError: division by zero
   ```

   É um erro de execução: o programa correu até à linha da divisão e parou a meio, com a mensagem "divisão por zero". As linhas de antes já tinham aparecido. Lê-se de baixo para cima: a última linha diz o erro, e as de cima dizem a linha onde aconteceu.

3. Agora a correção. Substitui as duas linhas que acrescentaste no passo 1 por estas:

   ```python
   # Sem este if, com zero turmas, a conta seria uma divisão por zero e o programa parava.
   if turmas > 0:
       media = total_quilos / turmas
       print("Média por turma:", media, "kg")
   else:
       print("Não houve entregas, por isso não há média.")
   ```

   Leitura guiada: o `if` pergunta se há turmas. Se houver, executa-se o seu bloco, com as duas linhas da média. Se não houver, salta-se esse bloco e executa-se o do `else`, que escreve a outra mensagem. A divisão está dentro do bloco do `if`, e por isso só se faz quando `turmas` é maior do que 0. O `else` está na mesma margem do `if`, com os dois pontos, e o seu `print` quatro espaços para dentro.

4. Prepara os casos de teste. A fronteira desta decisão está entre 0 e 1 turmas. O valor de baixo seria -1, mas não há turmas negativas, e a fase 6 vai recusá-las. Por isso, os casos da fronteira são 0 e 1. Junta-lhes um caso do meio, como 6. No caderno, escreve primeiro o que esperas que apareça na linha da média de cada um. Depois confere com esta tabela:

   | Turmas | Quilos | A linha da média |
   | ---: | ---: | --- |
   | 6 | 120 | `Média por turma: 20.0 kg` |
   | 1 | 15 | `Média por turma: 15.0 kg` |
   | 0 | 0 | `Não houve entregas, por isso não há média.` |

   Guarda e corre os três casos. O que deves ver: em cada um, a linha da tabela, e no fim sempre "Fim do balanço.". Com 0 turmas, o programa já não para: o `else` escreve a mensagem e a divisão nunca se faz. Se ainda aparecer `ZeroDivisionError`, confirma que as linhas da média estão dentro do bloco do `if`, quatro espaços para dentro.

### Paragem 3

O `balanco.py` mostra a média só quando houve entregas, e nunca para com uma divisão por zero. Confere o teu com este:

```python
# balanco.py: o balanço da campanha de recolha de alimentos da escola.
# Lê quantas turmas entregaram e o total de quilos, e mostra o resultado da campanha.
META_QUILOS = 100

turmas = int(input("Quantas turmas entregaram alimentos? "))
total_quilos = int(input("Quantos quilos se recolheram ao todo? "))
print("Turmas que entregaram:", turmas)
print("Total:", total_quilos, "kg")
# Sem este if, com zero turmas, a conta seria uma divisão por zero e o programa parava.
if turmas > 0:
    media = total_quilos / turmas
    print("Média por turma:", media, "kg")
else:
    print("Não houve entregas, por isso não há média.")
# Esta mensagem só aparece quando a condição é verdadeira.
if total_quilos >= META_QUILOS:
    print("Meta atingida!")
print("Fim do balanço.")
```

Acrescenta à tua tabela do caderno:

| Pseudocódigo | Python |
| --- | --- |
| `Senão` | `else:`, com os dois pontos e sem condição |
| `float media = totalQuilos / turmas` | `media = total_quilos / turmas`, sem o tipo; o resultado é um `float` |

Pensa antes de continuares: há algum caso em que aparecem as duas mensagens, a da média e a de "Não houve entregas"? A resposta: não. Com `if` e `else`, executa-se sempre um dos dois blocos, e só um. Se `turmas > 0` for verdadeiro, executa-se o do `if`; se for falso, o do `else`.

## Fase 4: Mais de dois caminhos, com a cadeia `elif`

A mensagem da meta tem agora só dois casos: aparece ou não aparece. A organização quer três. Com 200 quilos ou mais, o dobro da meta, o programa dá os parabéns à escola. Com 100 quilos ou mais, diz que a meta foi atingida. Abaixo dos 100, diz quantos quilos faltam. No pseudocódigo, escrevias uma seleção encadeada, com `Se`, `Senão se` e `Senão`. Em Python, o `Senão se` passa a `elif`, numa só palavra, com os dois pontos. As condições avaliam-se de cima para baixo, e só se executa o bloco da primeira que for verdadeira. Se nenhuma for, executa-se o do `else`. Para saber mais, lê a secção "Mais de dois caminhos: a cadeia com `elif`" do [guia](03-selecao.md).

1. Em `balanco.py`, substitui as três linhas da meta, desde o comentário `# Esta mensagem só aparece quando a condição é verdadeira.` até ao `print("Meta atingida!")`, por estas:

   ```python
   # A condição mais exigente vem primeiro: quem chega ao dobro também chegou à meta.
   if total_quilos >= 2 * META_QUILOS:
       print("O dobro da meta! A escola está de parabéns.")
   elif total_quilos >= META_QUILOS:
       print("Meta atingida!")
   else:
       print("Quilos que faltam para a meta:", META_QUILOS - total_quilos)
   ```

   O `print("Fim do balanço.")` fica onde estava, na margem, depois da cadeia.

   Leitura guiada: lê a cadeia de cima para baixo. A primeira condição pergunta se o total chega a 200, o dobro da meta. Se não chegar, o `elif` pergunta se chega a 100. Quando o programa chega ao `elif`, já sabe que o total é menor do que 200, porque senão tinha entrado no primeiro ramo. Se as duas condições forem falsas, o `else` apanha o resto, e calcula os quilos que faltam. Essa conta só faz sentido nesse ramo, com o total abaixo da meta. O `if`, o `elif` e o `else` estão na mesma margem, e são uma só cadeia.

2. Prepara os casos de teste. Esta cadeia tem duas fronteiras, nos 100 e nos 200 quilos. Para cada uma, testas o valor de baixo, o da fronteira e o de cima. Usa sempre 4 turmas. No caderno, escreve primeiro a mensagem do nível que esperas em cada caso. Depois confere com esta tabela:

   | Quilos | A mensagem do nível |
   | ---: | --- |
   | 99 | `Quilos que faltam para a meta: 1` |
   | 100 | `Meta atingida!` |
   | 101 | `Meta atingida!` |
   | 199 | `Meta atingida!` |
   | 200 | `O dobro da meta! A escola está de parabéns.` |
   | 201 | `O dobro da meta! A escola está de parabéns.` |

   Guarda e corre os seis casos, com a seta para cima para repetir o comando. Com 200, o ecrã fica assim:

   ```text
   Quantas turmas entregaram alimentos? 4
   Quantos quilos se recolheram ao todo? 200
   Turmas que entregaram: 4
   Total: 200 kg
   Média por turma: 50.0 kg
   O dobro da meta! A escola está de parabéns.
   Fim do balanço.
   ```

   O que deves ver nos outros cinco: a mensagem do nível da tabela, sempre uma só. Isto quer dizer que a cadeia escolheu um ramo em cada caso, e que os dois sinais `>=` incluem as fronteiras. Se o 200 mostrar "Meta atingida!", confirma a ordem das condições, e lê o passo seguinte.

3. Experimenta a ordem. Troca as duas primeiras condições da cadeia e as suas mensagens, para ficarem assim:

   ```python
   if total_quilos >= META_QUILOS:
       print("Meta atingida!")
   elif total_quilos >= 2 * META_QUILOS:
       print("O dobro da meta! A escola está de parabéns.")
   ```

   Antes de correres, prevê o que aparece com 200 quilos, e depois com 250. Guarda e corre com 4 turmas e 200 quilos. O que deves ver: `Meta atingida!`, e não os parabéns. Com 250 aparece o mesmo.

   Com 200, a primeira condição, `200 >= 100`, é verdadeira, e a primeira condição verdadeira ganha. O `elif` nunca dá `True`. Só chegam lá os totais abaixo de 100, e nenhum deles chega aos 200. A mensagem dos parabéns nunca aparece. É um erro de lógica, e só os casos de 200 ou mais o mostram. Volta a pôr a ordem do passo 1, guarda e corre com 200, para confirmares os parabéns.

### Paragem 4

O `balanco.py` diz o nível da campanha nos três casos, e confirmaste as duas fronteiras com seis casos. Confere o teu com este:

```python
# balanco.py: o balanço da campanha de recolha de alimentos da escola.
# Lê quantas turmas entregaram e o total de quilos, e mostra o resultado da campanha.
META_QUILOS = 100

turmas = int(input("Quantas turmas entregaram alimentos? "))
total_quilos = int(input("Quantos quilos se recolheram ao todo? "))
print("Turmas que entregaram:", turmas)
print("Total:", total_quilos, "kg")
# Sem este if, com zero turmas, a conta seria uma divisão por zero e o programa parava.
if turmas > 0:
    media = total_quilos / turmas
    print("Média por turma:", media, "kg")
else:
    print("Não houve entregas, por isso não há média.")
# A condição mais exigente vem primeiro: quem chega ao dobro também chegou à meta.
if total_quilos >= 2 * META_QUILOS:
    print("O dobro da meta! A escola está de parabéns.")
elif total_quilos >= META_QUILOS:
    print("Meta atingida!")
else:
    print("Quilos que faltam para a meta:", META_QUILOS - total_quilos)
print("Fim do balanço.")
```

Acrescenta à tua tabela do caderno:

| Pseudocódigo | Python |
| --- | --- |
| `Senão se totalQuilos >= META_QUILOS` | `elif total_quilos >= META_QUILOS:`, numa só palavra e com os dois pontos |

Pensa antes de continuares: porque é que a condição do `elif` não precisa de dizer `total_quilos < 2 * META_QUILOS`? A resposta: quando o programa chega ao `elif`, a primeira condição já deu falso. O total já é, com certeza, menor do que 200.

## Fase 5: Uma decisão dentro de outra

A organização acha que a campanha correu bem quando cada turma trouxe, em média, 10 quilos ou mais, e quer uma mensagem para esse caso. Mas a média só existe quando houve entregas: calcula-se dentro do bloco do `if turmas > 0:`. Por isso, a decisão nova vai para dentro desse bloco. Dentro de um bloco pode estar qualquer instrução, também outro `if`. Fica na mesma margem das outras linhas do bloco, e o seu `print` fica mais quatro espaços para dentro, com oito. No pseudocódigo era igual: cada nível de indentação são quatro espaços. Para saber mais, lê a parte "Uma decisão dentro de outra", na secção "Validar um valor: dentro e fora de um intervalo" do [guia](03-selecao.md).

1. Em `balanco.py`, acrescenta a constante da média boa, na linha a seguir a `META_QUILOS = 100`:

   ```python
   MEDIA_BOA = 10
   ```

2. No bloco do `if turmas > 0:`, a seguir ao `print` da média, acrescenta estas três linhas. O comentário e o `if` levam quatro espaços, como o `print` da média, e o `print` novo leva oito:

   ```python
       # Este if está dentro do bloco do if turmas > 0, porque só aí existe média.
       if media >= MEDIA_BOA:
           print("Cada turma trouxe, em média, 10 kg ou mais.")
   ```

   A decisão da média deve ficar assim:

   ```python
   # Sem este if, com zero turmas, a conta seria uma divisão por zero e o programa parava.
   if turmas > 0:
       media = total_quilos / turmas
       print("Média por turma:", media, "kg")
       # Este if está dentro do bloco do if turmas > 0, porque só aí existe média.
       if media >= MEDIA_BOA:
           print("Cada turma trouxe, em média, 10 kg ou mais.")
   else:
       print("Não houve entregas, por isso não há média.")
   ```

   Leitura guiada: o `if` novo está na margem do `media = ...`, porque pertence ao mesmo bloco, o do `if turmas > 0:`. O seu `print` está oito espaços para dentro, porque está dentro de dois blocos. Com 0 turmas, o bloco de fora é saltado inteiro, também o `if` de dentro, e o programa passa ao `else`. Com turmas, calcula a média, escreve-a, e só então pergunta se ela chega aos 10. O `else` continua alinhado com o `if turmas > 0:`, e é dele.

3. Prepara os casos de teste. A fronteira está numa média de 10 kg. Com 4 turmas, a média chega aos 10 com 40 quilos, e os casos são 39, 40 e 41. Junta-lhes o caso sem turmas, 0 e 0, em que a mensagem não pode aparecer. No caderno, escreve primeiro se esperas a mensagem da média boa em cada caso. Depois confere com esta tabela:

   | Turmas | Quilos | Média | A mensagem da média boa aparece? |
   | ---: | ---: | --- | --- |
   | 4 | 39 | `9.75` | não |
   | 4 | 40 | `10.0` | sim |
   | 4 | 41 | `10.25` | sim |
   | 0 | 0 | não há média | não |

   Guarda e corre os quatro casos. Com 4 e 40, o ecrã fica assim:

   ```text
   Quantas turmas entregaram alimentos? 4
   Quantos quilos se recolheram ao todo? 40
   Turmas que entregaram: 4
   Total: 40 kg
   Média por turma: 10.0 kg
   Cada turma trouxe, em média, 10 kg ou mais.
   Quilos que faltam para a meta: 60
   Fim do balanço.
   ```

   O que deves ver nos outros: o que a tabela diz. O 40 já mostra a mensagem, porque `10.0 >= 10` dá `True`. Se a mensagem aparecer com 0 e 0, ou se o programa parar com um erro, confirma as margens com a decisão do passo 2.

### Paragem 5

O `balanco.py` diz se a média por turma foi boa, e só pergunta quando há média. Confere o teu com este:

```python
# balanco.py: o balanço da campanha de recolha de alimentos da escola.
# Lê quantas turmas entregaram e o total de quilos, e mostra o resultado da campanha.
META_QUILOS = 100
MEDIA_BOA = 10

turmas = int(input("Quantas turmas entregaram alimentos? "))
total_quilos = int(input("Quantos quilos se recolheram ao todo? "))
print("Turmas que entregaram:", turmas)
print("Total:", total_quilos, "kg")
# Sem este if, com zero turmas, a conta seria uma divisão por zero e o programa parava.
if turmas > 0:
    media = total_quilos / turmas
    print("Média por turma:", media, "kg")
    # Este if está dentro do bloco do if turmas > 0, porque só aí existe média.
    if media >= MEDIA_BOA:
        print("Cada turma trouxe, em média, 10 kg ou mais.")
else:
    print("Não houve entregas, por isso não há média.")
# A condição mais exigente vem primeiro: quem chega ao dobro também chegou à meta.
if total_quilos >= 2 * META_QUILOS:
    print("O dobro da meta! A escola está de parabéns.")
elif total_quilos >= META_QUILOS:
    print("Meta atingida!")
else:
    print("Quilos que faltam para a meta:", META_QUILOS - total_quilos)
print("Fim do balanço.")
```

Acrescenta à tua tabela do caderno:

| Pseudocódigo | Python |
| --- | --- |
| um `Se` dentro do bloco de outro `Se` | o mesmo, com mais quatro espaços por cada nível |

Pensa antes de continuares: porque é que o `if` da média boa não pode ficar encostado à margem, depois do `else` da média? A resposta: com 0 turmas, a linha `media = total_quilos / turmas` nunca se executa, e a variável `media` não existe. O programa parava com `NameError: name 'media' is not defined`. Dentro do bloco, a pergunta só se faz quando a média já existe.

## Fase 6: Validar os valores antes de os usar

Quem escreve os valores pode enganar-se. A escola tem 12 turmas. Por isso, o número de turmas tem de estar entre 0 e 12, incluindo os dois, e os quilos não podem ser negativos. Com -3 turmas ou 15 turmas, o balanço daria contas sem sentido, com ar de certas. A validação vem primeiro, como na algoritmia: se os valores forem impossíveis, o programa avisa e não faz mais contas.

Um valor está fora do intervalo de 0 a 12 quando está abaixo de 0 ou acima de 12. Escreve-se `turmas < 0 or turmas > TOTAL_TURMAS`, com o `or` do Python, o `ou` do pseudocódigo: basta falhar um dos lados para estar fora. Os quilos negativos juntam-se com mais um `or`. Tudo o que o programa já fazia passa para dentro do bloco do `else`, porque só faz sentido com valores válidos. É uma decisão dentro de outra, como na fase 5, mas agora com quase todo o programa lá dentro. Para saber mais, lê a secção "Validar um valor: dentro e fora de um intervalo" do [guia](03-selecao.md).

1. Em `balanco.py`, acrescenta a constante do número de turmas da escola, na linha acima de `META_QUILOS = 100`:

   ```python
   TOTAL_TURMAS = 12
   ```

   As regras da campanha ficam juntas, no início do ficheiro, em maiúsculas.

2. Indenta o que o programa já fazia. Seleciona com o rato todas as linhas desde o `print("Turmas que entregaram:", turmas)` até ao último `print` da cadeia do nível, o dos quilos que faltam. O `print("Fim do balanço.")` fica de fora. Carrega uma vez na tecla Tab. O que deves ver: todas as linhas selecionadas ganharam quatro espaços à esquerda. As que estavam na margem ficaram com quatro, as que tinham quatro ficaram com oito, e o `print` da média boa ficou com doze. Se ganharam espaços a mais, carrega em Shift+Tab, que tira quatro espaços a cada linha selecionada.

3. Escreve a validação e o `else`. Põe o cursor no fim da linha `total_quilos = int(input(...))`, a segunda leitura, e carrega em Enter. Na linha nova, que fica encostada à margem, escreve estas quatro linhas:

   ```python
   # A validação vem primeiro: com valores impossíveis, nenhuma conta faz sentido.
   if turmas < 0 or turmas > TOTAL_TURMAS or total_quilos < 0:
       print("Valores inválidos: confirma as turmas e os quilos.")
   else:
   ```

   O comentário, o `if` e o `else:` ficam encostados à margem, e o aviso quatro espaços para dentro. Se o VS Code puser espaços antes do `else:`, apaga-os. Depois do `else:`, não carregues em Enter: a linha seguinte já existe, e é o `print` das turmas, que indentaste no passo 2.

   O ficheiro inteiro deve ficar assim:

   ```python
   # balanco.py: o balanço da campanha de recolha de alimentos da escola.
   # Lê quantas turmas entregaram e o total de quilos, e mostra o resultado da campanha.
   TOTAL_TURMAS = 12
   META_QUILOS = 100
   MEDIA_BOA = 10

   turmas = int(input("Quantas turmas entregaram alimentos? "))
   total_quilos = int(input("Quantos quilos se recolheram ao todo? "))
   # A validação vem primeiro: com valores impossíveis, nenhuma conta faz sentido.
   if turmas < 0 or turmas > TOTAL_TURMAS or total_quilos < 0:
       print("Valores inválidos: confirma as turmas e os quilos.")
   else:
       print("Turmas que entregaram:", turmas)
       print("Total:", total_quilos, "kg")
       # Sem este if, com zero turmas, a conta seria uma divisão por zero e o programa parava.
       if turmas > 0:
           media = total_quilos / turmas
           print("Média por turma:", media, "kg")
           # Este if está dentro do bloco do if turmas > 0, porque só aí existe média.
           if media >= MEDIA_BOA:
               print("Cada turma trouxe, em média, 10 kg ou mais.")
       else:
           print("Não houve entregas, por isso não há média.")
       # A condição mais exigente vem primeiro: quem chega ao dobro também chegou à meta.
       if total_quilos >= 2 * META_QUILOS:
           print("O dobro da meta! A escola está de parabéns.")
       elif total_quilos >= META_QUILOS:
           print("Meta atingida!")
       else:
           print("Quilos que faltam para a meta:", META_QUILOS - total_quilos)
   print("Fim do balanço.")
   ```

   Leitura guiada: lê primeiro as linhas encostadas à margem. São as constantes, as duas leituras, a validação com o seu `else`, e o `print("Fim do balanço.")`. Esse é o esqueleto do programa. A condição da validação junta três comparações com `or`, e basta uma ser verdadeira para os valores serem inválidos. Com valores inválidos, executa-se o aviso, e o bloco do `else` é saltado inteiro, com as decisões que tem lá dentro. Com valores válidos, executa-se o bloco do `else`, quatro espaços para dentro. Lá dentro, cada decisão de antes ganhou mais quatro espaços. O último `print` está na margem, e aparece sempre.

4. Provoca um erro de propósito. Na linha a seguir ao `else:` da validação, o `print("Turmas que entregaram:", turmas)`, tira os quatro espaços, para ela ficar encostada à margem. Antes de correres, prevê que tipo de erro vai ser. Guarda e corre. O que deves ver, sem nenhuma pergunta antes:

   ```text
     File "C:\Users\aluno\Documents\fp-python\balanco.py", line 13
       print("Turmas que entregaram:", turmas)
       ^^^^^
   IndentationError: expected an indented block after 'else' statement on line 12
   ```

   Quer dizer "erro de indentação: esperava-se um bloco indentado depois do `else` da linha 12". Depois de uma linha que acaba em dois pontos, o Python exige pelo menos uma linha indentada. É um erro de sintaxe, e o programa nem arranca. Volta a pôr os quatro espaços, guarda e corre com 6 e 120, para confirmares que funciona.

5. Prepara os casos de teste da validação. As turmas têm duas fronteiras, no 0 e no 12, e os quilos têm uma, no 0. Para cada fronteira, testas o valor de baixo, o da fronteira e o de cima. No caderno, escreve primeiro, para cada caso, se esperas o aviso ou o balanço. Depois confere com esta tabela:

   | Turmas | Quilos | O que aparece antes de "Fim do balanço." |
   | ---: | ---: | --- |
   | -1 | 10 | `Valores inválidos: confirma as turmas e os quilos.` |
   | 0 | 0 | o balanço, com "Não houve entregas" e os 100 quilos que faltam |
   | 1 | 10 | o balanço, com a média de 10.0 kg, a média boa e os 90 quilos que faltam |
   | 11 | 110 | o balanço, com a média de 10.0 kg, a média boa e "Meta atingida!" |
   | 12 | 150 | o balanço, com a média de 12.5 kg, a média boa e "Meta atingida!" |
   | 13 | 10 | `Valores inválidos: confirma as turmas e os quilos.` |
   | 4 | -1 | `Valores inválidos: confirma as turmas e os quilos.` |
   | 4 | 0 | o balanço, com a média de 0.0 kg e os 100 quilos que faltam |
   | 4 | 1 | o balanço, com a média de 0.25 kg e os 99 quilos que faltam |

   Guarda e corre os nove casos. Com 13 turmas, o ecrã fica assim:

   ```text
   Quantas turmas entregaram alimentos? 13
   Quantos quilos se recolheram ao todo? 10
   Valores inválidos: confirma as turmas e os quilos.
   Fim do balanço.
   ```

   O que deves ver nos outros: o que a tabela diz. O 0, o 1, o 11 e o 12 são turmas válidas, e o -1 e o 13 não. Os quilos 0 e 1 são válidos, e o -1 não. Se o 12 der o aviso, confirma que a condição é `turmas > TOTAL_TURMAS`, sem o igual. Se o 13 der o balanço, confirma que as três comparações estão ligadas por `or`, e não por `and`.

### Paragem 6

O `balanco.py` está completo. Avisa dos valores impossíveis antes de fazer contas e mostra a média só quando há entregas. Diz também se a média foi boa, e o nível da campanha. Confirmaste as fronteiras de cada decisão.

Acrescenta à tua tabela do caderno:

| Pseudocódigo | Python |
| --- | --- |
| `turmas < 0 ou turmas > TOTAL_TURMAS` | `turmas < 0 or turmas > TOTAL_TURMAS` |

Pensa antes de continuares: porque é que o `print("Fim do balanço.")` ficou na margem, e não dentro do `else`? A resposta: na margem, está fora da validação, e aparece sempre, também depois do aviso dos valores inválidos. Dentro do `else`, só apareceria com valores válidos.

## Fase 7: Escolher entre valores certos com `match`

No posto de recolha, a pessoa escreve o número do alimento que trouxe, de 1 a 4, e o programa diz a caixa. Cada número tem a sua caixa, e qualquer outro número quer dizer um alimento que a campanha não recolhe. Com o que já sabes, escreve-se uma cadeia de `if` em que cada condição compara o mesmo valor com um número fixo. Para estes casos, o Python tem uma forma mais curta, o `match`. A linha `match tipo:` diz que valor se compara, e cada `case` traz um valor fixo, com o seu bloco. O `case _`, com o traço baixo, apanha qualquer outro valor, como o `else`. O `match` só existe a partir do Python 3.10. Para saber mais, lê a secção "Escolher entre valores certos com `match`" do [guia](03-selecao.md).

1. Começa pela versão com `if`. Cria o ficheiro `posto.py`, no painel Explorer, com o ícone New File..., e escreve nele este conteúdo, que é o ficheiro completo:

   ```python
   # posto.py: o posto de recolha da campanha diz em que caixa vai cada alimento.
   print("1 Arroz e massa")
   print("2 Enlatados")
   print("3 Leite")
   print("4 Azeite e óleo")
   tipo = int(input("Que alimento trouxeste? "))
   if tipo == 1:
       print("Vai para a caixa azul.")
   elif tipo == 2:
       print("Vai para a caixa verde.")
   elif tipo == 3:
       print("Vai para a caixa amarela.")
   elif tipo == 4:
       print("Vai para a caixa vermelha.")
   else:
       print("Esse alimento não se recolhe nesta campanha.")
   ```

   Leitura guiada: os quatro primeiros `print` mostram o menu, e o `input` lê a escolha, convertida em número. A cadeia compara o `tipo` com 1, depois com 2, com 3 e com 4, e executa o bloco da primeira comparação que der `True`. Se nenhuma der, o `else` escreve que o alimento não se recolhe. Repara que todas as condições têm a mesma forma, `tipo ==` e um número.

2. Antes de correres, prevê o que aparece com o 2 e com o 5. Guarda e corre:

   ```bash
   python posto.py
   ```

   Escreve 2. O que deves ver: o menu, a pergunta com o teu 2, e por baixo `Vai para a caixa verde.`. Corre outra vez, com a seta para cima, e escreve 5. O que deves ver: `Esse alimento não se recolhe nesta campanha.`. O 5 não é igual a nenhum dos quatro números, e por isso caiu no `else`.

3. Provoca um erro de propósito. Na linha `if tipo == 1:`, apaga um dos dois sinais de igual, para ficar `if tipo = 1:`. Antes de correres, prevê que tipo de erro vai ser. Guarda e corre. O que deves ver:

   ```text
     File "C:\Users\aluno\Documents\fp-python\posto.py", line 7
       if tipo = 1:
          ^^^^^^^^
   SyntaxError: invalid syntax. Maybe you meant '==' or ':=' instead of '='?
   ```

   Quer dizer "escrita inválida. Talvez quisesses `==` ou `:=` em vez de `=`". Um só `=` guarda um valor, e numa condição queres perguntar, com `==`. O `:=` é outra coisa, que não se usa nas aulas. Volta a pôr o `==`, guarda e corre com o 1, para confirmares a caixa azul.

4. Agora a versão com `match`. Em `posto.py`, substitui a cadeia inteira, desde o `if tipo == 1:` até ao último `print`, por estas linhas:

   ```python
   # Cada case compara o tipo com um valor fixo; o case _ apanha todos os outros.
   match tipo:
       case 1:
           print("Vai para a caixa azul.")
       case 2:
           print("Vai para a caixa verde.")
       case 3:
           print("Vai para a caixa amarela.")
       case 4:
           print("Vai para a caixa vermelha.")
       case _:
           print("Esse alimento não se recolhe nesta campanha.")
   ```

   Leitura guiada: a linha `match tipo:` diz que o valor a comparar é o `tipo`. Os `case` ficam quatro espaços para dentro do `match`, e cada `print` mais quatro, dentro do seu `case`. O Python compara o `tipo` com o valor de cada `case`, de cima para baixo, e executa o bloco do primeiro que for igual. O `case _` fica no fim e apanha o que sobra. Cada linha de `match` e de `case` acaba em dois pontos. O `tipo ==` deixou de se repetir.

5. Prepara os casos de teste. Cada ramo é um caso: o 1, o 2, o 3 e o 4. Junta-lhes dois valores que não existem, o 5 e o 0. No caderno, escreve primeiro a caixa que esperas em cada um. Depois confere com esta tabela:

   | Alimento | O que aparece |
   | ---: | --- |
   | 1 | `Vai para a caixa azul.` |
   | 2 | `Vai para a caixa verde.` |
   | 3 | `Vai para a caixa amarela.` |
   | 4 | `Vai para a caixa vermelha.` |
   | 5 | `Esse alimento não se recolhe nesta campanha.` |
   | 0 | `Esse alimento não se recolhe nesta campanha.` |

   Guarda e corre os seis casos. O que deves ver: a tabela, linha a linha, igual ao que a versão com `if` dava. As duas versões fazem o mesmo, para qualquer número. Se o Python recusar o programa com `SyntaxError: invalid syntax` na linha do `match`, a tua versão é anterior à 3.10. Nesse caso, volta à versão com `if` do passo 1 e avisa o professor.

6. Provoca um erro de propósito. Move o `case _:` e o seu `print` para o princípio, logo a seguir à linha `match tipo:`. Antes de correres, prevê o que acontece. Guarda e corre. O que deves ver:

   ```text
     File "C:\Users\aluno\Documents\fp-python\posto.py", line 9
       case _:
            ^
   SyntaxError: wildcard makes remaining patterns unreachable
   ```

   Quer dizer "o caso que apanha tudo torna inalcançáveis os casos seguintes". No princípio, o `case _` apanhava todos os valores, e os outros `case` nunca seriam usados. O Python percebe-o e recusa o programa. Volta a pôr o `case _` no fim, guarda e corre com o 3.

### Paragem 7

O `posto.py` diz em que caixa vai cada alimento, com `match`, e dá os mesmos resultados que a versão com `if`. Confere o teu com este:

```python
# posto.py: o posto de recolha da campanha diz em que caixa vai cada alimento.
print("1 Arroz e massa")
print("2 Enlatados")
print("3 Leite")
print("4 Azeite e óleo")
tipo = int(input("Que alimento trouxeste? "))
# Cada case compara o tipo com um valor fixo; o case _ apanha todos os outros.
match tipo:
    case 1:
        print("Vai para a caixa azul.")
    case 2:
        print("Vai para a caixa verde.")
    case 3:
        print("Vai para a caixa amarela.")
    case 4:
        print("Vai para a caixa vermelha.")
    case _:
        print("Esse alimento não se recolhe nesta campanha.")
```

Acrescenta à tua tabela do caderno:

| Pseudocódigo | Python |
| --- | --- |
| uma cadeia de `Se` que compara sempre a mesma variável com `==` | `match` e um `case` por valor, com `case _` no fim |

Pensa antes de continuares: porque é que a cadeia do nível do `balanco.py` fica com `if`, e não passa a `match`? A resposta: nas aulas, o `match` usa-se só para comparar um valor com valores fixos, como 1, 2 ou 3. A cadeia do nível pergunta se o total é maior ou igual a 100 ou a 200, e isso escreve-se com `if`.

## Problemas frequentes

### `SyntaxError: expected ':'`

Faltam os dois pontos no fim da linha que a mensagem mostra. As linhas do `if`, do `elif`, do `else`, do `match` e do `case` acabam sempre em dois pontos. O `^` aponta para o sítio onde faltam.

### `IndentationError: expected an indented block after ...`

A linha a seguir a uns dois pontos ficou encostada à margem. A mensagem diz depois de que linha, como `after 'else' statement on line 12`. Põe quatro espaços antes dela, com a tecla Tab.

### `SyntaxError: invalid syntax. Maybe you meant '==' ...`

Numa condição, escreveste um só `=`. Para perguntar se dois valores são iguais, usa `==`.

### `SyntaxError: invalid syntax` numa linha com `e`, `ou` ou `Senão`

Ficou uma palavra do pseudocódigo no programa. Em Python, escreve-se `and`, `or`, `not`, `elif` e `else`.

### `ZeroDivisionError: division by zero`

A média calculou-se com 0 turmas. A divisão tem de estar dentro do bloco do `if turmas > 0:`, quatro espaços para dentro, como na fase 3.

### `ValueError: invalid literal for int() with base 10`

Escreveste letras, ou um número com casas decimais, numa pergunta que espera um número inteiro. O `int` não o consegue converter. Corre outra vez e escreve um número inteiro, como `12`.

### `SyntaxError: invalid syntax` na linha do `match`

O teu Python é anterior à versão 3.10, que não conhece o `match`. Confirma com `python --version`. Usa a versão com `if` do passo 1 da fase 7, e avisa o professor.

### `NameError: name 'media' is not defined`

O `if` da média boa ficou fora do bloco do `if turmas > 0:`, e correu com 0 turmas, quando a média não existe. Põe-no outra vez dentro do bloco, com quatro espaços a mais do que o `if turmas > 0:`, como na fase 5.

### Aparecem mensagens a mais, ou falta uma mensagem

Uma linha ficou dentro de um bloco a que não pertence, ou fora de um bloco a que pertencia. O programa corre sem erro, mas faz outra coisa. Compara a indentação de cada linha com a do ficheiro da última paragem. Cada nível são quatro espaços.

### O resultado não muda depois de corrigires o código

O ficheiro não foi guardado. Guarda com Ctrl+S, ou Cmd+S no macOS, e corre outra vez.

## Desafios

1. Turmas sem quilos e quilos sem turmas. Com 0 turmas e 30 quilos, o `balanco.py` diz que não houve entregas e que faltam 70 quilos. Os dois valores, cada um sozinho, são válidos, mas juntos não fazem sentido: sem turmas, não pode haver quilos. Muda o programa para que, neste caso, escreva "Valores inválidos: sem turmas, não pode haver quilos." e não faça o balanço. Testa com 0 e 30, com 0 e 0, e com 3 e 30. Pista: a condição deste caso junta duas comparações, sobre as turmas e sobre os quilos, e as duas têm de ser verdadeiras.

2. A média com uma casa decimal. Com 12 turmas e 200 quilos, a média aparece como `16.666666666666668`. Muda o programa para a média aparecer só com uma casa decimal, como `16.7`. Testa também com 7 turmas e 100 quilos. Pista: a função predefinida `round`, do guia 02, arredonda um número e deixa escolher quantas casas decimais ficam.

3. As palavras no posto. No `posto.py`, a pessoa passa a escrever o nome do alimento, em minúsculas, em vez do número. O menu mostra uma palavra por caixa: `arroz`, `enlatados`, `leite` e `azeite`. Muda o menu e o `match` para isso, com as mesmas caixas. Escolhe tu os casos de teste, com o resultado esperado de cada um escrito antes de correr, e inclui uma palavra com maiúscula, como `Leite`. Pista: a resposta passa a ser um texto, e os valores dos `case` também.

## Antes de terminares

- [ ] O `balanco.py` dá os resultados das tabelas das fases 2 a 6, e escreveste no caderno os resultados esperados antes de correr cada caso.
- [ ] O `balanco.py` nunca para com `ZeroDivisionError`, mesmo com 0 turmas.
- [ ] O `posto.py` corre com `match` e dá os mesmos resultados que a versão com `if`, nos seis casos.
- [ ] A tua tabela do caderno tem as linhas das sete paragens, do pseudocódigo para o Python.
- [ ] Sabes dizer de que tipo foi cada erro que provocaste: de sintaxe, de execução ou de lógica.
- [ ] Consegues explicar, por palavras tuas, porque é que os casos de teste de uma decisão se escolhem nas fronteiras. E porque é que, numa cadeia, a ordem das condições muda o resultado.

![Rodapé](../imagens/rodape.png)
