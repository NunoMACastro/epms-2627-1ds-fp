![Cabeçalho](../imagens/cabecalho.png)

# Laboratório: Coleções, strings e escolha de representação

Laboratório do tema Coleções, strings e escolha de representação, do módulo Criar aplicações em linguagem de programação Python. Vais construir o programa do catálogo de um clube de videojogos, que procura jogos pelo código e pelo género e mostra os géneros sem repetidos. Cada passo diz o que fazer, porquê e o que deves ver, e avanças ao teu ritmo. Tudo o que precisas está aqui; o [guia do tema](02-colecoes-strings-e-representacao.md) tem a teoria completa, para quem quiser saber mais.

## O que vais construir

O clube de videojogos de uma escola, inventado para as aulas, tem um catálogo de sete jogos. Cada jogo tem um código, como `PLA-01`, um título, um género e o ano em que saiu. No fim, tens três programas em Python:

- `codigo.py` lê um código escrito de qualquer maneira, como ` pla-01 `, arruma-o e separa as suas partes;
- `catalogo_lista.py` procura um jogo pelo código, com o catálogo guardado numa lista;
- `catalogo.py` faz a mesma procura com o catálogo guardado num dicionário. Depois mostra o catálogo, junta os jogos de um género e diz que géneros há, sem repetidos.

Pelo caminho, ficas a saber tirar fatias de um texto, usar os métodos dos textos e escrever mensagens com f-strings. Ficas também a saber usar tuplos, dicionários, listas que crescem e conjuntos. Fazes ainda, no caderno, a tua **tabela de decisões**: uma tabela com os dados do problema, a coleção que escolheste para cada um e porquê.

| Fase | O que muda | O que funciona no fim |
| --- | --- | --- |
| 1 | Nada no disco; experimentas na consola do Python | Sabes ler um carácter e uma fatia de um texto |
| 2 | `codigo.py`, a primeira versão | O programa arruma o código escrito e separa o género e o número |
| 3 | `codigo.py`, com uma f-string | O programa mostra o código numa só frase, sem espaços a mais |
| 4 | `catalogo_lista.py`, com uma lista de tuplos | O programa procura um jogo pelo código, percorrendo a lista |
| 5 | `catalogo.py`, com um dicionário | O programa procura o jogo pela chave, sem ciclo |
| 6 | `catalogo.py`, com o catálogo percorrido | O programa mostra o catálogo inteiro antes da procura |
| 7 | `catalogo.py`, com uma lista que cresce | O programa junta os jogos do género que se pede, ou diz que não há |
| 8 | `catalogo.py`, com um conjunto | O programa mostra os géneros do catálogo, sem repetidos e por ordem |

No fim, a tua pasta fica assim, com os ficheiros do laboratório do tema 01 e mais estes três:

```text
fp-python/
├── ...
├── codigo.py
├── catalogo_lista.py
└── catalogo.py
```

## Palavras que vais usar

- Coleção: um valor que guarda outros valores, como uma lista. Para saber mais, vê a secção "O catálogo do clube de videojogos" do [guia](02-colecoes-strings-e-representacao.md).
- Carácter: uma letra, um algarismo, um sinal ou um espaço. Um texto é uma sequência de caracteres.
- Índice: a posição de um carácter num texto, ou de um elemento numa lista, a contar do 0.
- Fatia: um pedaço de um texto tirado por posições, como `codigo[0:3]`. O segundo índice não entra.
- Método: uma função que pertence a um valor e se chama com um ponto, como `codigo.upper()`.
- Imutável: que não se pode alterar depois de criado, como um texto ou um tuplo.
- f-string: um texto com um `f` antes das aspas, em que cada par de chavetas recebe um valor.
- Tuplo: um grupo fixo de valores entre parênteses curvos, que não se altera, como `("Celeste", "plataformas", 2018)`.
- Desempacotar: dar a cada valor de um tuplo uma variável própria, numa só linha, como `titulo, genero, ano = jogo`.
- Dicionário: uma coleção de pares chave e valor, em que se procura o valor pela chave.
- Chave: num dicionário, o que se procura, como o código de um jogo. Cada chave aparece uma só vez.
- `KeyError`: o erro de procurar num dicionário uma chave que não existe.
- Lista vazia: a lista sem elementos, `[]`.
- `append`: o método que acrescenta um elemento no fim de uma lista.
- Conjunto: uma coleção sem repetidos e sem ordem. Para saber mais, vê a secção "Conjuntos: valores sem repetidos" do [guia](02-colecoes-strings-e-representacao.md).
- Tabela de decisões: a tabela do teu caderno com os dados, a coleção escolhida para cada um e porquê.

## O que precisas

- O Python 3 e o VS Code, os do laboratório do tema 01. Para confirmares o Python, abre o terminal do VS Code, no menu Terminal, com a opção New Terminal, e escreve `python --version`. Deve aparecer uma linha como `Python 3.13.2`, com o 3 no início. No macOS, o comando é `python3 --version`.
- A pasta `fp-python`, a do laboratório do tema 01. Se não a tiveres, cria-a como diz "Preparar o projeto".
- O caderno, para a tabela de decisões.

Os resultados e as mensagens de erro deste laboratório são os do Python 3.14. Num Python mais antigo, uma mensagem pode ter outras palavras, ou apontar outra coluna da linha. O tipo de erro, a palavra antes dos dois pontos, é o mesmo.

## Se alguma coisa falhar

