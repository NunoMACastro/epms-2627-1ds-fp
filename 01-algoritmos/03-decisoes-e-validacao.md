![Cabeçalho](../imagens/cabecalho.png)

# Decisões e validação

| Identificação | Valor |
| --- | --- |
| Disciplina | Fundamentos de Programação, 10.º ano, Desenvolvimento de Software |
| Unidade de competência | UC00245, Desenvolver algoritmos |
| Percurso | Algoritmos, terceiro guia |

## O que vais aprender

Até agora, os teus algoritmos executavam sempre as mesmas instruções, pela mesma ordem, fosse qual fosse a entrada. Neste guia vais aprender a escrever algoritmos que escolhem o que fazer consoante os dados, e a usar essa capacidade para verificar se uma entrada respeita o contrato antes de a usar.

No fim deves conseguir:

- escrever condições com operadores de comparação e prever se são verdadeiras ou falsas para um valor concreto;
- juntar condições com `E`, `OU` e `NÃO`, e saber qual usar em cada situação;
- escrever seleções simples, compostas e encadeadas, em pseudocódigo e em fluxograma;
- escrever um intervalo de valores como condição, incluindo ou excluindo os extremos conforme o enunciado;
- verificar que as condições de uma seleção não se sobrepõem e cobrem todos os casos;
- encontrar as fronteiras de um problema e escolher casos de teste abaixo, na fronteira e acima dela;
- validar uma entrada, separando casos válidos de inválidos, e explicar porque é que um caso de fronteira segue um ramo e não outro.

## O que já sabes e vais usar

Na aula já trabalhaste as estruturas de seleção, com se, senão se e senão, e já juntaste condições com `E` e `OU` em exercícios. Este guia retoma essas ideias com calma, escreve-as na convenção da disciplina e acrescenta o que ainda falta: intervalos, fronteiras e validação de entradas.

Do [guia anterior](02-estado-sequencia-representacoes.md) vais usar a convenção de pseudocódigo, os símbolos do fluxograma, a tabela de trace e o tipo `lógico`, que só tem dois valores, `verdadeiro` e `falso`. Do [primeiro guia](01-do-enunciado-ao-problema.md) vais usar o contrato de entrada e saída, que é o que diz que entradas são aceitáveis e é, por isso, a base de qualquer validação.

## Algoritmos que decidem

O algoritmo que converte minutos em horas faz sempre as mesmas contas. Serve para esse problema, mas a maior parte dos problemas não é assim. Uma loja cobra portes de envio só em encomendas pequenas. Uma aplicação de mapas escolhe um caminho diferente se houver trânsito. Um jogo acaba quando as vidas chegam a zero. Em todos estes casos, o que se faz depende dos dados.

No dia a dia tomas decisões destas constantemente. "Se estiver a chover, levo o guarda-chuva." "Se o semáforo estiver verde, atravesso; senão, espero." Cada uma destas frases tem duas partes: uma pergunta cuja resposta é sim ou não, e o que fazer em cada caso. Os algoritmos decidem exatamente da mesma maneira, e é essa estrutura que vais aprender a escrever.

## Condições e o tipo lógico

Uma **condição** é uma pergunta cuja resposta só pode ser `verdadeiro` ou `falso`. "A nota é maior ou igual a 10?" é uma condição. "Qual é a nota?" não é, porque a resposta é um número.

No guia anterior viste que o tipo `lógico` só tem esses dois valores. Uma condição é, portanto, uma expressão que dá um valor lógico, tal como uma conta dá um valor numérico. `7 + 3` dá `10`. `7 > 3` dá `verdadeiro`.

A diferença importante é que uma condição não depende do que achas que o valor devia ser. Depende do valor que as variáveis têm no momento em que a condição é avaliada. Se `nota` valer 9, a condição `nota >= 10` é falsa, por muito perto que 9 esteja de 10.

## Operadores de comparação

As condições mais simples comparam dois valores. Na convenção desta disciplina escrevem-se assim, e a tabela mostra o resultado de cada uma quando `nota` vale 10:

| Operador | Pergunta | Exemplo | Resultado com nota a valer 10 |
| --- | --- | --- | --- |
| `=` | é igual a? | `nota = 10` | `verdadeiro` |
| `!=` | é diferente de? | `nota != 10` | `falso` |
| `<` | é menor do que? | `nota < 10` | `falso` |
| `<=` | é menor ou igual a? | `nota <= 10` | `verdadeiro` |
| `>` | é maior do que? | `nota > 10` | `falso` |
| `>=` | é maior ou igual a? | `nota >= 10` | `verdadeiro` |

Na aula de matemática escreves "menor ou igual" com o sinal ≤, "maior ou igual" com ≥ e "diferente" com ≠. Significam o mesmo. Aqui usam-se `<=`, `>=` e `!=` porque se escrevem com as teclas que existem no teclado, e porque vais encontrar os três tal e qual nas linguagens de programação desta disciplina, o C e o Python. O `!=` lê-se "diferente de": o ponto de exclamação antes do igual quer dizer "não igual".

