![Cabeçalho](../imagens/cabecalho.png)

# Decisões e validação

Módulo Desenvolver algoritmos. Neste guia aprendes a escrever algoritmos que escolhem o que fazer consoante os dados. Aprendes também a usar essas escolhas para verificar se uma entrada respeita o contrato, antes de a usar. Lê-se ao teu ritmo, de preferência em mais do que uma vez. Para praticar, há o [laboratório](03-decisoes-e-validacao-laboratorio.md) e a [ficha de exercícios](03-decisoes-e-validacao-exercicios.md) deste tema.

Até agora, os teus algoritmos executavam sempre as mesmas instruções, pela mesma ordem, fosse qual fosse a entrada. Na aula já trabalhaste as estruturas de seleção, com se, senão se e senão, e já juntaste condições com `e` e `ou` em exercícios. Este guia retoma essas ideias com calma e escreve-as na forma que usamos nas aulas. Depois acrescenta o que ainda falta: os intervalos, as fronteiras e a validação de entradas. Este tema ainda não repete instruções. Um algoritmo que recebe um valor inválido avisa e termina.

## Neste guia

1. O que vais aprender
2. O que já sabes e vais usar
3. Algoritmos que decidem
4. Condições e o tipo `bool`
5. Operadores de comparação
6. Operadores lógicos: `e`, `ou` e `não`
7. Seleção simples
8. Seleção composta
9. Seleção encadeada
10. Intervalos
11. Condições que não se sobrepõem e que cobrem todos os casos
12. Fronteiras e casos de teste
13. Casos válidos, casos inválidos e validação
14. Exemplo guiado: validar e classificar uma nota
15. Erros frequentes
16. Palavras novas deste guia
17. Verificar o que aprendeste
18. O que vem a seguir

## O que vais aprender

No fim deste guia, consegues:

- escrever condições com comparações e com `e`, `ou` e `não`, saber qual usar em cada situação e prever se dão `true` ou `false`;
- escrever seleções simples, compostas e encadeadas em pseudocódigo, com a indentação a mostrar o que está dentro de cada caso, e ler o seu fluxograma;
- escrever um intervalo de valores como condição, incluindo ou excluindo os extremos conforme o enunciado;
- verificar que as condições de uma seleção não se sobrepõem e cobrem todos os casos;
- encontrar as fronteiras de um problema e escolher casos de teste abaixo, na fronteira e acima dela;
- validar uma entrada, separando casos válidos de inválidos, e explicar porque é que um caso de fronteira segue um ramo e não outro.

## O que já sabes e vais usar

- O contrato de entrada e saída, a base de qualquer validação: guia [01 Do enunciado ao problema delimitado](01-do-enunciado-ao-problema.md), secção "O contrato de entrada e saída".
- O caso que fica no limite de uma regra e o caso extremo: guia [01](01-do-enunciado-ao-problema.md), na mesma secção.
- O que fazer quando o enunciado não diz uma coisa, ou a diz de duas maneiras: guia [01](01-do-enunciado-ao-problema.md), secção "Dados relevantes e pormenores do contexto".
- O algoritmo que converte minutos em horas e minutos: guia [02 Estado, sequência e representações](02-estado-sequencia-representacoes.md), no exemplo guiado.
- A forma do pseudocódigo das aulas: guia [02](02-estado-sequencia-representacoes.md), secção "A forma de escrever pseudocódigo nas aulas".
- As frases claras, que também valem se disserem quanto, quando e o que acontece se não der: guia [02](02-estado-sequencia-representacoes.md), na mesma secção.
- A indentação, o recuo de quatro espaços por nível que mostra o que está dentro de quê: guia [02](02-estado-sequencia-representacoes.md), na mesma secção.
- As constantes, como `const LIMITE = 50`: guia [02](02-estado-sequencia-representacoes.md), secção "Constantes".
- O tipo `bool`, que só tem dois valores, `true` e `false`: guia [02](02-estado-sequencia-representacoes.md), secção "Tipos de dados".
- `=`, que dá um valor, e `==`, que pergunta se é igual: guia [02](02-estado-sequencia-representacoes.md), secção "Atribuição: dar um valor não é perguntar se é igual".
- `ler valor` e `Escreve:`: guia [02](02-estado-sequencia-representacoes.md), secção "Entrada e saída: `ler valor` e `Escreve:`".
- A ordem das operações numa conta, como em `2 + 3 * 4`: guia [02](02-estado-sequencia-representacoes.md), secção "Operadores aritméticos".
- Os símbolos do fluxograma, incluindo o losango: guia [02](02-estado-sequencia-representacoes.md), secção "Fluxogramas".
- A tabela de trace: guia [02](02-estado-sequencia-representacoes.md), secção "Tabela de trace".
- Os casos de teste, as entradas com o resultado previsto à mão: guia [02](02-estado-sequencia-representacoes.md), no passo 7 do exemplo guiado.
- Os sinais de comparação da matemática, como =, < e ≤, do ensino básico.

## Algoritmos que decidem

O algoritmo que converte minutos em horas e minutos faz sempre as mesmas contas. Serve para esse problema, mas a maior parte dos problemas não é assim. Uma loja cobra portes de envio só em encomendas pequenas. Uma aplicação de mapas escolhe um caminho diferente se houver trânsito. Um jogo acaba quando as vidas chegam a zero. Em todos estes casos, o que se faz depende dos dados.

No dia a dia tomas decisões destas constantemente. "Se estiver a chover, levo o guarda-chuva." "Se o semáforo estiver verde, atravesso; senão, espero." Cada uma destas frases tem duas partes: uma pergunta cuja resposta é sim ou não, e o que fazer em cada caso. Os algoritmos decidem da mesma maneira, e é essa estrutura que vais aprender a escrever.

## Condições e o tipo `bool`

"A nota é maior ou igual a 10?" só tem duas respostas possíveis, sim ou não. "Qual é a nota?" tem muitas, porque a resposta é um número. A primeira pergunta é uma condição, e a segunda não.

Uma **condição** é uma pergunta cuja resposta só pode ser verdadeiro ou falso. No pseudocódigo, essas duas respostas escrevem-se `true` e `false`.

No guia anterior viste que o tipo `bool` só tem esses dois valores. Uma condição é, portanto, uma expressão que dá um valor do tipo `bool`, tal como uma conta dá um valor numérico. `7 + 3` dá `10`. `7 > 3` dá `true`.

Uma condição não depende do que achas que o valor devia ser. Depende do valor que as variáveis têm no momento em que a condição é avaliada. Se `nota` valer 9, a condição `nota >= 10` é falsa, por muito perto que 9 esteja de 10.

## Operadores de comparação

As condições mais simples comparam dois valores. A tabela mostra os seis operadores de comparação, na forma que usamos nas aulas. Antes de leres a última coluna, tenta prever o resultado de cada exemplo com a variável `nota` a valer 10.

| Operador | Pergunta | Exemplo | Resultado com nota a valer 10 |
| --- | --- | --- | --- |
| `==` | é igual a? | `nota == 10` | `true` |
| `!=` | é diferente de? | `nota != 10` | `false` |
| `<` | é menor do que? | `nota < 10` | `false` |
| `<=` | é menor ou igual a? | `nota <= 10` | `true` |
| `>` | é maior do que? | `nota > 10` | `false` |
| `>=` | é maior ou igual a? | `nota >= 10` | `true` |

Na aula de matemática escreves "igual" com um só sinal, =, "menor ou igual" com o sinal ≤, "maior ou igual" com ≥ e "diferente" com ≠. Significam o mesmo. Aqui, a pergunta "é igual a?" escreve-se com dois sinais, `==`, porque o sinal sozinho já está ocupado. Como viste no guia anterior, `=` dá um valor a uma variável. `<=`, `>=` e `!=` usam-se porque se escrevem com as teclas que existem no teclado. Vais encontrar os seis tal e qual nas linguagens de programação desta disciplina, o C e o Python. O `!=` lê-se "diferente de": o ponto de exclamação antes do igual quer dizer "não igual".

