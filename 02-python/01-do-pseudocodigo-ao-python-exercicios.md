![Cabeçalho](../imagens/cabecalho.png)

# Ficha de exercícios: Do pseudocódigo ao Python

Ficha do tema Do pseudocódigo ao Python, do módulo Criar aplicações em linguagem de programação Python. Praticas a tradução de algoritmos para Python, a leitura dos erros e a leitura de código que não escreveste. Fazes sozinho, ao teu ritmo: o que não acabares na aula, acabas em casa ou na aula seguinte.

## O que precisas de saber

O [guia do tema](01-do-pseudocodigo-ao-python.md) e o [laboratório](01-do-pseudocodigo-ao-python-laboratorio.md).

## Como trabalhar

Os exercícios 1 a 7 são obrigatórios e fazem-se por esta ordem, porque cada um usa o que os anteriores treinaram. Cada um precisa das secções do guia que estão entre parênteses:

1. Exercício 1 (as secções "Os tipos dos valores", "Contas e divisões" e "Funções predefinidas").
2. Exercício 2 (até "Ler do teclado com `input`, e converter").
3. Exercício 3 (até "Decidir com `if`, `elif` e `else`").
4. Exercício 4 ("Repetir com `while`").
5. Exercício 5 ("Contar voltas com `for` e `range`" e "Percorrer uma lista com `for`").
6. Exercício 6 ("Os três tipos de erro" e "Erros frequentes").
7. Exercício 7 (até "Funções com `def` e `return`").

O desafio opcional e a secção "Para ires mais longe" são para quem acabar os obrigatórios.

Guarda os teus scripts na pasta `fp-python`, a do laboratório, com os nomes que cada exercício indica. As tabelas e as respostas escritas ficam no caderno. Antes de correres um script, escreve sempre o resultado que esperas. É aí que percebes se a ideia ficou entendida.

## Exercício 1: Prever na consola

Abre a consola do Python, no terminal, com `python`, ou `python3` no macOS. Para cada linha da tabela, escreve no caderno o valor que esperas e o tipo desse valor, antes de experimentares. Os tipos possíveis são `int`, `float`, `str` e `bool`. Depois escreve a linha a seguir ao `>>>` e confirma. Para saberes o tipo de um resultado, podes usar `type`, como em `type(19 / 4)`.

| Linha | O valor que esperas | O tipo que esperas |
| --- | --- | --- |
| `19 / 4` | | |
| `19 // 4` | | |
| `19 % 4` | | |
| `12 / 4` | | |
| `"5" + "5"` | | |
| `int("8") * 2` | | |
| `round(6.5)` | | |
| `int(5.99)` | | |

Para cada linha em que te enganaste, escreve uma frase a explicar o que o Python fez.

## Exercício 2: As moedas do jogo

Num jogo, 100 moedas de prata trocam-se por 1 moeda de ouro. Este algoritmo diz quantas moedas de ouro dão as moedas de prata do jogador, e quantas moedas de prata sobram:

```text
const PRATA_POR_OURO = 100
Escreve: "Quantas moedas de prata tens?"
int prata = ler valor
int ouro = prata div PRATA_POR_OURO
int prataQueSobra = prata resto PRATA_POR_OURO
Escreve: "Moedas de ouro: ", ouro
Escreve: "Moedas de prata que sobram: ", prataQueSobra
```

a) Antes de escreveres código, completa no caderno o resultado esperado de cada caso, calculado à mão a partir do enunciado:

| Moedas de prata | Moedas de ouro | Moedas de prata que sobram |
| ---: | ---: | ---: |
| 250 | | |
| 100 | | |
| 99 | | |
| 0 | | |

b) Traduz o algoritmo para Python, no script `moedas.py`. Começa com um comentário que diga o que o script faz.

c) Corre o script com os quatro casos e confirma a tabela.

## Exercício 3: O escalão do jogador

Num jogo online, o escalão de um jogador depende dos pontos de experiência que tem, um número inteiro. Com menos de 1000 pontos, o escalão é Bronze. De 1000 a 2499 pontos, é Prata. Com 2500 pontos ou mais, é Ouro. Um número negativo de pontos é inválido, e o programa escreve "Pontos inválidos" em vez de um escalão.

a) Completa no caderno a tabela dos casos de teste, com o resultado esperado de cada um:

| Pontos | Resultado esperado |
| ---: | --- |
| -1 | |
| 0 | |
| 999 | |
| 1000 | |
| 2499 | |
| 2500 | |

b) Escreve o script `escalao.py`, que lê os pontos e escreve o escalão. Se te ajudar, escreve primeiro o algoritmo em pseudocódigo, e depois traduz.

c) Corre o script com os seis casos e confirma a tabela.

## Exercício 4: O número de jogadores

Um jogo de tabuleiro joga-se com 2 a 6 jogadores, incluindo o 2 e o 6. Escreve o script `jogadores.py`, que pergunta quantos jogadores há. Enquanto o número não estiver entre 2 e 6, escreve "Esse número não dá. Escreve de 2 a 6:" e lê outra vez. Quando o número for aceite, escreve uma linha como "Jogo para 4 jogadores", com o número aceite.

Testa o script com estas entradas, e escreve no caderno, antes de cada uma, quantas vezes esperas que ele volte a perguntar:

| Valores escritos, por ordem | Quantas vezes volta a perguntar | O que escreve no fim |
| --- | ---: | --- |
| 4 | | |
| 2 | | |
| 6 | | |
| 1, 7, 4 | | |

## Exercício 5: As estrelas dos níveis

Num jogo de plataformas, cada nível dá de 0 a 3 estrelas. As estrelas que a Inês ganhou nos níveis que já jogou estão nesta lista:

```python
estrelas = [3, 2, 3, 0, 1, 3, 2, 3]
```

a) Escreve o script `estrelas.py`, que mostra três coisas. A primeira é quantos níveis têm 3 estrelas. A segunda é o total de estrelas. A terceira é quantas estrelas faltam para ter 3 em todos os níveis jogados. O script tem de funcionar para uma lista com qualquer número de níveis, por isso não escrevas o 8 em lado nenhum.

b) Antes de correres, calcula à mão o que o script deve mostrar com a lista da Inês. Depois corre e confirma.

c) Muda a lista para `[]`, e depois para `[0]`. Antes de correres cada uma, escreve o que esperas que apareça. Depois confirma.

## Exercício 6: Encontrar o erro

O script `torneio.py` devia somar os pontos das 3 rondas de um torneio e contar as rondas ganhas. Uma ronda é ganha quando o jogador faz 10 pontos ou mais. Tem três erros, de propósito.

```python
# torneio.py: soma os pontos das 3 rondas de um torneio e conta as rondas ganhas.
# Este script tem três erros, de propósito.
RONDAS = 3
PONTOS_PARA_GANHAR = 10

total = 0
ganhas = 0
for ronda in range(1, RONDAS + 1):
    pontos = input("Pontos da ronda: ")
    if pontos >= PONTOS_PARA_GANHAR:
        ganhas = ganhas + 1
total = total + pontos
print("Total de pontos:", total
print("Rondas ganhas:", ganhas)
```

Com os pontos 12, 8 e 15, o script devia mostrar `Total de pontos: 35` e `Rondas ganhas: 2`.

Copia o script para o ficheiro `torneio.py` e corre-o com os pontos 12, 8 e 15. O Python mostra os erros um de cada vez. Para cada erro que encontrares, segue a rotina e escreve no caderno:

1. O que aconteceu, e que tipo de erro é: de sintaxe, de execução ou de lógica. Se houver uma mensagem, copia a última linha e a linha que ela aponta.
2. Numa frase, o que achas que causa o erro.
3. Como confirmaste essa frase.
4. A linha que mudaste, e como ficou. Muda o mínimo possível.
5. O que aconteceu quando voltaste a correr.

Quando o script mostrar o resultado certo com 12, 8 e 15, testa-o também com 10, 9 e 0. Antes de correres, calcula o que deve aparecer.

## Exercício 7: A função mistério

Esta função foi escrita por outra pessoa. Falta-lhe a documentação, e o nome não diz o que ela faz:

```python
def misterio(pontos, limite):
    quantos = 0
    for valor in pontos:
        if valor > limite:
            quantos = quantos + 1
        else:
            break
    return quantos
```

a) Sem a correres, diz o que devolve cada chamada:

| Chamada | O que devolve |
| --- | --- |
| `misterio([15, 12, 8, 20], 10)` | |
| `misterio([5, 30], 10)` | |
| `misterio([], 10)` | |

b) Escreve a função em pseudocódigo, na forma das aulas.