1. Guardaste o ficheiro? O Python corre o que está guardado no disco. Guarda com Ctrl+S, ou Cmd+S no macOS. Uma bola cheia no separador do ficheiro, no lugar do X, quer dizer que há alterações por guardar.
2. Estás na pasta certa? No terminal, o texto antes do cursor tem de ter `fp-python` no fim. Se não tiver, abre um terminal novo, no menu Terminal, com a opção New Terminal.
3. Estás na consola do Python sem quereres? Se a linha começa por `>>>`, escreve `exit()` e carrega em Enter, para voltares ao terminal.
4. O programa não volta ao terminal? Pode estar à espera que escrevas um código ou um género. Lê a última linha do terminal, escreve e carrega em Enter.
5. Copiaste o código à mão? Confirma as vírgulas entre os elementos e entre os pares, e os parênteses e as chavetas que fecham. Confirma também os dois pontos no fim das linhas do `for`, do `if` e do `else`.

## Preparar o projeto

1. Abre a pasta `fp-python` no VS Code. No menu File, escolhe Open Folder..., isto é, "abrir pasta", e escolhe `fp-python`. Se ainda não tens a pasta, cria-a primeiro no sítio onde guardas os trabalhos, por exemplo em Documentos. O que deves ver: à esquerda, no painel Explorer, o nome `FP-PYTHON`, com os ficheiros que já lá estiverem.

2. No caderno, faz uma tabela com três colunas, com estes títulos: "Os dados", "A coleção" e "Porquê". É a tua tabela de decisões. Em cada paragem em que escolheres uma coleção, acrescentas-lhe uma linha.

## Fase 1: Um texto é uma sequência de caracteres

O código de um jogo, como `"PLA-01"`, é um texto. Um texto é uma coleção: guarda uma sequência de caracteres, por ordem. Cada carácter tem uma posição, o índice, que começa em 0, como nas listas do tema 01. O código tem seis caracteres, com os índices de 0 a 5:

| Carácter | `P` | `L` | `A` | `-` | `0` | `1` |
| --- | --- | --- | --- | --- | --- | --- |
| Índice | 0 | 1 | 2 | 3 | 4 | 5 |

Nesta fase experimentas na consola do Python, onde cada linha mostra logo o resultado. Para saber mais, lê a secção "Um texto é uma sequência de caracteres" do [guia](02-colecoes-strings-e-representacao.md).

1. Abre a consola: no terminal, escreve `python`, ou `python3` no macOS, e carrega em Enter. O que deves ver: umas linhas com a versão do Python e, por baixo, `>>>`, à espera de uma linha.

2. Escreve estas linhas, uma de cada vez, e carrega em Enter depois de cada uma. Antes de cada Enter, prevê o que aparece.

   ```text
   >>> codigo = "PLA-01"
   >>> codigo[0]
   'P'
   >>> len(codigo)
   6
   >>> codigo[-1]
   '1'
   ```

   O que deves ver: os resultados acima. O `codigo[0]` é o primeiro carácter, e a consola mostra-o entre plicas, as aspas simples, para se ver que é um texto. O `len` conta os caracteres. O `-1` é um índice negativo, que conta a partir do fim: `-1` é o último carácter.

3. Agora tira pedaços do código. Um pedaço de um texto, tirado por posições, chama-se fatia. Escreve-se com dois índices separados por dois pontos. O primeiro entra na fatia, e o segundo não entra, como no `range`. Prevê e escreve:

   ```text
   >>> codigo[0:3]
   'PLA'
   >>> codigo[:3]
   'PLA'
   >>> codigo[4:]
   '01'
   ```

   O que deves ver: os resultados acima. O `codigo[0:3]` dá os índices 0, 1 e 2, e para antes do hífen. Sem o primeiro índice, a fatia começa no início. Sem o segundo, vai até ao fim. São estas duas fatias que separam o género e o número de um código.

4. Provoca um erro de propósito: tenta mudar o primeiro carácter do código.

   ```text
   >>> codigo[0] = "D"
   ```

   O que deves ver: uma mensagem de erro, que acaba nesta linha:

   ```text
   TypeError: 'str' object does not support item assignment
   ```

   Quer dizer "erro de tipo: um objeto `str` não aceita que se dê um valor a um elemento". Um texto é imutável: depois de criado, nunca muda. Para ter outro código, constrói-se um texto novo, como `"D" + codigo[1:]`, que dá `'DLA-01'`. Experimenta-o.

5. Sai da consola com `exit()` e Enter. O que deves ver: o terminal normal, sem o `>>>`.

### Paragem 1

Sabes ler um carácter de um texto pelo índice e tirar-lhe uma fatia.

Pensa antes de continuares: que fatia de `"DES-02"` dá `"02"`, e porque é que `"DES-02"[0:2]` não dá o género? A resposta: `[4:]` dá `"02"`. O `[0:2]` dá só `"DE"`, porque o índice 2 não entra; o género é `[0:3]`, ou `[:3]`.

Acrescenta à tua tabela de decisões:

| Os dados | A coleção | Porquê |
| --- | --- | --- |
| O código de um jogo, `PLA-01` | texto | é uma sequência de caracteres, e as partes tiram-se por fatias |

## Fase 2: Arrumar um código com os métodos dos textos

Quem escreve um código no teclado pode escrever ` pla-01 `, com espaços à volta e em minúsculas. Para o Python, isso é outro texto, diferente de `"PLA-01"`. Antes de usar um texto que vem do teclado, é preciso arrumá-lo.

Para isso, cada texto traz consigo funções próprias, os métodos. Chamam-se com um ponto depois do valor e os parênteses no fim. O `strip()` devolve o texto sem os espaços do início e do fim, e o `upper()` devolve o texto em maiúsculas. Nenhum dos dois muda o texto original: devolvem um texto novo. Para saber mais, lê a secção "Os métodos dos textos" do [guia](02-colecoes-strings-e-representacao.md).

