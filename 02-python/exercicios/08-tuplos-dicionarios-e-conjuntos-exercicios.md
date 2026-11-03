![Cabeçalho](../../imagens/cabecalho.png)

# Ficha de exercícios: Tuplos, dicionários e conjuntos

Ficha do tema Tuplos, dicionários e conjuntos, do módulo Criar aplicações em linguagem de programação Python. Praticas os tuplos, os dicionários e os conjuntos, e a escolha da coleção que serve cada problema. Fazes sozinho, ao teu ritmo: o que não acabares na aula, acabas em casa ou na aula seguinte.

## O que precisas de saber

O [guia do tema](../08-tuplos-dicionarios-e-conjuntos.md) e o [laboratório](../laboratorios/08-tuplos-dicionarios-e-conjuntos-laboratorio.md).

## Como trabalhar

Os exercícios 1 a 8 são obrigatórios e fazem-se por esta ordem, porque cada um usa o que os anteriores treinaram. Cada um precisa das secções do guia que estão entre parênteses:

1. Exercício 1 (do início até "As chavetas com três papéis").
2. Exercício 2 ("Tuplos: valores que andam juntos").
3. Exercício 3 ("Dicionários: procurar por chave").
4. Exercício 4 ("Contar com um dicionário").
5. Exercício 5 ("Conjuntos: valores sem repetidos").
6. Exercício 6 ("Percorrer um dicionário", e a rotina de cinco passos para procurar um erro).
7. Exercício 7 ("Escolher a representação").
8. Exercício 8 ("Contar com um dicionário", "Conjuntos: valores sem repetidos" e "Escolher a representação").

O desafio opcional e a secção "Para ires mais longe" são para quem acabar os obrigatórios.

Guarda os teus scripts na pasta `fp-python`, com os nomes que cada exercício indica. Quando um exercício pede uma resposta escrita, escreve-a no script, num comentário com `#`, no sítio que o exercício indica. Antes de correres um script, decide que resultado esperas, a partir do enunciado: é com ele que vês se o script está certo. Nas mensagens, usa f-strings ou o `print` com vírgulas, como preferires, desde que o ecrã fique como o enunciado mostra.

## Exercício 1: Prever o estado das coleções

Abre a consola do Python, com o teu comando, `python`, `py` ou `python3`. Vais escrever as linhas abaixo, por esta ordem. Antes de cada linha marcada com uma letra, prevê o que a consola vai mostrar. Só depois a escreves e confirmas. As linhas sem letra não mostram nada, mas criam ou mudam as coleções.

```text
jogo = ("Tetris", "puzzle", 1984)
a) jogo[1]
b) len(jogo)
titulo, genero, ano = jogo
c) ano
idades = {"Rui": 15, "Bia": 16}
idades["Rui"] = 16
idades["Eva"] = 14
d) idades
e) len(idades)
f) "Ana" in idades
g) 16 in idades
cores = {"azul", "verde", "azul"}
h) len(cores)
cores.add("verde")
i) len(cores)
j) sorted(cores)
k) type({})
```

Na consola, não escrevas a letra nem o parêntese: escreve só o que vem a seguir, como `jogo[1]`.

Quando uma previsão falhar, procura no guia a razão do que o Python fez.

## Exercício 2: O caminho até ao tesouro

Num jogo, o mapa é uma quadrícula, e cada posição é um par de números, o x e o y. O jogador só anda na horizontal e na vertical, uma casa de cada vez. O número de passos entre duas posições é a distância entre os dois x mais a distância entre os dois y, sem sinal.

Escreve o script `tesouro.py`, que começa com estas duas linhas:

```python
jogador = (2, 3)
tesouro = (7, 1)
```

a) O script mostra quantos passos separam o jogador do tesouro, numa linha como `Do (2, 3) ao (7, 1): 7 passos`. Dá um nome a cada um dos quatro números, numa linha por tuplo. Experimenta-o também com estes casos, mudando as duas linhas do início:

| `jogador` | `tesouro` |
| --- | --- |
| `(7, 1)` | `(2, 3)` |
| `(4, 4)` | `(4, 4)` |
| `(0, 0)` | `(0, 5)` |

b) Num comentário no início do script, explica numa frase porque é que cada posição está num tuplo, e não numa lista.

c) O jogador anda uma casa para cima: o y aumenta 1, e o x fica igual. Acrescenta ao fim do script a linha que muda `jogador`, sem escreveres os números à mão, e mostra o `jogador` novo com um `print`.

## Exercício 3: Os pontos das palavras

Num jogo de palavras, cada letra vale pontos. As vogais sem acento valem 1, e as letras raras valem mais. As letras que não estão na tabela valem 2, também as que têm acento ou cedilha, como o `ã` e o `ç`. Uma palavra vale a soma dos pontos das suas letras, e as maiúsculas valem o mesmo que as minúsculas. Os pontos estão neste dicionário:

