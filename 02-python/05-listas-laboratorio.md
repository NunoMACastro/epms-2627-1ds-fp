![Cabeçalho](../imagens/cabecalho.png)

# Laboratório: Listas

Laboratório do tema Listas, do módulo Criar aplicações em linguagem de programação Python. Vais construir, fase a fase, um programa que mostra o estado de uma equipa num jogo, a partir de uma lista. Cada passo diz o que fazer, porquê e o que deves ver, e avanças ao teu ritmo. Tudo o que precisas está aqui; o [guia do tema](05-listas.md) tem a teoria completa, para quem quiser saber mais.

## O que vais construir

Num jogo de equipa, cada jogador tem pontos de vida, de 0 a 100. Um jogador com 0 pontos de vida está fora de combate. Os pontos de vida dos cinco jogadores de uma equipa estão numa lista, `[80, 45, 0, 100, 25]`, pela ordem dos jogadores.

No fim, o programa `equipa.py` mostra o resumo da equipa e o estado de cada jogador. Diz também qual é o primeiro jogador fora de combate. Depois usa a poção da equipa, que dá 30 pontos de vida a cada jogador em jogo, sem passar dos 100. Funciona também com uma equipa sem jogadores. Com a lista do enunciado, o ecrã final é este:

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

Pelo caminho, ficas a saber usar os elementos de uma lista pelo índice e contar os elementos com o `len`. Ficas também a saber percorrer uma lista pelo valor e pelo índice, e mudar os seus elementos. E ficas a saber procurar com uma bandeira, parar com `break` e saltar com `continue`. No fim, testas o programa com a lista vazia, com um elemento e com vários.

| Fase | O que muda em `equipa.py` | O que funciona no fim |
| --- | --- | --- |
| 1 | A lista e o índice | O programa mostra a lista, o primeiro e o último jogador |
| 2 | O `len` | O programa conta os jogadores e encontra o último sozinho |
| 3 | Um `for` sobre a lista | O programa mostra a vida total e a média |
| 4 | Um `for` com o índice | O programa mostra cada jogador com o seu número |
| 5 | Uma bandeira | O programa diz se há algum jogador fora de combate |
| 6 | O `break` | O programa diz qual é o primeiro jogador fora de combate |
| 7 | Mudar elementos pelo índice | A poção dá vida a todos os jogadores |
| 8 | O `continue` | A poção salta os jogadores fora de combate |
| 9 | Os três casos de teste | O programa funciona também sem jogadores e com um só |

No fim, a tua pasta tem mais um ficheiro, ao lado dos scripts dos temas anteriores:

```text
fp-python/
├── ...
└── equipa.py
```

## Palavras que vais usar

- Lista: o array do pseudocódigo, em Python; guarda vários valores, numa ordem fixa, com um só nome. Escreve-se entre parênteses retos, com os valores separados por vírgulas. Para saber mais, vê a secção "Uma lista guarda vários valores com um só nome" do [guia](05-listas.md).
- Elemento: cada valor guardado numa lista.
- Índice: a posição de um elemento na lista, a contar do 0. O primeiro elemento tem o índice 0. Para saber mais, vê a secção "O índice: a posição de cada elemento" do [guia](05-listas.md).
- Último índice válido: o número de elementos menos 1. Numa lista de 5 elementos, é o 4.
- `IndexError`: o erro de execução que aparece quando se usa um índice que não existe na lista.
- `len`: a função predefinida que diz quantos elementos tem uma lista. Para saber mais, vê a secção "O `len`: quantos elementos tem a lista" do [guia](05-listas.md).
- Percorrer uma lista: passar por todos os elementos, um a um, fazendo alguma coisa com cada um.
- Percorrer pelo valor: com `for vida in pontos_de_vida:`; em cada volta, a variável recebe um elemento. Para saber mais, vê a secção "Percorrer a lista pelo valor, com `for`" do [guia](05-listas.md).
- Percorrer pelo índice: com `for i in range(0, len(pontos_de_vida)):`; em cada volta, a variável recebe uma posição. Para saber mais, vê a secção "Percorrer a lista pelo índice, com `range` e `len`" do [guia](05-listas.md).
- Bandeira: uma variável `bool` que começa em `False` e passa a `True` quando acontece o que se procura. Para saber mais, vê a secção "Procurar um valor: a pesquisa com bandeira" do [guia](05-listas.md).
- `break`: termina o ciclo imediatamente; é o `Parar` do pseudocódigo.
- `continue`: termina só a volta atual e passa à seguinte; é o `Continuar` do pseudocódigo.
- Lista vazia: a lista sem elementos, `[]`. Para saber mais, vê a secção "A lista vazia e os três casos de teste" do [guia](05-listas.md).

## O que precisas

- O Python 3, o interpretador que corre os teus scripts. Para confirmares que o tens, abre o terminal do VS Code e escreve `python --version`. Deve aparecer uma linha como `Python 3.13.2`, com o 3 à frente. No Windows, se o `python` não funcionar, usa `py --version`; no macOS, `python3 --version`.
- O VS Code, com a pasta `fp-python` aberta, a mesma dos temas anteriores. Se não a tiveres, cria uma pasta com esse nome e abre-a no VS Code: no menu File, escolhe Open Folder... e depois a pasta.

