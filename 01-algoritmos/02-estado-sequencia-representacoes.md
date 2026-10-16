![Cabeçalho](../imagens/cabecalho.png)

# Estado, sequência e representações

Módulo Desenvolver algoritmos. Neste guia aprendes a escrever algoritmos em pseudocódigo, com variáveis, constantes, tipos e contas, e a ler o mesmo algoritmo num fluxograma. Aprendes também a acompanhar o que acontece dentro de um algoritmo, instrução a instrução, numa tabela de trace. Lê-se ao teu ritmo, de preferência em mais do que uma vez. Para praticar, há o [laboratório](02-estado-sequencia-representacoes-laboratorio.md) e a [ficha de exercícios](02-estado-sequencia-representacoes-exercicios.md) deste tema.

No guia anterior escreveste passos em português, numerados. Funcionou, mas o português deixa passar ambiguidades sem dar sinal. Neste guia vais aprender duas formas de escrever algoritmos que ajudam a apanhar essas ambiguidades, o pseudocódigo e o fluxograma. Na aula já escreveste as primeiras instruções em pseudocódigo. Este guia arruma essas instruções na forma que usamos nas aulas, a mesma em todos os guias de algoritmos. E explica a razão de cada escolha. Todos os algoritmos deste guia são sequenciais: fazem sempre os mesmos passos, pela mesma ordem. Escolher entre caminhos é o assunto do guia seguinte.

## Neste guia

1. O que vais aprender
2. O que já sabes e vais usar
3. Uma forma de escrever algoritmos
4. Variáveis
5. Constantes
6. Tipos de dados
7. Estado
8. Atribuição: dar um valor não é perguntar se é igual
9. Operadores aritméticos
10. Entrada e saída: `ler valor` e `Escreve:`
11. Funções predefinidas
12. A forma de escrever pseudocódigo nas aulas
13. Sequência
14. Fluxogramas
15. Tabela de trace
16. Exemplo guiado: converter minutos em horas e minutos
17. Erros frequentes
18. Palavras novas deste guia
19. Verificar o que aprendeste
20. O que vem a seguir

## O que vais aprender

No fim deste guia, consegues:

- explicar o que é uma variável, uma constante e um tipo de dados, e escolher o tipo certo para cada valor;
- distinguir dar um valor a uma variável, com `=`, de perguntar se dois valores são iguais, com `==`;
- fazer contas com os operadores aritméticos, incluindo a divisão inteira e o resto, e usar uma função predefinida, como `abs`;
- escrever um algoritmo sequencial completo em pseudocódigo, na forma que usamos nas aulas, ou em frases claras que não deixem dúvidas;
- ler o mesmo algoritmo num fluxograma e, se o professor o indicar, desenhá-lo em papel e numa aplicação de diagramas;
- executar um algoritmo à mão numa tabela de trace, instrução a instrução, comparando o estado antes e depois de cada atribuição;
- confirmar que o pseudocódigo, o fluxograma e o trace dão os mesmos resultados nos mesmos casos de teste.

## O que já sabes e vais usar

- O contrato de entrada e saída: as entradas, as saídas, as restrições e os exemplos, escritos antes de qualquer instrução. Explicado no guia [01 Do enunciado ao problema delimitado](01-do-enunciado-ao-problema.md), secção "O contrato de entrada e saída".
- O estado, a fotografia da situação num dado momento, como (3, 3, esquerda) nos Missionários e Canibais: guia [01](01-do-enunciado-ao-problema.md), secção "Ação e estado".
- A decomposição, que ajuda a decidir que passos o algoritmo tem de dar: guia [01](01-do-enunciado-ao-problema.md), secção "Decomposição".
- Os passos vagos, como "espera um bocado", que cada pessoa executa à sua maneira: guia [01](01-do-enunciado-ao-problema.md), secção "Algoritmo: os passos antes da linguagem".
- Executar à letra o que está escrito, como o robô da sandes: guia [01](01-do-enunciado-ao-problema.md), secção "Programar é dar instruções a quem as cumpre à letra".
- As quatro operações, a divisão com resto e a ordem das operações numa conta, da matemática do ensino básico.

## Uma forma de escrever algoritmos

No guia anterior viste que o português permite frases como "espera um bocado". Cada pessoa executa-as à sua maneira, porque não dizem quanto tempo é um bocado. Uma linguagem de programação, como o C ou o Python, não tem esse problema: cada instrução tem um único significado. Mas tem outro, para quem está a começar. Obriga a respeitar regras de escrita muito rígidas. No C, por exemplo, um ponto e vírgula esquecido impede o programa de funcionar, mesmo que o raciocínio esteja certo.

O **pseudocódigo** fica a meio caminho. É texto, escrito com um vocabulário pequeno e sempre igual, que toda a turma lê da mesma maneira. Não é uma linguagem de programação. Nenhum computador lê o teu pseudocódigo, e por isso não há erros de escrita que o impeçam de funcionar. Serve para escreveres depressa, e sem ambiguidades, o raciocínio que resolve o problema. A tua atenção fica no raciocínio, e não na pontuação.

O **fluxograma** é um desenho do mesmo algoritmo, feito com figuras ligadas por setas. Mostra de relance o caminho que o algoritmo percorre. É o que se costuma usar para explicar um processo a quem não programa.

O mesmo algoritmo escreve-se das duas maneiras. Se as duas versões não disserem exatamente a mesma coisa, pelo menos uma está errada.

## Variáveis

Uma **variável** é um espaço com um nome onde se guarda um valor. Esse valor pode mudar enquanto o algoritmo é executado.

A imagem mais usada é a de uma caixa com uma etiqueta. A etiqueta é o nome e nunca muda. O conteúdo é o valor e pode ser trocado. Quando se guarda um valor novo na caixa, o antigo sai. Uma variável guarda um valor de cada vez, nunca dois.

No dia a dia, o marcador de um jogo de basquetebol funciona assim. Há um espaço com a etiqueta "Casa" e outro com a etiqueta "Fora". As etiquetas ficam o jogo inteiro. Os números lá dentro mudam a cada cesto, e quando mudam, o número anterior desaparece do marcador.

No guia anterior, o estado dos Missionários e Canibais era formado por três valores sem nome, escritos entre parênteses. Com variáveis, passam a ter nome próprio, por exemplo `missionariosEsquerda`, `canibaisEsquerda` e `ladoDoBarco`. Cada travessia muda o valor de algumas delas.

O nome de uma variável deve dizer o que ela guarda. `totalMinutos` é um bom nome. `x`, `aux` ou `numero2` não são, porque daqui a uma semana nem tu te lembras do que lá estava. Nos exercícios de treino que só seguem contas, sem um problema por trás, usam-se nomes curtos, como `a`, `b`, `x` e `y`. Nesta disciplina, os nomes das variáveis seguem estas regras:

- começam por uma letra minúscula;
- não têm espaços, e quando têm várias palavras, cada palavra a partir da segunda começa por maiúscula, como em `totalMinutos` ou `precoPorUnidade`;
- não têm acentos nem cedilhas, porque as linguagens que vais usar a seguir nem sempre os aceitam nos nomes, e é melhor habituares-te desde já.

O erro típico com variáveis é usar uma variável antes da linha onde ela nasce, a primeira que lhe dá um valor. Nesse momento, a caixa ainda nem existe. Perguntar o que está lá dentro não dá nenhuma resposta útil. Vais ver este erro num algoritmo completo em "Erros frequentes", no fim do guia.

## Constantes

Uma **constante** é um valor com nome que não muda durante a execução do algoritmo.

Há valores que fazem parte das regras do problema, e não dos dados. Uma hora tem 60 minutos, uma caixa da biblioteca leva 12 livros, a nota máxima é 20. Podias escrever o número diretamente nas contas, mas dar-lhe um nome traz duas vantagens.

A primeira é que se percebe o que o número significa. `MINUTOS_POR_HORA` diz muito mais do que um 60 solto no meio de uma conta.

A segunda é que, se a regra mudar, muda-se num sítio só. Imagina que a biblioteca passa a usar caixas de 15 livros. Altera-se a linha da constante, e o resto do algoritmo fica igual. Não tens de andar à procura de todos os 12 espalhados pelo texto.