Olha com atenção para as linhas de `<` e de `<=`. Com a nota a valer 10, `nota < 10` é falso e `nota <= 10` é verdadeiro. A única diferença entre os dois operadores é o que acontece no próprio valor 10. Para 9 dão os dois verdadeiro, e para 11 dão os dois falso. Guarda esta observação, porque é a razão de ser da secção sobre fronteiras, mais à frente.

Numa comparação com contas, como `a + b > 10`, as contas fazem-se primeiro. Com `a` a valer 4 e `b` a valer 7, faz-se `4 + 7`, que dá 11, e só depois `11 > 10`, que dá `true`.

Lembra-te também da regra do guia anterior: um `=` manda, dois `==` perguntam. `nota = 10` guarda 10 em `nota`, e o valor que lá estava perde-se. `nota == 10` pergunta se `nota` vale 10 e não muda nada. Numa condição queres sempre perguntar. Por isso, numa condição que pergunta "é igual?", escreves sempre `==`. Se escrevesses um só sinal, estarias a dar uma ordem no sítio de uma pergunta.

## Operadores lógicos: `e`, `ou` e `não`

Muitas decisões dependem de mais do que uma pergunta. Os **operadores lógicos** juntam condições para formar uma condição maior, ou trocam o valor de uma condição. Escrevem-se em minúsculas, como as palavras portuguesas que são.

### O operador `e`

Para entrares na piscina municipal tens de ter a entrada paga e trazer touca. Com a entrada paga e sem touca não entras. Com touca e sem entrada também não. Só entras com as duas.

Uma condição do tipo `A e B` é verdadeira só quando `A` e `B` são as duas verdadeiras. Basta uma ser falsa para o conjunto ser falso.

| A | B | A e B |
| --- | --- | --- |
| `true` | `true` | `true` |
| `true` | `false` | `false` |
| `false` | `true` | `false` |
| `false` | `false` | `false` |

A uma tabela destas, que mostra o resultado para todas as combinações possíveis, chama-se **tabela de verdade**.

### O operador `ou`

Na cantina, podes pagar o lanche com dinheiro ou com cartão. Basta teres um dos dois. Se tiveres os dois, continuas a poder pagar.

Uma condição do tipo `A ou B` é verdadeira quando pelo menos uma das duas é verdadeira. Só é falsa quando são as duas falsas.

| A | B | A ou B |
| --- | --- | --- |
| `true` | `true` | `true` |
| `true` | `false` | `true` |
| `false` | `true` | `true` |
| `false` | `false` | `false` |

Repara na primeira linha: com as duas verdadeiras, o `ou` dá verdadeiro. No português do dia a dia, "ou" às vezes quer dizer "um ou outro, mas não os dois". É o caso de "ao almoço podes escolher sopa ou sobremesa". O `ou` dos algoritmos não é esse. Funciona como o pagamento do lanche, com dinheiro ou com cartão.

### O operador `não`

`não A` troca o valor de `A`. Se `A` é verdadeiro, dá falso, e se `A` é falso, dá verdadeiro.

É útil, mas tem uma armadilha. Antes de continuares, tenta escrever o contrário de "a nota é maior ou igual a 10".

O contrário não é "a nota é menor ou igual a 10". É "a nota é menor do que 10". `não (nota >= 10)` é o mesmo que `nota < 10`, porque o 10 pertence a um lado e só a um. Quando trocas o sentido de uma comparação, o valor do limite muda de lado.

### Misturar `e` e `ou`

Quando uma condição tem `e` e `ou` ao mesmo tempo, a ordem por que se avaliam muda o resultado. É como nas contas `2 + 3 * 4` e `(2 + 3) * 4`, que dão 14 e 20.

Imagina que a piscina passou a deixar entrar as crianças com menos de 6 anos, mesmo sem entrada paga e sem touca. A regra fica assim: entra quem paga e traz touca, ou quem tem menos de 6 anos. Uma criança de 4 anos chega sem entrada paga e sem touca, e por isso `paga` vale `false`, `touca` vale `false` e `idade` vale 4. Antes de leres a tabela, tenta prever o que dá cada uma destas duas condições, que só diferem nos parênteses:

| Condição | Primeiro | Depois | Resultado |
| --- | --- | --- | --- |
| `(paga e touca) ou idade < 6` | `false` e `false` dá `false` | `false` ou `true` dá `true` | `true` |
| `paga e (touca ou idade < 6)` | `false` ou `true` dá `true` | `false` e `true` dá `false` | `false` |

A primeira deixa a criança entrar, como a regra quer. A segunda não a deixa, porque obriga toda a gente a pagar. Nas aulas fazemos assim: sempre que misturares `e` com `ou`, usa parênteses para mostrar o que se avalia primeiro. Não custa nada, e evita que tu, ou quem ler o algoritmo, tenha de decorar qual se avalia primeiro.

## Seleção simples

Imagina uma aplicação de meteorologia que, de manhã, te avisa quando está frio. Se a temperatura estiver abaixo de 12 graus, mostra um aviso para levares um casaco. A temperatura já está guardada na variável `temperatura`, porque foi lida mais acima, numa parte do algoritmo que aqui não se mostra.

Antes de leres o resultado, tenta prever: o que aparece no ecrã com a temperatura a valer 8? E a valer 20?

```text
Se temperatura < 12
    Escreve: "Leva um casaco."
```

O resultado, para as duas temperaturas:

| temperatura | `temperatura < 12` | Ecrã |
| ---: | --- | --- |
| 8 | `8 < 12` dá `true` | Leva um casaco. |
| 20 | `20 < 12` dá `false` | nada |

Se a temperatura for 8, a condição é verdadeira, aparece a mensagem, e o algoritmo continua na primeira linha a seguir ao bloco. Se for 20, a condição é falsa, o bloco é saltado, e o algoritmo continua também na primeira linha a seguir ao bloco. Nos dois casos o algoritmo segue em frente. A seleção só decide se o bloco de dentro se executa ou não.

Leitura guiada: começa pela linha do `Se` e lê a condição, com o valor da temperatura no lugar do nome. Depois olha para a margem da linha de baixo. Está quatro espaços mais para dentro do que o `Se`, e por isso só se executa quando a condição dá `true`.

Uma instrução destas chama-se **seleção**. É uma instrução que escolhe o que executar consoante uma condição. A forma mais simples, a **seleção simples**, executa um bloco de instruções quando a condição é verdadeira e não faz nada quando é falsa:

```text
Se condição
    instruções que só se executam se a condição for verdadeira
```

A linha do `Se` leva a condição. Por baixo dela, quatro espaços mais para dentro, estão as instruções que dependem dessa condição. A esse conjunto de linhas indentadas chama-se o **bloco** do `Se`.

### A indentação mostra o que está dentro

Repara que nenhuma palavra diz onde acaba o bloco do `Se`. Quem o diz é a indentação. As linhas escritas quatro espaços mais para dentro do que o `Se` pertencem-lhe, e só se executam se a condição for verdadeira. A primeira linha que volta à margem do `Se` já está fora do bloco. Executa-se sempre, seja qual for a condição. Há uma exceção, que vais ver nas secções seguintes. O `Senão` e o `Senão se` voltam à margem do `Se`, mas continuam a fazer parte da mesma decisão.

No guia anterior a indentação não aparecia, porque numa sequência nenhuma instrução está dentro de outra. Aqui passa a ser indispensável, e um exemplo mostra porquê. Compara estas duas versões, que só diferem na margem da última linha. A primeira:

```text
Se temperatura < 12
    Escreve: "Leva um casaco."
Escreve: "Bom dia."
```

A segunda:

```text
Se temperatura < 12
    Escreve: "Leva um casaco."
    Escreve: "Bom dia."
```

Antes de leres a tabela, tenta prever o que aparece em cada versão com 8 graus e com 20 graus.

| temperatura | Primeira versão | Segunda versão |
| ---: | --- | --- |
| 8 | Leva um casaco. Bom dia. | Leva um casaco. Bom dia. |
| 20 | Bom dia. | nada |

Na primeira versão, `Escreve: "Bom dia."` está encostado à margem do `Se`, fora do bloco, e por isso executa-se sempre. Com 8 graus aparecem as duas mensagens, e com 20 graus aparece só "Bom dia.". Na segunda versão, a mesma linha está quatro espaços para dentro e pertence ao bloco. Com 8 graus aparecem as duas mensagens, como antes, mas com 20 graus não aparece nada. As palavras são as mesmas, e o comportamento mudou. É por isso que, a partir deste guia, a indentação se escreve com cuidado: é ela que diz o que depende de quê.

O Python, que vais aprender este ano, funciona assim: é a indentação que diz que instruções estão dentro de uma decisão. No C, os blocos marcam-se com chavetas, `{` e `}`. Mas escrevem-se também com indentação, para quem lê perceber logo o que está dentro de quê.

## Seleção composta

Numas eleições, só vota quem tem 18 anos ou mais. Um algoritmo que diga a cada pessoa se já pode votar tem duas mensagens, e escolhe sempre uma delas. A idade já está guardada na variável `idade`. Antes de leres o resultado, tenta prever o que aparece com a idade a valer 17 e a valer 18.

```text
Se idade >= 18
    Escreve: "Já pode votar."
Senão
    Escreve: "Ainda não pode votar."
```

O resultado:

| idade | `idade >= 18` | Bloco executado | Ecrã |
| ---: | --- | --- | --- |
| 17 | `17 >= 18` dá `false` | o do `Senão` | Ainda não pode votar. |
| 18 | `18 >= 18` dá `true` | o do `Se` | Já pode votar. |

Leitura guiada: lê primeiro a condição do `Se`. Depois procura, na mesma margem, o `Senão` que lhe pertence. Cada um tem a sua mensagem, quatro espaços mais para dentro. Para cada idade, avalias a condição uma vez. Se der `true`, executas o bloco do `Se` e saltas o do `Senão`. Se der `false`, saltas o do `Se` e executas o do `Senão`.

A **seleção composta** escolhe assim entre dois blocos: um para quando a condição é verdadeira e outro para quando é falsa.

```text
Se condição
    instruções para quando a condição é verdadeira
Senão
    instruções para quando a condição é falsa
```

O `Senão` escreve-se na mesma margem do `Se` a que pertence, e o seu bloco vai também quatro espaços para dentro. Numa seleção composta executa-se sempre exatamente um dos dois blocos, nunca os dois e nunca nenhum. Não há um valor de idade para o qual apareçam as duas mensagens, nem um para o qual não apareça nenhuma.

No fluxograma, a seleção é o losango. Tem uma entrada e duas saídas. Uma saída está marcada `Sim`, para quando a condição é verdadeira, e a outra está marcada `Não`, para quando é falsa. Os dois caminhos voltam a juntar-se num ponto. Esse ponto corresponde à primeira linha depois dos dois blocos, a que volta à margem do `Se`:

```text
                  |
                  ↓
         /                  \
        <     condição ?     >
         \                  /
         |                 |
        Sim               Não
         |                 |
         ↓                 ↓
  [ bloco do Se ] [ bloco do Senão ]
         |                 |
         ↓                 ↓
         +--------+--------+
                  |
                  ↓
```

A cada um destes caminhos chama-se **ramo**. Numa seleção simples, sem `Senão`, o ramo do `Não` vai diretamente para o ponto de junção, sem passar por nenhuma figura.

Tal como no guia anterior, os fluxogramas são para saberes ler: seguir os caminhos com o dedo e compará-los com o pseudocódigo. Desenhá-los numa aplicação é a parte opcional do [laboratório deste tema](03-decisoes-e-validacao-laboratorio.md), que só fazes quando o professor o indicar.

## Seleção encadeada

Às vezes há mais do que duas possibilidades. Num jogo, o ecrã mostra uma mensagem diferente conforme as vidas que te restam. Com 0 vidas, o jogo acabou. Com 1 ou 2, estás quase a perder. Com 3 ou mais, o jogo continua. As vidas estão guardadas na variável `vidas`.

Antes de leres o resultado, tenta prever o que aparece com 5 vidas, com 2 e com 0.

```text
Se vidas == 0
    Escreve: "Fim do jogo"
Senão se vidas < 3
    Escreve: "Cuidado, estás quase a perder"
Senão
    Escreve: "O jogo continua"
```

O resultado:

| vidas | `vidas == 0` | `vidas < 3` | Bloco executado | Ecrã |
| ---: | --- | --- | --- | --- |
| 5 | `5 == 0` dá `false` | `5 < 3` dá `false` | o do `Senão` | O jogo continua |
| 2 | `2 == 0` dá `false` | `2 < 3` dá `true` | o do `Senão se` | Cuidado, estás quase a perder |
| 0 | `0 == 0` dá `true` | não é avaliada | o do `Se` | Fim do jogo |

Leitura guiada: lê a cadeia de cima para baixo, uma pergunta de cada vez, e para na primeira que der `true`. Se nenhuma der `true`, desces até ao `Senão`, que não pergunta nada e apanha o que sobra. Na tabela, "não é avaliada" mostra o sítio onde se parou.

Repara no 0. A segunda condição também seria verdadeira, porque 0 é menor do que 3. Mas nunca chega a ser avaliada, e por isso quem perdeu todas as vidas vê "Fim do jogo", e não o aviso.

Uma seleção destas chama-se **seleção encadeada**. Usa `Senão se` para acrescentar condições, umas a seguir às outras.

```text
Se condição1
    instruções para quando a condição1 é verdadeira
Senão se condição2
    instruções para quando a condição1 é falsa e a condição2 é verdadeira
Senão
    instruções para quando todas as condições anteriores são falsas
```

O funcionamento tem três regras:

1. As condições avaliam-se por ordem, de cima para baixo.
2. A primeira condição verdadeira ganha. Executa-se o seu bloco e salta-se para o fim da cadeia, a primeira linha a seguir ao último bloco. As condições que estão abaixo dela nem chegam a ser avaliadas.
3. Se nenhuma condição for verdadeira, executa-se o bloco do `Senão`. Se não houver `Senão`, não se executa nada.

Destas regras resulta uma consequência que vais usar muito. Quando o algoritmo chega a avaliar a `condição2`, já sabe que a `condição1` é falsa. Se não fosse, nunca teria chegado ali. É por isso que, no modelo acima, a linha por baixo do `Senão se` diz "a condição1 é falsa e a condição2 é verdadeira". No jogo, quando se pergunta `vidas < 3`, já se sabe que as vidas não são 0. Vais ver no exemplo guiado como isto simplifica as condições.

Um `Senão se` pertence ao mesmo `Se` que está acima dele. Escreve-se na mesma margem, alinhado com ele, tal como o `Senão`. É esse alinhamento que mostra que o `Se`, os `Senão se` e o `Senão` são partes de uma só cadeia, e não decisões separadas. O fim da cadeia é a primeira linha que volta a essa margem sem ser um `Senão se` nem um `Senão`. Numa cadeia destas executa-se sempre, no máximo, um bloco. Com `Senão` no fim, executa-se sempre exatamente um.

