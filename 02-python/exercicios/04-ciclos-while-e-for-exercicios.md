![Cabeçalho](../../imagens/cabecalho.png)

# Ficha de exercícios: Ciclos while e for

Praticas a previsão das voltas de um ciclo, a validação repetida, a sentinela, o contador, o acumulador e o `for` com `range`. Os exercícios 1 a 5 são obrigatórios. Os teus scripts ficam na pasta `fp-python`, e cada um abre com um comentário a dizer o que faz. Antes de correres um caso, decide de cabeça o resultado. Para rever: o [guia do tema](../04-ciclos-while-e-for.md) e o [laboratório](../laboratorios/04-ciclos-while-e-for-laboratorio.md).

## Exercício 1: Quantas voltas?

Para cada programa, descobre, sem o correr, quantas voltas dá o ciclo e o que aparece no ecrã. Copia o programa para um ficheiro com o nome da primeira linha, e escreve a tua resposta num comentário a seguir à primeira linha. Depois confirma-a no computador.

a) Completa a tabela de iterações, com as linhas que faltam até ao teste que dá `False`. Diz também quanto vale `vidas` depois do ciclo.

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
# niveis.py: escreve os níveis de um jogo.
for nivel in range(2, 6):
    print("Nível", nivel)
print("Acabaram os níveis")
```

| Volta | nivel | Escreve |
| --- | ---: | --- |

c) Aqui decides tu a forma: uma tabela como as anteriores, ou outra que mostre o que acontece em cada volta.

```python
# range_quatro.py: escreve múltiplos de 5.
for i in range(4):
    print(i * 5)
