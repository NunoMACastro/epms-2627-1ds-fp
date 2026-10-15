![Cabeçalho](../imagens/cabecalho.png)

# Ficha de exercícios: Repetição e arrays

Ficha do tema Repetição e arrays, do módulo Desenvolver algoritmos. Treinas o que aprendeste no guia, uma ideia em cada exercício. Contas as voltas de um ciclo e usas os índices de um array. Contas e somas ao percorrer um array, e calculas uma média sem dividir por zero. Lês também valores até uma sentinela, procuras um valor com `Parar` e encontras os erros de dois ciclos. Cerca de 132 minutos, para fazeres sozinho: 112 na parte obrigatória e 20 no desafio opcional.

## O que precisas de saber

O [guia do tema](04-repeticao-e-arrays.md). Antes de começar, deves conseguir explicar:

- as três peças de um ciclo;
- porque é que os índices começam em 0;
- a diferença entre um contador e um acumulador;
- porque é que a sentinela se lê antes do ciclo e no fim do corpo.

Se alguma destas ideias não estiver clara, volta à secção do guia que a explica. São as secções "As três peças de um ciclo", "O índice", "Contadores e acumuladores" e "A sentinela: ler até aparecer o valor que diz "acabou"". Para o exercício 5 precisas também do `div` e do `resto`, do [guia 02](02-estado-sequencia-representacoes.md), secção "Operadores aritméticos".

O [laboratório](04-repeticao-e-arrays-laboratorio.md) deste tema é de fluxogramas, e é opcional. Os desenhos de fluxogramas não fazem parte desta ficha. Se o professor indicar o laboratório, é lá que os desenhas.

## Como trabalhar

Resolve os exercícios pela ordem. Cada um treina uma ideia do guia:

| Exercício | O que treina | Tempo |
| --- | --- | ---: |
| 1 | Contar as voltas de um ciclo, com a tabela de iterações | 12 min |
| 2 | Usar os índices de um array | 10 min |
| 3 | Contar os valores de um array que cumprem uma regra | 15 min |
| 4 | Contar e somar no mesmo ciclo, e calcular uma média sem dividir por zero | 15 min |
| 5 | Ler valores até uma sentinela | 20 min |
| 6 | Procurar um valor num array, com `Parar` e uma bandeira | 20 min |
| 7 | Encontrar e corrigir o erro de um ciclo | 20 min |
| Total da parte obrigatória | Exercícios 1 a 7 | 112 min |
| Desafio opcional | Percorrer uma tabela com dois `Para` | 20 min |

Os exercícios 1 a 7 são obrigatórios e cabem nos 112 minutos. O desafio é para quem terminar e quiser mais prática, ou para estudares em casa, e não conta para concluíres a ficha.

Escreve os algoritmos na forma que usamos nas aulas, com a indentação a mostrar o que está dentro de cada ciclo. Um array escreve-se como uma lista de Python, sem tipo à frente. Se souberes a lógica e não te lembrares da forma, escreve frases claras, que também valem. Têm de dizer o que se repete, até quando, e o que muda de uma volta para a seguinte.

Nas tabelas de iterações, segue as regras do guia. Faz uma linha por cada teste da condição, com a fotografia das variáveis nesse momento, e continua até ao teste que dá falso. No exercício 1 a), a tabela já vem começada. Na alínea b), recebes só as colunas, e fazes a tabela toda. Na alínea c) e nos exercícios seguintes, escolhes tu como seguir o ciclo.

Precisas de papel, de preferência quadriculado, e de lápis. Entregas as respostas em papel ou num ficheiro de texto, com as tabelas de iterações.

## Exercício 1: Quantas voltas? (12 minutos)

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

c) Escolhe tu como seguir este ciclo.

```text
Para i = 0, i < 3, i++
    Escreve: i
```

## Exercício 2: Os índices de um array (10 minutos)

Os minutos de atraso do autocarro da escola em cinco dias ficaram guardados neste array:

```text
atrasos = [5, 9, 0, 3, 7]
```

a) Quanto vale `atrasos[0]`? E `atrasos[4]`?

b) Qual é o último índice válido deste array? Explica como chegas a ele.

c) O que aparece no ecrã com `Escreve: atrasos[1] + atrasos[3]`?

d) O que acontece com `Escreve: atrasos[5]`?

