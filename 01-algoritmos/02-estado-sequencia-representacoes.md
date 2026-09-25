![Cabeçalho](../imagens/cabecalho.png)

# Estado, sequência e representações

| Identificação | Valor |
| --- | --- |
| Disciplina | Fundamentos de Programação, 10.º ano, Desenvolvimento de Software |
| Unidade de competência | UC00245, Desenvolver algoritmos |
| Percurso | Algoritmos, segundo guia |

## O que vais aprender

No guia anterior escreveste passos em português, numerados. Funcionou, mas o português deixa passar ambiguidades sem dar sinal. Neste guia vais aprender a escrever algoritmos de duas formas mais rigorosas, o pseudocódigo e o fluxograma, e a acompanhar o que acontece dentro de um algoritmo enquanto ele é executado, com uma tabela de trace.

No fim deves conseguir:

- explicar o que é uma variável, uma constante e um tipo de dados, e escolher o tipo certo para cada valor;
- distinguir dar um valor a uma variável de perguntar se dois valores são iguais;
- usar os operadores aritméticos, incluindo a divisão inteira e o resto, e uma função predefinida como ABS;
- escrever um algoritmo sequencial completo em pseudocódigo, segundo a convenção desta disciplina;
- desenhar o mesmo algoritmo em fluxograma, primeiro em papel e depois numa aplicação de diagramas;
- executar um algoritmo à mão numa tabela de trace, instrução a instrução, e comparar o estado antes e depois de cada atribuição;
- confirmar que o pseudocódigo, o fluxograma e o trace dão os mesmos resultados nos mesmos casos de teste.

## O que já sabes e vais usar

Do [guia anterior](01-do-enunciado-ao-problema.md) vais usar três ideias. O contrato de entrada e saída, que continua a ser o primeiro passo de qualquer problema: antes de escrever uma instrução, escreves as entradas, as saídas, as restrições e os exemplos. O estado, que era a fotografia da situação num dado momento, como (3, 3, esquerda) nos Missionários e Canibais. E a decomposição, que te ajuda a decidir que passos o algoritmo tem de dar.

Na aula já escreveste as primeiras instruções em pseudocódigo. Este guia arruma essas instruções numa convenção única, que vais usar da mesma maneira em todos os guias do percurso de algoritmos, e explica a razão de cada regra.

## Uma notação própria para algoritmos

Já viste que o português permite frases como "espera um bocado", que parecem instruções e não são. Uma linguagem de programação, como C ou Python, não tem esse problema: cada instrução tem um único significado. Mas tem outro, para quem está a começar: obriga a respeitar regras de escrita muito rígidas, e um ponto e vírgula esquecido impede o programa de funcionar, mesmo que o raciocínio esteja certo.

O **pseudocódigo** fica a meio caminho. É texto, com um conjunto pequeno de palavras reservadas e regras de escrita simples. É suficientemente rigoroso para não deixar passar ambiguidades, e suficientemente simples para que a tua atenção fique no raciocínio e não na pontuação.

O **fluxograma** é um desenho do mesmo algoritmo, feito com figuras ligadas por setas. Mostra de relance o caminho que o algoritmo percorre, e é o que se costuma usar para explicar um processo a quem não programa.

O mesmo algoritmo escreve-se das duas maneiras. Se as duas versões não disserem exatamente a mesma coisa, pelo menos uma está errada.

## Variáveis

Uma **variável** é um espaço com um nome onde se guarda um valor, e esse valor pode mudar enquanto o algoritmo é executado.

A imagem mais usada é a de uma caixa com uma etiqueta. A etiqueta é o nome e nunca muda. O conteúdo é o valor e pode ser trocado. Quando se guarda um valor novo na caixa, o antigo sai: uma variável guarda um valor de cada vez, nunca dois.

No dia a dia, o marcador de um jogo de basquetebol funciona assim. Há um espaço com a etiqueta "Casa" e outro com a etiqueta "Fora". As etiquetas ficam o jogo inteiro. Os números lá dentro mudam a cada cesto, e quando mudam o número anterior desaparece do marcador.

No guia anterior, o estado dos Missionários e Canibais era formado por três valores sem nome, escritos entre parênteses. Com variáveis, passam a ter nome próprio, por exemplo `missionariosEsquerda`, `canibaisEsquerda` e `ladoDoBarco`, e cada travessia muda o valor de algumas delas.

O nome de uma variável deve dizer o que ela guarda. `totalMinutos` é um bom nome. `x`, `aux` ou `numero2` não são, porque daqui a uma semana nem tu te lembras do que lá estava. Nesta disciplina os nomes das variáveis seguem estas regras:

- começam por uma letra minúscula;
- não têm espaços, e quando têm várias palavras, cada palavra a partir da segunda começa por maiúscula, como em `totalMinutos` ou `precoPorUnidade`;
- não têm acentos nem cedilhas, porque as linguagens que vais usar a seguir nem sempre os aceitam nos nomes, e é melhor habituares-te desde já.

O erro típico com variáveis é usar uma variável antes de ela ter recebido algum valor. Uma caixa acabada de etiquetar está vazia. Perguntar o que está lá dentro não dá nenhuma resposta útil. Vais ver este erro com mais pormenor no fim do guia.

## Constantes

Uma **constante** é um valor com nome que não muda durante a execução do algoritmo.