c) Explica numa ou duas frases o que a função faz. Depois escreve a documentação que lhe falta, entre três pares de aspas, e dá-lhe um nome que diga o que ela faz.

d) Confirma a alínea a) no computador: copia a função para um script, acrescenta três `print` com as três chamadas e corre.

## Apoio

- Exercício 1: lembra-te de que o `/` dá sempre um `float`, e de que o `+` entre dois textos não soma. O `round` tem um pormenor nos números que estão exatamente a meio.
- Exercício 2: a tradução de cada linha do pseudocódigo está numa tabela do guia. Confirma que a palavra `div` passou ao operador certo. Com 250, uma das traduções dá 2.5 moedas de ouro, o que não existe num jogo.
- Exercício 3: desenha primeiro a reta dos pontos, com as regiões e as fronteiras, como no guia 03. A ordem das condições na cadeia conta.
- Exercício 4: a condição do `while` é a de um número que não dá. Repara que o 2 e o 6 são aceites.
- Exercício 5: há uma função predefinida que diz quantos elementos tem uma lista. Com a lista vazia, confirma que os três resultados fazem sentido e que o script não dá erro.
- Exercício 6: o Python só mostra o erro seguinte depois de corrigires o anterior. Um dos erros não dá mensagem nenhuma: só o encontras se comparares o resultado com o esperado.
- Exercício 7: faz a tabela de iterações da primeira chamada. Repara no que o `break` faz à volta em que a condição é falsa.

## Desafio opcional

Traduz para Python o teu algoritmo do [projeto 2, Adivinha o número](../01-algoritmos/05-projeto-2-adivinha-o-numero.md), que está no teu portefólio, no script `adivinha.py`. Usa os casos da tua tabela de casos esperados do projeto, e confirma que o programa dá o mesmo que o algoritmo.

As mensagens do enunciado têm de aparecer palavra por palavra, como "Acertaste à tentativa 3!", sem nenhum espaço antes do ponto de exclamação. Com o `print` e as vírgulas, isso não acontece. O guia diz como se junta um número a um texto sem espaços.

## Para ires mais longe

### Mais longe 1: O robô aspirador

Um robô aspirador recebe um comando de uma letra. O `f` manda andar para a frente, e o `t` para trás. O `e` manda virar à esquerda, e o `d` à direita. Escreve o script `robo.py`, que lê o comando e escreve o que o robô vai fazer, como "A andar para a frente.". Para qualquer outra letra, escreve "Comando desconhecido.". Usa o `match`. Testa com as quatro letras e com `x`.

Este exercício precisa do Python 3.10 ou mais recente, por causa do `match`. Confirma a tua versão com `python --version`, ou `python3 --version` no macOS.

### Mais longe 2: Um script do Python 2

Encontraste numa página antiga este script, que lê dois números inteiros e mostra a média:

```text
primeiro = int(raw_input("Primeiro numero? "))
segundo = int(raw_input("Segundo numero? "))
print "A media e", (primeiro + segundo) / 2
```

a) Diz porque é que este script não corre no Python 3, e que mensagem esperas ver.

b) Escreve a versão para o Python 3, no script `media_de_dois.py`, com os acentos nas mensagens.

c) Com 7 e 8, a versão antiga, no Python 2, mostrava `A media e 7`. Quanto mostra a tua versão, e porque é que os dois resultados são diferentes?

## Critérios de conclusão

- O exercício 1 tem a previsão e a confirmação de cada linha, e uma frase para cada previsão errada.
- Os scripts `moedas.py`, `escalao.py`, `jogadores.py` e `estrelas.py` correm e dão os resultados das tabelas, que preencheste antes de correr.
- O `torneio.py` dá os resultados certos nos dois casos. Tens no caderno a rotina de cada um dos três erros, com o tipo de cada um.
- A função do exercício 7 tem pseudocódigo, uma explicação, documentação e um nome novo, e as três chamadas foram confirmadas no computador.

## Autoavaliação

1. Que parte da tradução para Python ainda te faz hesitar? Pode ser a leitura e a conversão, os dois pontos e a indentação, o `range`, ou outra.
2. No exercício 6, qual dos três erros foi o mais difícil de encontrar, e porquê?
3. Quando um script teu dá um erro, já consegues dizer de que tipo é antes de leres a mensagem toda?

![Rodapé](../imagens/rodape.png)
