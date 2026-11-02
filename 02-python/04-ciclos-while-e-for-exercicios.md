![Cabeçalho](../imagens/cabecalho.png)

# Ficha de exercícios: Ciclos while e for

Ficha do tema Ciclos while e for, do módulo Criar aplicações em linguagem de programação Python. Praticas a previsão das voltas de um ciclo, a validação repetida, a sentinela, o contador e o acumulador. Praticas também o `for` com `range` e a procura de erros em ciclos. Fazes sozinho, ao teu ritmo: o que não acabares na aula, acabas em casa ou na aula seguinte.

## O que precisas de saber

O [guia do tema](04-ciclos-while-e-for.md) e o [laboratório](04-ciclos-while-e-for-laboratorio.md).

## Como trabalhar

Os exercícios 1 a 5 são obrigatórios e fazem-se por esta ordem, porque cada um usa o que os anteriores treinaram. Cada um precisa das secções do guia que estão entre parênteses:

1. Exercício 1 ("Repetir com `while`", "Ver as voltas: a tabela de iterações prevista e observada" e "As duas formas do `Para` e o `range`").
2. Exercício 2 ("Validação repetida").
3. Exercício 3 ("Um `for` com um número lido do teclado" e "Contar só algumas voltas").
4. Exercício 4 ("Ler até à sentinela" e "O contador e o acumulador").
5. Exercício 5 (as secções do `for` e "Erros frequentes").

O desafio opcional e a secção "Para ires mais longe" são para quem acabar os obrigatórios.

Guarda os teus scripts na pasta `fp-python`, com os nomes que cada exercício indica. As tabelas e as respostas escritas ficam no caderno. Antes de correres um script, escreve sempre o resultado que esperas, tirado do enunciado. É aí que percebes se a ideia ficou entendida.

## Exercício 1: Quantas voltas?

Para cada programa, escreve no caderno, antes de o correres, quantas voltas dá o ciclo e o que aparece no ecrã. Depois copia-o para um ficheiro com o nome da primeira linha, corre-o e confirma.

a) Copia a tabela de iterações e acrescenta as linhas que faltam, até ao teste que dá `False`. Diz também quanto vale `vidas` depois do ciclo.

```python
# contagem_vidas.py: escreve as vidas que restam, da última à primeira.
vidas = 3
while vidas > 0:
    print("Vidas:", vidas)
    vidas = vidas - 1
print("Fim do jogo")
```

| Teste | vidas | Condição | Durante a volta |
| --- | ---: | --- | --- |
| 1.º | 3 | `3 > 0` dá `True` | escreve "Vidas: 3" |
| 2.º | 2 | | |

b) Faz a tabela toda, com uma linha por volta. Diz se o número 6 chega a aparecer, e porquê.

```python
# niveis.py: escreve os números dos níveis de 2 a 5.
for nivel in range(2, 6):
    print("Nível", nivel)
print("Acabaram os níveis")
```

| Volta | nivel | Escreve |
| --- | ---: | --- |

c) Escolhe tu como seguir este ciclo.

```python
# range_quatro.py: escreve os primeiros quatro múltiplos de 5, a começar no 0.
for i in range(4):
    print(i * 5)
```

d) No programa da alínea a), acrescenta uma linha de observação na primeira linha do corpo e outra logo a seguir ao ciclo. Corre-o e confirma que a tabela observada é igual à tua.

## Exercício 2: O número de jogadores

Um jogo de tabuleiro joga-se com 2 a 6 jogadores, incluindo o 2 e o 6. Escreve o script `jogadores_ciclo.py`, que pergunta quantos jogadores há. Enquanto o número não der, escreve "Esse número não dá. Escreve de 2 a 6:" e pergunta outra vez. Quando o número for aceite, escreve uma linha como "Jogo para 4 jogadores". No fim, escreve também quantas respostas foram recusadas, como "Respostas recusadas: 2".

Testa o script com estas entradas. Antes de cada uma, escreve no caderno o que esperas:

| Valores escritos, por ordem | Quantas vezes volta a perguntar | O que escreve no fim |
| --- | ---: | --- |
| 4 | | |
| 2 | | |
| 6 | | |
| 1, 7, 4 | | |

## Exercício 3: O treino de lançamentos

Num treino de basquetebol, fazes séries de 10 lançamentos ao cesto. Uma série é boa quando marcas 7 cestos ou mais. Escreve o script `lancamentos.py`, que pergunta quantas séries fizeste e depois quantos cestos marcaste em cada uma, como "Cestos da série 1?". Quem usa o programa escreve sempre um número de 0 a 10. No fim, o script mostra três coisas:

- o total de cestos;
- quantas séries foram boas;
- quantos lançamentos falhaste, ao todo.

a) Antes de escreveres código, calcula à mão o que o script deve mostrar com 4 séries de 8, 5, 7 e 10 cestos.

b) Escreve o script e corre-o com esse caso.

c) Antes de correres, escreve o que esperas com 0 séries, e com 1 série de 6 cestos. Depois confirma.

## Exercício 4: O carrinho da loja do jogo

Na loja de um jogo, compras itens com moedas, e tens 500 moedas. Todos os itens da loja custam pelo menos 1 moeda. Escreve o script `carrinho.py`, que pede o preço de cada item que queres comprar, até escreveres 0. No fim, mostra quantos itens tens no carrinho e o total. Depois diz se as tuas moedas chegam e quantas sobram, ou que não chegam e quantas faltam.

a) Explica numa frase porque é que o 0 pode ser a sentinela deste programa.

b) Completa no caderno o resultado esperado de cada caso, calculado à mão a partir do enunciado:

| Preços escritos, por ordem | Itens | Total | Chegam? | Sobram ou faltam |
| --- | ---: | ---: | --- | --- |
| 120, 250, 80, 0 | | | | |
| 300, 250, 0 | | | | |
| 500, 0 | | | | |
| 0 | | | | |

c) Escreve o script e corre-o com os quatro casos, para confirmar a tabela.

## Exercício 5: Encontrar o erro

O script `recompensas.py` devia escrever a recompensa de cada dia de uma semana num jogo. Quem entra todos os dias ganha 10 moedas no dia 1, 20 no dia 2, e assim por diante, sempre mais 10. No fim, devia escrever o total da semana. Tem três erros, de propósito.

```python
# recompensas.py: escreve a recompensa de cada dia de uma semana e o total da semana.
# Este script tem três erros, de propósito.
DIAS = 7
MOEDAS_POR_DIA = 10

total = 0
for dia in Range(1, DIAS + 1):
    moedas = DIAS * MOEDAS_POR_DIA
    print("Dia", dia, "dá", moedas, "moedas")
    total = moedas
print("Total da semana:", total, "moedas")
```

O ecrã devia ser este:

```text
Dia 1 dá 10 moedas
Dia 2 dá 20 moedas
Dia 3 dá 30 moedas
Dia 4 dá 40 moedas
Dia 5 dá 50 moedas
Dia 6 dá 60 moedas
Dia 7 dá 70 moedas
Total da semana: 280 moedas
```

Copia o script para o ficheiro `recompensas.py` e corre-o. Para cada erro que encontrares, segue a rotina e escreve no caderno:

1. O que aconteceu, e que tipo de erro é: de sintaxe, de execução ou de lógica. Se houver uma mensagem, copia a última linha e a linha que ela aponta. Se não houver, escreve a primeira linha do ecrã que é diferente da esperada.
2. Numa frase, o que achas que causa o erro.
3. Como confirmaste essa frase.
4. A linha que mudaste, e como ficou. Muda o mínimo possível.
5. O que aconteceu quando voltaste a correr.

Quando o ecrã for igual ao esperado, muda `DIAS` para 3 e corre outra vez. Antes de correres, escreve o ecrã que esperas.

## Apoio

- Exercício 1: na alínea a), não pares quando o ecrã mostra a última linha das vidas. Continua até o teste dar `False`. Na alínea b), lembra-te do que acontece ao segundo número do `range`. Na alínea c), um `range` só com um número começa onde?
- Exercício 2: a condição do `while` é a de um número que não dá. Repara que o 2 e o 6 são aceites. Para contar as respostas recusadas, pensa em que linha do programa sabes que uma resposta foi recusada.
- Exercício 3: o número de séries lido no início serve para duas coisas. Uma é o número de voltas. Qual é a outra? Com 0 séries, confirma que os três resultados fazem sentido e que o script não dá erro.
- Exercício 4: é o padrão da bilheteira do guia, com a mesma sentinela, o 0. O que muda é o que fazes depois do ciclo. O caso de 500 moedas exatas está na tabela por alguma razão.
- Exercício 5: o Python só mostra uma mensagem depois de corrigires a anterior. Dois dos erros não dão mensagem nenhuma: só os encontras se comparares o ecrã com o esperado, linha a linha. Uma linha de observação pode ajudar.

## Desafio opcional

Traduz para Python o teu algoritmo do [projeto 2, Adivinha o número](../01-algoritmos/05-projeto-2-adivinha-o-numero.md), que está no teu portefólio, no script `adivinha.py`. Usa os casos da tua tabela de casos esperados do projeto, e confirma que o programa dá o mesmo que o algoritmo. Se o teu algoritmo usa `Parar`, troca-o por uma bandeira, porque o `Parar` só chega ao Python no tema seguinte.

As mensagens do enunciado têm de aparecer palavra por palavra, como "Acertaste à tentativa 3!", sem nenhum espaço antes do ponto de exclamação. Com o `print` e as vírgulas, isso não acontece. O guia [02 Dados e interação](02-dados-e-interacao.md) mostra como se junta um número a um texto sem espaços.

## Para ires mais longe

Esta secção é opcional e fica fora da parte obrigatória.

### Mais longe 1: O mesmo ciclo com `while`

Escreve o `lancamentos_while.py`, que faz o mesmo que o `lancamentos.py` do exercício 3, mas com um ciclo `while` no lugar do `for`.

a) Escreve as três peças do teu `while`: a inicialização, a condição e a atualização.

b) Corre os três casos do exercício 3 nos dois scripts e confirma que dão o mesmo.

c) Explica numa ou duas frases qual dos dois preferes para este problema, e porquê.

## Critérios de conclusão

- O exercício 1 tem as três tabelas, ou a forma que escolheste na alínea c). A tabela observada da alínea a) é igual à prevista.
- Os scripts `jogadores_ciclo.py`, `lancamentos.py` e `carrinho.py` correm e dão os resultados das tabelas, que preencheste antes de correr.
- O `recompensas.py` dá o ecrã esperado com 7 dias e com 3 dias. Tens no caderno a rotina de cada um dos três erros, com o tipo de cada um.

## Autoavaliação

1. Que parte dos ciclos ainda te faz hesitar? Pode ser o fim do `range`, o sítio da leitura numa sentinela, a indentação do corpo, ou outra.
2. No exercício 5, qual dos três erros foi o mais difícil de encontrar, e porquê?
3. Antes de correres um ciclo, já consegues dizer quantas voltas vai dar?

![Rodapé](../imagens/rodape.png)