As constantes escrevem-se em maiúsculas, com as palavras separadas por um traço baixo, como `MINUTOS_POR_HORA`. A forma diferente serve para as distinguires à primeira vista das variáveis.

No pseudocódigo, uma constante escreve-se no início do algoritmo, antes da primeira linha que a usa, com a palavra `const` à frente:

```text
const MINUTOS_POR_HORA = 60
```

A palavra `const` é a abreviatura de "constante". Diz a quem lê que este valor fica fixo do princípio ao fim. O sinal `=` quer dizer que o nome `MINUTOS_POR_HORA` fica com o valor 60. A secção "Atribuição: dar um valor não é perguntar se é igual" explica porque é que se escreve assim. As constantes vão para o início porque são regras do problema. Quem lê o algoritmo fica a conhecê-las antes de ver as contas que as usam.

## Tipos de dados

Cada variável guarda valores de um **tipo**. O tipo decide que valores são possíveis e o que se pode fazer com eles. Nas aulas usamos quatro tipos:

| Tipo | Guarda | Exemplos |
| --- | --- | --- |
| `int` | números inteiros, sem parte decimal | `0`, `59`, `-3` |
| `float` | números com parte decimal | `2.25`, `0.5`, `-1.75` |
| `string` | texto, ou seja, sequências de caracteres, entre aspas | `"Ana"`, `"Quantos minutos?"` |
| `bool` | só um de dois valores, verdadeiro ou falso | `true`, `false` |

Os nomes vêm do inglês, a língua em que as linguagens de programação são escritas. Vais reencontrá-los, iguais ou muito parecidos, no C e no Python. Cada um quer dizer isto:

- `int` vem de *integer*, que quer dizer inteiro: um número sem casas decimais, como 12 ou -3.
- `float` vem de *floating point*, "vírgula flutuante": um número com casas decimais, como 2,5. Vírgula flutuante é o nome técnico da forma como o computador guarda estes números.
- `string` quer dizer "fio" ou "cadeia", e aqui é uma cadeia de caracteres, uns atrás dos outros: um texto, como `"Ana"`.
- `bool` vem de George Boole, o matemático: só pode ser verdadeiro ou falso. Boole estudou as contas feitas só com estes dois valores, que se escrevem `true`, verdadeiro, e `false`, falso.

No pseudocódigo escreves sempre estes quatro nomes ingleses, para já estares habituado a eles quando chegares ao C e ao Python.

No pseudocódigo, a parte decimal de um número separa-se com um ponto, `2.25`, tal como nas linguagens de programação. No texto em português continua a escrever-se com vírgula, 2,25. São duas convenções para dois contextos, e não se misturam. Dentro do pseudocódigo, ponto; no texto que escreves à volta, vírgula.

Escolher o tipo é uma decisão com consequências, e decide-se pelo que o valor representa. Um número de minutos, de caixas ou de pessoas é `int`, porque não existem 2,5 pessoas. Um peso ou uma média é `float`. Um nome ou uma mensagem é `string`. A resposta a uma pergunta de sim ou não, como "a nota é positiva?", é `bool`. Vais usar muito o tipo `bool` no guia seguinte, quando o algoritmo tiver de tomar decisões.

A confusão mais frequente é entre o número `12` e o texto `"12"`. No papel escrevem-se com os mesmos dois algarismos. Mas são de tipos diferentes, `int` e `string`, e portam-se de maneira diferente. Com o número podes fazer contas. Com o texto não: é uma sequência de dois caracteres, o 1 e o 2, tal como `"ab"` é uma sequência de duas letras. Juntar o texto `"12"` com o texto `"3"` dá `"123"`, e não 15.

## Estado

No guia anterior, o estado era a fotografia da situação num dado momento. Com variáveis, a definição fica mais precisa. O **estado** de um algoritmo, num dado momento, é o valor de todas as suas variáveis nesse momento.

Cada instrução que muda o valor de uma variável muda o estado. Se quiseres saber o que um algoritmo está a fazer, não precisas de adivinhar. Olhas para o estado antes de uma instrução e para o estado depois, e a diferença é o efeito dessa instrução. É esta a ideia por trás da tabela de trace, que vais aprender mais à frente neste guia.

## Atribuição: dar um valor não é perguntar se é igual

**Atribuir** é dar um valor a uma variável. No pseudocódigo que usamos nas aulas, escreve-se com um sinal de igual, com a variável à esquerda e o valor à direita. Se já existir uma variável chamada `horas`, dar-lhe o valor 2 escreve-se assim:

```text
horas = 2
```

Lê-se "horas recebe 2" ou "horas fica com 2". É uma ordem, e não uma pergunta. A partir deste momento, `horas` vale 2, seja qual for o valor que tinha antes.

Este sinal de igual não quer dizer o mesmo que na matemática. Na matemática, `x = 2` afirma que dois lados são iguais, e podes lê-lo da esquerda para a direita ou da direita para a esquerda. No pseudocódigo, `horas = 2` manda pôr o 2 dentro da caixa `horas`. Só se lê num sentido: o valor da direita vai para a variável da esquerda. O C e o Python, as duas linguagens que vais aprender este ano, escrevem a atribuição com este mesmo sinal. É por isso que o usamos já.

### A linha onde a variável nasce

A primeira vez que uma variável aparece num algoritmo, é aí que ela nasce. É nessa linha que se cria a caixa com a etiqueta e se lhe põe o primeiro valor. Nessa linha, e só nessa, escreve-se o tipo à frente do nome:

```text
int horas = 2
```

Lê-se "cria a variável `horas`, do tipo `int`, e dá-lhe o valor 2". Daí para baixo, a variável já existe, e usa-se só pelo nome, sem o tipo:

```text
horas = 3
```

Porque é que o tipo só se escreve uma vez? Porque o tipo é uma característica da caixa, decidida quando ela é criada, e não muda depois. Escrever `int horas = 3` mais abaixo daria a ideia de que estavas a criar uma segunda caixa com o mesmo nome. Isso deixaria qualquer leitor sem saber de que caixa se fala, e a ti próprio também, daí a uma semana.

E porque é que o tipo aparece na linha onde a variável nasce, e não numa lista no topo do algoritmo? Porque é aí que ele interessa. Quem lê `int horas = 2` fica a saber de uma só vez o nome, o tipo e o primeiro valor. Não tem de andar para cima e para baixo no texto. E porque é também assim que se faz no C, onde se escreve `int horas = 2;`, com um ponto e vírgula no fim. No Python o tipo nem se escreve, mas a variável nasce da mesma maneira, na primeira linha que lhe dá um valor.

Quando o primeiro valor de uma variável é o resultado de uma conta, a conta vai na mesma linha em que ela nasce. No marcador do basquetebol, por exemplo, o total de pontos do jogo nasce assim: `int totalPontos = pontosCasa + pontosFora`.

### Como se executa uma atribuição

A atribuição executa-se sempre em duas fases, por esta ordem. Primeiro calcula-se o lado direito do sinal de igual, usando os valores que as variáveis têm nesse momento. Depois guarda-se o resultado na variável do lado esquerdo, e o valor antigo dessa variável perde-se.

Antes de leres a explicação, tenta prever: com que valor fica `total` depois destas duas linhas?

```text
int total = 10
total = total + 5
```

`total` fica com 15.

Leitura guiada: a primeira linha cria a variável `total` e dá-lhe 10. A segunda linha já não leva o tipo, porque `total` já existe. Se lesses a segunda linha como uma equação da matemática, "total é igual a total mais 5", seria impossível. Nenhum número é igual a ele próprio mais cinco. Lida como atribuição, faz todo o sentido. Calcula-se o lado direito com o valor atual de `total`, que é 10, e dá 15. Guarda-se 15 em `total`. No fim, `total` vale 15, e o 10 desapareceu.

A perda do valor antigo tem consequências, e veem-se melhor com números. Nestas quatro linhas, as duas primeiras criam `a` com 4 e `b` com 9. Antes de leres a tabela, tenta prever: com que valores ficam `a` e `b` no fim?

```text
int a = 4
int b = 9
a = b
b = a
```

A tabela mostra, passo a passo, o valor das duas variáveis depois de cada linha. No passo 0, antes de começar, nenhuma nasceu, e por isso as duas estão "sem valor". Nenhuma destas linhas escreve no ecrã, e por isso a última coluna diz sempre "nada".