```python
pontos = {
    "a": 1,
    "e": 1,
    "i": 1,
    "o": 1,
    "u": 1,
    "k": 5,
    "w": 5,
    "y": 5,
    "j": 8,
    "q": 8,
    "x": 8,
    "z": 10
}
```

Escreve o script `palavras.py`, que lê uma palavra e mostra quantos pontos ela vale, numa linha como `Xadrez vale 24 pontos`. A palavra aparece no ecrã tal como a pessoa a escreveu.

Experimenta-o com `casa`, `Xadrez`, `QUIZ` e `k`.

## Exercício 4: As estrelas do jogo do mês

Os sócios do clube dão de 1 a 5 estrelas ao jogo do mês. Este mês, as avaliações foram estas:

```python
avaliacoes = [5, 4, 5, 3, 5, 4, 1]
```

Escreve o script `estrelas_do_mes.py`, que começa com esta linha e conta, com um dicionário, quantas vezes foi dada cada classificação. Depois mostra as classificações de 1 a 5, uma por linha. As cinco aparecem sempre, também as que ninguém deu. O ecrã começa assim:

```text
Estrelas: vezes
1: 1
```

Experimenta-o também com `avaliacoes = []` e com `avaliacoes = [3, 3, 3]`.

## Exercício 5: A caderneta de cromos

Uma caderneta tem 12 cromos, numerados de 1 a 12. A Joana abriu umas saquetas, e saíram-lhe estes cromos, por esta ordem:

```python
saidos = [3, 7, 3, 12, 1, 7, 7, 5]
```

Escreve o script `cromos.py`, que mostra quatro coisas:

- quantos cromos saíram;
- quantos cromos diferentes a Joana tem;
- quantas cópias a mais tem para trocar: um cromo que saiu três vezes dá duas cópias para trocar;
- que números lhe faltam para completar a caderneta.

O script tem de funcionar com qualquer lista de cromos saídos. Experimenta-o também com `saidos = []` e com uma lista com os 12 números, cada um uma vez.

## Exercício 6: Encontrar o erro

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

Copia o script para o ficheiro `playlist.py` e corre-o. O Python mostra os erros um de cada vez. Para cada erro que encontrares, segue a rotina. Escreve o que ela pede num comentário no fim do script, com `#`, para os números das linhas não mudarem:

1. O que aconteceu, e que tipo de erro é: de sintaxe, de execução ou de lógica. Se houver uma mensagem, copia a última linha e a linha que ela aponta.
2. Numa frase, o que achas que causa o erro.
3. Como confirmaste essa frase.
4. A linha que mudaste, e como ficou. Muda o mínimo possível.
5. O que aconteceu quando voltaste a correr.

Quando o script mostrar o resultado certo, experimenta-o também com uma playlist de uma só música, `{"Só uma": "0:59"}`, e com a playlist vazia, `{}`.

## Exercício 7: Escolher as coleções

Para cada situação da tabela, escolhe a coleção que usavas: lista, tuplo, dicionário ou conjunto. Justifica cada escolha com as quatro perguntas do guia: a ordem, os repetidos, a forma de procurar e se os valores mudam. Escreve as escolhas no ficheiro `colecoes.py`, só com comentários: uma linha por situação, com a coleção e o porquê.

| Situação | Coleção | Porquê |
| --- | --- | --- |
| Os números que já saíram num bingo, para saber se um número já saiu | | |
| As notas de um aluno num período, para a média | | |
| As vidas que restam a cada personagem de um jogo, para as procurar pelo nome | | |
| O dia, o mês e o ano de uma data de nascimento | | |
| As músicas que tocaram numa festa, por ordem, com as que se repetiram | | |

## Exercício 8: As inscrições nos clubes

A escola registou as inscrições nos clubes. Cada inscrição é um tuplo com o nome do aluno e o clube, e um aluno pode estar em mais do que um clube:

```python
inscricoes = [("Ana", "xadrez"), ("Rui", "teatro"), ("Ana", "teatro"),
              ("Bia", "xadrez"), ("Tomás", "robótica")]
```

a) Escreve o script `inscricoes.py`, que mostra:

- quantos alunos diferentes se inscreveram;
- quantos inscritos tem cada clube, com os clubes por ordem alfabética.

Experimenta-o também com a lista vazia, `inscricoes = []`.

b) Num comentário no início do script, faz a tabela de decisões dele. Tem uma linha para cada coleção que usaste, com os dados, a coleção e porquê.

## Apoio

