![Cabeçalho](../imagens/cabecalho.png)

# Repetição e arrays

| Identificação | Valor |
| --- | --- |
| Disciplina | Fundamentos de Programação, 10.º ano, Desenvolvimento de Software |
| Unidade de competência | UC00245, Desenvolver algoritmos |
| Percurso | Algoritmos, quarto guia |

## O que vais aprender

Até agora, cada instrução dos teus algoritmos executava-se no máximo uma vez. Neste guia vais aprender a repetir instruções, a guardar vários valores numa só variável, chamada array, e a percorrer esses valores um a um. São as duas ideias que mais vais usar daqui até ao fim do curso.

No fim deves conseguir:

- escrever ciclos com `Enquanto` e com `Para`, nas duas formas do `Para`, e escolher qual usar;
- identificar as três peças de um ciclo, a inicialização, a condição e a atualização, e explicar porque é que um ciclo termina;
- fazer o trace de um ciclo, linha a linha e numa tabela de iterações, incluindo o caso em que o ciclo não dá nenhuma volta;
- criar um array, aceder a um elemento pelo índice e dizer qual é o último índice válido;
- percorrer um array com `Para` e com `Para cada`, e saber quando é preciso o índice;
- usar um contador e um acumulador, e calcular uma média só quando há valores;
- ler valores até uma sentinela e validar uma entrada repetindo o pedido até ela ser válida;
- usar `Parar` e `Continuar` dentro de um ciclo;
- reconhecer um array de arrays como uma tabela e percorrê-lo com dois `Para`.

## O que já sabes e vais usar

Na aula já trabalhaste o `Para`, o "para cada" e o `Enquanto`, arrays escritos como listas de Python, uma introdução aos arrays de arrays, o `Parar` e o `Continuar`, e exercícios com contadores, acumuladores e sentinela. Este guia arruma tudo isso na forma que usamos nas aulas, explica o porquê de cada regra e acrescenta o que ainda faltava, como a validação repetida.

Dos guias anteriores vais usar quase tudo. Do [guia 2](02-estado-sequencia-representacoes.md), as variáveis, a atribuição (incluindo `total = total + 5`, que é a base de quase todos os ciclos), o `div` e o `resto`, e a tabela de trace. Do [guia 3](03-decisoes-e-validacao.md), as condições, com `e`, `ou` e `não`, a seleção, a indentação que mostra o que está dentro de quê, as fronteiras e a validação. E do [guia 1](01-do-enunciado-ao-problema.md), o contrato de entrada e saída e os casos extremos, que aqui vão ter um nome novo: o caso de zero voltas.

Tal como nos guias anteriores, um algoritmo escrito em frases claras também é válido, desde que não deixe dúvidas. Num ciclo, isso quer dizer sobretudo deixar claro o que se repete, até quando, e o que muda de uma volta para a seguinte.

## Algoritmos que repetem

Imagina que te pedem um algoritmo que escreva a tabuada do 7, de 7 x 1 a 7 x 10. Com o que sabes até agora, ficaria assim:

```text
Escreve: "7 x 1 = ", 7 * 1
Escreve: "7 x 2 = ", 7 * 2
Escreve: "7 x 3 = ", 7 * 3
(e assim por diante, uma linha por cada multiplicação, até)
Escreve: "7 x 10 = ", 7 * 10
```

Dez linhas quase iguais. Funciona, mas tem três problemas, e o terceiro é o mais grave.

O primeiro é o tamanho. Dez linhas escrevem-se, mas se fosse a tabuada até 100 ninguém as conseguiria ler com atenção, e um engano na linha 57 passaria despercebido.

O segundo é a mudança. Se amanhã quiserem a tabuada até 12, alguém tem de acrescentar linhas. Se quiserem a do 8, alguém tem de mudar o 7 em dez sítios. O algoritmo não se adapta: tem de ser reescrito.

O terceiro é o que torna esta forma impossível em muitos problemas. Imagina que o algoritmo tem de ler as notas de uma turma, e que as turmas têm números de alunos diferentes. Quantas linhas com `ler valor` escreves? Não sabes. Nenhum número fixo de linhas serve para todas as turmas.

Olha outra vez para as linhas da tabuada. São todas iguais, exceto num pormenor: o número que multiplica o 7, que aumenta 1 de uma linha para a seguinte. Reparar nesta regularidade é o que permite resolver o problema. Se conseguirmos dizer ao algoritmo "escreve uma linha da tabuada, passa ao número seguinte, e volta a fazer o mesmo até chegares ao 10", as dez linhas passam a ser três ou quatro. É o reconhecimento de padrões do guia 1, aplicado às instruções.

No dia a dia fazes repetições destas sem lhes dares esse nome. "Enquanto houver pratos na banca, lava um prato." "Enquanto houver pessoas na fila, atende a seguinte." Todas estas frases têm três partes: uma pergunta cuja resposta é sim ou não (há pratos na banca?), uma ação que se faz quando a resposta é sim (lavar um prato), e uma consequência escondida, que é a mais importante de todas: a ação muda a resposta à pergunta. Cada prato lavado sai da banca, e mais cedo ou mais tarde a banca fica vazia e paras. Se lavar um prato não o tirasse da banca, ficarias a lavar o mesmo prato para sempre.

Num algoritmo, a uma parte que se executa várias vezes seguidas chama-se **ciclo**, e a cada execução dessa parte chama-se **iteração**. Na conversa de todos os dias diz-se também uma **volta** do ciclo: se o algoritmo lava três pratos, o ciclo teve três iterações, ou deu três voltas.

## Enquanto: repetir enquanto a condição for verdadeira

Na forma que usamos nas aulas, a repetição mais geral escreve-se assim:

```text
Enquanto condição
    instruções que se repetem
```

A `condição` é uma condição como as do guia 3: uma pergunta cuja resposta só pode ser `true` ou `false`. Às instruções escritas debaixo do `Enquanto`, quatro espaços mais para dentro, chama-se **corpo do ciclo**. Tal como no `Se`, não há nenhuma palavra a fechar o ciclo: é a indentação que mostra onde o corpo acaba. A primeira linha que volta a começar na mesma coluna do `Enquanto` já não faz parte do ciclo.

O `Enquanto` funciona com quatro regras:

1. Quando o algoritmo chega à linha do `Enquanto`, avalia a condição, com os valores que as variáveis têm nesse momento.
2. Se a condição for verdadeira, executa o corpo, de cima para baixo, até à última linha indentada.
3. Depois da última linha do corpo, o algoritmo não continua para baixo. Volta à linha do `Enquanto` e avalia outra vez a condição, agora com os valores que as variáveis têm depois do corpo. E recomeça na regra 2.
4. Se a condição for falsa, o corpo é saltado, e o algoritmo continua na primeira linha a seguir ao corpo.

Compara com o `Se` do guia 3. O `Se` avalia a condição uma vez e segue em frente. O `Enquanto` avalia a condição, executa o corpo e, no fim, volta atrás para perguntar outra vez. Uma boa forma de o pensar: um `Enquanto` é um `Se` que, quando acaba o seu bloco, volta a subir para fazer a mesma pergunta.

Destas regras saem duas consequências que convém fixar já.

A primeira: a condição do `Enquanto` diz quando continuar, e não quando parar. "Enquanto houver pratos na banca" descreve a situação em que se continua a lavar. Quando escreveres um ciclo, pergunta-te "em que situação quero continuar?", e escreve essa situação. Quem escreve a situação em que quer parar obtém um ciclo que faz o contrário do que queria.

A segunda: a condição só é avaliada na linha do `Enquanto`. Se, a meio do corpo, as variáveis mudarem de forma a tornar a condição falsa, o corpo não é interrompido. Continua até à última linha indentada, e só no teste seguinte o ciclo termina.

Este é o algoritmo da tabuada do 7, escrito com um ciclo. Para o trace ficar curto, vai só até 7 x 3; para ir até 7 x 10, bastava mudar a constante `ULTIMO` para 10.

```text
const NUMERO = 7
const ULTIMO = 3
int vezes = 1
Enquanto vezes <= ULTIMO
    Escreve: NUMERO, " x ", vezes, " = ", NUMERO * vezes
    vezes = vezes + 1
Escreve: "Fim da tabuada"
```

Lê-o por palavras: o número da tabuada é o 7 e a última multiplicação é a do 3; a variável `vezes` começa em 1; enquanto `vezes` for menor ou igual a 3, escreve-se uma linha da tabuada e passa-se ao número seguinte; quando `vezes` passar do 3, escreve-se que a tabuada acabou.

### A indentação mostra o que está dentro do ciclo

Olha para a margem esquerda de cada linha. Há duas linhas que começam quatro espaços mais à direita, o `Escreve:` da tabuada e `vezes = vezes + 1`, e são essas, e só essas, o corpo do ciclo. As outras estão fora: `int vezes = 1` vem antes do ciclo e `Escreve: "Fim da tabuada"` vem depois.

| Linha | Indentação | Onde está | Quantas vezes é executada |
| --- | --- | --- | ---: |
| `int vezes = 1` | nenhuma | antes do ciclo | 1 |
| `Enquanto vezes <= ULTIMO` | nenhuma | é a linha da condição | 4 |
| `Escreve: NUMERO, " x ", vezes, ...` | quatro espaços | dentro do ciclo | 3 |
| `vezes = vezes + 1` | quatro espaços | dentro do ciclo | 3 |
| `Escreve: "Fim da tabuada"` | nenhuma | depois do ciclo | 1 |

