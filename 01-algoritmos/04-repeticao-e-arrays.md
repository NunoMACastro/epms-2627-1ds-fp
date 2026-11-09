![Cabeçalho](../imagens/cabecalho.png)

# Repetição e arrays

Neste guia, aprendes a escrever algoritmos que repetem instruções, e a guardar muitos valores numa só variável, um array. Aprendes também a percorrer esses valores, a contá-los e a somá-los. Tem papel e lápis ao lado, porque as tabelas se fazem à mão.

Usas as decisões e a tabela de trace dos guias anteriores. Rever: [Tabela de trace](02-estado-sequencia-representacoes.md#tabela-de-trace), [Intervalos](03-decisoes-e-validacao.md#intervalos) e [Validar é verificar uma entrada antes de a usar](03-decisoes-e-validacao.md#validar-é-verificar-uma-entrada-antes-de-a-usar). Para praticar: [ficha de exercícios](exercicios/04-repeticao-e-arrays-exercicios.md).

## Neste guia

1. [Um ciclo repete instruções](#um-ciclo-repete-instruções)
2. [Enquanto: repetir enquanto a condição for verdadeira](#enquanto-repetir-enquanto-a-condição-for-verdadeira)
3. [Para: o ciclo contado](#para-o-ciclo-contado)
4. [Um array guarda vários valores](#um-array-guarda-vários-valores)
5. [Contadores e acumuladores](#contadores-e-acumuladores)
6. [A sentinela: ler até aparecer o valor que diz "acabou"](#a-sentinela-ler-até-aparecer-o-valor-que-diz-acabou)
7. [A validação repetida insiste até o valor servir](#a-validação-repetida-insiste-até-o-valor-servir)
8. [Parar e Continuar](#parar-e-continuar)
9. [Um array de arrays lê-se como uma tabela](#um-array-de-arrays-lê-se-como-uma-tabela)
10. [Exemplo guiado: a campanha de recolha de alimentos](#exemplo-guiado-a-campanha-de-recolha-de-alimentos)

## Um ciclo repete instruções

Com o que sabes até agora, a tabuada do 7, de 7 x 1 a 7 x 10, são dez linhas quase iguais. E um algoritmo que lê as notas de uma turma nem se consegue escrever assim, porque não sabes quantos alunos tem a turma.

No dia a dia, fazes repetições sem lhes dares esse nome: "Enquanto houver pratos na banca, lava um prato." A frase tem uma pergunta, uma ação e uma parte escondida, que é a mais importante. A ação muda a resposta à pergunta: cada prato lavado sai da banca, e mais cedo ou mais tarde paras.

Num algoritmo, a uma parte que se executa várias vezes seguidas chama-se **ciclo**. A cada execução dessa parte chama-se **iteração**, ou volta.

## Enquanto: repetir enquanto a condição for verdadeira

Este algoritmo escreve a tabuada do 7, só até 7 x 3, para as tabelas ficarem curtas:

```text
const NUMERO = 7
const ULTIMO = 3
int vezes = 1
Enquanto vezes <= ULTIMO
    Escreve: NUMERO, " x ", vezes, " = ", NUMERO * vezes
    vezes = vezes + 1
Escreve: "Fim da tabuada"
```

As linhas indentadas são o **corpo do ciclo**. Como no `Se`, é a indentação que mostra onde ele acaba. O `Escreve:` também pode mostrar o resultado de uma conta. O `Enquanto` funciona assim:

1. Avalia a condição, com os valores que as variáveis têm nesse momento.
2. Se for verdadeira, executa o corpo até à última linha indentada.
3. Depois da última linha, volta à linha do `Enquanto` e avalia outra vez a condição.
4. Se for falsa, salta o corpo e continua na primeira linha a seguir ao corpo.

A condição diz quando continuar, e não quando parar. E só é avaliada na linha do `Enquanto`: se ficar falsa a meio do corpo, o corpo vai até ao fim na mesma.

### As três peças de um ciclo

Os ciclos que terminam têm três peças:

- a **inicialização**, antes do ciclo, dá o valor inicial às variáveis. Na tabuada, é `int vezes = 1`;
- a condição decide se se faz mais uma volta. Na tabuada, é `vezes <= ULTIMO`;
- a **atualização**, dentro do corpo, muda a variável da condição e aproxima o ciclo do fim. Na tabuada, é `vezes = vezes + 1`.

Para cada ciclo, responde a três perguntas. Com que valor começa? Em que situação continua? O que muda em cada volta, e essa mudança aproxima o fim?

### A tabela de iterações

Num trace linha a linha, a mesma instrução aparece muitas vezes. Por isso, um ciclo segue-se numa tabela mais curta, a **tabela de iterações**. Tem uma linha por cada teste da condição, com as variáveis nesse momento:

| Teste | vezes | Condição | Durante a iteração |
| --- | ---: | --- | --- |
| 1.º | 1 | `1 <= 3` dá `true` | escreve "7 x 1 = 7" |
| 2.º | 2 | `2 <= 3` dá `true` | escreve "7 x 2 = 14" |
| 3.º | 3 | `3 <= 3` dá `true` | escreve "7 x 3 = 21" |
| 4.º | 4 | `4 <= 3` dá `false` | o ciclo termina |

Há mais um teste do que voltas, porque o último é o que dá falso. Repara que `vezes` acaba a valer 4, e não 3. Depois do ciclo, aparece "Fim da tabuada", uma só vez, porque essa linha já não está indentada.

### Zero voltas e voltas sem fim

Se a condição for falsa logo no primeiro teste, o corpo não se executa, e o ciclo dá **zero voltas**. Pode ser o que deve acontecer, como ao somar os pedidos de um dia sem pedidos. Também pode ser um erro, como escrever `Enquanto vezes > ULTIMO`, a situação de parar no lugar da de continuar.

Um **ciclo infinito** é um ciclo cuja condição nunca chega a ser falsa, e a causa mais frequente é a atualização. Sem `vezes = vezes + 1`, ou com essa linha fora do corpo, `vezes` vale sempre 1 e o ecrã enche-se de "7 x 1 = 7". Com `vezes = vezes - 1`, a variável afasta-se do fim.

Uma condição com `!=` também pode saltar por cima do valor em que devia parar. Se `x` começar em 1 e aumentar 2 em cada volta, `x != 10` nunca fica falsa, porque passa do 9 para o 11.

## Para: o ciclo contado

Quando se sabe, antes de começar, quantas voltas vão ser, o ciclo é um **ciclo contado**, e escreve-se com o `Para`. Nas aulas usamos duas formas.

### A primeira forma: `Para ... de ... até ...`

```text
const NUMERO = 7
const ULTIMO = 3
Para vezes de 1 até ULTIMO
    Escreve: NUMERO, " x ", vezes, " = ", NUMERO * vezes
Escreve: "Fim da tabuada"
```

A variável `vezes` vai de 1 até `ULTIMO`, de 1 em 1, e o corpo executa-se uma vez para cada valor. O "até" quer dizer "continua enquanto for menor ou igual". A tabela de iterações é igual à do `Enquanto`.

A esta variável chama-se **variável de controlo**. Não leva tipo, porque é o `Para` que a cria, e segue estas regras:

- avança sempre de 1 em 1;
- dentro do corpo, não se muda a variável de controlo nem o limite;
- se o limite for menor do que o valor inicial, como em `Para dia de 1 até 0`, dá zero voltas;
- depois do ciclo, não se usa.

### A segunda forma: as três peças à vista

```text
Para vezes = 1, vezes <= ULTIMO, vezes++
    Escreve: NUMERO, " x ", vezes, " = ", NUMERO * vezes
```

Também aqui a variável não leva tipo. `vezes = 1` é a inicialização, executada uma só vez. `vezes <= ULTIMO` é a condição, testada antes de cada volta. `vezes++` é a atualização, executada no fim de cada volta, e quer dizer `vezes = vezes + 1`.

Esta forma dá jeito para começar em 0 e parar antes de um número, como vais precisar nos arrays. `Para i = 0, i < 5, i++` dá 5 voltas, com `i` a valer de 0 a 4. Aqui és tu que escreves as três peças, e por isso os erros do `Enquanto` voltam a ser possíveis.

### Escolher entre `Enquanto` e `Para`

Quando o algoritmo chega ao ciclo, já se sabe quantas vezes ele se vai repetir? Se sim, usa-se o `Para`, como para ler as notas de 25 alunos, ou um número de dias lido antes do ciclo. Se não, usa-se o `Enquanto`, como para pedir uma nota até ela ser válida.

## Um array guarda vários valores

Para guardar as notas de 25 alunos, precisavas de 25 variáveis. Imagina antes uma fila de cacifos numerados: a fila tem um nome, e cada cacifo tem um número e guarda uma coisa. Um **array** é uma variável que guarda vários valores, uns a seguir aos outros. A cada valor chama-se **elemento**.

### Criar um array

Um array escreve-se entre parênteses retos, com os valores separados por vírgulas, sem tipo à frente. O nome vai no plural:

```text
pontuacoes = [12, 7, 20, 5]
```

Um array também pode estar vazio, `pontuacoes = []`. É um caso de teste importante, como vais ver.

### O índice

Cada elemento tem uma posição, o **índice**, e os índices começam em 0, porque o primeiro elemento está a zero posições do início:

| Índice | 0 | 1 | 2 | 3 |
| --- | ---: | ---: | ---: | ---: |
| Elemento | 12 | 7 | 20 | 5 |

`pontuacoes[0]` é o 12, e `pontuacoes[3]` é o 5. Num array com `n` elementos, o último índice válido é `n - 1`. `pontuacoes[4]` não existe, e usá-lo é um erro a que se chama índice fora do array.

Um elemento usa-se como qualquer variável. Antes de leres a resposta, tenta prever o que aparece no ecrã:

```text
pontuacoes = [12, 7, 20, 5]
pontuacoes[1] = 9
Escreve: pontuacoes[1] + pontuacoes[2]
```

Aparece 29, porque o elemento de índice 1 já vale 9, e o array fica `[12, 9, 20, 5]`.

<details>
<summary>Para ires mais longe: o índice fora do array no Python e no C</summary>

Em Python, se o índice não existir, o programa para e mostra uma mensagem de erro. O C foi pensado para programas muito rápidos, e não confirma em cada acesso se o índice existe. Essa verificação fica a cargo de quem programa, e o programa pode continuar com um valor qualquer.

</details>

### Percorrer um array com `Para`

**Percorrer** um array é passar por todos os elementos, um a um, fazendo alguma coisa com cada um. Com o índice, usa-se o `Para` com as três peças à vista:

```text
const NUMERO_DE_JOGOS = 4
pontuacoes = [12, 7, 20, 5]
Para i = 0, i < NUMERO_DE_JOGOS, i++
    Escreve: "Jogo ", i + 1, ": ", pontuacoes[i], " pontos"
```

| Teste | i | Condição | pontuacoes[i] | Durante a iteração |
| --- | ---: | --- | ---: | --- |
| 1.º | 0 | `0 < 4` dá `true` | 12 | escreve "Jogo 1: 12 pontos" |
| 2.º | 1 | `1 < 4` dá `true` | 7 | escreve "Jogo 2: 7 pontos" |
| 3.º | 2 | `2 < 4` dá `true` | 20 | escreve "Jogo 3: 20 pontos" |
| 4.º | 3 | `3 < 4` dá `true` | 5 | escreve "Jogo 4: 5 pontos" |
| 5.º | 4 | `4 < 4` dá `false` | não se usa | o ciclo termina |

A condição usa `<` e não `<=`. Com `<=`, o ciclo dava mais uma volta, e `pontuacoes[4]` não existe. O `i + 1` existe porque, para as pessoas, o primeiro jogo é o jogo 1. O número de elementos está numa constante, porque nas aulas ainda não pedimos a um array quantos elementos tem.

### Percorrer um array com `Para cada`

Muitas vezes, só interessa o valor de cada elemento:

```text
pontuacoes = [12, 7, 20, 5]
Para cada pontuacao em pontuacoes
    Escreve: pontuacao, " pontos"
```

Em cada volta, a variável `pontuacao` recebe o elemento seguinte, e o ciclo acaba sozinho quando eles se esgotam. Não há índice nem condição a escrever. A variável não leva tipo, e costuma ter o nome do array no singular. Com um array vazio, o `Para cada` dá zero voltas.

### Quando é preciso o índice

Se só precisas dos valores, para os somar, contar ou mostrar, usa o `Para cada`. O `Para` com o índice serve para dizer em que posição está um valor, ou para comparar um elemento com o seguinte.

O professor quer dar mais um valor a todas as notas. Antes de leres a explicação, tenta prever o que aparece no ecrã:

```text
notas = [12, 8, 15]
Para cada nota em notas
    nota = nota + 1
Escreve: notas[0], " ", notas[1], " ", notas[2]
```

Aparece "12 8 15". Em cada volta, a variável recebe uma **cópia** do valor, e mudar a cópia não muda o array. Para mudar um elemento, é preciso saber a sua posição:

```text
const NUMERO_DE_NOTAS = 3
notas = [12, 8, 15]
Para i = 0, i < NUMERO_DE_NOTAS, i++
    notas[i] = notas[i] + 1
Escreve: notas[0], " ", notas[1], " ", notas[2]
```

Agora aparece "13 9 16".

## Contadores e acumuladores

### O contador

Um **contador** é uma variável que conta quantas vezes uma coisa aconteceu. Começa em 0, antes do ciclo, aumenta 1 sempre que a coisa acontece, e só se lê o resultado depois do ciclo:

```text
const MINIMO = 10
pontuacoes = [12, 7, 20, 5]
int jogosBons = 0
Para cada pontuacao em pontuacoes
    Se pontuacao >= MINIMO
        jogosBons = jogosBons + 1
Escreve: "Jogos com ", MINIMO, " ou mais pontos: ", jogosBons
```

Num `Para cada`, a tabela tem uma linha por volta, com as variáveis no fim da volta:

| Volta | pontuacao | Condição do `Se` | jogosBons no fim da volta |
| --- | ---: | --- | ---: |
| antes do ciclo | sem valor | não se avalia | 0 |
| 1.ª | 12 | `12 >= 10` dá `true` | 1 |
| 2.ª | 7 | `7 >= 10` dá `false` | 1 |
| 3.ª | 20 | `20 >= 10` dá `true` | 2 |
| 4.ª | 5 | `5 >= 10` dá `false` | 2 |

A linha do aumento tem oito espaços, porque está dentro do `Se`, e só conta as voltas em que a condição é verdadeira. Com quatro espaços, contava todas as voltas.

### O acumulador

Um **acumulador** é uma variável que vai somando valores: `total = total + valor`. Também começa em 0, antes do ciclo. O contador soma 1 e responde a "quantos?". O acumulador soma cada valor e responde a "quanto?".

### A média só se calcula quando há valores

Com um contador e um acumulador no mesmo ciclo, calcula-se uma média:

```text
pontuacoes = [12, 7, 20, 5]
int quantidade = 0
int total = 0
Para cada pontuacao em pontuacoes
    quantidade = quantidade + 1
    total = total + pontuacao
Se quantidade > 0
    float media = total / quantidade
    Escreve: "Média: ", media, " pontos"
Senão
    Escreve: "Não há pontuações, por isso não há média."
```

Aqui, `quantidade` acaba em 4 e `total` em 44, e a média é 11. O `Se` trata do caso de zero voltas: com o array vazio, a conta seria 0 / 0, e não se pode dividir por zero.

## A sentinela: ler até aparecer o valor que diz "acabou"

Na bilheteira de um cinema, o funcionário escreve quantos bilhetes saíram em cada venda, à medida que acontecem. Ninguém sabe quantas vendas vão ser. Por isso, combina-se um valor especial que quer dizer "acabou", a **sentinela**. Não pode ser um valor que os dados possam ter, e quem escreve tem de saber qual é.

```text
const SENTINELA = 0
int vendas = 0
int bilhetes = 0
Escreve: "Bilhetes desta venda (0 para terminar)?"
int bilhetesDaVenda = ler valor
Enquanto bilhetesDaVenda != SENTINELA
    vendas = vendas + 1
    bilhetes = bilhetes + bilhetesDaVenda
    Escreve: "Bilhetes desta venda (0 para terminar)?"
    bilhetesDaVenda = ler valor
Escreve: "Vendas: ", vendas
Escreve: "Bilhetes vendidos: ", bilhetes
```

O primeiro valor lê-se antes do ciclo, e o seguinte como última linha do corpo. Assim, cada valor passa pela condição antes de ser tratado, e a sentinela nunca é contada. Com 2, 4, 1 e o 0:

| Teste | bilhetesDaVenda | vendas | bilhetes | Condição | Durante a iteração |
| --- | ---: | ---: | ---: | --- | --- |
| 1.º | 2 | 0 | 0 | `2 != 0` dá `true` | lê 4 |
| 2.º | 4 | 1 | 2 | `4 != 0` dá `true` | lê 1 |
| 3.º | 1 | 2 | 6 | `1 != 0` dá `true` | lê 0 |
| 4.º | 0 | 3 | 7 | `0 != 0` dá `false` | o ciclo termina |

O algoritmo escreve "Vendas: 3" e "Bilhetes vendidos: 7". Se o primeiro valor for logo 0, o ciclo dá zero voltas, e escreve 0 vendas e 0 bilhetes.

## A validação repetida insiste até o valor servir

No guia anterior, uma nota inválida terminava o algoritmo. Com um ciclo, pede-se o valor outra vez, até ser válido:

```text
const NOTA_MINIMA = 0
const NOTA_MAXIMA = 20
Escreve: "Nota do teste (inteiro de 0 a 20)?"
int nota = ler valor
Enquanto nota < NOTA_MINIMA ou nota > NOTA_MAXIMA
    Escreve: "Nota inválida. Escreve um inteiro de 0 a 20."
    nota = ler valor
Escreve: "Nota aceite: ", nota
```

Se a pessoa escrever 25, depois -3 e depois 14, o ciclo dá duas voltas. Se escrever logo 14, dá zero voltas. Na primeira linha a seguir ao ciclo, a condição acabou de dar falso, e por isso tens a certeza de que a nota é válida.

## Parar e Continuar

São duas instruções que mudam o caminho de um ciclo a meio de uma volta. Escrevem-se sozinhas numa linha, quase sempre dentro de um `Se`.

### `Parar`: sair do ciclo já

`Parar` termina o ciclo imediatamente. O uso mais comum é numa pesquisa, que procura um valor num array e para assim que o encontra:

```text
const NUMERO_DE_JOGOS = 5
golos = [2, 1, 0, 3, 0]
bool encontrado = false
Para i = 0, i < NUMERO_DE_JOGOS, i++
    Se golos[i] == 0
        Escreve: "Primeiro jogo sem golos: jogo ", i + 1
        encontrado = true
        Parar
Se encontrado == false
    Escreve: "A equipa marcou em todos os jogos."
```

O ciclo dá três voltas, escreve "Primeiro jogo sem golos: jogo 3" e não olha para o resto do array. O `Parar` sai sem voltar ao teste, e por isso aqui há tantos testes como voltas.

Sabe-se o máximo de voltas, o tamanho do array, e por isso é um `Para`. Um ciclo destes pode acabar por duas razões: encontrou o valor, ou os índices esgotaram-se. A variável `encontrado` diz qual foi. A uma variável `bool` usada assim chama-se **bandeira**. A mensagem de "não encontrado" escreve-se depois do ciclo. Dentro do ciclo, num `Senão`, aparecia em cada volta anterior à que o encontra.

### `Continuar`: saltar para a volta seguinte

`Continuar` termina só a volta atual, e o ciclo passa à seguinte. Este algoritmo soma as leituras de um sensor, e põe de lado as negativas, que são erros:

```text
leituras = [5, -2, 8, -1, 4]
int total = 0
Para cada leitura em leituras
    Se leitura < 0
        Continuar
    total = total + leitura
Escreve: "Total das leituras válidas: ", total
```

O total é 5 + 8 + 4, que dá 17. Num `Enquanto`, há um cuidado: se a atualização estiver abaixo do `Continuar`, também é saltada, e o ciclo pode nunca acabar.

## Um array de arrays lê-se como uma tabela

Um elemento de um array pode ser, ele próprio, um array. Estas são as notas de dois alunos em três testes:

```text
notas = [[12, 15, 9], [8, 11, 14]]
```

| | Teste 0 | Teste 1 | Teste 2 |
| --- | ---: | ---: | ---: |
| Aluno 0 | 12 | 15 | 9 |
| Aluno 1 | 8 | 11 | 14 |

Para chegar a uma nota, dizem-se dois índices, primeiro a linha e depois a coluna. `notas[1][2]` é o 14. Para percorrer a tabela inteira, usam-se dois `Para`, um dentro do outro:

```text
const NUMERO_DE_ALUNOS = 2
const NUMERO_DE_TESTES = 3
notas = [[12, 15, 9], [8, 11, 14]]
Para a = 0, a < NUMERO_DE_ALUNOS, a++
    Para t = 0, t < NUMERO_DE_TESTES, t++
        Escreve: "Aluno ", a + 1, ", teste ", t + 1, ": ", notas[a][t]
```

Para cada valor de `a`, o `Para` de dentro dá todas as suas voltas. O corpo de dentro executa-se 2 vezes 3, ou seja, 6 vezes, uma por cada nota.

## Exemplo guiado: a campanha de recolha de alimentos

### O enunciado

> A escola organiza uma campanha de recolha de alimentos. Cada turma entrega os alimentos que juntou, e a funcionária escreve quantos quilos a turma trouxe, um número inteiro. Uma turma pode não ter trazido nada, e nesse caso a funcionária escreve 0. Quando não há mais turmas, escreve -1. O algoritmo mostra quantas turmas entregaram, o total de quilos e a média por turma, mas a média só se houver pelo menos uma turma.
>
> No fim da campanha, os quilos das 6 turmas do 10.º ano ficaram registados num array, `quilosPorTurma = [12, 0, 9, 15, 6, 18]`. A diretora quer saber que turmas trouxeram mais do que a média dessas 6 turmas.

O enunciado tem duas partes, e cada uma vai ser um algoritmo.

### O contrato da primeira parte

A entrada é uma sequência de inteiros, iguais ou maiores do que zero, terminada por -1. O 0 é um dado verdadeiro: a turma conta e entra na média. Por isso, a sentinela é o -1. As saídas são o número de turmas, o total de quilos e a média.

| Valores escritos | Turmas | Total | Média | Porque foi escolhido |
| --- | ---: | ---: | --- | --- |
| -1 | 0 | 0 | não há média | Zero voltas: ninguém entregou |
| 15, -1 | 1 | 15 | 15 | Uma só volta |
| 12, 0, 9, -1 | 3 | 21 | 7 | Várias voltas, com uma turma que trouxe 0 |

### O algoritmo da primeira parte, aos poucos

Não se sabe quantas turmas vão entregar, e por isso o ciclo é de sentinela. O contador e o acumulador nascem antes do ciclo, e o primeiro valor lê-se aí também:

```text
const SENTINELA = -1
int turmas = 0
int totalQuilos = 0
Escreve: "Quilos entregues pela turma (-1 para terminar)?"
int quilos = ler valor
```

Em cada volta, conta-se a turma, somam-se os quilos e lê-se o valor seguinte:

```text
Enquanto quilos != SENTINELA
    turmas = turmas + 1
    totalQuilos = totalQuilos + quilos
    Escreve: "Quilos entregues pela turma (-1 para terminar)?"
    quilos = ler valor
```

A média calcula-se depois do ciclo, quando a contagem e a soma estão completas, e só se houve turmas:

```text
Escreve: "Turmas que entregaram: ", turmas
Escreve: "Total: ", totalQuilos, " kg"
Se turmas > 0
    float media = totalQuilos / turmas
    Escreve: "Média por turma: ", media, " kg"
Senão
    Escreve: "Não houve entregas, por isso não há média."
```

### O trace da primeira parte

Com 12, 0, 9 e -1:

| Teste | quilos | turmas | totalQuilos | Condição | Durante a iteração |
| --- | ---: | ---: | ---: | --- | --- |
| 1.º | 12 | 0 | 0 | `12 != -1` dá `true` | lê 0 |
| 2.º | 0 | 1 | 12 | `0 != -1` dá `true` | lê 9 |
| 3.º | 9 | 2 | 12 | `9 != -1` dá `true` | lê -1 |
| 4.º | -1 | 3 | 21 | `-1 != -1` dá `false` | o ciclo termina |

A média é 21 / 3, que dá 7, e o 0 foi contado como turma, como o contrato pede. Com 15 e -1, o ciclo dá uma volta, e a média é 15. Com -1 logo de início, dá zero voltas, e aparece "Não houve entregas, por isso não há média.".

### A segunda parte, com o array

Para saber se uma turma está acima da média, é preciso conhecer a média, e ela só se conhece depois de somar todas as turmas. Por isso, o array percorre-se duas vezes. O primeiro percurso só precisa dos valores. O segundo tem de dizer o número da turma, e precisa do índice:

```text
const NUMERO_DE_TURMAS = 6
quilosPorTurma = [12, 0, 9, 15, 6, 18]
int total = 0
Para cada quilos em quilosPorTurma
    total = total + quilos
float media = total / NUMERO_DE_TURMAS
Escreve: "Média: ", media, " kg"
int acimaDaMedia = 0
Para i = 0, i < NUMERO_DE_TURMAS, i++
    Se quilosPorTurma[i] > media
        Escreve: "A turma ", i + 1, " trouxe mais do que a média"
        acimaDaMedia = acimaDaMedia + 1
Escreve: "Turmas acima da média: ", acimaDaMedia
```

Aqui a média não precisa de `Se`, porque o enunciado diz que o array tem 6 turmas. O primeiro percurso dá um total de 60, e a média é 10:

| Teste | i | Condição do `Para` | quilosPorTurma[i] | Comparação com a média | acimaDaMedia no fim da volta |
| --- | ---: | --- | ---: | --- | ---: |
| 1.º | 0 | `0 < 6` dá `true` | 12 | `12 > 10` dá `true` | 1 |
| 2.º | 1 | `1 < 6` dá `true` | 0 | `0 > 10` dá `false` | 1 |
| 3.º | 2 | `2 < 6` dá `true` | 9 | `9 > 10` dá `false` | 1 |
| 4.º | 3 | `3 < 6` dá `true` | 15 | `15 > 10` dá `true` | 2 |
| 5.º | 4 | `4 < 6` dá `true` | 6 | `6 > 10` dá `false` | 2 |
| 6.º | 5 | `5 < 6` dá `true` | 18 | `18 > 10` dá `true` | 3 |
| 7.º | 6 | `6 < 6` dá `false` | não se usa | não se avalia | não há volta |

Aparecem as turmas 1, 4 e 6, e "Turmas acima da média: 3". O último índice usado foi o 5, o último válido num array de 6 elementos.

## Erros frequentes

### Uma volta a mais ou a menos

Trocar `<` por `<=`, ou começar em 0 quando se devia começar em 1, dá uma volta a mais. O contrário dá uma volta a menos. A somar `[12, 7, 20, 5]`, `Para i = 1, i < 4, i++` dá 32 em vez de 44, porque o 12 nunca é somado. Confirma sempre a primeira e a última volta na tabela.

### O acumulador inicializado dentro do ciclo

Com `int total = 0` dentro do corpo, o total recomeça em cada volta e fica só com o último valor. Com `[12, 7, 20, 5]`, acaba em 5. Com um array de um só elemento, o erro não se vê.

### A sentinela contada como um dado

```text
int bilhetesDaVenda = 1
Enquanto bilhetesDaVenda != SENTINELA
    Escreve: "Bilhetes desta venda (0 para terminar)?"
    bilhetesDaVenda = ler valor
    vendas = vendas + 1
    bilhetes = bilhetes + bilhetesDaVenda
```

Aqui lê-se no princípio do corpo, e o 0 é contado antes de a condição o poder testar. Com 2, 4, 1 e o 0, escreve "Vendas: 4". O valor inventado para entrar no ciclo já era um sinal de alarme.

### Testar só o caso normal

Testa sempre zero voltas, uma volta e várias voltas. Num array, isso quer dizer um array vazio, um com um elemento e um com vários. O caso de zero voltas revela a média sem valores, e o de várias voltas revela o acumulador dentro do ciclo.

## Palavras novas deste guia

- Ciclo: uma parte de um algoritmo que se executa várias vezes seguidas.
- Iteração, ou volta: cada execução do corpo de um ciclo.
- Corpo do ciclo: as instruções indentadas, que se repetem.
- Inicialização: a peça que dá o valor inicial às variáveis, antes do ciclo.
- Atualização: a instrução do corpo que muda a variável da condição e aproxima o fim.
- Tabela de iterações: uma tabela com uma linha por cada teste da condição.
- Zero voltas: o caso em que a condição é falsa logo no primeiro teste.
- Ciclo infinito: um ciclo cuja condição nunca chega a ser falsa.
- Ciclo contado: um ciclo em que se sabe, antes de começar, quantas voltas vai dar.
- Variável de controlo: a variável que o `Para` cria e faz avançar de 1 em 1.
- Array: uma variável que guarda vários valores, uns a seguir aos outros.
- Elemento: cada valor guardado num array.
- Índice: a posição de um elemento num array, a contar de 0.
- Percorrer um array: passar por todos os elementos, um a um.
- Cópia: o valor que a variável do `Para cada` recebe; mudá-la não muda o array.
- Contador: uma variável que conta quantas vezes uma coisa aconteceu.
- Acumulador: uma variável que vai somando valores.
- Sentinela: o valor combinado que quer dizer "acabou", e que nenhum dado pode ter.
- Bandeira: uma variável `bool` que começa em `false` e passa a `true` quando acontece o que se procura.

## O que vem a seguir

No tema seguinte, [Funções e modelo integrado](05-funcoes-e-modelo-integrado.md), dás nome às partes que se repetem, como calcular uma média, e usas essas partes sempre que precisares.

![Rodapé](../imagens/rodape.png)