Há valores que fazem parte das regras do problema e não dos dados: uma hora tem 60 minutos, uma caixa da biblioteca leva 12 livros, a nota máxima é 20. Podias escrever o número diretamente nas contas, mas dar-lhe um nome traz duas vantagens. A primeira é que se percebe o que o número significa: `MINUTOS_POR_HORA` diz muito mais do que um 60 solto no meio de uma conta. A segunda é que, se a regra mudar, muda-se num sítio só. Se a biblioteca passar a usar caixas de 15 livros, altera-se a linha da constante e o resto do algoritmo fica igual, em vez de andares à procura de todos os 12 espalhados pelo texto.

As constantes escrevem-se em maiúsculas, com as palavras separadas por um traço baixo, como `MINUTOS_POR_HORA`. A forma diferente serve para as distinguires à primeira vista das variáveis.

## Tipos de dados

Cada variável guarda valores de um **tipo**, e o tipo decide que valores são possíveis e o que se pode fazer com eles. Nesta disciplina usam-se quatro tipos:

| Tipo | Guarda | Exemplos |
| --- | --- | --- |
| `inteiro` | números sem parte decimal | `0`, `59`, `-3` |
| `real` | números com parte decimal | `2.25`, `0.5`, `-1.75` |
| `texto` | sequências de caracteres, entre aspas | `"Ana"`, `"Quantos minutos?"` |
| `lógico` | só um de dois valores | `verdadeiro`, `falso` |

Repara que no pseudocódigo a parte decimal de um número se separa com um ponto, `2.25`, tal como nas linguagens de programação. No texto em português continua a escrever-se com vírgula, 2,25. São duas convenções para dois contextos, e não se misturam: dentro do pseudocódigo, ponto; no texto que escreves à volta, vírgula.

Escolher o tipo é uma decisão com consequências, e decide-se pelo que o valor representa. Um número de minutos, de caixas ou de pessoas é `inteiro`, porque não existem 2,5 pessoas. Um peso ou uma média é `real`. Um nome ou uma mensagem é `texto`. A resposta a uma pergunta de sim ou não, como "a nota é positiva?", é `lógico`. Vais usar muito o tipo lógico no guia seguinte, quando o algoritmo tiver de tomar decisões.

A confusão mais frequente é entre o número `12` e o texto `"12"`. No papel parecem iguais e não são. Com o número podes fazer contas. Com o texto não: é uma sequência de dois caracteres, o 1 e o 2, tal como `"ab"` é uma sequência de duas letras. Juntar o texto `"12"` com o texto `"3"` dá `"123"`, e não 15.

## Estado

No guia anterior, o estado era a fotografia da situação num dado momento. Com variáveis, a definição fica mais precisa: o **estado** de um algoritmo, num dado momento, é o valor de todas as suas variáveis nesse momento.

Cada instrução que muda o valor de uma variável muda o estado. Se quiseres saber o que um algoritmo está a fazer, não precisas de adivinhar: olhas para o estado antes de uma instrução, olhas para o estado depois, e a diferença é o efeito dessa instrução. É esta a ideia por trás da tabela de trace, que vais aprender mais à frente neste guia.

## Atribuição: dar um valor não é perguntar se é igual

Esta é a distinção mais importante do guia, e a que mais vezes se troca no início.

**Atribuir** é dar um valor a uma variável. No pseudocódigo desta disciplina escreve-se com uma seta que aponta para a esquerda:

```text
horas ← 2
```

Lê-se "horas recebe 2". É uma ordem, não uma pergunta: a partir deste momento, `horas` vale 2, seja qual for o valor que tinha antes.

A atribuição executa-se sempre em duas fases, por esta ordem. Primeiro calcula-se o lado direito da seta, usando os valores que as variáveis têm nesse momento. Depois guarda-se o resultado na variável do lado esquerdo, e o valor antigo dessa variável perde-se.

Vê o que isto significa nesta sequência:

```text
total ← 10
total ← total + 5
```

Se lesses a segunda linha como uma pergunta, "total é igual a total mais 5?", a resposta seria sempre não: nenhum número é igual a ele próprio mais cinco. Lida como atribuição, faz todo o sentido. Calcula-se o lado direito com o valor atual de `total`, que é 10, e dá 15. Guarda-se 15 em `total`. No fim, `total` vale 15, e o 10 desapareceu.

A perda do valor antigo tem consequências que vale a pena ver com números. Imagina duas variáveis, `a` com 4 e `b` com 9, e estas duas instruções:

```text
a ← b
b ← a
```

A primeira instrução guarda em `a` o valor de `b`, e `a` passa a valer 9. O 4 perdeu-se. A segunda guarda em `b` o valor atual de `a`, que já é 9. No fim, as duas valem 9. Quem esperava que os valores trocassem de lugar esqueceu-se de que, depois da primeira linha, o 4 já não existe em lado nenhum. Pensar no estado antes e depois de cada linha é o que te protege deste tipo de engano.

**Comparar** é perguntar se dois valores são iguais, ou se um é maior do que o outro. O resultado de uma comparação é `verdadeiro` ou `falso`, e as comparações escrevem-se com sinais como `=` e `>=`. São o assunto do guia seguinte. Por agora, fixa a regra: a seta manda, o sinal de igual pergunta. Nesta convenção nunca se usa `=` para dar um valor a uma variável.

Do lado esquerdo da seta está sempre uma única variável, porque é lá que o valor vai ser guardado. `10 ← total` e `total + 5 ← total` não fazem sentido: não se pode guardar um valor dentro do número 10, nem dentro de uma conta.

## Operadores aritméticos

