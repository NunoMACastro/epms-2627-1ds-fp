![Cabeçalho](../../imagens/cabecalho.png)

# Ficha de exercícios: Dados e interação

Ficha do tema Dados e interação, do módulo Criar aplicações em linguagem de programação Python. Praticas os tipos e as contas, o trace de uma variável que muda, as funções predefinidas, a leitura com conversão e a procura de erros. Fazes sozinho, ao teu ritmo: o que não acabares na aula, acabas em casa ou na aula seguinte.

## O que precisas de saber

O [guia do tema](../02-dados-e-interacao.md) e o [laboratório](../laboratorios/02-dados-e-interacao-laboratorio.md).

## Como trabalhar

Os exercícios 1 a 6 são obrigatórios e fazem-se por esta ordem, porque cada um usa o que os anteriores treinaram. Cada um precisa das secções do guia que estão entre parênteses:

1. Exercício 1 (de "Os tipos dos valores" a "A ordem das contas", e "Converter o texto lido num número: `int` e `float`").
2. Exercício 2 ("Atribuir outra vez: o valor antigo perde-se").
3. Exercício 3 ("Funções predefinidas" e "Converter o texto lido num número: `int` e `float`").
4. Exercício 4 ("A ordem das contas" e "Converter o texto lido num número: `int` e `float`").
5. Exercício 5 ("A divisão inteira e o resto: `//` e `%`" e o exemplo guiado).
6. Exercício 6 ("Erros frequentes" e as secções que ela indica).

O desafio opcional e a secção "Para ires mais longe" são para quem acabar os obrigatórios.

Guarda os teus scripts na pasta `fp-python`, com os nomes que cada exercício indica. Cada script começa com um comentário que diz o nome do ficheiro e o que ele faz. Os nomes escrevem-se à maneira do Python, em minúsculas, com traço baixo. Uma resposta escrita fica num comentário, com `#`, no início do script ou junto da linha a que diz respeito, como cada exercício indica. Antes de correres um script, pensa no resultado que esperas, tirado do enunciado, e não do que o programa mostra. É aí que percebes se a ideia ficou entendida, e é assim que um teste apanha um erro.

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

Para cada linha em que te enganaste, explica numa frase o que o Python fez. Escreve as frases num ficheiro `prever_na_consola.py`, só com comentários, um por linha.

Parte opcional, com duas linhas que enganam mais: `round(6.5)` e `100 / 10 / 2`.

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

Sem correres o script, faz o trace dele: o valor de `energia` e de `pocoes` depois de cada instrução, e o que aparece no ecrã. As primeiras linhas da tabela de trace já estão preenchidas.

| Passo | Linha | Instrução executada | `energia` | `pocoes` | Ecrã |
| ---: | ---: | --- | ---: | ---: | --- |
| 0 | | antes de começar | sem valor | sem valor | nada |
| 1 | 2 | `energia = 100` | 100 | sem valor | nada |
| 2 | 3 | `energia = energia - 35` | 65 | sem valor | nada |
| 3 | 4 | `pocoes = 2` | | | |
| 4 | 5 | `energia = energia + pocoes * 15` | | | |
| 5 | 6 | `energia = energia - 40` | | | |
| 6 | 7 | `print("Energia no fim:", energia)` | | | |

Copia o script para o ficheiro `energia.py` e escreve lá o trace, num comentário no fim de cada instrução, como em `energia = 100  # energia 100, pocoes sem valor`. No `print`, o comentário diz também o que aparece no ecrã. O ecrã do script tem de coincidir com a última linha do teu trace.

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

## Exercício 4: A temperatura do jogo

Num jogo de sobrevivência feito nos Estados Unidos, a temperatura aparece em graus Fahrenheit, e não em graus Celsius, como em Portugal. Para converter, tira-se 32 à temperatura em Fahrenheit, multiplica-se o resultado por 5 e divide-se por 9.

Escreve o script `temperatura.py`, que pergunta a temperatura em graus Fahrenheit e mostra a temperatura em graus Celsius, arredondada a uma casa decimal. Com 50, o ecrã fica assim:

```text
Temperatura em graus Fahrenheit? 50
Em graus Celsius: 10.0
```

Experimenta-o também com 32, 212, 98.6 e 0 graus Fahrenheit.

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

