![Cabeçalho](../../imagens/cabecalho.png)

# Laboratório: Tuplos, dicionários e conjuntos

## O que vais construir

Vais construir o programa do catálogo do clube de videojogos. O `catalogo_lista.py` procura um jogo pelo código, numa lista. O `catalogo.py` faz a mesma procura num dicionário, junta os jogos de um género, diz que géneros há e quantos jogos tem cada um.

No fim, o ecrã do `catalogo.py` fica assim, com o que a pessoa escreveu a seguir a cada pergunta:

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

1. [Fase 1: Um tuplo guarda valores que andam juntos](#fase-1-um-tuplo-guarda-valores-que-andam-juntos)
2. [Fase 2: Um dicionário procura por chave](#fase-2-um-dicionário-procura-por-chave)
3. [Fase 3: Percorrer um dicionário com `items` e `values`](#fase-3-percorrer-um-dicionário-com-items-e-values)
4. [Fase 4: A coleção vazia é sempre um caso de teste](#fase-4-a-coleção-vazia-é-sempre-um-caso-de-teste)
5. [Fase 5: Um conjunto guarda valores sem repetidos](#fase-5-um-conjunto-guarda-valores-sem-repetidos)
6. [Fase 6: Contar com um dicionário](#fase-6-contar-com-um-dicionário)

## O que precisas

- A pasta `fp-python`, aberta no VS Code, e um terminal, que se abre no menu Terminal, com a opção New Terminal. Se não a tiveres, faz primeiro [Preparar o projeto](01-do-pseudocodigo-ao-python-laboratorio.md#preparar-o-projeto), no laboratório do tema 01.
- O comando que corre o Python no teu computador, `python`, `py` ou `python3`. Onde o texto diz `python`, usa o teu.

## Fase 1: Um tuplo guarda valores que andam juntos

Guardas o catálogo numa lista de tuplos e procuras um jogo pelo código. Os quatro dados de cada jogo ficam juntos. Rever: [Um tuplo guarda valores que andam juntos](../08-tuplos-dicionarios-e-conjuntos.md#um-tuplo-guarda-valores-que-andam-juntos).

1. No terminal, abre a consola do Python, com o teu comando, sem mais nada. Escreve estas linhas e confirma os resultados:

   ```text
   >>> jogo = ("PLA-02", "Celeste", "plataformas", 2018)
   >>> jogo[1]
   'Celeste'
   >>> codigo, titulo, genero, ano = jogo
   >>> titulo
   'Celeste'
   ```

2. Provoca um erro: escreve `jogo[3] = 2019`. O que deves ver no fim da mensagem: `TypeError: 'tuple' object does not support item assignment`. Sai da consola com `exit()` e Enter.

3. No painel Explorer, cria um ficheiro novo, com o nome `catalogo_lista.py`, e escreve nele:

   ```python
   # catalogo_lista.py: o catálogo do clube de videojogos, numa lista de tuplos.
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
   # Em cada volta, o tuplo do jogo desempacota-se nas quatro variáveis.
   for codigo, titulo, genero, ano in jogos:
       if codigo == procura:
           print(f"{titulo}, {genero}, {ano}")
           encontrado = True
           # Depois de encontrar o jogo, o resto da lista já não interessa.
           break
   if not encontrado:
       print(f"Não há nenhum jogo com o código {procura}.")
   ```

4. Guarda e corre três vezes, com `PLA-02`, ` des-01`, com um espaço antes, e `PLA-09`:

   ```bash
   python catalogo_lista.py
   ```

   O que deves ver depois de cada pergunta: `Celeste, plataformas, 2018`, `Rocket League, desporto, 2015` e `Não há nenhum jogo com o código PLA-09.`. Se aparecer outra coisa, vê [Se alguma coisa falhar](#se-alguma-coisa-falhar).

5. Provoca um erro: na linha do `for`, apaga o `, ano`. Guarda e corre com `PLA-02`. O que deves ver:

   ```text
   Código do jogo? PLA-02
   Traceback (most recent call last):
     File "C:\Users\aluno\Documents\fp-python\catalogo_lista.py", line 15, in <module>
       for codigo, titulo, genero in jogos:
           ^^^^^^^^^^^^^^^^^^^^^^
   ValueError: too many values to unpack (expected 3, got 4)
   ```

   Cada tuplo tem quatro valores, e só havia três variáveis. Volta a pôr o `, ano` e guarda.

### Paragem 1

O `catalogo_lista.py` procura um jogo pelo código, percorrendo a lista.

Pensa antes de continuares: com o código `AVE-01`, o último da lista, quantas voltas dá o ciclo? E com `PLA-09`? A resposta: 7 nos dois casos.

## Fase 2: Um dicionário procura por chave

Guardas o mesmo catálogo num dicionário, com o código como chave. A procura deixa de precisar de um ciclo. Rever: [Um dicionário procura por chave](../08-tuplos-dicionarios-e-conjuntos.md#um-dicionário-procura-por-chave).

1. Cria o ficheiro `catalogo.py` e escreve nele:

   ```python
   # catalogo.py: o catálogo do clube de videojogos, num dicionário.
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

2. Guarda e corre três vezes, com `PLA-02`, ` des-01`, com o espaço antes, e `PLA-09`. O que deves ver: as mesmas três respostas da fase 1.

3. Provoca um erro: substitui as cinco linhas do `if` e do `else` por estas duas, encostadas à margem:

   ```python
   titulo, genero, ano = catalogo[codigo]
   print(f"{titulo}, {genero}, {ano}")
   ```

   Guarda e corre com `PLA-09`. O que deves ver:

   ```text
   Código do jogo? PLA-09
   Traceback (most recent call last):
     File "C:\Users\aluno\Documents\fp-python\catalogo.py", line 13, in <module>
       titulo, genero, ano = catalogo[codigo]
                             ~~~~~~~~^^^^^^^^
   KeyError: 'PLA-09'
   ```

   Volta a pôr as cinco linhas do `if` e do `else`, guarda e corre com `PLA-09`.

4. Compara os dois ficheiros e conta as linhas da procura, a partir da linha do `input`. O que deves ver: contando os comentários, são onze linhas na lista, com ciclo, bandeira e `break`, e seis no dicionário, sem ciclo.

### Paragem 2

O `catalogo.py` procura um jogo pela chave, sem ciclo, e não para com um código que não existe.

Pensa antes de continuares: e se o clube quisesse procurar pelo título, e não pelo código? A resposta: a chave teria de ser o título, porque um dicionário só procura pelas chaves.

## Fase 3: Percorrer um dicionário com `items` e `values`

O programa passa a mostrar o catálogo inteiro antes de perguntar um código. O método `items` dá a chave e o valor em cada volta. Rever: [Percorrer um dicionário com `items` e `values`](../08-tuplos-dicionarios-e-conjuntos.md#percorrer-um-dicionário-com-items-e-values).

1. Clica na linha em branco a seguir à chaveta que fecha o catálogo e carrega em Enter. Na linha nova, escreve:

   ```python
   print("Catálogo do clube:")
   for codigo, jogo in catalogo.items():
       titulo, genero, ano = jogo
       print(f"{codigo}  {titulo} ({ano})")
   print()
   ```

   No fim, carrega em Enter, para ficar uma linha em branco antes do `codigo = input(...)`.

2. Guarda e corre com `PLA-02`. O que deves ver:

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

### Paragem 3

O `catalogo.py` mostra o catálogo inteiro e procura um jogo pelo código.

Pensa antes de continuares: com `for jogo in catalogo:`, sem o `items`, o que ficava em `jogo` em cada volta? A resposta: o código, a chave, e não o tuplo.

## Fase 4: A coleção vazia é sempre um caso de teste

O programa pergunta um género e junta os títulos numa lista, que pode ficar vazia. O `values` dá só os tuplos dos jogos. Rever: [A coleção vazia é sempre um caso de teste](../08-tuplos-dicionarios-e-conjuntos.md#a-coleção-vazia-é-sempre-um-caso-de-teste).

1. No fim do ficheiro, encostadas à margem, acrescenta estas linhas:

   ```python
   print()

   genero_pedido = input("Que género procuras? ").strip().lower()
   titulos = []
   for jogo in catalogo.values():
       titulo, genero, ano = jogo
       if genero == genero_pedido:
           titulos.append(titulo)
   # Com a lista vazia, o ciclo de baixo não escrevia nenhum título.
   if len(titulos) == 0:
       print(f"Não há jogos do género {genero_pedido}.")
   else:
       print(f"Jogos de {genero_pedido}: {len(titulos)}")
       for titulo in titulos:
           print("-", titulo)
   ```

2. Guarda e corre três vezes, com `PLA-02` e os géneros `puzzle`, ` Desporto`, com um espaço antes, e `luta`. O que deves ver no fim do ecrã, em cada vez:

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

3. Provoca um erro: apaga a linha `titulos = []`. Guarda e corre com `PLA-02` e `puzzle`. O que deves ver no fim da mensagem: `NameError: name 'titulos' is not defined. Did you mean: 'titulo'?`. A sugestão engana-se, porque a causa é a linha que falta. Volta a pôr a linha e guarda.

### Paragem 4

O `catalogo.py` junta os jogos do género pedido e trata o caso de não haver nenhum.

Pensa antes de continuares: porque é que os títulos de um género não se guardam num tuplo? A resposta: não se sabe quantos são, e um tuplo não pode receber valores um a um.

## Fase 5: Um conjunto guarda valores sem repetidos

Os géneros repetem-se no catálogo, e o clube quer cada um uma só vez. Um conjunto fica só com um de cada. Rever: [Um conjunto guarda valores sem repetidos](../08-tuplos-dicionarios-e-conjuntos.md#um-conjunto-guarda-valores-sem-repetidos).

1. No fim do ficheiro, também encostadas à margem, acrescenta estas linhas:

   ```python
   print()

   generos = set()
   for jogo in catalogo.values():
       # O conjunto ignora um género que já lá esteja: cada um fica uma só vez.
       generos.add(jogo[1])
   print(f"{len(catalogo)} jogos, {len(generos)} géneros diferentes")
   print(generos)
   ```

2. Guarda e corre duas vezes, com `PLA-02` e `puzzle`. O que deves ver no fim: as duas vezes, `7 jogos, 5 géneros diferentes`, e por baixo os cinco géneros, entre chavetas, provavelmente por ordem diferente.

3. Substitui a última linha, `print(generos)`, por esta:

   ```python
   print(sorted(generos))
   ```

   Guarda e corre duas vezes. O que deves ver: as duas vezes, `['aventura', 'corridas', 'desporto', 'plataformas', 'puzzle']`.

4. Provoca um erro: muda `generos = set()` para `generos = {}`. Guarda e corre. O que deves ver no fim da mensagem: `AttributeError: 'dict' object has no attribute 'add'`. Volta a pôr `generos = set()` e guarda.

### Paragem 5

O `catalogo.py` mostra os géneros do catálogo, cada um uma vez e por ordem.

Pensa antes de continuares: o conjunto dos géneros podia substituir o catálogo? A resposta: não, porque só diz que géneros há. Não tem os títulos nem quantos jogos há de cada género.

## Fase 6: Contar com um dicionário

Agora os repetidos contam: os dois jogos de plataformas têm de dar 2. Cada género é uma chave, e o valor é o seu contador. Rever: [Contar com um dicionário](../08-tuplos-dicionarios-e-conjuntos.md#contar-com-um-dicionário).

1. Outra vez no fim do ficheiro, encostadas à margem, acrescenta:

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

2. Conta à mão quantos jogos há de cada género. Guarda e corre com `pla-02` e `puzzle`. O que deves ver: o ecrã de "O que vais construir".

### Paragem 6

O `catalogo.py` está completo.

O ficheiro `catalogo.py` completo, como deve estar no fim:

```python
# catalogo.py: o catálogo do clube de videojogos, num dicionário.
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
# Com a lista vazia, o ciclo de baixo não escrevia nenhum título.
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

A tabela de decisões deste programa:

| Os dados | A coleção | Porquê |
| --- | --- | --- |
| Os dados de um jogo | tuplo | um grupo fixo de valores que descrevem um só jogo |
| O catálogo | dicionário | procura-se pelo código, e cada código existe uma só vez |
| Os títulos do género pedido | lista | não se sabe quantos são, e a lista cresce um a um |
| Os géneros do catálogo | conjunto | cada género conta uma só vez |
| Quantos jogos tem cada género | dicionário | procura-se o contador pelo género |

Pensa antes de continuares: agora que tens o dicionário das contagens, ainda precisavas do conjunto? A resposta: para saber quantos géneros há, não, porque `len(jogos_por_genero)` também dá 5. Escolhe-se a coleção que responde à pergunta que se faz.

## Se alguma coisa falhar

1. Guardaste o ficheiro? O Python corre o que está no disco, e não o que vês no ecrã.
2. Estás na pasta certa? No terminal, o texto antes do cursor tem de ter `fp-python` no fim, antes do `>` ou do `%`.
3. Estás na consola do Python sem quereres? Se a linha começa por `>>>`, escreve `exit()` e carrega em Enter.
4. O programa não volta ao terminal? Pode estar à espera de um código ou de um género.

### `SyntaxError: '{' was never closed` ou `'[' was never closed`

Falta a chaveta que fecha o dicionário, ou o parêntese reto que fecha a lista.

### `SyntaxError: invalid syntax. Perhaps you forgot a comma?` numa linha do dicionário

Falta a vírgula no fim da linha que a mensagem mostra. Entre dois pares tem de haver uma vírgula.

### `TypeError: 'tuple' object is not callable` numa linha da lista

Falta uma vírgula entre dois tuplos da lista, no fim da primeira das duas linhas que a mensagem mostra.

### Um código que existe não é encontrado

O código foi escrito noutra forma e não foi arrumado. Confirma que a linha do `input` acaba em `.strip().upper()`.

### O programa diz que não há jogos de um género que existe

Confirma que a linha do `input` do género acaba em `.strip().lower()`, porque os géneros do catálogo estão em minúsculas.

### `ValueError: too many values to unpack` ou `not enough values to unpack`

O número de variáveis não é igual ao número de valores do tuplo. Cada tuplo do `catalogo_lista.py` tem quatro valores, e cada tuplo do `catalogo.py` tem três.

### Só aparece um género, com o contador a 1

A linha `jogos_por_genero = {}` ficou dentro do ciclo. Põe-na antes do `for`, encostada à margem.

## Desafios

Faz cada desafio num ficheiro novo, com o catálogo copiado para lá.

1. Conta quantos jogos há de cada década, como `Anos 2010: 3`, e mostra as décadas por ordem. Pista: a década de um ano calcula-se com a divisão inteira e uma multiplicação.
2. Faz o programa `acrescentar_jogo.py`, que pede o código, o título, o género e o ano de um jogo novo e o acrescenta ao catálogo. Se o código já existir, diz de que jogo é, não pede o resto e não acrescenta nada. No fim, mostra quantos jogos tem o catálogo. Testa com `PUZ-02`, Portal 2, puzzle, 2011, e depois com `PLA-02`.
3. Faz o programa `corrigir_ano.py`, que pede o código de um jogo e o ano certo, e muda o ano desse jogo no catálogo. Se o código não existir, diz-o e não pede o ano. Se existir, no fim mostra o jogo como ficou. Testa com `PUZ-01` e `1985`, e depois com `PUZ-09`. Pista: o dicionário muda, mas o tuplo de cada jogo não.

## Antes de terminares

- [ ] O `catalogo_lista.py` e o `catalogo.py` dão a mesma resposta com `PLA-02`, ` des-01` e `PLA-09`.
- [ ] O `catalogo.py` dá os resultados de `puzzle`, ` Desporto` e `luta`, e mostra o ecrã de "O que vais construir".

![Rodapé](../../imagens/rodape.png)