As contas escrevem-se com os operadores que já conheces da matemática, com duas novidades para trabalhar com números inteiros.

| Operador | O que faz | Exemplo | Resultado |
| --- | --- | --- | ---: |
| `+` | soma | `7 + 2` | `9` |
| `-` | subtração | `7 - 2` | `5` |
| `*` | multiplicação | `7 * 2` | `14` |
| `/` | divisão, com parte decimal | `7 / 2` | `3.5` |
| `DIV` | divisão inteira: quantas vezes cabe | `7 DIV 2` | `3` |
| `RESTO` | o que sobra da divisão inteira | `7 RESTO 2` | `1` |

A multiplicação escreve-se com asterisco porque o "x" é uma letra e podia ser o nome de uma variável.

`DIV` e `RESTO` são as contas de dividir que aprendeste na primária, antes de haver números decimais. Imagina 17 rebuçados para repartir por 5 amigos, sem partir nenhum. Cada amigo recebe 3, e sobram 2. Em pseudocódigo, `17 DIV 5` dá `3`, que é quanto recebe cada um, e `17 RESTO 5` dá `2`, que é o que sobra. Há uma forma simples de confirmar as duas contas ao mesmo tempo: o divisor vezes a divisão inteira, mais o resto, tem de dar o número de partida. Aqui, 5 vezes 3 mais 2 dá 17.

A diferença entre `/` e `DIV` não é um pormenor. `7 / 2` dá `3.5`, um número real. `7 DIV 2` dá `3`, um inteiro, e a parte que não cabe vai para o `RESTO`. Usa `DIV` e `RESTO` quando as quantidades são inteiras e a parte decimal não faz sentido, como em pessoas, caixas ou minutos. Usa `/` quando a parte decimal interessa, como numa média. `DIV` e `RESTO` usam-se só com números inteiros e com um divisor maior do que zero.

Noutros livros e noutras linguagens vais encontrar o resto escrito como `MOD` ou como `%`. É a mesma operação com outro nome. Nesta disciplina, no pseudocódigo, escreve-se `RESTO`.

As contas seguem a ordem que conheces da matemática. Primeiro o que está entre parênteses. Depois multiplicações e divisões, incluindo `DIV` e `RESTO`. Por fim somas e subtrações. Entre operações do mesmo nível, faz-se da esquerda para a direita. Assim, `2 + 3 * 4` dá `14`, porque a multiplicação se faz primeiro, e `(2 + 3) * 4` dá `20`. Quando tiveres dúvidas sobre a ordem, põe parênteses: não custam nada e tiram a dúvida a quem ler.

## Entrada e saída: LER e ESCREVER

Um algoritmo recebe dados e produz resultados. As entradas e as saídas do contrato têm, no pseudocódigo, instruções próprias.

`LER variavel` recebe um valor de fora do algoritmo, normalmente escrito por uma pessoa no teclado, e guarda-o na variável. É uma forma de atribuição: o valor que a variável tinha antes perde-se, e passa a ter o valor lido.

`ESCREVER` mostra informação a quem está a usar o algoritmo. Pode mostrar texto e valores de variáveis, separados por vírgulas. O que está entre aspas aparece tal e qual. O que está sem aspas é o nome de uma variável, e o que aparece é o seu valor.

A diferença entre as duas coisas é uma fonte clássica de erros. Se `horas` valer 2:

| Instrução | O que aparece no ecrã |
| --- | --- |
| `ESCREVER "horas"` | horas |
| `ESCREVER horas` | 2 |
| `ESCREVER "Passaram ", horas, " horas"` | Passaram 2 horas |

Repara nos espaços dentro das aspas na última linha. Sem eles, aparecia "Passaram2horas". O algoritmo escreve exatamente o que lhe mandas, incluindo os espaços que te esqueceste de pôr.

Antes de cada `LER`, escreve-se quase sempre um `ESCREVER` com uma pergunta, para quem está do outro lado saber o que tem de escrever. Um `LER` sem pergunta deixa a pessoa a olhar para um ecrã parado, sem saber que o algoritmo está à espera dela.

## Funções predefinidas

Uma **função predefinida** é um pedaço de algoritmo que já vem feito, com um nome, pronto a usar. Dás-lhe um ou mais valores, entre parênteses, e ela devolve um resultado, que podes usar numa conta ou guardar numa variável.

A primeira que vais usar é `ABS`, o valor absoluto. O seu contrato é este:

- entrada: um número, inteiro ou real;
- saída: a distância desse número a zero, ou seja, o mesmo número sem sinal;
- exemplos: `ABS(-7)` dá `7`, `ABS(7)` dá `7` e `ABS(0)` dá `0`.

Onde é que isto serve? Sempre que interessa o tamanho de uma diferença e não o seu sentido. Se o João tem 12 anos e a irmã tem 15, a diferença de idades é 3 anos, seja qual for a ordem em que fazes a conta. `12 - 15` dá `-3` e `15 - 12` dá `3`, mas `ABS(12 - 15)` e `ABS(15 - 12)` dão ambos `3`. Num algoritmo escrevia-se assim:

```text
diferenca ← ABS(idadeJoao - idadeIrma)
```

Primeiro calcula-se o que está dentro dos parênteses, depois aplica-se a função a esse resultado, e por fim guarda-se o valor em `diferenca`.