e) Em que dia é que o autocarro não teve atraso, contando o primeiro dia como dia 1? E qual é o índice desse elemento no array?

## Exercício 3: Contar num intervalo (15 minutos)

As alturas, em centímetros, dos jogadores de uma equipa de voleibol estão neste array:

```text
alturas = [172, 165, 181, 158, 175, 169]
```

a) Escreve um algoritmo que conte quantos jogadores medem entre 165 e 175 centímetros, incluindo os extremos, e mostre o resultado.

b) Diz quando é que o teu ciclo termina, e porquê.

c) Sem mudar o algoritmo, diz o que ele mostra se o array for `[]` e se for `[170]`.

## Exercício 4: A média de estudo (15 minutos)

Uma aluna registou num array os minutos que estudou em cada dia da semana. Nos dias em que não estudou, registou 0:

```text
estudo = [30, 45, 0, 60, 15]
```

a) Escreve um algoritmo que mostre o total de minutos da semana e a média dos dias em que ela estudou. Os dias com 0 minutos não contam para a média. A aluna quer saber quanto tempo estuda, em média, num dia em que se senta a estudar. Não escrevas à mão quantos dias foram, porque o algoritmo conta-os dentro do ciclo. Antes de seguires o teu algoritmo, calcula à mão o total e a média.

b) O mesmo algoritmo tem de funcionar se a aluna não tiver estudado em nenhum dia, como em `[0, 0, 0, 0, 0]`. Tem de funcionar também se o array estiver vazio. Em nenhum dos dois casos pode fazer uma conta impossível. O que mostra em cada um?

## Exercício 5: A duração da playlist (20 minutos)

O Rui quer saber quanto dura a sua playlist. Escreve a duração de cada música em segundos, uma de cada vez, e escreve 0 quando acabar. Nenhuma música dura 0 segundos.

a) Escreve um algoritmo que mostre quantas músicas tem a playlist e quanto dura ao todo. A duração aparece em minutos e segundos, como "3 min e 5 s".

b) As músicas duram 200, 185 e 240 segundos. Antes de fazeres a tabela, calcula à mão a duração total, primeiro em segundos e depois em minutos e segundos. Depois faz a tabela de iterações para essas três durações, seguidas do 0, e confirma o que calculaste.

c) O que mostra o algoritmo se o Rui escrever logo 0?

## Exercício 6: Procurar um cacifo (20 minutos)

Os números dos cinco cacifos ocupados no corredor estão neste array:

```text
ocupados = [12, 23, 7, 31, 18]
```

a) Escreve um algoritmo que lê um número de cacifo e o procura no array. Se o encontrar, escreve em que posição está, contando a primeira posição como 1, e para de procurar. Se não o encontrar, escreve "Cacifo livre". Usa `Parar` e uma bandeira, como no guia.

b) Antes de seguires o algoritmo, olha para o array e prevê o que deve acontecer com os cacifos 23, 18 e 40. Para cada um, prevê a posição, ou se está livre, e quantas voltas dá o ciclo. Depois segue o teu algoritmo com os três e confirma as voltas e o que aparece no ecrã.

## Exercício 7: Encontrar o erro (20 minutos)

Cada um destes algoritmos tem um erro. Para cada um, segue estes passos:

1. Calcula à mão o que o algoritmo devia mostrar, a partir do enunciado. Depois faz a tabela de iterações e escreve o que ele mostra.
2. Escreve numa frase o que achas que causa a diferença.
3. Aponta na tabela a volta ou o teste que confirma a tua frase.
4. Corrige a linha que causa o erro, mudando o mínimo possível.
5. Segue outra vez a versão corrigida e confirma que mostra o que calculaste à mão.

a) Este algoritmo devia somar a chuva, em milímetros, de quatro dias:

```text
const NUMERO_DE_DIAS = 4
chuva = [3, 0, 12, 5]
int total = 0
Para i de 1 até NUMERO_DE_DIAS
    total = total + chuva[i]
Escreve: "Chuva total: ", total, " mm"
```

b) Este algoritmo devia fazer a contagem decrescente de um lançamento, de 10 até 1. Logo a seguir ao 5, devia escrever "Meio caminho!", e no fim devia escrever "Partida!":

