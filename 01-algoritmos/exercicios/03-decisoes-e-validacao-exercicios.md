![Cabeçalho](../../imagens/cabecalho.png)

# Ficha de exercícios: Decisões e validação

Avalias comparações, juntas condições, prevês o ramo de uma seleção e escreves intervalos. Testas fronteiras, validas uma entrada e procuras a entrada que mostra um erro. Os exercícios 1 a 6 são obrigatórios, e as respostas ficam em papel ou num ficheiro de texto, com a tabela de casos de teste. Nos algoritmos, a indentação mostra o que está dentro de cada ramo, e as frases claras também valem. Para rever: o [guia do tema](../03-decisoes-e-validacao.md).

## Exercício 1: Verdadeiro ou falso

A variável `idade` vale 16. Para cada condição, diz se dá `true` ou `false`:

a) `idade >= 16`

b) `idade > 16`

c) `idade == 18`

d) `idade != 16`

e) `idade < 18`

f) `idade <= 15`

Há duas condições que só diferem no sinal de igual e deram resultados diferentes. Quais são? Explica numa frase.

Rever: [Seis operadores comparam dois valores](../03-decisoes-e-validacao.md#seis-operadores-comparam-dois-valores).

<details>
<summary>Pista</summary>

Substitui `idade` por 16 e lê cada condição por palavras: "dezasseis é maior ou igual a dezasseis?".

</details>

## Exercício 2: Juntar condições

Num parque de diversões, a montanha-russa tem duas regras: só entra quem tiver pelo menos 12 anos e pelo menos 1,40 metros de altura.

a) A variável `idade` vale 15 e a variável `altura` vale `1.45`. Diz se cada condição dá `true` ou `false`:

- `idade >= 12 e altura >= 1.40`
- `idade >= 18 e altura >= 1.40`
- `idade >= 12 ou altura >= 1.40`
- `não (idade >= 18)`

b) Qual das quatro é a regra da montanha-russa? Para cada uma das outras três, dá uma pessoa, com idade e altura, a quem ela dá um resultado errado.

Rever: [Operadores lógicos: `e`, `ou` e `não`](../03-decisoes-e-validacao.md#operadores-lógicos-e-ou-e-não).

<details>
<summary>Pista</summary>

Avalia primeiro cada comparação sozinha, e só depois junta com a tabela de verdade do `e` ou do `ou`.

</details>

## Exercício 3: Prever o ramo

Lê este algoritmo de um cinema:

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

Rever: [Seleção encadeada](../03-decisoes-e-validacao.md#seleção-encadeada).

<details>
<summary>Pista</summary>

Para cada idade, começa na primeira condição e desce, uma de cada vez.

</details>

## Exercício 4: A estufa

Numa estufa de tomates, a temperatura está boa a partir de 18 graus, incluindo os 18, e abaixo de 26 graus. Com 26 graus já está demasiado quente, e é preciso abrir as janelas. As temperaturas são números inteiros.

a) Escreve a condição que diz se a temperatura está boa.

b) Escreve a condição que diz se a temperatura está fora do bom, sem usar `não`.

c) Para as temperaturas 17, 18, 25, 26 e 27, diz se a temperatura está boa ou fora. Confirma que as tuas duas condições dão sempre respostas contrárias.

Rever: [Intervalos](../03-decisoes-e-validacao.md#intervalos).

<details>
<summary>Pista</summary>

Para cada extremo, pergunta-te se ele pertence ao bom ou ao fora.

</details>

## Exercício 5: O preço das fotocópias

Lê o enunciado:

> A papelaria da escola cobra as fotocópias por esta tabela. De 1 a 10 cópias, cada cópia custa 0,10 euros. De 11 a 50 cópias, cada cópia custa 0,08 euros. Com mais de 50 cópias, cada cópia custa 0,05 euros. O preço de cada cópia aplica-se a todas as cópias do pedido: 20 cópias custam 20 vezes 0,08 euros. Um pedido com 0 cópias, ou com um número negativo, é inválido, e o algoritmo escreve "Pedido inválido" em vez de um preço.

Usa só as regras da tabela. Não acrescentes descontos, arredondamentos nem outras regras que conheças de lojas verdadeiras.

a) A reta dos números de cópias já tem duas regiões marcadas: a dos pedidos inválidos e a das cópias a 0,10 euros. Copia-a e completa-a, como no exemplo guiado do guia. Marca as regiões que faltam e a fronteira que falta.

```text
   inválido  |      0,10 cada      |
  ...  -1  0 |  1  2  ...  9  10   |  11  12  ...
             ↑                     ↑
        entre 0 e 1          entre 10 e 11
```

b) Completa a tabela de casos de teste, com o resultado esperado calculado à mão. Para cada fronteira, segue a regra do guia. As três linhas da fronteira entre 10 e 11 já estão feitas. Nessa fronteira, o enunciado escreve os dois números, o 10 e o 11, e escolheu-se o 10. Acrescenta as linhas das outras duas fronteiras.

| Cópias | Resultado esperado | Porque é que este caso foi escolhido |
| ---: | --- | --- |
| 9 | 9 × 0,10 = 0,90 euros | Imediatamente abaixo do 10 |
| 10 | 10 × 0,10 = 1,00 euros | O valor da fronteira, o último que custa 0,10 euros cada |
| 11 | 11 × 0,08 = 0,88 euros | Imediatamente acima do 10 |
| | | |
| | | |
| | | |
| | | |
| | | |
| | | |