Repara na ligação ao guia anterior. Para usar `ABS` não precisas de saber como ela está feita por dentro, tal como não precisas de saber como funciona uma máquina de venda automática para comprar uma garrafa de água. Chega-te o contrato. Existem outras funções predefinidas, cada uma com o seu contrato, como a raiz quadrada. Quando precisares de uma, o enunciado ou o professor dá-te o nome e o contrato.

## A convenção de pseudocódigo desta disciplina

Há muitas formas de escrever pseudocódigo, e livros diferentes usam palavras diferentes. Nesta disciplina usa-se sempre a mesma, e é esta que vais encontrar em todos os guias do percurso de algoritmos. Se num livro ou num vídeo encontrares outra, não está errada: é outra convenção. Quando escreveres, usa esta.

Um algoritmo tem sempre esta estrutura:

```text
ALGORITMO NomeDoAlgoritmo
CONSTANTES
    NOME_DA_CONSTANTE ← valor
VARIÁVEIS
    nomeDaVariavel: tipo
INÍCIO
    instruções, uma por linha, pela ordem em que são executadas
FIM
```

Primeiro dá-se um nome ao algoritmo. Depois declaram-se as constantes, cada uma com o seu valor, e as variáveis, cada uma com o seu tipo. Só depois, entre `INÍCIO` e `FIM`, vêm as instruções. Declarar antes de usar obriga-te a pensar em que dados o algoritmo vai precisar, e isso é, outra vez, o contrato a trabalhar. Se um algoritmo não tiver constantes, a secção `CONSTANTES` omite-se.

As linhas dentro de cada secção escrevem-se com quatro espaços à esquerda. Esse recuo, a que se chama **indentação**, mostra o que está dentro de quê. Aqui parece decorativo. No guia seguinte, quando houver instruções dentro de decisões, passa a ser indispensável para se perceber o algoritmo.

A tabela seguinte reúne toda a convenção. As três últimas linhas pertencem ao guia seguinte e estão aqui para teres a convenção completa num só sítio.

| Elemento | Como se escreve | Exemplo |
| --- | --- | --- |
| Nome do algoritmo | `ALGORITMO`, seguido do nome, com cada palavra a começar por maiúscula | `ALGORITMO ConverterMinutos` |
| Constantes | `CONSTANTES`, e depois uma por linha, em maiúsculas | `MINUTOS_POR_HORA ← 60` |
| Variáveis | `VARIÁVEIS`, e depois uma por linha, com dois pontos e o tipo | `horas: inteiro` |
| Tipos | `inteiro`, `real`, `texto`, `lógico` | `nome: texto` |
| Instruções | entre `INÍCIO` e `FIM`, uma por linha | qualquer das instruções das linhas seguintes |
| Atribuição | variável, seta para a esquerda, expressão | `horas ← totalMinutos DIV MINUTOS_POR_HORA` |
| Entrada | `LER`, seguido da variável | `LER totalMinutos` |
| Saída | `ESCREVER`, seguido de texto e variáveis separados por vírgulas | `ESCREVER "Horas: ", horas` |
| Aritmética | `+`, `-`, `*`, `/`, `DIV`, `RESTO`, parênteses | `(a + b) / 2` |
| Função predefinida | nome em maiúsculas e valor entre parênteses | `ABS(a - b)` |
| Comparações | `=`, `!=`, `<`, `<=`, `>`, `>=` | `nota >= 10` |
| Operadores lógicos | `E`, `OU`, `NÃO` | `nota < 0 OU nota > 20` |
| Seleção | `SE` condição `ENTÃO`, `SENÃO SE` condição `ENTÃO`, `SENÃO`, `FIM SE` | ver o guia seguinte |

As palavras da convenção, como `LER`, `ESCREVER` ou `INÍCIO`, escrevem-se sempre em maiúsculas. Chamam-se **palavras reservadas**, porque têm um significado fixo e não podem ser usadas como nomes de variáveis. Os tipos escrevem-se em minúsculas.

## Sequência

Uma **estrutura sequencial** é uma sequência de instruções executadas uma depois da outra, de cima para baixo, cada uma exatamente uma vez, sem saltar nenhuma e sem voltar atrás.

É a forma mais simples de algoritmo, e é a única que usas neste guia. Uma receita em que todos os passos se fazem sempre, pela mesma ordem, é uma sequência. Uma receita com "se a massa estiver muito mole, junta mais farinha" já não é, porque há um passo que umas vezes se faz e outras não. Esse tipo de instrução é o assunto do guia seguinte.

Numa sequência, a ordem importa. Uma instrução só pode usar valores que já existem no momento em que é executada. Se uma conta precisa de um valor que só é lido duas linhas abaixo, a conta é feita com uma variável que ainda não tem valor, e o resultado não faz sentido. Parece óbvio escrito assim, e é um dos erros mais frequentes de quem começa.

## Fluxogramas

Um fluxograma representa um algoritmo com figuras ligadas por setas. Cada figura tem uma forma que diz que tipo de instrução é, e as setas dizem a ordem.

| Figura | Para que serve | Como aparece nestes guias |
| --- | --- | --- |
| Oval | Início e fim do algoritmo | `( Início )` e `( Fim )` |
| Paralelogramo | Entrada e saída de dados: `LER` e `ESCREVER` | `/ LER totalMinutos /` |
| Retângulo | Processamento: atribuições e contas | `[ horas ← totalMinutos DIV MINUTOS_POR_HORA ]` |
| Losango | Decisão: o caminho divide-se em dois | uma figura de três linhas com pontas à esquerda e à direita, mostrada abaixo |
| Seta | O sentido do percurso | linhas verticais terminadas em `↓` |