1. Cria o ficheiro `codigo.py`. No painel Explorer, passa o rato por cima de `FP-PYTHON` e carrega no ícone New File..., o primeiro dos quatro que aparecem. Escreve o nome e carrega em Enter. Cria-o com este conteúdo:

   ```python
   # codigo.py: lê o código de um jogo do clube e separa as suas duas partes.
   codigo = input("Código do jogo? ").strip().upper()
   prefixo = codigo[:3]
   numero = codigo[4:]
   print("Código arrumado:", codigo)
   print("Género:", prefixo)
   print("Número:", numero)
   ```

   Leitura guiada: a segunda linha lê-se da esquerda para a direita. O `input` devolve o texto escrito, o `strip` tira-lhe os espaços e o `upper` passa o resultado a maiúsculas. Só esse texto arrumado fica em `codigo`. As duas linhas seguintes são as fatias da fase 1: as três primeiras letras e o que está depois do hífen. Os três `print` mostram as partes, uma por linha.

2. Guarda. Antes de correres, prevê o que aparece se escreveres ` pla-01 `, com um espaço antes e outro depois. Depois corre `python codigo.py`, ou `python3 codigo.py` no macOS, e escreve-o. O que deves ver:

   ```text
   Código do jogo?  pla-01 
   Código arrumado: PLA-01
   Género: PLA
   Número: 01
   ```

   Isto quer dizer que os métodos arrumaram o código antes das fatias. Experimenta também `des-02`, que deve dar o género `DES` e o número `02`.

3. Provoca um erro de propósito: na segunda linha, apaga o `.strip()`, para ficar `input("Código do jogo? ").upper()`. Guarda e corre outra vez, com ` pla-01 `. O que deves ver:

   ```text
   Código do jogo?  pla-01 
   Código arrumado:  PLA-01 
   Género:  PL
   Número: -01 
   ```

   Não aparece nenhuma mensagem de erro, e o resultado está errado. O espaço do início ficou no texto e ocupou o índice 0. Por isso, a fatia `[:3]` apanhou o espaço, o `P` e o `L`. É um erro de lógica, que só se vê comparando com o esperado. Volta a pôr o `.strip()`, guarda e corre outra vez.

### Paragem 2

O `codigo.py` arruma o código escrito e separa o género e o número, mesmo com espaços e minúsculas.

Pensa antes de continuares: depois de `texto = " Pla-01"` e de `texto.upper()`, quanto vale `texto`? A resposta: continua `" Pla-01"`. O `upper` devolve um texto novo e não muda o original. Para guardar o resultado, escreve-se `texto = texto.upper()`, como no `codigo.py`.

## Fase 3: Uma mensagem com f-string

O programa escreve três linhas, mas o clube quer uma só frase: "O código PLA-01 é do género PLA e tem o número 1.". Com o `print` e as vírgulas, aparece um espaço antes do ponto final. Com o `+`, era preciso converter o número com `str` e cuidar de cada espaço.

Para isto há as f-strings. Uma f-string é um texto com um `f` antes das aspas. Dentro dele, cada par de chavetas, `{` e `}`, marca o sítio onde entra um valor. O Python calcula o que está entre as chavetas e põe o resultado no lugar delas, já como texto. Para saber mais, lê a secção "Juntar textos e valores com f-strings" do [guia](02-colecoes-strings-e-representacao.md).

1. Em `codigo.py`, substitui as três linhas do `print` por estas duas:

   ```python
   # O int() tira o zero à esquerda: o texto "01" passa ao número 1.
   print(f"O código {codigo} é do género {prefixo} e tem o número {int(numero)}.")
   ```

   Leitura guiada: o `f` antes das aspas faz do texto uma f-string. Há três pares de chavetas. Os dois primeiros recebem as variáveis `codigo` e `prefixo`. O terceiro recebe uma chamada, `int(numero)`, que converte o texto `"01"` no número 1. O ponto final fica colado ao número, porque está escrito colado a ele.

2. Guarda. Antes de correres, prevê a frase que aparece com ` pla-01 `. Depois corre o programa e escreve-o. O que deves ver:

   ```text
   Código do jogo?  pla-01 
   O código PLA-01 é do género PLA e tem o número 1.
   ```

   Com `des-02`, aparece `O código DES-02 é do género DES e tem o número 2.`.

3. Provoca um erro de propósito: apaga o `f` antes das aspas. Guarda e corre com `pla-01`. O que deves ver:

   ```text
   Código do jogo? pla-01
   O código {codigo} é do género {prefixo} e tem o número {int(numero)}.
   ```

   Sem o `f`, as chavetas são caracteres como os outros, e o Python escreve-as tal e qual. Não há mensagem de erro: é um erro de lógica, que se vê no ecrã. Volta a pôr o `f`, guarda e corre outra vez.

### Paragem 3

O `codigo.py` mostra o código numa só frase. Confere o teu com este:

```python
# codigo.py: lê o código de um jogo do clube e separa as suas duas partes.
codigo = input("Código do jogo? ").strip().upper()
prefixo = codigo[:3]
numero = codigo[4:]
# O int() tira o zero à esquerda: o texto "01" passa ao número 1.
print(f"O código {codigo} é do género {prefixo} e tem o número {int(numero)}.")
```

Pensa antes de continuares: o que escrevia `print(f"{prefixo}{numero}")`, com o código `PLA-01`? A resposta: `PLA01`. Entre os dois pares de chavetas não há nada, e por isso os dois valores ficam colados, sem espaço nem hífen.