O que está dentro do ciclo executa-se uma vez por iteração, e o que está fora executa-se uma vez só. A linha do `Enquanto` executa-se mais uma vez do que o corpo, e vais perceber porquê no trace. As linhas `const` não entram na tabela nem nos traces, como nos guias anteriores: dão nome a regras do problema e não mudam o estado.

Como não há nenhuma palavra a fechar o ciclo, as mesmas linhas com outra margem fazem outro algoritmo. Se a linha `vezes = vezes + 1` ficasse alinhada com o `Enquanto`, passava para fora do corpo: só se executaria depois de o ciclo acabar, o que nunca aconteceria, porque sem ela `vezes` vale sempre 1 e a condição é sempre verdadeira. O ecrã encher-se-ia de "7 x 1 = 7". E se a última linha, `Escreve: "Fim da tabuada"`, ganhasse quatro espaços, passava a fazer parte do corpo, e a mensagem de fim aparecia três vezes, uma depois de cada linha da tabuada.

Para leres a indentação sem te enganares, põe o dedo por baixo da primeira letra do `Enquanto` e desce a direito. As linhas que começam à direita do teu dedo, até à primeira que começa em cima dele, são o corpo. É assim que o Python, a linguagem que vais aprender a seguir, marca os blocos.

### As três peças de um ciclo

Todos os ciclos que terminam têm três peças. Se faltar uma, ou se uma estiver errada, o ciclo não faz o que devia, e é quase sempre assim que os ciclos falham.

A **inicialização** dá o valor inicial às variáveis que a condição e o corpo vão usar. Fica antes do ciclo, sem indentação. Na tabuada é `int vezes = 1`.

A **condição** decide se se faz mais uma iteração. Fica na linha do `Enquanto`. Na tabuada é `vezes <= ULTIMO`, e diz em que situação se continua.

A **atualização** é a instrução, dentro do corpo, que muda a variável de que a condição depende e que aproxima o ciclo do fim. Na tabuada é `vezes = vezes + 1`. É a atualização que tira o prato da banca.

O resto do corpo é o trabalho que o ciclo faz em cada iteração. Na tabuada é o `Escreve:`.

Para cada ciclo que escreveres, responde a três perguntas, uma por peça:

1. Com que valor começa, e porquê esse?
2. Em que situação continua, e quando é que deixa de continuar?
3. O que muda em cada iteração, e essa mudança aproxima o fim?

Na tabuada: começa em 1 porque a primeira multiplicação é a do 1; continua enquanto `vezes` for menor ou igual a 3, e deixa de continuar quando chegar a 4; em cada iteração `vezes` aumenta 1, e por isso aproxima-se de 4.

### O trace linha a linha

O trace de um ciclo faz-se com as regras do guia 2, com duas novidades. A primeira é uma coluna para a condição, como no guia 3: na linha do `Enquanto` escreves a condição com os valores substituídos e o resultado. A segunda é que a mesma instrução aparece várias vezes na tabela, uma por cada vez que é executada. A tabela segue a ordem em que as instruções são executadas, e não a ordem em que estão escritas: depois da última linha do corpo, a linha seguinte da tabela é outra vez a do `Enquanto`.

| Passo | Instrução executada | vezes | Condição e resultado | Ecrã |
| ---: | --- | ---: | --- | --- |
| 0 | antes de começar | sem valor | nenhuma | nada |
| 1 | `int vezes = 1` | 1 | nenhuma | nada |
| 2 | `Enquanto vezes <= ULTIMO` | 1 | `1 <= 3` dá `true` | nada |
| 3 | `Escreve:` da tabuada | 1 | nenhuma | 7 x 1 = 7 |
| 4 | `vezes = vezes + 1` | 2 | nenhuma | nada |
| 5 | `Enquanto vezes <= ULTIMO` | 2 | `2 <= 3` dá `true` | nada |
| 6 | `Escreve:` da tabuada | 2 | nenhuma | 7 x 2 = 14 |
| 7 | `vezes = vezes + 1` | 3 | nenhuma | nada |
| 8 | `Enquanto vezes <= ULTIMO` | 3 | `3 <= 3` dá `true` | nada |
| 9 | `Escreve:` da tabuada | 3 | nenhuma | 7 x 3 = 21 |
| 10 | `vezes = vezes + 1` | 4 | nenhuma | nada |
| 11 | `Enquanto vezes <= ULTIMO` | 4 | `4 <= 3` dá `false` | nada |
| 12 | `Escreve: "Fim da tabuada"` | 4 | nenhuma | Fim da tabuada |

No passo 5 acontece o que é novo. O algoritmo acabou a última linha do corpo e voltou atrás, à linha do `Enquanto`, e avalia a condição outra vez, agora com `vezes` a valer 2. No passo 11, `vezes` já vale 4, `4 <= 3` é falso, e o algoritmo salta para a primeira linha a seguir ao corpo.

Conta as linhas do `Enquanto`: são quatro, nos passos 2, 5, 8 e 11. Três deram verdadeiro e uma deu falso. Isto é sempre assim num ciclo que termina: há sempre mais um teste da condição do que iterações, porque o último teste é o que dá falso e faz o ciclo parar.

Repara também no valor final de `vezes`: é 4, e não 3. O ciclo não para quando escreve a última linha da tabuada. Para quando `vezes` passa o limite, porque só nessa altura a condição fica falsa. Depois de um ciclo, quanto vale a variável? É uma pergunta frequente em testes, e a resposta está sempre na última linha do trace.

### A tabela de iterações

Com a tabuada até 10, a tabela teria 33 passos. Depois de perceberes como um ciclo se executa instrução a instrução, podes usar uma tabela mais curta, a **tabela de iterações**, com uma linha por cada teste da condição. Cada linha mostra o valor das variáveis no momento em que o algoritmo chega ao `Enquanto`, como uma fotografia do estado nesse instante, a condição com o resultado, e o que acontece durante a iteração que começa a seguir.

| Teste | vezes | Condição | Durante a iteração |
| --- | ---: | --- | --- |
| 1.º | 1 | `1 <= 3` dá `true` | escreve "7 x 1 = 7" |
| 2.º | 2 | `2 <= 3` dá `true` | escreve "7 x 2 = 14" |
| 3.º | 3 | `3 <= 3` dá `true` | escreve "7 x 3 = 21" |
| 4.º | 4 | `4 <= 3` dá `false` | o ciclo termina |

Cada linha resume um grupo de linhas do trace anterior. A tabela de iterações não mostra os passos um a um, mas mostra tudo o que interessa: com que valores começa cada iteração, quantas iterações há e com que valores o ciclo termina. Sempre que te pedirem o trace de um ciclo, é esta tabela que se espera, a não ser que te peçam o trace linha a linha. Nos primeiros ciclos que fizeres, faz as duas, para veres que dizem o mesmo.

### A seta que volta ao losango

No fluxograma, um ciclo desenha-se com o losango do guia 3 e com uma seta nova, que volta atrás, para cima, até ao losango da condição:

```text
                     ( Início )
                          |
                          ↓
                  [ int vezes = 1 ]
                          |
                          ↓
              /                      \
   +-------> <    vezes <= ULTIMO ?   > ----- Não ------+
   |          \                      /                  |
   |                      |                             |
   |                     Sim                            |
   |                      |                             |
   |                      ↓                             ↓
   |   / Escreve: NUMERO, " x ", vezes, ... /   / Escreve: "Fim da tabuada" /
   |                      |                             |
   |                      ↓                             ↓
   |            [ vezes = vezes + 1 ]                ( Fim )
   |                      |
   +----------------------+
```

Segue o percurso com o dedo. Do início passas pela inicialização e chegas ao losango. Se a condição for verdadeira, sais pelo `Sim`, escreves a linha da tabuada, fazes a atualização, e a seta leva-te de volta ao losango, para perguntares outra vez. Se for falsa, sais pelo `Não`, escreves a mensagem final e terminas. Para três linhas da tabuada, o dedo passa quatro vezes pelo losango, tantas quantas as linhas da tabela de iterações.

A seta de volta vai sempre ao losango. Se voltasse à inicialização, `vezes` voltaria a 1 em cada iteração e o ciclo nunca acabaria. E é a seta que sobe que te diz que há um ciclo: num fluxograma só com sequência e seleção, as setas andam sempre para baixo.

Como nos guias anteriores, os fluxogramas são para saberes ler. Desenhá-los numa aplicação é a parte opcional do [laboratório deste tema](04-repeticao-e-arrays-laboratorio.md), que só fazes quando o professor o indicar.

### O ciclo que nunca começa

Se a condição for falsa logo no primeiro teste, o corpo não se executa nenhuma vez. Diz-se que o ciclo tem zero iterações, ou que dá **zero voltas**.