Estes guias são ficheiros de texto e não têm desenhos. Por isso, cada figura aparece representada por caracteres: parênteses curvos para o oval, barras inclinadas para o paralelogramo e parênteses retos para o retângulo. O losango ocupa três linhas, para se distinguir bem dos sinais de comparação que muitas vezes vão lá dentro, e a condição termina sempre com um ponto de interrogação:

```text
         /                  \
        <     condição ?     >
         \                  /
```

Nas decisões, cada saída do losango leva escrito `Sim` ou `Não`, conforme a condição seja verdadeira ou falsa. Quando desenhares no papel ou na aplicação de diagramas, usa as figuras verdadeiras.

Um fluxograma bem feito cumpre sempre estas regras:

- tem um único início;
- tem pelo menos um fim;
- todas as figuras estão ligadas por setas, e nenhuma seta fica pendurada sem destino;
- cada figura tem uma só instrução, escrita da mesma maneira que no pseudocódigo.

Neste guia só vais usar o oval, o paralelogramo e o retângulo, ligados em linha reta, porque os algoritmos sequenciais nunca escolhem entre dois caminhos. O losango fica apresentado porque faz parte da simbologia, e entra em uso no guia seguinte.

## Tabela de trace

Uma **tabela de trace** é uma tabela onde se executa um algoritmo à mão, instrução a instrução, registando em cada linha o valor de todas as variáveis depois dessa instrução. Em inglês chama-se trace table, e vais ouvir muitas vezes dizer apenas "fazer o trace".

Serve para veres o algoritmo por dentro. Um algoritmo só mostra o que escreve no ecrã, e quando o resultado está errado, isso não diz onde está o erro. O trace mostra o estado depois de cada instrução, e por isso mostra o sítio exato onde um valor passou a ser diferente do que devia.

Uma tabela de trace constrói-se assim:

1. Faz uma coluna para o número do passo, uma para a instrução executada, uma para cada variável e uma para o que aparece no ecrã.
2. Na primeira linha, antes de qualquer instrução, escreve "sem valor" em todas as variáveis, porque nenhuma recebeu ainda um valor.
3. Para cada instrução, pela ordem em que é executada, acrescenta uma linha. Copia os valores da linha de cima e muda só o que essa instrução muda.
4. Numa atribuição ou num `LER`, muda só a coluna da variável que recebe o valor. As outras ficam iguais.
5. Num `ESCREVER`, nenhuma variável muda. Escreve na coluna do ecrã exatamente o que aparece, com os valores que as variáveis têm nesse momento.

Há uma forma simples de ler uma tabela destas: o estado antes de uma instrução está na linha de cima, e o estado depois está na própria linha. Comparar as duas linhas mostra o efeito da instrução.

A regra mais importante do trace é executar o que está escrito, e não o que achas que o algoritmo devia fazer. Se preencheres a tabela com os valores que esperavas, ela concorda sempre contigo e não encontra erro nenhum. O trace só serve se fores tão literal como o robô da sandes.

## Exemplo guiado: converter minutos em horas e minutos

### Passo 1: o enunciado

> Um treinador regista o tempo de treino de cada atleta em minutos, mas os atletas preferem ver esse tempo em horas e minutos. Escreve um algoritmo que leia um número de minutos e mostre quantas horas completas e quantos minutos restantes correspondem a esse tempo. Por exemplo, 135 minutos são 2 horas e 15 minutos.

### Passo 2: o contrato

A entrada é o número total de minutos, um inteiro igual ou maior do que zero.

As saídas são o número de horas completas, um inteiro igual ou maior do que zero, e o número de minutos restantes, um inteiro entre 0 e 59. Os minutos restantes nunca podem chegar a 60, porque 60 minutos já fazem mais uma hora completa.

A restrição do problema é a regra das horas: uma hora tem 60 minutos. É um valor fixo, que vai ser uma constante.

Os exemplos concretos calculam-se à mão, antes de haver algoritmo. Estes quatro foram escolhidos de propósito:

| Minutos | Horas | Minutos restantes | Porque é que este caso foi escolhido |
| ---: | ---: | ---: | --- |
| 135 | 2 | 15 | O caso do enunciado, um caso normal |
| 0 | 0 | 0 | O valor mais pequeno permitido |
| 59 | 0 | 59 | O maior valor que ainda não chega a uma hora |
| 60 | 1 | 0 | O primeiro valor que completa uma hora |

Os casos 59 e 60 estão lado a lado de propósito. São os dois lados do sítio onde a resposta muda de comportamento: com 59 ainda não há nenhuma hora completa, com 60 já há uma. Se o algoritmo tiver um erro nessa passagem, estes dois casos apanham-no. O 0 verifica que o algoritmo se porta bem quando não há nada para converter. O contrato diz que a entrada é igual ou maior do que zero, e por isso um valor negativo fica fora deste problema. O que fazer quando alguém escreve um valor fora do contrato é o assunto do guia seguinte.

### Passo 3: decompor e pensar nas contas

A decomposição é curta: ler os minutos, calcular as horas completas, calcular os minutos restantes, mostrar o resultado.

As contas merecem mais atenção. Pensa no caso de 135 minutos. Quantas horas completas cabem em 135 minutos? É perguntar quantas vezes 60 cabe em 135, sem partir nenhuma hora. Cabe 2 vezes, que dão 120 minutos. É exatamente a divisão inteira: `135 DIV 60` dá `2`.

