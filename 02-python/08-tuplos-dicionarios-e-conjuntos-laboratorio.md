![Cabeçalho](../imagens/cabecalho.png)

# Laboratório: Tuplos, dicionários e conjuntos

Laboratório do tema Tuplos, dicionários e conjuntos, do módulo Criar aplicações em linguagem de programação Python. Vais construir o programa do catálogo de um clube de videojogos. O programa procura jogos pelo código e pelo género, mostra os géneros sem repetidos e conta os jogos de cada género. Cada passo diz o que fazer, porquê e o que deves ver, e avanças ao teu ritmo. Tudo o que precisas está aqui; o [guia do tema](08-tuplos-dicionarios-e-conjuntos.md) tem a teoria completa, para quem quiser saber mais.

## O que vais construir

O clube de videojogos de uma escola foi inventado para as aulas. Tem um catálogo de sete jogos, e cada jogo tem um código, como `PLA-01`, um título, um género e o ano em que saiu. No fim, tens dois programas em Python:

- `catalogo_lista.py` procura um jogo pelo código, com o catálogo guardado numa lista;
- `catalogo.py` faz a mesma procura com o catálogo guardado num dicionário. Depois mostra o catálogo, junta os jogos de um género, diz que géneros há, sem repetidos, e quantos jogos tem cada um.

Pelo caminho, ficas a saber usar tuplos, dicionários e conjuntos, e a escolher entre eles. Fazes ainda, no caderno, a tua **tabela de decisões**. É uma tabela com os dados do problema, a coleção que escolheste para cada um e porquê.

| Fase | O que muda | O que funciona no fim |
| --- | --- | --- |
| 1 | `catalogo_lista.py`, com uma lista de tuplos | O programa procura um jogo pelo código, percorrendo a lista |
| 2 | `catalogo.py`, com um dicionário | O programa procura o jogo pela chave, sem ciclo |
| 3 | `catalogo.py`, com o catálogo percorrido | O programa mostra o catálogo inteiro antes da procura |
| 4 | `catalogo.py`, com uma lista que cresce | O programa junta os jogos do género que se pede, ou diz que não há |
| 5 | `catalogo.py`, com um conjunto | O programa mostra os géneros do catálogo, sem repetidos e por ordem |
| 6 | `catalogo.py`, com um dicionário de contagens | O programa diz quantos jogos tem cada género |

No fim, a tua pasta fica assim, com os ficheiros dos laboratórios anteriores e mais estes dois:

```text
fp-python/
├── ...
├── catalogo_lista.py
└── catalogo.py
```

## Palavras que vais usar

- Coleção: um valor que guarda outros valores, como uma lista ou um texto.
- Tuplo: um grupo fixo de valores entre parênteses curvos, que não se altera, como `("Celeste", "plataformas", 2018)`. Para saber mais, vê a secção "Tuplos: valores que andam juntos" do [guia](08-tuplos-dicionarios-e-conjuntos.md).
- Desempacotar: dar a cada valor de um tuplo uma variável própria, numa só linha, como `titulo, genero, ano = jogo`.
- Dicionário: uma coleção de pares chave e valor, em que se procura o valor pela chave.
- Chave: num dicionário, o que se procura, como o código de um jogo. Cada chave aparece uma só vez.
- `KeyError`: o erro de procurar num dicionário uma chave que não existe.
- `items` e `values`: os métodos que dão, para percorrer um dicionário, os pares de chave e valor, ou só os valores.
- Lista vazia: a lista sem elementos, `[]`.
- `append`: o método que acrescenta um elemento no fim de uma lista.
- Conjunto: uma coleção sem repetidos e sem ordem. Para saber mais, vê a secção "Conjuntos: valores sem repetidos" do [guia](08-tuplos-dicionarios-e-conjuntos.md).
- `set()` e `add`: a função que cria um conjunto vazio, e o método que lhe acrescenta um valor. Se o valor já lá estiver, nada muda.
- Dicionário de contagens: um dicionário em que cada chave é um valor que apareceu e o valor é quantas vezes apareceu.
- Tabela de decisões: a tabela do teu caderno com os dados, a coleção escolhida para cada um e porquê.

