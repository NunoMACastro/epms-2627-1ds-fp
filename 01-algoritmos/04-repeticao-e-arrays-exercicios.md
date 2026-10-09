![Cabeçalho](../imagens/cabecalho.png)

# Ficha de exercícios: Repetição e arrays

| Identificação | Valor |
| --- | --- |
| Disciplina | Fundamentos de Programação, 10.º ano, Desenvolvimento de Software |
| Unidade de competência | UC00245, Desenvolver algoritmos |
| Material | Ficha do quarto tema, acompanha o [guia](04-repeticao-e-arrays.md) |
| Tempo | 105 minutos de exercícios e 20 minutos de desafio opcional |
| Entrega | As respostas em papel ou num ficheiro de texto, com as tabelas de iterações |

## Antes de começares

Esta ficha treina o que aprendeste no guia: contar as voltas de um ciclo, usar os índices de um array, contar e somar ao percorrer um array, calcular uma média sem dividir por zero, ler valores até uma sentinela, procurar um valor com `Parar` e encontrar os erros mais frequentes dos ciclos.

Antes de começar, deves conseguir explicar as três peças de um ciclo, porque é que os índices começam em 0, a diferença entre um contador e um acumulador e porque é que a sentinela se lê antes do ciclo e no fim do corpo. Se alguma destas ideias não estiver clara, volta à secção do guia que a explica.

Escreve os algoritmos na forma que usamos nas aulas, com a indentação a mostrar o que está dentro de cada ciclo. Um array escreve-se como uma lista de Python, sem tipo à frente. Se souberes a lógica e não te lembrares da forma, escreve frases claras que digam o que se repete, até quando, e o que muda de uma volta para a seguinte.

Os desenhos de fluxogramas não fazem parte desta ficha. Se o professor indicar o [laboratório](04-repeticao-e-arrays-laboratorio.md) deste tema, é lá que os desenhas.

## Exercício 1: Quantas voltas? (10 min)

Para cada ciclo, diz quantas voltas dá, o que aparece no ecrã e com que valor da variável é feito o último teste.

a)

```text
int x = 10
Enquanto x > 0
    Escreve: x
    x = x - 3
```

b)

```text
Para i de 1 até 4
    Escreve: i * 2
```

c)

```text
Para i = 0, i < 3, i++
    Escreve: i
```

Concluíste quando, para cada ciclo, souberes dizer o número de voltas e o valor da variável no teste que deu falso.

## Exercício 2: Os índices de um array (10 min)

Os minutos de atraso do autocarro da escola em cinco dias ficaram guardados neste array:

```text
atrasos = [5, 9, 0, 3, 7]
```

a) Quanto vale `atrasos[0]`? E `atrasos[4]`?

b) Qual é o último índice válido deste array? Explica porquê.

c) O que aparece no ecrã com `Escreve: atrasos[1] + atrasos[3]`?

d) O que acontece com `Escreve: atrasos[5]`?

Concluíste quando tiveres as quatro respostas e a da alínea b) disser como se chega ao último índice.

## Exercício 3: Contar num intervalo (15 min)

As alturas, em centímetros, dos jogadores de uma equipa de voleibol estão neste array:

```text
alturas = [172, 165, 181, 158, 177, 169]
```

a) Escreve um algoritmo que conte quantos jogadores medem entre 165 e 175 centímetros, incluindo os extremos, e mostre o resultado.

b) Diz quando é que o teu ciclo termina, e porquê.

c) Sem mudar o algoritmo, diz o que ele mostra se o array for `[]` e se for `[170]`.

Concluíste quando o teu algoritmo der o resultado certo para o array do enunciado e souberes o que mostra nos dois casos da alínea c).

## Exercício 4: A média de estudo (15 min)

Uma aluna registou num array os minutos que estudou em cada dia da semana. Nos dias em que não estudou, registou 0:

```text
estudo = [30, 45, 0, 60, 15]
```

a) Escreve um algoritmo que mostre o total de minutos da semana e a média dos dias em que ela estudou. Os dias com 0 minutos não contam para a média, porque a aluna quer saber quanto tempo estuda, em média, num dia em que se senta a estudar. Não escrevas à mão quantos dias foram: o algoritmo conta-os dentro do ciclo.

b) O mesmo algoritmo tem de funcionar se a aluna não tiver estudado em nenhum dia, como em `[0, 0, 0, 0, 0]`, e se o array estiver vazio, sem fazer nenhuma conta impossível. O que mostra em cada um dos dois casos?

Concluíste quando o total e a média que o algoritmo mostra para o array do enunciado forem os que calculaste à mão antes de o seguir, e quando os dois casos da alínea b) derem uma mensagem com sentido, sem nenhuma conta impossível.

## Exercício 5: A duração da playlist (20 min)

O Rui quer saber quanto dura a sua playlist. Escreve a duração de cada música em segundos, uma de cada vez, e escreve 0 quando acabar. Nenhuma música dura 0 segundos.

a) Escreve um algoritmo que mostre quantas músicas tem a playlist e quanto dura ao todo, em minutos e segundos, como "10 min e 25 s".

b) Faz a tabela de iterações para as durações 200, 185 e 240, seguidas do 0.

c) O que mostra o algoritmo se o Rui escrever logo 0?

