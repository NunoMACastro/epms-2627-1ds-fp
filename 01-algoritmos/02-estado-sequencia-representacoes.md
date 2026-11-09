![Cabeçalho](../imagens/cabecalho.png)

# Estado, sequência e representações

Neste guia, aprendes a escrever algoritmos em pseudocódigo, com variáveis, tipos e contas, e a segui-los à mão, linha a linha, numa tabela. Todos os algoritmos são sequenciais: fazem sempre os mesmos passos, pela mesma ordem.

Usas o contrato e o estado do guia anterior. Rever: [O contrato diz o que entra, o que sai e que regras há](01-do-enunciado-ao-problema.md#o-contrato-diz-o-que-entra-o-que-sai-e-que-regras-há) e [O estado é uma fotografia, e a ação muda-o](01-do-enunciado-ao-problema.md#o-estado-é-uma-fotografia-e-a-ação-muda-o). Para praticar: [ficha de exercícios](exercicios/02-estado-sequencia-representacoes-exercicios.md).

## Neste guia

1. [O pseudocódigo escreve o raciocínio sem ambiguidades](#o-pseudocódigo-escreve-o-raciocínio-sem-ambiguidades)
2. [Uma variável é uma caixa com etiqueta](#uma-variável-é-uma-caixa-com-etiqueta)
3. [Uma constante dá nome a uma regra do problema](#uma-constante-dá-nome-a-uma-regra-do-problema)
4. [O tipo diz que valores uma variável guarda](#o-tipo-diz-que-valores-uma-variável-guarda)
5. [Atribuição: dar um valor não é perguntar se é igual](#atribuição-dar-um-valor-não-é-perguntar-se-é-igual)
6. [Operadores aritméticos](#operadores-aritméticos)
7. [Entrada e saída: `ler valor` e `Escreve:`](#entrada-e-saída-ler-valor-e-escreve)
8. [Uma função predefinida já vem feita](#uma-função-predefinida-já-vem-feita)
9. [O pseudocódigo das aulas é um vocabulário pequeno](#o-pseudocódigo-das-aulas-é-um-vocabulário-pequeno)
10. [Numa sequência, a ordem importa](#numa-sequência-a-ordem-importa)
11. [Tabela de trace](#tabela-de-trace)
12. [Exemplo guiado: converter minutos em horas e minutos](#exemplo-guiado-converter-minutos-em-horas-e-minutos)

## O pseudocódigo escreve o raciocínio sem ambiguidades

No guia anterior, escreveste passos em português, e o português deixa passar frases como "espera um bocado". Uma linguagem de programação não tem esse problema, mas obriga a regras de escrita rígidas. No C, um ponto e vírgula esquecido impede o programa de funcionar.

O **pseudocódigo** fica a meio caminho. É texto escrito com um vocabulário pequeno e sempre igual, que toda a turma lê da mesma maneira. Nenhum computador o executa, e por isso a tua atenção fica no raciocínio, e não na pontuação.

## Uma variável é uma caixa com etiqueta

Uma **variável** é um espaço com um nome, onde se guarda um valor que pode mudar enquanto o algoritmo é executado. Imagina uma caixa com uma etiqueta. A etiqueta é o nome e nunca muda. Quando entra um valor novo na caixa, o antigo sai.

O nome deve dizer o que a variável guarda. `totalMinutos` é um bom nome, e `aux` não é, porque daqui a uma semana já não te lembras do que lá estava. Os nomes seguem três regras:

- começam por uma letra minúscula;
- não têm espaços, e cada palavra a partir da segunda começa por maiúscula, como em `precoPorUnidade`;
- não têm acentos nem cedilhas.

Nos exercícios que só seguem contas, sem um problema por trás, usam-se nomes curtos, como `a` e `b`.

## Uma constante dá nome a uma regra do problema

Uma **constante** é um valor com nome que não muda durante o algoritmo. Há valores que fazem parte das regras do problema: uma hora tem 60 minutos, e a nota máxima é 20. A constante escreve-se no início do algoritmo, com `const` à frente e o nome em maiúsculas, com um traço baixo entre as palavras:

```text
const MINUTOS_POR_HORA = 60
```

O nome diz o que o número significa, o que um 60 solto no meio de uma conta não diz. E, se a regra mudar, muda-se num sítio só. Um número que é da própria conta, como o 2 de uma média, não precisa de nome.

## O tipo diz que valores uma variável guarda

Cada variável guarda valores de um **tipo**, que decide que valores são possíveis e o que se pode fazer com eles. Nas aulas, usamos quatro:

| Tipo | Guarda | Exemplos |
| --- | --- | --- |
| `int` | números inteiros, sem parte decimal | `0`, `59`, `-3` |
| `float` | números com parte decimal | `2.25`, `-1.75` |
| `string` | texto, entre aspas | `"Ana"`, `"Quantos minutos?"` |
| `bool` | só um de dois valores, verdadeiro ou falso | `true`, `false` |

O tipo decide-se pelo que o valor representa. Um número de pessoas é `int`, porque não existem 2,5 pessoas. Um peso ou uma média é `float`. Um nome é `string`, e a resposta a "a nota é positiva?" é `bool`.

Dentro do pseudocódigo, a parte decimal separa-se com ponto, `2.25`. No texto em português, continua a ser vírgula, 2,25.

O número `12` e o texto `"12"` escrevem-se com os mesmos algarismos, mas são de tipos diferentes. Com o número fazes contas. O texto é só uma sequência de dois caracteres.

<details>
<summary>Para ires mais longe: de onde vêm os nomes dos tipos</summary>

Vêm do inglês, e vais reencontrá-los no Python e no C. `int` vem de *integer*, que quer dizer inteiro. `float` vem de *floating point*, "vírgula flutuante", o nome técnico da forma como o computador guarda estes números. `string` quer dizer "fio" ou "cadeia", aqui uma cadeia de caracteres. `bool` vem de George Boole, o matemático que estudou as contas feitas só com verdadeiro e falso.

</details>

## Atribuição: dar um valor não é perguntar se é igual

**Atribuir** é dar um valor a uma variável. Escreve-se com um sinal de igual, com a variável à esquerda e o valor à direita, e lê-se "horas recebe 2":

```text
int horas = 2
horas = 3
```

A primeira linha é aquela onde a variável nasce: cria a caixa e dá-lhe o primeiro valor. Só nessa linha se escreve o tipo. Daí para baixo, usa-se só o nome, porque o tipo é da caixa e não muda.

A atribuição executa-se em duas fases. A primeira calcula o lado direito, com os valores que as variáveis têm nesse momento. A segunda guarda o resultado na variável da esquerda, e o valor antigo perde-se.

```text
int total = 10
total = total + 5
```

Como equação da matemática, a segunda linha seria impossível. Como atribuição, calcula-se `10 + 5` e guarda-se 15 em `total`. O 10 desapareceu.

Antes de leres a tabela, tenta prever com que valores ficam `a` e `b`. A tabela mostra os valores depois de cada linha.

```text
int a = 4
int b = 9
a = b
b = a
```

| Instrução | a | b |
| --- | ---: | ---: |
| `int a = 4` | 4 | sem valor |
| `int b = 9` | 4 | 9 |
| `a = b` | 9 | 9 |
| `b = a` | 9 | 9 |

As duas ficam com 9, e por isso estas linhas não trocam os valores. Depois de `a = b`, o 4 já não existe em lado nenhum.

Do lado esquerdo está sempre uma única variável. `10 = total` não faz sentido, porque não se guarda um valor dentro do número 10.

**Comparar** é perguntar se dois valores são iguais. Como o `=` já está ocupado, a pergunta escreve-se com dois sinais:

```text
horas == 2
```

A resposta é `true` ou `false`, e `horas` fica como estava, porque perguntar não muda nada. Um `=` manda, e `==` pergunta.

## Operadores aritméticos

As contas escrevem-se com **operadores**, os sinais e as palavras que dizem que conta se faz:

| Operador | O que faz | Exemplo | Resultado |
| --- | --- | --- | ---: |
| `+` | soma | `7 + 2` | `9` |
| `-` | subtração | `7 - 2` | `5` |
| `*` | multiplicação | `7 * 2` | `14` |
| `/` | divisão, com parte decimal | `7 / 2` | `3.5` |
| `div` | divisão inteira: quantas vezes cabe | `7 div 2` | `3` |
| `resto` | o que sobra da divisão inteira | `7 resto 2` | `1` |

A multiplicação escreve-se com asterisco porque o "x" podia ser o nome de uma variável.

`div` e `resto` são as contas de dividir da primária. Com 17 rebuçados para 5 amigos, sem partir nenhum, `17 div 5` dá `3`, o que recebe cada um, e `17 resto 5` dá `2`, o que sobra. Para confirmares, o divisor vezes a divisão inteira, mais o resto, dá o número de partida: 5 vezes 3, mais 2, dá 17.

Usa `div` e `resto` com números inteiros, como pessoas ou minutos, e com um divisor maior do que zero. Usa `/` quando a parte decimal interessa, como numa média.

A ordem das contas é a da matemática. Primeiro fazem-se os parênteses, depois as multiplicações e as divisões, incluindo `div` e `resto`, e no fim as somas e as subtrações. `2 + 3 * 4` dá `14`, e `(2 + 3) * 4` dá `20`. Na dúvida, põe parênteses.

## Entrada e saída: `ler valor` e `Escreve:`

`ler valor` recebe um valor de fora do algoritmo, escrito por uma pessoa. Aparece sempre do lado direito de uma atribuição:

```text
int totalMinutos = ler valor
```

Esta é a linha onde `totalMinutos` nasce, e por isso leva o tipo, que diz também o que se espera da pessoa.

`Escreve:` mostra informação a quem usa o algoritmo. O ecrã é imaginário, porque quem executa o pseudocódigo és tu. Depois dos dois pontos vêm textos e variáveis, separados por vírgulas. O que está entre aspas aparece tal e qual, e o que está sem aspas é o nome de uma variável. Com `horas` a valer 2:

| Instrução | O que aparece no ecrã |
| --- | --- |
| `Escreve: "horas"` | horas |
| `Escreve: horas` | 2 |
| `Escreve: "Passaram ", horas, " horas"` | Passaram 2 horas |

Sem os espaços dentro das aspas, aparecia "Passaram2horas". Antes de cada `ler valor`, escreve-se quase sempre um `Escreve:` com uma pergunta, para a pessoa saber o que tem de escrever.

## Uma função predefinida já vem feita

Uma **função predefinida** é um pedaço de algoritmo que já vem feito, com um nome. Dás-lhe valores entre parênteses, e ela devolve um resultado. A primeira que usas é `abs`, o **valor absoluto**, com este contrato:

- entrada: um número, `int` ou `float`;
- saída: a distância desse número a zero, ou seja, o número sem sinal;
- exemplos: `abs(-7)` dá `7`, `abs(7)` dá `7` e `abs(0)` dá `0`.

Serve quando interessa o tamanho de uma diferença, e não o sentido:

```text
int idadeJoao = 12
int idadeIrma = 15
int diferenca = abs(idadeJoao - idadeIrma)
```

Primeiro calcula-se o que está dentro dos parênteses, que dá `-3`. Depois `abs(-3)` dá `3`, que fica em `diferenca`. Para usar `abs`, não precisas de saber como está feita por dentro: basta o contrato.

## O pseudocódigo das aulas é um vocabulário pequeno

Nas aulas, escrevemos o pseudocódigo sempre desta forma, e noutros livros podes encontrar outra. Uma vírgula fora do sítio não estraga o algoritmo. O que tem de estar certo é a lógica: que passos se dão, por que ordem e com que valores.

Por isso, um algoritmo em frases claras também vale, desde que não deixe dúvidas. Uma boa frase diz que valor se usa, que conta se faz e em que momento. "Divide os minutos por 60 e mostra o resultado" não diz se é a divisão com parte decimal ou só a parte inteira.

A forma assenta em poucas ideias:

- o algoritmo começa na primeira linha e acaba na última, sem linhas de início nem de fim;
- escreve-se uma instrução por linha, pela ordem em que se executam;
- as palavras que começam uma instrução, como `Escreve:`, levam maiúscula, e os tipos, `const`, `div`, `resto` e `ler valor` vão em minúsculas;
- uma variável não tem o nome de uma palavra da forma, como `const`, `int` ou `resto`.

## Numa sequência, a ordem importa

Uma **sequência** são instruções executadas uma depois da outra, de cima para baixo, cada uma exatamente uma vez. Todos os algoritmos deste guia são assim.

Uma instrução só pode usar valores que já existem no momento em que é executada. Se uma conta precisa de um valor lido duas linhas abaixo, usa uma variável que ainda não nasceu. O resultado não faz sentido. E, mesmo com os valores todos prontos, trocar duas linhas pode mudar o resultado.

## Tabela de trace

Uma **tabela de trace** é uma tabela onde se executa um algoritmo à mão, instrução a instrução. Em cada linha, regista-se o valor de todas as variáveis depois dessa instrução. Com variáveis, o estado é o valor de todas elas num dado momento. Cada linha é uma fotografia do estado, e cada instrução é uma ação. *Trace* é uma palavra inglesa que quer dizer "rasto".

Um algoritmo só mostra o que escreve no ecrã, e isso não diz onde está um erro. A tabela mostra o sítio exato onde um valor passou a ser diferente do que devia.

Constrói-se assim:

1. Faz uma coluna para o passo, uma para a instrução, uma para cada variável e uma para o ecrã.
2. No passo 0, escreve "sem valor" em todas as variáveis e "nada" no ecrã.
3. Para cada instrução, acrescenta uma linha, copia os valores das variáveis da linha de cima e muda só o que essa instrução muda.
4. Numa atribuição, muda só a variável à esquerda do `=`. Numa leitura, o ecrã diz o que a pessoa escreve, como "a pessoa escreve 60". Nas outras atribuições, diz "nada".
5. Num `Escreve:`, nenhuma variável muda, e o ecrã mostra o que aparece.
6. As constantes não têm coluna nem passo, porque valem o mesmo do princípio ao fim.

A regra mais importante é executar o que está escrito, e não o que achas que o algoritmo devia fazer. Se preencheres a tabela com o que esperavas, ela concorda sempre contigo e não encontra erro nenhum.

## Exemplo guiado: converter minutos em horas e minutos

### O enunciado

> Um treinador regista o tempo de treino de cada atleta em minutos, mas os atletas preferem ver esse tempo em horas e minutos. Escreve um algoritmo que leia um número de minutos e mostre quantas horas completas e quantos minutos restantes correspondem a esse tempo. Por exemplo, 135 minutos são 2 horas e 15 minutos.

### O contrato

A entrada é o número total de minutos, um inteiro igual ou maior do que zero. As saídas são as horas completas, um inteiro igual ou maior do que zero, e os minutos restantes, um inteiro entre 0 e 59. A restrição é a regra das horas: uma hora tem 60 minutos.

| Minutos | Horas | Minutos restantes | Porque foi escolhido |
| ---: | ---: | ---: | --- |
| 135 | 2 | 15 | O caso do enunciado, um caso normal |
| 0 | 0 | 0 | O valor mais pequeno permitido |
| 59 | 0 | 59 | O maior valor que ainda não chega a uma hora |
| 60 | 1 | 0 | O primeiro valor que completa uma hora |

O 59 e o 60 estão lado a lado porque ficam dos dois lados do sítio onde a resposta muda. Um valor negativo fica fora do contrato, e o guia seguinte trata disso.

### As contas

Quantas horas completas cabem em 135 minutos? É perguntar quantas vezes 60 cabe em 135, e isso é `135 div 60`, que dá `2`. Os minutos que ficam de fora são o que sobra: `135 resto 60` dá `15`. Para confirmar, 60 vezes 2, mais 15, dá 135.

### O algoritmo, aos poucos

O 60 é uma regra do problema, e por isso é a primeira linha. A seguir vêm a pergunta e a leitura, porque as contas precisam do valor lido:

```text
const MINUTOS_POR_HORA = 60
Escreve: "Quantos minutos?"
int totalMinutos = ler valor
```

As duas contas vêm a seguir. As variáveis são `int`, porque o contrato diz que os minutos e as horas completas não têm parte decimal:

```text
int horas = totalMinutos div MINUTOS_POR_HORA
int minutos = totalMinutos resto MINUTOS_POR_HORA
```

`totalMinutos` e `minutos` têm nomes diferentes porque guardam coisas diferentes: o total lido e o que sobra depois de tirar as horas. Falta mostrar o resultado:

```text
Escreve: horas, " h e ", minutos, " min"
```

O algoritmo completo:

```text
const MINUTOS_POR_HORA = 60
Escreve: "Quantos minutos?"
int totalMinutos = ler valor
int horas = totalMinutos div MINUTOS_POR_HORA
int minutos = totalMinutos resto MINUTOS_POR_HORA
Escreve: horas, " h e ", minutos, " min"
```

Em frases claras, o mesmo algoritmo também vale:

1. Pergunta "Quantos minutos?" e guarda o número inteiro que a pessoa escrever como total de minutos.
2. Calcula as horas completas: quantas vezes 60 cabe inteiro no total de minutos.
3. Calcula os minutos restantes: o que sobra dessa divisão.
4. Mostra as horas, seguidas do texto " h e ", dos minutos restantes e do texto " min".

### O trace

Este é o trace do caso em que a pessoa escreve 60:

| Passo | Instrução executada | totalMinutos | horas | minutos | Ecrã |
| ---: | --- | ---: | ---: | ---: | --- |
| 0 | antes de começar | sem valor | sem valor | sem valor | nada |
| 1 | `Escreve: "Quantos minutos?"` | sem valor | sem valor | sem valor | Quantos minutos? |
| 2 | `int totalMinutos = ler valor` | 60 | sem valor | sem valor | a pessoa escreve 60 |
| 3 | `int horas = totalMinutos div MINUTOS_POR_HORA` | 60 | 1 | sem valor | nada |
| 4 | `int minutos = totalMinutos resto MINUTOS_POR_HORA` | 60 | 1 | 0 | nada |
| 5 | `Escreve: horas, " h e ", minutos, " min"` | 60 | 1 | 0 | 1 h e 0 min |

Lê cada linha comparando-a com a de cima, que é o estado antes da instrução. No passo 3, `totalMinutos` continua a valer 60, porque usar uma variável numa conta não a altera.

Nos outros casos do contrato, só mudam os passos 2 a 5. Com 59, `59 div 60` dá 0 e `59 resto 60` dá 59. Com 0, as duas contas dão 0. Com 135, dão 2 e 15.

### Confirmar o contrato

Os exemplos do contrato, com o resultado previsto à mão, servem agora de **casos de teste**. O algoritmo está certo nestes casos se o trace der, em cada um, o que o contrato previu.

| Minutos | Previsto no contrato | O que o trace mostra no ecrã |
| ---: | --- | --- |
| 135 | 2 horas e 15 minutos | 2 h e 15 min |
| 0 | 0 horas e 0 minutos | 0 h e 0 min |
| 59 | 0 horas e 59 minutos | 0 h e 59 min |
| 60 | 1 hora e 0 minutos | 1 h e 0 min |

Os quatro casos coincidem. Se algum não coincidisse, procurava-se no trace a primeira linha onde um valor ficou diferente do esperado.

## Erros frequentes

### Usar uma variável antes da linha onde ela nasce

```text
const MINUTOS_POR_HORA = 60
int horas = totalMinutos div MINUTOS_POR_HORA
int minutos = totalMinutos resto MINUTOS_POR_HORA
Escreve: "Quantos minutos?"
int totalMinutos = ler valor
Escreve: horas, " h e ", minutos, " min"
```

No primeiro passo do trace, a conta usa `totalMinutos`, e a coluna dessa variável diz "sem valor". Antes de escreveres uma conta, pergunta-te de onde vem cada valor que ela usa.

### Fazer uma conta antes de ter todos os dados

```text
float teste1 = ler valor
float media = (teste1 + teste2) / 2
float teste2 = ler valor
```

Na linha da conta, `teste2` ainda não nasceu. Leem-se primeiro todos os dados, e só depois se faz a conta.

### Usar `/` em vez de `div`

Com `/`, 135 minutos dão `2.25`, e é tentador ler "2 horas e 25 minutos". Está errado, porque 2,25 horas são 2 horas e um quarto de hora. Pergunta-te se o resultado pode ter parte decimal.

### Escrever o tipo outra vez

Depois de `int horas = 2`, uma linha como `int horas = horas + 1` parece criar uma segunda caixa. Daí para baixo, escreve-se `horas = horas + 1`.

## Palavras novas deste guia

- Pseudocódigo: texto escrito com um vocabulário pequeno e sempre igual, que nenhum computador executa.
- Variável: um espaço com um nome, onde se guarda um valor que pode mudar.
- Constante: um valor com nome que não muda durante o algoritmo.
- Tipo: o que decide que valores uma variável pode guardar. Nas aulas, `int`, `float`, `string` e `bool`.
- Atribuir: dar um valor a uma variável, com `=`.
- Comparar: perguntar se dois valores são iguais, com `==`.
- Operador: o sinal ou a palavra que diz que conta se faz.
- Função predefinida: um pedaço de algoritmo já feito, que recebe valores e devolve um resultado.
- Valor absoluto: a distância de um número a zero; é o que `abs` devolve.
- Sequência: instruções executadas uma depois da outra, cada uma exatamente uma vez.
- Tabela de trace: uma tabela onde se executa um algoritmo à mão, com o valor das variáveis depois de cada instrução.
- Caso de teste: um exemplo do contrato, com o resultado previsto à mão, que serve para testar o algoritmo.

## O que vem a seguir

No tema seguinte, [Decisões e validação](03-decisoes-e-validacao.md), o algoritmo passa a tomar decisões, por exemplo para recusar uma entrada como -30 minutos.

![Rodapé](../imagens/rodape.png)