| Passo | Instrução executada | a | b | Ecrã |
| ---: | --- | ---: | ---: | --- |
| 0 | antes de começar | sem valor | sem valor | nada |
| 1 | `int a = 4` | 4 | sem valor | nada |
| 2 | `int b = 9` | 4 | 9 | nada |
| 3 | `a = b` | 9 | 9 | nada |
| 4 | `b = a` | 9 | 9 | nada |

No fim, as duas valem 9.

Leitura guiada: no passo 3, `a` recebe o valor de `b` e passa a valer 9. O 4 perdeu-se. No passo 4, `b` recebe o valor atual de `a`, que já é 9. Quem esperava que os valores trocassem de lugar esqueceu-se de que, depois do passo 3, o 4 já não existe em lado nenhum. Pensar no estado antes e depois de cada linha é o que te protege deste tipo de engano. Esta tabela chama-se tabela de trace, e a secção "Tabela de trace" ensina a construí-la com todas as regras.

Do lado esquerdo do sinal de igual está sempre uma única variável, porque é lá que o valor vai ser guardado. `10 = total` e `total + 5 = total` não fazem sentido. Não se pode guardar um valor dentro do número 10, nem dentro de uma conta.

### Perguntar se é igual: dois sinais, `==`

**Comparar** é perguntar se dois valores são iguais, ou se um é maior do que o outro. O resultado de uma comparação é verdadeiro ou falso, ou seja, `true` ou `false`. O sinal `=` sozinho já está ocupado a dar valores. Por isso, a pergunta "é igual?" escreve-se com dois sinais seguidos, `==`:

```text
horas == 2
```

Lê-se "horas é igual a 2?". Antes de continuares, tenta prever a resposta com `horas` a valer 2, e depois com `horas` a valer 5. Com 2, a resposta é `true`. Com 5, é `false`. Em qualquer dos casos, `horas` continua com o valor que tinha, porque perguntar não muda nada.

As comparações, com `==` e com sinais como `>=`, são o assunto do guia seguinte. Por agora, fixa a regra: um `=` manda, dois `==` perguntam. O C e o Python fazem a mesma distinção, com os mesmos sinais. Trocar um pelo outro é dos enganos mais frequentes de quem começa a programar.

## Operadores aritméticos

As contas escrevem-se com **operadores**, os sinais e as palavras que dizem que conta se faz. São os que já conheces da matemática, com duas novidades para trabalhar com números inteiros.

| Operador | O que faz | Exemplo | Resultado |
| --- | --- | --- | ---: |
| `+` | soma | `7 + 2` | `9` |
| `-` | subtração | `7 - 2` | `5` |
| `*` | multiplicação | `7 * 2` | `14` |
| `/` | divisão, com parte decimal | `7 / 2` | `3.5` |
| `div` | divisão inteira: quantas vezes cabe | `7 div 2` | `3` |
| `resto` | o que sobra da divisão inteira | `7 resto 2` | `1` |

A multiplicação escreve-se com asterisco porque o "x" é uma letra e podia ser o nome de uma variável. `div` e `resto` escrevem-se em minúsculas. É assim com todas as palavras que aparecem no meio das contas e das condições, como o `e` e o `ou` do guia seguinte.

`div` e `resto` são as contas de dividir que aprendeste na primária, antes de haver números decimais. Imagina 17 rebuçados para repartir por 5 amigos, sem partir nenhum. Antes de leres a resposta, tenta prever: quantos recebe cada amigo, e quantos sobram?

Cada amigo recebe 3, e sobram 2. Em pseudocódigo, `17 div 5` dá `3`, que é quanto recebe cada um, e `17 resto 5` dá `2`, que é o que sobra. Há uma forma simples de confirmar as duas contas ao mesmo tempo. O divisor vezes a divisão inteira, mais o resto, tem de dar o número de partida. Aqui, 5 vezes 3 mais 2 dá 17.

A diferença entre `/` e `div` muda o resultado. `7 / 2` dá `3.5`, um número com parte decimal, que se guardaria numa variável `float`. `7 div 2` dá `3`, um inteiro, e a parte que não cabe vai para o `resto`. Usa `div` e `resto` quando as quantidades são inteiras e a parte decimal não faz sentido, como em pessoas, caixas ou minutos. Usa `/` quando a parte decimal interessa, como numa média. `div` e `resto` usam-se só com números inteiros e com um divisor maior do que zero.

Noutros livros e noutras linguagens vais encontrar o resto escrito como `MOD` ou como `%`. É a mesma operação com outro nome. Nas aulas, no pseudocódigo, escreve-se `resto`.

As contas seguem a ordem que conheces da matemática. Primeiro o que está entre parênteses. Depois as multiplicações e as divisões, incluindo `div` e `resto`. Por fim, as somas e as subtrações. Entre operações do mesmo nível, faz-se da esquerda para a direita.

Antes de leres o resultado, tenta prever quanto dá `2 + 3 * 4`. Dá `14`, porque a multiplicação se faz primeiro. Com parênteses, `(2 + 3) * 4` dá `20`. Quando tiveres dúvidas sobre a ordem, põe parênteses. Não custam nada e tiram a dúvida a quem ler.

## Entrada e saída: `ler valor` e `Escreve:`

Um algoritmo recebe dados e produz resultados. As entradas e as saídas do contrato têm, no pseudocódigo, uma forma própria de se escrever.

`ler valor` recebe um valor de fora do algoritmo, normalmente escrito por uma pessoa no teclado. Aparece sempre do lado direito de uma atribuição. O valor que a pessoa escrever fica guardado na variável da esquerda:

```text
int totalMinutos = ler valor
```

Lê-se "`totalMinutos` recebe o valor que a pessoa escrever". É uma atribuição como as outras, com uma única diferença: do lado direito, em vez de uma conta, está um valor que vem de fora. Esta é a linha onde `totalMinutos` nasce, e por isso leva o tipo à frente. O tipo diz também que tipo de valor se espera da pessoa, neste caso um número inteiro de minutos.

Se mais abaixo fosse preciso ler outro valor para a mesma variável, escrevia-se sem o tipo, `totalMinutos = ler valor`. O valor antigo perdia-se, como em qualquer atribuição.

`Escreve:` mostra informação a quem está a usar o algoritmo. Depois dos dois pontos vem o que se quer mostrar, que pode ser texto e valores de variáveis, separados por vírgulas. O que está entre aspas aparece tal e qual. O que está sem aspas é o nome de uma variável, e o que aparece é o seu valor.

A diferença entre as duas coisas é uma fonte clássica de erros. Imagina que `horas` vale 2. Antes de leres a tabela, tenta prever o que aparece no ecrã com cada uma destas três instruções.

| Instrução | O que aparece no ecrã |
| --- | --- |
| `Escreve: "horas"` | horas |
| `Escreve: horas` | 2 |
| `Escreve: "Passaram ", horas, " horas"` | Passaram 2 horas |

Repara nos espaços dentro das aspas na última linha. Sem eles, aparecia "Passaram2horas". O algoritmo escreve exatamente o que lhe mandas, incluindo os espaços que te esqueceste de pôr.

Antes de cada `ler valor`, escreve-se quase sempre um `Escreve:` com uma pergunta, para quem está do outro lado saber o que tem de escrever. Um `ler valor` sem pergunta deixa a pessoa a olhar para um ecrã parado. Não sabe que o algoritmo está à espera dela.

## Funções predefinidas

Uma **função predefinida** é um pedaço de algoritmo que já vem feito, com um nome, pronto a usar. Dás-lhe um ou mais valores, entre parênteses, e ela devolve um resultado. Podes usar esse resultado numa conta ou guardá-lo numa variável.

A primeira que vais usar é `abs`, o **valor absoluto**. O nome vem de "absoluto" e escreve-se em minúsculas. O seu contrato é este:

- entrada: um número, `int` ou `float`;
- saída: a distância desse número a zero, ou seja, o mesmo número sem sinal;
- exemplos: `abs(-7)` dá `7`, `abs(7)` dá `7` e `abs(0)` dá `0`.