E quantos minutos ficam de fora dessas 2 horas? O que sobra: 135 menos 120, que dá 15. É exatamente o resto: `135 RESTO 60` dá `15`.

Confirma com a verificação que viste na secção dos operadores: 60 vezes 2, mais 15, dá 135. As duas contas estão certas.

### Passo 4: o pseudocódigo

```text
ALGORITMO ConverterMinutos
CONSTANTES
    MINUTOS_POR_HORA ← 60
VARIÁVEIS
    totalMinutos: inteiro
    horas: inteiro
    minutos: inteiro
INÍCIO
    ESCREVER "Quantos minutos?"
    LER totalMinutos
    horas ← totalMinutos DIV MINUTOS_POR_HORA
    minutos ← totalMinutos RESTO MINUTOS_POR_HORA
    ESCREVER horas, " h e ", minutos, " min"
FIM
```

Cada decisão deste pseudocódigo tem uma razão:

1. `MINUTOS_POR_HORA` é uma constante porque o 60 é uma regra do problema e não um dado que mude de atleta para atleta. Assim, cada conta diz o que está a fazer: dividir pelos minutos que tem uma hora.
2. As três variáveis são do tipo `inteiro`, porque minutos e horas completas não têm parte decimal. Foi o contrato que o decidiu.
3. `totalMinutos` e `minutos` têm nomes diferentes porque guardam coisas diferentes: o total que foi lido e o que sobra depois de tirar as horas. Se as duas se chamassem `minutos`, não havia forma de as distinguir.
4. O `ESCREVER` com a pergunta vem antes do `LER`, para quem usa o algoritmo saber o que tem de escrever.
5. As duas contas vêm depois do `LER`, porque ambas precisam do valor de `totalMinutos`, que só existe depois de ser lido.
6. O último `ESCREVER` junta valores e texto. Os espaços dentro das aspas estão lá para o resultado aparecer como "2 h e 15 min" e não como "2h e15min".

### Passo 5: o fluxograma

O mesmo algoritmo, desenhado:

```text
                     ( Início )
                         |
                         ↓
          / ESCREVER "Quantos minutos?" /
                         |
                         ↓
                / LER totalMinutos /
                         |
                         ↓
   [ horas ← totalMinutos DIV MINUTOS_POR_HORA ]
                         |
                         ↓
 [ minutos ← totalMinutos RESTO MINUTOS_POR_HORA ]
                         |
                         ↓
    / ESCREVER horas, " h e ", minutos, " min" /
                         |
                         ↓
                      ( Fim )
```

Segue o percurso com o dedo, de cima para baixo. Começa no oval de início, passa pelos dois paralelogramos da pergunta e da leitura, faz as duas contas nos retângulos, mostra o resultado noutro paralelogramo e termina no oval de fim. É uma linha única, sem bifurcações, e é isso que significa uma estrutura sequencial.

Agora compara figura a figura com o pseudocódigo. A cada instrução entre `INÍCIO` e `FIM` corresponde uma figura, pela mesma ordem e com o mesmo texto. As declarações de constantes e variáveis não têm figura, porque não são instruções executadas: dizem que dados existem, não o que se faz com eles.

### Passo 6: o trace, linha a linha

Vais fazer o trace dos três casos de fronteira do contrato. A constante não tem coluna, porque vale 60 do princípio ao fim e nunca muda.

Primeiro caso: a pessoa escreve 60.

| Passo | Instrução executada | totalMinutos | horas | minutos | Ecrã |
| ---: | --- | ---: | ---: | ---: | --- |
| 0 | antes de começar | sem valor | sem valor | sem valor | nada |
| 1 | `ESCREVER "Quantos minutos?"` | sem valor | sem valor | sem valor | Quantos minutos? |
| 2 | `LER totalMinutos` | 60 | sem valor | sem valor | a pessoa escreve 60 |
| 3 | `horas ← totalMinutos DIV MINUTOS_POR_HORA` | 60 | 1 | sem valor | nada |
| 4 | `minutos ← totalMinutos RESTO MINUTOS_POR_HORA` | 60 | 1 | 0 | nada |
| 5 | `ESCREVER horas, " h e ", minutos, " min"` | 60 | 1 | 0 | 1 h e 0 min |

Lê a tabela comparando cada linha com a de cima, que é o estado antes da instrução.

No passo 1 nenhuma variável muda, porque `ESCREVER` não mexe no estado: só aparece a pergunta no ecrã.

No passo 2, `totalMinutos` passa de "sem valor" para 60. É a única coluna que muda, porque o `LER` só guarda valor na variável que está à frente dele.

No passo 3 calcula-se o lado direito com o valor que `totalMinutos` tem nesse momento: `60 DIV 60`. O 60 cabe uma vez em 60, e por isso dá 1. Esse 1 é guardado em `horas`, que passa de "sem valor" para 1. `totalMinutos` continua a valer 60: usar o valor de uma variável numa conta não o altera.

No passo 4 calcula-se `60 RESTO 60`. Depois de tirar uma hora de 60 minutos a 60 minutos, não sobra nada, e por isso dá 0. `minutos` passa de "sem valor" para 0.

No passo 5 nenhuma variável muda, e aparece no ecrã o resultado, com os valores que as variáveis têm nesse momento.

Segundo caso: a pessoa escreve 59.