c) Escreve o algoritmo. O princípio já está feito: as constantes dos preços e dos limites, a leitura e a validação. Continua a cadeia a partir daí, com um ramo para cada preço.

```text
const PRECO_ATE_10 = 0.10
const PRECO_ATE_50 = 0.08
const PRECO_ACIMA_50 = 0.05
const MINIMO_COPIAS = 1
const MAXIMO_PEDIDO_PEQUENO = 10
const MAXIMO_PEDIDO_MEDIO = 50
Escreve: "Quantas cópias?"
int copias = ler valor
Se copias < MINIMO_COPIAS
    Escreve: "Pedido inválido"
```

Cada ramo com preço guarda-o numa variável. Uma variável pode nascer dentro de um ramo. Nesse caso, a linha onde ela nasce, com o tipo à frente, escreve-se em cada ramo que a usa. Como só um ramo se executa, a variável nasce uma vez em cada execução.

Rever: [Exemplo guiado: validar e classificar uma nota](../03-decisoes-e-validacao.md#exemplo-guiado-validar-e-classificar-uma-nota) e [Fronteiras e casos de teste](../03-decisoes-e-validacao.md#fronteiras-e-casos-de-teste).

<details>
<summary>Pista</summary>

Para encontrares a fronteira que falta, pergunta-te qual é o último número de cópias de cada região e o primeiro da região seguinte. Na alínea c), repara que, depois de cada `Senão se`, já sabes que as condições de cima foram falsas.

</details>

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

Rever: [Seleção encadeada](../03-decisoes-e-validacao.md#seleção-encadeada), [Cada valor cai num grupo, e num só](../03-decisoes-e-validacao.md#cada-valor-cai-num-grupo-e-num-só) e [Fronteiras e casos de teste](../03-decisoes-e-validacao.md#fronteiras-e-casos-de-teste).

<details>
<summary>Pista</summary>

Em cada alínea, escreve primeiro o que o enunciado manda aparecer para alguns valores, um de cada lado de cada fronteira. Só depois segue o bocado de algoritmo com esses valores, condição a condição, e compara.

</details>

## Desafios

### Desafio 1: O ano bissexto

Um ano é bissexto quando tem 29 de fevereiro. Isso acontece quando o ano é divisível por 4 e não é divisível por 100, ou quando é divisível por 400. Um número é divisível por outro quando o resto da divisão é 0. O resto escreve-se com `resto`.

a) Escreve a condição que diz se um ano é bissexto. Como mistura `e` com `ou`, usa parênteses para mostrar o que se avalia primeiro.

b) Testa-a com os anos 2024, 2023, 1900 e 2000, e diz quais são bissextos.

c) Qual destes quatro anos mostra que a regra dos 100 faz falta? E qual mostra que a regra dos 400 faz falta?

Rever: [Operadores aritméticos](../02-estado-sequencia-representacoes.md#operadores-aritméticos) e [Operadores lógicos: `e`, `ou` e `não`](../03-decisoes-e-validacao.md#operadores-lógicos-e-ou-e-não).

### Desafio 2: O trace das fotocópias nas fronteiras

Continua o exercício 5: usa o teu algoritmo da alínea c) e a tua tabela de casos de teste da alínea b).

Faz o trace de dois casos de fronteira. O primeiro é o 11, e as três primeiras linhas já estão feitas. Continua-o com as linhas do teu algoritmo. Se a tua variável do preço tiver outro nome, usa-o na coluna `preco`. O segundo caso escolhes tu, da tua tabela.

| Passo | Instrução executada | copias | preco | Condição e resultado | Ecrã |
| ---: | --- | ---: | ---: | --- | --- |
| 0 | antes de começar | sem valor | sem valor | nenhuma | nada |
| 1 | `Escreve: "Quantas cópias?"` | sem valor | sem valor | nenhuma | Quantas cópias? |
| 2 | `int copias = ler valor` | 11 | sem valor | nenhuma | a pessoa escreve 11 |
| 3 | `Se copias < MINIMO_COPIAS` | 11 | sem valor | `11 < 1` dá `false` | nada |

Confirma que os dois casos dão, no trace, o resultado que previste na tabela antes de escreveres o algoritmo.

Rever: [O trace](../03-decisoes-e-validacao.md#o-trace).

## Critérios de conclusão

- No exercício 1, avaliaste as seis condições e explicaste a diferença que o igual faz.
- No exercício 2, avaliaste as quatro condições, e deste uma pessoa concreta para cada uma das que estão erradas.
- No exercício 3, paraste na primeira condição verdadeira, e explicaste a alínea b) com a regra da seleção encadeada.
- No exercício 4, cada extremo ficou do lado que o enunciado diz. As duas condições, a segunda sem `não`, dão respostas contrárias nos cinco casos.
- No exercício 5, completaste a reta e a tabela antes do algoritmo, e o algoritmo continua a validação com um ramo para cada preço.
- No exercício 6, mostraste em cada alínea a entrada que revela o erro, o que devia aparecer e o que aparece, e corrigiste o bocado.
- Usaste só as regras que os enunciados deram.

![Rodapé](../../imagens/rodape.png)