## O que precisas

- O Python 3 e o VS Code, os dos laboratórios anteriores. Para confirmares o Python, abre o terminal do VS Code, no menu Terminal, com a opção New Terminal. Escreve `python --version`, com o teu comando: `python`, `py` no Windows ou `python3` no macOS. Deve aparecer uma linha como `Python 3.14.0`, com o 3 no início.
- A pasta `fp-python`, a dos laboratórios anteriores. Se não a tiveres, cria-a como diz "Preparar o projeto".
- O caderno, para a tabela de decisões.

Os resultados e as mensagens de erro deste laboratório são os do Python 3.14. Num Python mais antigo, uma mensagem pode ter outras palavras, ou apontar outra coluna da linha. O tipo de erro, a palavra antes dos dois pontos, é o mesmo. O caminho do ficheiro que aparece nas mensagens, a seguir a `File`, muda de computador para computador.

## Se alguma coisa falhar

1. Guardaste o ficheiro? O Python corre o que está guardado no disco. Guarda com Ctrl+S, ou Cmd+S no macOS. Uma bola cheia no separador do ficheiro, no lugar do X, quer dizer que há alterações por guardar.
2. Estás na pasta certa? No terminal, o texto antes do cursor tem de ter `fp-python` no fim. Se não tiver, abre um terminal novo, no menu Terminal, com a opção New Terminal.
3. Estás na consola do Python sem quereres? Se a linha começa por `>>>`, escreve `exit()` e carrega em Enter, para voltares ao terminal.
4. O programa não volta ao terminal? Pode estar à espera que escrevas um código ou um género. Lê a última linha do terminal, escreve e carrega em Enter.
5. Copiaste o código à mão? Confirma as vírgulas entre os elementos e entre os pares, e os parênteses e as chavetas que fecham. Confirma também os dois pontos no fim das linhas do `for`, do `if` e do `else`.

## Preparar o projeto

1. Abre a pasta `fp-python` no VS Code. No menu File, escolhe Open Folder..., isto é, "abrir pasta", e escolhe `fp-python`. Se ainda não tens a pasta, cria-a primeiro no sítio onde guardas os trabalhos, por exemplo em Documentos. O que deves ver: à esquerda, no painel Explorer, o nome `FP-PYTHON`, com os ficheiros que já lá estiverem.

2. No caderno, faz uma tabela com três colunas, com estes títulos: "Os dados", "A coleção" e "Porquê". É a tua tabela de decisões. Em cada paragem em que escolheres uma coleção, acrescentas-lhe uma linha.

## Fase 1: O catálogo numa lista de tuplos

O catálogo tem sete jogos, e cada jogo tem quatro dados que andam sempre juntos: o código, o título, o género e o ano. Se cada dado ficasse numa lista própria, bastava tirar um título e esquecer o ano. Cada jogo seguinte passava a ter o ano do anterior. Para guardar um grupo de valores que andam juntos, o Python tem o tuplo. Escreve-se com os valores entre parênteses curvos, separados por vírgulas. É imutável, como os textos: depois de criado, não muda.

Para usar os valores de um tuplo, dá-se um nome a cada um, numa só linha: `codigo, titulo, genero, ano = jogo`. O primeiro valor vai para a primeira variável, o segundo para a segunda, e assim por diante. Chama-se desempacotar. Funciona também no `for`, quando cada elemento da lista é um tuplo. Para saber mais, lê a secção "Tuplos: valores que andam juntos" do [guia](08-tuplos-dicionarios-e-conjuntos.md).

