![Cabeçalho](../../imagens/cabecalho.png)

# Ficha de exercícios: Tuplos, dicionários e conjuntos

Praticas os tuplos, os dicionários e os conjuntos, e a escolha da coleção que serve cada problema. Os exercícios 1 a 8 são obrigatórios. Os scripts ficam na pasta `fp-python`, com um comentário no início a dizer o que fazem. As respostas que um exercício pedir por escrito ficam em comentários. Para rever: o [guia do tema](../08-tuplos-dicionarios-e-conjuntos.md) e o [laboratório](../laboratorios/08-tuplos-dicionarios-e-conjuntos-laboratorio.md).

## Exercício 1: Prever o estado das coleções

Na consola do Python, escreve as linhas abaixo, por esta ordem. Em cada linha com uma letra, decide primeiro o que vai aparecer, e só depois a escreves. As outras linhas não mostram nada, mas criam ou mudam as coleções.

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

A letra e o parêntese não se escrevem: a linha `a)` é só `jogo[1]`.

Se te enganares, procura no guia a explicação.

Rever: [Um tuplo guarda valores que andam juntos](../08-tuplos-dicionarios-e-conjuntos.md#um-tuplo-guarda-valores-que-andam-juntos), [Um dicionário procura por chave](../08-tuplos-dicionarios-e-conjuntos.md#um-dicionário-procura-por-chave), [Um conjunto guarda valores sem repetidos](../08-tuplos-dicionarios-e-conjuntos.md#um-conjunto-guarda-valores-sem-repetidos) e [As chavetas têm três papéis](../08-tuplos-dicionarios-e-conjuntos.md#as-chavetas-têm-três-papéis).

## Exercício 2: O caminho até ao tesouro

Num jogo, o mapa é uma quadrícula, e cada posição é um par de números, o x e o y. O jogador só anda na horizontal e na vertical, uma casa de cada vez. O número de passos entre duas posições é a distância entre os dois x mais a distância entre os dois y, sem sinal.

Escreve o script `tesouro.py`, com estas duas linhas:

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

Rever: [Um tuplo guarda valores que andam juntos](../08-tuplos-dicionarios-e-conjuntos.md#um-tuplo-guarda-valores-que-andam-juntos).

<details>
<summary>Pista</summary>

Há uma função predefinida que dá a distância de um número a zero.

</details>

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

Rever: [Um dicionário procura por chave](../08-tuplos-dicionarios-e-conjuntos.md#um-dicionário-procura-por-chave).

<details>
<summary>Pista</summary>

Precisas da palavra de duas formas: uma para fazer as contas, e outra para mostrar.

</details>

## Exercício 4: As estrelas do jogo do mês

Os sócios do clube dão de 1 a 5 estrelas ao jogo do mês. Este mês, as avaliações foram estas:

```python
avaliacoes = [5, 4, 5, 3, 5, 4, 1]
```

Escreve o script `estrelas_do_mes.py`, com esta lista, que conta, com um dicionário, quantas vezes foi dada cada classificação. Depois mostra as classificações de 1 a 5, uma por linha. As cinco aparecem sempre, também as que ninguém deu. O ecrã começa assim:

```text
Estrelas: vezes
1: 1
```

Experimenta-o também com `avaliacoes = []` e com `avaliacoes = [3, 3, 3]`.

Rever: [Contar com um dicionário](../08-tuplos-dicionarios-e-conjuntos.md#contar-com-um-dicionário).

<details>
<summary>Pista</summary>

Mostra com um `print` provisório o dicionário que o padrão dá, e compara-o com o ecrã pedido.

</details>

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

Rever: [Um conjunto guarda valores sem repetidos](../08-tuplos-dicionarios-e-conjuntos.md#um-conjunto-guarda-valores-sem-repetidos).

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

Copia o script para o ficheiro `playlist.py`, corre-o e corrige-o, mudando o mínimo possível. Num comentário no fim do script, regista, para cada erro, o que viste e de que tipo é. Regista também a causa que suspeitas, como a confirmaste, a linha que mudaste e o resultado de voltares a correr. Depois, experimenta-o também com uma playlist de uma só música, `{"Só uma": "0:59"}`, e com a playlist vazia, `{}`.

Rever: [Os três tipos de erro](../01-do-pseudocodigo-ao-python.md#os-três-tipos-de-erro).

<details>
<summary>Pista</summary>

Corrige um erro de cada vez, e volta a correr antes de passares ao seguinte.

</details>

## Exercício 7: Escolher as coleções

Para cada situação da tabela, escolhe a coleção que usavas: lista, tuplo, dicionário ou conjunto. Justifica cada escolha com a razão que a decide. As quatro perguntas do guia ajudam: a ordem, os repetidos, a forma de procurar e se os valores mudam. Escreve as escolhas no ficheiro `colecoes.py`, só com comentários: uma linha por situação, com a coleção e o porquê.

| Situação | Coleção | Porquê |
| --- | --- | --- |
| Os números que já saíram num bingo, para saber se um número já saiu | | |
| As notas de um aluno num período, para a média | | |
| As vidas que restam a cada personagem de um jogo, para as procurar pelo nome | | |
| O dia, o mês e o ano de uma data de nascimento | | |
| As músicas que tocaram numa festa, por ordem, com as que se repetiram | | |

Rever: [Escolher a representação](../08-tuplos-dicionarios-e-conjuntos.md#escolher-a-representação).

## Exercício 8: As inscrições nos clubes

A escola registou as inscrições nos clubes. Cada inscrição é um tuplo com o nome do aluno e o clube, e um aluno pode estar em mais do que um clube:

```python
inscricoes = [("Ana", "xadrez"), ("Rui", "teatro"), ("Ana", "teatro"),
              ("Bia", "xadrez"), ("Tomás", "robótica")]
```

a) Escreve o script `inscricoes.py`, que mostra:

- quantos alunos diferentes se inscreveram;
- quantos inscritos tem cada clube, com os clubes por ordem alfabética.

Experimenta-o também com a lista vazia, `inscricoes = []`, que não pode parar o programa.

b) Num comentário no início do script, faz a tabela de decisões dele. Tem uma linha para cada coleção que usaste, com os dados, a coleção e porquê.

Rever: [Escolher a representação](../08-tuplos-dicionarios-e-conjuntos.md#escolher-a-representação).

## Desafios

### Desafio 1: Os anagramas

Duas palavras são anagramas quando têm as mesmas letras, o mesmo número de vezes, por outra ordem, como "roma" e "amor". Um colega escreveu um programa que diz que duas palavras são anagramas quando `set(primeira) == set(segunda)`. O `set` de um texto dá o conjunto dos seus caracteres, e dois conjuntos são iguais quando têm os mesmos valores.

Escreve o script `anagramas.py`, que lê duas palavras e diz se são anagramas, sem ligar às maiúsculas. Conta as letras de cada palavra num dicionário. Dois dicionários são iguais, com o `==`, quando têm exatamente os mesmos pares. Testa com `Roma` e `amor`, `pedra` e `perda`, `ola` e `olaa`, e `mar` e `sol`. Num comentário no início, diz o que o programa do colega responde com `ola` e `olaa`, e porquê.

### Desafio 2: A inscrição repetida

Uma das inscrições do exercício 8 foi registada duas vezes, por engano. Copia o teu `inscricoes.py` para `inscricoes_repetidas.py`, e muda lá a lista para esta. Muda também o script, para que a inscrição repetida não conte duas vezes: o teatro tem de continuar com 2 inscritos.

```python
inscricoes = [("Ana", "xadrez"), ("Rui", "teatro"), ("Ana", "teatro"),
              ("Bia", "xadrez"), ("Rui", "teatro"), ("Tomás", "robótica")]
```

### Desafio 3: O clube que se pergunta

Copia o teu `inscricoes.py` para `inscricoes_clube.py`, e acrescenta-lhe no fim uma pergunta: o nome de um clube. O script diz quantos inscritos tem esse clube, sem ligar às maiúsculas. Um clube sem inscritos, como `música`, não pode parar o programa. Testa com `Teatro`, com `música` e com a lista vazia.

### Desafio 4: Os jogos em comum

O Rui e a Ana disseram que jogos do clube querem experimentar. Escreve o script `em_comum.py`, que mostra, por ordem alfabética, os jogos que os dois querem experimentar. Se não houver nenhum, diz-o. Testa também com a Ana a querer só o `"EA Sports FC 25"`, e com a Ana sem nenhum jogo.

```python
quer_rui = {"Minecraft", "Tetris", "Celeste", "Rocket League"}
quer_ana = {"Celeste", "Forza Horizon 5", "Minecraft"}
```

## Critérios de conclusão

- As previsões do exercício 1 foram confirmadas na consola.
- Os scripts `tesouro.py`, `palavras.py`, `estrelas_do_mes.py` e `cromos.py` dão o resultado certo em todos os casos do seu exercício.
- O `tesouro.py` tem, no comentário do início, a explicação da escolha do tuplo, e no fim a linha que muda o jogador.
- O `playlist.py` dá os resultados certos nos três casos, e o comentário do fim explica cada erro.
- O `colecoes.py` tem as cinco escolhas do exercício 7, cada uma com o porquê.
- O `inscricoes.py` funciona nos dois casos do exercício 8, e tem a tabela de decisões no comentário do início.

![Rodapé](../../imagens/rodape.png)