Olha com atenção para as linhas de `<` e de `<=`. Com a nota a valer 10, `nota < 10` é falso e `nota <= 10` é verdadeiro. A única diferença entre os dois operadores é o que acontece exatamente no valor 10. Para 9 dão os dois verdadeiro, para 11 dão os dois falso. Guarda esta observação, porque é a razão de ser da secção sobre fronteiras, mais à frente.

Lembra-te também da regra do guia anterior: a seta manda, o sinal de igual pergunta. `nota ← 10` guarda 10 em `nota`. `nota = 10` pergunta se `nota` vale 10 e não muda nada.

## Operadores lógicos: E, OU e NÃO

Muitas decisões dependem de mais do que uma pergunta. Os operadores lógicos juntam condições para formar uma condição maior.

### E

Uma condição do tipo `A E B` é verdadeira só quando `A` e `B` são as duas verdadeiras. Basta uma ser falsa para o conjunto ser falso.

| A | B | A E B |
| --- | --- | --- |
| verdadeiro | verdadeiro | verdadeiro |
| verdadeiro | falso | falso |
| falso | verdadeiro | falso |
| falso | falso | falso |

A uma tabela destas, que mostra o resultado para todas as combinações possíveis, chama-se **tabela de verdade**.

No dia a dia: para entrares na piscina municipal tens de ter a entrada paga e trazer touca. Com a entrada paga e sem touca não entras. Com touca e sem entrada também não. Só entras com as duas.

### OU

Uma condição do tipo `A OU B` é verdadeira quando pelo menos uma das duas é verdadeira. Só é falsa quando são as duas falsas.

| A | B | A OU B |
| --- | --- | --- |
| verdadeiro | verdadeiro | verdadeiro |
| verdadeiro | falso | verdadeiro |
| falso | verdadeiro | verdadeiro |
| falso | falso | falso |

Repara na primeira linha: com as duas verdadeiras, o `OU` dá verdadeiro. No português do dia a dia, "ou" às vezes quer dizer "um ou outro, mas não os dois", como em "ao almoço podes escolher sopa ou sobremesa". O `OU` dos algoritmos não é esse. Funciona como "podes pagar o lanche com dinheiro ou com cartão": se tiveres os dois, continuas a poder pagar.

### NÃO

`NÃO A` troca o valor de `A`: se `A` é verdadeiro, dá falso, e se `A` é falso, dá verdadeiro.

É útil, mas cuidado com uma armadilha. O contrário de "a nota é maior ou igual a 10" não é "a nota é menor ou igual a 10". É "a nota é menor do que 10". `NÃO (nota >= 10)` é o mesmo que `nota < 10`, porque o 10 pertence a um lado e só a um. Quando trocas o sentido de uma comparação, o valor do limite muda de lado.

### Misturar E e OU

Quando uma condição tem `E` e `OU` ao mesmo tempo, a ordem por que se avaliam muda o resultado, tal como nas contas `2 + 3 * 4` e `(2 + 3) * 4`. Nesta disciplina a regra é simples: sempre que misturares `E` com `OU`, usa parênteses para mostrar o que se avalia primeiro. Não custa nada e evita que tu, ou quem ler o algoritmo, tenha de decorar qual se avalia primeiro.

## Seleção simples

Uma **seleção** é uma instrução que escolhe o que executar consoante uma condição. A forma mais simples executa um bloco de instruções quando a condição é verdadeira e não faz nada quando é falsa:

```text
SE condição ENTÃO
    instruções que só se executam se a condição for verdadeira
FIM SE
```

Um exemplo:

```text
SE temperatura < 12 ENTÃO
    ESCREVER "Leva um casaco."
FIM SE
```

Se a temperatura for 8, a condição é verdadeira, aparece a mensagem, e o algoritmo continua na instrução a seguir ao `FIM SE`. Se for 20, a condição é falsa, a mensagem é saltada, e o algoritmo continua também na instrução a seguir ao `FIM SE`. Nos dois casos o algoritmo segue em frente. A seleção só decide se o bloco de dentro se executa ou não.

As instruções dentro do `SE` escrevem-se com mais quatro espaços de indentação. É aqui que a indentação deixa de ser decorativa: é ela que mostra, à primeira vista, que instruções dependem da condição e quais se executam sempre.

## Seleção composta

A **seleção composta** escolhe entre dois blocos: um para quando a condição é verdadeira e outro para quando é falsa.

```text
SE condição ENTÃO
    instruções para quando a condição é verdadeira
SENÃO
    instruções para quando a condição é falsa
FIM SE
```

Por exemplo:

```text
SE idade >= 18 ENTÃO
    ESCREVER "Já pode votar."
SENÃO
    ESCREVER "Ainda não pode votar."
FIM SE
```

Aqui executa-se sempre exatamente um dos dois blocos, nunca os dois e nunca nenhum. Não há um valor de idade para o qual apareçam as duas mensagens, nem um para o qual não apareça nenhuma.