1. Começa na consola, para veres um tuplo de perto. No terminal, escreve o teu comando do Python, sem mais nada, e carrega em Enter. Escreve estas linhas, uma de cada vez. Antes de cada Enter, prevê o que aparece.

   ```text
   >>> jogo = ("PLA-02", "Celeste", "plataformas", 2018)
   >>> jogo[1]
   'Celeste'
   >>> len(jogo)
   4
   >>> codigo, titulo, genero, ano = jogo
   >>> titulo
   'Celeste'
   ```

   O que deves ver: os resultados acima. O tuplo tem índices, como uma lista, e o `len` conta os quatro valores. A linha do desempacotar não mostra nada, mas dá um nome a cada valor.

2. Provoca um erro de propósito: tenta mudar o ano do jogo.

   ```text
   >>> jogo[3] = 2019
   ```

   O que deves ver: uma mensagem que acaba nesta linha:

   ```text
   TypeError: 'tuple' object does not support item assignment
   ```

   Quer dizer "erro de tipo: um objeto `tuple` não aceita que se dê um valor a um elemento". O tuplo protege o grupo: o ano não muda por engano. Sai da consola com `exit()` e Enter.

3. Cria o ficheiro `catalogo_lista.py`. No painel Explorer, passa o rato por cima de `FP-PYTHON` e carrega no ícone New File..., o primeiro dos quatro que aparecem. Escreve o nome e carrega em Enter. Cria-o com este conteúdo:

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

   Leitura guiada: começa pela lista. Uma lista comprida pode escrever-se com um elemento por linha, e o parêntese reto que a fecha fica sozinho na última. Cada elemento é um tuplo com os quatro dados de um jogo. Depois vem a procura, com o padrão da bandeira e do `break` do tema 05. Em cada volta do `for`, o tuplo desempacota-se nas quatro variáveis. Quando o código é o procurado, o programa mostra o jogo, levanta a bandeira e sai do ciclo. O `if not encontrado` só escreve quando o ciclo acabou sem encontrar o código.

4. Guarda. Antes de correres, prevê o que aparece com cada um destes códigos: `PLA-02`, ` des-01` e `PLA-09`. Depois corre o programa três vezes, com o teu comando, como `python catalogo_lista.py`, uma vez com cada código. O que deves ver, em cada vez:

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

5. Provoca um erro de propósito: na linha do `for`, apaga o `, ano`, para ficar `for codigo, titulo, genero in jogos:`. Guarda e corre com `PLA-02`. O que deves ver:

   ```text
   Código do jogo? PLA-02
   Traceback (most recent call last):
     File "C:\Users\aluno\Documents\fp-python\catalogo_lista.py", line 15, in <module>
       for codigo, titulo, genero in jogos:
           ^^^^^^^^^^^^^^^^^^^^^^
   ValueError: too many values to unpack (expected 3, got 4)
   ```

   Quer dizer "erro de valor: valores a mais para desempacotar; esperavam-se 3 e vieram 4". Cada tuplo tem quatro valores, e só havia três variáveis para os receber. Volta a pôr o `, ano`, guarda e corre outra vez.

### Paragem 1

O `catalogo_lista.py` procura um jogo pelo código, percorrendo a lista.

Pensa antes de continuares: com o código `AVE-01`, o último da lista, quantas voltas dá o ciclo? E com `PLA-09`? A resposta: 7 nos dois casos. Com `AVE-01`, o jogo só aparece na sétima volta. Com `PLA-09`, o ciclo percorre a lista toda sem o encontrar. Um catálogo com mil jogos podia obrigar a mil comparações.

Acrescenta à tua tabela de decisões:

| Os dados | A coleção | Porquê |
| --- | --- | --- |
| O código, o título, o género e o ano de um jogo | tuplo | é um grupo fixo de valores que descrevem um só jogo e não mudam |

## Fase 2: O mesmo catálogo num dicionário