Às vezes é um erro. Se alguém escrever a condição da tabuada ao contrário, `Enquanto vezes > ULTIMO`, o primeiro teste é `1 > 3`, que é falso, e o algoritmo salta logo para o fim: aparece "Fim da tabuada" e mais nada. Quem escreveu isto pensou em quando o ciclo devia parar e escreveu essa situação no `Enquanto`, que é o sítio onde se escreve quando continuar.

Outras vezes, zero voltas é exatamente o que deve acontecer. Se o algoritmo soma os pedidos que chegaram hoje e hoje não chegou nenhum, o ciclo não deve executar-se nenhuma vez, e a resposta certa é 0. Daqui sai uma regra de teste que vais usar sempre: testa o caso de zero voltas, e confirma que o algoritmo dá uma resposta com sentido. É o caso extremo do guia 1, agora com nome próprio.

### O ciclo que nunca acaba

Um **ciclo infinito** é um ciclo cuja condição nunca chega a ser falsa. O algoritmo não dá nenhum aviso: num computador, fica parado a trabalhar, ou a escrever a mesma coisa, até alguém o interromper à força. No papel, o trace mostra o problema com toda a clareza.

A causa mais frequente é a atualização. Pode faltar, pode estar fora do corpo por causa da indentação, como viste acima, e nos dois casos a tabela de iterações mostra a mesma fotografia em todas as linhas: `vezes` vale sempre 1. Num ciclo que não lê nada no corpo, se a fotografia se repetir, o ciclo é infinito.

A atualização também pode andar no sentido errado. Com `vezes = vezes - 1`, `vezes` passa a 0, -1, -2, e cada um destes números continua a ser menor ou igual a 3. A fotografia não se repete, mas afasta-se da saída. Não basta que a variável mude: tem de mudar na direção que torna a condição falsa.

E a atualização pode saltar por cima da saída. Uma condição com `!=`, como "enquanto `x` for diferente de 10", só fica falsa se `x` valer exatamente 10 num dos testes. Se `x` começar em 1 e aumentar 2 em cada volta, passa por 9 e por 11, mas nunca por 10.

A pergunta que apanha todos estes casos é a terceira das três perguntas das peças: **em cada iteração, a variável da condição muda, e aproxima-se de um valor que torna a condição falsa?** Se a resposta for não, o ciclo é infinito.

## Para: o ciclo contado

Na tabuada, sabe-se antes de o ciclo começar quantas iterações vai haver: três, ou dez. A um ciclo assim chama-se **ciclo contado**. Os ciclos contados são tão frequentes que têm uma forma curta de escrever, o `Para`, e nas aulas usamos duas formas dele.

### A primeira forma: `Para ... de ... até ...`

```text
Para vezes de 1 até ULTIMO
    Escreve: NUMERO, " x ", vezes, " = ", NUMERO * vezes
```

Lê-se "para `vezes` de 1 até ao último, escreve a linha da tabuada". A variável `vezes` vai de 1 até `ULTIMO`, de 1 em 1, e o corpo executa-se uma vez para cada valor. À variável que o `Para` controla chama-se **variável de controlo**.

As três peças estão lá, mas duas estão escondidas na primeira linha e a terceira nem se escreve. A inicialização é o `de 1`. A condição é o `até ULTIMO`, que quer dizer "continua enquanto `vezes <= ULTIMO`". A atualização é feita pelo próprio `Para`: depois da última linha do corpo, `vezes` aumenta 1 e o algoritmo volta ao teste. A tabela de iterações é igual à do `Enquanto`, e é essa a prova de que os dois algoritmos são equivalentes.

A variável de controlo não leva tipo. É o próprio `Para` que a cria, e é sempre um número inteiro. O `Para` segue quatro regras:

1. A variável de controlo avança sempre de 1 em 1.
2. Dentro do corpo não se muda a variável de controlo nem o limite. O `Para` trata disso. Se precisares de mudar a variável a meio, o ciclo não é contado, e deves usar `Enquanto`.
3. Se o limite for menor do que o valor inicial, como em `Para dia de 1 até 0`, o corpo executa-se zero vezes. É o caso de zero voltas do `Para`.
4. Depois do ciclo, não se usa o valor da variável de controlo. Ela só se usa dentro do ciclo.

### A segunda forma: as três peças à vista

Há outra maneira de escrever o `Para`, muito usada nas linguagens de programação, em que as três peças ficam escritas na primeira linha, separadas por vírgulas:

```text
Para vezes = 1, vezes <= ULTIMO, vezes++
    Escreve: NUMERO, " x ", vezes, " = ", NUMERO * vezes
```

Lê-se "para `vezes` a começar em 1, enquanto `vezes` for menor ou igual ao último, aumentando `vezes` de 1 em 1". Cada parte é uma das três peças:

1. `vezes = 1` é a inicialização. Executa-se uma só vez, antes do primeiro teste.
2. `vezes <= ULTIMO` é a condição. É testada antes de cada iteração, como a do `Enquanto`, e diz quando continuar.
3. `vezes++` é a atualização. Executa-se no fim de cada iteração, depois da última linha do corpo e antes do teste seguinte. O `++` é uma abreviatura: `vezes++` quer dizer exatamente `vezes = vezes + 1`.

Esta forma é a mais prática para percorrer arrays, como vais ver já a seguir, porque permite começar em 0 e parar antes de um número. `Para i = 0, i < 5, i++` repete o corpo 5 vezes, com `i` a valer 0, 1, 2, 3 e 4. Quando `i` chega a 5, `5 < 5` é falso e o ciclo termina.

Repara numa diferença para a primeira forma: aqui és tu que escreves as três peças, e por isso os erros do `Enquanto` voltam a ser possíveis. Com `vezes > ULTIMO` na condição, o ciclo nunca começa. Com `vezes < ULTIMO`, falta uma iteração. Com `vezes--`, que quer dizer `vezes = vezes - 1`, o ciclo nunca acaba. As três perguntas das peças servem aqui como no `Enquanto`.

A tabela seguinte põe as três escritas do mesmo ciclo lado a lado:

| Peça | Com `Enquanto` | Com `Para ... de 1 até ...` | Com as três peças à vista |
| --- | --- | --- | --- |
| Inicialização | `int vezes = 1`, antes do ciclo | `de 1`, na primeira linha | `vezes = 1`, a primeira parte |
| Condição | `vezes <= ULTIMO`, na linha do `Enquanto` | `até ULTIMO`, na primeira linha | `vezes <= ULTIMO`, a segunda parte |
| Atualização | `vezes = vezes + 1`, a última linha do corpo | não se escreve: o `Para` soma 1 | `vezes++`, a terceira parte |

No fluxograma, as duas formas do `Para` desenham-se como o `Enquanto` equivalente: a inicialização num retângulo antes do losango, a condição no losango e a atualização num retângulo no fim do corpo.

### Escolher entre `Enquanto` e `Para`

A escolha faz-se com uma pergunta: **quando o algoritmo chega ao ciclo, já se sabe quantas vezes ele se vai repetir?** Se sim, o ciclo é contado, e usa-se `Para`. Se não, porque o fim depende de alguma coisa que só acontece durante o ciclo, como um valor lido, usa-se `Enquanto`.

| Situação | Ciclo | Porquê |
| --- | --- | --- |
| Escrever a tabuada do 7 até 10 | `Para` | São 10 antes de começar |
| Ler as notas dos 25 alunos de uma turma | `Para` | São sempre 25 |
| Ler um número de dias escrito no início e depois as vendas de cada dia | `Para` | O número é lido antes de o ciclo começar |
| Ler valores até aparecer o valor que diz "acabou" | `Enquanto` | Só se sabe que acabou quando ele aparece |
| Pedir uma nota até ela ser válida | `Enquanto` | Depende do que a pessoa escrever |

Todo o `Para` se pode escrever como um `Enquanto`, e viste como. O contrário não é verdade. Se estiveres em dúvida, o `Enquanto` funciona sempre, mas obriga-te a escrever as três peças à mão, com mais oportunidades de errar. Quando o ciclo é contado, o `Para` é a escolha mais segura.

## Arrays

Até agora, cada variável guardava um valor. Uma variável `nota` guardava uma nota. Se quisesses guardar as notas de 25 alunos, precisavas de 25 variáveis, `nota1`, `nota2`, até `nota25`, e de 25 linhas para fazer seja o que for com elas. Voltávamos ao problema das dez linhas da tabuada.

Um **array** é uma variável que guarda vários valores, uns a seguir aos outros, numa ordem fixa. A cada valor guardado chama-se **elemento** do array.

A imagem mais usada é a de uma fila de cacifos numerados. A fila tem um nome, e cada cacifo tem um número e guarda uma coisa. Para ires buscar o que está num cacifo, dizes o nome da fila e o número do cacifo.

### Criar um array

No pseudocódigo das aulas, um array escreve-se como uma lista de Python: os valores entre parênteses retos, separados por vírgulas.

```text
pontuacoes = [12, 7, 20, 5]
```

Esta linha cria o array `pontuacoes` com quatro elementos, as pontuações de uma equipa em quatro jogos. Repara que o array não leva tipo à frente, ao contrário das outras variáveis: é a forma que usamos nas aulas, igual à do Python. O nome do array vai no plural, porque guarda vários valores, e isso ajuda a ler o algoritmo.

Um array pode também estar vazio, sem nenhum elemento:

```text
pontuacoes = []
```