Uma variável pode nascer dentro de um ramo. Nesse caso, a linha onde ela nasce, com o tipo à frente, escreve-se em cada ramo que a usa. Como só um ramo se executa, a variável nasce uma vez em cada execução.

## Intervalos

Muitas condições perguntam se um valor está entre dois limites, como uma nota entre 0 e 20. A esse conjunto de valores chama-se **intervalo**.

Na matemática, os intervalos escrevem-se com parênteses retos: [0, 20] são os números de 0 a 20, incluindo o 0 e o 20. Um extremo que pertence ao intervalo diz-se **fechado**. Um extremo que não pertence diz-se **aberto**. Na notação portuguesa escreve-se com o parêntese reto virado para fora, como em [0, 10[, que inclui o 0 e exclui o 10.

Num algoritmo, um intervalo escreve-se como duas comparações ligadas por `e`. "A nota está entre 0 e 20, incluindo os extremos" escreve-se assim. Antes de leres a tabela, tenta prever o que dá esta condição com a nota a valer 25, a valer -3 e a valer 12:

```text
nota >= 0 e nota <= 20
```

| nota | `nota >= 0` | `nota <= 20` | `nota >= 0 e nota <= 20` |
| ---: | --- | --- | --- |
| 25 | `true` | `false` | `false` |
| -3 | `false` | `true` | `false` |
| 12 | `true` | `true` | `true` |

Lê-se "a nota é maior ou igual a 0 e a nota é menor ou igual a 20". Porquê `e`? Porque o valor tem de cumprir as duas coisas ao mesmo tempo. Não pode estar abaixo do limite de baixo, nem acima do limite de cima. O 25 cumpre a primeira e falha a segunda. O -3 cumpre a segunda e falha a primeira. Só os valores de 0 a 20 cumprem as duas.

Os operadores escolhem-se pelo que o enunciado diz sobre os extremos. "Entre 0 e 20, inclusive" leva `>=` e `<=`. "Maior do que 0 e menor do que 20" leva `>` e `<`, e deixa o 0 e o 20 de fora. Quando o enunciado não diz se os extremos estão incluídos, não adivinhes. É uma ambiguidade, e trata-se como aprendeste no primeiro guia: pergunta-se a quem escreveu o enunciado, ou escreve-se a decisão que se tomou.

Há uma forma de escrever intervalos que parece natural e que não usamos:

```text
0 <= nota <= 20
```

No C, `0 <= nota <= 20` compara primeiro `0 <= nota`, que dá verdadeiro ou falso, e depois compara esse resultado com 20. O Python lê-a como na matemática. Para a condição se ler da mesma maneira em todo o lado, nas aulas cada comparação compara dois valores. As comparações juntam-se com `e` ou `ou`. Assim a condição só se pode ler de uma maneira. Se já escreveste uma comparação encadeada destas, parte-a em duas, ligadas por `e`.

### O contrário de um intervalo

Muitas vezes o que interessa é o contrário: a nota não está entre 0 e 20. Um valor está fora do intervalo quando está abaixo do limite de baixo ou acima do limite de cima:

```text
nota < 0 ou nota > 20
```

Repara no que mudou em relação à condição de dentro. O `e` passou a `ou`, e cada comparação passou para o seu contrário, com o limite a mudar de lado. O `>= 0` passou a `< 0`, e o `<= 20` passou a `> 20`.

Porquê `ou`? Porque, para estar fora, basta falhar um dos lados. O -3 está fora por estar abaixo de 0. O 25 está fora por estar acima de 20. E não existe nenhum número que esteja ao mesmo tempo abaixo de 0 e acima de 20. Se escrevesses `nota < 0 e nota > 20`, estarias a pedir um número que fosse as duas coisas ao mesmo tempo. Essa condição seria falsa para todos os números que existem. É um dos erros mais frequentes desta matéria, e vais vê-lo com números no fim do guia.

Também podias escrever `não (nota >= 0 e nota <= 20)`. Está correto e diz o mesmo, mas é mais difícil de ler, e por isso nestes guias usa-se a forma com `ou`.

## Condições que não se sobrepõem e que cobrem todos os casos

Quando uma seleção separa os valores possíveis em grupos, há duas propriedades a verificar.

A primeira é que as condições **não se sobrepõem**: nenhum valor pode pertencer a dois grupos ao mesmo tempo. A estas condições chama-se **mutuamente exclusivas**. Imagina que a regra era "negativa até 10, inclusive" e "positiva a partir de 10, inclusive". O 10 pertencia aos dois grupos, e o algoritmo não saberia o que dizer de uma nota de 10.

A segunda é que as condições **cobrem todos os casos**: todos os valores possíveis pertencem a algum grupo. Imagina que a regra era "negativa abaixo de 10" e "positiva acima de 10". O 10 não pertencia a nenhum, e ficava sem resposta.

A forma mais segura de verificar as duas propriedades é desenhar uma reta com os valores possíveis e marcar nela os grupos. Cada valor da reta tem de cair num grupo, e num só. Vais fazê-lo no exemplo guiado.

A seleção encadeada ajuda muito com a primeira propriedade. Como a primeira condição verdadeira ganha e as seguintes nem são avaliadas, dois blocos nunca se executam para o mesmo valor. Mas repara que isso não resolve a sobreposição, esconde-a. O valor que pertencia a dois grupos passa a ir, sem aviso, para o que estiver escrito primeiro. Se não era isso que o enunciado pedia, o algoritmo está errado, e nada no ecrã te avisa. Por isso, a verificação na reta faz-se na mesma.

## Fronteiras e casos de teste

No guia 01 viste um caso no limite de uma regra: os 24 livros que enchem duas caixas de 12, sem sobrar nenhum. Nas decisões, o sítio onde está esse limite tem um nome. Uma **fronteira** é o sítio onde a resposta de um algoritmo muda: de um lado dá uma coisa, do outro dá outra. Ao valor a partir do qual a resposta muda chama-se **limiar**. Numa nota com o limiar de positiva em 10, há uma fronteira entre 9 e 10.

Os erros de decisão concentram-se nas fronteiras. Viste na secção dos operadores que `nota < 10` e `nota <= 10` dão o mesmo resultado para 9, para 11 e para qualquer valor longe de 10. Só discordam no 10. Se testares um algoritmo com 5 e com 15, nunca vais descobrir que escreveste o operador errado. Para esses valores, os dois operadores dão o mesmo.

Daí a regra para escolher casos de teste numa decisão. Para cada fronteira, testa-se o valor imediatamente abaixo, o próprio valor da fronteira e o valor imediatamente acima. Com números inteiros, os vizinhos são os valores a uma unidade de distância. Para a fronteira do 10, são o 9, o 10 e o 11.

O valor da fronteira é o número que o enunciado escreve para esse limite, como o 10 de "igual ou superior a 10". Há enunciados que escrevem os dois números de uma fronteira, como em "criança até aos 12 anos, jovem a partir dos 13". Nesse caso escolhe-se um deles. Com o 12, os casos são 11, 12 e 13; com o 13, são 12, 13 e 14. Nos dois, os dois lados da fronteira ficam testados.

Cada caso apanha erros diferentes. O 10 apanha quem trocou `>=` por `>`, porque é o único valor em que os dois operadores discordam. O 9 dá negativa com os dois, e por isso sozinho não mostra esse erro. O 9 está nos casos para confirmar o outro lado da fronteira, porque é a nota mais alta que tem de dar negativa. O 11 apanha quem escreveu `nota == 10` em vez de `nota >= 10`, porque essa condição acerta no 10 e falha logo a seguir.

O erro do `>` não aparece com 5 nem com 15. O erro do `==` aparece também com o 15, que dá negativa nessa versão. Mas o 11 é a nota mais perto da fronteira que o revela.

## Casos válidos, casos inválidos e validação

Uma entrada é **válida** quando cumpre o contrato e **inválida** quando não cumpre. **Validar** uma entrada é verificar se é válida antes de a usar.

Porque é que um algoritmo há de desconfiar dos dados? Porque quem os escreve é gente, e a gente engana-se. Quem quer escrever 10 pode escrever 100, ou -10, ou 1. Sem validação, o algoritmo aceita o 100 e classifica-o, com toda a confiança, como uma nota positiva. É uma resposta sem sentido para uma escala de 0 a 20. Um algoritmo que dá respostas erradas com ar de certas é pior do que um que avisa que não consegue responder.

No dia a dia estás rodeado de validações. Um formulário de inscrição que não aceita uma data de nascimento no futuro está a validar. Uma máquina de bilhetes que devolve uma moeda estrangeira está a validar. Em ambos os casos, a entrada é verificada antes de ser usada, e quem a escreveu fica a saber que tem de a corrigir.

O contrato é o que diz o que é válido. Por isso, a validação começa sempre por reler o contrato e transformar cada limite numa condição. E a validação vem sempre antes do resto. Não faz sentido calcular, classificar ou decidir com um valor que ainda não se sabe se é aceitável.

Há um limite ao que se valida nesta fase do percurso. Assume-se que, numa linha como `int nota = ler valor`, a pessoa escreve sempre um número inteiro. O que fazer quando alguém escreve letras, ou um número com casas decimais, é um problema que vais tratar quando passares para o Python.

## Exemplo guiado: validar e classificar uma nota

### Passo 1: o enunciado

> Um professor quer um algoritmo que o ajude a classificar os testes. O algoritmo lê a nota de um teste, que é um número inteiro na escala de 0 a 20. Se a nota for igual ou superior a 10, escreve "Positiva". Se for inferior a 10, escreve "Negativa". Se a nota escrita não pertencer à escala, o algoritmo escreve "Nota inválida" e não a classifica.

### Passo 2: o contrato

A entrada é a nota, um número inteiro. Repara num pormenor: o algoritmo aceita qualquer inteiro que lhe escrevam, e é ele próprio que verifica se o valor pertence à escala. É isso que o enunciado pede quando diz o que fazer com uma nota fora da escala.

A saída é exatamente uma de três mensagens: "Positiva", "Negativa" ou "Nota inválida".

As restrições vêm todas do enunciado, e convém escrevê-las com os extremos bem claros. A escala vai de 0 a 20 e inclui os dois extremos, porque 0 e 20 são notas possíveis. O limiar de positiva é 10, e "igual ou superior a 10" quer dizer que o 10 já é positiva.

O limiar é um dado do enunciado, e não uma regra que o algoritmo possa ir buscar a outro lado. Sabes da tua escola que há situações em que um 9,5 se arredonda para 10. Este enunciado não fala de arredondamentos e diz que a nota é inteira, e por isso o algoritmo não arredonda nada. Usar uma regra que conheces de fora, mas que o enunciado não dá, é inventar requisitos. Se o enunciado dissesse que o limiar era 12, o limiar seria 12.

### Passo 3: desenhar a reta e marcar as regiões

Antes de escrever uma única condição, desenha-se a reta dos valores inteiros e marcam-se as regiões com a resposta que cada uma deve dar:

```text
     inválida   |         negativa         |          positiva          |   inválida
  ...  -2   -1  |   0   1   2  ...  8   9  |  10  11  12  ...  19  20   |  21  22  ...
                ↑                          ↑                            ↑
           entre -1 e 0               entre 9 e 10                entre 20 e 21
```

A reta mostra quatro regiões e três fronteiras. Verifica as duas propriedades da secção anterior: cada inteiro cai numa região, e numa só. Não há nenhum valor sem resposta, e nenhum valor com duas.

### Passo 4: escolher os casos de teste e prever os resultados

Para cada fronteira aplica-se a regra que viste: o valor imediatamente abaixo, o próprio valor da fronteira e o valor imediatamente acima. O valor de cada fronteira é o limite que o enunciado dá. São o 0 e o 20, que são os extremos da escala, e o 10, que é o limiar. Os resultados esperados escrevem-se agora, antes de haver algoritmo, a partir do enunciado:

| Nota | Resultado esperado | Porque é que este caso foi escolhido |
| ---: | --- | --- |
| -1 | Nota inválida | Imediatamente abaixo da escala |
| 0 | Negativa | O extremo de baixo da escala, que é válido |
| 1 | Negativa | Imediatamente acima do extremo de baixo da escala |
| 9 | Negativa | Imediatamente abaixo do limiar |
| 10 | Positiva | O próprio limiar, que o enunciado diz ser positiva |
| 11 | Positiva | Imediatamente acima do limiar |
| 19 | Positiva | Imediatamente abaixo do extremo de cima da escala |
| 20 | Positiva | O extremo de cima da escala, que é válido |
| 21 | Nota inválida | Imediatamente acima da escala |

Esta tabela de casos com os resultados esperados é tão importante como o algoritmo. É ela que vai dizer se o algoritmo está certo. Escreve-se antes do algoritmo de propósito: os resultados vêm do enunciado, e não do que o algoritmo faz.

### Passo 5: escrever as condições

A condição de validação é o contrário do intervalo da escala. A nota é inválida se estiver abaixo de 0 ou acima de 20:

```text
nota < NOTA_MINIMA ou nota > NOTA_MAXIMA
```

A condição de positiva é a do limiar, com o 10 incluído:

```text
nota >= LIMIAR_POSITIVA
```

Repara que a condição de positiva não diz nada sobre a nota ser menor ou igual a 20. Não precisa, e a razão está nas regras da seleção encadeada. Esta condição vai ficar num `Senão se` logo a seguir à validação. Quando o algoritmo chegar a ela, já sabe que a nota não é inválida, porque se fosse tinha entrado no primeiro ramo. Uma nota válida está sempre entre 0 e 20, e por isso basta perguntar se é maior ou igual a 10.

A negativa não precisa de condição nenhuma. Se a nota não é inválida e não é positiva, só pode ser negativa, e é isso que o `Senão` apanha.

### Passo 6: o pseudocódigo

Este é o algoritmo que valida e classifica uma nota, na forma que usamos nas aulas:

```text
const NOTA_MINIMA = 0
const NOTA_MAXIMA = 20
const LIMIAR_POSITIVA = 10
Escreve: "Nota do teste (inteiro de 0 a 20)?"
int nota = ler valor
Se nota < NOTA_MINIMA ou nota > NOTA_MAXIMA
    Escreve: "Nota inválida"
Senão se nota >= LIMIAR_POSITIVA
    Escreve: "Positiva"
Senão
    Escreve: "Negativa"
```

As decisões deste pseudocódigo, uma a uma:

1. Os limites da escala e o limiar são constantes. São regras do enunciado, e não dados que mudem de teste para teste. Escrevem-se no início, com `const`, antes da cadeia que as usa. Se o professor passar a usar outro limiar, muda-se uma linha.
2. A variável `nota` é `int`, porque o contrato diz que a nota é inteira. Nasce na linha da leitura, e por isso é essa a linha que leva o tipo.
3. A pergunta do `Escreve:` diz a escala. Quem usa o algoritmo fica a saber o que se espera dele, e é menos provável que se engane.
4. A validação é a primeira condição da cadeia. As outras só são avaliadas para notas válidas.
5. O `Senão se` e o `Senão` estão na mesma margem do `Se`. Cada `Escreve:` está quatro espaços mais para dentro, por baixo da linha de que depende. É a indentação que mostra que as três mensagens são os três blocos de uma só cadeia. Cada uma só se escreve no seu caso.
6. Qualquer que seja a nota, aparece uma só mensagem, porque numa seleção encadeada com `Senão` se executa sempre um só bloco.

O mesmo algoritmo, em frases claras, também é válido:

1. Pergunta "Nota do teste (inteiro de 0 a 20)?" e guarda o número inteiro que a pessoa escrever como nota.
2. Se a nota for menor do que 0 ou maior do que 20, escreve "Nota inválida" e não faz mais nada.
3. Se não, e se a nota for 10 ou mais, escreve "Positiva".
4. Em todos os outros casos, escreve "Negativa".

Repara como as frases respondem às três perguntas do guia anterior. Dizem quanto, com os limites escritos por extenso, incluindo se o 10 conta. Dizem quando, pela ordem das frases: a validação primeiro. E dizem o que acontece se não der: uma nota fora da escala recebe "Nota inválida" e não é classificada. A frase "se a nota for boa escreve Positiva" não chegava, porque não diz a partir de que valor uma nota é boa.

### Passo 7: a validação vem primeiro

Imagina que a cadeia começava pela positiva:

```text
Se nota >= LIMIAR_POSITIVA
    Escreve: "Positiva"
Senão se nota < NOTA_MINIMA ou nota > NOTA_MAXIMA
    Escreve: "Nota inválida"
Senão
    Escreve: "Negativa"
```

Antes de leres a explicação, tenta prever o que esta versão escreve com a nota 21, e depois com a nota -1.

Com a nota 21, a primeira condição pergunta se 21 é maior ou igual a 10. É verdadeiro. Pela segunda regra da seleção encadeada, a primeira condição verdadeira ganha: aparece "Positiva", e o algoritmo salta para o fim da cadeia. A validação nunca chega a ser avaliada, e uma nota que não existe foi classificada como positiva.

Repara num pormenor que torna este erro traiçoeiro: com a nota -1, esta versão errada responde bem. O -1 não é maior ou igual a 10, e a primeira condição é falsa. Passa-se à validação, que é verdadeira, e aparece "Nota inválida". Quem testasse só -1 como caso inválido ficava convencido de que a validação funcionava. É por isso que se testam os dois lados da escala.

### Passo 8: o fluxograma, com o caminho da entrada inválida

```text
                            ( Início )
                                |
                                ↓
        / Escreve: "Nota do teste (inteiro de 0 a 20)?" /
                                |
                                ↓
                     / int nota = ler valor /
                                |
                                ↓
         /                                              \
        <   nota < NOTA_MINIMA ou nota > NOTA_MAXIMA ?   >
         \                                              /
               |                                  |
              Sim                                Não
               |                                  |
               ↓                                  ↓
  / Escreve: "Nota inválida" /     /                             \
               |                  <   nota >= LIMIAR_POSITIVA ?   >
               |                   \                             /
               |                     |                         |
               |                    Sim                       Não
               |                     |                         |
               |                     ↓                         ↓
               |          / Escreve: "Positiva" /   / Escreve: "Negativa" /
               |                     |                         |
               ↓                     ↓                         ↓
               +---------------------+------------+------------+
                                                  |
                                                  ↓
                                               ( Fim )
```

Segue com o dedo o caminho de uma entrada inválida, como 21. Depois de ler a nota, chegas ao primeiro losango. A condição é verdadeira, e sais pelo `Sim`, à esquerda. Mostras "Nota inválida" e desces diretamente até à linha de junção, sem passar pelo segundo losango. É o desenho da regra "a primeira condição verdadeira ganha". O segundo losango está no caminho do `Não`, e por isso só é visitado por notas válidas.

Agora segue o caminho de 10. No primeiro losango a condição é falsa, e sais pelo `Não`, à direita. No segundo losango, 10 é maior ou igual a 10, sais pelo `Sim` e mostras "Positiva". Com 9 farias o mesmo caminho até ao segundo losango e sairias pelo `Não`, para "Negativa".

Compara o desenho com o pseudocódigo. O primeiro losango é o `Se`. O segundo losango, pendurado no `Não` do primeiro, é o `Senão se`. A figura do `Não` do segundo losango é o bloco do `Senão`. A linha onde os três caminhos se juntam é o fim da cadeia. É o sítio onde estaria a primeira linha que voltasse à margem do `Se`. Neste algoritmo não há mais nenhuma linha depois da cadeia, e por isso a junção leva diretamente ao fim.

Neste desenho, o `Sim` sai para a esquerda. Noutros desenhos, como os do laboratório, sai pela direita. O lado de cada saída não importa, desde que cada seta tenha o texto certo.

Tal como no guia anterior, as três linhas `const` não têm figura, porque são regras do problema e não passos do caminho. Há três caminhos possíveis do início ao fim, um por cada mensagem, e cada entrada percorre um só deles.

### Passo 9: o trace dos casos de fronteira

Primeiro, o trace completo de duas entradas, linha a linha. As constantes não têm coluna nem passo, porque nunca mudam, e o passo 1 é a primeira linha depois das três linhas `const`. Numa linha com uma condição, a coluna "Condição e resultado" mostra a condição com os valores substituídos e o resultado da avaliação.

Antes de leres a primeira tabela, faz tu o trace com a nota 10, o próprio limiar, e compara depois.

| Passo | Instrução executada | nota | Condição e resultado | Ecrã |
| ---: | --- | ---: | --- | --- |
| 0 | antes de começar | sem valor | nenhuma | nada |
| 1 | `Escreve: "Nota do teste (inteiro de 0 a 20)?"` | sem valor | nenhuma | Nota do teste (inteiro de 0 a 20)? |
| 2 | `int nota = ler valor` | 10 | nenhuma | a pessoa escreve 10 |
| 3 | `Se nota < NOTA_MINIMA ou nota > NOTA_MAXIMA` | 10 | `10 < 0` dá `false`, `10 > 20` dá `false`; `false` ou `false` dá `false` | nada |
| 4 | `Senão se nota >= LIMIAR_POSITIVA` | 10 | `10 >= 10` dá `true` | nada |
| 5 | `Escreve: "Positiva"` | 10 | nenhuma | Positiva |

No passo 3 a validação é falsa. Por isso, o bloco do `Se`, a linha indentada por baixo dele, é saltado, e passa-se ao `Senão se`. No passo 4 a condição é verdadeira, e executa-se o seu bloco, no passo 5. Depois disso o algoritmo salta para o fim da cadeia. O `Senão` e o `Escreve: "Negativa"` não aparecem na tabela, porque não foram executados. Com a nota 9, a condição do passo 4 seria falsa, e passava-se ao `Senão`. O `Senão` não pergunta nada: passa-se diretamente ao seu bloco, e por isso não tem linha própria no trace. O passo 5 seria logo `Escreve: "Negativa"`. A variável `nota` nunca muda depois da linha onde nasce, porque avaliar uma condição não altera o estado.

Com a nota 21, acima da escala:

| Passo | Instrução executada | nota | Condição e resultado | Ecrã |
| ---: | --- | ---: | --- | --- |
| 0 | antes de começar | sem valor | nenhuma | nada |
| 1 | `Escreve: "Nota do teste (inteiro de 0 a 20)?"` | sem valor | nenhuma | Nota do teste (inteiro de 0 a 20)? |
| 2 | `int nota = ler valor` | 21 | nenhuma | a pessoa escreve 21 |
| 3 | `Se nota < NOTA_MINIMA ou nota > NOTA_MAXIMA` | 21 | `21 < 0` dá `false`, `21 > 20` dá `true`; `false` ou `true` dá `true` | nada |
| 4 | `Escreve: "Nota inválida"` | 21 | nenhuma | Nota inválida |

Aqui a primeira condição é verdadeira, executa-se o seu bloco, e o algoritmo salta para o fim da cadeia. A condição do `Senão se` nunca é avaliada. Se fosse, `21 >= 10` daria verdadeiro. É precisamente por ela não ser avaliada que a nota 21 não aparece como positiva.

Os outros sete casos seguem o mesmo raciocínio. Na tabela seguinte, cada linha resume o trace de uma entrada. Mostra o valor de cada comparação, o ramo por onde a execução seguiu e o que apareceu no ecrã.

| nota | `nota < NOTA_MINIMA` | `nota > NOTA_MAXIMA` | Validação (ou) | `nota >= LIMIAR_POSITIVA` | Ramo executado | Ecrã |
| ---: | --- | --- | --- | --- | --- | --- |
| -1 | `true` | `false` | `true` | não é avaliada | bloco do `Se` | Nota inválida |
| 0 | `false` | `false` | `false` | `false` | bloco do `Senão` | Negativa |
| 1 | `false` | `false` | `false` | `false` | bloco do `Senão` | Negativa |
| 9 | `false` | `false` | `false` | `false` | bloco do `Senão` | Negativa |
| 10 | `false` | `false` | `false` | `true` | bloco do `Senão se` | Positiva |
| 11 | `false` | `false` | `false` | `true` | bloco do `Senão se` | Positiva |
| 19 | `false` | `false` | `false` | `true` | bloco do `Senão se` | Positiva |
| 20 | `false` | `false` | `false` | `true` | bloco do `Senão se` | Positiva |
| 21 | `false` | `true` | `true` | não é avaliada | bloco do `Se` | Nota inválida |

Os casos de fronteira explicam-se também por palavras. É essa explicação que mostra que percebeste a decisão, e não apenas que acertaste no resultado.

O 0 é negativa, e não inválida, porque `0 < 0` é falso: zero não é menor do que zero. Pertence à escala, a validação deixa-o passar, e depois `0 >= 10` é falso, pelo que cai no `Senão`. O -1 é inválido porque `-1 < 0` é verdadeiro. O 1, do lado de dentro da escala, é negativa pelo mesmo caminho do 0. Confirma que a validação deixa passar as notas logo acima do extremo.

O 10 é positiva, e não negativa, porque o operador é `>=` e não `>`. `10 >= 10` é verdadeiro. O 9 é negativa porque `9 >= 10` é falso.

O 20 é positiva, e não inválida, porque `20 > 20` é falso: vinte não é maior do que vinte. O 21 é inválido porque `21 > 20` é verdadeiro. O 19, do lado de dentro da escala, é positiva pelo mesmo caminho do 20. Confirma que a validação deixa passar as notas logo abaixo do extremo.

Em todas as fronteiras, a decisão é tomada por um único operador. Os dois operadores, com igual e sem igual, só dão resultados diferentes num valor: o da fronteira.

### Passo 10: comparar com o previsto

Compara a coluna "Ecrã" da tabela anterior com a coluna "Resultado esperado" da tabela do passo 4. Coincidem nos nove casos. O algoritmo cumpre o contrato em todas as fronteiras e em todas as regiões da reta. Se algum caso não coincidisse, o trace mostraria qual foi a condição que deu um resultado diferente do que devia. É essa condição que se corrige.

## Erros frequentes

Os erros desta secção são versões erradas do exemplo guiado. Para cada um vais ver o que acontece e, mais importante, que entrada o demonstra. Um erro só está bem explicado quando se consegue mostrar a entrada que o revela. O erro das comparações encadeadas, como `0 <= nota <= 20`, está explicado na secção "Intervalos".

### Limite do limiar sem o igual

O que se vê: com a condição de positiva escrita `nota > LIMIAR_POSITIVA`, a nota 10 aparece como negativa, quando o enunciado diz que é positiva. A entrada que demonstra o erro é o 10, e só o 10. Com 9 e com 11, as duas versões dão o mesmo resultado.

Porque acontece: lê-se "superior a 10" e esquece-se o "igual" de "igual ou superior". É um erro que só se encontra testando o valor da própria fronteira.

Como se corrige: volta-se ao enunciado. "Igual ou superior" inclui o igual, e por isso o operador é `>=`.

### Limite da escala com o igual no sítio errado

O que se vê: com a validação escrita `nota < NOTA_MINIMA ou nota >= NOTA_MAXIMA`, o 20 passa a ser considerado inválido, quando é uma nota possível. A entrada que demonstra o erro é o 20. O 21 continua a dar inválido e o 19 continua a dar positiva, e por isso quem só testasse esses dois não dava por nada.

Porque acontece: escreve-se o igual por hábito, sem perguntar se o próprio 20 pertence à escala.

Como se corrige: numa condição de inválido, o limite de cima tem de ficar de fora. É inválido o que é maior do que 20, e não o que é maior ou igual a 20.

### Usar `e` onde é preciso `ou`

O que se vê: com a validação escrita `nota < NOTA_MINIMA e nota > NOTA_MAXIMA`, a validação nunca apanha nada. A condição pede uma nota que seja ao mesmo tempo menor do que 0 e maior do que 20. Nenhum número é as duas coisas, e por isso a condição é falsa para todas as notas.

As entradas que demonstram o erro são qualquer valor fora da escala. Com -1, a validação é falsa, a condição de positiva também, e o algoritmo escreve "Negativa". Com 21, a validação é falsa, `21 >= 10` é verdadeiro, e o algoritmo escreve "Positiva". Todos os casos válidos continuam a dar o resultado certo. É por isso que este erro passa despercebido a quem só testa notas normais.

Porque acontece: pensa-se nas duas pontas da escala, "abaixo de 0" e "acima de 20", e junta-se com `e`, como numa enumeração em português.

Como se corrige: para estar fora, basta falhar um dos lados, e por isso o contrário de um intervalo escreve-se com `ou`.

### Usar `ou` onde é preciso `e`

O que se vê: o erro simétrico aparece em quem prefere perguntar se a nota é válida, para depois classificar só as notas válidas. Essa pessoa escreve a condição com `ou`: `nota >= NOTA_MINIMA ou nota <= NOTA_MAXIMA`. Esta condição é verdadeira para todos os números, e por isso não separa nada: todas as notas passam por válidas. As entradas que o demonstram são as mesmas do erro anterior, o -1 e o 21, que são aceites e classificadas.

Porque acontece: qualquer número é maior ou igual a 0 ou menor ou igual a 20. Os números que falham a primeira parte, os negativos, cumprem a segunda, e os que falham a segunda cumprem a primeira.

Como se corrige: um intervalo, "entre isto e aquilo", escreve-se com `e`. O seu contrário, "fora disto", escreve-se com `ou`. Trocar um pelo outro, num sentido ou no outro, dá sempre uma condição que não separa nada.

### Igual em vez de maior ou igual

O que se vê: com a condição de positiva escrita `nota == LIMIAR_POSITIVA`, só o 10 aparece como positiva. O 11, o 20 e todas as outras notas acima do limiar aparecem como negativas. A entrada que demonstra o erro é o 11. O 10, sozinho, não o mostra, porque essa versão acerta precisamente no 10. É esta a razão de o 11 estar nos casos de teste.

Porque acontece: o limiar é um número só, o 10, e escreve-se a pergunta "é igual a 10?" em vez de "é 10 ou mais?".

Como se corrige: pergunta-se pelo que o enunciado diz, "igual ou superior", com `>=`. Repara também que a pergunta "é igual?" leva dois sinais. Escrita com um só, `nota = LIMIAR_POSITIVA`, deixava de ser uma pergunta e passava a ser uma ordem, que guardaria 10 em `nota`. Numa linha de `Se` ou de `Senão se` quer-se sempre uma pergunta, e por isso o igual que lá aparece é sempre `==`.

### Ordem da cadeia trocada

O que se vê: já o viste no passo 7. Se a positiva vier antes da validação, o 21 aparece como positiva. A entrada que demonstra o erro é o 21, e não o -1, que continua a dar o resultado certo.

Porque acontece: escreve-se primeiro o caso que mais interessa, a positiva, e a validação fica para o fim.

Como se corrige: numa cadeia com `Senão se`, a validação vem primeiro.

### Dois `Se` separados em vez de uma cadeia

Imagina a validação escrita num `Se` sozinho e a classificação escrita noutro `Se` a seguir, na mesma margem:

```text
Se nota < NOTA_MINIMA ou nota > NOTA_MAXIMA
    Escreve: "Nota inválida"
Se nota >= LIMIAR_POSITIVA
    Escreve: "Positiva"
Senão
    Escreve: "Negativa"
```

O que se vê: com 21, aparecem duas mensagens, "Nota inválida" e, logo a seguir, "Positiva". Com -1, aparece "Nota inválida" e depois "Negativa". O contrato diz que aparece exatamente uma mensagem, e esta versão falha-o com qualquer entrada inválida.

Porque acontece: a diferença para o algoritmo certo está numa só palavra. Onde devia estar `Senão se` está `Se`. Um `Se` encostado à margem começa uma decisão nova, que não tem nada a ver com a de cima. Os dois `Se` são independentes, e o segundo é avaliado sempre, mesmo quando o primeiro já apanhou uma nota inválida.

Como se corrige: quando os casos são alternativas uns dos outros, e só um deve acontecer, escrevem-se numa única cadeia com `Senão se`.

### Testar só valores do meio

O que se vê: quase todos os erros desta secção desaparecem se testares só com notas do meio das regiões, como 5 e 15. A exceção é o igual em vez de maior ou igual. O 15 também o revela, porque essa versão falha todas as positivas menos o 10. Um algoritmo testado apenas no meio das regiões parece quase sempre certo.

Porque acontece: os valores do meio são os primeiros que vêm à cabeça, e são valores em que os operadores errados também acertam.

Como se corrige: os casos de teste de uma decisão escolhem-se nas fronteiras, e é aí que se encontram os erros.

## Palavras novas deste guia

- Condição: uma pergunta cuja resposta só pode ser `true` ou `false`.
- Operador de comparação: o sinal que compara dois valores, como `==`, `!=`, `<`, `<=`, `>` e `>=`; dá `true` ou `false`.
- Operador lógico: `e`, `ou` ou `não`, que juntam condições ou trocam o valor de uma condição.
- `e`: dá `true` só quando as duas condições são verdadeiras.
- `ou`: dá `true` quando pelo menos uma das condições é verdadeira, também quando são as duas.
- `não`: troca o valor de uma condição, de `true` para `false` e de `false` para `true`.
- Tabela de verdade: a tabela com o resultado de um operador lógico para todas as combinações possíveis.
- Seleção: uma instrução que escolhe o que executar consoante uma condição.
- Bloco: as linhas indentadas por baixo de um `Se`, de um `Senão se` ou de um `Senão`, que só se executam no seu caso.
- Seleção simples: um `Se` sem `Senão`, que executa o bloco quando a condição é verdadeira e não faz nada quando é falsa.
- Seleção composta: um `Se` com `Senão`, que executa sempre exatamente um de dois blocos.
- Seleção encadeada: um `Se` seguido de um ou mais `Senão se`, em que a primeira condição verdadeira ganha.
- Ramo: cada um dos caminhos que saem de uma decisão; no fluxograma, cada saída do losango.
- Intervalo: o conjunto dos valores entre dois limites.
- Extremo fechado: um extremo que pertence ao intervalo.
- Extremo aberto: um extremo que não pertence ao intervalo.
- Condições mutuamente exclusivas: condições que não se sobrepõem, porque nenhum valor pertence a dois grupos.
- Cobrir todos os casos: todos os valores possíveis pertencem a algum grupo.
- Fronteira: o sítio onde a resposta de um algoritmo muda.
- Limiar: o valor a partir do qual a resposta muda, como o 10 da positiva.
- Entrada válida: uma entrada que cumpre o contrato.
- Entrada inválida: uma entrada que não cumpre o contrato.
- Validar: verificar se uma entrada é válida antes de a usar.

## Verificar o que aprendeste

Usa estas perguntas para te testares. Responde a cada uma sem olhar para o guia. Se não conseguires, volta à secção que explica a ideia.

1. A variável `pontos` vale 50. Quanto dão `pontos > 50`, `pontos >= 50` e `pontos != 50`? Porque é que as duas primeiras dão resultados diferentes?
2. Escreve de memória as tabelas de verdade do `e` e do `ou`. Qual é a diferença entre o `ou` dos algoritmos e o "ou" de "sopa ou sobremesa"?
3. Qual é o contrário de `altura >= 150`? E o de `temperatura <= 30`? Escreve-os sem usar `não`.
4. Escreve um exemplo teu de uma seleção simples, de uma composta e de uma encadeada, com a indentação certa. Como reconheces cada uma num fluxograma?
5. Dá um exemplo teu em que passar uma linha para dentro do bloco de um `Se` muda o que aparece no ecrã. Com que valor se vê a diferença?
6. Escreve em frases claras uma decisão tua com três casos, que diga também o que acontece quando o valor não serve.
7. No jogo das vidas, 0 é menor do que 3. Porque é que, com 0 vidas, não aparece o aviso "Cuidado, estás quase a perder"?
8. Escreve como condição "a idade está entre 12 e 17, inclusive". Escreve também o seu contrário, sem usar `não`.
9. Uma loja online oferece os portes nas encomendas de 50 euros ou mais, e recusa as encomendas de 0 euros ou menos. Os valores são inteiros. Desenha a reta, marca as regiões e as fronteiras, e confirma que cada valor cai numa região, e numa só.
10. Para a loja da pergunta 9, que casos de teste escolhes? Escreve o resultado esperado de cada um antes de pensares no algoritmo.
11. No exemplo guiado, porque é que a nota 0 é negativa e não inválida? Porque é que a nota 10 é positiva e não negativa? E porque é que a nota 20 é positiva e não inválida?
12. Um colega escreveu a validação da nota como `nota < NOTA_MINIMA ou nota >= NOTA_MAXIMA`. O que aparece com 19, com 20 e com 21? Que entrada mostra o erro, e que condição é responsável?
13. O enunciado de um parque de estacionamento diz que os primeiros 30 minutos são grátis. Um colega acrescenta que ao domingo também é grátis, porque é assim no parque perto da casa dele. O que está errado no que ele fez?

## O que vem a seguir

Para praticar este tema, faz a [ficha de exercícios](03-decisoes-e-validacao-exercicios.md). Tem seis exercícios, do mais simples ao mais completo, e um desafio opcional. Se o professor o indicar, faz também o [laboratório](03-decisoes-e-validacao-laboratorio.md), onde desenhas fluxogramas com decisões no computador.

O tema seguinte é [Repetição e arrays](04-repeticao-e-arrays.md). No algoritmo deste guia, uma nota inválida termina o algoritmo com uma mensagem. Se a pessoa se enganou, tem de começar tudo outra vez. Seria mais útil o algoritmo voltar a pedir a nota até receber uma válida. Mas para isso tem de repetir instruções, e até agora cada instrução executava-se no máximo uma vez. No guia seguinte vais aprender a escrever repetições, a contar e a somar valores ao longo delas, e a garantir que uma repetição acaba.

![Rodapé](../imagens/rodape.png)
