![Cabeçalho](../imagens/cabecalho.png)

# Ficha de exercícios: Coleções, strings e escolha de representação

Ficha do tema Coleções, strings e escolha de representação, do módulo Criar aplicações em linguagem de programação Python. Praticas os textos, as listas, os tuplos, os dicionários e os conjuntos. Praticas também a escolha da coleção que serve cada problema. Fazes sozinho, ao teu ritmo: o que não acabares na aula, acabas em casa ou na aula seguinte.

## O que precisas de saber

O [guia do tema](02-colecoes-strings-e-representacao.md) e o [laboratório](02-colecoes-strings-e-representacao-laboratorio.md).

## Como trabalhar

Os exercícios 1 a 8 são obrigatórios e fazem-se por esta ordem, porque cada um usa o que os anteriores treinaram. Cada um precisa das secções do guia que estão entre parênteses:

1. Exercício 1 (até "Conjuntos: valores sem repetidos").
2. Exercício 2 ("Fatias de um texto" e "Juntar textos e valores com f-strings").
3. Exercício 3 ("Listas que crescem e encolhem" e "Funções predefinidas para listas").
4. Exercício 4 ("Tuplos: valores que andam juntos").
5. Exercício 5 ("Os métodos dos textos" e "Dicionários: procurar por chave").
6. Exercício 6 ("Conjuntos: valores sem repetidos").
7. Exercício 7 (o guia todo, e a rotina para procurar um erro do guia 01).
8. Exercício 8 ("Contar com um dicionário" e "Escolher a representação").

O desafio opcional e a secção "Para ires mais longe" são para quem acabar os obrigatórios.

Guarda os teus scripts na pasta `fp-python`, com os nomes que cada exercício indica. As tabelas e as respostas escritas ficam no caderno. Antes de correres um script, escreve sempre o resultado que esperas, calculado à mão a partir do enunciado. Nas mensagens, usa f-strings ou o `print` com vírgulas, como preferires, desde que o ecrã fique como o enunciado mostra.

## Exercício 1: Prever o estado das coleções

Abre a consola do Python, com `python`, ou `python3` no macOS. Vais escrever as linhas abaixo, por esta ordem. Antes de cada linha marcada com uma letra, escreve no caderno o que esperas que a consola mostre. Só depois a escreves e confirmas. As linhas sem letra não mostram nada, mas mudam as coleções.

```text
mochila = ["corda", "lanterna"]
mochila.append("mapa")
a) mochila
mochila.remove("corda")
b) mochila
c) len(mochila)
nome = "Ana Sofia"
d) nome[4:]
e) nome[:3].upper()
f) nome
g) nome.split()
idades = {"Rui": 15, "Bia": 16}
idades["Rui"] = 16
idades["Eva"] = 14
h) idades
i) "Ana" in idades
cores = {"azul", "verde", "azul"}
j) len(cores)
cores.add("verde")
k) len(cores)
```

Na consola, não escrevas a letra nem o parêntese: escreve só o que vem a seguir, como `mochila`.

Para cada previsão em que te enganaste, escreve uma frase a explicar o que o Python fez.

## Exercício 2: O despertador

Um despertador mostra as horas num texto com cinco caracteres, como `"07:45"`: dois algarismos das horas, os dois pontos e dois algarismos dos minutos. Escreve o script `despertador.py`, que lê uma hora nesta forma e diz quantos minutos passaram desde a meia-noite. O ecrã fica assim:

```text
Hora do despertador (hh:mm)? 07:45
07:45 são 465 minutos depois da meia-noite.
```

a) Antes de escreveres código, completa no caderno o resultado esperado de cada caso, calculado à mão:

| Hora | Minutos depois da meia-noite |
| --- | ---: |
| `00:00` | |
| `07:45` | 465 |
| `12:00` | |
| `23:59` | |

b) Escreve o script. Começa com um comentário que diga o que ele faz.

c) Corre o script com os quatro casos e confirma a tabela.

## Exercício 3: Os lançamentos de dardos