Parece inútil, mas vais ver que é um caso de teste importante, o caso de zero voltas dos arrays.

### O índice

Cada elemento tem uma posição, a que se chama **índice**, e **os índices começam em 0**. No array `pontuacoes = [12, 7, 20, 5]`:

| Índice | 0 | 1 | 2 | 3 |
| --- | ---: | ---: | ---: | ---: |
| Elemento | 12 | 7 | 20 | 5 |

Para usar um elemento, escreve-se o nome do array e o índice entre parênteses retos. `pontuacoes[0]` é o primeiro elemento, o 12. `pontuacoes[3]` é o quarto elemento, o 5.

Porque é que se começa em 0 e não em 1? Porque o índice diz quantas posições andas a partir do início do array: o primeiro elemento está a zero posições do início. É assim no Python e no C, e por isso usamos já esta regra. Tem uma consequência que vais usar sempre: num array com `n` elementos, o último índice válido é `n - 1`. Neste array há 4 elementos, e o último índice é o 3.

Um elemento de um array usa-se como qualquer variável. Pode aparecer numa conta, numa condição ou num `Escreve:`, e pode receber um valor novo:

```text
pontuacoes = [12, 7, 20, 5]
int primeira = pontuacoes[0]
pontuacoes[1] = 9
Escreve: pontuacoes[1] + pontuacoes[2]
```

A segunda linha cria a variável `primeira` com o valor do elemento de índice 0, ou seja, 12. A terceira muda o elemento de índice 1, que passa de 7 a 9: o array fica `[12, 9, 20, 5]`. A quarta escreve 9 + 20, que dá 29.

E `pontuacoes[4]`? Não existe. O array tem os índices 0, 1, 2 e 3, e o 4 já está fora. Usar um índice que não existe é um dos erros mais frequentes com arrays, e chama-se **índice fora do array**. No papel, um algoritmo que o faz está errado. Num programa, o Python para com uma mensagem de erro. O C, que vais aprender mais tarde, foi pensado para programas muito rápidos e para dar a quem programa o controlo de cada passo, e por isso não confirma, em cada acesso, se o índice existe: essa verificação fica a cargo de quem programa. Num programa em C, um índice fora do array não dá mensagem nenhuma, e o programa continua com um valor qualquer, sem avisar. São ferramentas com propósitos diferentes, e cada uma faz a escolha que serve o seu. Em qualquer delas, o último índice válido é uma das perguntas que vais ter sempre de saber responder.

### Percorrer um array com `Para`

**Percorrer** um array é passar por todos os seus elementos, um a um, fazendo alguma coisa com cada um. É para isto que os ciclos e os arrays foram feitos.

A forma mais direta usa o `Para` com as três peças à vista, com o índice a começar em 0 e a parar antes do número de elementos:

```text
const NUMERO_DE_JOGOS = 4
pontuacoes = [12, 7, 20, 5]
Para i = 0, i < NUMERO_DE_JOGOS, i++
    Escreve: "Jogo ", i + 1, ": ", pontuacoes[i], " pontos"
```

Em cada volta, `i` vale um índice diferente, de 0 a 3, e `pontuacoes[i]` é o elemento nessa posição. O ecrã mostra "Jogo 1: 12 pontos", "Jogo 2: 7 pontos", "Jogo 3: 20 pontos" e "Jogo 4: 5 pontos". Repara no `i + 1` do `Escreve:`: o índice começa em 0, mas para as pessoas o primeiro jogo é o jogo 1.

Repara também na condição, `i < NUMERO_DE_JOGOS`, com `<` e não com `<=`. O último índice válido é o 3, e é por isso que o ciclo tem de parar antes do 4. Com `<=`, o ciclo dava mais uma volta com `i` a valer 4, e `pontuacoes[4]` é um índice fora do array.

O número de elementos está numa constante porque, no pseudocódigo das aulas, ainda não aprendemos a pedir a um array quantos elementos tem. Nos enunciados, o número de elementos é dado. Também podias escrever o mesmo ciclo com a primeira forma do `Para`, `Para i de 0 até NUMERO_DE_JOGOS - 1`: vai de 0 até 3, os mesmos índices.

### Percorrer um array com `Para cada`

Muitas vezes não interessa a posição de cada elemento, só o seu valor. Para esses casos há uma forma mais simples, o **para cada**:

```text
pontuacoes = [12, 7, 20, 5]
Para cada pontuacao em pontuacoes
    Escreve: pontuacao, " pontos"
```

Lê-se "para cada pontuação no array das pontuações, escreve-a". Em cada volta, a variável `pontuacao` recebe o elemento seguinte do array: na primeira volta vale 12, na segunda 7, na terceira 20 e na quarta 5. O ciclo dá tantas voltas quantos os elementos, e acaba sozinho quando eles se esgotam. Não há índice, não há condição a escrever, e não há como sair do array.

A variável do `Para cada` não leva tipo, tal como a variável de controlo do `Para`: é o próprio ciclo que lhe dá os valores. Costuma ter o nome do array no singular, `pontuacao` para `pontuacoes`, para se ler como uma frase.

Com um array vazio, o `Para cada` não dá nenhuma volta, e o corpo não se executa. É o caso de zero voltas dos arrays.

### Quando é preciso o índice

As duas formas percorrem o array do primeiro ao último elemento. A escolha faz-se com uma pergunta: **preciso de saber em que posição está cada elemento?**

Se só precisas dos valores, para os somar, contar ou mostrar, usa `Para cada`. É mais curto e não tens de pensar no último índice.

Se precisas da posição, usa `Para` com o índice. Precisas dela quando queres dizer em que posição está um valor ("o jogo 3 teve 20 pontos"), quando queres mudar um elemento do array (`pontuacoes[i] = 0`), ou quando queres comparar um elemento com outro do mesmo array, como o seguinte (`pontuacoes[i + 1]`).

### O `Para cada` não muda o array

Há uma razão para a regra da secção anterior, e vale a pena vê-la com calma, porque engana quase toda a gente da primeira vez.

Em cada volta do `Para cada`, a variável do ciclo recebe uma **cópia** do valor do elemento, e não o próprio elemento. Mudar a variável muda a cópia; o array fica como estava. À variável que o `Para cada` vai enchendo chama-se **variável de iteração**, e a esta forma de percorrer um array, em que cada volta trabalha com uma cópia do valor, chama-se **percorrer por valor**. Percorrer com o `Para` e o índice, em que cada volta trabalha diretamente na posição do array, chama-se **percorrer por índice**.

O exemplo seguinte mostra a diferença. O professor decidiu dar mais um valor a todas as notas de um teste, e o algoritmo tem de aumentar 1 a cada nota do array.

#### Primeira tentativa, com `Para cada`

```text
notas = [12, 8, 15]
Para cada nota em notas
    nota = nota + 1
Escreve: notas[0], " ", notas[1], " ", notas[2]
```

Antes de leres o trace, prevê o que aparece no ecrã. O trace tem uma coluna para a `nota` e outra para o array `notas`, lado a lado:

| Passo | Instrução executada | nota | notas | Ecrã |
| ---: | --- | ---: | --- | --- |
| 0 | antes de começar | sem valor | sem valor | nada |
| 1 | `notas = [12, 8, 15]` | sem valor | [12, 8, 15] | nada |
| 2 | `Para cada`, 1.ª volta: `nota` recebe uma cópia de `notas[0]` | 12 | [12, 8, 15] | nada |
| 3 | `nota = nota + 1` | 13 | [12, 8, 15] | nada |
| 4 | `Para cada`, 2.ª volta: `nota` recebe uma cópia de `notas[1]` | 8 | [12, 8, 15] | nada |
| 5 | `nota = nota + 1` | 9 | [12, 8, 15] | nada |
| 6 | `Para cada`, 3.ª volta: `nota` recebe uma cópia de `notas[2]` | 15 | [12, 8, 15] | nada |
| 7 | `nota = nota + 1` | 16 | [12, 8, 15] | nada |
| 8 | `Para cada`: não há mais elementos, o ciclo termina | 16 | [12, 8, 15] | nada |
| 9 | `Escreve:` das três notas | 16 | [12, 8, 15] | 12 8 15 |

A coluna `nota` muda três vezes. A coluna `notas` nunca muda. O algoritmo não tem nenhum erro de escrita, corre até ao fim, e não fez o que se pedia: as notas continuam 12, 8 e 15.

Faz esta pergunta: no passo 3, a `nota` passou a valer 13; qual das três notas do array passou a 13? Nenhuma. A `nota` é uma cópia, e uma cópia não sabe de que posição veio. Por isso, mesmo que quisesse, não conseguia mudar o elemento certo. Para mudar um elemento do array, o algoritmo precisa de saber a sua posição, e isso é o índice.

#### A versão certa, com o índice

```text
const N_NOTAS = 3

notas = [12, 8, 15]
Para i = 0, i < N_NOTAS, i++
    notas[i] = notas[i] + 1
Escreve: notas[0], " ", notas[1], " ", notas[2]
```

Aqui não há variável `nota`. Em cada volta, o algoritmo lê o elemento da posição `i`, soma-lhe 1 e escreve o resultado na mesma posição:

| Passo | Instrução executada | i | Condição e resultado | notas | Ecrã |
| ---: | --- | ---: | --- | --- | --- |
| 0 | antes de começar | sem valor | nenhuma | sem valor | nada |
| 1 | `notas = [12, 8, 15]` | sem valor | nenhuma | [12, 8, 15] | nada |
| 2 | `i = 0` | 0 | nenhuma | [12, 8, 15] | nada |
| 3 | teste do `Para` | 0 | `0 < 3` dá `true` | [12, 8, 15] | nada |
| 4 | `notas[i] = notas[i] + 1`, ou seja 12 + 1 | 0 | nenhuma | [13, 8, 15] | nada |
| 5 | `i++` | 1 | nenhuma | [13, 8, 15] | nada |
| 6 | teste do `Para` | 1 | `1 < 3` dá `true` | [13, 8, 15] | nada |
| 7 | `notas[i] = notas[i] + 1`, ou seja 8 + 1 | 1 | nenhuma | [13, 9, 15] | nada |
| 8 | `i++` | 2 | nenhuma | [13, 9, 15] | nada |
| 9 | teste do `Para` | 2 | `2 < 3` dá `true` | [13, 9, 15] | nada |
| 10 | `notas[i] = notas[i] + 1`, ou seja 15 + 1 | 2 | nenhuma | [13, 9, 16] | nada |
| 11 | `i++` | 3 | nenhuma | [13, 9, 16] | nada |
| 12 | teste do `Para` | 3 | `3 < 3` dá `false`: o ciclo termina | [13, 9, 16] | nada |
| 13 | `Escreve:` das três notas | 3 | nenhuma | [13, 9, 16] | 13 9 16 |

Agora é a coluna `notas` que muda, um elemento por volta. Repara no passo 12, o teste que dá falso: é ele que faz o ciclo dar exatamente três voltas, uma por cada índice válido, 0, 1 e 2. Quando `i` chega a 3, o ciclo termina sem nunca usar `notas[3]`, que não existe.

#### Usar o valor como se fosse a posição

Quem percebe que é preciso o array, mas continua com o `Para cada`, escreve às vezes isto:

```text
Para cada nota em notas
    notas[nota] = nota + 1
```

Na primeira volta, a `nota` vale 12, e o algoritmo tenta escrever em `notas[12]`. Num array com três elementos, os índices válidos são 0, 1 e 2: o 12 é um índice fora do array. O erro está em usar o valor de um elemento como se fosse a sua posição. São duas coisas diferentes: em `notas = [12, 8, 15]`, o elemento de índice 0 vale 12.

#### A regra prática

Quando só precisas de ler os elementos, para os somar, contar, comparar ou mostrar, percorre por valor, com o `Para cada`. Quando precisas de mudar os elementos do array, percorre por índice, com o `Para` e o índice.

Esta regra vale para arrays de números e de textos, como os deste guia. Num array de arrays, a variável do `Para cada` não recebe uma cópia de cada linha, mas a própria linha, e a conversa é outra: vais vê-la em Python, quando aprenderes o que é uma referência. Até lá, sempre que quiseres mudar alguma coisa num array, usa o índice, e a dúvida não se põe.

## Contadores e acumuladores

Um **padrão** é uma forma de resolver um pequeno problema que aparece vezes sem conta, em algoritmos diferentes. Os padrões desta secção e das seguintes vão aparecer em quase todos os algoritmos que escreveres até ao fim do ano.

### O contador

Um **contador** é uma variável que conta quantas vezes uma coisa aconteceu. Segue três regras:

1. Começa em 0, antes do ciclo. Antes de se contar o que quer que seja, já se contaram zero coisas.
2. Sempre que a coisa acontece, aumenta 1: `contador = contador + 1`.
3. Só se lê o resultado depois do ciclo. Durante o ciclo, o contador tem uma contagem parcial.

Se a linha que aumenta o contador estiver diretamente no corpo do ciclo, conta todas as voltas. Se estiver dentro de um `Se`, com oito espaços, conta só as voltas em que a condição é verdadeira. É esta a forma mais útil: contar quantos valores cumprem uma regra. Mais uma vez, é a indentação que decide.

Exemplo: quantos jogos tiveram 10 ou mais pontos?

```text
const MINIMO = 10
pontuacoes = [12, 7, 20, 5]
int jogosBons = 0
Para cada pontuacao em pontuacoes
    Se pontuacao >= MINIMO
        jogosBons = jogosBons + 1
Escreve: "Jogos com ", MINIMO, " ou mais pontos: ", jogosBons
```

O contador aumenta com o 12 e com o 20, e o algoritmo escreve 2.

### O acumulador

Um **acumulador** é uma variável que vai somando valores ao longo das voltas. Segue três regras parecidas com as do contador:

1. Começa em 0, antes do ciclo. A soma de nada é zero.
2. Em cada volta, soma-se o valor: `total = total + valor`.
3. Só se lê o resultado depois do ciclo.

A diferença está na regra 2. O contador soma 1, seja qual for o valor, e responde à pergunta "quantos?". O acumulador soma o próprio valor, e responde à pergunta "quanto?".

### Contar e somar no mesmo ciclo, e calcular a média

Com um contador e um acumulador no mesmo ciclo calcula-se uma média: a soma a dividir pelo número de valores. Como ainda não sabemos pedir a um array quantos elementos tem, o próprio ciclo pode contá-los: um contador que aumenta em todas as voltas conta os elementos.

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

Num ciclo com `Para cada`, a tabela de iterações tem uma linha por volta. Como não há condição escrita, mostra-se em cada linha o elemento dessa volta e o valor das variáveis no fim da volta:

| Volta | pontuacao | quantidade no fim da volta | total no fim da volta |
| ---: | ---: | ---: | ---: |
| antes do ciclo | sem valor | 0 | 0 |
| 1.ª | 12 | 1 | 12 |
| 2.ª | 7 | 2 | 19 |
| 3.ª | 20 | 3 | 39 |
| 4.ª | 5 | 4 | 44 |

Depois do ciclo, `quantidade` vale 4 e `total` vale 44. Como `4 > 0` é verdadeiro, calcula-se a média, 44 / 4, que dá 11, e o algoritmo escreve "Média: 11 pontos". A conta usa `/` e não `div`, porque uma média pode ter parte decimal, e a variável `media` é `float`.

Porquê o `Se quantidade > 0`? Por causa do caso de zero voltas. Com o array vazio, o ciclo não dá nenhuma volta, `quantidade` fica 0 e `total` fica 0. Calcular a média seria fazer 0 / 0, e não se pode dividir por zero: a conta não tem resultado. Sem o `Se`, o algoritmo pedia uma conta impossível. Com ele, escreve uma mensagem que explica porque é que não há média. Sempre que dividires por um contador, pergunta-te o que acontece se ele ficar a zero.

### Inicializar fora do ciclo

Os contadores e os acumuladores inicializam-se sempre antes do ciclo, sem indentação. Se a linha `int total = 0` estivesse dentro do ciclo, o total voltaria a zero no início de cada volta, antes de somar o elemento dessa volta, e no fim guardaria só o último elemento. A regra a fixar: o que se inicializa dentro do ciclo recomeça em cada volta.

## A sentinela: ler até aparecer o valor que diz "acabou"

Imagina uma bilheteira de um cinema. O funcionário escreve o número de bilhetes de cada venda, à medida que as vendas acontecem, e no fim do dia o algoritmo diz quantas vendas houve e quantos bilhetes se venderam. Ninguém sabe, quando o ciclo começa, quantas vendas vão ser. O `Para` não serve, e não há nenhum array: os valores chegam um a um, lidos do teclado.

A solução é combinar um valor especial que quer dizer "acabou". Quem escreve os dados escreve esse valor no fim, e o algoritmo, quando o lê, sabe que não há mais dados. A este valor chama-se **sentinela**. É como a última pessoa de uma fila levar uma placa a dizer "sou a última": quem atende não precisa de contar a fila, só precisa de parar quando vir a placa.

A sentinela tem de cumprir duas regras. Não pode ser um valor que os dados verdadeiros possam ter, senão o algoritmo pararia no meio dos dados. E quem escreve os dados tem de saber qual é, e por isso a pergunta do `Escreve:` diz-lho. Na bilheteira, nenhuma venda tem 0 bilhetes, e o 0 serve de sentinela.

Um ciclo com sentinela tem sempre esta forma:

- antes do ciclo lê-se o primeiro valor. A esta leitura chama-se **leitura antecipada**, e é a inicialização;
- a condição é "o valor lido não é a sentinela";
- o corpo trata o valor e, como última instrução, ainda indentada, lê o valor seguinte. Essa leitura é a atualização.

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

As duas leituras não se escrevem da mesma maneira. A primeira é a linha onde `bilhetesDaVenda` nasce, e leva o tipo. A do fim do corpo usa uma variável que já existe, e não o leva.

Porquê ler antes do ciclo e no fim do corpo, e não no princípio do corpo? Porque cada valor tem de passar pela condição antes de ser tratado. Com esta forma, o valor lido vai sempre direto para o teste. Se for um dado, entra no corpo e é tratado. Se for a sentinela, a condição dá falso e o ciclo termina, sem a sentinela ter sido tratada como um dado.

