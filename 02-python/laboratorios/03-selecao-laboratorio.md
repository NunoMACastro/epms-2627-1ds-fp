![Cabeçalho](../../imagens/cabecalho.png)

# Laboratório: Seleção

## O que vais construir

Vais construir dois programas para a campanha de recolha de alimentos da escola. O `balanco.py` pergunta quantas turmas entregaram alimentos e quantos quilos se recolheram, e decide o que mostrar. O `posto.py` diz em que caixa vai cada alimento.

No fim, com 6 turmas e 120 quilos, o `balanco.py` mostra:

```text
Quantas turmas entregaram alimentos? 6
Quantos quilos se recolheram ao todo? 120
Turmas que entregaram: 6
Total: 120 kg
Média por turma: 20.0 kg
Cada turma trouxe, em média, 10 kg ou mais.
Meta atingida!
Fim do balanço.
```

1. [Fase 1: As comparações dão `True` ou `False`](#fase-1-as-comparações-dão-true-ou-false)
2. [Fase 2: Decidir com `if`](#fase-2-decidir-com-if)
3. [Fase 3: Os dois pontos e a indentação marcam o bloco](#fase-3-os-dois-pontos-e-a-indentação-marcam-o-bloco)
4. [Fase 4: Dois caminhos, com `if` e `else`](#fase-4-dois-caminhos-com-if-e-else)
5. [Fase 5: Mais de dois caminhos, com a cadeia `elif`](#fase-5-mais-de-dois-caminhos-com-a-cadeia-elif)
6. [Fase 6: A ordem das condições conta](#fase-6-a-ordem-das-condições-conta)
7. [Fase 7: Uma decisão dentro de outra](#fase-7-uma-decisão-dentro-de-outra)
8. [Fase 8: Validar os valores antes de os usar](#fase-8-validar-os-valores-antes-de-os-usar)
9. [Fase 9: Escolher entre valores certos com `match`](#fase-9-escolher-entre-valores-certos-com-match)

## O que precisas

- A pasta `fp-python`, aberta no VS Code, e um terminal, que se abre no menu Terminal, com a opção New Terminal.
- O comando que corre o Python no teu computador, `python`, `py` ou `python3`. Onde o texto diz `python`, usa o teu.
- O Python 3.10 ou mais recente, para a fase 9. Confirma com `python --version`. Deve aparecer uma linha como `Python 3.13.2`, e o número a seguir ao 3 tem de ser 10 ou mais.

## Fase 1: As comparações dão `True` ou `False`

Nesta fase experimentas comparações na consola, sem criar ficheiros. Lembra-te de que uma comparação dá `True` ou `False`, com maiúscula. Rever: [As comparações dão `True` ou `False`](../03-selecao.md#as-comparações-dão-true-ou-false).

1. Entra na consola: no terminal, escreve `python`, com o teu comando, e carrega em Enter. O que deves ver: `>>>`, à espera de uma linha de Python.

2. Escreve só o que está a seguir a cada `>>>`.

   ```text
   >>> 120 >= 100
   True
   >>> 99 >= 100
   False
   >>> type(99 >= 100)
   <class 'bool'>
   ```

   A consola respondeu `True` ou `False` a cada comparação, e o `type` mostra que a resposta é um `bool`.

3. Agora com uma variável, como num programa:

   ```text
   >>> turmas = 6
   >>> turmas > 0
   True
   >>> turmas = 0
   >>> turmas > 0
   False
   ```

   As linhas com um só `=` não mostram resposta, porque guardam um valor. A mesma pergunta deu `True` e depois `False`, porque a variável mudou entre as duas.

4. Sai da consola com `exit()`.

### Paragem 1

Sabes prever se uma comparação dá `True` ou `False`, e a consola confirma-o.

Pensa antes de continuares: qual é a diferença entre `turmas = 0` e `turmas == 0`? A resposta: a primeira guarda 0 na variável. A segunda pergunta se a variável vale 0, responde `True` ou `False`, e não muda nada.

## Fase 2: Decidir com `if`

O programa passa a escrever "Meta atingida!" só quando os quilos chegam aos 100. O `Se` do pseudocódigo passa a `if`, e o bloco fica quatro espaços para dentro. Rever: [Decidir com `if`](../03-selecao.md#decidir-com-if).

1. O balanço começa por ler os dois valores e mostrá-los. No painel Explorer, passa o rato por cima de `FP-PYTHON` e carrega no ícone `New File...`. Escreve `balanco.py`, carrega em Enter e escreve no ficheiro esta primeira versão:

   ```python
   # balanco.py: o balanço da campanha de recolha de alimentos da escola.

   turmas = int(input("Quantas turmas entregaram alimentos? "))
   total_quilos = int(input("Quantos quilos se recolheram ao todo? "))
   print("Turmas que entregaram:", turmas)
   print("Total:", total_quilos, "kg")
   print("Fim do balanço.")
   ```

2. Guarda e corre o programa:

   ```bash
   python balanco.py
   ```

   Clica no terminal e responde 6 e 120. O que deves ver: as duas perguntas, `Turmas que entregaram: 6`, `Total: 120 kg` e `Fim do balanço.`. Se aparecer outra coisa, vê [Se alguma coisa falhar](#se-alguma-coisa-falhar).

3. A meta é uma regra da campanha, e fica numa constante. Põe o cursor no fim da linha 1 e carrega em Enter. Na linha nova, escreve:

   ```python
   META_QUILOS = 100
   ```

4. Antes da linha `print("Fim do balanço.")`, acrescenta a decisão:

   ```python
   # Esta mensagem só aparece quando a condição é verdadeira.
   if total_quilos >= META_QUILOS:
       print("Meta atingida!")
   ```

5. Antes de correres, prevê o que aparece com 4 turmas e 99 quilos. Guarda e corre com 6 e 120, e depois com 4 e 99. Para repetires o comando, carrega na seta para cima do teclado e em Enter.

   O que deves ver: com 120, `Meta atingida!` antes da última linha. Com 99, a mensagem não aparece, porque `99 >= 100` dá `False` e o bloco é saltado. `Fim do balanço.` aparece nos dois casos, porque está na margem.

6. Testa a fronteira. A resposta muda entre 99 e 100 quilos, e a meta conta a partir dos 100, incluindo os 100. Corre com 4 turmas e cada valor desta tabela:

   | Quilos | "Meta atingida!" aparece? |
   | ---: | --- |
   | 99 | não |
   | 100 | sim |
   | 101 | sim |

   O que deves ver: o 100 já mostra a mensagem, porque `100 >= 100` dá `True`.

7. Provoca um erro, para o reconheceres. Na linha do `if`, apaga o `>`, para ficar `if total_quilos = META_QUILOS:`. Guarda e corre. O que deves ver, sem nenhuma pergunta antes:

   ```text
     File "C:\Users\aluno\Documents\fp-python\balanco.py", line 9
       if total_quilos = META_QUILOS:
          ^^^^^^^^^^^^^^^^^^^^^^^^^^
   SyntaxError: invalid syntax. Maybe you meant '==' or ':=' instead of '='?
   ```

   Um só `=` guarda um valor, e numa condição queres perguntar. Volta a pôr o `>=`, guarda e confirma com 6 e 120.

### Paragem 2

O `balanco.py` diz "Meta atingida!" só a partir dos 100 quilos.

Pensa antes de continuares: porque é que o caso 100 é mais importante do que o 150, para testar este `if`? A resposta: com 150, o `>=` e o `>` dão os dois `True`. Com 100, só o `>=` dá `True`.

## Fase 3: Os dois pontos e a indentação marcam o bloco

Experimentas o que acontece quando uma linha muda de margem e quando faltam os dois pontos. Os dois pontos abrem o bloco, e a indentação diz o que está lá dentro. Rever: [Os dois pontos e a indentação marcam o bloco](../03-selecao.md#os-dois-pontos-e-a-indentação-marcam-o-bloco).

1. Na última linha, põe quatro espaços antes do `print("Fim do balanço.")`, para ela entrar no bloco do `if`. Antes de correres, prevê o que muda com 4 turmas e 99 quilos. Guarda e corre.

   O que deves ver: a linha `Fim do balanço.` desapareceu. Passou a pertencer ao bloco, e com 99 o bloco é saltado. Não há mensagem nenhuma: é um erro de lógica, e só um caso em que a condição é falsa o mostra. Tira os quatro espaços e guarda.

2. Apaga os dois pontos no fim da linha do `if`. Guarda e corre. O que deves ver, antes de qualquer pergunta:

   ```text
     File "C:\Users\aluno\Documents\fp-python\balanco.py", line 9
       if total_quilos >= META_QUILOS
                                     ^
   SyntaxError: expected ':'
   ```

   O Python recusa o programa antes de executar qualquer linha, e o `^` aponta para o sítio onde faltam os dois pontos. Volta a pô-los, guarda e confirma com 6 e 120.

### Paragem 3

O programa está como no fim da fase 2, e já reconheces os dois erros.

Pensa antes de continuares: o que diz ao Python onde acaba o bloco? A resposta: a primeira linha que volta à margem do `if`. Nenhuma palavra marca o fim.

## Fase 4: Dois caminhos, com `if` e `else`

O programa passa a mostrar a média por turma, só quando houve entregas, e escreve outra mensagem nos outros casos. O `Senão` passa a `else`, com os dois pontos e sem condição. Rever: [Dois caminhos, com `if` e `else`](../03-selecao.md#dois-caminhos-com-if-e-else) e [Uma conta que só se faz num dos ramos](../03-selecao.md#uma-conta-que-só-se-faz-num-dos-ramos).

1. Vê primeiro o problema. A seguir à linha `print("Total:", total_quilos, "kg")`, acrescenta:

   ```python
   media = total_quilos / turmas
   print("Média por turma:", media, "kg")
   ```

   Guarda e corre com 6 e 120. O que deves ver: `Média por turma: 20.0 kg`, a seguir ao total.

2. Corre agora com 0 turmas e 0 quilos. O que deves ver no fim:

   ```text
   Traceback (most recent call last):
     File "C:\Users\aluno\Documents\fp-python\balanco.py", line 8, in <module>
       media = total_quilos / turmas
               ~~~~~~~~~~~~~^~~~~~~~
   ZeroDivisionError: division by zero
   ```

   O programa correu até à divisão e parou a meio: é um erro de execução.

3. Substitui as duas linhas que acrescentaste no passo 1 por estas:

   ```python
   # Sem este if, com zero turmas, a conta seria uma divisão por zero e o programa parava.
   if turmas > 0:
       media = total_quilos / turmas
       print("Média por turma:", media, "kg")
   else:
       print("Não houve entregas, por isso não há média.")
   ```

   Depois do `print`, o VS Code deixa o cursor quatro espaços para dentro. Se o `else:` não voltar sozinho à margem, apaga esses espaços.

4. Guarda e corre com cada linha desta tabela:

   | Turmas | Quilos | A linha da média |
   | ---: | ---: | --- |
   | 6 | 120 | `Média por turma: 20.0 kg` |
   | 1 | 15 | `Média por turma: 15.0 kg` |
   | 0 | 0 | `Não houve entregas, por isso não há média.` |

   O que deves ver: em cada caso, a linha da tabela e, no fim, `Fim do balanço.`. Com 0 turmas, o programa já não para.

### Paragem 4

O `balanco.py` mostra a média só quando houve entregas.

Pensa antes de continuares: há algum caso em que aparecem a média e o aviso de não haver entregas? A resposta: não. Com `if` e `else`, executa-se sempre um dos dois blocos, e só um.

## Fase 5: Mais de dois caminhos, com a cadeia `elif`

A mensagem da meta passa a ter três casos, conforme os quilos. O `Senão se` passa a `elif`, e só se executa o bloco da primeira condição verdadeira. Rever: [Mais de dois caminhos, com a cadeia `elif`](../03-selecao.md#mais-de-dois-caminhos-com-a-cadeia-elif).

1. Com 200 quilos ou mais, o programa dá os parabéns. Com 100 ou mais, diz que a meta foi atingida. Abaixo dos 100, diz quantos faltam. Substitui as três linhas da meta, desde o comentário `# Esta mensagem só aparece quando a condição é verdadeira.` até ao `print("Meta atingida!")`, por estas:

   ```python
   # A condição mais exigente vem primeiro: quem chega ao dobro também chegou à meta.
   if total_quilos >= 2 * META_QUILOS:
       print("O dobro da meta! A escola está de parabéns.")
   elif total_quilos >= META_QUILOS:
       print("Meta atingida!")
   else:
       print("Quilos que faltam para a meta:", META_QUILOS - total_quilos)
   ```

2. Esta cadeia tem duas fronteiras, nos 100 e nos 200 quilos. Guarda e corre com 4 turmas e cada valor desta tabela:

   | Quilos | A mensagem do nível |
   | ---: | --- |
   | 99 | `Quilos que faltam para a meta: 1` |
   | 100 | `Meta atingida!` |
   | 101 | `Meta atingida!` |
   | 199 | `Meta atingida!` |
   | 200 | `O dobro da meta! A escola está de parabéns.` |
   | 201 | `O dobro da meta! A escola está de parabéns.` |

   O que deves ver: em cada caso, uma só mensagem do nível, a da tabela. Se aparecer outra coisa, vê [Se alguma coisa falhar](#se-alguma-coisa-falhar).

### Paragem 5

O `balanco.py` diz o nível da campanha nos três casos.

O ficheiro `balanco.py` completo, como deve estar agora:

```python
# balanco.py: o balanço da campanha de recolha de alimentos da escola.
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

O programa tem duas decisões separadas, a da média e a do nível. A cadeia do nível escolhe sempre um só dos seus três ramos.

Pensa antes de continuares: porque é que a condição do `elif` não precisa de dizer `total_quilos < 2 * META_QUILOS`? A resposta: quando o programa chega ao `elif`, a primeira condição já deu falso, e o total é, com certeza, menor do que 200.

## Fase 6: A ordem das condições conta

Trocas de propósito a ordem da cadeia, para veres o que acontece. A primeira condição verdadeira ganha, e por isso a que apanha menos valores vem primeiro. Rever: [A ordem das condições conta](../03-selecao.md#a-ordem-das-condições-conta).

1. Troca as duas primeiras condições da cadeia e as suas mensagens, para ficarem assim:

   ```python
   if total_quilos >= META_QUILOS:
       print("Meta atingida!")
   elif total_quilos >= 2 * META_QUILOS:
       print("O dobro da meta! A escola está de parabéns.")
   ```

2. Antes de correres, prevê o que aparece com 4 turmas e 200 quilos. Guarda e corre.

   O que deves ver: `Meta atingida!`, e não os parabéns. Com 200, `200 >= 100` é verdadeira e ganha, e o `elif` nunca dá `True`. É um erro de lógica.

3. Volta a pôr a ordem da fase 5, guarda e corre com 200, para confirmares os parabéns.

### Paragem 6

O programa está como na paragem 5.

Pensa antes de continuares: que casos de teste mostram este erro? A resposta: só os de 200 ou mais. Com menos, as duas ordens dão o mesmo.

## Fase 7: Uma decisão dentro de outra

O programa passa a dizer se cada turma trouxe, em média, 10 quilos ou mais. A média só existe quando houve entregas, e por isso a decisão nova vai para dentro do bloco do `if turmas > 0:`. Rever: [Uma decisão dentro de outra](../03-selecao.md#uma-decisão-dentro-de-outra).

1. Põe o cursor no fim da linha `META_QUILOS = 100` e carrega em Enter. Na linha nova, escreve a constante:

   ```python
   MEDIA_BOA = 10
   ```

2. No bloco do `if turmas > 0:`, a seguir ao `print` da média, acrescenta estas três linhas. O comentário e o `if` levam quatro espaços, e o `print` novo leva oito:

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

3. A fronteira está numa média de 10 kg. Guarda e corre um caso por linha:

   | Turmas | Quilos | Média | A mensagem da média boa aparece? |
   | ---: | ---: | --- | --- |
   | 4 | 39 | `9.75` | não |
   | 4 | 40 | `10.0` | sim |
   | 4 | 41 | `10.25` | sim |
   | 0 | 0 | não há média | não |

   O que deves ver: a coluna da direita da tabela. Com 0 e 0, o bloco de fora é saltado inteiro, também o `if` de dentro.

### Paragem 7

O `balanco.py` diz se a média foi boa, e só decide quando há média.

Pensa antes de continuares: porque é que o `if` da média boa não pode ficar na margem, depois do `else` da média? A resposta: com 0 turmas, a variável `media` não existe, e o programa parava com `NameError: name 'media' is not defined`.

## Fase 8: Validar os valores antes de os usar

O programa passa a recusar valores impossíveis antes de fazer contas. O `ou` do pseudocódigo passa a `or`, e basta uma das comparações dar `True` para o valor ser recusado. Rever: [Juntar condições com `and`, `or` e `not`](../03-selecao.md#juntar-condições-com-and-or-e-not) e [Validar os valores antes de os usar](../03-selecao.md#validar-os-valores-antes-de-os-usar).

1. A escola tem 12 turmas, e os quilos não podem ser negativos. Põe o cursor no fim da linha 1 e carrega em Enter. Na linha nova, escreve a constante:

   ```python
   TOTAL_TURMAS = 12
   ```

2. Tudo o que o programa já fazia passa a depender de os valores serem válidos. Seleciona com o rato as linhas desde o `print("Turmas que entregaram:", turmas)` até ao último `print` da cadeia do nível, o dos quilos que faltam. O `print("Fim do balanço.")` fica de fora. Carrega uma vez na tecla Tab.

   O que deves ver: todas as linhas selecionadas ganharam quatro espaços. O VS Code pode sublinhá-las a vermelho até acabares o passo seguinte. Se ganharam espaços a mais, carrega em Shift+Tab.

3. Põe o cursor no fim da linha `total_quilos = int(input(...))` e carrega em Enter. Na linha nova, encostada à margem, escreve estas linhas. Depois do `else:`, não carregues em Enter, porque a linha seguinte já existe.

   ```python
   # A validação vem primeiro: com valores impossíveis, nenhuma conta faz sentido.
   if turmas < 0 or turmas > TOTAL_TURMAS or total_quilos < 0:
       print("Valores inválidos: confirma as turmas e os quilos.")
   else:
   ```

   O comentário, o `if` e o `else:` ficam na margem, e o aviso quatro espaços para dentro. Se o VS Code puser espaços antes do `else:`, apaga-os.

4. Provoca um erro. Na linha 12, o `print("Turmas que entregaram:", turmas)`, tira os quatro espaços. Guarda e corre. O programa nem chega às perguntas, e o que deves ver é:

   ```text
     File "C:\Users\aluno\Documents\fp-python\balanco.py", line 12
       print("Turmas que entregaram:", turmas)
       ^^^^^
   IndentationError: expected an indented block after 'else' statement on line 11
   ```

   Depois de uma linha que acaba em dois pontos, o Python exige pelo menos uma linha indentada. Volta a pôr os quatro espaços e guarda.

5. As turmas têm fronteiras no 0 e no 12, e os quilos no 0. Antes de correres, prevê o que aparece com 13 turmas e 10 quilos. Guarda e corre cada caso da tabela:

   | Turmas | Quilos | O que aparece antes de "Fim do balanço." |
   | ---: | ---: | --- |
   | -1 | 10 | o aviso dos valores inválidos |
   | 0 | 0 | o balanço, com "Não houve entregas" e os 100 quilos que faltam |
   | 1 | 10 | o balanço, com a média de 10.0 kg, a média boa e os 90 quilos que faltam |
   | 11 | 110 | o balanço, com a média de 10.0 kg, a média boa e "Meta atingida!" |
   | 12 | 150 | o balanço, com a média de 12.5 kg, a média boa e "Meta atingida!" |
   | 13 | 10 | o aviso dos valores inválidos |
   | 4 | -1 | o aviso dos valores inválidos |
   | 4 | 0 | o balanço, com a média de 0.0 kg e os 100 quilos que faltam |
   | 4 | 1 | o balanço, com a média de 0.25 kg e os 99 quilos que faltam |

   O que deves ver: o que a tabela diz. Se o 12 der o aviso, confirma que a condição é `turmas > TOTAL_TURMAS`, sem o igual.

### Paragem 8

O `balanco.py` está completo.

O ficheiro `balanco.py` completo, como deve estar agora:

```python
# balanco.py: o balanço da campanha de recolha de alimentos da escola.
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

As linhas na margem são o esqueleto: as constantes, as leituras, a validação com o seu `else`, e o último `print`. Com valores inválidos, o bloco do `else` é saltado inteiro, com as decisões que tem lá dentro.

Pensa antes de continuares: porque é que o `print("Fim do balanço.")` ficou na margem? A resposta: na margem, aparece sempre, também depois do aviso. Dentro do `else`, só apareceria com valores válidos.

## Fase 9: Escolher entre valores certos com `match`

Constróis o programa do posto de recolha, primeiro com uma cadeia de `if` e depois com `match`. O `match` compara um valor com vários valores fixos, e o `case _` apanha os outros. Rever: [Escolher entre valores certos com `match`](../03-selecao.md#escolher-entre-valores-certos-com-match).

1. Cria o ficheiro `posto.py`, com o ícone `New File...`, e escreve nele esta primeira versão:

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

2. Guarda e corre com o 2, e depois com o 5:

   ```bash
   python posto.py
   ```

   O que deves ver: com o 2, `Vai para a caixa verde.`. Com o 5, `Esse alimento não se recolhe nesta campanha.`, porque o 5 não é igual a nenhum dos quatro números.

3. Todas as condições têm a mesma forma, `tipo ==` e um número. Substitui a cadeia inteira, desde o `if tipo == 1:` até ao último `print`, por estas linhas:

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

4. Guarda e experimenta cada alimento da tabela:

   | Alimento | O que aparece |
   | ---: | --- |
   | 1 | `Vai para a caixa azul.` |
   | 2 | `Vai para a caixa verde.` |
   | 3 | `Vai para a caixa amarela.` |
   | 4 | `Vai para a caixa vermelha.` |
   | 5 | `Esse alimento não se recolhe nesta campanha.` |
   | 0 | `Esse alimento não se recolhe nesta campanha.` |

   O que deves ver: o mesmo que a versão com `if` dava. Se o Python recusar a linha do `match`, vê [Se alguma coisa falhar](#se-alguma-coisa-falhar).

5. Provoca um erro. Move o `case _:` e o seu `print` para logo a seguir à linha `match tipo:`. Antes de correres, prevê o que acontece. Guarda e corre. O que deves ver:

   ```text
     File "C:\Users\aluno\Documents\fp-python\posto.py", line 9
       case _:
            ^
   SyntaxError: wildcard makes remaining patterns unreachable
   ```

   Quer dizer que o caso que apanha tudo torna inalcançáveis os seguintes. Volta a pôr o `case _` no fim, guarda e corre com o 3.

### Paragem 9

O `posto.py` diz em que caixa vai cada alimento, com `match`.

Pensa antes de continuares: porque é que a cadeia do nível do `balanco.py` fica com `if`? A resposta: a cadeia pergunta se o total chega a 100 ou a 200. O `match` usa-se só para comparar um valor com valores fixos.

## Se alguma coisa falhar

1. Guardaste o ficheiro? O Python corre o que está no disco, e não o que vês no ecrã.
2. Estás na pasta certa? No terminal, o texto antes do cursor tem de ter `fp-python` no fim, antes do `>` ou do `%`.
3. Estás na consola do Python sem quereres? Se a linha começa por `>>>`, escreve `exit()` e carrega em Enter.
4. O programa ficou parado? Está à espera da tua resposta. Clica no terminal, escreve-a e carrega em Enter.

### `SyntaxError: expected ':'`

Faltam os dois pontos no fim da linha que a mensagem mostra.

### `IndentationError: expected an indented block after ...`

A linha a seguir a uns dois pontos ficou encostada à margem. Põe quatro espaços antes dela, com a tecla Tab.

### `SyntaxError: invalid syntax. Maybe you meant '==' ...`

Numa condição, escreveste um só `=`. Para perguntar se dois valores são iguais, usa `==`.

### `SyntaxError: invalid syntax` na linha do `else` ou do `elif`

A linha ficou com espaços antes. Fica na mesma margem do seu `if`.

### `SyntaxError: invalid syntax` na linha do `match`

O teu Python é anterior à versão 3.10, que não conhece o `match`. Confirma com `python --version`, fica com a versão com `if` da fase 9 e avisa o professor.

### `NameError: name 'media' is not defined`

O `if` da média boa ficou fora do bloco do `if turmas > 0:`. Compara as margens com as da paragem 8.

### `ValueError: invalid literal for int() with base 10`

Escreveste letras, ou um número com casas decimais, numa pergunta que espera um número inteiro.

### Aparecem mensagens a mais, ou falta uma mensagem

Uma linha ficou dentro de um bloco a que não pertence, ou fora de um a que pertencia. Compara a indentação de cada linha com a do ficheiro da última paragem.

## Desafios

Faz cada desafio num ficheiro novo, como `desafio_1.py`, com o código do programa copiado para lá. Calcula os casos à mão antes de correres.

1. Com 0 turmas e 30 quilos, o `balanco.py` diz que não houve entregas e que faltam 70 quilos. Cada valor sozinho é válido, mas juntos não fazem sentido. Muda o programa para que, neste caso, escreva "Valores inválidos: sem turmas, não pode haver quilos." e não faça o balanço. Testa com 0 e 30, com 0 e 0, e com 3 e 30. Pista: a condição junta duas comparações, e as duas têm de ser verdadeiras. Rever: [Juntar condições com `and`, `or` e `not`](../03-selecao.md#juntar-condições-com-and-or-e-not).
2. Com 12 turmas e 200 quilos, a média aparece como `16.666666666666668`. Muda o programa para a média aparecer só com uma casa decimal. Testa também com 7 turmas e 100 quilos. Rever: [O `round` arredonda um número](../02-dados-e-interacao.md#o-round-arredonda-um-número).
3. No `posto.py`, a pessoa passa a escrever o nome do alimento, em minúsculas, em vez do número: `arroz`, `enlatados`, `leite` ou `azeite`. Muda o menu e o `match`, com as mesmas caixas. Escolhe tu os casos de teste, e inclui uma palavra com maiúscula, como `Leite`. Pista: a resposta passa a ser um texto, e os valores dos `case` também. Rever: [Escolher entre valores certos com `match`](../03-selecao.md#escolher-entre-valores-certos-com-match).

## Antes de terminares

- [ ] O `balanco.py` dá os resultados das tabelas das fases 2, 4, 5, 7 e 8.
- [ ] O `balanco.py` nunca para com `ZeroDivisionError`, mesmo com 0 turmas.
- [ ] O `posto.py` corre com `match`, com os seis casos da fase 9.

![Rodapé](../../imagens/rodape.png)
