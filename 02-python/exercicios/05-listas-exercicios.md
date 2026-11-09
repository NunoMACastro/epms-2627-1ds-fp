![Cabeçalho](../../imagens/cabecalho.png)

# Ficha de exercícios: Listas

Praticas a leitura dos índices e os percursos de listas para contar, somar, mudar, procurar e saltar valores. Os exercícios 1 a 7 são obrigatórios. Cada script fica na pasta `fp-python` e abre com um comentário a dizer o que faz. Decide de cabeça o resultado de cada caso antes de o correres. Para rever: o [guia do tema](../05-listas.md) e o [laboratório](../laboratorios/05-listas-laboratorio.md).

## Exercício 1: Os índices de uma lista

Num jogo de corridas, fizeste quatro tentativas numa pista. O tempo de cada tentativa, em segundos, ficou nesta lista:

```python
tempos = [42, 38, 45, 40]
```

a) Prevê o que dá cada uma destas linhas e confirma-o na consola do Python:

- `tempos[0]`
- `tempos[3]`
- `len(tempos)`
- `tempos[len(tempos) - 1]`
- `tempos[1] + tempos[2]`
- `tempos[4]`

Este exercício faz-se só na consola, sem ficheiro. Abre a consola do Python, no terminal, com o teu comando, e guarda nela a lista. Na linha que der erro, lê a última linha da mensagem: como se chama esse erro, e é de sintaxe, de execução ou de lógica?

b) Em que tentativa fizeste o melhor tempo, o mais baixo, contando a primeira como tentativa 1? Qual é o índice desse elemento na lista?

c) Prevê como fica a lista depois de `tempos[2] = 39` e confirma-o na consola.