Num jogo de dardos, cada lançamento vale de 0 a 60 pontos. Escreve o script `dardos.py`, que lê as pontuações dos lançamentos, uma de cada vez, até a pessoa carregar em Enter sem escrever nada. No fim, mostra quantos lançamentos houve, o total de pontos, o melhor lançamento e o pior. Se não houver nenhum lançamento, escreve só "Não houve lançamentos.".

Testa o script com estas entradas. Antes de cada uma, escreve no caderno o que esperas que apareça:

| Pontuações escritas, por ordem | Lançamentos | Total | Melhor | Pior |
| --- | ---: | ---: | ---: | ---: |
| 20, 5, 60, 0 | | | | |
| 25 | | | | |

Testa também sem nenhuma pontuação, carregando logo em Enter, e escreve antes o que esperas que apareça.

## Exercício 4: O caminho até ao tesouro

Num jogo, o mapa é uma quadrícula, e cada posição é um par de números, o x e o y. O jogador só anda na horizontal e na vertical, uma casa de cada vez. O número de passos entre duas posições é a distância entre os dois x mais a distância entre os dois y, sem sinal.

Escreve o script `tesouro.py`, que começa com estas duas linhas:

```python
jogador = (2, 3)
tesouro = (7, 1)
```

O script mostra quantos passos separam o jogador do tesouro, numa linha como `Do (2, 3) ao (7, 1): 7 passos`. Dá um nome a cada um dos quatro números, numa linha por tuplo.

a) Corre o script e confirma os 7 passos. Depois, muda as duas linhas do início para testar os casos da tabela. Antes de cada um, calcula à mão:

| `jogador` | `tesouro` | Passos |
| --- | --- | ---: |
| `(7, 1)` | `(2, 3)` | |
| `(4, 4)` | `(4, 4)` | |
| `(0, 0)` | `(0, 5)` | |

b) Explica numa frase porque é que cada posição está num tuplo, e não numa lista.

c) Sem experimentar, que tipo de erro esperas com a linha `jogador[0] = 5`? Depois confirma na consola.

## Exercício 5: Os pontos das palavras

Num jogo de palavras, cada letra vale pontos. As vogais valem 1, e as letras raras valem mais. As letras que não estão na tabela valem 2. Uma palavra vale a soma dos pontos das suas letras, e as maiúsculas valem o mesmo que as minúsculas. Os pontos estão neste dicionário:

```python
pontos = {"a": 1, "e": 1, "i": 1, "o": 1, "u": 1,
          "k": 5, "w": 5, "y": 5, "j": 8, "q": 8, "x": 8, "z": 10}
```

Escreve o script `palavras.py`, que lê uma palavra e mostra quantos pontos ela vale, numa linha como `Xadrez vale 24 pontos`. A palavra aparece no ecrã tal como a pessoa a escreveu.

Antes de correres, calcula à mão os pontos de cada palavra da tabela. Depois corre o script com cada uma e confirma:

| Palavra escrita | Pontos |
| --- | ---: |
| `casa` | |
| `Xadrez` | 24 |
| `QUIZ` | |
| `k` | |

## Exercício 6: A caderneta de cromos

Uma caderneta tem 12 cromos, numerados de 1 a 12. A Joana abriu umas saquetas, e saíram-lhe estes cromos, por esta ordem:

```python
saidos = [3, 7, 3, 12, 1, 7, 7, 5]
```

Escreve o script `cromos.py`, que mostra quatro coisas:

- quantos cromos saíram;
- quantos cromos diferentes a Joana tem;
- quantas cópias a mais tem para trocar: um cromo que saiu três vezes dá duas cópias para trocar;
- que números lhe faltam para completar a caderneta.

O script tem de funcionar com qualquer lista de cromos saídos. Antes de correres, calcula à mão as quatro respostas para a lista da Joana. Depois corre e confirma. Testa também com `saidos = []` e com uma lista com os 12 números, cada um uma vez. Antes de cada caso, escreve o que esperas.