```

d) No programa da alínea a), com linhas de observação, confirma no computador a tua tabela.

Rever: [Repetir com `while`](../04-ciclos-while-e-for.md#repetir-com-while), [Contar voltas com `for` e `range`](../04-ciclos-while-e-for.md#contar-voltas-com-for-e-range), [As duas formas do `Para` e o `range`](../04-ciclos-while-e-for.md#as-duas-formas-do-para-e-o-range) e [Ver as voltas com linhas de observação](../04-ciclos-while-e-for.md#ver-as-voltas-com-linhas-de-observação).

<details>
<summary>Pista</summary>

Na alínea b), lembra-te do que acontece ao segundo número do `range`. Na alínea c), um `range` só com um número começa onde?

</details>

## Exercício 2: O número de jogadores

Um jogo de tabuleiro joga-se com 2 a 6 jogadores, incluindo o 2 e o 6. Escreve o script `jogadores_ciclo.py`, que pergunta quantos jogadores há. Enquanto o número não der, escreve "Esse número não dá. Escreve de 2 a 6:" e pergunta outra vez. Quando o número for aceite, escreve uma linha como "Jogo para 4 jogadores". No fim, escreve também quantas respostas foram recusadas, como "Respostas recusadas: 2".

Experimenta-o com estas entradas:

| Valores escritos, por ordem |
| --- |
| 4 |
| 2 |
| 6 |
| 1, 7, 4 |

Rever: [A validação repetida pede o valor outra vez](../04-ciclos-while-e-for.md#a-validação-repetida-pede-o-valor-outra-vez) e [O contador e o acumulador](../04-ciclos-while-e-for.md#o-contador-e-o-acumulador).

<details>
<summary>Pista</summary>

Para contar as respostas recusadas, pensa em que linha do programa sabes que uma resposta foi recusada.

</details>

## Exercício 3: O treino de lançamentos

Num treino de basquetebol, fazes séries de 10 lançamentos ao cesto. Uma série é boa quando marcas 7 cestos ou mais. Escreve o script `lancamentos.py`, que pergunta quantas séries fizeste e depois quantos cestos marcaste em cada uma, como "Cestos da série 1?". Quem usa o programa escreve sempre um número de 0 a 10. No fim, o script mostra três coisas:

- o total de cestos;
- quantas séries foram boas;
- quantos lançamentos falhaste, ao todo.

Experimenta-o com 4 séries de 8, 5, 7 e 10 cestos, com 0 séries, e com 1 série de 6 cestos.

Rever: [Um `for` com um número lido do teclado](../04-ciclos-while-e-for.md#um-for-com-um-número-lido-do-teclado) e [Contar só algumas voltas](../04-ciclos-while-e-for.md#contar-só-algumas-voltas).

<details>
<summary>Pista</summary>

Quantos lançamentos fizeste, ao todo?

</details>

## Exercício 4: O carrinho da loja do jogo

Na loja de um jogo, compras itens com moedas, e tens 500 moedas. Todos os itens da loja custam pelo menos 1 moeda. Escreve o script `carrinho.py`, que pede o preço de cada item que queres comprar, até escreveres 0. No fim, mostra quantos itens tens no carrinho e o total. Depois diz se as tuas moedas chegam e quantas sobram, ou que não chegam e quantas faltam.

Experimenta-o com estes casos:

| Preços escritos, por ordem |
| --- |
| 120, 250, 80, 0 |
| 300, 250, 0 |
| 500, 0 |
| 0 |

Num comentário no início do script, explica numa frase porque é que o 0 pode ser a sentinela deste programa.

Rever: [Ler até à sentinela](../04-ciclos-while-e-for.md#ler-até-à-sentinela) e [O contador e o acumulador](../04-ciclos-while-e-for.md#o-contador-e-o-acumulador).

<details>
<summary>Pista</summary>

O que muda em relação à bilheteira do guia é o que fazes depois do ciclo.

</details>

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

Copia o script para o ficheiro `recompensas.py` e corrige-o até o ecrã ser igual ao esperado, mudando o mínimo possível. Para cada erro, segue a rotina da depuração e escreve, num comentário no fim do script, o que aconteceu e o tipo de erro. Quando não há mensagem, diz a primeira linha do ecrã que é diferente da esperada. Diz também a causa que suspeitas, como a confirmaste, a linha que mudaste e o que aconteceu ao correr de novo.

Quando o ecrã for igual ao esperado, muda `DIAS` para 3 e confirma que o ecrã é o que esperas.

Rever: [Os três tipos de erro](../01-do-pseudocodigo-ao-python.md#os-três-tipos-de-erro) e [Ver as voltas com linhas de observação](../04-ciclos-while-e-for.md#ver-as-voltas-com-linhas-de-observação).

<details>
<summary>Pista</summary>

Dois dos erros não dão mensagem nenhuma: só os encontras se comparares o ecrã com o esperado, linha a linha. Uma linha de observação pode ajudar.

</details>

## Desafios

### Desafio 1: O adivinha o número em Python

Escreve o script `adivinha.py`, que traduz para Python o teu algoritmo do [projeto 2, Adivinha o número](../../01-algoritmos/projetos-guiados/05-projeto-2-adivinha-o-numero.md), que tens no portefólio. Usa os casos da tua tabela de casos esperados do projeto, e confirma que o programa dá o mesmo que o algoritmo. Se o teu algoritmo usa `Parar`, troca-o por uma bandeira, porque o `Parar` só chega ao Python no tema seguinte.

As mensagens do enunciado do projeto têm de aparecer palavra por palavra, como "Acertaste à tentativa 3!", sem nenhum espaço antes do ponto de exclamação. Com o `print` e as vírgulas, isso não acontece. Rever: [Juntar textos com `+` e `str`](../02-dados-e-interacao.md#juntar-textos-com--e-str).

### Desafio 2: O mesmo ciclo com `while`

Escreve o `lancamentos_while.py`, que faz o mesmo que o `lancamentos.py` do exercício 3, mas com um ciclo `while` no lugar do `for`. Nos três casos do exercício 3, os dois scripts têm de dar o mesmo. Num comentário no início do `lancamentos_while.py`, responde a duas perguntas.

a) Quais são as três peças do teu `while`: a inicialização, a condição e a atualização?

b) Qual dos dois ciclos preferes para este problema, e porquê? Responde numa ou duas frases.

## Critérios de conclusão

- No exercício 1, cada programa tem, num comentário a seguir à primeira linha, a tua tabela, ou a forma que escolheste na alínea c).
- A tabela observada da alínea d) é igual à tua da alínea a).
- Os scripts `jogadores_ciclo.py`, `lancamentos.py` e `carrinho.py` correm e dão o resultado certo em todos os casos de teste. O `carrinho.py` tem o comentário sobre a sentinela.
- O `recompensas.py` dá o ecrã certo, também com `DIAS` a 3, e o comentário do fim tem a rotina de cada erro.

![Rodapé](../../imagens/rodape.png)