## Fase 4: O catálogo numa lista de tuplos

O catálogo tem sete jogos, e cada jogo tem quatro dados que andam sempre juntos: o código, o título, o género e o ano. Não faz sentido ter o título de um jogo com o ano de outro. Para guardar um grupo de valores que andam juntos, o Python tem o tuplo. Escreve-se com os valores entre parênteses curvos, separados por vírgulas, e é imutável, como os textos: depois de criado, não muda.

Para usar os valores de um tuplo, dá-se um nome a cada um, numa só linha: `codigo, titulo, genero, ano = jogo`. O primeiro valor vai para a primeira variável, o segundo para a segunda, e assim por diante. Chama-se desempacotar. Funciona também no `for`, quando cada elemento da lista é um tuplo. Para saber mais, lê a secção "Tuplos: valores que andam juntos" do [guia](02-colecoes-strings-e-representacao.md).

1. Cria o ficheiro `catalogo_lista.py` com este conteúdo:

   ```python
   # catalogo_lista.py: o catálogo do clube de videojogos, numa lista de tuplos.
   # Procura um jogo pelo código, percorrendo a lista do princípio ao fim.
   jogos = [
       ("PLA-01", "Super Mario Bros. Wonder", "plataformas", 2023),
       ("PLA-02", "Celeste", "plataformas", 2018),
       ("COR-01", "Forza Horizon 5", "corridas", 2021),
       ("DES-01", "Rocket League", "desporto", 2015),
       ("DES-02", "EA Sports FC 25", "desporto", 2024),
       ("PUZ-01", "Tetris", "puzzle", 1984),
       ("AVE-01", "Minecraft", "aventura", 2011)
   ]

   procura = input("Código do jogo? ").strip().upper()
   encontrado = False
   for codigo, titulo, genero, ano in jogos:
       if codigo == procura:
           print(f"{titulo}, {genero}, {ano}")
           encontrado = True
           # Depois de encontrar o jogo, o resto da lista já não interessa.
           break
   if not encontrado:
       print(f"Não há nenhum jogo com o código {procura}.")
   ```

   Leitura guiada: começa pela lista. Uma lista comprida pode escrever-se com um elemento por linha, e o parêntese reto que a fecha fica sozinho na última. Cada elemento é um tuplo com os quatro dados de um jogo. Depois vem a procura, com o padrão da bandeira e do `break` do tema 01. Em cada volta do `for`, o tuplo desempacota-se nas quatro variáveis. Quando o código é o procurado, o programa mostra o jogo, levanta a bandeira e sai do ciclo. O `if not encontrado` só escreve quando o ciclo acabou sem encontrar o código.

2. Guarda. Antes de correres, prevê o que aparece com cada um destes códigos: `PLA-02`, ` des-01` e `PLA-09`. Depois corre `python catalogo_lista.py` três vezes, uma com cada código. O que deves ver, em cada vez:

   ```text
   Código do jogo? PLA-02
   Celeste, plataformas, 2018
   ```

   ```text
   Código do jogo?  des-01
   Rocket League, desporto, 2015
   ```

   ```text
   Código do jogo? PLA-09
   Não há nenhum jogo com o código PLA-09.
   ```

   O segundo caso confirma que o código é arrumado antes da procura. O terceiro testa um código que não existe.

3. Provoca um erro de propósito: na linha do `for`, apaga o `, ano`, para ficar `for codigo, titulo, genero in jogos:`. Guarda e corre com `PLA-02`. O que deves ver:

   ```text
   Traceback (most recent call last):
     File "C:\Users\aluno\fp-python\catalogo_lista.py", line 15, in <module>
       for codigo, titulo, genero in jogos:
           ^^^^^^^^^^^^^^^^^^^^^^
   ValueError: too many values to unpack (expected 3, got 4)
   ```

   Quer dizer "erro de valor: valores a mais para desempacotar; esperavam-se 3 e vieram 4". Cada tuplo tem quatro valores, e só havia três variáveis para os receber. O caminho do ficheiro, a seguir a `File`, muda de computador para computador. Volta a pôr o `, ano`, guarda e corre outra vez.

### Paragem 4

O `catalogo_lista.py` procura um jogo pelo código, percorrendo a lista.

Pensa antes de continuares: com o código `AVE-01`, o último da lista, quantas voltas dá o ciclo? E com `PLA-09`? A resposta: 7 nos dois casos. Com `AVE-01`, o jogo só aparece na sétima volta. Com `PLA-09`, o ciclo percorre a lista toda sem o encontrar. Um catálogo com mil jogos podia obrigar a mil comparações.

Acrescenta à tua tabela de decisões:

| Os dados | A coleção | Porquê |
| --- | --- | --- |
| O código, o título, o género e o ano de um jogo | tuplo | é um grupo fixo de valores que descrevem um só jogo e não mudam |

## Fase 5: O mesmo catálogo num dicionário

No dia a dia, procuramos muitas coisas por um nome, e não por uma posição. Num dicionário de português, procuras a palavra e lês o significado. Na lista de contactos do telemóvel, procuras o nome e lês o número. O clube procura cada jogo pelo código.

No Python, há uma coleção feita para isto: o dicionário. Guarda pares. Cada par tem uma chave, que é o que se procura, e um valor, que é o que se encontra. Escreve-se entre chavetas, com cada par na forma `chave: valor`. Aqui, as chavetas não estão numa f-string: abrem e fecham o dicionário. Lê-se um valor com a chave entre parênteses retos, como `catalogo["PLA-02"]`, sem ciclo nenhum. Cada chave aparece uma só vez. Para saber mais, lê a secção "Dicionários: procurar por chave" do [guia](02-colecoes-strings-e-representacao.md).