Rever: [O índice é a posição de cada elemento](../05-listas.md#o-índice-é-a-posição-de-cada-elemento) e [O `len` diz quantos elementos tem a lista](../05-listas.md#o-len-diz-quantos-elementos-tem-a-lista).

## Exercício 2: As estrelas dos níveis

Num jogo de plataformas, cada nível dá de 0 a 3 estrelas. As estrelas que a Inês ganhou nos níveis que já jogou estão nesta lista:

```python
estrelas = [3, 2, 3, 0, 1, 3, 2, 3]
```

Escreve o script `estrelas_niveis.py`, que mostra três coisas. A primeira é quantos níveis têm 3 estrelas. A segunda é o total de estrelas. A terceira é quantas estrelas faltam para ter 3 em todos os níveis jogados. O script tem de funcionar para uma lista com qualquer número de níveis, por isso não escrevas o 8 em lado nenhum. Experimenta-o também com as listas `[]` e `[3]`.

Rever: [Percorrer a lista pelo valor, com `for`](../05-listas.md#percorrer-a-lista-pelo-valor-com-for) , [O `len` diz quantos elementos tem a lista](../05-listas.md#o-len-diz-quantos-elementos-tem-a-lista) e [Exemplo guiado: os jogos da equipa](../05-listas.md#exemplo-guiado-os-jogos-da-equipa).

<details>
<summary>Pista</summary>

O contador e o acumulador podem estar no mesmo ciclo.

</details>

## Exercício 3: Os dias em que o Duarte chegou à meta

O telemóvel do Duarte conta os passos de cada dia. Os passos da última semana, de segunda a domingo, estão nesta lista:

```python
passos = [6200, 8000, 10450, 3900, 7999, 12100, 7500]
```

O Duarte tem uma meta de 8000 passos por dia. Chega à meta num dia em que dá 8000 passos ou mais.

Escreve o script `passos_meta.py`, que mostra os dias em que o Duarte chegou à meta, contando a segunda-feira como dia 1. Cada dia aparece numa linha como, por exemplo, `Dia 4 com 9150 passos`. No fim, o script mostra quantos dias foram, numa linha como, por exemplo, `Dias com a meta cumprida: 2`. Experimenta-o também com as listas `[]`, `[8000]` e `[7999]`.

Rever: [Escolher entre o valor e o índice](../05-listas.md#escolher-entre-o-valor-e-o-índice).

## Exercício 4: Os saldos da loja

Na loja de um jogo, as skins custam moedas do jogo. Os preços estão nesta lista:

```python
precos = [1500, 800, 1000, 2400, 600]
```

Começaram os saldos: as skins que custam mais de 1000 moedas passam a custar metade. As outras ficam com o preço que tinham. Os preços são sempre números inteiros de moedas.

Escreve o script `saldos.py`, que muda os preços da lista e, no fim, mostra a lista com uma linha como `Preços com os saldos: [...]`. Experimenta-o também com as listas `[]`, `[1000]` e `[1200]`.

Rever: [Mudar um elemento pelo índice](../05-listas.md#mudar-um-elemento-pelo-índice).

<details>
<summary>Pista</summary>

Compara a lista que aparece com a que esperavas, número a número, também na forma como cada número está escrito.

</details>

## Exercício 5: O primeiro jogo que a equipa não ganhou

Uma equipa de um jogo online registou o resultado de cada jogo, pela ordem em que os jogou. Cada resultado é um texto de uma letra: `"V"` para vitória, `"E"` para empate e `"D"` para derrota.

```python
resultados = ["V", "V", "E", "D", "V", "D"]
```

Escreve o script `sem_vitoria.py`, que diz qual foi o primeiro jogo que a equipa não ganhou, numa linha como, por exemplo, `Primeiro jogo sem vitória: jogo 5`. Se a equipa ganhou todos os jogos, mostra `Nenhum jogo sem vitória.`. Com a lista vazia, mostra a mesma frase. O programa para de procurar logo que encontra o primeiro jogo que a equipa não ganhou.

Experimenta-o com estas cinco listas:

- `["V", "V", "E", "D", "V", "D"]`
- `["D"]`
- `["V", "V", "E"]`
- `["V", "V"]`
- `[]`

Rever: [Procurar um valor com uma bandeira](../05-listas.md#procurar-um-valor-com-uma-bandeira) e [Parar a pesquisa com `break`](../05-listas.md#parar-a-pesquisa-com-break).

<details>
<summary>Pista</summary>

Antes de escreveres o `if`, pode ajudar escrever num comentário, por palavras, que resultados fazem o programa parar.

</details>

## Exercício 6: A média sem as faltas

As notas dos testes de um aluno estão nesta lista, pela ordem dos testes. Num teste a que o aluno faltou, a nota ficou registada como -1:

```python
notas = [14, -1, 12, 16, -1]
```

Escreve o script `media_testes.py`, que mostra duas linhas, como, por exemplo, `Testes feitos: 2` e `Média dos testes feitos: 13.5`. Os testes a que faltou não contam para nada. Usa o `continue` para os saltar.

Experimenta-o com as listas `[14, -1, 12, 16, -1]`, `[15]`, `[-1, -1]` e `[]`. Em nenhum dos casos o programa pode parar com um erro. Quando não há média para mostrar, mostra, no lugar dessa linha, uma frase que o explique.

Rever: [Saltar uma volta com `continue`](../05-listas.md#saltar-uma-volta-com-continue) e [A lista vazia e os três casos de teste](../05-listas.md#a-lista-vazia-e-os-três-casos-de-teste).

<details>
<summary>Pista</summary>

Antes de dividires, pergunta-te se o número por que divides pode ser zero.

</details>

## Exercício 7: Encontrar o erro

O script `inventario.py` devia dizer se algum item do inventário de um jogo acabou, isto é, se algum tem 0 unidades. Cada elemento da lista é o número de unidades de um item. O script tem dois erros, de propósito.

```python
# inventario.py: diz se algum item do inventário de um jogo acabou, isto é, tem 0 unidades.
# Este script tem dois erros, de propósito.
unidades = [3, 0, 5, 2]
for i in range(0, len(unidades) - 1):
    acabou = False
    if unidades[i] == 0:
        acabou = True
if acabou:
    print("Há itens que acabaram.")
else:
    print("Nenhum item acabou.")
```

Os resultados esperados são estes:

| Lista | Resultado esperado |
| --- | --- |
| `[3, 0, 5, 2]` | Há itens que acabaram. |
| `[3, 5, 0]` | Há itens que acabaram. |
| `[4, 1]` | Nenhum item acabou. |
| `[]` | Nenhum item acabou. |

Copia o script para o ficheiro `inventario.py`, corre-o com as quatro listas e corrige-o, mudando o mínimo possível. Para cada erro, escreve a rotina da depuração num comentário no fim do script. Diz o caso que falhou, o resultado esperado, o obtido e o tipo de erro nesse caso. Diz também a causa que suspeitas, como a confirmaste, a linha que mudaste e o que se viu ao voltares a correr as quatro listas.

Rever: [Os três tipos de erro](../01-do-pseudocodigo-ao-python.md#os-três-tipos-de-erro) e [A lista vazia e os três casos de teste](../05-listas.md#a-lista-vazia-e-os-três-casos-de-teste).

<details>
<summary>Pista</summary>

Um dos erros aparece de duas maneiras, conforme a lista: com umas, o resultado sai errado sem mensagem, e com outra o programa para. Faz a tabela de iterações da lista `[3, 0, 5, 2]`, com uma coluna para `i` e outra para `acabou`.

</details>

## Desafios

### Desafio 1: Os dias com melhorias

O Duarte quer saber em que dias da semana deu mais passos do que no dia anterior. Escreve o script `melhorias.py`, que usa a lista de passos do exercício 3. Para cada um desses dias, mostra uma linha como, por exemplo, `Dia 4 com 9150 passos, mais do que no dia anterior`. No fim, mostra quantos dias foram. Testa também com `[]`, `[5000]`, `[3000, 3000]` e `[5000, 3000]`.

Rever: [Escolher entre o valor e o índice](../05-listas.md#escolher-entre-o-valor-e-o-índice).

### Desafio 2: O último jogo com golos

Os golos que uma equipa marcou em cada jogo estão na lista `golos = [2, 0, 1, 0, 0]`. Escreve o script `ultimo_golo.py`, que diz em que jogo a equipa marcou pela última vez, numa linha como, por exemplo, `Último jogo com golos: jogo 4`. Se a equipa nunca marcou, mostra `A equipa ainda não marcou.`. Testa com `[2, 0, 1, 0, 0]`, `[0, 0, 4]`, `[0, 0]` e `[]`. Explica, num comentário no início do script, se o teu programa usa o `break`, e porquê.

## Critérios de conclusão

- No exercício 1, confirmaste na consola o que dá cada linha.
- Os scripts `estrelas_niveis.py`, `passos_meta.py`, `saldos.py`, `sem_vitoria.py` e `media_testes.py` correm e dão os resultados pedidos, em todas as listas de teste.
- O `inventario.py` dá os quatro resultados esperados, e o comentário do fim tem a rotina de cada erro.

![Rodapé](../../imagens/rodape.png)