No dia a dia, procuramos muitas coisas por um nome, e não por uma posição. Num dicionário de português, procuras a palavra e lês o significado. Na lista de contactos do telemóvel, procuras o nome e lês o número. O clube procura cada jogo pelo código.

No Python, há uma coleção feita para isto: o dicionário. Guarda pares. Cada par tem uma chave, que é o que se procura, e um valor, que é o que se encontra. Escreve-se entre chavetas, com cada par na forma `chave: valor`. Aqui, as chavetas não estão numa f-string: abrem e fecham o dicionário. Lê-se um valor com a chave entre parênteses retos, como `catalogo["PLA-02"]`, sem ciclo nenhum. Cada chave aparece uma só vez. Para saber mais, lê a secção "Dicionários: procurar por chave" do [guia](08-tuplos-dicionarios-e-conjuntos.md).

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

   Leitura guiada: o catálogo tem um par por linha. A chave é o código, e o valor é um tuplo com os outros três dados. Entre dois pares há uma vírgula, e só o último não a leva. A procura não tem ciclo. O `in` pergunta se o código é uma chave do dicionário. Se for, `catalogo[codigo]` dá o tuplo desse jogo, que se desempacota em três variáveis. Se não for, o `else` escreve a mensagem. O `in` de um dicionário só pergunta pelas chaves, e nunca pelos valores.

2. Guarda. Antes de correres, prevê o que aparece com `PLA-02`, ` des-01` e `PLA-09`. Depois corre `catalogo.py` três vezes, uma com cada código. O que deves ver: exatamente as mesmas três respostas da fase 1. Isto quer dizer que as duas representações respondem ao mesmo, de maneiras diferentes.

3. Provoca um erro de propósito: tira a pergunta do `in`. Substitui as cinco linhas do `if` e do `else` por estas duas, encostadas à margem:

   ```python
   titulo, genero, ano = catalogo[codigo]
   print(f"{titulo}, {genero}, {ano}")
   ```

   Guarda e corre com `PLA-09`. O que deves ver:

   ```text
   Código do jogo? PLA-09
   Traceback (most recent call last):
     File "C:\Users\aluno\Documents\fp-python\catalogo.py", line 14, in <module>
       titulo, genero, ano = catalogo[codigo]
                             ~~~~~~~~^^^^^^^^
   KeyError: 'PLA-09'
   ```

   `KeyError` quer dizer "erro de chave", e a seguir vem a chave que não existe. É o erro de procurar num dicionário uma chave que lá não está. Numa lista, o erro parecido é o `IndexError`, de um índice que não existe. Volta a pôr as cinco linhas do `if` e do `else` do passo 1, guarda e corre com `PLA-09`, para confirmares a mensagem.

4. Compara os dois ficheiros. Abre `catalogo_lista.py` e `catalogo.py` lado a lado e conta as linhas da procura em cada um, a partir da linha do `input`, inclusive. No `catalogo_lista.py` são dez, com um ciclo, uma bandeira e um `break`. No `catalogo.py` são seis, sem ciclo.

### Paragem 2

O `catalogo.py` procura um jogo pela chave, sem ciclo, e não para com um código que não existe.

Pensa antes de continuares: com mil jogos no catálogo, qual dos dois programas encontra mais depressa o último jogo, e porquê? A resposta: o do dicionário. A lista compara o código com cada jogo, um a um, até o encontrar. O dicionário vai diretamente à chave, e o tamanho do catálogo quase não conta.

Acrescenta à tua tabela de decisões:

| Os dados | A coleção | Porquê |
| --- | --- | --- |
| O catálogo, procurado pelo código | dicionário, do código para o tuplo do jogo | procura-se pelo código, e não pela posição; cada código existe uma só vez |

## Fase 3: Percorrer o dicionário

O clube quer que o programa mostre o catálogo inteiro antes de perguntar um código. Para isso, é preciso passar por todos os pares do dicionário.