1. Cria o ficheiro `catalogo.py` com este conteúdo:

   ```python
   # catalogo.py: o catálogo do clube de videojogos, num dicionário.
   # Procura um jogo pelo código.
   catalogo = {
       "PLA-01": ("Super Mario Bros. Wonder", "plataformas", 2023),
       "PLA-02": ("Celeste", "plataformas", 2018),
       "COR-01": ("Forza Horizon 5", "corridas", 2021),
       "DES-01": ("Rocket League", "desporto", 2015),
       "DES-02": ("EA Sports FC 25", "desporto", 2024),
       "PUZ-01": ("Tetris", "puzzle", 1984),
       "AVE-01": ("Minecraft", "aventura", 2011)
   }

   codigo = input("Código do jogo? ").strip().upper()
   if codigo in catalogo:
       titulo, genero, ano = catalogo[codigo]
       print(f"{titulo}, {genero}, {ano}")
   else:
       print(f"Não há nenhum jogo com o código {codigo}.")
   ```

   Leitura guiada: o catálogo tem um par por linha. A chave é o código, e o valor é um tuplo com os outros três dados. A procura não tem ciclo. O `in` pergunta se o código é uma chave do dicionário. Se for, `catalogo[codigo]` dá o tuplo desse jogo, que se desempacota em três variáveis. Se não for, o `else` escreve a mensagem. O `in` de um dicionário só pergunta pelas chaves, e nunca pelos valores.

2. Guarda. Antes de correres, prevê o que aparece com `PLA-02`, ` des-01` e `PLA-09`. Depois corre `python catalogo.py` três vezes, uma com cada código. O que deves ver: exatamente as mesmas três respostas da fase 4. Isto quer dizer que as duas representações respondem ao mesmo, de maneiras diferentes.

3. Provoca um erro de propósito: tira a pergunta do `in`. Substitui as cinco linhas do `if` e do `else` por estas duas, encostadas à margem:

   ```python
   titulo, genero, ano = catalogo[codigo]
   print(f"{titulo}, {genero}, {ano}")
   ```

   Guarda e corre com `PLA-09`. O que deves ver:

   ```text
   Traceback (most recent call last):
     File "C:\Users\aluno\fp-python\catalogo.py", line 14, in <module>
       titulo, genero, ano = catalogo[codigo]
                             ~~~~~~~~^^^^^^^^
   KeyError: 'PLA-09'
   ```

   `KeyError` quer dizer "erro de chave", e a seguir vem a chave que não existe. É o erro de procurar num dicionário uma chave que lá não está. Volta a pôr as cinco linhas do `if` e do `else` do passo 1, guarda e corre com `PLA-09`, para confirmares a mensagem.

4. Compara os dois ficheiros. Abre `catalogo_lista.py` e `catalogo.py` lado a lado e conta as linhas da procura em cada um, a partir da linha do `input`, inclusive. No `catalogo_lista.py` são dez, com um ciclo, uma bandeira e um `break`. No `catalogo.py` são seis, sem ciclo.

### Paragem 5

O `catalogo.py` procura um jogo pela chave, sem ciclo, e não para com um código que não existe.

Pensa antes de continuares: com mil jogos no catálogo, qual dos dois programas encontra mais depressa o último jogo, e porquê? A resposta: o do dicionário. A lista compara o código com cada jogo, um a um, até o encontrar. O dicionário vai diretamente à chave, e o tamanho do catálogo quase não conta.

Acrescenta à tua tabela de decisões:

| Os dados | A coleção | Porquê |
| --- | --- | --- |
| O catálogo, procurado pelo código | dicionário, do código para o tuplo do jogo | procura-se pelo código, e não pela posição; cada código existe uma só vez |

## Fase 6: Percorrer o dicionário

O clube quer que o programa mostre o catálogo inteiro antes de perguntar um código. Para isso, é preciso passar por todos os pares do dicionário.

Um `for` sobre um dicionário dá só as chaves. Para ter a chave e o valor em cada volta, usa-se o método `items`, que quer dizer "itens". Em cada volta, dá um tuplo com a chave e o valor, que se desempacota nas duas variáveis do `for`. Os pares saem pela ordem em que foram escritos. Para ter só os valores, sem as chaves, há o método `values`, que quer dizer "valores", e que vais usar na fase 7. Para saber mais, lê a secção "Percorrer um dicionário" do [guia](02-colecoes-strings-e-representacao.md).

1. Em `catalogo.py`, acrescenta estas linhas entre a chaveta que fecha o catálogo e a linha do `codigo = input(...)`, encostadas à margem. Deixa uma linha em branco antes delas e outra depois, como no resto do ficheiro:

   ```python
   print("Catálogo do clube:")
   for codigo, jogo in catalogo.items():
       titulo, genero, ano = jogo
       print(f"{codigo}  {titulo} ({ano})")
   print()
   ```

   Leitura guiada: em cada volta, o `items` dá um par. O código vai para `codigo`, e o tuplo do jogo vai para `jogo`. A linha seguinte desempacota o tuplo nas três variáveis. A f-string escreve o código, dois espaços, o título e o ano entre parênteses. O `print()` vazio, no fim, deixa uma linha em branco antes da pergunta.