| Passo | Instrução executada | totalMinutos | horas | minutos | Ecrã |
| ---: | --- | ---: | ---: | ---: | --- |
| 0 | antes de começar | sem valor | sem valor | sem valor | nada |
| 1 | `ESCREVER "Quantos minutos?"` | sem valor | sem valor | sem valor | Quantos minutos? |
| 2 | `LER totalMinutos` | 59 | sem valor | sem valor | a pessoa escreve 59 |
| 3 | `horas ← totalMinutos DIV MINUTOS_POR_HORA` | 59 | 0 | sem valor | nada |
| 4 | `minutos ← totalMinutos RESTO MINUTOS_POR_HORA` | 59 | 0 | 59 | nada |
| 5 | `ESCREVER horas, " h e ", minutos, " min"` | 59 | 0 | 59 | 0 h e 59 min |

A diferença para o primeiro caso está toda nos passos 3 e 4. O 60 não cabe nenhuma vez em 59, e por isso `59 DIV 60` dá 0. Como não se tirou nenhuma hora, sobram os 59 minutos inteiros, e `59 RESTO 60` dá 59. Repara que os minutos restantes ficaram em 59, o maior valor que o contrato permite, e não passaram de lá.

Terceiro caso: a pessoa escreve 0.

| Passo | Instrução executada | totalMinutos | horas | minutos | Ecrã |
| ---: | --- | ---: | ---: | ---: | --- |
| 0 | antes de começar | sem valor | sem valor | sem valor | nada |
| 1 | `ESCREVER "Quantos minutos?"` | sem valor | sem valor | sem valor | Quantos minutos? |
| 2 | `LER totalMinutos` | 0 | sem valor | sem valor | a pessoa escreve 0 |
| 3 | `horas ← totalMinutos DIV MINUTOS_POR_HORA` | 0 | 0 | sem valor | nada |
| 4 | `minutos ← totalMinutos RESTO MINUTOS_POR_HORA` | 0 | 0 | 0 | nada |
| 5 | `ESCREVER horas, " h e ", minutos, " min"` | 0 | 0 | 0 | 0 h e 0 min |

O 60 não cabe nenhuma vez em 0, e não sobra nada. O algoritmo não precisa de nenhum cuidado especial para o zero: as duas contas tratam-no sozinhas. Foi por isso que valeu a pena testá-lo. Nem sempre é assim, e há algoritmos que falham precisamente no zero.

Se fizeres também o trace de 135, o caso do enunciado, os passos 3 e 4 dão 2 e 15, e o ecrã mostra "2 h e 15 min".

### Passo 7: confirmar que as três representações concordam

Tens agora três representações do mesmo algoritmo: o pseudocódigo, o fluxograma e o trace. Estão certas se derem os mesmos resultados nos mesmos casos de teste, e se esses resultados forem os que o contrato previu à mão no passo 2.

| Minutos | Previsto no contrato | Resultado do trace |
| ---: | --- | --- |
| 0 | 0 horas e 0 minutos | 0 h e 0 min |
| 59 | 0 horas e 59 minutos | 0 h e 59 min |
| 60 | 1 hora e 0 minutos | 1 h e 0 min |
| 135 | 2 horas e 15 minutos | 2 h e 15 min |

Os quatro casos coincidem. O fluxograma tem as mesmas instruções pela mesma ordem que o pseudocódigo, e por isso percorrê-lo com o dedo, com os mesmos valores, produz as mesmas linhas de trace. Se algum caso não coincidisse, o passo seguinte seria procurar no trace a primeira linha onde um valor ficou diferente do esperado.

### Passo 8: desenhar o fluxograma na aplicação de diagramas

Depois de desenhares o fluxograma em papel, vais reconstruí-lo numa aplicação de diagramas no computador, a que o professor indicar na aula. O processo é o mesmo em qualquer aplicação:

1. Cria um diagrama novo e procura a biblioteca de figuras de fluxograma. Tem sempre o oval, o paralelogramo, o retângulo e o losango.
2. Coloca as figuras de cima para baixo, pela ordem do papel, uma instrução por figura, com o texto escrito exatamente como no pseudocódigo.
3. Liga as figuras com setas, sempre no sentido da execução. Confirma que cada seta sai de uma figura e chega a outra, sem pontas soltas.
4. Percorre o diagrama com o dedo no ecrã e compara-o, figura a figura, com o pseudocódigo.
5. Guarda o ficheiro da aplicação e exporta o diagrama como imagem ou como PDF. Dá ao ficheiro um nome que diga o que ele contém, em minúsculas, com hífenes e sem acentos nem espaços, como `fluxograma-converter-minutos.png`.

O desenho em papel vem primeiro de propósito. No papel pensas no algoritmo. Na aplicação tratas da apresentação. Se começares pela aplicação, a tua atenção vai para o tamanho das caixas e para o alinhamento das setas, e o algoritmo fica para segundo plano.

## Erros frequentes

### Usar uma variável antes de ela ser lida

Imagina que alguém escreveu o corpo do algoritmo com as contas antes da leitura:

```text
INÍCIO
    horas ← totalMinutos DIV MINUTOS_POR_HORA
    minutos ← totalMinutos RESTO MINUTOS_POR_HORA
    ESCREVER "Quantos minutos?"
    LER totalMinutos
    ESCREVER horas, " h e ", minutos, " min"
FIM
```

Lido à pressa, parece ter tudo. O trace mostra o problema logo no primeiro passo: a conta de `horas` usa `totalMinutos`, e nesse momento a coluna de `totalMinutos` diz "sem valor". A conta está a ser feita com uma caixa vazia. O valor escrito pela pessoa só chega duas linhas depois, quando as contas já foram feitas, e não é usado em mais nenhuma conta até ao fim.

