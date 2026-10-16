![Cabeçalho](../imagens/cabecalho.png)

# Ficha de exercícios: Decisões e validação

Ficha do tema Decisões e validação, do módulo Desenvolver algoritmos. Treinas o que aprendeste no guia, uma ideia em cada exercício. Avalias comparações, juntas condições, prevês o ramo de uma seleção e escreves intervalos. Escolhes também casos de teste nas fronteiras, validas uma entrada e encontras a entrada que mostra um erro. Fazes sozinho, ao teu ritmo: o que não acabares na aula, acabas em casa ou na aula seguinte.

## O que precisas de saber

O [guia do tema](03-decisoes-e-validacao.md). Antes de começar, deves conseguir explicar:

- a diferença entre `<` e `<=`;
- as tabelas de verdade do `e` e do `ou`;
- a regra da seleção encadeada: a primeira condição verdadeira ganha.

Se alguma destas ideias não estiver clara, volta à secção do guia que a explica. São as secções "Operadores de comparação", "Operadores lógicos: `e`, `ou` e `não`" e "Seleção encadeada". Para o desafio opcional precisas também do `resto`, do [guia 02](02-estado-sequencia-representacoes.md), secção "Operadores aritméticos".

O [laboratório](03-decisoes-e-validacao-laboratorio.md) deste tema é de fluxogramas, e é opcional. Os desenhos de fluxogramas não fazem parte desta ficha. Se o professor indicar o laboratório, é lá que os desenhas.

## Como trabalhar

Resolve os exercícios pela ordem. Cada um treina uma ideia do guia:

| Exercício | O que treina |
| --- | --- |
| 1 | Avaliar comparações, também no próprio limite |
| 2 | Juntar condições com `e`, `ou` e `não` |
| 3 | Prever o ramo de uma seleção encadeada |
| 4 | Escrever um intervalo e o seu contrário |
| 5 | Validar uma entrada e aplicar uma tabela de preços, da reta ao algoritmo |
| 6 | Encontrar a entrada que mostra um erro |
| Desafio opcional | Uma condição que mistura `e` e `ou` |

Os exercícios 1 a 6 são obrigatórios. Depois do desafio, a secção "Para ires mais longe" tem mais um exercício, também opcional. É para quem terminar e quiser mais prática, ou para estudares em casa. Nem o desafio nem essa secção contam para concluíres a ficha.

Escreve os algoritmos na forma que usamos nas aulas, com a indentação a mostrar o que está dentro de cada caso. Se souberes a lógica e não te lembrares da forma, escreve frases claras, que também valem. Têm de dizer o que acontece em cada caso, incluindo quando um valor não serve.

Entregas as respostas em papel ou num ficheiro de texto, com as tabelas de casos.

## Exercício 1: Verdadeiro ou falso

A variável `idade` vale 16. Para cada condição, diz se dá `true` ou `false`:

a) `idade >= 16`

b) `idade > 16`

c) `idade == 18`

d) `idade != 16`

e) `idade < 18`

f) `idade <= 15`

Há duas condições que só diferem no igual e deram resultados diferentes. Quais são? Explica numa frase.

## Exercício 2: Juntar condições

Num parque de diversões, a montanha-russa tem duas regras: só entra quem tiver pelo menos 12 anos e pelo menos 1,40 metros de altura.

a) A variável `idade` vale 15 e a variável `altura` vale `1.45`. Diz se cada condição dá `true` ou `false`:

- `idade >= 12 e altura >= 1.40`
- `idade >= 18 e altura >= 1.40`
- `idade >= 18 ou altura >= 1.40`
- `não (idade >= 18)`

b) Qual das quatro é a regra da montanha-russa? Explica a escolha com uma pessoa a quem as outras dariam um resultado errado.

## Exercício 3: Prever o ramo

Lê este algoritmo de um cinema, sem o executar:

```text
Escreve: "Idade?"
int idade = ler valor
Se idade < 12
    Escreve: "Bilhete de criança"
Senão se idade < 65
    Escreve: "Bilhete normal"
Senão
    Escreve: "Bilhete sénior"
```

a) Diz que mensagem aparece para cada uma destas idades: 5, 11, 12, 40, 64 e 65.

b) A condição do `Senão se` é só `idade < 65`. Porque é que não precisa de dizer também `idade >= 12`?

## Exercício 4: A estufa

Numa estufa de tomates, a temperatura está boa a partir de 18 graus, incluindo os 18, e abaixo de 26 graus. Com 26 graus já está demasiado quente, e é preciso abrir as janelas. As temperaturas são números inteiros.

a) Escreve a condição que diz se a temperatura está boa.