2. Guarda. Antes de correres, prevê quantas linhas tem o catálogo e qual é a primeira. Depois corre e escreve `PLA-02`. O que deves ver:

   ```text
   Catálogo do clube:
   PLA-01  Super Mario Bros. Wonder (2023)
   PLA-02  Celeste (2018)
   COR-01  Forza Horizon 5 (2021)
   DES-01  Rocket League (2015)
   DES-02  EA Sports FC 25 (2024)
   PUZ-01  Tetris (1984)
   AVE-01  Minecraft (2011)

   Código do jogo? PLA-02
   Celeste, plataformas, 2018
   ```

   São sete linhas, pela ordem em que os pares estão escritos no catálogo. A procura funciona como antes.

### Paragem 6

O `catalogo.py` mostra o catálogo inteiro e procura um jogo pelo código.

Pensa antes de continuares: se escrevesses `for jogo in catalogo:`, sem o `items`, o que ficava em `jogo` em cada volta? A resposta: o código, a chave, e não o tuplo. Um texto também se desempacota, um carácter por variável. A linha `titulo, genero, ano = jogo` tentava pôr os seis caracteres do código em três variáveis, e o programa parava com `ValueError: too many values to unpack (expected 3)`.

## Fase 7: Uma lista que cresce: os jogos de um género

Agora o programa pergunta um género e mostra os títulos desse género. Não se sabe quantos são: podem ser dois, um ou nenhum. A lista dos títulos tem de começar vazia e crescer à medida que se encontram jogos do género.

Uma lista vazia escreve-se `[]`. Para acrescentar um elemento no fim, usa-se o método `append`, que quer dizer "acrescentar". As listas são mutáveis: o `append` muda a própria lista. Para percorrer os jogos, usa-se o `values` da fase 6, que dá só os valores do dicionário, os tuplos. Para saber mais, lê a secção "Listas que crescem e encolhem" do [guia](02-colecoes-strings-e-representacao.md).

1. Em `catalogo.py`, acrescenta estas linhas no fim do ficheiro, encostadas à margem. Começam por um `print()`, que separa esta parte da procura:

   ```python
   print()

   genero_pedido = input("Que género procuras? ").strip().lower()
   titulos = []
   for jogo in catalogo.values():
       titulo, genero, ano = jogo
       if genero == genero_pedido:
           titulos.append(titulo)
   # Com a lista vazia, o ciclo de baixo não escrevia nada, e o ecrã ficava em branco.
   if len(titulos) == 0:
       print(f"Não há jogos do género {genero_pedido}.")
   else:
       print(f"Jogos de {genero_pedido}: {len(titulos)}")
       for titulo in titulos:
           print("-", titulo)
   ```

   Leitura guiada: o género lido passa a minúsculas, porque os géneros do catálogo estão em minúsculas. A lista `titulos` nasce vazia, antes do ciclo, como um contador nasce a 0. O `for` percorre os tuplos dos jogos, com o `values`. Sempre que o género é o pedido, o `append` acrescenta o título à lista. Depois do ciclo, o `if` trata a lista vazia à parte. Se houver títulos, o programa diz quantos são e escreve um por linha.

2. Guarda. Antes de correres, prevê o que aparece com cada um destes três géneros: `puzzle`, ` Desporto` e `luta`. Depois corre o programa três vezes. Em cada uma, escreve um código qualquer, como `PLA-02`, e depois o género. O que deves ver, no fim do ecrã, em cada vez:

   ```text
   Que género procuras? puzzle
   Jogos de puzzle: 1
   - Tetris
   ```

   ```text
   Que género procuras?  Desporto
   Jogos de desporto: 2
   - Rocket League
   - EA Sports FC 25
   ```

   ```text
   Que género procuras? luta
   Não há jogos do género luta.
   ```

   O segundo caso confirma que o género é arrumado, e o terceiro testa a lista vazia.

3. Provoca um erro de propósito: apaga a linha `titulos = []`. Guarda e corre com `PLA-02` e `puzzle`. O que deves ver: o programa para na linha do `append`, com esta mensagem no fim:

   ```text
   NameError: name 'titulos' is not defined. Did you mean: 'titulo'?
   ```

   Quer dizer "erro de nome: o nome `titulos` não está definido. Querias dizer `titulo`?". A lista nunca nasceu, e não se pode acrescentar nada a uma coisa que não existe. Repara na sugestão do fim: desta vez, engana-se. Trocar `titulos` por `titulo` não corrige nada, porque a causa é a linha que falta, antes do ciclo. A mensagem é uma pista, e não a resposta. Volta a pôr a linha `titulos = []`, guarda e corre outra vez.

### Paragem 7

O `catalogo.py` junta numa lista os jogos do género pedido e trata o caso de não haver nenhum.

Pensa antes de continuares: porque é que os títulos de um género se guardam numa lista, e não num tuplo? A resposta: porque o número de títulos não se sabe à partida, e a lista cresce com o `append`. Um tuplo não muda depois de criado, e não podia receber os títulos um a um.

Acrescenta à tua tabela de decisões:

| Os dados | A coleção | Porquê |
| --- | --- | --- |
| Os títulos do género pedido | lista, que começa vazia | não se sabe quantos são, e a lista cresce um a um; pode ficar vazia |

## Fase 8: Os géneros sem repetidos, com um conjunto

Por fim, o clube quer saber que géneros há no catálogo. Há sete jogos, mas os géneros repetem-se: há dois de plataformas e dois de desporto. Numa lista de géneros, `plataformas` aparecia duas vezes.

Para isto há o conjunto: uma coleção sem repetidos e sem ordem. Cria-se vazio com `set()`, e acrescenta-se um valor com o método `add`. Se o valor já lá estiver, nada muda: cada valor fica uma só vez. Para saber mais, lê a secção "Conjuntos: valores sem repetidos" do [guia](02-colecoes-strings-e-representacao.md).