No fluxograma, a seleção é o losango. Tem uma entrada e duas saídas, uma marcada `Sim`, para quando a condição é verdadeira, e outra marcada `Não`, para quando é falsa. Os dois caminhos voltam a juntar-se num ponto, e esse ponto corresponde ao `FIM SE`:

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
   [ ramo ENTÃO ]    [ ramo SENÃO ]
         |                 |
         ↓                 ↓
         +--------+--------+
                  |
                  ↓
```

Numa seleção simples, sem `SENÃO`, o caminho do `Não` vai diretamente para o ponto de junção, sem passar por nenhuma figura. A cada um destes caminhos chama-se **ramo**.

## Seleção encadeada

Às vezes há mais do que duas possibilidades. A **seleção encadeada** usa `SENÃO SE` para acrescentar condições, umas a seguir às outras:

```text
SE condição1 ENTÃO
    instruções para quando a condição1 é verdadeira
SENÃO SE condição2 ENTÃO
    instruções para quando a condição1 é falsa e a condição2 é verdadeira
SENÃO
    instruções para quando todas as condições anteriores são falsas
FIM SE
```

O funcionamento tem três regras, e as três são importantes:

1. As condições avaliam-se por ordem, de cima para baixo.
2. A primeira condição verdadeira ganha: executa-se o seu bloco e salta-se para depois do `FIM SE`. As condições que estão abaixo dela nem chegam a ser avaliadas.
3. Se nenhuma condição for verdadeira, executa-se o bloco do `SENÃO`. Se não houver `SENÃO`, não se executa nada.

Destas regras resulta uma consequência que vais usar muito: quando o algoritmo chega a avaliar a `condição2`, já sabe que a `condição1` é falsa. Se não fosse, nunca teria chegado ali. É por isso que a segunda linha do modelo acima diz "a condição1 é falsa e a condição2 é verdadeira". Vais ver no exemplo guiado como isto simplifica as condições.

Um `SENÃO SE` pertence ao mesmo `SE` que está acima dele, e por isso há um único `FIM SE` no fim de toda a cadeia. Numa cadeia destas executa-se sempre, no máximo, um bloco. Com `SENÃO` no fim, executa-se sempre exatamente um.

## Intervalos

Muitas condições perguntam se um valor está entre dois limites. A esse conjunto de valores chama-se **intervalo**.

Na matemática aprendeste a escrever intervalos com parênteses retos: [0, 20] são os números de 0 a 20, incluindo o 0 e o 20. Um extremo que pertence ao intervalo diz-se **fechado**. Um extremo que não pertence diz-se **aberto**, e na notação portuguesa escreve-se com o parêntese reto virado para fora, como em [0, 10[, que inclui o 0 e exclui o 10.

Num algoritmo, um intervalo escreve-se como duas comparações ligadas por `E`. "A nota está entre 0 e 20, incluindo os extremos" escreve-se:

```text
nota >= 0 E nota <= 20
```

Lê-se "a nota é maior ou igual a 0 e a nota é menor ou igual a 20". Porque `E`? Porque o valor tem de cumprir as duas coisas ao mesmo tempo: não pode estar abaixo do limite de baixo, e não pode estar acima do limite de cima. O 25 cumpre a primeira e falha a segunda. O -3 cumpre a segunda e falha a primeira. Só os valores de 0 a 20 cumprem as duas.

Os operadores escolhem-se pelo que o enunciado diz sobre os extremos. "Entre 0 e 20, inclusive" leva `>=` e `<=`. "Maior do que 0 e menor do que 20" leva `>` e `<`, e deixa o 0 e o 20 de fora. Quando o enunciado não diz se os extremos estão incluídos, não adivinhes: é uma ambiguidade, e trata-se como aprendeste no primeiro guia.

Há uma forma de escrever intervalos que parece natural e não é permitida nesta convenção:

```text
0 <= nota <= 20
```

A razão é que o algoritmo avalia uma comparação de cada vez. Avaliaria primeiro `0 <= nota`, que dá `verdadeiro` ou `falso`, e depois tentaria comparar esse valor lógico com 20, o que não faz sentido. Algumas linguagens nem assinalam erro: dão um resultado errado sem avisar. Por isso, nesta convenção, cada comparação compara dois valores, e as comparações juntam-se com `E` ou `OU`.

### O contrário de um intervalo

Muitas vezes o que interessa é o contrário: a nota não está entre 0 e 20. Um valor está fora do intervalo quando está abaixo do limite de baixo ou acima do limite de cima:

```text
nota < 0 OU nota > 20
```

Repara no que mudou em relação à condição de dentro. O `E` passou a `OU`, e cada comparação passou para o seu contrário, com o limite a mudar de lado: `>= 0` passou a `< 0`, e `<= 20` passou a `> 20`.

Porque `OU`? Porque, para estar fora, basta falhar um dos lados. O -3 está fora por estar abaixo de 0. O 25 está fora por estar acima de 20. E não existe nenhum número que esteja ao mesmo tempo abaixo de 0 e acima de 20. Se escrevesses `nota < 0 E nota > 20`, estarias a pedir um número que fosse as duas coisas ao mesmo tempo, e essa condição seria falsa para todos os números que existem. É um dos erros mais frequentes desta matéria, e vais vê-lo com números no fim do guia.

Também podias escrever `NÃO (nota >= 0 E nota <= 20)`. Está correto e diz o mesmo, mas é mais difícil de ler, e por isso nestes guias usa-se a forma com `OU`.

## Condições que não se sobrepõem e que cobrem todos os casos

Quando uma seleção separa os valores possíveis em grupos, há duas propriedades a verificar.

A primeira é que as condições **não se sobrepõem**: nenhum valor pode pertencer a dois grupos ao mesmo tempo. A estas condições chama-se **mutuamente exclusivas**. Se a regra fosse "negativa até 10, inclusive" e "positiva a partir de 10, inclusive", o 10 pertencia aos dois grupos, e o algoritmo não saberia o que dizer de uma nota de 10.

A segunda é que as condições **cobrem todos os casos**: todos os valores possíveis pertencem a algum grupo. Se a regra fosse "negativa abaixo de 10" e "positiva acima de 10", o 10 não pertencia a nenhum, e ficava sem resposta.

A forma mais segura de verificar as duas propriedades é desenhar uma reta com os valores possíveis e marcar nela os grupos. Cada valor da reta tem de cair num grupo, e num só. Vais fazer exatamente isso no exemplo guiado.

A seleção encadeada ajuda muito com a primeira propriedade. Como a primeira condição verdadeira ganha e as seguintes nem são avaliadas, dois blocos nunca se executam para o mesmo valor. Mas repara que isso não resolve a sobreposição, esconde-a: o valor que pertencia a dois grupos passa a ir, sem aviso, para o que estiver escrito primeiro. Se não era isso que o enunciado pedia, o algoritmo está errado e nada no ecrã te avisa. Por isso, a verificação na reta faz-se na mesma.

## Fronteiras e casos de teste

Uma **fronteira** é o sítio onde a resposta de um algoritmo muda: de um lado dá uma coisa, do outro dá outra. Numa nota com limiar de positiva em 10, há uma fronteira entre 9 e 10.

Os erros de decisão concentram-se nas fronteiras. Viste na secção dos operadores que `nota < 10` e `nota <= 10` dão o mesmo resultado para 9, para 11 e para qualquer valor longe de 10. Só discordam no 10. Se testares um algoritmo com 5 e com 15, nunca vais descobrir que escreveste o operador errado, porque para esses valores os dois operadores dão o mesmo.

Daí a regra para escolher casos de teste numa decisão: para cada fronteira, testar o valor imediatamente abaixo, o próprio valor da fronteira e o valor imediatamente acima. Com números inteiros, os vizinhos são os valores a uma unidade de distância. Para a fronteira do 10, são o 9, o 10 e o 11.

Cada caso apanha erros diferentes. O 10 apanha quem trocou `>=` por `>`, porque é o único valor em que os dois operadores discordam: o 9 dá negativa com os dois, e por isso sozinho não mostra esse erro. O 9 está nos casos para confirmar o outro lado da fronteira, porque é a nota mais alta que tem de dar negativa. O 11 apanha quem escreveu `nota = 10` em vez de `nota >= 10`, porque essa condição acerta no 10 e falha logo a seguir. O erro do `>` não aparece com 5 nem com 15. O erro do `=` aparece com o 15, que também dá negativa nessa versão, mas o 11 é a nota mais perto da fronteira que o revela.

## Casos válidos, casos inválidos e validação

Uma entrada é **válida** quando cumpre o contrato e **inválida** quando não cumpre. **Validar** uma entrada é verificar se é válida antes de a usar.

Porque é que um algoritmo há de desconfiar dos dados? Porque quem os escreve é gente, e a gente engana-se. Quem quer escrever 10 pode escrever 100, ou -10, ou 1. Sem validação, o algoritmo aceita o 100 e classifica-o, com toda a confiança, como uma nota positiva, que é uma resposta sem sentido para uma escala de 0 a 20. Um algoritmo que dá respostas erradas com ar de certas é pior do que um que avisa que não consegue responder.

No dia a dia estás rodeado de validações. Um formulário de inscrição que não aceita uma data de nascimento no futuro está a validar. Uma máquina de bilhetes que devolve uma moeda estrangeira está a validar. Em ambos os casos, a entrada é verificada antes de ser usada, e quem a escreveu fica a saber que tem de a corrigir.

O contrato é o que diz o que é válido. Por isso a validação começa sempre por reler o contrato e transformar cada limite numa condição. E a validação vem sempre antes do resto: não faz sentido calcular, classificar ou decidir com um valor que ainda não se sabe se é aceitável.

Há um limite ao que se valida nesta fase do percurso. Assume-se que o `LER` de uma variável inteira recebe sempre um número inteiro. O que fazer quando alguém escreve letras, ou um número com casas decimais, é um problema que vais tratar quando passares para a linguagem C.

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

A reta mostra quatro regiões e três fronteiras. Verifica as duas propriedades da teoria: cada inteiro cai numa região, e numa só. Não há nenhum valor sem resposta, e nenhum valor com duas.

### Passo 4: escolher os casos de teste e prever os resultados

Para cada fronteira escolhem-se os vizinhos dos dois lados. Na fronteira do limiar acrescenta-se ainda o valor acima, pela razão que viste na teoria. Os resultados esperados escrevem-se agora, antes de haver algoritmo, a partir do enunciado:

| Nota | Resultado esperado | Porque é que este caso foi escolhido |
| ---: | --- | --- |
| -1 | Nota inválida | Imediatamente abaixo da escala |
| 0 | Negativa | O extremo de baixo da escala, que é válido |
| 9 | Negativa | Imediatamente abaixo do limiar |
| 10 | Positiva | O próprio limiar, que o enunciado diz ser positiva |
| 11 | Positiva | Imediatamente acima do limiar |
| 20 | Positiva | O extremo de cima da escala, que é válido |
| 21 | Nota inválida | Imediatamente acima da escala |

Esta tabela de casos com os resultados esperados é tão importante como o algoritmo. É ela que vai dizer se o algoritmo está certo.

### Passo 5: escrever as condições

A condição de validação é o contrário do intervalo da escala. A nota é inválida se estiver abaixo de 0 ou acima de 20:

```text
nota < NOTA_MINIMA OU nota > NOTA_MAXIMA
```

A condição de positiva é a do limiar, com o 10 incluído:

```text
nota >= LIMIAR_POSITIVA
```

Repara que a condição de positiva não diz nada sobre a nota ser menor ou igual a 20. Não precisa, e a razão está nas regras da seleção encadeada. Esta condição vai ficar num `SENÃO SE` logo a seguir à validação. Quando o algoritmo chegar a ela, já sabe que a nota não é inválida, porque se fosse tinha entrado no primeiro ramo. Uma nota válida está sempre entre 0 e 20, e por isso basta perguntar se é maior ou igual a 10.

A negativa não precisa de condição nenhuma. Se a nota não é inválida e não é positiva, só pode ser negativa, e isso é exatamente o que o `SENÃO` apanha.

### Passo 6: o pseudocódigo

```text
ALGORITMO ClassificarNota
CONSTANTES
    NOTA_MINIMA ← 0
    NOTA_MAXIMA ← 20
    LIMIAR_POSITIVA ← 10