b) Escreve a condição que diz se a temperatura está fora do bom, sem usar `não`.

c) Para as temperaturas 17, 18, 25, 26 e 27, diz se a temperatura está boa ou fora. Confirma que as tuas duas condições dão sempre respostas contrárias.

## Exercício 5: O preço das fotocópias

Lê o enunciado:

> A papelaria da escola cobra as fotocópias por esta tabela. De 1 a 10 cópias, cada cópia custa 0,10 euros. De 11 a 50 cópias, cada cópia custa 0,08 euros. Com mais de 50 cópias, cada cópia custa 0,05 euros. O preço de cada cópia aplica-se a todas as cópias do pedido: 20 cópias custam 20 vezes 0,08 euros. Um pedido com 0 cópias, ou com um número negativo, é inválido, e o algoritmo escreve "Pedido inválido" em vez de um preço.

Usa só as regras da tabela. Não acrescentes descontos, arredondamentos nem outras regras que conheças de lojas verdadeiras.

a) A reta dos números de cópias já tem duas regiões marcadas: a dos pedidos inválidos e a das cópias a 0,10 euros. Copia-a e completa-a, como no passo 3 do exemplo guiado do guia. Marca as regiões que faltam e a fronteira que falta.

```text
   inválido  |      0,10 cada      |
  ...  -1  0 |  1  2  ...  9  10   |  11  12  ...
             ↑                     ↑
        entre 0 e 1          entre 10 e 11
```

b) Completa a tabela de casos de teste, com o resultado esperado calculado à mão. Para cada fronteira, segue a regra do guia: testa o valor imediatamente abaixo, o próprio valor da fronteira e o valor imediatamente acima. As três linhas da fronteira entre 10 e 11 já estão feitas. Nessa fronteira, o enunciado escreve os dois números, o 10 e o 11, e escolheu-se o 10. Acrescenta as linhas das outras duas fronteiras.

| Cópias | Resultado esperado | Porque é que este caso foi escolhido |
| ---: | --- | --- |
| 9 | 9 × 0,10 = 0,90 euros | Imediatamente abaixo da fronteira entre 10 e 11 |
| 10 | 10 × 0,10 = 1,00 euros | O valor da fronteira, o último que custa 0,10 euros cada |
| 11 | 11 × 0,08 = 0,88 euros | Imediatamente acima da fronteira |
| | | |
| | | |
| | | |
| | | |
| | | |
| | | |

c) Escreve o algoritmo em pseudocódigo, ou em frases claras. O princípio já está feito: as constantes dos preços e dos limites, a leitura e a validação. Continua a cadeia a partir daí, com um ramo para cada preço.

```text
const PRECO_ATE_10 = 0.10
const PRECO_ATE_50 = 0.08
const PRECO_ACIMA_50 = 0.05
const MINIMO_COPIAS = 1
const LIMITE_1 = 10
const LIMITE_2 = 50
Escreve: "Quantas cópias?"
int copias = ler valor
Se copias < MINIMO_COPIAS
    Escreve: "Pedido inválido"
```

Cada ramo pode guardar o preço numa variável. Uma variável pode nascer dentro de um ramo. Nesse caso, a linha onde ela nasce, com o tipo à frente, escreve-se em cada ramo que a usa. Como só um ramo se executa, a variável nasce uma vez em cada execução.

Se quiseres confirmar o teu algoritmo com um trace, o Mais longe 1, no fim da ficha, pede-o. É opcional.

## Exercício 6: Encontrar o erro

Cada um destes bocados de algoritmo tem um erro. Para cada um, escreve a entrada que mostra o erro, o que devia aparecer, tirado do enunciado, e o que aparece. Depois corrige o bocado, mudando o mínimo possível.

a) Os dias da semana numeram-se de 1, a segunda-feira, a 7, o domingo. Este bocado devia escrever "Dia inválido" para um número que não seja de nenhum dia. Devia escrever "Fim de semana" ao sábado e ao domingo, e "Dia de aulas" nos outros dias:

```text
Se dia < 1 ou dia > 7
    Escreve: "Dia inválido"
Senão se dia > 5
    Escreve: "Fim de semana"
Senão se dia < 5
    Escreve: "Dia de aulas"
```

b) A papelaria dá desconto conforme o número de cadernos. Quem compra menos de 3 não tem desconto, quem compra de 3 a 9 tem 10% e quem compra 10 ou mais tem 20%:

```text
Se quantidade >= 3
    Escreve: "Desconto de 10%"
Senão se quantidade >= 10
    Escreve: "Desconto de 20%"
Senão
    Escreve: "Sem desconto"
```

## Apoio

Se estiveres encravado, usa estas pistas pela ordem em que aparecem, e passa à seguinte só se a anterior não tiver chegado.