1. Em `catalogo.py`, acrescenta estas linhas no fim do ficheiro, encostadas à margem:

   ```python
   print()

   generos = set()
   for jogo in catalogo.values():
       # O conjunto ignora um género que já lá esteja: cada um fica uma só vez.
       generos.add(jogo[1])
   print(f"{len(catalogo)} jogos, {len(generos)} géneros diferentes")
   print(generos)
   ```

   Leitura guiada: o conjunto nasce vazio, com `set()`. O `for` percorre os tuplos dos jogos, e o `jogo[1]` é o género, o segundo valor do tuplo. O `add` acrescenta-o ao conjunto. Quando chega o segundo jogo de plataformas, o `add` não faz nada, porque `plataformas` já lá está. No fim, o `len` do dicionário conta os jogos, e o do conjunto conta os géneros.

2. Guarda. Antes de correres, prevê quantos géneros diferentes há. Depois corre o programa duas vezes, com `PLA-02` e `puzzle`, e olha para as duas últimas linhas. O que deves ver: as duas vezes, `7 jogos, 5 géneros diferentes`. Por baixo, o conjunto, entre chavetas, com os cinco géneros, por exemplo:

   ```text
   {'desporto', 'puzzle', 'plataformas', 'aventura', 'corridas'}
   ```

   A ordem dos géneros é provavelmente diferente nas duas vezes. Um conjunto não guarda a ordem, e o Python pode mostrá-lo de cada vez por outra ordem. As chavetas, aqui, são a forma de o Python escrever um conjunto.

3. Para os géneros aparecerem sempre pela mesma ordem, usa a função `sorted`, que devolve uma lista com os valores ordenados. Substitui a última linha, `print(generos)`, por esta:

   ```python
   print(sorted(generos))
   ```

   Guarda e corre duas vezes. O que deves ver: as duas vezes, a mesma lista, por ordem alfabética, entre parênteses retos:

   ```text
   ['aventura', 'corridas', 'desporto', 'plataformas', 'puzzle']
   ```

4. Provoca um erro de propósito: muda `generos = set()` para `generos = {}`. Guarda e corre. O que deves ver: o programa para na linha do `add` com esta mensagem, no fim:

   ```text
   AttributeError: 'dict' object has no attribute 'add'
   ```

   Quer dizer "erro de atributo: um objeto `dict` não tem `add`". As chavetas vazias não são um conjunto vazio, são um dicionário vazio. Os dicionários não têm `add`, porque guardam pares, e não valores soltos. Volta a pôr `generos = set()`, guarda e corre outra vez.

5. Por fim, atualiza o comentário do início, porque o programa passou a fazer mais coisas. Substitui as duas primeiras linhas do ficheiro por estas três:

   ```python
   # catalogo.py: o catálogo do clube de videojogos, num dicionário.
   # Mostra o catálogo, procura um jogo pelo código, junta os jogos de um género
   # e diz que géneros há, sem repetidos.
   ```

### Paragem 8

O `catalogo.py` está completo. Corre-o com `pla-02` e `puzzle`, e confere o ecrã:

```text
Catálogo do clube:
PLA-01  Super Mario Bros. Wonder (2023)
PLA-02  Celeste (2018)
COR-01  Forza Horizon 5 (2021)
DES-01  Rocket League (2015)
DES-02  EA Sports FC 25 (2024)
PUZ-01  Tetris (1984)
AVE-01  Minecraft (2011)

Código do jogo? pla-02
Celeste, plataformas, 2018

Que género procuras? puzzle
Jogos de puzzle: 1
- Tetris

7 jogos, 5 géneros diferentes
['aventura', 'corridas', 'desporto', 'plataformas', 'puzzle']
```

Confere também o teu ficheiro com este:

```python
# catalogo.py: o catálogo do clube de videojogos, num dicionário.
# Mostra o catálogo, procura um jogo pelo código, junta os jogos de um género
# e diz que géneros há, sem repetidos.
catalogo = {
    "PLA-01": ("Super Mario Bros. Wonder", "plataformas", 2023),
    "PLA-02": ("Celeste", "plataformas", 2018),
    "COR-01": ("Forza Horizon 5", "corridas", 2021),
    "DES-01": ("Rocket League", "desporto", 2015),
    "DES-02": ("EA Sports FC 25", "desporto", 2024),
    "PUZ-01": ("Tetris", "puzzle", 1984),
    "AVE-01": ("Minecraft", "aventura", 2011)
}

print("Catálogo do clube:")
for codigo, jogo in catalogo.items():
    titulo, genero, ano = jogo
    print(f"{codigo}  {titulo} ({ano})")
print()

codigo = input("Código do jogo? ").strip().upper()
if codigo in catalogo:
    titulo, genero, ano = catalogo[codigo]
    print(f"{titulo}, {genero}, {ano}")
else:
    print(f"Não há nenhum jogo com o código {codigo}.")
print()

genero_pedido = input("Que género procuras? ").strip().lower()
titulos = []
for jogo in catalogo.values():
    titulo, genero, ano = jogo
    if genero == genero_pedido:
        titulos.append(titulo)
# Com a lista vazia, o ciclo de baixo não escrevia nada, e o ecrã ficava em branco.
if len(titulos) == 0:
    print(f"Não há jogos do género {genero_pedido}.")
else:
    print(f"Jogos de {genero_pedido}: {len(titulos)}")
    for titulo in titulos:
        print("-", titulo)
print()

generos = set()
for jogo in catalogo.values():
    # O conjunto ignora um género que já lá esteja: cada um fica uma só vez.
    generos.add(jogo[1])
print(f"{len(catalogo)} jogos, {len(generos)} géneros diferentes")
print(sorted(generos))
```