Onde é que isto serve? Sempre que interessa o tamanho de uma diferença, e não o seu sentido. O João tem 12 anos e a irmã tem 15. A diferença de idades é 3 anos, seja qual for a ordem em que fazes a conta. `12 - 15` dá `-3` e `15 - 12` dá `3`, mas `abs(12 - 15)` e `abs(15 - 12)` dão ambos `3`.

Num algoritmo, escrevia-se assim. Antes de leres a explicação, tenta prever com que valor fica `diferenca`.

```text
int idadeJoao = 12
int idadeIrma = 15
int diferenca = abs(idadeJoao - idadeIrma)
```

`diferenca` fica com 3.

Leitura guiada: na terceira linha, primeiro calcula-se o que está dentro dos parênteses, `12 - 15`, que dá `-3`. Depois aplica-se a função a esse resultado, e `abs(-3)` dá `3`. Por fim, guarda-se o 3 em `diferenca`, que nasce nesta linha e por isso leva o tipo à frente.

Repara na ligação ao guia anterior. Para usar `abs` não precisas de saber como ela está feita por dentro. Também não precisas de saber como funciona uma máquina de venda automática para comprar uma garrafa de água. Chega-te o contrato. Existem outras funções predefinidas, cada uma com o seu contrato, como a raiz quadrada. Quando precisares de uma, o enunciado ou o professor dá-te o nome e o contrato.

## A forma de escrever pseudocódigo nas aulas

Há muitas formas de escrever pseudocódigo, e livros diferentes usam palavras diferentes. Nas aulas usamos sempre a mesma, e é essa que vais encontrar em todos os guias de algoritmos. Se num livro ou num vídeo encontrares outra, não está errada. É outra maneira de escrever a mesma lógica.

Esta forma é um vocabulário pequeno e estável. Serve para escreveres e leres algoritmos depressa, e para toda a turma perceber o mesmo quando lê a mesma linha. Não há nela regras que deem erro. Podes esquecer-te dos dois pontos de um `Escreve:`, ou escrever com maiúscula uma palavra que costuma ir em minúscula. O algoritmo continua a dizer o mesmo, e continua certo se a lógica estiver certa. O que tem de estar certo é a lógica: que passos se dão, por que ordem e com que valores.

Por isso, um algoritmo escrito em frases claras, em português, também é válido, desde que não deixe dúvidas a quem o executa. As dúvidas costumam aparecer em três sítios, e uma boa frase responde aos três:

- quanto: que valor exatamente, que conta exatamente;
- quando: em que momento e por que ordem;
- o que acontece se não der: o que fazer quando um valor não serve, uma pergunta que vai ganhar importância no guia seguinte.

"Divide os minutos por 60 e mostra o resultado" deixa uma dúvida sobre o quanto. É a divisão com parte decimal, que dá `2.25` para 135 minutos, ou só a parte inteira, que dá 2? "Calcula quantas vezes 60 cabe inteiro nos minutos e mostra esse número como as horas" não deixa nenhuma. Nesta fase, o que importa é que a lógica esteja lá. O pseudocódigo é uma ajuda para a escrever sem ambiguidades. No exemplo guiado vais ver o mesmo algoritmo escrito das duas maneiras.

A forma que usamos assenta em poucas ideias, que já viste nas secções anteriores:

- O algoritmo começa na primeira linha e acaba na última. Não tem cabeçalho com o nome do algoritmo, nem palavras a marcar onde começa e onde acaba. Quando for preciso dar-lhe um nome, o nome vai no título ou na frase que o apresenta, como "o algoritmo que converte minutos".
- As constantes escrevem-se no início, antes de serem usadas, com `const` à frente.
- Cada variável nasce na linha onde aparece pela primeira vez, com o tipo à frente, e daí para baixo usa-se só pelo nome.
- Um `=` dá um valor a uma variável. Dois `==` perguntam se dois valores são iguais.
- Escreve-se uma instrução por linha, pela ordem em que são executadas.

Há uma última ideia que neste guia ainda não se vê, mas que convém conheceres já. O recuo de uma linha em relação à margem, a que se chama **indentação**, mostra o que está dentro de quê. Escreve-se com quatro espaços por cada nível. Nos algoritmos deste guia, todas as linhas começam encostadas à margem, porque nenhuma instrução está dentro de outra. Todas se executam, uma depois da outra.

No guia seguinte vais escrever instruções que só se executam em certos casos, e são essas que vão quatro espaços mais para dentro. A indentação passa então a ser a única marca de onde começa e onde acaba um conjunto de instruções. Mudar uma linha de margem passa a mudar o que o algoritmo faz. O Python, que vais aprender este ano, funciona exatamente assim.

A tabela seguinte reúne toda a forma. As três últimas linhas pertencem ao guia seguinte e estão marcadas como tal, para teres tudo num só sítio.

| Elemento | Como se escreve | Exemplo |
| --- | --- | --- |
| Início e fim | não se escrevem: o algoritmo começa na primeira linha e acaba na última | a primeira linha do exemplo guiado é `const MINUTOS_POR_HORA = 60` |
| Constante | `const`, o nome em maiúsculas, `=` e o valor, no início do algoritmo | `const MINUTOS_POR_HORA = 60` |
| Variável, na linha onde nasce | o tipo, o nome, `=` e o primeiro valor | `int horas = 0` |
| Variável, nas linhas seguintes | só o nome, sem o tipo | `horas = horas + 1` |
| Tipos | `int`, `float`, `string`, `bool` | `string nome = "Ana"` |
| Valores lógicos | `true`, `false` | `bool terminou = false` |
| Atribuição | variável, `=`, expressão | `int horas = totalMinutos div MINUTOS_POR_HORA` |
| Entrada | `ler valor`, do lado direito de uma atribuição | `int totalMinutos = ler valor` |
| Saída | `Escreve:`, seguido de texto e variáveis separados por vírgulas | `Escreve: "Horas: ", horas` |
| Aritmética | `+`, `-`, `*`, `/`, `div`, `resto`, parênteses | `(a + b) / 2` |
| Função predefinida | nome em minúsculas e valor entre parênteses | `abs(a - b)` |
| Indentação | quatro espaços por nível, para mostrar o que está dentro de quê | neste guia não há nada dentro de nada, e todas as linhas começam na margem |
| Comparações (guia seguinte) | `==`, `!=`, `<`, `<=`, `>`, `>=` | `nota >= 10` |
| Operadores lógicos (guia seguinte) | `e`, `ou`, `não` | `nota < 0 ou nota > 20` |
| Seleção (guia seguinte) | `Se` condição, `Senão se` condição, `Senão`, com as instruções de cada caso indentadas por baixo | ver o guia seguinte |

Na linha da atribuição, uma **expressão** é o que está à direita do `=`: um valor, uma variável ou uma conta.

As palavras que começam uma instrução, como `Escreve:` e, no guia seguinte, `Se` e `Senão`, escrevem-se com maiúscula inicial. Assim veem-se logo no princípio da linha. Os tipos, os operadores, como `div`, `resto`, `e` e `ou`, e `ler valor` escrevem-se em minúsculas. Os nomes das variáveis seguem as regras da secção "Variáveis", e os das constantes vão em maiúsculas, com traço baixo. Nada disto é para decorar como uma lei. É para que todos escrevam da mesma maneira, e cada um leia depressa o que os outros escreveram.

Evita dar a uma variável o nome de uma destas palavras. Uma variável chamada `const` ou `int` deixaria quem lê sem saber se a palavra é uma variável ou parte da forma. Nas linguagens de programação, estas palavras chamam-se **palavras reservadas**. No C, `int` e `const` são palavras reservadas, proibidas como nomes. O Python tem as suas, que vais conhecer quando lá chegares.

## Sequência

Uma **estrutura sequencial** é uma sequência de instruções executadas uma depois da outra, de cima para baixo. Cada uma executa-se exatamente uma vez, sem saltar nenhuma e sem voltar atrás.

É a forma mais simples de algoritmo, e é a única que usas neste guia. Uma receita em que todos os passos se fazem sempre, pela mesma ordem, é uma sequência. Uma receita com "se a massa estiver muito mole, junta mais farinha" já não é. Há um passo que umas vezes se faz e outras não. Esse tipo de instrução é o assunto do guia seguinte.