Um `for` sobre um dicionário dá só as chaves. Para ter a chave e o valor em cada volta, usa-se o método `items`, que quer dizer "itens". Em cada volta, dá um tuplo com a chave e o valor, que se desempacota nas duas variáveis do `for`. Os pares saem pela ordem em que foram escritos. Para ter só os valores, sem as chaves, há o método `values`, que quer dizer "valores", e que vais usar na fase 4. Para saber mais, lê a secção "Percorrer um dicionário" do [guia](08-tuplos-dicionarios-e-conjuntos.md).

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

### Paragem 3

O `catalogo.py` mostra o catálogo inteiro e procura um jogo pelo código.

Pensa antes de continuares: se escrevesses `for jogo in catalogo:`, sem o `items`, o que ficava em `jogo` em cada volta? A resposta: o código, a chave, e não o tuplo. Um texto também se desempacota, um carácter por variável. A linha `titulo, genero, ano = jogo` tentava pôr os seis caracteres do código em três variáveis, e o programa parava com `ValueError: too many values to unpack (expected 3)`.

## Fase 4: Uma lista que cresce: os jogos de um género

Agora o programa pergunta um género e mostra os títulos desse género. Não se sabe quantos são: podem ser dois, um ou nenhum. A lista dos títulos tem de começar vazia e crescer à medida que se encontram jogos do género.

É o que já sabes das listas: uma lista vazia escreve-se `[]`, e o método `append` acrescenta um elemento no fim, mudando a própria lista. Para percorrer os jogos, usa-se o `values` da fase 3, que dá só os valores do dicionário, os tuplos. Para saber mais, lê a secção "Percorrer um dicionário" do [guia](08-tuplos-dicionarios-e-conjuntos.md).

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

### Paragem 4

O `catalogo.py` junta numa lista os jogos do género pedido e trata o caso de não haver nenhum.

Pensa antes de continuares: porque é que os títulos de um género se guardam numa lista, e não num tuplo? A resposta: porque o número de títulos não se sabe à partida, e a lista cresce com o `append`. Um tuplo não muda depois de criado, e não podia receber os títulos um a um.

Acrescenta à tua tabela de decisões:

| Os dados | A coleção | Porquê |
| --- | --- | --- |
| Os títulos do género pedido | lista, que começa vazia | não se sabe quantos são, e a lista cresce um a um; pode ficar vazia |

## Fase 5: Os géneros sem repetidos, com um conjunto

O clube quer saber que géneros há no catálogo. Há sete jogos, mas os géneros repetem-se: há dois de plataformas e dois de desporto. Numa lista de géneros, `plataformas` aparecia duas vezes.

Para isto há o conjunto: uma coleção sem repetidos e sem ordem. Cria-se vazio com `set()`, e acrescenta-se um valor com o método `add`. Se o valor já lá estiver, nada muda: cada valor fica uma só vez. Para saber mais, lê a secção "Conjuntos: valores sem repetidos" do [guia](08-tuplos-dicionarios-e-conjuntos.md).

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

   A ordem dos géneros é provavelmente diferente nas duas vezes. Um conjunto não guarda a ordem, e o Python pode mostrá-lo de cada vez por outra ordem. As chavetas, aqui, são a forma de o Python escrever um conjunto. Se a ordem sair igual nas duas vezes, corre uma terceira.

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

   Quer dizer "erro de atributo: um objeto `dict` não tem `add`". Um atributo é o que se escreve depois do ponto, como o nome de um método. As chavetas vazias não são um conjunto vazio, são um dicionário vazio. Os dicionários não têm `add`, porque guardam pares, e não valores soltos. Volta a pôr `generos = set()`, guarda e corre outra vez.

### Paragem 5

O `catalogo.py` mostra os géneros do catálogo, cada um uma vez e por ordem.

Pensa antes de continuares: o conjunto dos géneros podia substituir o catálogo inteiro? A resposta: não. O conjunto diz que géneros há, e mais nada. Perdeu quantos jogos há de cada género, os títulos e a ordem. Um conjunto serve quando a pergunta é "que valores há, cada um uma vez", e não quando os repetidos contam.