## Exercício 7: Encontrar o erro

O script `playlist.py` devia somar a duração das músicas de uma playlist. Cada duração é um texto com os minutos e os segundos, separados por dois pontos, como `"3:45"`. Tem três erros, de propósito.

```python
# playlist.py: soma a duração das músicas de uma playlist.
# Cada duração é um texto com os minutos e os segundos, como "3:45".
# Este script tem três erros, de propósito.
SEGUNDOS_POR_MINUTO = 60

playlist = {
    "Luzes da cidade": "3:45",
    "Corrida noturna" = "4:10",
    "Último nível": "2:05"
}

total = 0
for musica in playlist:
    partes = musica.split(":")
    minutos = int(partes[0])
    segundos = int(partes[0])
    total = total + minutos * SEGUNDOS_POR_MINUTO + segundos
print(f"Músicas: {len(playlist)}")
print(f"Duração total: {total // SEGUNDOS_POR_MINUTO} min {total % SEGUNDOS_POR_MINUTO} s")
```

Com estas três músicas, o script devia mostrar `Músicas: 3` e `Duração total: 10 min 0 s`.

Copia o script para o ficheiro `playlist.py` e corre-o. O Python mostra os erros um de cada vez. Para cada erro que encontrares, segue a rotina e escreve no caderno:

1. O que aconteceu, e que tipo de erro é: de sintaxe, de execução ou de lógica. Se houver uma mensagem, copia a última linha e a linha que ela aponta.
2. Numa frase, o que achas que causa o erro.
3. Como confirmaste essa frase.
4. A linha que mudaste, e como ficou. Muda o mínimo possível.
5. O que aconteceu quando voltaste a correr.

Quando o script mostrar o resultado certo, testa-o também com uma playlist de uma só música, `{"Só uma": "0:59"}`, e com a playlist vazia, `{}`. Antes de correres, escreve o que deve aparecer.

## Exercício 8: Escolher as coleções

a) Para cada situação da tabela, escolhe a coleção que usavas: lista, tuplo, dicionário ou conjunto. Justifica cada escolha com as quatro perguntas do guia: a ordem, os repetidos, a forma de procurar e se os valores mudam.

| Situação | Coleção | Porquê |
| --- | --- | --- |
| Os números que já saíram num bingo, para saber se um número já saiu | | |
| A ordem de chegada dos atletas numa corrida de 100 metros | | |
| As vidas que restam a cada personagem de um jogo, para as procurar pelo nome | | |
| O dia, o mês e o ano de uma data de nascimento | | |
| As músicas que tocaram numa festa, por ordem, com as que se repetiram | | |

b) A escola registou as inscrições nos clubes. Cada inscrição é um tuplo com o nome do aluno e o clube. Uma das inscrições foi registada duas vezes, por engano:

```python
inscricoes = [("Ana", "xadrez"), ("Rui", "teatro"), ("Ana", "teatro"),
              ("Bia", "xadrez"), ("Rui", "teatro"), ("Tomás", "robótica")]
```

Escreve o script `inscricoes.py`, que mostra:

- quantos alunos diferentes se inscreveram;
- quantos inscritos tem cada clube, sem contar duas vezes a inscrição repetida, com os clubes por ordem alfabética.

Antes de correres, calcula à mão o que deve aparecer com a lista dada. Depois corre e confirma. Testa também com a lista vazia, `inscricoes = []`.

c) Faz a tabela de decisões do teu script, com uma linha para cada coleção que usaste: os dados, a coleção e porquê.

## Apoio

