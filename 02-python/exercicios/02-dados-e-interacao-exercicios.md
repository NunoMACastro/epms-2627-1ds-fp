![Cabeçalho](../../imagens/cabecalho.png)

# Ficha de exercícios: Dados e interação

Nesta ficha, praticas os tipos e as contas, o trace de uma variável que muda, as funções predefinidas e a leitura com conversão. Os exercícios 1 a 6 são obrigatórios. Guarda os scripts na pasta `fp-python`, cada um com um comentário no início a dizer o que faz. Em cada caso de teste, calcula o resultado à mão antes de correres o script. Para rever: o [guia do tema](../02-dados-e-interacao.md) e o [laboratório](../laboratorios/02-dados-e-interacao-laboratorio.md).

## Exercício 1: Prever na consola

Abre a consola do Python, no terminal, com `python`, ou `python3` no macOS. Para cada uma destas linhas, prevê o valor que ela dá e o tipo desse valor, e confirma-os na consola. Os tipos possíveis são `int`, `float` e `str`. Para confirmares o tipo, podes usar o `type`, como em `type(25 / 4)`.

- `25 / 4`
- `25 // 4`
- `25 % 4`
- `24 / 4`
- `3 * 2 ** 2`
- `"7" + "1"`
- `int("7") + 1`
- `int(9.87)`
- `int("7") / 2`

Para cada linha em que te enganaste, explica numa frase o que o Python fez. Escreve as frases num ficheiro `prever_na_consola.py`, só com comentários, um por linha. Se acertaste em todas, o ficheiro fica só com o comentário do início.