Acrescenta à tua tabela de decisões:

| Os dados | A coleção | Porquê |
| --- | --- | --- |
| Os géneros que há no catálogo | conjunto | cada género conta uma só vez, e a ordem não interessa; para mostrar, ordena-se com `sorted` |

## Fase 6: Quantos jogos tem cada género

Por fim, o clube quer saber quantos jogos tem de cada género. Aqui os repetidos contam: os dois jogos de plataformas têm de dar 2. Um conjunto não serve, porque deita fora as repetições.

Conta-se com um dicionário. Cada género é uma chave, e o valor é o seu contador. Para cada jogo, há dois casos. Se o género já é uma chave, soma-se 1 ao seu contador. Se ainda não é, é o primeiro jogo desse género, e o género entra com o contador a 1. O dicionário começa vazio, com `{}`. Para saber mais, lê a secção "Contar com um dicionário" do [guia](08-tuplos-dicionarios-e-conjuntos.md).

1. Em `catalogo.py`, acrescenta estas linhas no fim do ficheiro, encostadas à margem:

   ```python
   print()

   jogos_por_genero = {}
   for jogo in catalogo.values():
       genero = jogo[1]
       if genero in jogos_por_genero:
           jogos_por_genero[genero] = jogos_por_genero[genero] + 1
       else:
           # Primeiro jogo deste género: o contador nasce a 1.
           jogos_por_genero[genero] = 1
   for genero in sorted(jogos_por_genero):
       print(f"{genero}: {jogos_por_genero[genero]}")
   ```

   Leitura guiada: o dicionário das contagens nasce vazio, antes do ciclo. Repara que aqui as chavetas vazias estão certas, porque se quer mesmo um dicionário. Em cada volta, o `if` pergunta se o género já tem contador, e soma 1 ou cria-o com 1. O último `for` percorre as chaves por ordem alfabética, com o `sorted`, e lê o contador de cada uma com `jogos_por_genero[genero]`.

2. Guarda. Antes de correres, conta à mão quantos jogos há de cada género, no catálogo do teu `catalogo.py`. Depois corre o programa com `PLA-02` e `puzzle`. O que deves ver, no fim do ecrã:

   ```text
   aventura: 1
   corridas: 1
   desporto: 2
   plataformas: 2
   puzzle: 1
   ```

3. Segue as quatro primeiras voltas no caderno. Os jogos saem pela ordem do catálogo:

   | Volta | `genero` | Já é chave? | `jogos_por_genero` depois da volta |
   | ---: | --- | --- | --- |
   | 1 | plataformas | não | `{'plataformas': 1}` |
   | 2 | plataformas | sim | `{'plataformas': 2}` |
   | 3 | corridas | não | `{'plataformas': 2, 'corridas': 1}` |
   | 4 | desporto | não | `{'plataformas': 2, 'corridas': 1, 'desporto': 1}` |

   Continua a tabela até à volta 7, e confirma que acaba com os cinco pares do ecrã.

4. Por fim, atualiza o comentário do início, porque o programa passou a fazer mais coisas. Substitui as duas primeiras linhas do ficheiro por estas três:

   ```python
   # catalogo.py: o catálogo do clube de videojogos, num dicionário.
   # Mostra o catálogo, procura um jogo pelo código, junta os jogos de um género,
   # diz que géneros há, sem repetidos, e quantos jogos tem cada género.
   ```

### Paragem 6

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

aventura: 1
corridas: 1
desporto: 2
plataformas: 2
puzzle: 1
```

Confere também o teu ficheiro com este:

```python
# catalogo.py: o catálogo do clube de videojogos, num dicionário.
# Mostra o catálogo, procura um jogo pelo código, junta os jogos de um género,
# diz que géneros há, sem repetidos, e quantos jogos tem cada género.
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
print()