Pensa antes de continuares: o conjunto dos géneros podia substituir o catálogo inteiro? A resposta: não. O conjunto diz que géneros há, e mais nada. Perdeu quantos jogos há de cada género, os títulos e a ordem. Um conjunto serve quando a pergunta é "que valores há, cada um uma vez", e não quando os repetidos contam.

Acrescenta à tua tabela de decisões:

| Os dados | A coleção | Porquê |
| --- | --- | --- |
| Os géneros que há no catálogo | conjunto | cada género conta uma só vez, e a ordem não interessa; para mostrar, ordena-se com `sorted` |

## Problemas frequentes

### `SyntaxError: '{' was never closed` ou `'[' was never closed`

Falta a chaveta que fecha o dicionário, ou o parêntese reto que fecha a lista. A mensagem diz em que linha a coleção abriu. Confirma que o catálogo acaba com a chaveta, ou com o parêntese reto, sozinho na última linha. Num Python mais antigo, a mensagem é só `SyntaxError: invalid syntax`, e aponta a primeira linha depois do catálogo.

### `SyntaxError: invalid syntax. Perhaps you forgot a comma?` numa linha do dicionário

Quer dizer "erro de sintaxe: escrita inválida. Talvez te tenhas esquecido de uma vírgula?". Falta a vírgula no fim da linha que a mensagem mostra. Entre dois pares de um dicionário tem de haver uma vírgula, e só o último par não a leva. Num Python mais antigo, a mensagem é só `SyntaxError: invalid syntax`, e aponta a linha seguinte.

### `TypeError: 'tuple' object is not callable` numa linha da lista

Falta uma vírgula entre dois tuplos da lista, no fim da primeira das duas linhas que a mensagem mostra. Sem a vírgula, o Python lê o segundo tuplo como se fosse uma chamada ao primeiro, e um tuplo não se pode chamar. Antes da mensagem, aparece um aviso, `SyntaxWarning`, que acaba em `perhaps you missed a comma?`, isto é, "talvez te tenhas esquecido de uma vírgula?". É mesmo isso: acrescenta a vírgula.

### `KeyError` com um código que existe

O código foi escrito noutra forma, com minúsculas ou espaços, e não foi arrumado. Confirma que a linha do `input` acaba em `.strip().upper()`. Para o Python, `pla-02` e `PLA-02` são chaves diferentes.

### O programa diz que não há jogos de um género que existe

O género escrito tem maiúsculas ou espaços. Confirma que a linha do `input` do género acaba em `.strip().lower()`, porque os géneros do catálogo estão em minúsculas.

### `ValueError: too many values to unpack` ou `not enough values to unpack`

O número de variáveis à esquerda do `=`, ou no `for`, não é igual ao número de valores do tuplo. Cada tuplo do `catalogo_lista.py` tem quatro valores, e cada tuplo do `catalogo.py` tem três.

### Aparecem as chavetas no ecrã, como `{titulo}`

Falta o `f` antes das aspas da f-string. Acrescenta-o, colado às aspas: `f"..."`.

### A ordem dos géneros muda de cada vez que corres

Estás a mostrar o conjunto diretamente, com `print(generos)`. Um conjunto não tem ordem. Usa `print(sorted(generos))`.

## Desafios

1. Os jogos de cada década. Em `catalogo.py`, acrescenta no fim uma parte que conta quantos jogos há de cada década, como `Anos 2010: 3`. Mostra as décadas por ordem. Antes de correres, conta à mão. Pista: a década de um ano calcula-se com a divisão inteira e uma multiplicação. Um dicionário serve de contador, com uma chave por década.

2. Procurar por uma parte do título. Faz um programa novo, `procurar_por_titulo.py`, com o mesmo catálogo. O programa pergunta uma parte do título e mostra o código e o título dos jogos que a têm. A procura não liga a maiúsculas: `mine` encontra o Minecraft, e `LEAGUE` encontra o Rocket League. Se nenhum jogo a tiver, diz-o. Testa também com uma letra só, como `o`. Pista: o `in` pergunta se um texto aparece dentro de outro.

3. Acrescentar um jogo. Faz um programa novo, `acrescentar_jogo.py`, com o mesmo catálogo. O programa pede o código, o título, o género e o ano de um jogo novo, e acrescenta-o ao catálogo. Se o código já existir, o programa não pode apagar o jogo que lá está. Nesse caso, diz de que jogo é o código e não acrescenta nada. No fim, mostra quantos jogos tem o catálogo. Testa com `PUZ-02`, Portal 2, puzzle, 2011, e depois com `PLA-02`. Pista: dar um valor a uma chave que já existe substitui o valor antigo.

## Antes de terminares

- [ ] O `codigo.py` arruma ` pla-01 ` e mostra a frase com o género `PLA` e o número 1.
- [ ] O `catalogo_lista.py` e o `catalogo.py` dão a mesma resposta com `PLA-02`, ` des-01` e `PLA-09`.
- [ ] O `catalogo.py` mostra o catálogo, os jogos de `puzzle`, de ` Desporto` e de `luta`, e os cinco géneros por ordem.
- [ ] A tua tabela de decisões tem as cinco linhas das paragens 1, 4, 5, 7 e 8.
- [ ] Sabes dizer de que tipo foi cada erro que provocaste: de sintaxe, de execução ou de lógica.
- [ ] Consegues explicar, por palavras tuas, porque é que o catálogo ficou num dicionário e os géneros num conjunto. E porque é que um conjunto não pode substituir sempre uma lista.

![Rodapé](../imagens/rodape.png)