Numa sequência, a ordem importa. Uma instrução só pode usar valores que já existem no momento em que é executada. Imagina uma conta que precisa de um valor que só é lido duas linhas abaixo. A conta é feita com uma variável que ainda não nasceu e por isso não tem valor, e o resultado não faz sentido. Parece óbvio escrito assim, e é um dos erros mais frequentes de quem começa.

## Fluxogramas

Um fluxograma representa um algoritmo com figuras ligadas por setas. Cada figura tem uma forma que diz que tipo de instrução é, e as setas dizem a ordem.

| Figura | Para que serve | Como aparece nestes guias |
| --- | --- | --- |
| Oval | Início e fim do algoritmo | `( Início )` e `( Fim )` |
| Paralelogramo | Entrada e saída de dados: `ler valor` e `Escreve:` | `/ int totalMinutos = ler valor /` |
| Retângulo | Processamento: atribuições e contas | `[ int horas = totalMinutos div MINUTOS_POR_HORA ]` |
| Losango | Decisão: o caminho divide-se em dois | uma figura de três linhas com pontas à esquerda e à direita, mostrada abaixo |
| Seta | O sentido do percurso | linhas verticais terminadas em `↓` |

Estes guias são ficheiros de texto e não têm desenhos. Por isso, cada figura aparece representada por caracteres: parênteses curvos para o oval, barras inclinadas para o paralelogramo e parênteses retos para o retângulo. O losango ocupa três linhas, para se distinguir bem dos sinais de comparação que muitas vezes vão lá dentro. A condição termina sempre com um ponto de interrogação:

```text
         /                  \
        <     condição ?     >
         \                  /
```

Nas decisões, cada saída do losango leva escrito `Sim` ou `Não`, conforme a condição seja verdadeira ou falsa. Quando desenhares no papel ou na aplicação de diagramas, usa as figuras verdadeiras.

Repara que uma linha com `ler valor` vai num paralelogramo, e não num retângulo, apesar de ser escrita como uma atribuição. O que decide a figura é o que a linha faz. Se recebe um valor de fora, é entrada, e a entrada desenha-se no paralelogramo.

O fluxograma tem um oval de início e um oval de fim, e o pseudocódigo não tem nenhuma palavra para isso. No pseudocódigo não fazem falta, porque se lê de cima para baixo e o algoritmo começa na primeira linha e acaba na última. Num desenho, as figuras podem estar espalhadas pela folha, e os ovais mostram onde se entra e por onde se sai. Há sempre um só oval de fim. A partir do guia seguinte, o percurso pode dividir-se em caminhos diferentes, mas os caminhos voltam a juntar-se antes do fim.

Um fluxograma bem feito cumpre sempre estas regras:

- tem um único início;
- tem um único fim;
- todas as figuras estão ligadas por setas, e nenhuma seta fica pendurada sem destino;
- cada figura tem uma só instrução, escrita da mesma maneira que no pseudocódigo.

Neste guia só vais usar o oval, o paralelogramo e o retângulo, ligados em linha reta, porque os algoritmos sequenciais nunca escolhem entre dois caminhos. O losango fica apresentado porque faz parte da simbologia, e entra em uso no guia seguinte.

Nesta disciplina, os fluxogramas são para saberes o que são e como se leem. Tens de saber o que quer dizer cada figura e como se segue o caminho com o dedo. E tens de saber comparar um fluxograma com o pseudocódigo. Desenhar fluxogramas, no papel ou numa aplicação, é uma parte opcional, que só fazes quando o professor o indicar. O [laboratório deste tema](02-estado-sequencia-representacoes-laboratorio.md) é essa parte opcional. Ensina, passo a passo, a desenhar fluxogramas no diagrams.net, uma aplicação que se usa no browser, sem criar conta.

## Tabela de trace

Uma **tabela de trace** é uma tabela onde se executa um algoritmo à mão, instrução a instrução. Em cada linha, regista-se o valor de todas as variáveis depois dessa instrução. A palavra *trace* é inglesa e quer dizer "rasto". Em inglês, a tabela chama-se *trace table*. Vais ouvir muitas vezes dizer apenas "fazer o trace".

Serve para veres o algoritmo por dentro. Um algoritmo só mostra o que escreve no ecrã, e quando o resultado está errado, isso não diz onde está o erro. O trace mostra o estado depois de cada instrução. Por isso, mostra o sítio exato onde um valor passou a ser diferente do que devia.

Uma tabela de trace constrói-se assim:

1. Faz uma coluna para o número do passo, uma para a instrução executada, uma para cada variável e uma para o que aparece no ecrã.
2. Na primeira linha, antes de qualquer instrução, escreve "sem valor" em todas as variáveis, porque nenhuma nasceu ainda, e "nada" no ecrã. Cada variável fica "sem valor" até ao passo da linha onde nasce.
3. Para cada instrução, pela ordem em que é executada, acrescenta uma linha. Copia os valores da linha de cima e muda só o que essa instrução muda.
4. Numa atribuição, incluindo as que usam `ler valor`, muda só a coluna da variável que está à esquerda do `=`. As outras ficam iguais. Na coluna do ecrã, numa leitura escreve-se o que a pessoa escreve, como "a pessoa escreve 60", e numa conta escreve-se "nada".
5. Num `Escreve:`, nenhuma variável muda. Escreve na coluna do ecrã exatamente o que aparece, com os valores que as variáveis têm nesse momento.
6. As constantes não têm coluna nem passo. A linha do `const` dá nome a uma regra do problema, que vale o mesmo do princípio ao fim. Por isso, não muda nada no estado.

Há uma forma simples de ler uma tabela destas. O estado antes de uma instrução está na linha de cima, e o estado depois está na própria linha. Comparar as duas linhas mostra o efeito da instrução.

A regra mais importante do trace é executar o que está escrito, e não o que achas que o algoritmo devia fazer. Se preencheres a tabela com os valores que esperavas, ela concorda sempre contigo e não encontra erro nenhum. O trace só serve se fores tão literal como o robô da sandes do guia anterior.

## Exemplo guiado: converter minutos em horas e minutos

### Passo 1: o enunciado

> Um treinador regista o tempo de treino de cada atleta em minutos, mas os atletas preferem ver esse tempo em horas e minutos. Escreve um algoritmo que leia um número de minutos e mostre quantas horas completas e quantos minutos restantes correspondem a esse tempo. Por exemplo, 135 minutos são 2 horas e 15 minutos.

### Passo 2: o contrato

A entrada é o número total de minutos, um inteiro igual ou maior do que zero.

Há duas saídas. A primeira é o número de horas completas, um inteiro igual ou maior do que zero. A segunda é o número de minutos restantes, um inteiro entre 0 e 59. Os minutos restantes nunca podem chegar a 60, porque 60 minutos já fazem mais uma hora completa.

A restrição do problema é a regra das horas: uma hora tem 60 minutos. É um valor fixo, que vai ser uma constante.

Os exemplos concretos calculam-se à mão, antes de haver algoritmo. Estes quatro foram escolhidos de propósito:

| Minutos | Horas | Minutos restantes | Porque é que este caso foi escolhido |
| ---: | ---: | ---: | --- |
| 135 | 2 | 15 | O caso do enunciado, um caso normal |
| 0 | 0 | 0 | O valor mais pequeno permitido |
| 59 | 0 | 59 | O maior valor que ainda não chega a uma hora |
| 60 | 1 | 0 | O primeiro valor que completa uma hora |

Os casos 59 e 60 estão lado a lado de propósito. São os dois lados do sítio onde a resposta muda de comportamento. Com 59 ainda não há nenhuma hora completa, e com 60 já há uma. Se o algoritmo tiver um erro nessa passagem, estes dois casos apanham-no. O 0 verifica que o algoritmo se porta bem quando não há nada para converter.

O contrato diz que a entrada é igual ou maior do que zero, e por isso um valor negativo fica fora deste problema. O que fazer quando alguém escreve um valor fora do contrato é o assunto do guia seguinte.

### Passo 3: decompor e pensar nas contas

A decomposição é curta: ler os minutos, calcular as horas completas, calcular os minutos restantes, mostrar o resultado.

As contas merecem mais atenção. Pensa no caso de 135 minutos. Quantas horas completas cabem em 135 minutos? É perguntar quantas vezes 60 cabe em 135, sem partir nenhuma hora. Cabe 2 vezes, que dão 120 minutos. É exatamente a divisão inteira: `135 div 60` dá `2`.