VARIÁVEIS
    nota: inteiro
INÍCIO
    ESCREVER "Nota do teste (inteiro de 0 a 20)?"
    LER nota
    SE nota < NOTA_MINIMA OU nota > NOTA_MAXIMA ENTÃO
        ESCREVER "Nota inválida"
    SENÃO SE nota >= LIMIAR_POSITIVA ENTÃO
        ESCREVER "Positiva"
    SENÃO
        ESCREVER "Negativa"
    FIM SE
FIM
```

As decisões deste pseudocódigo, uma a uma:

1. Os limites da escala e o limiar são constantes. São regras do enunciado e não dados que mudem de teste para teste. Se o professor passar a usar outro limiar, muda-se uma linha.
2. A variável `nota` é `inteiro`, porque o contrato diz que a nota é inteira.
3. A pergunta do `ESCREVER` diz a escala. Quem usa o algoritmo fica a saber o que se espera dele, e é menos provável que se engane.
4. A validação é a primeira condição da cadeia. As outras só são avaliadas para notas válidas.
5. Há um único `FIM SE`, porque o `SENÃO SE` e o `SENÃO` pertencem ao mesmo `SE`.
6. Qualquer que seja a nota, aparece exatamente uma mensagem, porque numa seleção encadeada com `SENÃO` se executa sempre exatamente um bloco.

### Passo 7: a validação vem primeiro

Imagina que a cadeia começava pela positiva:

```text
    SE nota >= LIMIAR_POSITIVA ENTÃO
        ESCREVER "Positiva"
    SENÃO SE nota < NOTA_MINIMA OU nota > NOTA_MAXIMA ENTÃO
        ESCREVER "Nota inválida"
    SENÃO
        ESCREVER "Negativa"
    FIM SE