Concluíste quando tiveres calculado à mão, antes de fazeres a tabela, a duração total das três músicas da alínea b), primeiro em segundos e depois em minutos e segundos, e a tabela e o ecrã derem os valores que previste, incluindo o número de músicas, com a duração escrita em minutos e segundos.

## Exercício 6: Procurar um cacifo (20 min)

Os números dos cinco cacifos ocupados no corredor estão neste array:

```text
ocupados = [12, 23, 7, 31, 18]
```

a) Escreve um algoritmo que lê um número de cacifo e procura-o no array. Se o encontrar, escreve em que posição está, contando a primeira posição como 1, e para de procurar. Se não o encontrar, escreve "Cacifo livre". Usa `Parar` e uma bandeira, como no guia.

b) Diz quantas voltas dá o ciclo e o que aparece no ecrã para os cacifos 23, 18 e 40.

Concluíste quando tiveres previsto, olhando para o array, em que posição está cada um dos três cacifos, ou se está livre, e quantas voltas o ciclo deve dar para cada um, e o teu algoritmo der essas posições, essas voltas e essas mensagens nos três casos.

## Exercício 7: Encontrar o erro (15 min)

Cada um destes algoritmos tem um erro. Para cada um, diz qual é o erro, mostra com a tabela de iterações ou com um passo do trace onde ele aparece, e corrige-o mudando o mínimo possível.

a) Devia somar a chuva, em milímetros, de quatro dias:

```text
const NUMERO_DE_DIAS = 4
chuva = [3, 0, 12, 5]
int total = 0
Para i de 1 até NUMERO_DE_DIAS
    total = total + chuva[i]
Escreve: "Chuva total: ", total, " mm"
```

b) Devia fazer a contagem decrescente de um lançamento, de 10 até 1, escrever "Meio caminho!" logo a seguir ao 5, e no fim escrever "Partida!":

```text
int contagem = 10
Enquanto contagem > 0
    Escreve: contagem
    Se contagem == 5
        Escreve: "Meio caminho!"
        contagem = contagem - 1
Escreve: "Partida!"
```

Concluíste quando, para cada algoritmo, souberes apontar a volta ou o passo onde o erro aparece e a versão corrigida fizer o que devia.

## Apoio

Se estiveres encravado, usa estas pistas pela ordem em que aparecem, e passa à seguinte só se a anterior não tiver chegado.

Exercício 1. Faz uma tabela de iterações para cada ciclo, com uma linha por teste. Na alínea a), não pares quando o ecrã mostra o último número: continua até o teste dar falso.

Exercício 2. Escreve os índices por baixo dos elementos, a começar em 0. O último índice é o que está por baixo do último elemento.

Exercício 3. É o padrão contador, com o aumento dentro de um `Se`. A condição do `Se` é um intervalo, com `e`, como no guia 3. Para a alínea c), lembra-te do que faz um `Para cada` com um array vazio.

Exercício 4. Precisas de um contador e de um acumulador no mesmo ciclo. A média calcula-se depois do ciclo, dentro de um `Se`.

Exercício 5. É o padrão sentinela, com a leitura antes do ciclo e outra no fim do corpo. Para os minutos e os segundos, usa `div` e `resto`, como no guia 2.

Exercício 6. Percorre o array com o índice, porque precisas da posição. A bandeira começa em `false`; depois do ciclo, é ela que diz se o cacifo foi encontrado.

Exercício 7. Na alínea a), escreve os índices por baixo dos elementos do array, a começar em 0, e ao lado os valores que `i` toma, volta a volta, e compara as duas listas. Na alínea b), faz a tabela de iterações, com uma linha por teste, e vê se a variável da condição se aproxima do valor que faz o ciclo terminar.

## Desafio opcional (20 min)

Os pontos de duas equipas em três jogos de um torneio estão guardados numa tabela, uma linha por equipa:

```text
pontos = [[3, 1, 0], [1, 1, 3]]
```

a) Quanto vale `pontos[1][2]`? E `pontos[0][0]`?

b) Escreve um algoritmo com dois `Para`, um dentro do outro, que mostre o total de pontos de cada equipa: "Equipa 1: 4 pontos" e "Equipa 2: 5 pontos".

c) No guia viste que um acumulador inicializado dentro do ciclo é um erro. No teu algoritmo, onde é que o total de cada equipa tem de começar em 0? Explica porque é que aqui está certo pô-lo dentro de um dos ciclos.

## Critérios de conclusão

- [ ] Contei as voltas de cada ciclo com uma tabela de iterações, até ao teste que dá falso.
- [ ] Usei índices a partir de 0 e sei qual é o último índice válido de um array.
- [ ] Inicializei os contadores e os acumuladores antes do ciclo.
- [ ] Testei os meus ciclos com zero voltas, uma volta e várias voltas.
- [ ] Não dividi por um contador que pode ficar a zero.
- [ ] Li a sentinela antes do ciclo e no fim do corpo, sem a tratar como um dado.
- [ ] Usei `Parar` numa pesquisa, com uma bandeira para saber se o valor foi encontrado.
- [ ] Para cada erro, mostrei a volta ou o passo onde ele aparece.

## Autoavaliação breve

O que já consigo fazer sozinho:

Uma dificuldade que tive e o que fiz para a resolver:

![Rodapé](../imagens/rodape.png)