E quantos minutos ficam de fora dessas 2 horas? O que sobra: 135 menos 120, que dá 15. É exatamente o resto: `135 resto 60` dá `15`.

Confirma com a verificação da secção dos operadores: 60 vezes 2, mais 15, dá 135. As duas contas estão certas.

### Passo 4: o pseudocódigo

Este é o algoritmo que converte minutos, na forma que usamos nas aulas:

```text
const MINUTOS_POR_HORA = 60
Escreve: "Quantos minutos?"
int totalMinutos = ler valor
int horas = totalMinutos div MINUTOS_POR_HORA
int minutos = totalMinutos resto MINUTOS_POR_HORA
Escreve: horas, " h e ", minutos, " min"
```

Cada decisão deste pseudocódigo tem uma razão:

1. `MINUTOS_POR_HORA` é uma constante porque o 60 é uma regra do problema, e não um dado que mude de atleta para atleta. Assim, cada conta diz o que está a fazer: dividir pelos minutos que tem uma hora. Vai na primeira linha, com `const`, antes das contas que a usam.
2. As três variáveis são do tipo `int`, porque minutos e horas completas não têm parte decimal. Foi o contrato que o decidiu. Cada uma leva o tipo na linha onde nasce: `totalMinutos` na linha da leitura, `horas` e `minutos` nas contas que lhes dão o primeiro valor.
3. `totalMinutos` e `minutos` têm nomes diferentes porque guardam coisas diferentes: o total que foi lido e o que sobra depois de tirar as horas. Se as duas se chamassem `minutos`, não havia forma de as distinguir.
4. O `Escreve:` com a pergunta vem antes do `ler valor`, para quem usa o algoritmo saber o que tem de escrever.
5. As duas contas vêm depois da leitura, porque ambas precisam do valor de `totalMinutos`, que só existe a partir da linha onde nasce.
6. O último `Escreve:` junta valores e texto. Os espaços dentro das aspas estão lá para o resultado aparecer como "2 h e 15 min", e não como "2h e15min".
7. Todas as linhas começam encostadas à margem, sem indentação, porque o algoritmo é uma sequência. Nenhuma instrução está dentro de outra, e todas se executam uma vez, de cima para baixo.

O mesmo algoritmo também se pode escrever em frases claras, como os passos numerados do guia anterior, e continua a ser válido:

1. Pergunta "Quantos minutos?" e guarda o número inteiro que a pessoa escrever como total de minutos.
2. Calcula as horas completas: quantas vezes 60 cabe inteiro no total de minutos, sem parte decimal.
3. Calcula os minutos restantes: o que sobra dessa divisão.
4. Mostra as horas, seguidas do texto " h e ", dos minutos restantes e do texto " min".

Cada frase diz que valor se usa, que conta se faz e em que momento, e por isso não deixa dúvidas a quem a executa. Compara com a frase vaga da secção "A forma de escrever pseudocódigo nas aulas". "Divide os minutos por 60 e mostra o resultado" não dizia que divisão era. As frases e o pseudocódigo têm a mesma lógica, passo a passo. O pseudocódigo diz o mesmo com menos palavras, e com o tempo vais achá-lo mais rápido de escrever e de ler. Mas se, a resolver um exercício, souberes a lógica e não te lembrares da forma, escreve as frases. Nesta fase, o que conta é a lógica.

### Passo 5: o fluxograma

O mesmo algoritmo, desenhado:

```text
                      ( Início )
                           |
                           ↓
            / Escreve: "Quantos minutos?" /
                           |
                           ↓
           / int totalMinutos = ler valor /
                           |
                           ↓
   [ int horas = totalMinutos div MINUTOS_POR_HORA ]
                           |
                           ↓
 [ int minutos = totalMinutos resto MINUTOS_POR_HORA ]
                           |
                           ↓
     / Escreve: horas, " h e ", minutos, " min" /
                           |
                           ↓
                        ( Fim )
```

Segue o percurso com o dedo, de cima para baixo. Começa no oval de início e passa pelos dois paralelogramos da pergunta e da leitura. Faz as duas contas nos retângulos, mostra o resultado noutro paralelogramo e termina no oval de fim. É uma linha única, sem bifurcações, e é isso que significa uma estrutura sequencial.

Agora compara figura a figura com o pseudocódigo. A cada linha do pseudocódigo corresponde uma figura, pela mesma ordem e com o mesmo texto, incluindo o tipo nas linhas onde as variáveis nascem. Há uma exceção: a linha `const MINUTOS_POR_HORA = 60` não tem figura. O fluxograma desenha o caminho que a execução percorre, passo a passo, e a constante não é um passo desse caminho. É uma regra do problema, que vale o mesmo em todas as figuras, do início ao fim. As linhas onde as variáveis nascem têm figura, porque fazem alguma coisa: recebem um valor de fora ou fazem uma conta.

### Passo 6: o trace, linha a linha

Vais fazer o trace dos três casos do contrato que não são o caso normal. São o 60 e o 59, que ficam dos dois lados do sítio onde a resposta muda, e o 0, o valor mais pequeno permitido. A constante não tem coluna nem passo, porque vale 60 do princípio ao fim e nunca muda. O passo 1 é, por isso, a primeira linha depois do `const`.

Antes de veres cada tabela, tenta prever o que aparece no ecrã no fim. O contrato do passo 2 já te dá a resposta que devias encontrar.

Primeiro caso: a pessoa escreve 60.

| Passo | Instrução executada | totalMinutos | horas | minutos | Ecrã |
| ---: | --- | ---: | ---: | ---: | --- |
| 0 | antes de começar | sem valor | sem valor | sem valor | nada |
| 1 | `Escreve: "Quantos minutos?"` | sem valor | sem valor | sem valor | Quantos minutos? |
| 2 | `int totalMinutos = ler valor` | 60 | sem valor | sem valor | a pessoa escreve 60 |
| 3 | `int horas = totalMinutos div MINUTOS_POR_HORA` | 60 | 1 | sem valor | nada |
| 4 | `int minutos = totalMinutos resto MINUTOS_POR_HORA` | 60 | 1 | 0 | nada |
| 5 | `Escreve: horas, " h e ", minutos, " min"` | 60 | 1 | 0 | 1 h e 0 min |

Lê a tabela comparando cada linha com a de cima, que é o estado antes da instrução.

No passo 1 nenhuma variável muda, porque `Escreve:` não mexe no estado. Só aparece a pergunta no ecrã.

No passo 2, `totalMinutos` nasce e passa de "sem valor" para 60. É a única coluna que muda, porque `ler valor` só guarda o valor na variável que está à esquerda do `=`.

No passo 3 calcula-se o lado direito com o valor que `totalMinutos` tem nesse momento: `60 div 60`. O 60 cabe uma vez em 60, e por isso dá 1. Esse 1 é guardado em `horas`, que nasce neste passo e passa de "sem valor" para 1. `totalMinutos` continua a valer 60, porque usar o valor de uma variável numa conta não o altera.

No passo 4 calcula-se `60 resto 60`. Depois de tirar uma hora de 60 minutos a 60 minutos, não sobra nada, e por isso dá 0. `minutos` nasce e passa de "sem valor" para 0.

No passo 5 nenhuma variável muda, e aparece no ecrã o resultado, com os valores que as variáveis têm nesse momento.

Segundo caso: a pessoa escreve 59.

| Passo | Instrução executada | totalMinutos | horas | minutos | Ecrã |
| ---: | --- | ---: | ---: | ---: | --- |
| 0 | antes de começar | sem valor | sem valor | sem valor | nada |
| 1 | `Escreve: "Quantos minutos?"` | sem valor | sem valor | sem valor | Quantos minutos? |
| 2 | `int totalMinutos = ler valor` | 59 | sem valor | sem valor | a pessoa escreve 59 |
| 3 | `int horas = totalMinutos div MINUTOS_POR_HORA` | 59 | 0 | sem valor | nada |
| 4 | `int minutos = totalMinutos resto MINUTOS_POR_HORA` | 59 | 0 | 59 | nada |
| 5 | `Escreve: horas, " h e ", minutos, " min"` | 59 | 0 | 59 | 0 h e 59 min |