Copia o script para o ficheiro `quiz.py` e corrige-o até mostrar este resultado com 20 e 15. O Python mostra os erros um de cada vez. Para cada erro que encontrares, segue a rotina e escreve-a num comentário no fim do script:

1. O que aconteceu, e que tipo de erro é: de sintaxe, de execução ou de lógica. Se houver uma mensagem, copia a última linha e a linha que ela aponta.
2. Numa frase, o que achas que causa o erro.
3. Como confirmaste essa frase.
4. A linha que mudaste, e como ficou. Muda o mínimo possível.
5. O que aconteceu quando voltaste a correr.

Quando o script mostrar o resultado certo com 20 e 15, experimenta-o também com 12 perguntas e 5 certas.

## Apoio

- Exercício 1: em cada linha, decide primeiro o tipo e só depois o valor. Pergunta-te se a conta tem um `/` ou se os valores estão entre aspas. Na quinta linha, lembra-te da ordem das contas.
- Exercício 2: em cada instrução, parte dos valores da linha de cima e muda só a variável que está à esquerda do `=`. Um `print` não muda nenhuma variável.
- Exercício 3: antes de escreveres cada linha do script, pensa no que ela tem de mostrar nos três casos.
- Exercício 4: confirma à mão o caso 50 antes de correres, e depois confirma-o no computador.
- Exercício 5: começa pelas contas que farias à mão para o caso 3 e 20, por ordem. Cada conta passa a uma linha do script.
- Exercício 6: lê cada mensagem de baixo para cima, e lembra-te de que a linha apontada pode não ser a da causa. Um dos erros não dá mensagem nenhuma: só o encontras comparando o resultado com o esperado.

## Desafio opcional

Uma aplicação de vídeos guarda a duração de cada vídeo em segundos, mas mostra-a em horas, minutos e segundos. Escreve o script `video.py`, que pergunta a duração de um vídeo em segundos, um número inteiro, e a mostra assim. Com 3725 segundos, o ecrã fica assim:

```text
Duração do vídeo em segundos? 3725
1 h 2 min 5 s
```

Experimenta-o com 3725, 59, 3600, 3599 e 7384 segundos.

## Para ires mais longe

### Mais longe 1: Um script do Python 2

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

### Mais longe 2: Um nome que estraga uma função

Este script devia mostrar o melhor de três jogos e, a seguir, o melhor dos dois primeiros:

```python
# melhor_jogo.py: o melhor de três jogos e o melhor dos dois primeiros.
jogo1 = 12
jogo2 = 30
jogo3 = 21
max = max(jogo1, jogo2, jogo3)
print("O melhor jogo teve", max, "pontos")
print("Dos dois primeiros, o melhor teve", max(jogo1, jogo2), "pontos")
```

Copia-o para o ficheiro `melhor_jogo.py` e corre-o. A primeira linha do ecrã aparece, e depois o script para. A mensagem quer dizer "erro de tipo: um `int` não se pode chamar". Chamar é usar com parênteses, como uma função.

a) Explica, numa ou duas frases, porque é que a linha 5 funcionou e a linha 7 não. Escreve a explicação num comentário no início do script. Pista: segue o que o nome `max` quer dizer antes e depois da linha 5.

b) Corrige o script mudando o mínimo possível, para as duas linhas aparecerem.

## Critérios de conclusão

- O `prever_na_consola.py` tem uma frase para cada linha do exercício 1 em que te enganaste.
- O `energia.py` tem o trace completo, num comentário no fim de cada instrução, e o ecrã coincide com a última linha do trace.
- Os scripts `pontuacoes.py`, `temperatura.py` e `loja.py` correm e dão o resultado certo em todos os casos do enunciado.
- O `quiz.py` dá os resultados certos nos dois casos. O comentário do fim tem a rotina de cada um dos três erros, com o tipo de cada um.

## Autoavaliação

1. Que parte deste tema ainda te faz hesitar? Pode ser o tipo de uma conta, a ordem das contas, a conversão do que se lê ou outra.
2. No exercício 6, qual dos três erros foi o mais difícil de encontrar, e porquê?
3. Quando escreves um `input`, já te lembras sozinho de pensar se o valor lido precisa de conversão?

![Rodapé](../../imagens/rodape.png)