As mensagens de erro deste laboratório são as do Python 3.14. Num Python mais antigo, uma mensagem pode ter outras palavras, ou não ter os sinais `~~~^^^` por baixo da linha. O tipo de erro, a palavra antes dos dois pontos na última linha, é o mesmo.

## Se alguma coisa falhar

1. Guardaste o ficheiro? O Python corre o que está guardado no disco, e não o que vês no ecrã. Guarda com Ctrl+S, ou Cmd+S no macOS.
2. Estás na pasta certa? No terminal, o texto antes do cursor tem de acabar em `fp-python`. Se não acabar, abre um terminal novo no menu Terminal, com a opção New Terminal.
3. Estás na consola do Python sem quereres? Se a linha começa por `>>>`, escreve `exit()` e carrega em Enter, para voltares ao terminal.
4. Copiaste o código à mão? Confirma os parênteses retos e as vírgulas da lista. Confirma também os dois pontos no fim das linhas do `for` e do `if`, e os quatro espaços da indentação.
5. Desfizeste o erro da fase anterior? Algumas fases mandam provocar um erro de propósito. Antes de passares à fase seguinte, o programa tem de voltar a dar o resultado certo.

## Fase 1: A lista e o índice

Uma lista guarda vários valores com um só nome, uns a seguir aos outros. Em vez de cinco variáveis, uma por jogador, a equipa fica numa só, `pontos_de_vida`. Escreve-se como um array do pseudocódigo: os valores entre parênteses retos, separados por vírgulas. Para usar um só elemento, escreve-se o nome da lista e a posição entre parênteses retos. A essa posição chama-se índice, e começa no 0: `pontos_de_vida[0]` é o primeiro jogador. Para saber mais, lê a secção "O índice: a posição de cada elemento" do [guia](05-listas.md).

1. Cria o ficheiro novo, para o programa da equipa: no painel Explorer, clica no ícone New File..., escreve `equipa.py` e carrega em Enter. O conteúdo do ficheiro é este:

   ```python
   # equipa.py: o estado de uma equipa num jogo, a partir dos pontos de vida de cada jogador.

   pontos_de_vida = [80, 45, 0, 100, 25]
   print("Pontos de vida:", pontos_de_vida)
   print("Primeiro jogador:", pontos_de_vida[0], "pontos de vida")
   print("Último jogador:", pontos_de_vida[4], "pontos de vida")
   ```

   Leitura guiada: a linha 3 cria a lista, com os pontos de vida dos cinco jogadores, e guarda-a com o nome `pontos_de_vida`. O nome vai no plural, porque a lista guarda vários valores. O primeiro `print` mostra a lista inteira. O segundo usa o elemento de índice 0, o primeiro jogador. O terceiro usa o de índice 4, o último, porque numa lista de cinco elementos os índices vão de 0 a 4.