A diferença para o primeiro caso está toda nos passos 3 e 4. O 60 não cabe nenhuma vez em 59, e por isso `59 div 60` dá 0. Como não se tirou nenhuma hora, sobram os 59 minutos inteiros, e `59 resto 60` dá 59. Os minutos restantes ficaram em 59, o maior valor que o contrato permite, e não passaram de lá.

Terceiro caso: a pessoa escreve 0.

| Passo | Instrução executada | totalMinutos | horas | minutos | Ecrã |
| ---: | --- | ---: | ---: | ---: | --- |
| 0 | antes de começar | sem valor | sem valor | sem valor | nada |
| 1 | `Escreve: "Quantos minutos?"` | sem valor | sem valor | sem valor | Quantos minutos? |
| 2 | `int totalMinutos = ler valor` | 0 | sem valor | sem valor | a pessoa escreve 0 |
| 3 | `int horas = totalMinutos div MINUTOS_POR_HORA` | 0 | 0 | sem valor | nada |
| 4 | `int minutos = totalMinutos resto MINUTOS_POR_HORA` | 0 | 0 | 0 | nada |
| 5 | `Escreve: horas, " h e ", minutos, " min"` | 0 | 0 | 0 | 0 h e 0 min |

O 60 não cabe nenhuma vez em 0, e não sobra nada. O algoritmo não precisa de nenhum cuidado especial para o zero, porque as duas contas tratam-no sozinhas. Foi por isso que valeu a pena testá-lo. Nem sempre é assim, e há algoritmos que falham precisamente no zero.

Se fizeres também o trace de 135, o caso do enunciado, os passos 3 e 4 dão 2 e 15. O ecrã mostra "2 h e 15 min".

### Passo 7: confirmar que as três representações concordam

Tens agora três representações do mesmo algoritmo: o pseudocódigo, o fluxograma e o trace. Os exemplos do contrato, cada um com o resultado previsto à mão, servem agora para testar o algoritmo, e por isso chamam-se **casos de teste**. As três representações estão certas se derem os mesmos resultados nos mesmos casos de teste. E esses resultados têm de ser os que o contrato previu à mão no passo 2.

| Minutos | Previsto no contrato | Resultado do trace |
| ---: | --- | --- |
| 0 | 0 horas e 0 minutos | 0 h e 0 min |
| 59 | 0 horas e 59 minutos | 0 h e 59 min |
| 60 | 1 hora e 0 minutos | 1 h e 0 min |
| 135 | 2 horas e 15 minutos | 2 h e 15 min |

Os quatro casos coincidem. O fluxograma tem as mesmas instruções pela mesma ordem que o pseudocódigo. Por isso, percorrê-lo com o dedo, com os mesmos valores, produz as mesmas linhas de trace. Se algum caso não coincidisse, o passo seguinte seria procurar no trace a primeira linha onde um valor ficou diferente do esperado.

### Passo 8: desenhar o fluxograma na aplicação de diagramas (opcional)

Este passo é opcional. Só o fazes quando o professor o indicar, e o [laboratório deste tema](02-estado-sequencia-representacoes-laboratorio.md) guia-te nele, clique a clique. Depois de desenhares o fluxograma em papel, reconstrói-lo numa aplicação de diagramas no computador, a que o professor indicar na aula. O processo é o mesmo em qualquer aplicação:

1. Cria um diagrama novo e procura a biblioteca de figuras de fluxograma. Tem sempre o oval, o paralelogramo, o retângulo e o losango.
2. Coloca as figuras de cima para baixo, pela ordem do papel, uma instrução por figura, com o texto escrito exatamente como no pseudocódigo. A linha do `const` fica de fora, tal como no papel.
3. Liga as figuras com setas, sempre no sentido da execução. Confirma que cada seta sai de uma figura e chega a outra, sem pontas soltas.
4. Percorre o diagrama com o dedo no ecrã e compara-o, figura a figura, com o pseudocódigo.
5. Guarda o ficheiro da aplicação e exporta o diagrama como imagem ou como PDF. Dá ao ficheiro um nome que diga o que ele contém, em minúsculas, com hífenes e sem acentos nem espaços, como `fluxograma-converter-minutos.png`.

O desenho em papel vem primeiro de propósito. No papel pensas no algoritmo, e na aplicação tratas da apresentação. Se começares pela aplicação, a tua atenção vai para o tamanho das caixas e para o alinhamento das setas. O algoritmo fica para segundo plano.

## Erros frequentes

### Usar uma variável antes da linha onde ela nasce

Imagina que alguém escreveu o algoritmo dos minutos com as contas antes da leitura:

```text
const MINUTOS_POR_HORA = 60
int horas = totalMinutos div MINUTOS_POR_HORA
int minutos = totalMinutos resto MINUTOS_POR_HORA
Escreve: "Quantos minutos?"
int totalMinutos = ler valor
Escreve: horas, " h e ", minutos, " min"
```

O que se vê: lido à pressa, parece ter tudo. O trace mostra o problema logo no primeiro passo. A conta de `horas` usa `totalMinutos`, e nesse momento a coluna de `totalMinutos` diz "sem valor". A conta está a ser feita com uma caixa que ainda nem existe.

Porque acontece: o valor escrito pela pessoa só chega na linha do `ler valor`, quando as duas contas já foram feitas. Depois disso, não é usado em mais nenhuma conta até ao fim. A forma que usamos ajuda a ver este erro mesmo antes do trace. `totalMinutos` nasce na linha do `int totalMinutos = ler valor`, que é a única com o tipo à frente. Qualquer linha acima dela que use `totalMinutos` está a usar uma variável que ainda não nasceu.

Como se evita: antes de escreveres uma conta, pergunta-te de onde vem cada valor que ela usa. Tem de vir de uma leitura ou de uma atribuição que está acima dela.

### Fazer uma conta antes de ter todos os dados

É um parente do erro anterior, e aparece quando o algoritmo lê mais do que um valor. Vê este bocado de um algoritmo que devia calcular a média de dois testes:

```text
float teste1 = ler valor
float media = (teste1 + teste2) / 2
float teste2 = ler valor
```

As três variáveis são `float` porque as notas dos testes podem ter décimas, e a média também.

O que se vê: a conta está no sítio certo em relação ao primeiro teste e no sítio errado em relação ao segundo. No trace, a coluna de `teste2` diz "sem valor" na linha da conta, e só muda na linha seguinte, quando já é tarde.

Porque acontece: no momento da conta, `teste2` ainda não nasceu e não tem valor. Por isso, a média é calculada com um dado que falta.

Como se evita: numa sequência, leem-se primeiro todos os dados de que a conta precisa, e só depois se faz a conta. Uma boa regra é agrupar as leituras no início do algoritmo.

### Usar `/` em vez de `div`

O que se vê: com `int horas = totalMinutos / MINUTOS_POR_HORA`, o caso de 135 minutos dá `2.25`. É tentador ler isto como "2 horas e 25 minutos", e está errado.

Porque acontece: 2,25 horas são 2 horas e um quarto de hora, ou seja, 2 horas e 15 minutos. A parte decimal de um número de horas não são minutos, são frações de hora. Além disso, a própria linha contradiz-se. O `int` à frente de `horas` promete um número inteiro, que é o que o contrato pede. Mas a conta com `/` dá `2.25`, um número com parte decimal.

Como se evita: pergunta-te se o resultado pode ter parte decimal. Horas completas não podem, e por isso a conta certa é `div`.

### Confundir texto com variável no `Escreve:`

O que se vê: um ecrã com palavras onde deviam estar números, ou com números sem nenhuma explicação à volta.

Porque acontece: `Escreve: "horas"` mostra a palavra horas, e `Escreve: horas` mostra o valor da variável, por exemplo 2. Quem troca uma pela outra mostra o que não queria.

Como se evita: para cada pedaço do `Escreve:`, pergunta-te se queres o texto tal e qual, entre aspas, ou o valor de uma variável.

### Trocar `=` por `==`, ou escrever a atribuição ao contrário

O que se vê: `horas == totalMinutos div 60` pergunta se `horas` é igual à conta. Não guarda nada, e `horas` fica com o valor que tinha. `totalMinutos div 60 = horas` tenta guardar um valor dentro de uma conta, o que não faz sentido.