jogos_por_genero = {}
for jogo in catalogo.values():
    genero = jogo[1]
    if genero in jogos_por_genero:
        jogos_por_genero[genero] = jogos_por_genero[genero] + 1
    else:
        # Primeiro jogo deste género: o contador nasce a 1.
        jogos_por_genero[genero] = 1
for genero in sorted(jogos_por_genero):
    print(f"{genero}: {jogos_por_genero[genero]}")
```

Pensa antes de continuares: agora que tens o dicionário das contagens, ainda precisavas do conjunto dos géneros? A resposta: para saber quantos géneros há, não. As chaves de um dicionário não se repetem, e `len(jogos_por_genero)` também dá 5. O conjunto responde só a "que géneros há?", e di-lo de forma mais direta. O dicionário responde também a "quantos de cada?". Escolhe-se a coleção que responde à pergunta que se faz.

Acrescenta à tua tabela de decisões:

| Os dados | A coleção | Porquê |
| --- | --- | --- |
| Quantos jogos tem cada género | dicionário, do género para o número de jogos | procura-se o contador pelo género, e cada género é uma chave só uma vez |

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

### A ordem dos géneros muda de cada vez que corres

Estás a mostrar o conjunto diretamente, com `print(generos)`. Um conjunto não tem ordem. Usa `print(sorted(generos))`.

### Só aparece um género, com o contador a 1

A linha `jogos_por_genero = {}` ficou dentro do ciclo, e o dicionário volta a nascer vazio em cada volta. No fim, fica só o último jogo do catálogo, o Minecraft, de aventura. Põe essa linha antes do `for`, encostada à margem, como um contador que nasce a 0 antes do ciclo.

## Desafios

1. Os jogos de cada década. Em `catalogo.py`, acrescenta no fim uma parte que conta quantos jogos há de cada década, como `Anos 2010: 3`. Mostra as décadas por ordem. Antes de correres, conta à mão. Pista: a década de um ano calcula-se com a divisão inteira e uma multiplicação.

2. Acrescentar um jogo. Faz um programa novo, `acrescentar_jogo.py`, com o mesmo catálogo. O programa pede o código, o título, o género e o ano de um jogo novo, e acrescenta-o ao catálogo. Se o código já existir, o programa não pode apagar o jogo que lá está. Nesse caso, diz de que jogo é o código e não acrescenta nada. No fim, mostra quantos jogos tem o catálogo. Testa com `PUZ-02`, Portal 2, puzzle, 2011, e depois com `PLA-02`. Pista: dar um valor a uma chave que já existe substitui o valor antigo.

3. Corrigir o ano de um jogo. Faz um programa novo, `corrigir_ano.py`, com o mesmo catálogo. O programa pede o código de um jogo e o ano certo, e muda o ano desse jogo no catálogo. Se o código não existir, diz-o. No fim, mostra o jogo como ficou. Testa com `PUZ-01` e `1985`, e depois com `PUZ-09`. Pista: o dicionário muda, mas o tuplo de cada jogo não.

## Antes de terminares

- [ ] O `catalogo_lista.py` e o `catalogo.py` dão a mesma resposta com `PLA-02`, ` des-01` e `PLA-09`.
- [ ] O `catalogo.py` mostra o catálogo, os jogos de `puzzle`, de ` Desporto` e de `luta`, os cinco géneros por ordem e os jogos de cada género.
- [ ] A tua tabela de decisões tem as cinco linhas das paragens 1, 2, 4, 5 e 6.
- [ ] Sabes dizer de que tipo foi cada erro que provocaste: de sintaxe, de execução ou de lógica.
- [ ] Consegues explicar, por palavras tuas, porque é que o catálogo ficou num dicionário e os géneros num conjunto. E porque é que um conjunto não pode substituir sempre uma lista.

![Rodapé](../imagens/rodape.png)
