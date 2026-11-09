![Cabeçalho](../../imagens/cabecalho.png)

# Ficha de exercícios: Repetição e arrays

Contas as voltas de um ciclo, usas índices, contas e somas ao percorrer um array, e calculas uma média, mesmo quando não há valores. Lês valores até uma sentinela, procuras um valor com `Parar` e encontras o erro de um ciclo. Os exercícios 1 a 7 são obrigatórios. Precisas de papel e lápis para as tabelas de iterações, e entregas em papel ou num ficheiro de texto. Os algoritmos podem escrever-se em frases claras, que digam o que se repete e até quando. Para rever: o [guia do tema](../04-repeticao-e-arrays.md).

## Exercício 1: Quantas voltas?

Para cada ciclo, diz quantas voltas dá, o que aparece no ecrã e com que valor da variável é feito o último teste.

a) Copia a tabela de iterações e acrescenta as linhas que faltam, até ao teste que dá falso.

```text
int x = 10
Enquanto x > 0
    Escreve: x
    x = x - 3
```

| Teste | x | Condição | Durante a iteração |
| --- | ---: | --- | --- |
| 1.º | 10 | `10 > 0` dá `true` | escreve 10 |
| 2.º | 7 | `7 > 0` dá `true` | escreve 7 |

b) Faz a tabela de iterações toda, com estas colunas.

```text
Para i de 1 até 4
    Escreve: i * 2
```

| Teste | i | Condição | Durante a iteração |
| --- | ---: | --- | --- |

c) Segue este ciclo sem tabela já feita, como preferires.

```text
Para i = 0, i < 3, i++
    Escreve: i
```

Rever: [Enquanto: repetir enquanto a condição for verdadeira](../04-repeticao-e-arrays.md#enquanto-repetir-enquanto-a-condição-for-verdadeira) e [Para: o ciclo contado](../04-repeticao-e-arrays.md#para-o-ciclo-contado).

<details>
<summary>Pista</summary>

Na alínea b), escreve, na coluna da condição, a comparação que o "até" quer dizer.

</details>

## Exercício 2: Os índices de um array

Os minutos de atraso do autocarro da escola em cinco dias ficaram guardados neste array:

```text
atrasos = [5, 9, 0, 3, 7]
```

a) Quanto vale `atrasos[0]`? E `atrasos[4]`?

b) Qual é o último índice válido deste array? Explica como chegas a ele.

c) O que aparece no ecrã com `Escreve: atrasos[1] + atrasos[3]`?

d) O que acontece com `Escreve: atrasos[5]`?

e) Em que dia é que o autocarro não teve atraso, contando o primeiro dia como dia 1? E qual é o índice desse elemento no array?

Rever: [O índice](../04-repeticao-e-arrays.md#o-índice) e [Percorrer um array com `Para`](../04-repeticao-e-arrays.md#percorrer-um-array-com-para).

<details>
<summary>Pista</summary>

Escreve os índices por baixo dos elementos. Na alínea e), lembra-te de como o guia passa do índice para o número do jogo.

</details>

## Exercício 3: Contar num intervalo

As alturas, em centímetros, dos jogadores de uma equipa de voleibol estão neste array:

```text
alturas = [172, 165, 181, 158, 175, 169]
```

a) Escreve um algoritmo que conte quantos jogadores medem entre 165 e 175 centímetros, incluindo os extremos, e mostre o resultado. Depois segue-o com o array do enunciado, numa tabela com estas colunas:

| Volta | altura | Condição do `Se` | jogadores no fim da volta |
| --- | ---: | --- | ---: |

b) Diz quando é que o teu ciclo termina, e porquê.

c) Sem mudar o algoritmo, diz o que ele mostra se o array for `[]` e se for `[170]`.

Rever: [O contador](../04-repeticao-e-arrays.md#o-contador) e [Intervalos](../03-decisoes-e-validacao.md#intervalos).

<details>
<summary>Pista</summary>

Antes de escreveres a condição, marca no array as alturas que devem ser contadas.

</details>

## Exercício 4: A média de estudo

Uma aluna registou num array os minutos que estudou em cada dia da semana. Nos dias em que não estudou, registou 0:

```text
minutosDeEstudo = [30, 45, 0, 60, 15]
```

a) Escreve um algoritmo que mostre o total de minutos da semana e a média dos dias em que ela estudou. Os dias com 0 minutos não contam para a média. Não escrevas no algoritmo um número fixo para os dias, porque o algoritmo conta-os dentro do ciclo. Calcula à mão o total e a média, e depois segue o algoritmo para confirmares.

b) O mesmo algoritmo tem de funcionar se a aluna não tiver estudado em nenhum dia, como em `[0, 0, 0, 0, 0]`. Tem de funcionar também se o array estiver vazio. Em nenhum dos dois casos pode fazer uma conta impossível. O que mostra em cada um?

Rever: [A média só se calcula quando há valores](../04-repeticao-e-arrays.md#a-média-só-se-calcula-quando-há-valores).

<details>
<summary>Pista</summary>

Que dias deve contar o contador? Qual das formas de percorrer funciona com um array vazio?

</details>

## Exercício 5: A duração da playlist

O Rui quer saber quanto dura a sua playlist. O Rui escreve a duração de cada música em segundos, uma de cada vez, e escreve 0 quando acabar. Nenhuma música dura 0 segundos.

a) Escreve um algoritmo que mostre quantas músicas tem a playlist e quanto dura ao todo. A duração aparece em minutos e segundos, como "3 min e 5 s".

b) As músicas duram 200, 185 e 240 segundos. Antes de fazeres a tabela, calcula à mão a duração total, primeiro em segundos e depois em minutos e segundos. Depois faz a tabela de iterações para essas três durações, seguidas do 0, e confirma o que calculaste.