Porque acontece: na matemática, o sinal de igual lê-se nos dois sentidos e serve para afirmar que dois lados são iguais. No pseudocódigo, um sinal manda guardar e dois sinais perguntam.

Como se evita: para dar um valor usa-se um só sinal, `horas = totalMinutos div 60`. Na atribuição, a variável que recebe o valor está sempre sozinha do lado esquerdo do `=`. O valor vai sempre da direita para a esquerda.

### Escrever o tipo outra vez

O que se vê: depois de `int horas = 2`, uma linha mais abaixo como `int horas = horas + 1` volta a escrever o tipo. Parece criar uma segunda variável `horas`, e quem lê fica sem saber se é a mesma caixa ou outra nova.

Porque acontece: escreve-se o tipo por hábito, sempre que se usa a variável.

Como se evita: o tipo só se escreve na linha onde a variável nasce. Daí para baixo escreve-se `horas = horas + 1`.

### Preencher o trace com o que se esperava

O que se vê: quem já sabe que 60 minutos são 1 hora é tentado a escrever 1 na coluna das horas. Não faz a conta que está escrita. Se a instrução estiver errada, o trace fica certo e o algoritmo continua errado.

Porque acontece: é mais rápido escrever o que já se sabe do que fazer a conta da linha.

Como se evita: faz sempre a conta que está escrita, com os valores que estão na linha de cima.

### Fluxograma que não corresponde ao pseudocódigo

O que se vê: um destes erros, ou mais do que um:

- uma figura com a forma errada, como uma linha com `ler valor` dentro de um retângulo;
- uma instrução que existe no pseudocódigo e falta no desenho;
- uma seta que não chega a lado nenhum.

Porque acontece: desenha-se figura a figura, à pressa, sem voltar a comparar o desenho com o pseudocódigo.

Como se evita: todos se apanham da mesma maneira. Percorre o fluxograma com o dedo, ao lado do pseudocódigo, figura a figura e instrução a instrução.

## Palavras novas deste guia

- Pseudocódigo: texto escrito com um vocabulário pequeno e sempre igual, que toda a turma lê da mesma maneira; nenhum computador o executa.
- Fluxograma: o desenho de um algoritmo, com figuras ligadas por setas.
- Variável: um espaço com um nome, onde se guarda um valor que pode mudar enquanto o algoritmo é executado.
- Constante: um valor com nome que não muda durante a execução do algoritmo; escreve-se com `const` e em maiúsculas.
- Tipo: o que decide que valores uma variável pode guardar e o que se pode fazer com eles.
- `int`: o tipo dos números inteiros, sem parte decimal.
- `float`: o tipo dos números com parte decimal.
- `string`: o tipo do texto, uma sequência de caracteres entre aspas.
- `bool`: o tipo que só tem dois valores, `true`, verdadeiro, e `false`, falso.
- Estado: o valor de todas as variáveis de um algoritmo num dado momento.
- Atribuir: dar um valor a uma variável, com `=`; lê-se "recebe".
- Linha onde a variável nasce: a primeira linha onde a variável aparece, e a única que leva o tipo à frente.
- Comparar: perguntar se dois valores são iguais, ou se um é maior do que o outro; a resposta é `true` ou `false`.
- Operador: o sinal ou a palavra que diz que conta se faz, como `+`, `*` ou `div`.
- `div`: a divisão inteira, quantas vezes um número cabe noutro.
- `resto`: o que sobra da divisão inteira.
- Expressão: o que está à direita do `=` numa atribuição, que pode ser um valor, uma variável ou uma conta.
- `ler valor`: a instrução que recebe um valor de fora do algoritmo, escrito por uma pessoa.
- `Escreve:`: a instrução que mostra texto e valores a quem usa o algoritmo.
- Função predefinida: um pedaço de algoritmo já feito, com um nome, que recebe valores entre parênteses e devolve um resultado.
- Valor absoluto: a distância de um número a zero, ou seja, o número sem sinal; é o que `abs` devolve.
- Indentação: o recuo de uma linha em relação à margem, de quatro espaços por nível, que mostra o que está dentro de quê.
- Palavra reservada: uma palavra que faz parte da forma, como `const` ou `int`, e que não se usa como nome de uma variável.
- Estrutura sequencial: instruções executadas uma depois da outra, de cima para baixo, cada uma exatamente uma vez.
- Oval: a figura do fluxograma onde o algoritmo começa, com `Início`, e acaba, com `Fim`.
- Paralelogramo: a figura do fluxograma para as entradas e as saídas, com `ler valor` ou `Escreve:`.
- Retângulo: a figura do fluxograma para as atribuições e as contas.
- Losango: a figura do fluxograma para uma decisão, que só se usa a partir do guia seguinte.
- Tabela de trace: uma tabela onde se executa um algoritmo à mão, com o valor de todas as variáveis depois de cada instrução.
- Caso de teste: um exemplo do contrato, com a entrada e o resultado previsto à mão, que serve para testar o algoritmo.

## Verificar o que aprendeste

Usa estas perguntas para te testares. Responde a cada uma sem olhar para o guia. Se não conseguires, volta à secção que explica a ideia.

1. Qual é a diferença entre uma variável e uma constante? Dá um exemplo de cada que não esteja neste guia.
2. Que tipo escolhes para o número de golos de um jogo? E para a temperatura de uma sala, com décimas, o nome de um jogador e a resposta a "o jogo já acabou?"? Justifica cada escolha pelo que o valor representa.
3. Porque é que `contador = contador + 1` faz sentido como atribuição e não faria sentido como equação da matemática? Como escreves a pergunta "contador é igual a 10?"?
4. No algoritmo do exemplo guiado, em que linha nasce cada variável? Porque é que só essa linha leva o tipo?
5. Depois de `int a = 3`, `int b = a + 4` e `a = b * 2`, quanto valem `a` e `b`?
6. Quanto dão `23 div 4` e `23 resto 4`? Como confirmas as duas contas ao mesmo tempo?
7. Qual é o contrato da função `abs`? Escreve uma atribuição que guarde em `distancia` a diferença, sem sinal, entre duas variáveis `x` e `y`.
8. Escolhe um problema pequeno teu, com uma regra fixa, um dado que se lê e uma conta. Escreve o algoritmo na forma das aulas. Usa uma constante, uma leitura, uma conta e uma escrita, e põe o tipo de cada variável na linha onde nasce. Depois escreve-o em frases claras que não deixem dúvidas.
9. Diz que figura levaria cada linha do algoritmo da pergunta 8, pela ordem, e porque é que a linha `const` não tem figura. Se o professor indicar o desenho, desenha-o em papel. Se fores guardá-lo na aplicação de diagramas, que nome dás ao ficheiro da imagem?
10. Faz o trace completo do algoritmo do exemplo guiado para 125 minutos, uma entrada que o guia não testou. O que aparece no ecrã?
11. O que tens de comparar para mostrar que o pseudocódigo, o fluxograma e o trace de um algoritmo estão certos?
12. Dás o teu algoritmo da pergunta 8 a um colega, para ele o executar à letra. Pelo que ele fizer, como percebes que uma instrução ficou ambígua?

## O que vem a seguir

Para praticar este tema, faz a [ficha de exercícios](02-estado-sequencia-representacoes-exercicios.md). Tem seis exercícios, um para cada ideia do guia, e um desafio opcional. Se o professor o indicar, faz também o [laboratório](02-estado-sequencia-representacoes-laboratorio.md), onde desenhas fluxogramas no computador.

O tema seguinte é [Decisões e validação](03-decisoes-e-validacao.md). O algoritmo deste guia faz sempre as mesmas contas, por mais estranha que seja a entrada. Se alguém escrever -30 minutos, o contrato diz que a entrada não é válida. Mas o algoritmo não tem forma de o verificar, e faz as contas na mesma e mostra um resultado sem sentido. Para verificar uma entrada, ou para fazer coisas diferentes consoante os dados, o algoritmo precisa de tomar decisões. No guia seguinte vais aprender a escrever essas decisões em pseudocódigo e em fluxograma. Vais aprender também a escolher com cuidado os limites de cada decisão e a testar os valores onde uma decisão muda de resposta.

![Rodapé](../imagens/rodape.png)