```text
int contagem = 10
Enquanto contagem > 0
    Escreve: contagem
    Se contagem == 5
        Escreve: "Meio caminho!"
        contagem = contagem - 1
Escreve: "Partida!"
```

## Apoio

Se estiveres encravado, usa estas pistas pela ordem em que aparecem, e passa à seguinte só se a anterior não tiver chegado.

- Exercício 1. Na alínea a), não pares quando o ecrã mostra o último número: continua até o teste dar falso. Na alínea b), escreve por extenso, na coluna da condição, o que o "até" quer dizer.
- Exercício 2. Escreve os índices por baixo dos elementos, a começar em 0. O último índice é o que está por baixo do último elemento. Na alínea e), lembra-te de como o guia passa do índice para o número do jogo.
- Exercício 3. É o padrão contador, com o aumento dentro de um `Se`. Antes de escreveres a condição, marca no array as alturas que devem ser contadas. Para a alínea c), lembra-te do que faz um `Para cada` com um array vazio.
- Exercício 4. Precisas de um contador e de um acumulador no mesmo ciclo. A média calcula-se depois do ciclo, dentro de um `Se`. Que dias deve o contador contar?
- Exercício 5. É o padrão sentinela, com a leitura antes do ciclo e outra no fim do corpo. Que contas do guia 02 separam os minutos completos dos segundos que sobram? Em que momento do algoritmo já tens o total todo?
- Exercício 6. Precisas de dizer a posição do cacifo. Com qual das duas formas de percorrer um array sabes a posição de cada elemento? A bandeira começa em `false`, e depois do ciclo é ela que diz se o cacifo foi encontrado.
- Exercício 7. Na alínea a), escreve os índices por baixo dos elementos do array, a começar em 0. Ao lado, escreve os valores que `i` toma, volta a volta, e compara as duas listas. Na alínea b), faz a tabela de iterações, com uma linha por teste. A variável da condição aproxima-se do valor que faz o ciclo terminar?

## Desafio opcional

Leva cerca de 20 minutos.

Os pontos de duas equipas em três jogos de um torneio estão guardados numa tabela, uma linha por equipa:

```text
pontos = [[3, 1, 0], [1, 1, 3]]
```

a) Quanto vale `pontos[1][2]`? E `pontos[0][0]`?

b) Escreve um algoritmo com dois `Para`, um dentro do outro, que mostre o total de pontos de cada equipa. O ecrã deve mostrar "Equipa 1: 4 pontos" e "Equipa 2: 5 pontos".

c) No guia viste que um acumulador inicializado dentro do ciclo é um erro. No teu algoritmo, onde é que o total de cada equipa tem de começar em 0? Explica porque é que aqui está certo pô-lo dentro de um dos ciclos.

## Critérios de conclusão

- [ ] No exercício 1, contei as voltas de cada ciclo com uma tabela de iterações, até ao teste que dá falso. Sei o valor da variável nesse teste.
- [ ] Usei índices a partir de 0, sei qual é o último índice válido de um array e sei explicar como se chega a ele.
- [ ] O meu algoritmo do exercício 3 dá o resultado certo para o array do enunciado, e sei o que mostra com `[]` e com `[170]`.
- [ ] Inicializei os contadores e os acumuladores antes do ciclo.
- [ ] No exercício 4, o algoritmo dá o total e a média que calculei à mão. Os dois casos da alínea b) dão uma mensagem com sentido, sem nenhuma conta impossível.
- [ ] Não dividi por um contador que pode ficar a zero.
- [ ] No exercício 5, a tabela e o ecrã dão o número de músicas e a duração que calculei à mão, em minutos e segundos.
- [ ] Li a sentinela antes do ciclo e no fim do corpo, sem a tratar como um dado.
- [ ] No exercício 6, o meu algoritmo dá as posições, as voltas e as mensagens que previ para os três cacifos.
- [ ] Usei `Parar` numa pesquisa, com uma bandeira para saber se o valor foi encontrado.
- [ ] Testei os meus ciclos com zero voltas, uma volta e várias voltas.
- [ ] Para cada erro do exercício 7, apontei a volta ou o teste onde ele aparece, e a versão corrigida mostra o que calculei à mão.

## Autoavaliação

1. O que já consegues fazer sozinho?
2. Que dificuldade tiveste, e o que fizeste para a resolver?

![Rodapé](../imagens/rodape.png)