- Exercício 1: nas linhas `d)` e `j)`, a consola mostra a coleção inteira, com as chavetas ou os parênteses retos. Lembra-te do que faz uma atribuição a uma chave que já existe, e do que o `in` pergunta num dicionário.
- Exercício 2: há uma função predefinida do tema 02 que dá a distância de um número a zero, sem sinal.
- Exercício 3: percorre a palavra carácter a carácter. Nem todas as letras são chaves do dicionário, e o guia diz o que acontece quando se lê uma chave que não existe. Precisas da palavra de duas formas: uma para fazer as contas, e outra para mostrar.
- Exercício 4: o guia tem um padrão para contar com um dicionário. Mostra com um `print` provisório o dicionário que ele dá com as avaliações deste mês, e compara-o com o ecrã que o enunciado pede.
- Exercício 5: compara o número de cromos saídos com o número de cromos diferentes. Para os que faltam, percorre os números de 1 a 12 com um `range` e pergunta, a cada um, se a Joana o tem.
- Exercício 6: o Python só mostra o erro seguinte depois de corrigires o anterior. A linha que a mensagem aponta pode não ser a que tem a causa. Um dos erros não dá mensagem nenhuma: só o encontras comparando o resultado com o esperado.
- Exercício 7: responde às quatro perguntas para cada situação, antes de escolheres a coleção.
- Exercício 8: um `for` sobre a lista pode desempacotar cada inscrição em duas variáveis. Para os inscritos de cada clube, o guia tem um padrão para contar, e diz como se percorrem as chaves de um dicionário por ordem.

## Desafio opcional

Duas palavras são anagramas quando têm as mesmas letras, o mesmo número de vezes, por outra ordem, como "roma" e "amor". Um colega escreveu um programa que diz que duas palavras são anagramas quando `set(primeira) == set(segunda)`.

O `set` de um texto dá o conjunto dos seus caracteres: `set("ola")` dá `{'o', 'l', 'a'}`. Dois conjuntos são iguais quando têm os mesmos valores.

a) Sem correr, decide o que o programa do colega responde com `ola` e `olaa`. Está certo? Explica porquê numa frase, num comentário no início do `anagramas.py` da alínea b).

b) Escreve o script `anagramas.py`, que lê duas palavras e diz se são anagramas, sem ligar às maiúsculas. Conta as letras de cada palavra num dicionário. Testa com `Roma` e `amor`, `pedra` e `perda`, `ola` e `olaa`, e `mar` e `sol`.

Dois dicionários são iguais, com o `==`, quando têm exatamente os mesmos pares, seja qual for a ordem em que entraram.

## Para ires mais longe

### Mais longe 1: A inscrição repetida

Uma das inscrições foi registada duas vezes, por engano. Muda a lista do teu `inscricoes.py` para esta, com o `("Rui", "teatro")` duas vezes:

```python
inscricoes = [("Ana", "xadrez"), ("Rui", "teatro"), ("Ana", "teatro"),
              ("Bia", "xadrez"), ("Rui", "teatro"), ("Tomás", "robótica")]
```

Muda também o script, para que a inscrição repetida não conte duas vezes: o teatro tem de continuar com 2 inscritos.

### Mais longe 2: O clube que se pergunta

Acrescenta ao fim do teu `inscricoes.py` uma pergunta: o nome de um clube. O script diz quantos inscritos tem esse clube, sem ligar às maiúsculas. Um clube sem inscritos, como `música`, não pode parar o programa: o script diz que o clube não tem inscritos. Testa com `Teatro`, com `música` e com a lista vazia.

### Mais longe 3: Os jogos em comum

O Rui e a Ana disseram que jogos do clube querem experimentar:

```python
quer_rui = {"Minecraft", "Tetris", "Celeste", "Rocket League"}
quer_ana = {"Celeste", "Forza Horizon 5", "Minecraft"}
```

Escreve o script `em_comum.py`, que mostra, por ordem alfabética, os jogos que os dois querem experimentar. Se não houver nenhum, diz-o. Testa também com a Ana a querer só o `"EA Sports FC 25"`, e com a Ana sem nenhum jogo.

## Critérios de conclusão

- Correste as linhas do exercício 1 na consola, e percebes cada resultado, também os que não previste.
- Os scripts `tesouro.py`, `palavras.py` e `estrelas_do_mes.py` correm e dão o resultado certo em todos os casos do seu exercício.
- O `cromos.py` dá as quatro respostas certas com a lista da Joana e com os outros dois casos.
- O `tesouro.py` tem, no comentário do início, a explicação da escolha do tuplo, e no fim a linha que muda o jogador.
- O `playlist.py` dá os resultados certos nos três casos. O comentário do fim tem a rotina de cada um dos três erros, com o tipo de cada um.
- O `colecoes.py` tem as cinco escolhas do exercício 7, cada uma com o porquê.
- O `inscricoes.py` funciona nos dois casos do exercício 8, e tem a tabela de decisões no comentário do início.

## Autoavaliação

1. Que coleção ainda te faz hesitar na hora de escolher? Porquê?
2. No exercício 6, qual dos três erros foi o mais difícil de encontrar, e porquê?
3. Já consegues prever como fica uma coleção depois de um `add` ou de uma atribuição a uma chave, antes de correr?

![Rodapé](../../imagens/rodape.png)