- Exercício 1. Substitui `idade` por 16 e lê cada condição em voz alta: "dezasseis é maior ou igual a dezasseis?". Nas que têm igual, pergunta-te se o 16 está incluído.
- Exercício 2. Avalia primeiro cada comparação sozinha, e só depois junta com a tabela de verdade do `e` ou do `ou`.
- Exercício 3. Para cada idade, começa na primeira condição e desce. Para assim que uma condição for verdadeira: as de baixo já não contam.
- Exercício 4. O intervalo é "entre isto e aquilo", com `e`. O contrário é "abaixo disto ou acima daquilo", com `ou`, e cada limite muda de lado. Para cada extremo, pergunta-te se ele pertence ao bom ou ao fora.
- Exercício 5. Para encontrares a fronteira que falta, pergunta-te qual é o último número de cópias de cada região e o primeiro da região seguinte. Na alínea c), repara que, depois de cada `Senão se`, já sabes que as condições de cima foram falsas.
- Exercício 6. Em cada alínea, escreve primeiro o que o enunciado manda aparecer para alguns valores. Escolhe um valor de cada lado de cada fronteira e um de cada mensagem. Só depois segue o bocado de algoritmo com esses valores, condição a condição, e compara.

## Desafio opcional

Um ano é bissexto quando tem 29 de fevereiro. Isso acontece quando o ano é divisível por 4 e não é divisível por 100, ou quando é divisível por 400. Um número é divisível por outro quando o resto da divisão é 0. O resto escreve-se com `resto`, como aprendeste no guia anterior.

a) Escreve a condição que diz se um ano é bissexto. Como mistura `e` com `ou`, usa parênteses para mostrar o que se avalia primeiro.

b) Testa-a com os anos 2024, 2023, 1900 e 2000, e diz quais são bissextos.

c) Qual destes quatro anos mostra que a regra dos 100 é precisa? E qual mostra que a regra dos 400 é precisa?

## Para ires mais longe

Esta secção é opcional e fica fora da parte obrigatória. Não precisas de fazer nada daqui para concluíres a ficha, e os critérios de conclusão não a contam.

### Mais longe 1: O trace das fotocópias nas fronteiras

Continua o exercício 5: usa o teu algoritmo da alínea c) e a tua tabela de casos de teste da alínea b). A matéria está no passo 9 do exemplo guiado do guia, o trace dos casos de fronteira.

Faz o trace de dois casos de fronteira. O primeiro é o 11, e as três primeiras linhas já estão feitas. Continua-o com as linhas do teu algoritmo. Se a tua variável do preço tiver outro nome, usa-o na coluna `preco`. O segundo caso escolhes tu, da tua tabela.

| Passo | Instrução executada | copias | preco | Condição e resultado | Ecrã |
| ---: | --- | ---: | ---: | --- | --- |
| 0 | antes de começar | sem valor | sem valor | nenhuma | nada |
| 1 | `Escreve: "Quantas cópias?"` | sem valor | sem valor | nenhuma | Quantas cópias? |
| 2 | `int copias = ler valor` | 11 | sem valor | nenhuma | a pessoa escreve 11 |
| 3 | `Se copias < MINIMO_COPIAS` | 11 | sem valor | `11 < 1` dá `false` | nada |

Confirma que os dois casos dão, no trace, o resultado que previste na tabela antes de escreveres o algoritmo.

## Critérios de conclusão

- [ ] No exercício 1, tenho os seis resultados e a explicação do igual. Avaliei cada comparação com o valor que a variável tinha, também quando o valor era igual ao limite.
- [ ] No exercício 2, tenho os quatro resultados e a explicação da alínea b).
- [ ] No exercício 3, tenho as seis mensagens, parando na primeira condição verdadeira, e a explicação da alínea b) usa a regra da seleção encadeada.
- [ ] No exercício 4, usei `e` para "entre" e `ou` para "fora". As duas condições dão respostas contrárias nos cinco casos, e cada extremo fica do lado que o enunciado diz.
- [ ] No exercício 5, completei a reta e a tabela, com os três casos de cada fronteira. Calculei o resultado à mão antes de escrever o algoritmo. O algoritmo continua a validação que estava feita e calcula o preço de cada escalão com as constantes.
- [ ] No exercício 6, para cada alínea, mostrei uma entrada concreta que revela o erro, com o que devia aparecer e o que aparece. Corrigi o bocado.
- [ ] Usei só as regras que os enunciados deram.

## Autoavaliação

1. O que já consegues fazer sozinho?
2. Que dificuldade tiveste, e o que fizeste para a resolver?

![Rodapé](../imagens/rodape.png)
