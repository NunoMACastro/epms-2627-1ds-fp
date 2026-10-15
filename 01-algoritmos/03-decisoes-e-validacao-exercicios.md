![Cabeçalho](../imagens/cabecalho.png)

# Ficha de exercícios: Decisões e validação

Ficha do tema Decisões e validação, do módulo Desenvolver algoritmos. Treinas o que aprendeste no guia, uma ideia em cada exercício. Avalias comparações, juntas condições, prevês o ramo de uma seleção e escreves intervalos. Escolhes também casos de teste nas fronteiras, validas uma entrada e encontras a entrada que mostra um erro. Cerca de 110 minutos, para fazeres sozinho: 90 na parte obrigatória e 20 no desafio opcional.

## O que precisas de saber

O [guia do tema](03-decisoes-e-validacao.md). Antes de começar, deves conseguir explicar:

- a diferença entre `<` e `<=`;
- as tabelas de verdade do `e` e do `ou`;
- a regra da seleção encadeada: a primeira condição verdadeira ganha.

Se alguma destas ideias não estiver clara, volta à secção do guia que a explica. São as secções "Operadores de comparação", "Operadores lógicos: `e`, `ou` e `não`" e "Seleção encadeada". Para o desafio opcional precisas também do `resto`, do [guia 02](02-estado-sequencia-representacoes.md), secção "Operadores aritméticos".

O [laboratório](03-decisoes-e-validacao-laboratorio.md) deste tema é de fluxogramas, e é opcional. Os desenhos de fluxogramas não fazem parte desta ficha. Se o professor indicar o laboratório, é lá que os desenhas.

## Como trabalhar

Resolve os exercícios pela ordem. Cada um treina uma ideia do guia:

| Exercício | O que treina | Tempo |
| --- | --- | ---: |
| 1 | Avaliar comparações, também no próprio limite | 10 min |
| 2 | Juntar condições com `e`, `ou` e `não` | 10 min |
| 3 | Prever o ramo de uma seleção encadeada | 10 min |
| 4 | Escrever um intervalo e o seu contrário | 15 min |
| 5 | Validar uma entrada e aplicar uma tabela de preços, da reta ao algoritmo | 30 min |
| 6 | Encontrar a entrada que mostra um erro | 15 min |
| Total da parte obrigatória | Exercícios 1 a 6 | 90 min |
| Desafio opcional | Uma condição que mistura `e` e `ou` | 20 min |

Os exercícios 1 a 6 são obrigatórios e cabem nos 90 minutos. Depois do desafio, a secção "Para ires mais longe" tem mais um exercício, também opcional. É para quem terminar e quiser mais prática, ou para estudares em casa. Nem o desafio nem essa secção contam para concluíres a ficha.

Escreve os algoritmos na forma que usamos nas aulas, com a indentação a mostrar o que está dentro de cada caso. Se souberes a lógica e não te lembrares da forma, escreve frases claras, que também valem. Têm de dizer o que acontece em cada caso, incluindo quando um valor não serve.

Entregas as respostas em papel ou num ficheiro de texto, com as tabelas de casos e os traces.

## Exercício 1: Verdadeiro ou falso (10 minutos)

A variável `idade` vale 16. Para cada condição, diz se dá `true` ou `false`:

a) `idade >= 16`

b) `idade > 16`

c) `idade == 18`

d) `idade != 16`

e) `idade < 18`

f) `idade <= 15`

Depois escolhe duas das condições que deram resultados diferentes só por causa do igual, e explica a diferença numa frase.

## Exercício 2: Juntar condições (10 minutos)

Num parque de diversões, a montanha-russa tem duas regras: só entra quem tiver pelo menos 12 anos e pelo menos 1,40 metros de altura.

a) A variável `idade` vale 15 e a variável `altura` vale `1.45`. Diz se cada condição dá `true` ou `false`:

- `idade >= 12 e altura >= 1.40`
- `idade >= 18 e altura >= 1.40`
- `idade >= 18 ou altura >= 1.40`
- `não (idade >= 18)`

b) Qual das quatro condições é a regra da montanha-russa? Explica porque é que tem de ser com `e`, e não com `ou`.

## Exercício 3: Prever o ramo (10 minutos)

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

## Exercício 4: A estufa (15 minutos)

Numa estufa de tomates, a temperatura está boa a partir de 18 graus, incluindo os 18, e abaixo de 26 graus. Com 26 graus já está demasiado quente, e é preciso abrir as janelas. As temperaturas são números inteiros.

a) Escreve a condição que diz se a temperatura está boa.

b) Escreve a condição que diz se a temperatura está fora do bom, sem usar `não`.

c) Para as temperaturas 17, 18, 25, 26 e 27, diz se a temperatura está boa ou fora. Confirma que as tuas duas condições dão sempre respostas contrárias.

## Exercício 5: O preço das fotocópias (30 minutos)

Lê o enunciado:

> A papelaria da escola cobra as fotocópias por esta tabela. De 1 a 10 cópias, cada cópia custa 0,10 euros. De 11 a 50 cópias, cada cópia custa 0,08 euros. Com mais de 50 cópias, cada cópia custa 0,05 euros. O preço de cada cópia aplica-se a todas as cópias do pedido: 20 cópias custam 20 vezes 0,08 euros. Um pedido com 0 cópias, ou com um número negativo, é inválido, e o algoritmo escreve "Pedido inválido" em vez de um preço.

Usa só as regras da tabela. Não acrescentes descontos, arredondamentos nem outras regras que conheças de lojas verdadeiras.

a) Desenha a reta dos números de cópias, como no passo 3 do exemplo guiado do guia, e marca as regiões e as fronteiras.