```

Com a nota 21, a primeira condição pergunta se 21 é maior ou igual a 10. É verdadeiro. Pela segunda regra da seleção encadeada, a primeira condição verdadeira ganha: aparece "Positiva" e o algoritmo salta para depois do `FIM SE`. A validação nunca chega a ser avaliada, e uma nota que não existe foi classificada como positiva.

Repara num pormenor que torna este erro traiçoeiro: com a nota -1, esta versão errada responde bem. -1 não é maior ou igual a 10, a primeira condição é falsa, passa-se à validação, que é verdadeira, e aparece "Nota inválida". Quem testasse só -1 como caso inválido ficava convencido de que a validação funcionava. É por isso que se testam os dois lados da escala.

### Passo 8: o fluxograma, com o caminho da entrada inválida

```text
                            ( Início )
                                |
                                ↓
        / ESCREVER "Nota do teste (inteiro de 0 a 20)?" /
                                |
                                ↓
                           / LER nota /
                                |
                                ↓
         /                                              \
        <   nota < NOTA_MINIMA OU nota > NOTA_MAXIMA ?   >
         \                                              /
               |                                  |
              Sim                                Não
               |                                  |
               ↓                                  ↓
  / ESCREVER "Nota inválida" /     /                             \
               |                  <   nota >= LIMIAR_POSITIVA ?   >
               |                   \                             /
               |                     |                         |
               |                    Sim                       Não
               |                     |                         |
               |                     ↓                         ↓
               |          / ESCREVER "Positiva" /   / ESCREVER "Negativa" /
               |                     |                         |
               ↓                     ↓                         ↓
               +---------------------+------------+------------+
                                                  |
                                                  ↓
                                               ( Fim )