2. Guarda. Antes de correres, prevê as três linhas que aparecem. Depois, no terminal, corre:

   ```bash
   python equipa.py
   ```

   No Windows, se o `python` não funcionar, o comando é `py equipa.py`; no macOS, é `python3 equipa.py`. Também podes usar o botão de correr do VS Code.

   O que deves ver:

   ```text
   Pontos de vida: [80, 45, 0, 100, 25]
   Primeiro jogador: 80 pontos de vida
   Último jogador: 25 pontos de vida
   ```

   O `print` de uma lista mostra-a com os parênteses retos e as vírgulas, tal como a escreveste. Se aparecer uma mensagem de erro, vê os [problemas frequentes](#problemas-frequentes).

3. Provoca um erro de propósito: na última linha, muda o `[4]` para `[5]`. Guarda e corre. O que deves ver:

   ```text
   Pontos de vida: [80, 45, 0, 100, 25]
   Primeiro jogador: 80 pontos de vida
   Traceback (most recent call last):
     File "C:\Users\aluno\Documents\fp-python\equipa.py", line 6, in <module>
       print("Último jogador:", pontos_de_vida[5], "pontos de vida")
                                ~~~~~~~~~~~~~~^^^
   IndexError: list index out of range
   ```

   As duas primeiras linhas aparecem, e o programa para na linha 6. É um erro de execução. Lê-se de baixo para cima. A última linha quer dizer "erro de índice: índice da lista fora dos limites". Os sinais `~~~^^^` marcam `pontos_de_vida[5]`, a parte que falhou. Não há índice 5, porque o último índice válido é o 4. O caminho do ficheiro muda de computador para computador. Volta a pôr `[4]`, guarda e corre outra vez.

### Paragem 1

O `equipa.py` mostra a lista, o primeiro e o último jogador.

Pensa antes de continuares: se a equipa tivesse 8 jogadores, que índice tinha o último? A resposta: o 7, o número de elementos menos 1.

## Fase 2: O tamanho da lista, com `len`

O `[4]` da fase 1 só serve para uma equipa de cinco jogadores. Se entrar um sexto jogador, o programa continua a mostrar o quinto como se fosse o último, e não avisa. O Python tem uma função predefinida que diz quantos elementos tem uma lista, o `len`, do inglês *length*, "comprimento". `len(pontos_de_vida)` dá 5, e o último índice é esse número menos 1. Para saber mais, lê a secção "O `len`: quantos elementos tem a lista" do [guia](05-listas.md).

1. Em `equipa.py`, substitui tudo o que está abaixo da linha da lista por estas linhas, para o programa contar os jogadores:

   ```python
   numero_de_jogadores = len(pontos_de_vida)
   print("Pontos de vida:", pontos_de_vida)
   print("Jogadores na equipa:", numero_de_jogadores)
   print("Primeiro jogador:", pontos_de_vida[0], "pontos de vida")
   # O último índice válido é o número de elementos menos 1.
   print("Último jogador:", pontos_de_vida[numero_de_jogadores - 1], "pontos de vida")
   ```

   Leitura guiada: a primeira linha chama o `len` com a lista e guarda o resultado na variável `numero_de_jogadores`. A linha do último jogador usa uma conta como índice. O Python faz primeiro a conta, `5 - 1`, e só depois vai buscar o elemento de índice 4.

2. Guarda e corre. O que deves ver:

   ```text
   Pontos de vida: [80, 45, 0, 100, 25]
   Jogadores na equipa: 5
   Primeiro jogador: 80 pontos de vida
   Último jogador: 25 pontos de vida
   ```

   O resultado é o da fase 1, com mais uma linha. A diferença está no código: o programa já não depende do número de jogadores.

3. Confirma-o: entra um sexto jogador na equipa, com 60 pontos de vida. Muda a lista para `[80, 45, 0, 100, 25, 60]`, guarda e prevê o que muda antes de correres. O que deves ver: `Jogadores na equipa: 6` e `Último jogador: 60 pontos de vida`, sem mudares mais nenhuma linha. Volta a pôr a lista `[80, 45, 0, 100, 25]`, guarda e corre outra vez.

### Paragem 2

O `equipa.py` conta os jogadores e encontra o último, seja qual for o tamanho da lista.

Pensa antes de continuares: porque é que `pontos_de_vida[numero_de_jogadores]` daria `IndexError`? A resposta: o número de elementos, 5, está um a seguir ao último índice, o 4.

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

## Fase 3: Percorrer pelo valor, a vida total e a média

Para saber a vida total da equipa, é preciso somar os cinco jogadores. Em vez de uma conta com cinco parcelas, percorre-se a lista. O `Para cada` do pseudocódigo passa a `for`, e lê-se "para cada vida em pontos de vida". Em cada volta, a variável `vida` recebe o elemento seguinte da lista, do primeiro ao último, e o ciclo acaba sozinho. A isto chama-se percorrer pelo valor, porque a variável recebe o valor de cada elemento. Para saber mais, lê a secção "Percorrer a lista pelo valor, com `for`" do [guia](05-listas.md).

1. Em `equipa.py`, acrescenta estas linhas no fim do ficheiro, com uma linha em branco antes, encostadas à margem:

   ```python
   # A vida total soma os pontos de todos os jogadores.
   total = 0
   for vida in pontos_de_vida:
       total = total + vida
   print("Vida total da equipa:", total)
   media = total / numero_de_jogadores
   print("Vida média:", media)
   ```

   Leitura guiada: o acumulador `total` nasce antes do ciclo, com 0. O `for` leva os dois pontos no fim, e o corpo, a soma, vai indentado com quatro espaços. As linhas que vêm a seguir estão encostadas à margem: ficam fora do ciclo e executam-se uma só vez, no fim. A média divide o total pelo número de jogadores.

2. Guarda. Antes de correres, calcula de cabeça a vida total e a média. Depois corre. O que deves ver no fim:

   ```text
   Vida total da equipa: 250
   Vida média: 50.0
   ```

   A tabela de iterações mostra como o total cresce, uma linha por volta:

   | Volta | vida | total no fim da volta |
   | --- | ---: | ---: |
   | antes do ciclo | sem valor | 0 |
   | 1.ª | 80 | 80 |
   | 2.ª | 45 | 125 |
   | 3.ª | 0 | 125 |
   | 4.ª | 100 | 225 |
   | 5.ª | 25 | 250 |

   A média é 250 a dividir por 5, e aparece `50.0` porque a divisão com `/` dá sempre um `float`.

### Paragem 3

O `equipa.py` mostra a vida total e a vida média da equipa.

Pensa antes de continuares: o que aconteceria se a linha `total = 0` estivesse dentro do ciclo, com quatro espaços? A resposta: o total voltava a 0 no início de cada volta. No fim, guardava só o último jogador, 25, e a média dava `5.0`.

## Fase 4: Percorrer pelo índice, o estado de cada jogador

Agora queres uma linha por jogador, como "Jogador 1 tem 80 pontos de vida". O valor já não chega, porque cada linha precisa do número do jogador, que é a sua posição. Percorre-se a lista pelo índice, com o `for` e o `range`. O `range(0, numero_de_jogadores)` dá os números de 0 a 4, os índices da lista: começa no 0 e para logo antes do 5. É o `Para i = 0, i < 5, i++` do pseudocódigo. Para saber mais, lê a secção "Percorrer a lista pelo índice, com `range` e `len`" do [guia](05-listas.md).

1. Em `equipa.py`, acrescenta estas linhas no fim, com uma linha em branco antes:

   ```python
   for i in range(0, numero_de_jogadores):
       # O i + 1 faz com que o jogador de índice 0 seja, para as pessoas, o jogador 1.
       print("Jogador", i + 1, "tem", pontos_de_vida[i], "pontos de vida")
   ```

   Leitura guiada: em cada volta, `i` recebe um índice, de 0 a 4, e `pontos_de_vida[i]` é o elemento nessa posição. O `i + 1` só entra no que se mostra às pessoas, que contam os jogadores a partir do 1.

2. Guarda e corre. O que deves ver no fim:

   ```text
   Jogador 1 tem 80 pontos de vida
   Jogador 2 tem 45 pontos de vida
   Jogador 3 tem 0 pontos de vida
   Jogador 4 tem 100 pontos de vida
   Jogador 5 tem 25 pontos de vida
   ```

3. Provoca um erro de propósito: muda o `range(0, numero_de_jogadores)` para `range(1, numero_de_jogadores)`. Guarda e corre. O que deves ver no fim:

   ```text
   Jogador 2 tem 45 pontos de vida
   Jogador 3 tem 0 pontos de vida
   Jogador 4 tem 100 pontos de vida
   Jogador 5 tem 25 pontos de vida
   ```

   Não aparece nenhuma mensagem de erro, e falta o jogador 1. É um erro de lógica. O `range(1, 5)` começa no índice 1, e o elemento de índice 0 nunca é usado. Só dá por ele quem compara com o resultado esperado. Volta a pôr `range(0, numero_de_jogadores)`, guarda e corre outra vez.

### Paragem 4

O `equipa.py` mostra cada jogador com o seu número.

Pensa antes de continuares: porque é que aqui não serve o `for vida in pontos_de_vida:` da fase 3? A resposta: a variável `vida` só tem o valor de cada elemento, e não a posição. Sem a posição, o programa não sabe o número do jogador.

## Fase 5: Procurar com uma bandeira

Há algum jogador fora de combate? A resposta é sim ou não. O programa olha para os jogadores um a um. Se encontrar um com 0 pontos de vida, a resposta é sim. Mas só pode responder que não depois de ver a lista toda. A resposta fica guardada numa bandeira, uma variável `bool` que começa em `False` e passa a `True` quando aparece o que se procura. Em Python, escreve-se `False` e `True`, com maiúscula. Para saber mais, lê a secção "Procurar um valor: a pesquisa com bandeira" do [guia](05-listas.md).

1. Em `equipa.py`, acrescenta estas linhas no fim, com uma linha em branco antes:

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

   Leitura guiada: a bandeira `alguem_fora` nasce antes do ciclo, com `False`, porque ainda não se olhou para nenhum jogador. Dentro do ciclo, só lhe pode acontecer uma coisa: passar a `True`, na volta do 0. O `if` de baixo está encostado à margem, fora do ciclo. Lê a bandeira depois de vista a lista toda, e escreve uma só mensagem. O `if alguem_fora:` lê-se "se há alguém fora", e é o mesmo que `if alguem_fora == True:`, porque a bandeira já é `True` ou `False`. Aqui basta percorrer pelo valor, porque a pergunta é "há algum?" e não "qual?".

2. Guarda e corre. O que deves ver no fim: `Há pelo menos um jogador fora de combate.`

3. Testa o outro caso: muda o 0 da lista para 10, `[80, 45, 10, 100, 25]`, guarda e corre. O que deves ver no fim: `Nenhum jogador está fora de combate.` As linhas de cima também mudam, porque a vida total passa a 260 e a média a `52.0`. Volta a pôr a lista `[80, 45, 0, 100, 25]`, guarda e corre outra vez.

### Paragem 5

O `equipa.py` diz se há algum jogador fora de combate.

Pensa antes de continuares: porque é que a mensagem "Nenhum jogador está fora de combate." não está dentro do ciclo, num `else` do `if vida == 0:`? A resposta: aparecia uma vez por cada jogador em jogo, quatro vezes, mesmo havendo um fora de combate. Só depois de ver a lista toda se pode dizer que não há nenhum.

## Fase 6: Parar com `break`, o primeiro jogador fora de combate

A fase 5 diz que há um jogador fora de combate, mas não diz qual. A resposta é uma posição, e por isso a lista passa a percorrer-se pelo índice. E, depois de encontrar o primeiro, o resto da lista não interessa. O `Parar` do pseudocódigo escreve-se `break` em Python: termina o ciclo imediatamente, e o programa continua na primeira linha a seguir ao ciclo. Para saber mais, lê a secção "Parar a pesquisa com `break`" do [guia](05-listas.md).

1. Em `equipa.py`, substitui as linhas que acrescentaste na fase 5, do comentário da bandeira até ao fim, por estas:

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

   Leitura guiada: o ciclo passou a ir pelo índice, para o programa saber o número do jogador. Quando encontra o 0, escreve a resposta, levanta a bandeira e sai com o `break`. O `break` tem oito espaços, dentro do `if`, e por isso só se executa na volta em que se encontra o jogador. Depois do ciclo, a bandeira diz porque é que ele acabou. Se o `break` o fez sair, a bandeira está `True`. Se os índices se esgotaram sem encontrar nenhum 0, está `False`. O `if not alguem_fora:` lê-se "se não há alguém fora", e é aí que aparece a mensagem de "não encontrado".

2. Guarda. Antes de correres, prevê o que aparece no fim e quantas voltas dá o ciclo. Depois corre. O que deves ver no fim: `Primeiro jogador fora de combate: jogador 3`.

   A tabela de iterações mostra as voltas:

   | Volta | i | pontos_de_vida[i] | `pontos_de_vida[i] == 0` | O que acontece |
   | --- | ---: | ---: | --- | --- |
   | 1.ª | 0 | 80 | `False` | nada |
   | 2.ª | 1 | 45 | `False` | nada |
   | 3.ª | 2 | 0 | `True` | escreve a resposta, `alguem_fora` passa a `True`, `break` |

   O ciclo deu três voltas. Os jogadores 4 e 5 nunca foram vistos.

3. Testa com dois jogadores fora de combate: muda a lista para `[80, 0, 0, 100, 25]`, guarda e corre. O que deves ver no fim: `Primeiro jogador fora de combate: jogador 2`. O jogador 3 também tem 0, mas o `break` já tinha terminado o ciclo.

4. Provoca um erro de propósito, com a mesma lista: apaga a linha do `break` e o comentário de cima dela. Guarda e corre. O que deves ver no fim:

   ```text
   Primeiro jogador fora de combate: jogador 2
   Primeiro jogador fora de combate: jogador 3
   ```

   Sem o `break`, o ciclo continua depois do primeiro, e encontra o segundo. O programa diz que há dois "primeiros", e a segunda linha está errada. É um erro de lógica. Volta a escrever o comentário e o `break`, com oito espaços, e volta a pôr a lista `[80, 45, 0, 100, 25]`. Guarda e corre outra vez.

### Paragem 6

O `equipa.py` diz qual é o primeiro jogador fora de combate, ou que não há nenhum.

Pensa antes de continuares: imagina que o `break` tinha quatro espaços, encostado ao `if` em vez de estar dentro dele. O que mostrava o programa com a lista do enunciado? A resposta: "Nenhum jogador está fora de combate.". O `break` passava a executar-se logo na primeira volta, com o jogador 1, e o 0 do jogador 3 nunca era visto.

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

## Fase 7: Mudar os elementos pelo índice, a poção da equipa

A equipa tem uma poção que dá 30 pontos de vida a cada jogador, sem passar dos 100. A poção muda os pontos de vida, e por isso muda os elementos da lista. Um elemento muda-se como uma variável, com o elemento do lado esquerdo do `=`: `pontos_de_vida[1] = 75` põe 75 no lugar do 45. Para mudar um elemento, o programa precisa da posição dele, isto é, do índice. Para saber mais, lê a secção "Mudar um elemento pelo índice" do [guia](05-listas.md).

1. Os 30 pontos da poção e o máximo de 100 são regras do jogo, e ficam em constantes, no início do programa. Em `equipa.py`, a seguir à primeira linha, o comentário, e à linha em branco, acrescenta estas duas linhas e mais uma linha em branco:

   ```python
   VIDA_MAXIMA = 100
   CURA_DA_POCAO = 30
   ```

   O início do ficheiro fica assim:

   ```python
   # equipa.py: o estado de uma equipa num jogo, a partir dos pontos de vida de cada jogador.

   VIDA_MAXIMA = 100
   CURA_DA_POCAO = 30

   pontos_de_vida = [80, 45, 0, 100, 25]
   ```

2. Experimenta primeiro uma versão que parece certa e não está, para veres o que acontece. Acrescenta estas linhas no fim do ficheiro, com uma linha em branco antes:

   ```python
   # Primeira tentativa: percorrer pelo valor.
   for vida in pontos_de_vida:
       vida = vida + CURA_DA_POCAO
   print("Depois da poção:", pontos_de_vida)
   ```

   Guarda. Antes de correres, prevê a lista que aparece na última linha. Depois corre. O que deves ver no fim: `Depois da poção: [80, 45, 0, 100, 25]`.

   A lista não mudou, e o programa não deu nenhuma mensagem. Em cada volta, a variável `vida` recebe o valor de um elemento. A linha `vida = vida + CURA_DA_POCAO` dá um valor novo à variável, e só à variável. A lista não sabe nada disso, e a variável também não sabe de que posição veio o valor. É o mesmo que acontecia com o `Para cada` na algoritmia, que não mudava o array.

3. Substitui as quatro linhas que acabaste de acrescentar por estas:

   ```python
   # A poção da equipa cura cada jogador, sem passar do máximo de pontos de vida.
   for i in range(0, numero_de_jogadores):
       pontos_de_vida[i] = pontos_de_vida[i] + CURA_DA_POCAO
       if pontos_de_vida[i] > VIDA_MAXIMA:
           pontos_de_vida[i] = VIDA_MAXIMA
   print("Depois da poção:", pontos_de_vida)
   ```

   Leitura guiada: o ciclo vai pelo índice. Em cada volta, a primeira linha do corpo lê o elemento da posição `i`, soma-lhe a cura e escreve o resultado na mesma posição. O `if` a seguir confirma se o jogador passou do máximo e, se passou, põe-no no máximo. O `print` está fora do ciclo e mostra a lista depois de mudada.

4. Guarda. Antes de correres, calcula de cabeça a lista depois da poção. Depois corre. O que deves ver no fim: `Depois da poção: [100, 75, 30, 100, 55]`.

   O jogador 1 tinha 80 e ficava com 110, e o `if` pô-lo nos 100. O jogador 4 passou de 100 a 130, e o `if` também o pôs nos 100. Os outros ganharam 30.

### Paragem 7

O `equipa.py` usa a poção e mostra a lista depois de mudada.

Pensa antes de continuares: o jogador 3 estava fora de combate e ficou com 30 pontos de vida. Faz sentido, num jogo? A resposta: na maioria dos jogos, não. Uma poção de cura não serve a quem já está fora de combate. É a regra que a fase seguinte acrescenta.

## Fase 8: Saltar com `continue`, quem está fora de combate

A regra do jogo é esta: a poção não cura os jogadores fora de combate. No ciclo da poção, a volta de um jogador com 0 pontos de vida tem de ser saltada. O `Continuar` do pseudocódigo escreve-se `continue` em Python. Termina só a volta atual: as linhas do corpo que estão abaixo dele não se executam nessa volta, e o ciclo passa ao jogador seguinte. Para saber mais, lê a secção "Saltar uma volta com `continue`" do [guia](05-listas.md).

1. No bloco da poção, muda o comentário e acrescenta um `if` com o `continue`, logo no início do corpo do ciclo. O bloco fica assim:

   ```python
   # A poção da equipa cura cada jogador em jogo, sem passar do máximo de pontos de vida.
   for i in range(0, numero_de_jogadores):
       if pontos_de_vida[i] == 0:
           # Quem está fora de combate não é curado: passa-se ao jogador seguinte.
           continue
       pontos_de_vida[i] = pontos_de_vida[i] + CURA_DA_POCAO
       if pontos_de_vida[i] > VIDA_MAXIMA:
           pontos_de_vida[i] = VIDA_MAXIMA
   print("Depois da poção:", pontos_de_vida)
   ```

   Leitura guiada: o `continue` está dentro do `if`, com oito espaços, e só se executa na volta de um jogador com 0. Nessa volta, as três linhas de baixo não chegam a correr, e o elemento fica como estava. Nas outras voltas, o `if` não faz nada, e a cura faz-se como na fase 7.

2. Guarda. Antes de correres, prevê o que muda na última linha. Depois corre. O que deves ver no fim: `Depois da poção: [100, 75, 0, 100, 55]`. O jogador 3 continua com 0.

### Paragem 8

O `equipa.py` usa a poção só nos jogadores em jogo.

Pensa antes de continuares: como podias fazer o mesmo sem `continue`? A resposta: punhas as três linhas da cura dentro de um `if pontos_de_vida[i] > 0:`. As duas formas estão certas. O `continue` põe de lado logo no início o caso que não interessa, e o resto do corpo fica com menos indentação.

## Fase 9: Testar com a equipa vazia, com um jogador e com vários

O programa funciona com a lista do enunciado. Mas um programa com listas testa-se sempre com três listas: a lista vazia, uma lista com um só elemento e uma lista com vários. A lista vazia escreve-se `[]`, e o `len` dela é 0. É a equipa antes de entrar algum jogador. Cada um dos três casos mostra erros diferentes, e é por isso que se testam os três. Para saber mais, lê a secção "A lista vazia e os três casos de teste" do [guia](05-listas.md).

1. Muda a lista para `pontos_de_vida = []`, guarda e prevê o que acontece antes de correres. Depois corre. O que deves ver:

   ```text
   Pontos de vida: []
   Jogadores na equipa: 0
   Traceback (most recent call last):
     File "C:\Users\aluno\Documents\fp-python\equipa.py", line 10, in <module>
       print("Primeiro jogador:", pontos_de_vida[0], "pontos de vida")
                                  ~~~~~~~~~~~~~~^^^
   IndexError: list index out of range
   ```

   Segue a rotina. O caso que falhou é a equipa vazia: esperavas um resumo sem jogadores, e o programa parou na linha 10. É um erro de execução. A hipótese: uma lista vazia não tem o índice 0. A mensagem confirma-a, porque marca `pontos_de_vida[0]`. A linha do último jogador falhava pela mesma razão, porque também não há último. Essas duas linhas só fazem sentido quando há pelo menos um jogador.

2. Corrige a causa: põe as duas linhas do primeiro e do último jogador, e o comentário do meio, dentro de um `if`. Substitui essas três linhas por estas:

   ```python
   # Sem jogadores, não há primeiro nem último: a lista vazia não tem o índice 0.
   if numero_de_jogadores > 0:
       print("Primeiro jogador:", pontos_de_vida[0], "pontos de vida")
       # O último índice válido é o número de elementos menos 1.
       print("Último jogador:", pontos_de_vida[numero_de_jogadores - 1], "pontos de vida")
   ```

   Guarda e corre outra vez, ainda com a lista vazia. O que deves ver:

   ```text
   Pontos de vida: []
   Jogadores na equipa: 0
   Vida total da equipa: 0
   Traceback (most recent call last):
     File "C:\Users\aluno\Documents\fp-python\equipa.py", line 21, in <module>
       media = total / numero_de_jogadores
               ~~~~~~^~~~~~~~~~~~~~~~~~~~~
   ZeroDivisionError: division by zero
   ```

   O primeiro erro desapareceu, e apareceu outro, mais abaixo. O ciclo da soma não deu nenhuma volta, e o total ficou 0, o que está certo. Mas a média fez a conta `0 / 0`, e não se pode dividir por zero. A mensagem quer dizer "erro de divisão por zero". O Python mostra os erros de execução um de cada vez, pela ordem das linhas.

3. Corrige esta segunda causa: a média só se calcula quando há jogadores. Substitui as duas linhas da média por estas:

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

   Os ciclos do estado de cada jogador, da procura e da poção não deram nenhuma volta, e não escreveram nada. A procura, com a bandeira em `False`, diz que nenhum jogador está fora de combate, o que está certo.

4. Testa com um só jogador: muda a lista para `[45]`, guarda e prevê antes de correres. O que deves ver:

   ```text
   Pontos de vida: [45]
   Jogadores na equipa: 1
   Primeiro jogador: 45 pontos de vida
   Último jogador: 45 pontos de vida
   Vida total da equipa: 45
   Vida média: 45.0
   Jogador 1 tem 45 pontos de vida
   Nenhum jogador está fora de combate.
   Depois da poção: [75]
   ```

   Com um só jogador, o primeiro é também o último, e as duas linhas mostram o mesmo. O índice do último é `1 - 1`, ou seja, 0, e o programa não sai da lista.

5. Testa com um só jogador fora de combate: muda a lista para `[0]`, guarda e corre. O que deves ver nas duas últimas linhas:

   ```text
   Primeiro jogador fora de combate: jogador 1
   Depois da poção: [0]
   ```

   É o caso em que o valor procurado está na primeira posição. A procura encontra-o logo na primeira volta, e a poção salta-o.

6. Testa com o jogador fora de combate na última posição: muda a lista para `[80, 45, 100, 0]`, guarda e prevê antes de correres. O que deves ver nas duas últimas linhas:

   ```text
   Primeiro jogador fora de combate: jogador 4
   Depois da poção: [100, 75, 100, 0]
   ```

   A procura só o encontra na última volta, e confirma que o `range` chega ao último índice.

7. Volta a pôr a lista `[80, 45, 0, 100, 25]`, guarda e corre. O último passo da rotina é voltar a testar tudo, também o caso que já passava. O que deves ver é o ecrã completo do início deste laboratório, em "O que vais construir".

### Paragem 9

O `equipa.py` dá o resultado certo nos três casos de teste: a equipa vazia, uma equipa com um jogador e equipas com vários. Nas listas com um jogador fora de combate, ele está no início, no meio e no fim.

| Lista | Jogadores | Vida média | Fora de combate | Depois da poção |
| --- | ---: | --- | --- | --- |
| `[]` | 0 | Sem jogadores, não há vida média. | Nenhum jogador está fora de combate. | `[]` |
| `[45]` | 1 | `45.0` | Nenhum jogador está fora de combate. | `[75]` |
| `[0]` | 1 | `0.0` | jogador 1 | `[0]` |
| `[80, 45, 100, 0]` | 4 | `56.25` | jogador 4 | `[100, 75, 100, 0]` |
| `[80, 45, 0, 100, 25]` | 5 | `50.0` | jogador 3 | `[100, 75, 0, 100, 55]` |

Pensa antes de terminares: porque é que o caso da lista vazia mostrou erros que os outros não mostravam? A resposta: com a lista vazia, não há índice 0 e o número de jogadores é 0. Com um jogador ou mais, nem um nem outro acontece, e as duas linhas pareciam certas.

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

# A poção da equipa cura cada jogador em jogo, sem passar do máximo de pontos de vida.
for i in range(0, numero_de_jogadores):
    if pontos_de_vida[i] == 0:
        # Quem está fora de combate não é curado: passa-se ao jogador seguinte.
        continue
    pontos_de_vida[i] = pontos_de_vida[i] + CURA_DA_POCAO
    if pontos_de_vida[i] > VIDA_MAXIMA:
        pontos_de_vida[i] = VIDA_MAXIMA
print("Depois da poção:", pontos_de_vida)
```

## Problemas frequentes

### `IndexError: list index out of range`

O programa usou um índice que não existe na lista. A linha que a mensagem mostra tem os sinais `~~~^^^` por baixo da parte que falhou. Confirma o número de elementos e lembra-te de que o último índice válido é esse número menos 1. Se a lista pode estar vazia, nenhum índice existe, nem o 0.

### `SyntaxError: '[' was never closed`

A mensagem quer dizer "o `[` nunca foi fechado". Falta o parêntese reto do fim da lista, na linha que a mensagem aponta. Acrescenta o `]` depois do último valor.

### `SyntaxError: invalid syntax. Perhaps you forgot a comma?`

A mensagem quer dizer "sintaxe inválida; esqueceste-te de uma vírgula?". Na lista, falta uma vírgula entre dois valores, como em `[80, 45 0, 100, 25]`. Os sinais `^^^^` mostram onde.

### `SyntaxError: expected ':'`

Faltam os dois pontos no fim da linha do `for` ou do `if` que a mensagem mostra.

### `IndentationError: expected an indented block after 'for' statement on line 13`

A mensagem quer dizer "esperava um bloco indentado depois do `for` da linha 13". É a mensagem que aparece se a soma da fase 3 ficar encostada à margem, e o número muda conforme a linha do teu `for`. A linha a seguir aos dois pontos ficou encostada à margem. Recua-a quatro espaços. Dentro de um `if` que está dentro de um `for`, são oito.

### `NameError: name 'pontos_de_vidas' is not defined. Did you mean: 'pontos_de_vida'?`

A mensagem quer dizer "o nome `pontos_de_vidas` não está definido; querias dizer `pontos_de_vida`?". O nome está mal escrito nessa linha, e o Python sugere o nome certo.

### `ZeroDivisionError: division by zero`

O programa dividiu por zero. Com a lista vazia, o número de jogadores é 0. A divisão tem de ficar dentro de um `if numero_de_jogadores > 0:`, como na fase 9.

### A lista não muda depois da poção

O ciclo da poção percorre a lista pelo valor, com `for vida in pontos_de_vida:`. Mudar a variável `vida` não muda a lista. Usa o ciclo pelo índice, com `pontos_de_vida[i]` do lado esquerdo do `=`, como no passo 3 da fase 7.

### Aparecem duas linhas de "Primeiro jogador fora de combate"

Falta o `break`, ou está noutro sítio. Tem de estar dentro do `if`, com oito espaços, a seguir à linha `alguem_fora = True`.

### O resultado não muda depois de corrigires o código

O ficheiro não foi guardado. Guarda com Ctrl+S, ou Cmd+S no macOS, e corre outra vez.

## Desafios

1. O jogador com mais vida. Acrescenta ao programa, antes da poção, uma linha que diga que jogador tem mais pontos de vida, como `Jogador com mais vida: jogador 4 com 100 pontos de vida`. Testa também com `[100, 45, 100]`, em que há um empate, e decide qual dos dois aparece. Com a lista vazia, o programa não pode parar com um erro. Pista: guarda numa variável o maior visto até agora, a começar pelo primeiro jogador, e compara cada jogador com ela. Quando encontrares um com mais, a variável passa a ter esse valor, e outra variável guarda a posição dele.

2. Os jogadores em perigo. Um jogador está em perigo quando ainda está em jogo, mas tem menos de 30 pontos de vida. Acrescenta, antes da poção, uma linha que diga quantos jogadores estão em perigo. Com a lista do enunciado, é 1. Testa também com `[29, 30, 1]`. Pista: a condição tem duas partes, e o `and` junta-as.

3. A poção de reviver. A equipa tem também uma poção de reviver, que traz de volta ao jogo o primeiro jogador fora de combate, com 50 pontos de vida. Usa-a antes da poção de cura. Com a lista do enunciado, o jogador 3 volta com 50 e, depois da poção de cura, fica com 80. Com `[80, 0, 0, 100, 25]`, só o jogador 2 volta. Pista: junta numa só procura o que aprendeste nas fases 6 e 7.

## Antes de terminares

- [ ] O `equipa.py` mostra o ecrã completo de "O que vais construir" com a lista `[80, 45, 0, 100, 25]`.
- [ ] O `equipa.py` dá os resultados da tabela da paragem 9 com as listas `[]`, `[45]`, `[0]` e `[80, 45, 100, 0]`, sem parar com nenhum erro.
- [ ] Sabes dizer de que tipo foi cada erro que provocaste. O `IndexError` e o `ZeroDivisionError` são de execução. O `range(1, ...)`, a falta do `break` e a poção pelo valor são de lógica.
- [ ] Consegues explicar, por palavras tuas, quando percorres uma lista pelo valor e quando a percorres pelo índice.

![Rodapé](../imagens/rodape.png)