b) Escreve a tabela de casos de teste, com o resultado esperado calculado à mão. Para cada fronteira, segue a regra do guia: testa o valor imediatamente abaixo, o próprio valor da fronteira e o valor imediatamente acima. Por exemplo, na fronteira entre 10 e 11, o valor da fronteira é o 10. É o último número de cópias que ainda custa 0,10 euros cada. Os casos são o 9, o 10 e o 11.

c) Escreve o algoritmo em pseudocódigo, ou em frases claras. Usa constantes para os preços e para os limites.

Se quiseres confirmar o teu algoritmo com um trace, o Mais longe 1, no fim da ficha, pede-o. É opcional.

## Exercício 6: Encontrar o erro (15 minutos)

Cada um destes bocados de algoritmo tem um erro. Para cada um, diz qual é a entrada que mostra o erro, o que aparece com essa entrada e o que devia aparecer. Depois escreve a linha corrigida.

a) Os dias da semana numeram-se de 1, a segunda-feira, a 7, o domingo. Este bocado devia escrever "Dia inválido" para um número que não seja de nenhum dia. Devia escrever "Fim de semana" ao sábado e ao domingo, e "Dia de aulas" nos outros dias:

```text
Se dia < 1 ou dia > 7
    Escreve: "Dia inválido"
Senão se dia == 6 e dia == 7
    Escreve: "Fim de semana"
Senão
    Escreve: "Dia de aulas"
```

b) A papelaria dá desconto conforme o número de cadernos. Quem compra menos de 3 não tem desconto, quem compra de 3 a 9 tem 10% e quem compra 10 ou mais tem 20%:

```text
Se quantidade <= 3
    Escreve: "Sem desconto"
Senão se quantidade < 10
    Escreve: "Desconto de 10%"
Senão
    Escreve: "Desconto de 20%"
```

## Apoio

Se estiveres encravado, usa estas pistas pela ordem em que aparecem, e passa à seguinte só se a anterior não tiver chegado.

- Exercício 1. Substitui `idade` por 16 e lê cada condição em voz alta: "dezasseis é maior ou igual a dezasseis?". Nas que têm igual, pergunta-te se o 16 está incluído.
- Exercício 2. Avalia primeiro cada comparação sozinha, e só depois junta com a tabela de verdade do `e` ou do `ou`.
- Exercício 3. Para cada idade, começa na primeira condição e desce. Para assim que uma condição for verdadeira: as de baixo já não contam.
- Exercício 4. O intervalo é "entre isto e aquilo", com `e`. O contrário é "abaixo disto ou acima daquilo", com `ou`, e cada limite muda de lado. Para cada extremo, pergunta-te se ele pertence ao bom ou ao fora.
- Exercício 5. Para encontrares as fronteiras, pergunta-te qual é o último número de cópias de cada região e o primeiro da região seguinte. Põe a validação no primeiro `Se`, como no exemplo guiado. Repara que, depois de cada `Senão se`, já sabes que as condições de cima foram falsas.
- Exercício 6. Em cada alínea, escreve primeiro o que o enunciado manda aparecer para alguns valores. Só depois segue o bocado de algoritmo com esses valores, condição a condição. Que valores escolhes para teres a certeza de que já experimentaste cada linha do bocado, e cada fronteira do enunciado?

## Desafio opcional

Leva cerca de 20 minutos.

Um ano é bissexto quando tem 29 de fevereiro. Isso acontece quando o ano é divisível por 4 e não é divisível por 100, ou quando é divisível por 400. Um número é divisível por outro quando o resto da divisão é 0. O resto escreve-se com `resto`, como aprendeste no guia anterior.

a) Escreve a condição que diz se um ano é bissexto. Como mistura `e` com `ou`, usa parênteses para mostrar o que se avalia primeiro.

b) Testa-a com os anos 2024, 2023, 1900 e 2000, e diz quais são bissextos.

c) Qual destes quatro anos mostra que a regra dos 100 é precisa? E qual mostra que a regra dos 400 é precisa?

## Para ires mais longe

Esta secção é opcional e fica fora dos 90 minutos da ficha. Não precisas de fazer nada daqui para concluíres a ficha, e os critérios de conclusão não a contam. O tempo é indicativo.

### Mais longe 1: O trace das fotocópias nas fronteiras (15 minutos)

Continua o exercício 5: usa o teu algoritmo da alínea c) e a tua tabela de casos de teste da alínea b). A matéria está no passo 9 do exemplo guiado do guia, o trace dos casos de fronteira.

Faz o trace de dois casos de fronteira à tua escolha. Confirma que dão, no trace, o resultado que previste na tabela antes de escreveres o algoritmo.

## Critérios de conclusão

- [ ] No exercício 1, tenho os seis resultados e a explicação do igual. Avaliei cada comparação com o valor que a variável tinha, também quando o valor era igual ao limite.
- [ ] No exercício 2, tenho os quatro resultados e a explicação da alínea b).
- [ ] No exercício 3, tenho as seis mensagens, parando na primeira condição verdadeira, e a explicação da alínea b) usa a regra da seleção encadeada.
- [ ] No exercício 4, usei `e` para "entre" e `ou` para "fora". As duas condições dão respostas contrárias nos cinco casos, e cada extremo fica do lado que o enunciado diz.
- [ ] No exercício 5, a tabela tem os três casos de cada fronteira, com o resultado calculado à mão antes de escrever o algoritmo. O algoritmo valida o pedido antes de calcular o preço, e usa constantes para os preços e para os limites.
- [ ] No exercício 6, para cada alínea, mostrei uma entrada concreta que revela o erro, e escrevi a correção.
- [ ] Usei só as regras que os enunciados deram.

## Autoavaliação

1. O que já consegues fazer sozinho?
2. Que dificuldade tiveste, e o que fizeste para a resolver?

![Rodapé](../imagens/rodape.png)