Tabela de iterações com as vendas 2, 4, 1 e, no fim, a sentinela 0 (sem as perguntas):

| Teste | bilhetesDaVenda | vendas | bilhetes | Condição | Durante a iteração |
| --- | ---: | ---: | ---: | --- | --- |
| 1.º | 2 | 0 | 0 | `2 != 0` dá `true` | lê 4 |
| 2.º | 4 | 1 | 2 | `4 != 0` dá `true` | lê 1 |
| 3.º | 1 | 2 | 6 | `1 != 0` dá `true` | lê 0 |
| 4.º | 0 | 3 | 7 | `0 != 0` dá `false` | o ciclo termina |

Três vendas, sete bilhetes. A sentinela aparece no último teste e nada é feito com ela: não é contada nem somada. Se o primeiro valor escrito for logo 0, porque não houve vendas, o ciclo dá zero voltas e o algoritmo escreve 0 vendas e 0 bilhetes, que é a resposta certa.

Agora o erro que este padrão existe para evitar. Quem ainda não conhece a leitura antecipada costuma ler no princípio do corpo, e, como a condição precisa de um valor no primeiro teste, inventa um valor qualquer só para entrar no ciclo, como `int bilhetesDaVenda = 1`. Com os mesmos dados, essa versão lê o 0 dentro do corpo, conta-o como venda antes de a condição o poder testar, e escreve "Vendas: 4", quando foram três. O valor inventado, que não vem de lado nenhum, já era um sinal de alarme.

## Validação repetida

No guia 3 validaste uma nota com um `Se`: se fosse inválida, o algoritmo escrevia "Nota inválida" e terminava. Quem se tinha enganado tinha de começar tudo de novo. Com um ciclo dá para fazer melhor: pedir o valor outra vez, e outra, até ser válido. A isto chama-se **validação repetida**.

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

As três peças: a inicialização é a primeira leitura, antes do ciclo, como na sentinela; a condição é a de nota inválida, a mesma do guia 3, com `ou`; a atualização é a leitura dentro do corpo, que substitui o valor inválido por um novo. Se a pessoa escrever 25, depois -3 e depois 14, o ciclo dá duas voltas, com uma mensagem de erro em cada, e termina com 14. Se escrever logo 14, o ciclo dá zero voltas, e está certo: não há nada a corrigir.

O mais útil deste padrão está no que vem depois do ciclo. Quando o algoritmo chega à primeira linha a seguir ao corpo, a condição do ciclo acabou de dar falso, e por isso tens a certeza de que a nota está entre 0 e 20. O resto do algoritmo pode usá-la sem voltar a verificar. É uma ideia que vale para todos os ciclos: depois de um ciclo, a sua condição é falsa, e isso diz-te alguma coisa sobre o estado.

## Parar e Continuar

Às vezes é preciso mudar o caminho de um ciclo a meio de uma volta. Para isso há duas instruções, que se escrevem sozinhas numa linha, quase sempre dentro de um `Se`.

### `Parar`: sair do ciclo já

`Parar` termina o ciclo imediatamente. As linhas do corpo que estão abaixo dele não se executam, não há mais voltas, e o algoritmo continua na primeira linha a seguir ao ciclo.

O uso mais comum é numa **pesquisa**: procurar um valor num array e parar assim que se encontra, porque não vale a pena olhar para o resto. Exemplo: os golos de uma equipa em cinco jogos estão no array `golos = [2, 1, 0, 3, 0]`. Em que jogo é que a equipa ficou a zero pela primeira vez?

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

Tabela de iterações:

| Teste | i | golos[i] | encontrado | Condição do `Para` | Durante a iteração |
| --- | ---: | ---: | --- | --- | --- |
| 1.º | 0 | 2 | `false` | `0 < 5` dá `true` | `2 == 0` dá `false`; nada |
| 2.º | 1 | 1 | `false` | `1 < 5` dá `true` | `1 == 0` dá `false`; nada |
| 3.º | 2 | 0 | `false` | `2 < 5` dá `true` | `0 == 0` dá `true`; escreve "Primeiro jogo sem golos: jogo 3"; `encontrado` passa a `true`; `Parar` |

O ciclo terminou na terceira volta, sem olhar para o 3 nem para o segundo 0. Como `encontrado` vale `true`, a última mensagem não aparece.

Repara no que a variável `encontrado` resolve. Quando o ciclo termina, pode ter terminado por duas razões: porque o `Parar` o fez sair, ou porque os índices se esgotaram sem encontrar nenhum 0. Depois do ciclo, a variável `encontrado` diz qual das duas aconteceu. A uma variável `bool` usada assim chama-se uma **bandeira**: começa em `false` e passa a `true` quando acontece o que se procura. Com `golos = [2, 1, 4, 3, 2]`, o ciclo dá as cinco voltas, a bandeira fica em `false`, e aparece "A equipa marcou em todos os jogos."

### `Continuar`: saltar para a volta seguinte

`Continuar` termina só a volta atual. As linhas do corpo que estão abaixo dele não se executam nessa volta, e o ciclo passa à volta seguinte, como se tivesse chegado ao fim do corpo.

Exemplo: um sensor regista temperaturas, mas às vezes dá erro e regista um número negativo. Para somar só as leituras boas:

```text
leituras = [5, -2, 8, -1, 4]
int total = 0
Para cada leitura em leituras
    Se leitura < 0
        Continuar
    total = total + leitura
Escreve: "Total das leituras válidas: ", total
```

Nas voltas do -2 e do -1, o `Continuar` salta a soma, e o total fica 5 + 8 + 4, que dá 17.

O mesmo resultado consegue-se sem `Continuar`, com a soma dentro de um `Se leitura >= 0`. As duas formas estão certas. O `Continuar` ajuda quando há vários casos a pôr de lado logo no princípio da volta, e o resto do corpo fica mais limpo.

Um cuidado importante com `Continuar` dentro de um `Enquanto`: se a atualização estiver abaixo do `Continuar`, também é saltada nessa volta. A variável da condição não muda, a volta seguinte começa no mesmo estado, e o ciclo pode nunca acabar. Num `Enquanto`, confirma sempre que o `Continuar` não salta a atualização. No `Para` e no `Para cada` este perigo não existe, porque é o próprio ciclo que trata da atualização.

## Arrays de arrays: uma tabela

Um elemento de um array pode ser, ele próprio, um array. A um array de arrays chama-se muitas vezes **tabela**, porque se lê como uma tabela com linhas e colunas. Esta secção é uma introdução: vais trabalhar mais com tabelas mais à frente no curso.

Imagina as notas de dois alunos em três testes:

```text
notas = [[12, 15, 9], [8, 11, 14]]
```

O array `notas` tem dois elementos, e cada um é um array com três notas. O primeiro, `notas[0]`, é `[12, 15, 9]`, as notas do primeiro aluno. O segundo, `notas[1]`, é `[8, 11, 14]`, as notas do segundo. Lido como tabela:

| | Teste 0 | Teste 1 | Teste 2 |
| --- | ---: | ---: | ---: |
| Aluno 0 | 12 | 15 | 9 |
| Aluno 1 | 8 | 11 | 14 |

Para chegar a uma nota, dizem-se dois índices: primeiro a linha, depois a coluna. `notas[1][2]` é a nota do aluno 1 no teste 2, ou seja, 14. `notas[0][1]` é 15. Lê-se da esquerda para a direita: `notas[1]` é a linha do segundo aluno, e o `[2]` escolhe a terceira nota dessa linha.

Para percorrer uma tabela inteira usam-se dois `Para`, um dentro do outro:

```text
const NUMERO_DE_ALUNOS = 2
const NUMERO_DE_TESTES = 3
notas = [[12, 15, 9], [8, 11, 14]]
Para a = 0, a < NUMERO_DE_ALUNOS, a++
    Para t = 0, t < NUMERO_DE_TESTES, t++
        Escreve: "Aluno ", a + 1, ", teste ", t + 1, ": ", notas[a][t]
```

O `Para` de dentro está indentado debaixo do de fora, e o seu corpo tem oito espaços. Funciona assim: para cada valor de `a`, o `Para` de dentro dá todas as suas voltas. Com `a` a valer 0, `t` vale 0, 1 e 2, e escrevem-se as três notas do primeiro aluno. Depois `a` passa a 1, o `Para` de dentro recomeça do 0, e escrevem-se as três notas do segundo. O corpo de dentro executa-se 2 vezes 3, ou seja, 6 vezes, uma por cada nota da tabela.

## Exemplo guiado: a campanha de recolha de alimentos

### Passo 1: o enunciado

> A escola organiza uma campanha de recolha de alimentos. À medida que cada turma entrega os alimentos, a funcionária escreve quantos quilos a turma trouxe, um número inteiro. Uma turma pode não ter trazido nada, e nesse caso a funcionária escreve 0. Quando não há mais turmas, escreve -1. O algoritmo mostra quantas turmas entregaram, o total de quilos e a média por turma, mas a média só se houver pelo menos uma turma.
>
> No fim da campanha, os quilos das 6 turmas do 10.º ano ficaram registados num array, `quilosPorTurma = [12, 0, 9, 15, 6, 18]`. A diretora quer saber que turmas trouxeram mais do que a média dessas 6 turmas.

