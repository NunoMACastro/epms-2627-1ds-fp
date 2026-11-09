![Cabeçalho](../imagens/cabecalho.png)

# Funções e modelo integrado

Neste guia, aprendes a escrever as tuas próprias funções, partes de um algoritmo, com nome, que recebem valores e devolvem um resultado. Aprendes também a decompor um problema em funções e a testá-lo por partes. Tem papel e lápis ao lado.

Usas o `abs`, as fronteiras, os arrays e os contadores dos guias anteriores. Rever: [Uma função predefinida já vem feita](02-estado-sequencia-representacoes.md#uma-função-predefinida-já-vem-feita), [Fronteiras e casos de teste](03-decisoes-e-validacao.md#fronteiras-e-casos-de-teste) e [Contadores e acumuladores](04-repeticao-e-arrays.md#contadores-e-acumuladores). Para praticar: [ficha de exercícios](exercicios/05-funcoes-e-modelo-integrado-exercicios.md).

## Neste guia

1. [As funções evitam repetir e deixam testar por partes](#as-funções-evitam-repetir-e-deixam-testar-por-partes)
2. [Escrever uma função](#escrever-uma-função)
3. [Chamar uma função](#chamar-uma-função)
4. [`devolver`](#devolver)
5. [Funções que devolvem `true` ou `false`](#funções-que-devolvem-true-ou-false)
6. [Funções que recebem arrays](#funções-que-recebem-arrays)
7. [Decompor um problema em funções](#decompor-um-problema-em-funções)
8. [Duas soluções certas, uma mais eficiente](#duas-soluções-certas-uma-mais-eficiente)
9. [Exemplo guiado: o resumo das notas de um teste](#exemplo-guiado-o-resumo-das-notas-de-um-teste)

## As funções evitam repetir e deixam testar por partes

No guia 02 usaste o `abs`, sem saber como a conta era feita por dentro. Bastava o contrato. Uma **função** é isso: um pedaço de algoritmo com nome e com contrato, que se usa sem pensar no que tem lá dentro.

Há três razões para escreveres as tuas. A primeira é não repetir: a validação de uma nota, escrita uma vez, usa-se em todo o lado. A segunda é ler melhor: `Se notaValida(nota)` lê-se como uma frase. A terceira é a mais importante: um algoritmo dividido em funções pequenas testa-se por partes.

## Escrever uma função

```text
Função areaRetangulo(comprimento, largura)
    devolver comprimento * largura
```

A primeira linha é o cabeçalho, com a palavra `Função` e o nome. Entre parênteses estão os **parâmetros**, os nomes que a função dá aos valores que vai receber. Por baixo, mais para dentro, está o corpo da função. A palavra `devolver` termina a função e entrega um valor. Escrever a função ainda não calcula nenhuma área, porque ainda não há números.

Os parâmetros não levam tipo. O nome da função segue as regras das variáveis, e diz o que ela faz ou o que devolve. As funções escrevem-se antes do **algoritmo principal**, a parte que as usa.

Uma função também tem contrato:

- recebe: o comprimento e a largura de um retângulo, números maiores do que zero, na mesma unidade;
- devolve: a área, na unidade ao quadrado;
- exemplos: `areaRetangulo(4, 5)` devolve `20`, e `areaRetangulo(1.5, 1.5)` devolve `2.25`.

## Chamar uma função

Uma função só se executa quando alguém a **chama**, escrevendo o seu nome com valores entre parênteses. Tenta prever o que aparece no ecrã, antes de leres a resposta:

```text
Função areaRetangulo(comprimento, largura)
    devolver comprimento * largura

float area = areaRetangulo(3, 2)
Escreve: "Área: ", area
```

Aparece "Área: 6". As duas primeiras linhas só escrevem a função, e o algoritmo começa na linha do `float area`. Os valores escritos na chamada, o 3 e o 2, chamam-se **argumentos**. O parâmetro é o nome, como `comprimento`, e o argumento é o valor, como o 3. Um argumento também pode ser uma variável ou uma conta. O que passa é o valor que ela tem nesse momento, mesmo que se chame como o parâmetro.

### O que acontece numa chamada

Uma chamada executa-se sempre em quatro fases:

1. Os argumentos passam para os parâmetros, pela ordem em que estão escritos.
2. O algoritmo salta para dentro da função e executa o corpo.
3. Ao chegar a um `devolver`, a função calcula o valor e termina.
4. O algoritmo regressa ao ponto da chamada, e a chamada é substituída pelo valor devolvido.

Na fase 4, a linha passa a ser, na prática, `float area = 6`. Por isso, uma chamada pode aparecer onde caberia um valor: numa atribuição, numa conta, num `Escreve:` ou numa condição. Uma linha só com `areaRetangulo(3, 2)` calcula a área e perde-a.

### A ordem dos argumentos conta

```text
Função precoComDesconto(preco, percentagem)
    devolver preco - preco * percentagem / 100
```

`precoComDesconto(50, 10)` devolve 45, e `precoComDesconto(10, 50)` devolve 5. As duas contas são possíveis, e nenhuma dá aviso. Por isso, confirma a ordem dos parâmetros antes de escreveres a chamada.

### O trace de uma chamada

Cada chamada tem a sua própria tabela, só com as variáveis da função, a **tabela própria** da chamada. Na tabela do algoritmo principal, a linha da chamada mostra o valor que regressou:

| Passo | Instrução executada | area | Ecrã |
| ---: | --- | ---: | --- |
| 0 | antes de começar | sem valor | nada |
| 1 | `float area = areaRetangulo(3, 2)`: a função devolve 6 | 6 | nada |
| 2 | `Escreve: "Área: ", area` | 6 | Área: 6 |

A chamada do passo 1, em tabela própria:

| Passo | Instrução executada | comprimento | largura | Valor devolvido |
| ---: | --- | ---: | ---: | --- |
| 0 | os argumentos passam para os parâmetros | 3 | 2 | nenhum ainda |
| 1 | `devolver comprimento * largura` | 3 | 2 | 6, e a função termina |

Os parâmetros não começam "sem valor". Começam com os argumentos, porque é isso que a fase 1 faz.

### As variáveis da função são da função

Os parâmetros e as variáveis que nascem dentro de uma função só existem enquanto ela se executa. São **variáveis locais**. Duas variáveis com o mesmo nome, uma dentro e outra fora de uma função, são duas caixas diferentes.

Nas aulas, uma função só usa os seus parâmetros, as suas variáveis e as constantes. O que ela precisa chega pelos parâmetros, e o que tem para dar sai pelo `devolver`. Assim, pode testar-se sozinha.

## `devolver`

Uma função pode ter vários `devolver`, um em cada caminho:

```text
Função maior(a, b)
    Se a > b
        devolver a
    Senão
        devolver b
```

Em todos os caminhos possíveis, a função tem de chegar a um `devolver`. Se não chegar, a linha que a chamou fica sem valor.

`devolver` não é `Escreve:`. O `Escreve:` mostra um valor no ecrã, e o valor não vai para mais lado nenhum. O `devolver` entrega-o ao algoritmo que chamou a função, que o pode guardar ou usar numa conta. Nas aulas, as funções que calculam devolvem, e quem escreve no ecrã é o algoritmo principal.

## Funções que devolvem `true` ou `false`

Uma função pode devolver o resultado de uma condição, e responder a uma pergunta de sim ou não:

```text
const NOTA_MINIMA = 0
const NOTA_MAXIMA = 20

Função notaValida(nota)
    devolver nota >= NOTA_MINIMA e nota <= NOTA_MAXIMA
```

Os casos de teste escolhem-se nas fronteiras: -1, 0 e 1, e 19, 20 e 21. A chamada usa-se diretamente no sítio da condição:

```text
Escreve: "Nota?"
int nota = ler valor
Se notaValida(nota)
    Escreve: "Nota aceite"
Senão
    Escreve: "Nota inválida"
```

## Funções que recebem arrays

Um parâmetro pode receber um array inteiro:

```text
Função media(valores)
    int quantidade = 0
    float total = 0
    Para cada valor em valores
        quantidade = quantidade + 1
        total = total + valor
    devolver total / quantidade
```

`media([12, 7, 20, 5])` devolve 44 / 4, que é 11. Repara no contrato desta função:

- recebe: um array de números, com pelo menos um elemento;
- devolve: a média desses números, que pode ter parte decimal;
- exemplos: `media([12, 7, 20, 5])` devolve `11`, e `media([10])` devolve `10`.

A frase "com pelo menos um elemento" é uma condição que tem de ser verdadeira antes de a função ser chamada, uma **pré-condição**. Com um array vazio, a conta seria 0 / 0. O contrato diz que esse caso não está coberto, e passa a responsabilidade a quem chama. O "maiores do que zero" de `areaRetangulo` também era uma pré-condição.

Podia devolver-se 0 para o array vazio, mas quem recebesse o 0 não saberia se era uma média de zeros ou um array sem nada.

## Decompor um problema em funções

Para decidir que funções escrever, seguem-se seis passos:

1. Escrever o contrato do problema inteiro, com exemplos calculados à mão.
2. Decompor em partes, cada uma com um objetivo que se diz numa frase.
3. Escrever o contrato de cada função, com as pré-condições e dois ou três exemplos.
4. Escrever cada função e testá-la sozinha, antes de a usar.
5. Escrever o algoritmo principal, que lê os dados, chama as funções e mostra os resultados.
6. Executar à mão um exemplo do passo 1, do princípio ao fim, chamada a chamada.

Os testes do passo 4 escolhem-se a partir do contrato, antes de escrever a função. São **testes independentes da solução**, e testam o que a função devia fazer.

Uma boa função faz uma coisa só. Se precisares de dizer "e" no seu objetivo, como em "calcula a média e conta as positivas", provavelmente são duas.

## Duas soluções certas, uma mais eficiente

Dois algoritmos podem dar sempre os mesmos resultados, e um deles fazer muito mais trabalho. Nesta disciplina, esse trabalho mede-se a contar as voltas dos ciclos num exemplo pequeno. Esta solução conta as notas acima da média:

```text
int acima = 0
Para cada nota em notas
    Se nota > media(notas)
        acima = acima + 1
```

Antes de leres a conta, tenta prever: com 6 notas, quantas voltas faz esta solução, contando as de dentro da função?

O ciclo de fora dá 6 voltas, e em cada uma a função dá mais 6. São 36 voltas na função e 6 no ciclo, ao todo 42. E a média calculada é sempre a mesma.

```text
float mediaDasNotas = media(notas)
int acima = 0
Para cada nota em notas
    Se nota > mediaDasNotas
        acima = acima + 1
```

Aqui a média calcula-se uma vez. São 6 voltas na função e 6 no ciclo, ao todo 12.

| Notas no array | Média dentro do ciclo | Média calculada antes |
| ---: | ---: | ---: |
| 4 | 20 | 8 |
| 6 | 42 | 12 |
| 10 | 110 | 20 |

Um valor que não muda dentro de um ciclo calcula-se antes do ciclo. Se o array pode estar vazio, contam-se primeiro os elementos, como no guia 04, e esse cálculo fica dentro de um `Se`.

## Exemplo guiado: o resumo das notas de um teste

### O enunciado

> Um professor guardou num array as notas de um teste, todas inteiras: `notas = [14, 9, 17, 10, 6, 16]`. Quer um algoritmo que, antes de mais nada, confirme que todas as notas estão na escala de 0 a 20. Se houver alguma nota fora da escala, o algoritmo escreve "Há notas inválidas" e não calcula mais nada. Se estiverem todas certas, escreve a média da turma e quantas notas são positivas, ou seja, 10 ou mais.

### O contrato do problema

A entrada é um array de notas inteiras, com pelo menos uma nota. As saídas são a mensagem "Há notas inválidas", ou então a média e o número de positivas. As restrições são a escala de 0 a 20 e a positiva a partir de 10.

| Notas | Saída esperada | Porque foi escolhido |
| --- | --- | --- |
| `[14, 9, 17, 10, 6, 16]` | Média 12; 4 positivas | O caso do enunciado |
| `[10]` | Média 10; 1 positiva | Uma só nota, na fronteira da positiva |
| `[9]` | Média 9; 0 positivas | Uma só nota, do outro lado da fronteira |
| `[0, 20]` | Média 10; 1 positiva | Os dois extremos da escala |
| `[12, 21, 8]` | Há notas inválidas | Uma nota fora da escala, no meio do array |

### Decompor em funções

O problema precisa de três respostas: se uma nota é válida, a média e quantas são positivas. Cada uma é uma função:

| Função | Recebe | Devolve | Exemplos |
| --- | --- | --- | --- |
| `notaValida(nota)` | uma nota inteira | `true` se estiver entre 0 e 20, inclusive | -1 dá `false`; 20 dá `true` |
| `media(valores)` | um array de números, com pelo menos um elemento | a média | `[10]` dá 10; `[0, 20]` dá 10 |
| `contarPositivas(notas)` | um array de notas válidas | quantas são 10 ou mais | `[9]` dá 0; `[]` dá 0 |

`media` recebe "valores" porque serve para qualquer array de números. `contarPositivas` funciona com um array vazio, e por isso não precisa de pré-condição sobre o tamanho.

### As funções e os seus testes

```text
const NOTA_MINIMA = 0
const NOTA_MAXIMA = 20
const LIMIAR_POSITIVA = 10

Função notaValida(nota)
    devolver nota >= NOTA_MINIMA e nota <= NOTA_MAXIMA

Função media(valores)
    int quantidade = 0
    float total = 0
    Para cada valor em valores
        quantidade = quantidade + 1
        total = total + valor
    devolver total / quantidade

Função contarPositivas(notas)
    int positivas = 0
    Para cada nota em notas
        Se nota >= LIMIAR_POSITIVA
            positivas = positivas + 1
    devolver positivas
```

Antes de escrever o algoritmo principal, testa-se cada função sozinha: faz-se a chamada à mão e compara-se com o esperado. Os casos ficam nas fronteiras, e os arrays têm zero, um e vários elementos. A `media` não leva array vazio, pela pré-condição:

| Chamada | Esperado |
| --- | --- |
| `notaValida(-1)` | `false` |
| `notaValida(0)` | `true` |
| `notaValida(1)` | `true` |
| `notaValida(19)` | `true` |
| `notaValida(20)` | `true` |
| `notaValida(21)` | `false` |
| `media([10])` | 10 |
| `media([0, 20])` | 10 |
| `contarPositivas([])` | 0 |
| `contarPositivas([9])` | 0 |
| `contarPositivas([10])` | 1 |
| `contarPositivas([9, 10, 14])` | 2 |

### O algoritmo principal

```text
notas = [14, 9, 17, 10, 6, 16]
bool todasValidas = true
Para cada nota em notas
    Se notaValida(nota) == false
        todasValidas = false
        Parar
Se todasValidas
    float mediaDaTurma = media(notas)
    int positivas = contarPositivas(notas)
    Escreve: "Média: ", mediaDaTurma
    Escreve: "Positivas: ", positivas
Senão
    Escreve: "Há notas inválidas"
```

Aqui a bandeira começa em `true`, ao contrário da do guia 04, porque a pergunta é "estão todas certas?". Passa a `false` à primeira nota inválida. As funções de cálculo só são chamadas quando se sabe que as notas são válidas. A pré-condição de `media` fica garantida pelo contrato do problema.

### O teste completo

Com o array do enunciado, as seis chamadas a `notaValida` devolvem `true`, e a bandeira fica em `true`. A chamada `media(notas)`, em tabela própria:

| Volta | valor | quantidade no fim da volta | total no fim da volta |
| ---: | ---: | ---: | ---: |
| antes do ciclo | sem valor | 0 | 0 |
| 1.ª | 14 | 1 | 14 |
| 2.ª | 9 | 2 | 23 |
| 3.ª | 17 | 3 | 40 |
| 4.ª | 10 | 4 | 50 |
| 5.ª | 6 | 5 | 56 |
| 6.ª | 16 | 6 | 72 |

A função devolve 72 / 6, que é 12, e a linha passa a valer `float mediaDaTurma = 12`. `contarPositivas` conta o 14, o 17, o 10 e o 16, e devolve 4. O ecrã mostra "Média: 12" e "Positivas: 4", como o contrato previa.

Com `[12, 21, 8]`, o ciclo termina na segunda volta, e o ecrã mostra "Há notas inválidas". `media` e `contarPositivas` nunca chegam a ser chamadas.

### O dossiê do problema

O que fizeste aqui é um **dossiê algorítmico**. Tem tudo para outra pessoa perceber, verificar e programar a solução sem te fazer perguntas. Tem cinco partes:

1. a análise: o contrato do problema, com exemplos;
2. a decomposição em funções, com o objetivo de cada uma;
3. o contrato de cada função;
4. o pseudocódigo das funções e do algoritmo principal;
5. os testes de cada função e o teste completo.

## Erros frequentes

Quando uma função tua falha, procura o erro por esta ordem:

1. Escreve o caso que falhou, com o resultado esperado e o que apareceu.
2. Escreve numa frase o que achas que causa o erro.
3. Confirma essa frase na tabela própria, no caso mais curto que ainda mostra o erro.
4. Corrige a instrução que causa o erro, e não o sítio onde ele se vê.
5. Volta a testar todos os casos, também os que já davam certo.

### A função calcula, mas não devolve

```text
Função media(valores)
    int quantidade = 0
    float total = 0
    Para cada valor em valores
        quantidade = quantidade + 1
        total = total + valor
    float resultado = total / quantidade
```

A conta está certa, mas `resultado` é uma variável local, que desaparece quando a função termina. Guardar não é entregar. Acrescenta `devolver resultado` como última linha do corpo.

### `devolver` dentro do ciclo, no sítio errado

```text
Função existe(valores, procurado)
    Para cada valor em valores
        Se valor == procurado
            devolver true
        Senão
            devolver false
```

Com `existe([3, 8], 8)`, a primeira volta compara 3 com 8, e o `Senão` devolve `false`. A função termina sem olhar para o 8. Tira o `Senão` e põe o `devolver false` depois do ciclo, alinhado com o `Para cada`.

### Usar uma variável do algoritmo principal dentro da função

```text
Função precoFinal(preco)
    devolver preco - desconto

int desconto = 5
float total = precoFinal(30)
```

A função usa `desconto`, que não recebeu. O cabeçalho passa a `Função precoFinal(preco, desconto)`, e a chamada a `precoFinal(30, desconto)`.

### `Escreve:` em vez de `devolver`

Se `media` acabar com `Escreve: "Média: ", total / quantidade`, a média aparece no ecrã e a função parece certa. Mas uma linha como `Se media(notas) >= 10` fica sem nada para comparar. Troca essa linha por `devolver total / quantidade`.

## Palavras novas deste guia

- Função: um pedaço de algoritmo com nome e com contrato, que recebe valores e devolve um resultado.
- Parâmetro: o nome que a função dá, no cabeçalho, a um valor que vai receber.
- Argumento: o valor que se dá a uma função na chamada.
- Algoritmo principal: a parte do algoritmo que usa as funções.
- Chamar uma função: escrever o seu nome com valores entre parênteses, para ela se executar.
- Tabela própria: a tabela de trace de uma chamada, só com as variáveis da função.
- Variável local: um parâmetro, ou uma variável que nasce dentro de uma função.
- Pré-condição: uma condição que tem de ser verdadeira antes de a função ser chamada.
- Testes independentes da solução: testes escolhidos a partir do contrato, antes de olhar para a solução.
- Dossiê algorítmico: a análise, a decomposição, os contratos, o pseudocódigo e os testes de um problema.

## O que vem a seguir

A algoritmia fecha com os projetos [Duelo de dados](projetos-guiados/05-projeto-1-duelo-de-dados.md) e [Adivinha o número](projetos-guiados/05-projeto-2-adivinha-o-numero.md), em que levas um problema do enunciado até um algoritmo testado.

![Rodapé](../imagens/rodape.png)