```

Segue com o dedo o caminho de uma entrada inválida, como 21. Depois de ler a nota, chegas ao primeiro losango. A condição é verdadeira e sais pelo `Sim`, à esquerda. Mostras "Nota inválida" e desces diretamente até à linha de junção, sem passar pelo segundo losango. É o desenho da regra "a primeira condição verdadeira ganha": o segundo losango está no caminho do `Não` e por isso só é visitado por notas válidas.

Agora segue o caminho de 10. No primeiro losango a condição é falsa e sais pelo `Não`, à direita. No segundo losango, 10 é maior ou igual a 10, sais pelo `Sim` e mostras "Positiva". Com 9 farias o mesmo caminho até ao segundo losango e sairias pelo `Não`, para "Negativa".

Compara o desenho com o pseudocódigo. O primeiro losango é o `SE`. O segundo losango, pendurado no `Não` do primeiro, é o `SENÃO SE`. A figura do `Não` do segundo losango é o `SENÃO`. A linha onde os três caminhos se juntam é o `FIM SE`. Há três caminhos possíveis do início ao fim, um por cada mensagem, e cada entrada percorre exatamente um deles.

### Passo 9: o trace dos casos de fronteira

Primeiro, o trace completo de duas entradas, linha a linha. As constantes não têm coluna, porque nunca mudam. Numa linha com uma condição, a coluna "Condição e resultado" mostra a condição com os valores substituídos e o resultado da avaliação.

Com a nota 10, o próprio limiar:

| Passo | Instrução executada | nota | Condição e resultado | Ecrã |
| ---: | --- | ---: | --- | --- |
| 0 | antes de começar | sem valor | nenhuma | nada |
| 1 | `ESCREVER "Nota do teste (inteiro de 0 a 20)?"` | sem valor | nenhuma | Nota do teste (inteiro de 0 a 20)? |
| 2 | `LER nota` | 10 | nenhuma | a pessoa escreve 10 |
| 3 | `SE nota < NOTA_MINIMA OU nota > NOTA_MAXIMA ENTÃO` | 10 | `10 < 0` é falso, `10 > 20` é falso; falso OU falso dá falso | nada |
| 4 | `SENÃO SE nota >= LIMIAR_POSITIVA ENTÃO` | 10 | `10 >= 10` é verdadeiro | nada |
| 5 | `ESCREVER "Positiva"` | 10 | nenhuma | Positiva |

No passo 3 a validação é falsa, e por isso o bloco do `ENTÃO` é saltado e passa-se ao `SENÃO SE`. No passo 4 a condição é verdadeira, e executa-se o seu bloco, no passo 5. Depois disso o algoritmo salta para depois do `FIM SE`: o `SENÃO` e o `ESCREVER "Negativa"` não aparecem na tabela porque não foram executados. A variável `nota` nunca muda depois do `LER`, porque avaliar uma condição não altera o estado.

Com a nota 21, acima da escala:

| Passo | Instrução executada | nota | Condição e resultado | Ecrã |
| ---: | --- | ---: | --- | --- |
| 0 | antes de começar | sem valor | nenhuma | nada |
| 1 | `ESCREVER "Nota do teste (inteiro de 0 a 20)?"` | sem valor | nenhuma | Nota do teste (inteiro de 0 a 20)? |
| 2 | `LER nota` | 21 | nenhuma | a pessoa escreve 21 |
| 3 | `SE nota < NOTA_MINIMA OU nota > NOTA_MAXIMA ENTÃO` | 21 | `21 < 0` é falso, `21 > 20` é verdadeiro; falso OU verdadeiro dá verdadeiro | nada |
| 4 | `ESCREVER "Nota inválida"` | 21 | nenhuma | Nota inválida |

Aqui a primeira condição é verdadeira, executa-se o seu bloco e o algoritmo salta para depois do `FIM SE`. A condição do `SENÃO SE` nunca é avaliada. Se fosse, `21 >= 10` daria verdadeiro, e é precisamente por ela não ser avaliada que a nota 21 não aparece como positiva.

Os outros cinco casos seguem o mesmo raciocínio. Na tabela seguinte, cada linha resume o trace de uma entrada: o valor de cada comparação, o ramo por onde a execução seguiu e o que apareceu no ecrã.

| nota | `nota < NOTA_MINIMA` | `nota > NOTA_MAXIMA` | Validação (OU) | `nota >= LIMIAR_POSITIVA` | Ramo executado | Ecrã |
| ---: | --- | --- | --- | --- | --- | --- |
| -1 | verdadeiro | falso | verdadeiro | não é avaliada | `ENTÃO` do `SE` | Nota inválida |
| 0 | falso | falso | falso | falso | `SENÃO` | Negativa |
| 9 | falso | falso | falso | falso | `SENÃO` | Negativa |
| 10 | falso | falso | falso | verdadeiro | `SENÃO SE` | Positiva |
| 11 | falso | falso | falso | verdadeiro | `SENÃO SE` | Positiva |
| 20 | falso | falso | falso | verdadeiro | `SENÃO SE` | Positiva |
| 21 | falso | verdadeiro | verdadeiro | não é avaliada | `ENTÃO` do `SE` | Nota inválida |

Vale a pena explicar por palavras os casos de fronteira, porque é essa explicação que mostra que percebeste a decisão, e não apenas que acertaste no resultado.

O 0 é negativa, e não inválida, porque `0 < 0` é falso: zero não é menor do que zero. Pertence à escala, a validação deixa-o passar, e depois `0 >= 10` é falso, pelo que cai no `SENÃO`. O -1 é inválido porque `-1 < 0` é verdadeiro.

O 10 é positiva, e não negativa, porque o operador é `>=` e não `>`. `10 >= 10` é verdadeiro. O 9 é negativa porque `9 >= 10` é falso.

O 20 é positiva, e não inválida, porque `20 > 20` é falso: vinte não é maior do que vinte. O 21 é inválido porque `21 > 20` é verdadeiro.

Em todas as fronteiras, a decisão é tomada por um único operador, e a diferença entre o operador com igual e o operador sem igual é exatamente o valor da fronteira.

### Passo 10: comparar com o previsto

Compara a coluna "Ecrã" da tabela anterior com a coluna "Resultado esperado" da tabela do passo 4. Coincidem nos sete casos. O algoritmo cumpre o contrato em todas as fronteiras e em todas as regiões da reta. Se algum caso não coincidisse, o trace mostraria qual foi a condição que deu um resultado diferente do que devia, e é essa condição que se corrige.

## Erros frequentes

Os erros desta secção são versões erradas do exemplo guiado. Para cada um vais ver o que acontece e, mais importante, que entrada o demonstra. Um erro só está bem explicado quando se consegue mostrar a entrada que o revela.

### Limite do limiar sem o igual

Se a condição de positiva for `nota > LIMIAR_POSITIVA`, a nota 10 aparece como negativa, quando o enunciado diz que é positiva. A entrada que demonstra o erro é o 10, e só o 10: com 9 e com 11 as duas versões dão o mesmo resultado. É o exemplo perfeito de um erro que só se encontra testando o valor da própria fronteira.

A correção é voltar ao enunciado. "Igual ou superior" inclui o igual, e por isso o operador é `>=`.

### Limite da escala com o igual no sítio errado

Se a validação for `nota < NOTA_MINIMA OU nota >= NOTA_MAXIMA`, o 20 passa a ser considerado inválido, quando é uma nota possível. A entrada que demonstra o erro é o 20. O 21 continua a dar inválido e o 19 continua a dar positiva, e por isso quem só testasse esses dois não dava por nada.

Numa condição de inválido, o limite de cima tem de ficar de fora: é inválido o que é maior do que 20, e não o que é maior ou igual a 20.

### E onde é preciso OU

Se a validação for `nota < NOTA_MINIMA E nota > NOTA_MAXIMA`, a condição pede uma nota que seja ao mesmo tempo menor do que 0 e maior do que 20. Nenhum número é as duas coisas, e por isso a condição é falsa para todas as notas. A validação nunca apanha nada.

As entradas que demonstram o erro são qualquer valor fora da escala. Com -1, a validação é falsa, a condição de positiva também, e o algoritmo escreve "Negativa". Com 21, a validação é falsa, `21 >= 10` é verdadeiro, e o algoritmo escreve "Positiva". Todos os casos válidos continuam a dar o resultado certo, e é por isso que este erro passa despercebido a quem só testa notas normais.

### OU onde é preciso E

O erro simétrico aparece em quem prefere perguntar se a nota é válida, para depois classificar só as notas válidas, e escreve essa condição com `OU`: `nota >= NOTA_MINIMA OU nota <= NOTA_MAXIMA`. Qualquer número é maior ou igual a 0 ou menor ou igual a 20, porque os números que falham a primeira parte, os negativos, cumprem a segunda. Esta condição é verdadeira para todos os números, e por isso não separa nada: todas as notas passam por válidas. As entradas que o demonstram são as mesmas do erro anterior, o -1 e o 21, que são aceites e classificadas.

Um intervalo, "entre isto e aquilo", escreve-se com `E`. O seu contrário, "fora disto", escreve-se com `OU`. Trocar um pelo outro, num sentido ou no outro, dá sempre uma condição que não separa nada.

### Igual em vez de maior ou igual

Se a condição de positiva for `nota = LIMIAR_POSITIVA`, só o 10 aparece como positiva. O 11, o 20 e todas as outras notas acima do limiar aparecem como negativas. A entrada que demonstra o erro é o 11. O 10, sozinho, não o mostra, porque essa versão acerta precisamente no 10. É esta a razão de o 11 estar nos casos de teste.

### Ordem da cadeia trocada

Já o viste no passo 7. Se a positiva vier antes da validação, o 21 aparece como positiva. A entrada que demonstra o erro é o 21, e não o -1, que continua a dar o resultado certo. Numa cadeia de `SENÃO SE`, a validação vem primeiro.

### Dois SE separados em vez de uma cadeia

Imagina a validação escrita num `SE` sozinho, com o seu `FIM SE`, e a classificação escrita noutro `SE` a seguir. Os dois `SE` são independentes, e o segundo é avaliado sempre, mesmo quando o primeiro já apanhou uma nota inválida. Com 21, aparecem duas mensagens: "Nota inválida" e, logo a seguir, "Positiva". Com -1, aparece "Nota inválida" e depois "Negativa". O contrato diz que aparece exatamente uma mensagem, e esta versão falha-o com qualquer entrada inválida.

Quando os casos são alternativas uns dos outros, e só um deve acontecer, escrevem-se numa única cadeia com `SENÃO SE`.

### Comparações encadeadas

Escrever `0 <= nota <= 20` parece-se com a matemática e não funciona nesta convenção, pela razão que viste na secção dos intervalos. Escreve sempre duas comparações separadas, ligadas por `E` ou por `OU`.

### Testar só valores do meio

Quase todos os erros desta secção têm uma coisa em comum: não aparecem se testares só com notas do meio das regiões, como 5 e 15. A exceção é o igual em vez de maior ou igual, que o 15 também revela, porque essa versão falha todas as positivas menos o 10. Um algoritmo testado apenas no meio das regiões parece quase sempre certo. Os casos de teste de uma decisão escolhem-se nas fronteiras, e é aí que se encontram os erros.

## Verificar o que aprendeste

Usa esta lista para te testares. Para cada ponto, experimenta fazê-lo sem olhar para o guia. Se não conseguires, volta à secção correspondente.

- Consegues dizer se uma comparação é verdadeira ou falsa para um valor concreto, incluindo os casos em que o valor é igual ao limite.
- Consegues preencher de memória as tabelas de verdade do `E` e do `OU`, e explicar a diferença entre o `OU` dos algoritmos e o "ou" de "sopa ou sobremesa".
- Consegues escrever o contrário de uma comparação, pondo o limite do lado certo.
- Consegues escrever em pseudocódigo uma seleção simples, uma composta e uma encadeada, e desenhar o fluxograma de cada uma.
- Consegues explicar, com um exemplo, o que acontece numa seleção encadeada quando duas condições são verdadeiras para o mesmo valor.
- Consegues transformar um intervalo dado por palavras, com os extremos incluídos ou excluídos, numa condição com `E`, e o seu contrário numa condição com `OU`.
- Consegues desenhar a reta de um problema, marcar as regiões e as fronteiras, e confirmar que as condições não se sobrepõem e cobrem todos os casos.
- Consegues escolher os casos de teste de uma decisão, abaixo, na fronteira e acima, e escrever o resultado esperado de cada um antes de fazeres o trace.
- Consegues explicar porque é que a nota 0 é negativa e não inválida, porque é que a nota 10 é positiva e não negativa, e porque é que a nota 20 é positiva e não inválida.
- Perante uma versão errada de um algoritmo de decisão, consegues encontrar a entrada que mostra o erro e explicar qual foi a condição responsável.
- Perante um enunciado com uma tabela de valores, consegues usar só as regras que o enunciado dá, sem acrescentar regras que conheces de fora.

## O que vem a seguir

No algoritmo deste guia, uma nota inválida termina o algoritmo com uma mensagem. Se a pessoa se enganou, tem de começar tudo outra vez. Seria mais útil o algoritmo voltar a pedir a nota até receber uma válida, mas para isso tem de repetir instruções, e até agora cada instrução executava-se no máximo uma vez. No próximo guia do percurso vais aprender a escrever repetições, a contar e a somar valores ao longo delas, e a garantir que uma repetição acaba.

![Rodapé](../imagens/rodape.png)