O enunciado tem duas partes, e cada uma vai ser um algoritmo. A primeira lê os valores do teclado, até à sentinela. A segunda trabalha com um array já preenchido.

### Passo 2: o contrato da primeira parte

A entrada é uma sequência de números inteiros, um por turma, iguais ou maiores do que zero, terminada por -1.

As saídas são o número de turmas que entregaram, o total de quilos e a média por turma, com parte decimal. Quando não houver nenhuma turma, a saída diz que não há média.

A restrição mais importante está numa frase discreta: "uma turma pode não ter trazido nada, e nesse caso a funcionária escreve 0". O 0 é um dado verdadeiro, e por isso não pode ser a sentinela. É por isso que a sentinela é o -1: nenhuma turma traz quilos negativos.

Os exemplos concretos, calculados à mão, cobrem os casos que a regra dos ciclos manda testar:

| Valores escritos | Turmas | Total | Média | Porque é que este caso foi escolhido |
| --- | ---: | ---: | --- | --- |
| -1 | 0 | 0 | não há média | Zero voltas: ninguém entregou |
| 15, -1 | 1 | 15 | 15 | Uma só volta |
| 12, 0, 9, -1 | 3 | 21 | 7 | Várias voltas, com uma turma que trouxe 0 |

O terceiro caso confirma que o 0 é contado como uma turma: três turmas entregaram, mesmo que uma tenha trazido 0 quilos.

### Passo 3: as peças do ciclo

O ciclo é de sentinela, porque não se sabe quantas turmas vão entregar.

- Inicialização: o contador `turmas` e o acumulador `totalQuilos` começam em 0, e lê-se o primeiro valor antes do ciclo, a leitura antecipada.
- Condição: o valor lido não é a sentinela, `quilos != SENTINELA`.
- Atualização: a leitura do valor seguinte, como última linha do corpo.
- Trabalho de cada volta: contar a turma e somar os seus quilos.

Depois do ciclo, a média só se calcula se `turmas > 0`.

### Passo 4: o pseudocódigo da primeira parte

```text
const SENTINELA = -1
int turmas = 0
int totalQuilos = 0
Escreve: "Quilos entregues pela turma (-1 para terminar)?"
int quilos = ler valor
Enquanto quilos != SENTINELA
    turmas = turmas + 1
    totalQuilos = totalQuilos + quilos
    Escreve: "Quilos entregues pela turma (-1 para terminar)?"
    quilos = ler valor
Escreve: "Turmas que entregaram: ", turmas
Escreve: "Total: ", totalQuilos, " kg"
Se turmas > 0
    float media = totalQuilos / turmas
    Escreve: "Média por turma: ", media, " kg"
Senão
    Escreve: "Não houve entregas, por isso não há média."
```

As decisões, uma a uma:

1. A sentinela é uma constante, com o nome a dizer o que é, e vale -1 porque o 0 é um dado.
2. O contador e o acumulador nascem antes do ciclo, com 0. Dentro do ciclo recomeçariam em cada volta.
3. A pergunta diz qual é a sentinela, para a funcionária saber como terminar.
4. A primeira leitura nasce antes do ciclo e leva o tipo; a segunda, no fim do corpo, não o leva.
5. A média calcula-se depois do ciclo, quando a contagem e a soma estão completas, e só dentro do `Se turmas > 0`.

O mesmo algoritmo em frases claras também é válido:

1. Começa com zero turmas e zero quilos.
2. Pergunta os quilos da turma, dizendo que -1 termina, e lê o valor.
3. Enquanto o valor lido não for -1: conta mais uma turma, soma os quilos ao total, e pergunta e lê os quilos da turma seguinte.
4. Quando aparecer o -1, mostra o número de turmas e o total.
5. Se houve pelo menos uma turma, mostra a média, que é o total a dividir pelo número de turmas. Se não houve nenhuma, diz que não há média.

### Passo 5: o trace dos três casos

Com 12, 0, 9 e -1 (sem as perguntas):

| Teste | quilos | turmas | totalQuilos | Condição | Durante a iteração |
| --- | ---: | ---: | ---: | --- | --- |
| 1.º | 12 | 0 | 0 | `12 != -1` dá `true` | lê 0 |
| 2.º | 0 | 1 | 12 | `0 != -1` dá `true` | lê 9 |
| 3.º | 9 | 2 | 12 | `9 != -1` dá `true` | lê -1 |
| 4.º | -1 | 3 | 21 | `-1 != -1` dá `false` | o ciclo termina |

Depois do ciclo, `turmas > 0` é `3 > 0`, verdadeiro, e a média é 21 / 3, que dá 7. No ecrã: "Turmas que entregaram: 3", "Total: 21 kg" e "Média por turma: 7 kg". Repara no 2.º teste: o 0 passou pela condição, `0 != -1` deu verdadeiro, e foi contado como turma, como o contrato pede.

Com 15 e -1:

| Teste | quilos | turmas | totalQuilos | Condição | Durante a iteração |
| --- | ---: | ---: | ---: | --- | --- |
| 1.º | 15 | 0 | 0 | `15 != -1` dá `true` | lê -1 |
| 2.º | -1 | 1 | 15 | `-1 != -1` dá `false` | o ciclo termina |

Uma volta. A média é 15 / 1, que dá 15.

Com -1 logo de início:

| Teste | quilos | turmas | totalQuilos | Condição | Durante a iteração |
| --- | ---: | ---: | ---: | --- | --- |
| 1.º | -1 | 0 | 0 | `-1 != -1` dá `false` | o ciclo termina |

Zero voltas. Depois do ciclo, `turmas > 0` é `0 > 0`, falso, e o algoritmo escreve "Não houve entregas, por isso não há média.". Sem o `Se`, tentaria calcular 0 / 0.

Os três casos dão o que o contrato previu.

### Passo 6: a segunda parte, com o array

Agora os dados já estão no array `quilosPorTurma = [12, 0, 9, 15, 6, 18]`, e a pergunta é que turmas trouxeram mais do que a média.

Há um pormenor que decide a forma do algoritmo: para saber se uma turma está acima da média, é preciso saber a média, e a média só se conhece depois de somar todas as turmas. Por isso o array é percorrido duas vezes. A primeira volta soma, e calcula-se a média. A segunda compara cada turma com essa média.

Na primeira volta só interessam os valores, e usa-se `Para cada`. Na segunda é preciso dizer o número da turma, e por isso é preciso o índice, e usa-se `Para`.

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

Aqui a média não precisa de `Se`: o enunciado diz que o array tem as 6 turmas, e por isso nunca está vazio. Num array que pudesse estar vazio, o cuidado do passo 4 voltava a ser preciso.

### Passo 7: o trace da segunda parte

Primeiro ciclo, com `Para cada`:

| Volta | quilos | total no fim da volta |
| ---: | ---: | ---: |
| antes do ciclo | sem valor | 0 |
| 1.ª | 12 | 12 |
| 2.ª | 0 | 12 |
| 3.ª | 9 | 21 |
| 4.ª | 15 | 36 |
| 5.ª | 6 | 42 |
| 6.ª | 18 | 60 |

A média é 60 / 6, que dá 10.

Segundo ciclo, com o índice:

| Teste | i | quilosPorTurma[i] | Comparação com a média | acimaDaMedia no fim da volta | Ecrã |
| --- | ---: | ---: | --- | ---: | --- |
| 1.º | 0 | 12 | `12 > 10` dá `true` | 1 | A turma 1 trouxe mais do que a média |
| 2.º | 1 | 0 | `0 > 10` dá `false` | 1 | nada |
| 3.º | 2 | 9 | `9 > 10` dá `false` | 1 | nada |
| 4.º | 3 | 15 | `15 > 10` dá `true` | 2 | A turma 4 trouxe mais do que a média |
| 5.º | 4 | 6 | `6 > 10` dá `false` | 2 | nada |
| 6.º | 5 | 18 | `18 > 10` dá `true` | 3 | A turma 6 trouxe mais do que a média |
| 7.º | 6 | não se usa | `6 < 6` dá `false`: o ciclo termina | 3 | nada |

No fim aparece "Turmas acima da média: 3". Repara na última linha: `i` chegou a 6, e o ciclo terminou sem nunca usar `quilosPorTurma[6]`, que não existe. O último índice usado foi o 5, o último válido num array de 6 elementos. E repara no `i + 1` do `Escreve:`: a turma de índice 0 é, para as pessoas, a turma 1.

## Erros frequentes

Os erros desta secção são versões erradas dos algoritmos deste guia. Para cada um vais ver o que acontece e que entrada o revela, porque um erro só fica bem explicado quando se consegue mostrar a entrada que o faz aparecer.

### O ciclo infinito

Um ciclo fica infinito quando a atualização falta, quando está fora do corpo por causa da indentação, quando anda no sentido errado ou quando salta por cima do valor que tornaria a condição falsa. A tabuada não lê nada, e por isso qualquer execução mostra o erro: sem a atualização, ou com ela fora do corpo, `vezes` fica sempre a valer 1 e o ecrã enche-se de "7 x 1 = 7"; com `vezes = vezes - 1`, `vezes` passa a 0, -1, -2, e afasta-se cada vez mais do 4. Encontra-se com a tabela de iterações: se a fotografia se repetir, ou se a variável da condição se afastar do valor que faz o ciclo terminar, o ciclo é infinito.