- Exercício 1: nas linhas `a)`, `b)` e `h)`, a consola mostra a coleção inteira, com os parênteses retos ou as chavetas. Lembra-te de quais são os métodos que mudam a coleção e quais devolvem uma coleção nova.
- Exercício 2: desenha no caderno a tabela de índices de `"07:45"`, carácter a carácter, antes de escolher as fatias. Cada fatia é um texto, e um texto não se multiplica por 60 como um número. O Python não dá erro: repete o texto 60 vezes.
- Exercício 3: é o ciclo da sentinela, com o texto vazio no papel do -1. Converte cada pontuação antes de a guardar na lista. Pensa no que o `max` faz a uma lista vazia.
- Exercício 4: há uma função predefinida do tema 01 que dá a distância de um número a zero, sem sinal.
- Exercício 5: percorre a palavra carácter a carácter. Nem todas as letras são chaves do dicionário, e o guia diz o que acontece quando se lê uma chave que não existe. Precisas da palavra de duas formas: uma para fazer as contas, e outra para mostrar.
- Exercício 6: compara o número de cromos saídos com o número de cromos diferentes. Para os que faltam, percorre os números de 1 a 12 com um `range` e pergunta, a cada um, se a Joana o tem.
- Exercício 7: o Python só mostra o erro seguinte depois de corrigires o anterior. A linha que a mensagem aponta pode não ser a que tem a causa. Um dos erros não dá mensagem nenhuma: só o encontras comparando o resultado com o esperado.
- Exercício 8: na alínea b), repara que dois tuplos com os mesmos valores são iguais, e que um conjunto não guarda repetidos. Para os inscritos de cada clube, o guia tem um padrão para contar, e diz como se percorrem as chaves de um dicionário por ordem.

## Desafio opcional

Duas palavras são anagramas quando têm as mesmas letras, o mesmo número de vezes, por outra ordem, como "roma" e "amor". Escreve o script `anagramas.py`, que lê duas palavras e diz se são anagramas, sem ligar às maiúsculas. Testa com `Roma` e `amor`, `pedra` e `perda`, `mar` e `ram`, e `ola` e `olaa`. Antes de cada caso, escreve o que esperas.

Há uma forma de o fazer numa só condição, com uma das funções predefinidas para listas, que também funciona com textos.

## Para ires mais longe

### Mais longe 1: As iniciais

Escreve o script `iniciais.py`, que lê um nome completo e mostra as iniciais, em maiúsculas, como `Iniciais: ASM` para `ana sofia martins`. Testa também com um nome de uma só palavra.

### Mais longe 2: A palavra mais comprida

Escreve o script `palavra_comprida.py`, que lê uma frase e diz qual é a palavra mais comprida e quantas letras tem. Se houver duas com o mesmo tamanho, mostra a primeira. Se a frase não tiver palavras, por exemplo só com espaços, diz-o. Testa com `O clube de videojogos abre amanhã`, com `Ana viu Rui`, onde as três palavras têm o mesmo tamanho, e com uma frase só de espaços.

### Mais longe 3: O clube que se pergunta

Acrescenta ao fim do teu `inscricoes.py` uma pergunta: o nome de um clube. O script diz quantos inscritos tem esse clube, sem ligar às maiúsculas. Um clube sem inscritos, como `música`, não pode parar o programa: o script diz que o clube não tem inscritos. Testa com `Teatro`, com `música` e com a lista vazia.

## Critérios de conclusão

- O exercício 1 tem a previsão e a confirmação de cada linha marcada, e uma frase para cada previsão errada.
- Os scripts `despertador.py`, `dardos.py`, `tesouro.py`, `palavras.py` e `cromos.py` correm e dão os resultados das tabelas, que preencheste antes de correr.
- O exercício 4 tem a explicação da escolha do tuplo e a previsão do erro.
- O `playlist.py` dá os resultados certos nos três casos. Tens no caderno a rotina de cada um dos três erros, com o tipo de cada um.
- O exercício 8 tem as cinco escolhas justificadas, o `inscricoes.py` a funcionar nos dois casos e a tabela de decisões dele.

## Autoavaliação

1. Que coleção ainda te faz hesitar na hora de escolher? Porquê?
2. No exercício 7, qual dos três erros foi o mais difícil de encontrar, e porquê?
3. Já consegues prever como fica uma coleção depois de um `append`, de um `add` ou de uma atribuição a uma chave, antes de correr?

![Rodapé](../imagens/rodape.png)