Como se evita: antes de escreveres uma conta, pergunta-te de onde vem cada valor que ela usa. Tem de vir de um `LER` ou de uma atribuição que está acima dela.

### Fazer uma conta antes de ter todos os dados

É um parente do erro anterior, e aparece quando o algoritmo lê mais do que um valor. Vê este bocado de um algoritmo que devia calcular a média de dois testes:

```text
    LER teste1
    media ← (teste1 + teste2) / 2
    LER teste2
```

A conta está no sítio certo em relação ao primeiro teste e no sítio errado em relação ao segundo. No momento da conta, `teste2` ainda não tem valor, e por isso a média é calculada com um dado que falta. No trace, a coluna de `teste2` diz "sem valor" na linha da conta e só muda na linha seguinte, quando já é tarde.

Como se evita: numa sequência, leem-se primeiro todos os dados de que a conta precisa, e só depois se faz a conta. Uma boa regra é agrupar as leituras no início do algoritmo.

### Usar `/` em vez de `DIV`

Com `horas ← totalMinutos / MINUTOS_POR_HORA`, o caso de 135 minutos dá 2.25. É tentador ler isto como "2 horas e 25 minutos", e está errado. 2,25 horas são 2 horas e um quarto de hora, ou seja, 2 horas e 15 minutos. A parte decimal de um número de horas não são minutos: são frações de hora. Além disso, 2.25 é um real, e o contrato diz que as horas são um inteiro.

Como se evita: pergunta-te se o resultado pode ter parte decimal. Horas completas não podem, e por isso a conta certa é `DIV`.

### Confundir texto com variável no `ESCREVER`

`ESCREVER "horas"` mostra a palavra horas. `ESCREVER horas` mostra o valor da variável, por exemplo 2. Quem troca uma pela outra obtém um ecrã com palavras onde deviam estar números, ou com números sem nenhuma explicação à volta.

### Usar `=` para atribuir, ou escrever a atribuição ao contrário

`horas = totalMinutos DIV 60` pergunta se `horas` é igual à conta. Não guarda nada. `totalMinutos DIV 60 ← horas` tenta guardar um valor dentro de uma conta, o que não faz sentido. Na atribuição, a seta aponta para a variável que recebe o valor, e essa variável está sempre sozinha do lado esquerdo.

### Preencher o trace com o que se esperava

Quem já sabe que 60 minutos são 1 hora é tentado a escrever 1 na coluna das horas sem fazer a conta que está escrita. Se a instrução estiver errada, o trace fica certo e o algoritmo continua errado. Faz sempre a conta que está escrita, com os valores que estão na linha de cima.

### Fluxograma que não corresponde ao pseudocódigo

Os erros mais comuns no fluxograma são uma figura com a forma errada, como um `LER` dentro de um retângulo, uma instrução que existe no pseudocódigo e falta no desenho, e uma seta que não chega a lado nenhum. Todos se apanham da mesma maneira: percorrer o fluxograma com o dedo, ao lado do pseudocódigo, figura a figura e instrução a instrução.

## Verificar o que aprendeste

Usa esta lista para te testares. Para cada ponto, experimenta fazê-lo sem olhar para o guia. Se não conseguires, volta à secção correspondente.

- Consegues explicar a diferença entre uma variável e uma constante, e dar um exemplo de cada que não esteja neste guia.
- Consegues escolher o tipo certo para um valor e justificar a escolha pelo que o valor representa.
- Consegues explicar, com um exemplo teu, porque é que `contador ← contador + 1` faz sentido como atribuição e não faria sentido como pergunta.
- Consegues prever o estado de duas variáveis depois de uma sequência de atribuições em que uma usa o valor da outra.
- Consegues calcular à mão `DIV` e `RESTO` de dois inteiros e confirmar o resultado com a verificação do divisor vezes a divisão inteira mais o resto.
- Consegues escrever o contrato da função `ABS` e usá-la numa atribuição.
- Consegues escrever um algoritmo sequencial completo segundo a convenção desta disciplina, com constantes, variáveis declaradas com tipo, leituras, contas e escritas.
- Consegues desenhar o fluxograma desse algoritmo, primeiro no papel e depois na aplicação de diagramas, e exportá-lo com um nome de ficheiro correto.
- Consegues fazer o trace completo de um algoritmo, linha a linha, para uma entrada que ninguém testou antes de ti.
- Consegues mostrar, com casos de teste, que o teu pseudocódigo, o teu fluxograma e o teu trace dão os mesmos resultados, e que esses resultados são os previstos no contrato.
- Consegues dar o teu algoritmo a um colega para ele o executar à letra, e perceber, pelo que ele fizer, se alguma instrução ficou ambígua.

## O que vem a seguir

O algoritmo deste guia faz sempre as mesmas contas, por mais estranha que seja a entrada. Se alguém escrever -30 minutos, o contrato diz que a entrada não é válida, mas o algoritmo não tem forma de o verificar: faz as contas na mesma e mostra um resultado sem sentido. Para verificar uma entrada, ou para fazer coisas diferentes consoante os dados, o algoritmo precisa de tomar decisões. No [guia seguinte](03-decisoes-e-validacao.md) vais aprender a escrever essas decisões em pseudocódigo e em fluxograma, a escolher com cuidado os limites de cada decisão e a testar os valores onde uma decisão muda de resposta.

![Rodapé](../imagens/rodape.png)