Num `Enquanto` com `Continuar`, o erro só aparece com uma entrada que faça executar o `Continuar`. Se a atualização estiver abaixo dele, essa volta não muda a variável da condição, a volta seguinte começa no mesmo estado, e o ciclo não sai dali. Com entradas que nunca fazem executar o `Continuar`, o ciclo termina e o erro passa despercebido. Por isso, confirma sempre que o `Continuar` não salta a atualização, e testa o ciclo com um valor que o faça executar.

### A condição de paragem no sítio da condição de continuação

Quem pensa em quando o ciclo deve parar escreve essa situação no `Enquanto`, como `Enquanto vezes > ULTIMO` em vez de `Enquanto vezes <= ULTIMO`. Na tabuada, o primeiro teste é `1 > 3`, que dá falso, e o ciclo dá zero voltas quando devia dar três: aparece "Fim da tabuada" e mais nada. Como a tabuada não lê nada, o erro aparece logo na primeira execução. A condição do `Enquanto` diz quando continuar, e por isso a pergunta a fazer antes de a escrever é "em que situação quero continuar?".

### Uma volta a mais ou a menos

Trocar `<` por `<=`, ou começar em 0 quando se devia começar em 1, dá uma volta a mais. Trocar `<=` por `<`, ou começar em 1 quando se devia começar em 0, dá uma volta a menos. Num ciclo que devia dar quatro voltas, `Para i = 0, i <= 4, i++` dá cinco, e `Para i = 1, i < 4, i++` dá três.

Na tabuada até 3, `Para vezes = 0, vezes <= ULTIMO, vezes++` escreve uma linha a mais, "7 x 0 = 0", logo na primeira volta. A somar as pontuações `[12, 7, 20, 5]`, o ciclo `Para i = 1, i < 4, i++` dá um total de 32 em vez de 44, porque a primeira volta já usa `pontuacoes[1]` e o 12 nunca é somado. Com um array cujo primeiro elemento fosse 0, essa soma dava o resultado certo por acaso, e o erro passava despercebido. Uma volta a mais ou a menos aparece sempre na primeira ou na última volta, e por isso testa sempre essas duas e confirma os valores da variável de controlo.

### O índice fora do array

Num array com 4 elementos, como `pontuacoes = [12, 7, 20, 5]`, o ciclo `Para i = 0, i <= 4, i++` dá uma quinta volta, com `i` a valer 4, e chega a `pontuacoes[4]`, que não existe. O último índice válido é o número de elementos menos 1, e por isso a condição certa é `i < 4`. O erro aparece sempre na última volta, sejam quais forem os valores guardados no array, e é aí que se testa: no trace, é a linha em que `i` vale 4 que o mostra, porque não há nenhum elemento para escrever na coluna de `pontuacoes[i]`. Com o `Para cada`, este erro não pode acontecer, porque não há índice.

### Mudar a variável do `Para cada` para mudar o array

Quem quer aumentar 1 a cada nota e escreve `Para cada nota em notas` seguido de `nota = nota + 1` não muda nada no array. A variável de iteração recebe uma cópia de cada elemento, e mudá-la muda só a cópia. O erro vê-se escrevendo o array depois do ciclo: com `notas = [12, 8, 15]`, o ecrã mostra "12 8 15", quando devia mostrar "13 9 16". Para mudar os elementos, percorre por índice, com `notas[i] = notas[i] + 1`, como na secção "O `Para cada` não muda o array".

### O contador ou o acumulador inicializado dentro do ciclo

Com a linha `int total = 0` dentro do corpo, o total recomeça em cada volta, e no fim fica só com o último valor. A entrada que revela o erro é qualquer array com dois ou mais elementos: com `pontuacoes = [12, 7, 20, 5]`, o total acaba em 5, quando devia acabar em 44. Com um array de um só elemento, o erro não se vê, porque esse elemento é ao mesmo tempo o último valor e a soma de todos. Contadores e acumuladores inicializam-se antes do ciclo, sem indentação.

### O contador no sítio errado

Se a linha `jogosBons = jogosBons + 1` tiver quatro espaços, fica fora do `Se` e conta todos os jogos, e não só os bons. Com oito espaços, dentro do `Se`, conta só os que cumprem a condição. A entrada que revela o erro é um array com pelo menos um jogo abaixo do mínimo: com `pontuacoes = [12, 7, 20, 5]`, a versão errada escreve 4, quando devia escrever 2. Com um array em que todos os jogos tenham 10 ou mais pontos, as duas versões dão o mesmo, e o erro passa despercebido.

### A sentinela tratada como um dado

Quem lê o valor no princípio do corpo, e inventa um valor antes do ciclo só para entrar nele, trata a sentinela como um dado: ela é lida dentro do corpo e é contada antes de a condição a poder testar. Qualquer sequência de dados revela o erro, porque a sentinela aparece sempre no fim. Na bilheteira, com as vendas 2, 4 e 1 seguidas da sentinela 0, a versão errada escreve "Vendas: 4", quando foram três. Se a primeira coisa escrita for logo o 0, a versão errada conta uma venda num dia sem vendas. Conforme o valor da sentinela, ela também é somada: na campanha, onde a sentinela é -1, a versão errada tirava um quilo ao total. Usa sempre a leitura antecipada, antes do ciclo, e a leitura no fim do corpo.

### A média sem valores

Calcular a média sem o `Se` divide por um contador que pode ficar a zero. A entrada que revela o erro é a do caso de zero voltas: na campanha, o -1 escrito logo de início; na média das pontuações, o array vazio. Com zero voltas, a conta é 0 / 0, que não tem resultado. Com um ou mais valores, a versão sem `Se` dá a média certa, e por isso o erro só aparece a quem testa o caso de zero voltas. Põe a média dentro de um `Se contador > 0`.

### Testar só o caso normal

Um ciclo testado só com três ou quatro valores parece quase sempre certo, porque vários dos erros desta secção só aparecem noutros casos. Testa sempre três casos: zero voltas, uma volta e várias voltas. Num array, isso quer dizer um array vazio, um array com um elemento e um array com vários. O caso de zero voltas revela a média sem valores. O caso de várias voltas revela o acumulador inicializado dentro do ciclo, que com uma só volta dá o resultado certo.

## Verificar o que aprendeste

Usa esta lista para te testares. Para cada ponto, experimenta fazê-lo sem olhar para o guia. Se não conseguires, volta à secção correspondente.

- Consegues explicar as quatro regras do `Enquanto` e porque é que há sempre mais um teste do que voltas.
- Consegues apontar as três peças de qualquer ciclo e responder às três perguntas sobre elas.
- Consegues fazer o trace de um ciclo, linha a linha e numa tabela de iterações, e dizer quanto vale cada variável depois do ciclo.
- Consegues dizer, de um ciclo escrito, se ele termina, e mostrar com a tabela de iterações porque é que um ciclo infinito não termina.
- Consegues escrever o mesmo ciclo com `Enquanto`, com `Para ... de ... até ...` e com as três peças à vista.
- Consegues escolher entre `Enquanto` e `Para` e justificar a escolha.
- Consegues criar um array, dizer o elemento de um índice e qual é o último índice válido, e explicar o que é um índice fora do array.
- Consegues percorrer um array com `Para` e com `Para cada`, e explicar quando é preciso o índice.
- Consegues explicar porque é que mudar a variável de um `Para cada` não muda o array, e mostrá-lo com uma tabela de trace com a variável e o array lado a lado.
- Consegues usar um contador e um acumulador no mesmo ciclo e calcular uma média sem dividir por zero.
- Consegues escrever um ciclo com sentinela, com a leitura antecipada, e escolher uma sentinela que não seja um dado possível.
- Consegues escrever uma validação repetida e dizer o que se sabe sobre o valor depois do ciclo.
- Consegues usar `Parar` numa pesquisa, com uma bandeira para saber se o valor foi encontrado, e `Continuar` para saltar valores.
- Consegues dizer o valor de `tabela[1][2]` numa tabela escrita como array de arrays, e quantas vezes se executa o corpo de dois `Para` encaixados.
- Consegues testar um ciclo com zero, uma e várias voltas.

## Praticar

Para praticares o que aprendeste neste guia, faz a [ficha de exercícios](04-repeticao-e-arrays-exercicios.md) deste tema. Se o professor o indicar, faz também o [laboratório](04-repeticao-e-arrays-laboratorio.md), onde desenhas fluxogramas com ciclos no computador.

## O que vem a seguir

Os algoritmos deste guia já são grandes, e começam a repetir partes: calcular uma média, procurar um valor num array, validar uma nota. No [guia seguinte](05-funcoes-e-modelo-integrado.md), Funções e modelo integrado, vais aprender a dar nome a essas partes e a usá-las sempre que precisares, com as funções que já começaste a escrever na aula. E vais juntar tudo o que aprendeste na algoritmia num último problema, antes de passares para o Python, onde os ciclos `Enquanto` se chamam `while`, o `Para cada` se chama `for`, e as tabelas de iterações vão servir para prever o que o programa faz antes de o executares.

![Rodapé](../imagens/rodape.png)