Rever: [Parte 3: As contas](../02-dados-e-interacao.md#parte-3-as-contas) e [Parte 5: Ler do teclado](../02-dados-e-interacao.md#parte-5-ler-do-teclado).

<details>
<summary>Pista</summary>

Em cada linha, decide primeiro o tipo e só depois o valor. Pergunta-te se a conta tem um `/` sozinho, um `//` ou valores entre aspas. Na quinta linha, lembra-te da ordem das contas.

</details>

## Exercício 2: A energia da personagem

Num jogo de aventura, a energia de uma personagem muda ao longo de um combate. Este script mostra a energia com que ela acaba:

```python
# energia.py: a energia de uma personagem ao longo de um combate.
energia = 100
energia = energia - 35
pocoes = 2
energia = energia + pocoes * 15
energia = energia - 40
print("Energia no fim:", energia)
```

Sem correres o script, faz o trace dele: o valor de `energia` e de `pocoes` depois de cada instrução, e o que aparece no ecrã. As primeiras linhas já estão preenchidas, para veres como se faz. O resto do trace escreve-se no `energia.py`, como se diz a seguir à tabela.

| Passo | Linha | Instrução executada | `energia` | `pocoes` | Ecrã |
| ---: | ---: | --- | ---: | ---: | --- |
| 0 | | antes de começar | sem valor | sem valor | nada |
| 1 | 2 | `energia = 100` | 100 | sem valor | nada |
| 2 | 3 | `energia = energia - 35` | 65 | sem valor | nada |
| 3 | 4 | `pocoes = 2` | | | |
| 4 | 5 | `energia = energia + pocoes * 15` | | | |
| 5 | 6 | `energia = energia - 40` | | | |
| 6 | 7 | `print("Energia no fim:", energia)` | | | |

Copia o script para o ficheiro `energia.py` e escreve lá o trace, num comentário no fim de cada instrução, como em `energia = 100  # energia 100, pocoes sem valor`. No `print`, o comentário diz também o que aparece no ecrã. Só depois corre o script: o ecrã tem de coincidir com a última linha do teu trace.

Rever: [Atribuir outra vez apaga o valor antigo](../02-dados-e-interacao.md#atribuir-outra-vez-apaga-o-valor-antigo) e [A ordem das contas é a da matemática](../02-dados-e-interacao.md#a-ordem-das-contas-é-a-da-matemática).

<details>
<summary>Pista</summary>

Em cada instrução, parte dos valores da linha de cima e muda só a variável que está à esquerda do `=`.

</details>

## Exercício 3: As pontuações de dois amigos

Dois amigos jogaram o mesmo nível de um jogo e querem comparar as pontuações. Escreve o script `pontuacoes.py`, que pergunta os pontos do primeiro jogador e os do segundo, dois números inteiros. Depois mostra a melhor pontuação, a pior e a diferença entre as duas. A diferença diz quantos pontos separam os dois amigos, seja qual for o que fez mais.

Com 1200 e 950, o ecrã fica assim:

```text
Pontos do primeiro jogador? 1200
Pontos do segundo jogador? 950
Melhor pontuação: 1200
Pior pontuação: 950
Diferença: 250
```

Experimenta-o também com 800 e 1500, e com 1000 e 1000.

Rever: [Uma função predefinida já vem com o Python](../02-dados-e-interacao.md#uma-função-predefinida-já-vem-com-o-python) e [O `max` e o `min` dão o maior e o menor](../02-dados-e-interacao.md#o-max-e-o-min-dão-o-maior-e-o-menor).

## Exercício 4: A temperatura do jogo

Num jogo de sobrevivência feito nos Estados Unidos, a temperatura aparece em graus Fahrenheit, e não em graus Celsius, como em Portugal. Para converter, tira-se 32 à temperatura em Fahrenheit, multiplica-se o resultado por 5 e divide-se por 9.

Escreve o script `temperatura.py`, que pergunta a temperatura em graus Fahrenheit e mostra a temperatura em graus Celsius, arredondada a uma casa decimal. Com 50, o ecrã fica assim:

```text
Temperatura em graus Fahrenheit? 50
Em graus Celsius: 10.0
```

Experimenta-o também com 32, 212, 98.6 e 0 graus Fahrenheit.

Rever: [A ordem das contas é a da matemática](../02-dados-e-interacao.md#a-ordem-das-contas-é-a-da-matemática) , [Um número com parte decimal lê-se com `float`](../02-dados-e-interacao.md#um-número-com-parte-decimal-lê-se-com-float) e [O `round` arredonda um número](../02-dados-e-interacao.md#o-round-arredonda-um-número).

<details>
<summary>Pista</summary>

Calcula à mão o caso 50, pela ordem do enunciado, e confirma que a tua conta faz o mesmo.

</details>

## Exercício 5: A loja do jogo

Num jogo, há moedas de ouro e moedas de prata, e uma moeda de ouro vale 100 moedas de prata. Na loja do jogo, uma espada custa 250 moedas de prata. Escreve o script `loja.py`, que pergunta quantas moedas de ouro e quantas moedas de prata o jogador tem. Depois diz quantas espadas ele pode comprar com esse dinheiro, e quanto dinheiro lhe sobra, contado em moedas de prata.

Com 3 moedas de ouro e 20 de prata, o ecrã fica assim:

```text
Moedas de ouro? 3
Moedas de prata? 20
Espadas que podes comprar: 1
Moedas de prata que sobram: 70
```

Experimenta-o também com estas moedas de ouro e de prata: 5 e 0, 2 e 49, e 0 e 250.

Rever: [A divisão inteira e o resto](../02-dados-e-interacao.md#a-divisão-inteira-e-o-resto).

<details>
<summary>Pista</summary>

Começa pelas contas que farias à mão para o caso 3 e 20, por ordem. Cada conta passa a uma linha do script.

</details>

## Exercício 6: Encontrar o erro

O script `quiz.py` devia mostrar o resultado de um quiz: quantas respostas foram erradas e que percentagem das respostas foi certa, arredondada às unidades. Tem três erros, de propósito.

```python
# quiz.py: o resultado de um quiz, com as respostas erradas e a percentagem de certas.
# Este script tem três erros, de propósito.
perguntas = input("Quantas perguntas tinha o quiz? ")
certas = int(input("Quantas acertaste? "))
erradas = perguntas - certas
percentagem = round(certas / perguntas) * 100
print("Respostas erradas:" erradas)
print("Percentagem de certas:", percentagem)
```

Com 20 perguntas e 15 certas, o script devia mostrar:

```text
Quantas perguntas tinha o quiz? 20
Quantas acertaste? 15
Respostas erradas: 5
Percentagem de certas: 75
```

Copia o script para o ficheiro `quiz.py` e corrige-o até mostrar este resultado, mudando o mínimo possível. O Python para no primeiro erro que encontra. Num comentário no fim do script, escreve a rotina de cada erro. Diz o que aconteceu e o tipo de erro, a causa que suspeitas e como a confirmaste. Diz também a linha que mudaste e o que apareceu ao voltares a correr o script.

Quando o script mostrar o resultado certo com 20 e 15, experimenta-o também com 12 perguntas e 5 certas.

Rever: [Os três tipos de erro](../01-do-pseudocodigo-ao-python.md#os-três-tipos-de-erro) , [Parte 4: As funções predefinidas](../02-dados-e-interacao.md#parte-4-as-funções-predefinidas) e [Parte 5: Ler do teclado](../02-dados-e-interacao.md#parte-5-ler-do-teclado).

<details>
<summary>Pista</summary>

Lê cada mensagem de baixo para cima, e lembra-te de que a linha apontada pode não ser a da causa. Um dos erros não dá mensagem nenhuma: só o encontras comparando o resultado com o esperado.

</details>

## Desafios

### Desafio 1: Duas linhas que enganam

Na consola, prevê o valor e o tipo de `round(6.5)` e de `100 / 10 / 2`, e confirma-os. Rever: [O `round` arredonda um número](../02-dados-e-interacao.md#o-round-arredonda-um-número) e [A ordem das contas é a da matemática](../02-dados-e-interacao.md#a-ordem-das-contas-é-a-da-matemática).

### Desafio 2: A duração de um vídeo

Uma aplicação de vídeos guarda a duração de cada vídeo em segundos, mas mostra-a em horas, minutos e segundos. Escreve o script `video.py`, que pergunta a duração de um vídeo em segundos, um número inteiro, e a mostra nesse formato. Com 3725 segundos, o ecrã fica assim:

```text
Duração do vídeo em segundos? 3725
1 h 2 min 5 s
```

Experimenta-o com 3725, 59, 3600, 3599 e 7384 segundos.

### Desafio 3: Um script do Python 2

Encontraste numa página antiga este script, que lê dois números inteiros e mostra a média:

```text
primeiro = int(raw_input("Primeiro numero? "))
segundo = int(raw_input("Segundo numero? "))
print "A media e", (primeiro + segundo) / 2
```

a) Diz porque é que este script não corre no Python 3, e que mensagem esperas ver.

b) Escreve a versão para o Python 3, no script `media_de_dois.py`, com os acentos nas mensagens.

c) Com 7 e 8, a versão antiga, no Python 2, mostrava `A media e 7`. Quanto mostra a tua versão, e porque é que os dois resultados são diferentes?

Responde à a) e à c) num comentário no início do `media_de_dois.py`.

Rever: [O Python 3 e o código antigo](../01-do-pseudocodigo-ao-python.md#o-python-3-e-o-código-antigo), [A divisão com `/` dá sempre um `float`](../02-dados-e-interacao.md#a-divisão-com--dá-sempre-um-float) e [O `input` lê sempre um texto](../02-dados-e-interacao.md#o-input-lê-sempre-um-texto).

### Desafio 4: O melhor dos dois primeiros

Este script devia mostrar o melhor de três jogos e, a seguir, o melhor dos dois primeiros:

```python
# melhor_jogo.py: o melhor de três jogos e o melhor dos dois primeiros.
jogo1 = 12
jogo2 = 30
jogo3 = 41
max = max(jogo1, jogo2, jogo3)
print("O melhor jogo teve", max, "pontos")
print("Dos dois primeiros, o melhor teve", max(jogo1, jogo2), "pontos")
```

Copia-o para o ficheiro `melhor_jogo.py` e corre-o. A primeira linha do ecrã aparece, e depois o script para. A mensagem quer dizer "erro de tipo: um `int` não se pode chamar". Chamar é usar com parênteses, como uma função.

a) Explica, numa ou duas frases, porque é que a linha 5 funcionou e a linha 7 não. Escreve a explicação num comentário no início do script.

b) Corrige o script mudando o mínimo possível, para as duas linhas aparecerem.

<details>
<summary>Pista</summary>

Segue o que o nome `max` quer dizer antes e depois da linha 5.

</details>

## Critérios de conclusão

- O `prever_na_consola.py` tem uma frase para cada linha do exercício 1 em que te enganaste.
- O `energia.py` tem o trace completo, e o ecrã coincide com a última linha do trace.
- Os scripts `pontuacoes.py`, `temperatura.py` e `loja.py` correm e dão o resultado certo em todos os casos do enunciado.
- O `quiz.py` dá os resultados certos nos dois casos, e o comentário do fim tem a rotina de cada um dos três erros.

![Rodapé](../../imagens/rodape.png)