c) O que mostra o algoritmo se o Rui escrever logo 0?

Rever: [A sentinela: ler até aparecer o valor que diz "acabou"](../04-repeticao-e-arrays.md#a-sentinela-ler-até-aparecer-o-valor-que-diz-acabou) e [Operadores aritméticos](../02-estado-sequencia-representacoes.md#operadores-aritméticos).

<details>
<summary>Pista</summary>

Que contas do guia 02 separam os minutos completos dos segundos que sobram? Em que momento do algoritmo já tens o total todo?

</details>

## Exercício 6: Procurar um cacifo

Os números dos cinco cacifos ocupados no corredor estão neste array:

```text
ocupados = [12, 23, 7, 31, 18]
```

a) Escreve um algoritmo que lê um número de cacifo e o procura no array. Se o encontrar, escreve em que posição está, contando a primeira posição como 1, e para de procurar. Se não o encontrar, escreve "Cacifo livre". Usa `Parar` e uma bandeira, como no guia.

b) Antes de seguires o algoritmo, olha para o array e prevê o que deve acontecer com os cacifos 23, 18 e 40. Para cada um, prevê a posição, ou se está livre, e quantas voltas dá o ciclo. Depois segue o teu algoritmo só com o 18 e com o 40, e confirma as voltas e o que aparece no ecrã.

Rever: [Parar e Continuar](../04-repeticao-e-arrays.md#parar-e-continuar).

<details>
<summary>Pista</summary>

Com qual das duas formas de percorrer um array sabes a posição de cada elemento? Depois do ciclo, o que te diz se o cacifo foi encontrado?

</details>

## Exercício 7: Encontrar o erro

Este algoritmo tem um erro. Para o encontrares e corrigires, segue estes passos:

1. Calcula à mão o que o algoritmo devia mostrar, a partir do enunciado e dos dados. Depois faz a tabela de iterações e escreve o que ele mostra.
2. Escreve numa frase o que achas que causa a diferença.
3. Aponta na tabela a volta ou o teste que confirma a tua frase.
4. Corrige a linha que causa o erro, mudando o mínimo possível.
5. Segue outra vez a versão corrigida, confirma que mostra o que calculaste à mão e diz numa frase o que mudou.

O algoritmo devia somar a chuva, em milímetros, de quatro dias:

```text
const NUMERO_DE_DIAS = 4
milimetrosDeChuva = [3, 0, 12, 5]
int total = 0
Para i = 0, i < NUMERO_DE_DIAS, i++
    total = total + i
Escreve: "Chuva total: ", total, " mm"
```

Rever: [A tabela de iterações](../04-repeticao-e-arrays.md#a-tabela-de-iterações).

<details>
<summary>Pista</summary>

Faz uma coluna para cada variável. No fim de cada volta, compara `total` com a soma que fizeste à mão até esse dia.

</details>

## Desafios

### Desafio 1: Os pontos de duas equipas

Os pontos de duas equipas em três jogos de um torneio estão guardados numa tabela, uma linha por equipa:

```text
pontos = [[3, 1, 0], [1, 1, 3]]
```

a) Quanto vale `pontos[1][2]`? E `pontos[0][0]`?

b) Escreve um algoritmo com dois `Para`, um dentro do outro, que mostre o total de pontos de cada equipa. O ecrã deve mostrar "Equipa 1: 4 pontos" e "Equipa 2: 5 pontos".

c) No guia viste que um acumulador inicializado dentro do ciclo é um erro. No teu algoritmo, onde é que o total de cada equipa tem de começar em 0? Explica a que ciclo se aplica a regra do guia.

Rever: [Um array de arrays lê-se como uma tabela](../04-repeticao-e-arrays.md#um-array-de-arrays-lê-se-como-uma-tabela).

### Desafio 2: A contagem do lançamento

Este algoritmo devia fazer a contagem decrescente de um lançamento, de 5 até 1. Logo a seguir ao 3, devia escrever "Meio caminho!", e no fim devia escrever "Partida!". Tem um erro. Segue os cinco passos do exercício 7 para o encontrar e corrigir.

```text
int contagem = 5
Enquanto contagem > 0
    Escreve: contagem
    Se contagem == 3
        Escreve: "Meio caminho!"
        contagem = contagem - 1
Escreve: "Partida!"
```

Rever: [A tabela de iterações](../04-repeticao-e-arrays.md#a-tabela-de-iterações).

<details>
<summary>Pista</summary>

Compara cada linha com a anterior. O que mudou? Podes parar quando já souberes o que acontece a seguir.

</details>

## Critérios de conclusão

- No exercício 1, seguiste cada ciclo até ao teste que dá falso, e disseste as voltas, o ecrã e o valor da variável nesse teste.
- No exercício 2, explicaste como se chega ao último índice válido, disseste o que acontece com `atrasos[5]` e passaste do índice para o dia.
- No exercício 3, a tabela dá o resultado certo, e disseste quando o ciclo termina e o que ele mostra com `[]` e com `[170]`.
- No exercício 4, o algoritmo dá o total e a média que calculaste à mão, só com os dias em que ela estudou. Os dois casos da alínea b) não fazem nenhuma conta impossível.
- No exercício 5, a tabela e o ecrã dão o que calculaste à mão, sem tratar a sentinela como um dado. Disseste o que aparece com 0 logo de início.
- No exercício 6, previste os três cacifos, e o algoritmo confirma o 18 e o 40, com `Parar` e uma bandeira.
- No exercício 7, seguiste os cinco passos, e a versão corrigida mostra o que calculaste à mão.
- Inicializaste os contadores e os acumuladores antes do ciclo.

![Rodapé](../../imagens/rodape.png)
