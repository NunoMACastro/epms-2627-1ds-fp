![Cabeçalho](../imagens/cabecalho.png)

# Decisões e validação

Neste guia, aprendes a escrever algoritmos que escolhem o que fazer consoante os dados. Aprendes também a verificar uma entrada antes de a usar. Este tema ainda não repete instruções: um algoritmo que recebe um valor inválido avisa e termina.

Usas o contrato, a atribuição e a tabela de trace dos guias anteriores. Rever: [O contrato diz o que entra, o que sai e que regras há](01-do-enunciado-ao-problema.md#o-contrato-diz-o-que-entra-o-que-sai-e-que-regras-há), [Atribuição](02-estado-sequencia-representacoes.md#atribuição-dar-um-valor-não-é-perguntar-se-é-igual) e [Tabela de trace](02-estado-sequencia-representacoes.md#tabela-de-trace). Para praticar: [ficha de exercícios](exercicios/03-decisoes-e-validacao-exercicios.md).

## Neste guia

1. [Uma condição só responde `true` ou `false`](#uma-condição-só-responde-true-ou-false)
2. [Seis operadores comparam dois valores](#seis-operadores-comparam-dois-valores)
3. [Operadores lógicos: `e`, `ou` e `não`](#operadores-lógicos-e-ou-e-não)
4. [A seleção simples executa um bloco ou salta-o](#a-seleção-simples-executa-um-bloco-ou-salta-o)
5. [A indentação mostra o que está dentro](#a-indentação-mostra-o-que-está-dentro)
6. [A seleção composta escolhe entre dois blocos](#a-seleção-composta-escolhe-entre-dois-blocos)
7. [Seleção encadeada](#seleção-encadeada)
8. [Intervalos](#intervalos)
9. [Cada valor cai num grupo, e num só](#cada-valor-cai-num-grupo-e-num-só)
10. [Fronteiras e casos de teste](#fronteiras-e-casos-de-teste)
11. [Validar é verificar uma entrada antes de a usar](#validar-é-verificar-uma-entrada-antes-de-a-usar)
12. [Exemplo guiado: validar e classificar uma nota](#exemplo-guiado-validar-e-classificar-uma-nota)

## Uma condição só responde `true` ou `false`

Até agora, os teus algoritmos faziam sempre as mesmas contas. Mas uma loja cobra portes só nas encomendas pequenas, e um jogo acaba quando as vidas chegam a zero. O que se faz depende dos dados.

Uma **condição** é uma pergunta cuja resposta só pode ser verdadeiro ou falso, `true` ou `false`. "A nota é maior ou igual a 10?" é uma condição. "Qual é a nota?" não é, porque a resposta é um número.

Uma condição depende do valor que as variáveis têm nesse momento. Com `nota` a valer 9, `nota >= 10` é `false`, por muito perto que 9 esteja de 10.

## Seis operadores comparam dois valores

Nesta tabela, `nota` vale 10:

| Operador | Pergunta | Exemplo | Resultado |
| --- | --- | --- | --- |
| `==` | é igual a? | `nota == 10` | `true` |
| `!=` | é diferente de? | `nota != 10` | `false` |
| `<` | é menor do que? | `nota < 10` | `false` |
| `<=` | é menor ou igual a? | `nota <= 10` | `true` |
| `>` | é maior do que? | `nota > 10` | `false` |
| `>=` | é maior ou igual a? | `nota >= 10` | `true` |

Na matemática escreves ≠, ≤ e ≥. Aqui usam-se as teclas que existem no teclado, e vais encontrar os seis operadores no Python e no C. O igual de uma condição é sempre `==`, porque aqui se está a perguntar.

A diferença entre `<` e `<=` está só no próprio limite. Para 9, `nota < 10` e `nota <= 10` dão os dois `true`. Para 11, dão os dois `false`. Só discordam no 10.

Numa comparação com contas, como `a + b > 10`, as contas fazem-se primeiro.

## Operadores lógicos: `e`, `ou` e `não`

Os **operadores lógicos** juntam condições, ou trocam o valor de uma condição.

Para entrares na piscina, tens de ter a entrada paga e trazer touca. Sendo A e B duas condições, `A e B` só é verdadeira quando as duas são verdadeiras. A uma tabela destas, com todas as combinações, chama-se **tabela de verdade**:

| A | B | A e B |
| --- | --- | --- |
| `true` | `true` | `true` |
| `true` | `false` | `false` |
| `false` | `true` | `false` |
| `false` | `false` | `false` |

Na cantina, podes pagar com dinheiro ou com cartão. `A ou B` é verdadeira quando pelo menos uma é verdadeira, também quando são as duas:

| A | B | A ou B |
| --- | --- | --- |
| `true` | `true` | `true` |
| `true` | `false` | `true` |
| `false` | `true` | `true` |
| `false` | `false` | `false` |

No dia a dia, "sopa ou sobremesa" quer dizer uma ou a outra, mas não as duas. O `ou` dos algoritmos não é esse.

`não A` troca o valor de `A`. Antes de continuares, tenta escrever o contrário de "a nota é maior ou igual a 10".

O contrário é "a nota é menor do que 10", e não "menor ou igual". `não (nota >= 10)` é o mesmo que `nota < 10`, porque o 10 pertence a um lado, e só a um.

Quando se misturam `e` e `ou`, a ordem muda o resultado, como nas contas. Imagina que a piscina passou a deixar entrar as crianças com menos de 6 anos, mesmo sem pagar e sem touca. Chega uma criança de 4 anos, sem entrada paga e sem touca. `paga` e `touca` são variáveis `bool`, que servem sozinhas de condição:

| Condição | Primeiro | Depois | Resultado |
| --- | --- | --- | --- |
| `(paga e touca) ou idade < 6` | `false` e `false` dá `false` | `false` ou `true` dá `true` | `true` |
| `paga e (touca ou idade < 6)` | `false` ou `true` dá `true` | `false` e `true` dá `false` | `false` |

A primeira é a regra certa, e a segunda obriga toda a gente a pagar. Sempre que misturares `e` com `ou`, usa parênteses.

## A seleção simples executa um bloco ou salta-o

Uma **seleção** é uma instrução que escolhe o que executar consoante uma condição. Esta avisa de manhã quando está frio, e `temperatura` foi lida mais acima:

```text
Se temperatura < 12
    Escreve: "Leva um casaco."
```

Com 8 graus, `8 < 12` dá `true`, e aparece a mensagem. Com 20, dá `false`, e não aparece nada. Nos dois casos, o algoritmo continua na primeira linha depois do bloco. O **bloco** são as linhas por baixo do `Se`, mais para dentro, que só se executam se a condição for verdadeira.

## A indentação mostra o que está dentro

A **indentação** é o recuo de uma linha em relação à margem, com quatro espaços por nível. Nenhuma palavra diz onde acaba o bloco de um `Se`: quem o diz é a indentação. A primeira linha que volta à margem do `Se` já está fora do bloco.

Estas duas versões só diferem na margem da última linha:

```text
Se temperatura < 12
    Escreve: "Leva um casaco."
Escreve: "Bom dia."
```

```text
Se temperatura < 12
    Escreve: "Leva um casaco."
    Escreve: "Bom dia."
```

| temperatura | Primeira versão | Segunda versão |
| ---: | --- | --- |
| 8 | Leva um casaco. Bom dia. | Leva um casaco. Bom dia. |
| 20 | Bom dia. | nada |

As palavras são as mesmas, e o comportamento mudou. No Python, também é a indentação que decide.

## A seleção composta escolhe entre dois blocos

Numas eleições, só vota quem tem 18 anos ou mais. A **seleção composta** escolhe sempre um de dois blocos, um para quando a condição é verdadeira e outro para quando é falsa:

```text
Se idade >= 18
    Escreve: "Já pode votar."
Senão
    Escreve: "Ainda não pode votar."
```

Com 17, `17 >= 18` dá `false`, e executa-se o bloco do `Senão`. Com 18, executa-se o do `Se`. O `Senão` escreve-se na mesma margem do `Se`. Cada um dos caminhos de uma decisão chama-se **ramo**, e aqui executa-se sempre exatamente um.

## Seleção encadeada

Às vezes há mais de duas possibilidades. Com 0 vidas, o jogo acabou. Com 1 ou 2, ainda se joga, mas com um aviso. Com 3 ou mais, o jogo continua. A **seleção encadeada** acrescenta condições com `Senão se`:

```text
Se vidas == 0
    Escreve: "Fim do jogo"
Senão se vidas < 3
    Escreve: "Cuidado, estás quase a perder"
Senão
    Escreve: "O jogo continua"
```

A cadeia segue três regras:

1. As condições avaliam-se de cima para baixo.
2. A primeira condição verdadeira ganha: executa-se o seu bloco e salta-se para o fim da cadeia.
3. Se nenhuma for verdadeira, executa-se o `Senão`. Sem `Senão`, não se executa nada.

| vidas | `vidas == 0` | `vidas < 3` | Ecrã |
| ---: | --- | --- | --- |
| 5 | `false` | `false` | O jogo continua |
| 2 | `false` | `true` | Cuidado, estás quase a perder |
| 0 | `true` | não é avaliada | Fim do jogo |

Com 0 vidas, a segunda condição também seria verdadeira, mas nunca chega a ser avaliada. E, quando se pergunta `vidas < 3`, já se sabe que as vidas não são 0, porque senão o algoritmo não tinha chegado ali.

O `Senão se` escreve-se também na margem do `Se`, porque é parte da mesma cadeia.

## Intervalos

Muitas condições perguntam se um valor está entre dois limites, como uma nota entre 0 e 20. A esse conjunto de valores chama-se **intervalo**. Escreve-se com duas comparações ligadas por `e`, porque o valor tem de cumprir as duas:

```text
nota >= 0 e nota <= 20
```

Os operadores escolhem-se pelo que o enunciado diz sobre os extremos. "Entre 0 e 20, inclusive" leva `>=` e `<=`. "Maior do que 0 e menor do que 20" leva `>` e `<`. Quando o enunciado não diz se os extremos estão incluídos, pergunta-se a quem o escreveu, ou escreve-se a decisão que se tomou.

Nas aulas, cada comparação compara dois valores, e por isso não se escreve `0 <= nota <= 20`.

Um valor está fora do intervalo quando está abaixo do limite de baixo ou acima do limite de cima:

```text
nota < 0 ou nota > 20
```

O `e` passou a `ou`, o `>=` passou a `<`, e o `<=` passou a `>`. Para estar fora, basta falhar um dos lados.

<details>
<summary>Para ires mais longe: os intervalos noutros sítios</summary>

Na matemática, [0, 20] são os números de 0 a 20, incluindo o 0 e o 20. Um extremo que pertence ao intervalo diz-se fechado, e um que não pertence diz-se aberto: [0, 10[ inclui o 0 e exclui o 10.

No C, `0 <= nota <= 20` compara primeiro `0 <= nota`, que dá verdadeiro ou falso, e depois compara esse resultado com 20. O Python lê-a como na matemática. Com duas comparações, a condição só se lê de uma maneira.

</details>

## Cada valor cai num grupo, e num só

Quando uma seleção separa os valores em grupos, confirmam-se duas coisas.

Nenhum valor pode pertencer a dois grupos. Com "negativa até 10" e "positiva a partir de 10", o 10 ficava nos dois. A condições que não se sobrepõem chama-se **mutuamente exclusivas**.

Todos os valores têm de pertencer a algum grupo. Com "negativa abaixo de 10" e "positiva acima de 10", o 10 ficava sem resposta.

A forma mais segura de o verificar é desenhar uma reta com os valores e marcar os grupos. A seleção encadeada não resolve uma sobreposição, esconde-a: o valor vai, sem aviso, para o grupo que estiver escrito primeiro.

## Fronteiras e casos de teste

Uma **fronteira** é o sítio onde a resposta de um algoritmo muda. Ao valor a partir do qual ela muda chama-se **limiar**. Com a positiva em 10, há uma fronteira entre 9 e 10.

Os erros de decisão concentram-se nas fronteiras. `nota >= 10` e `nota > 10` só discordam no 10, e por isso testar com 5 e com 15 não mostra o erro.

Para cada fronteira, testa-se o valor imediatamente abaixo, o próprio valor da fronteira e o valor imediatamente acima. Para o 10, são o 9, o 10 e o 11. O valor da fronteira é o número que o enunciado escreve para esse limite. Se escrever dois, como em "criança até aos 12 anos, jovem a partir dos 13", escolhe-se um deles, e qualquer um serve.

## Validar é verificar uma entrada antes de a usar

Uma entrada é válida quando cumpre o contrato, e inválida quando não cumpre. **Validar** é verificar se é válida antes de a usar. Quem quer escrever 10 pode escrever 100, e sem validação o algoritmo classifica-o na mesma, com toda a confiança.

O contrato diz o que é válido, e por isso a validação transforma cada limite numa condição. Vem sempre antes do resto, porque não faz sentido calcular com um valor que não se sabe se serve.

Nesta fase, assume-se que, numa linha como `int nota = ler valor`, a pessoa escreve mesmo um inteiro. O que fazer quando alguém escreve letras fica para o Python.

## Exemplo guiado: validar e classificar uma nota

### O enunciado

> Um professor quer um algoritmo que o ajude a classificar os testes. O algoritmo lê a nota de um teste, que é um número inteiro na escala de 0 a 20. Se a nota for igual ou superior a 10, escreve "Positiva". Se for inferior a 10, escreve "Negativa". Se a nota escrita não pertencer à escala, o algoritmo escreve "Nota inválida" e não a classifica.

### O contrato

A entrada é a nota, um número inteiro de 0 a 20. Uma nota fora da escala é inválida, e o algoritmo tem de a recusar. A saída é uma de três mensagens: "Positiva", "Negativa" ou "Nota inválida". A escala inclui o 0 e o 20, e "igual ou superior a 10" quer dizer que o 10 já é positiva.

Sabes da escola que um 9,5 às vezes se arredonda para 10. Este enunciado não fala disso, e usar uma regra que ele não dá é inventar regras.

### Desenhar a reta e marcar as regiões

Antes de escrever uma condição, desenha-se a reta dos valores inteiros e marca-se a resposta de cada região:

```text
     inválida   |         negativa         |          positiva          |   inválida
  ...  -2   -1  |   0   1   2  ...  8   9  |  10  11  12  ...  19  20   |  21  22  ...
                ↑                          ↑                            ↑
           entre -1 e 0               entre 9 e 10                entre 20 e 21
```

A reta tem quatro regiões e três fronteiras. Cada inteiro cai numa região, e numa só.

### Escolher os casos de teste

Os valores das fronteiras são o 0 e o 20, os extremos da escala, e o 10, o limiar. Os resultados escrevem-se antes de haver algoritmo, porque vêm do enunciado:

| Nota | Resultado esperado | Porque foi escolhido |
| ---: | --- | --- |
| -1 | Nota inválida | Imediatamente abaixo da escala |
| 0 | Negativa | O extremo de baixo da escala |
| 1 | Negativa | Imediatamente acima do extremo de baixo |
| 9 | Negativa | Imediatamente abaixo do limiar |
| 10 | Positiva | O próprio limiar |
| 11 | Positiva | Imediatamente acima do limiar |
| 19 | Positiva | Imediatamente abaixo do extremo de cima |
| 20 | Positiva | O extremo de cima da escala |
| 21 | Nota inválida | Imediatamente acima da escala |

### O algoritmo, aos poucos

Os limites são regras do enunciado, e por isso são constantes. A validação é o contrário do intervalo da escala, e é a primeira condição da cadeia:

```text
const NOTA_MINIMA = 0
const NOTA_MAXIMA = 20
const LIMIAR_POSITIVA = 10
Escreve: "Nota do teste (inteiro de 0 a 20)?"
int nota = ler valor
Se nota < NOTA_MINIMA ou nota > NOTA_MAXIMA
    Escreve: "Nota inválida"
```

A condição de positiva não precisa de confirmar que a nota não passa de 20. Quando o algoritmo lá chega, já sabe que a nota é válida. A negativa não precisa de condição nenhuma, porque é o que sobra:

```text
Senão se nota >= LIMIAR_POSITIVA
    Escreve: "Positiva"
Senão
    Escreve: "Negativa"
```

O algoritmo completo:

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

O mesmo algoritmo pode escrever-se em frases claras:

1. Pergunta "Nota do teste (inteiro de 0 a 20)?" e guarda o número inteiro que a pessoa escrever como nota.
2. Se a nota for menor do que 0 ou maior do que 20, escreve "Nota inválida" e não faz mais nada.
3. Se não, e se a nota for 10 ou mais, escreve "Positiva".
4. Em todos os outros casos, escreve "Negativa".

### E se a validação viesse depois?

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

Com 21, a primeira condição é verdadeira, e aparece "Positiva". A validação nunca chega a ser avaliada. Com -1, esta versão responde bem, e quem testasse só esse caso ficava convencido de que funcionava. É por isso que se testam os dois lados da escala.

### O trace

Numa linha com uma condição, a coluna "Condição e resultado" mostra a condição com os valores e o que ela dá. Este é o trace da nota 10:

| Passo | Instrução executada | nota | Condição e resultado | Ecrã |
| ---: | --- | ---: | --- | --- |
| 0 | antes de começar | sem valor | nenhuma | nada |
| 1 | `Escreve: "Nota do teste (inteiro de 0 a 20)?"` | sem valor | nenhuma | Nota do teste (inteiro de 0 a 20)? |
| 2 | `int nota = ler valor` | 10 | nenhuma | a pessoa escreve 10 |
| 3 | `Se nota < NOTA_MINIMA ou nota > NOTA_MAXIMA` | 10 | `10 < 0` dá `false`, `10 > 20` dá `false`; `false` ou `false` dá `false` | nada |
| 4 | `Senão se nota >= LIMIAR_POSITIVA` | 10 | `10 >= 10` dá `true` | nada |
| 5 | `Escreve: "Positiva"` | 10 | nenhuma | Positiva |

No passo 3, a condição da validação é falsa, ou seja, a nota é válida, e o bloco do `Se` é saltado. Depois do passo 5, o algoritmo salta para o fim da cadeia, e por isso o `Senão` não aparece. O `Senão` não pergunta nada, e nunca tem linha própria no trace.

Cada linha desta tabela resume o trace de uma entrada:

| nota | Fora da escala? | `nota >= LIMIAR_POSITIVA` | Ramo executado | Ecrã |
| ---: | --- | --- | --- | --- |
| -1 | `true` | não é avaliada | o do `Se` | Nota inválida |
| 0 | `false` | `false` | o do `Senão` | Negativa |
| 1 | `false` | `false` | o do `Senão` | Negativa |
| 9 | `false` | `false` | o do `Senão` | Negativa |
| 10 | `false` | `true` | o do `Senão se` | Positiva |
| 11 | `false` | `true` | o do `Senão se` | Positiva |
| 19 | `false` | `true` | o do `Senão se` | Positiva |
| 20 | `false` | `true` | o do `Senão se` | Positiva |
| 21 | `true` | não é avaliada | o do `Se` | Nota inválida |

O 0 é negativa, e não inválida, porque `0 < 0` é falso. O 10 é positiva porque o operador é `>=`, e `10 >= 10` é verdadeiro. O 20 é positiva, e não inválida, porque `20 > 20` é falso.

### Comparar com o previsto

A coluna "Ecrã" coincide com o "Resultado esperado" nos nove casos. Se algum não coincidisse, o trace mostrava a condição que deu um resultado diferente do que devia.

## Erros frequentes

### O igual no sítio errado

Com `nota > LIMIAR_POSITIVA`, o 10 aparece como negativa, e é o único valor que mostra o erro. Com `nota >= NOTA_MAXIMA` na validação, o 20 passa a inválido. Volta ao enunciado e pergunta-te se o próprio limite está incluído.

### `e` onde é preciso `ou`

Com `nota < NOTA_MINIMA e nota > NOTA_MAXIMA`, a validação nunca apanha nada, porque nenhum número é as duas coisas. Com 21, o algoritmo escreve "Positiva". O erro inverso é perguntar se a nota é válida com `ou`: `nota >= NOTA_MINIMA ou nota <= NOTA_MAXIMA` é verdadeira para todos os números. Um intervalo escreve-se com `e`, e o seu contrário com `ou`.

### Igual em vez de maior ou igual

Com `nota == LIMIAR_POSITIVA`, só o 10 dá positiva. O 11 é o primeiro valor que mostra o erro, e é por isso que ele está nos casos de teste.

### Dois `Se` separados em vez de uma cadeia

```text
Se nota < NOTA_MINIMA ou nota > NOTA_MAXIMA
    Escreve: "Nota inválida"
Se nota >= LIMIAR_POSITIVA
    Escreve: "Positiva"
Senão
    Escreve: "Negativa"
```

Com 21, aparecem "Nota inválida" e "Positiva". Um `Se` encostado à margem começa uma decisão nova. Quando só um caso deve acontecer, escreve-se uma cadeia com `Senão se`.

## Palavras novas deste guia

- Condição: uma pergunta cuja resposta só pode ser `true` ou `false`.
- Operador lógico: `e`, `ou` ou `não`, que juntam condições ou trocam o valor de uma condição.
- Tabela de verdade: a tabela com o resultado de um operador lógico para todas as combinações.
- Seleção: uma instrução que escolhe o que executar consoante uma condição.
- Bloco: as linhas indentadas por baixo de um `Se`, de um `Senão se` ou de um `Senão`.
- Indentação: o recuo de uma linha em relação à margem, que mostra o que está dentro de quê.
- Seleção composta: um `Se` com `Senão`, que executa sempre um de dois blocos.
- Ramo: cada um dos caminhos de uma decisão.
- Seleção encadeada: um `Se` seguido de um ou mais `Senão se`, em que a primeira condição verdadeira ganha.
- Intervalo: o conjunto dos valores entre dois limites.
- Condições mutuamente exclusivas: condições que não se sobrepõem, porque nenhum valor pertence a dois grupos.
- Fronteira: o sítio onde a resposta de um algoritmo muda.
- Limiar: o valor a partir do qual a resposta muda.
- Validar: verificar se uma entrada cumpre o contrato antes de a usar.

## O que vem a seguir

No tema seguinte, [Repetição e arrays](04-repeticao-e-arrays.md), o algoritmo passa a repetir instruções, por exemplo para voltar a pedir uma nota até receber uma válida.

![Rodapé](../imagens/rodape.png)
