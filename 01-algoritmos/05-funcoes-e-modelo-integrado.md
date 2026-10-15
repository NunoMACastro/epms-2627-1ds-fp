![Cabeçalho](../imagens/cabecalho.png)

# Funções e modelo integrado

Módulo Desenvolver algoritmos. Neste guia aprendes a escrever as tuas próprias funções, partes de um algoritmo com nome que recebem valores e devolvem um resultado. Aprendes também a decompor um problema inteiro em funções e a testá-lo por partes. Lê-se em cerca de 90 minutos, de preferência em mais do que uma vez, com papel e lápis ao lado. Para praticar, há a [ficha de exercícios](05-funcoes-e-modelo-integrado-exercicios.md) deste tema.

Os algoritmos do guia 04 já eram grandes, e começavam a repetir partes de problema para problema. Somavam um array, calculavam uma média com cuidado com o zero, procuravam um valor, validavam uma nota. Neste guia vais aprender a dar nome a essas partes. Depois vais juntar tudo o que aprendeste na algoritmia num algoritmo completo, organizado em funções, testado e pronto para passar para o Python.

Na aula já escreveste as primeiras funções em pseudocódigo, com parâmetros, argumentos e `devolver`. Este guia arruma essa matéria na forma que usamos nas aulas. Explica também o que acontece por dentro de uma chamada, e mostra como se decompõe um problema inteiro em funções.

Tal como nos guias anteriores, um algoritmo escrito em frases claras também é válido, desde que não deixe dúvidas. Com funções, isso quer dizer sobretudo deixar claro o que cada função recebe, o que devolve e em que casos.

## Neste guia

1. O que vais aprender
2. O que já sabes e vais usar
3. Razões para escrever funções
4. Escrever uma função
5. Chamar uma função
6. `devolver`
7. Funções que devolvem `true` ou `false`
8. Funções que recebem arrays
9. Decompor um problema em funções
10. Duas soluções certas, uma mais eficiente
11. Ler funções num fluxograma
12. Exemplo guiado: o resumo das notas de um teste
13. Erros frequentes
14. Palavras novas deste guia
15. Verificar o que aprendeste
16. O que vem a seguir

## O que vais aprender

No fim deste guia, consegues:

- escrever uma função com `Função` e `devolver`, com parâmetros, e dizer o que ela recebe e o que devolve;
- distinguir parâmetro de argumento, explicar as quatro fases de uma chamada e segui-la numa tabela de trace própria;
- escrever o contrato de uma função, com as pré-condições, e testá-la sozinha antes de a usar;
- decompor um problema em funções e escrever o algoritmo principal que as chama;
- comparar duas soluções certas contando voltas, e tirar de dentro de um ciclo um cálculo repetido;
- encontrar e corrigir os erros mais frequentes com funções, como uma função que calcula mas não devolve.

## O que já sabes e vais usar

- O contrato de entrada e saída, com exemplos calculados à mão: guia [01 Do enunciado ao problema delimitado](01-do-enunciado-ao-problema.md), secção "O contrato de entrada e saída".
- O caso extremo e a decisão escrita para os 0 livros, nos livros em caixas: guia [01](01-do-enunciado-ao-problema.md), na mesma secção.
- A decomposição, partir um problema em partes que se resolvem e verificam sozinhas: guia [01](01-do-enunciado-ao-problema.md), secção "Pensamento computacional".
- A forma do pseudocódigo das aulas e as frases claras: guia [02 Estado, sequência e representações](02-estado-sequencia-representacoes.md), secção "A forma de escrever pseudocódigo nas aulas".
- A indentação de quatro espaços, que mostra o que está dentro de quê: guia [02](02-estado-sequencia-representacoes.md), na mesma secção.
- As regras dos nomes das variáveis: guia [02](02-estado-sequencia-representacoes.md), secção "Variáveis".
- Os tipos `int`, `float`, `string` e `bool`: guia [02](02-estado-sequencia-representacoes.md), secção "Tipos de dados".
- O tipo à frente só na linha onde a variável nasce: guia [02](02-estado-sequencia-representacoes.md), secção "A linha onde a variável nasce".
- As constantes, como `const LIMITE = 50`: guia [02](02-estado-sequencia-representacoes.md), secção "Constantes".
- As contas com `/` e com `resto`: guia [02](02-estado-sequencia-representacoes.md), secção "Operadores aritméticos".
- As funções predefinidas, como `abs`, e o seu contrato: guia [02](02-estado-sequencia-representacoes.md), secção "Funções predefinidas".
- `ler valor` e `Escreve:`: guia [02](02-estado-sequencia-representacoes.md), secção "Entrada e saída: `ler valor` e `Escreve:`".
- A tabela de trace: guia [02](02-estado-sequencia-representacoes.md), secção "Tabela de trace".
- As figuras do fluxograma, com um só início e um só fim: guia [02](02-estado-sequencia-representacoes.md), secção "Fluxogramas".
- As condições, que dão `true` ou `false`: guia [03 Decisões e validação](03-decisoes-e-validacao.md), secção "Condições e o tipo `bool`".
- Os operadores `e`, `ou` e `não`: guia [03](03-decisoes-e-validacao.md), secção "Operadores lógicos: `e`, `ou` e `não`".
- O `Se`, o `Senão se` e o `Senão`: guia [03](03-decisoes-e-validacao.md), secções "Seleção simples", "Seleção composta" e "Seleção encadeada".
- As fronteiras e os três casos de teste de cada uma, abaixo, na fronteira e acima: guia [03](03-decisoes-e-validacao.md), secção "Fronteiras e casos de teste".
- A validação de uma entrada: guia [03](03-decisoes-e-validacao.md), secção "Casos válidos, casos inválidos e validação".
- Os arrays e o `Para cada`, que não dá nenhuma volta com um array vazio: guia [04 Repetição e arrays](04-repeticao-e-arrays.md), secção "Arrays".
- A tabela de iterações: guia [04](04-repeticao-e-arrays.md), secção "A tabela de iterações".
- O contador, o acumulador e a média calculada só quando há valores: guia [04](04-repeticao-e-arrays.md), secção "Contadores e acumuladores".
- A validação repetida: guia [04](04-repeticao-e-arrays.md), secção "Validação repetida".
- O `Parar`, a pesquisa e a bandeira: guia [04](04-repeticao-e-arrays.md), secção "Parar e Continuar".
- Os testes com zero voltas, uma volta e várias voltas: guia [04](04-repeticao-e-arrays.md), secção "Erros frequentes".
- A ordem para procurar um erro, em cinco passos: guia [04](04-repeticao-e-arrays.md), na mesma secção.

## Razões para escrever funções

No guia 02 usaste a função predefinida `abs`. Bastava escrever `abs(-7)` para obter 7. Não precisavas de saber como a conta era feita por dentro. Chegava-te o contrato: recebe um número e devolve a distância desse número a zero. Uma **função** é exatamente isso. É um pedaço de algoritmo com nome e com contrato, que se usa sem pensar no que tem lá dentro.

As funções predefinidas já vêm feitas. Mas as partes que se repetem nos teus algoritmos não vêm feitas em lado nenhum, como validar uma nota ou calcular uma média. Neste guia vais aprender a escrevê-las tu.

Há três razões para o fazer, e todas já as sentiste nos guias anteriores.

A primeira é não repetir. A validação de uma nota, `nota < 0 ou nota > 20`, apareceu no guia 03, voltou no guia 04 e vai voltar sempre que houver notas. Escrita uma vez, com um nome, usa-se em todo o lado. Se a escala mudar, muda-se num sítio só.

A segunda é ler melhor. Uma linha como `Se notaValida(nota)` lê-se como uma frase: se a nota é válida. A mesma linha com a condição inteira obriga quem lê a descodificar a condição. Só depois percebe o que se está a perguntar.

A terceira é a mais importante: testar por partes. Um algoritmo grande, com ciclos dentro de seleções dentro de ciclos, é difícil de testar de uma vez. Se estiver dividido em funções pequenas, cada uma com o seu contrato, testa-se cada função sozinha, com poucos casos. Só depois se junta tudo. Quando aparece um erro, já sabes que as funções estão certas, e por isso o erro está na forma como as juntaste. É a decomposição do guia 01, levada até ao fim.

## Escrever uma função

Começa por um caso. A área de um retângulo é o comprimento vezes a largura. Uma função que a calcula escreve-se assim:

```text
Função areaRetangulo(comprimento, largura)
    devolver comprimento * largura
```

Esta função recebe dois valores, a que dá os nomes `comprimento` e `largura`, e devolve o produto dos dois. Repara que escrever a função ainda não calcula nenhuma área, porque ainda não há números. Os números chegam quando alguém usar a função.

A primeira linha é o **cabeçalho**. Começa com a palavra `Função`, com maiúscula, como as outras palavras que começam uma instrução. A seguir vem o nome da função. Entre parênteses vêm os **parâmetros**, separados por vírgulas. Os parâmetros são os nomes que a função dá aos valores que vai receber.

Por baixo do cabeçalho, quatro espaços mais para dentro, está o **corpo** da função, com as instruções que ela executa. Tal como num `Se` ou num `Enquanto`, não há nenhuma palavra a fechar a função. É a indentação que diz onde ela acaba.

A palavra `devolver` termina a função e entrega um valor ao sítio onde a função foi usada. Escreve-se em minúsculas, seguida do valor a devolver. Esse valor pode ser uma variável, uma conta ou uma condição.

Em geral, uma função tem esta forma:

```text
Função nome(parametro1, parametro2)
    instruções da função
    devolver resultado
```

Uma função também tem contrato, como os problemas do guia 01. O **contrato de uma função** diz o que ela recebe, o que devolve e alguns exemplos, com o valor devolvido calculado à mão. Diz-se em três linhas, e vale a pena escrevê-lo sempre, por cima ou ao lado da função. O de `areaRetangulo` é este:

- recebe: o comprimento e a largura de um retângulo, números maiores do que zero, na mesma unidade;
- devolve: a área, na unidade ao quadrado;
- exemplos: `areaRetangulo(3, 2)` devolve `6`; `areaRetangulo(1.5, 1.5)` devolve `2.25`.

Repara em três pormenores da forma.

Os parâmetros não levam tipo. A função recebe os valores que lhe derem, e é o contrato que diz que valores são esses.

O nome da função segue as regras dos nomes das variáveis do guia 02. Começa com minúscula, sem espaços nem acentos, e cada palavra a partir da segunda começa com maiúscula. Deve dizer o que a função faz ou o que devolve, como `areaRetangulo`, `media` ou `notaValida`. Um nome como `calcular` ou `funcao1` não diz nada.

E as funções escrevem-se antes do **algoritmo principal**, a parte que as usa. O algoritmo principal começa na primeira linha encostada à margem depois da última função. Num algoritmo com funções, só ficam encostadas à margem as constantes, os cabeçalhos das funções e as linhas do algoritmo principal. Tudo o resto está indentado debaixo de alguma coisa.

## Chamar uma função

Escrever uma função não a executa. A função fica à espera, como uma receita num livro, que só dá um bolo quando alguém a segue. Uma função só se executa quando alguém a **chama**, escrevendo o seu nome com valores entre parênteses.

Antes de leres a explicação, tenta prever: com que valor fica `area`, e o que aparece no ecrã?

```text
Função areaRetangulo(comprimento, largura)
    devolver comprimento * largura

float area = areaRetangulo(3, 2)
Escreve: "Área: ", area
```

`area` fica com 6, e o ecrã mostra "Área: 6".

Leitura guiada: as duas primeiras linhas são a função, e sozinhas não fazem nada. O algoritmo começa na terceira linha, a primeira do algoritmo principal. Nessa linha, `areaRetangulo(3, 2)` chama a função com o 3 e o 2. A função multiplica-os e devolve 6, e o 6 fica guardado em `area`, que nasce nesta linha. A última linha escreve o texto e o valor de `area`.

Os valores escritos entre parênteses na chamada, o 3 e o 2, chamam-se **argumentos**.

A diferença entre parâmetro e argumento é a diferença entre a etiqueta de uma caixa e o que se põe lá dentro. O parâmetro é o nome que está no cabeçalho da função, como `comprimento`. O argumento é o valor que se dá na chamada, como o 3. Os parâmetros escrevem-se uma vez, na função. Os argumentos mudam de chamada para chamada.

### O que acontece numa chamada

Uma chamada executa-se sempre em quatro fases, por esta ordem:

1. **Os argumentos passam para os parâmetros**, pela ordem em que estão escritos. O primeiro argumento vai para o primeiro parâmetro, e o segundo para o segundo. Na chamada `areaRetangulo(3, 2)`, `comprimento` fica com 3 e `largura` fica com 2.
2. **O algoritmo salta para dentro da função** e executa o corpo, de cima para baixo, como qualquer outro algoritmo.
3. **Ao chegar a um `devolver`**, a função calcula o valor a devolver e termina imediatamente.
4. **O algoritmo regressa ao ponto onde a função foi chamada**, e a chamada é substituída pelo valor devolvido. A linha `float area = areaRetangulo(3, 2)` passa a ser, na prática, `float area = 6`. Depois continua a executar-se como qualquer atribuição.

A fase 4 é a que mais vezes se esquece. Pensa na chamada como um buraco na linha onde está escrita. O algoritmo vai à função buscar o valor, volta, e tapa o buraco com ele. Ao valor que a função entrega chama-se **valor devolvido**.

Por isso, uma chamada pode aparecer em qualquer sítio onde caberia um valor: numa atribuição, numa conta, num `Escreve:` ou numa condição. Antes de leres as respostas, prevê o que dão estas duas linhas, com a mesma função da área.

```text
Escreve: areaRetangulo(4, 5)
float soma = areaRetangulo(3, 2) + areaRetangulo(1, 1)
```

A primeira linha escreve 20. Na segunda, uma chamada devolve 6 e a outra devolve 1, e `soma` fica com 7.

Leitura guiada: na primeira linha, o buraco está dentro do `Escreve:`, e é tapado com 20 antes de se escrever. Na segunda linha há dois buracos na mesma conta. Cada chamada faz as suas quatro fases, e só depois se faz a soma, 6 mais 1.

### A ordem dos argumentos conta

Os argumentos passam para os parâmetros pela ordem, e não pelo nome. Pensa nesta função, que aplica um desconto em percentagem a um preço:

```text
Função precoComDesconto(preco, percentagem)
    devolver preco - preco * percentagem / 100
```

Antes de leres a resposta, prevê o que devolvem `precoComDesconto(50, 10)` e `precoComDesconto(10, 50)`.

A primeira devolve 45, porque aplica 10% a 50 euros. A segunda devolve 5, porque aplica 50% a 10 euros. São duas contas certas para dois problemas diferentes, e nenhuma dá aviso.

Leitura guiada: na primeira chamada, `preco` fica com 50 e `percentagem` com 10, e o desconto é de 5 euros. Na segunda, os valores trocam de parâmetro. `preco` fica com 10 e `percentagem` com 50. O desconto volta a ser de 5 euros, mas sobre outro preço.

Quem chama uma função tem de saber a ordem dos parâmetros, e é por isso que o contrato a diz. Trocar a ordem dos argumentos é o erro típico desta ideia. O que se vê é um resultado errado, sem nenhum aviso, porque as duas contas são possíveis. Evita-se confirmando a ordem dos parâmetros no cabeçalho, ou no contrato, antes de escrever a chamada.

### O trace de uma chamada

Uma chamada faz-se no trace com uma regra simples: cada chamada tem a sua própria tabela, só com as variáveis da função. A essa tabela chama-se **tabela própria** da chamada. Na tabela do algoritmo principal, a linha da chamada mostra o valor que regressou.

Antes de leres as tabelas, tenta fazê-las tu, para o algoritmo da área.

Algoritmo principal:

| Passo | Instrução executada | area | Ecrã |
| ---: | --- | ---: | --- |
| 0 | antes de começar | sem valor | nada |
| 1 | `float area = areaRetangulo(3, 2)`: chama a função, que devolve 6 | 6 | nada |
| 2 | `Escreve: "Área: ", area` | 6 | Área: 6 |

A chamada do passo 1, em tabela própria:

| Passo | Instrução executada | comprimento | largura | Valor devolvido |
| ---: | --- | ---: | ---: | --- |
| 0 | os argumentos passam para os parâmetros | 3 | 2 | nenhum ainda |
| 1 | `devolver comprimento * largura` | 3 | 2 | 6, e a função termina |

Leitura guiada: lê primeiro a tabela do algoritmo principal até ao passo 1. Nesse passo, salta para a tabela da chamada e segue-a até ao `devolver`. Volta com o 6, acaba a linha do passo 1 e passa ao passo 2.

Repara na linha 0 da tabela da chamada. Os parâmetros não começam "sem valor", como as variáveis do algoritmo principal. Começam com os argumentos, porque é isso que a fase 1 faz antes de a primeira linha do corpo se executar.

### As variáveis da função são da função

Os parâmetros e as variáveis que nascem dentro de uma função existem só enquanto a função está a ser executada. Quando a função devolve o seu valor, essas variáveis desaparecem. A estas variáveis chama-se **variáveis locais** da função.

Isto tem duas consequências que vais usar sempre.

A primeira é que duas variáveis com o mesmo nome, uma dentro e outra fora de uma função, são duas caixas diferentes. Imagina que o algoritmo principal tem uma variável `total`, e a função tem também uma variável `total`. Mexer numa não mexe na outra. É por isso que, no trace, cada chamada tem a sua tabela.

A segunda é uma regra das aulas. Uma função só usa os seus parâmetros e as suas variáveis locais. Tudo aquilo de que precisa chega-lhe pelos parâmetros, e tudo o que tem para dar sai pelo `devolver`. Uma função que fosse buscar uma variável do algoritmo principal, sem a receber, deixava de se poder testar sozinha. O seu resultado dependeria de uma coisa que não está no contrato. As constantes são a exceção. Escrevem-se no início, antes das funções, e valem em todo o lado, porque são regras do problema.

## `devolver`

A palavra `devolver` faz duas coisas ao mesmo tempo: entrega o valor e termina a função. As linhas do corpo que estiverem abaixo dela não se executam.

Uma função pode ter vários `devolver`, um em cada caminho de uma seleção. Antes de leres a tabela, prevê o que devolvem `maior(3, 8)` e `maior(8, 3)`.

```text
Função maior(a, b)
    Se a > b
        devolver a
    Senão
        devolver b
```

As duas chamadas devolvem 8. A chamada `maior(3, 8)`, em tabela própria:

| Passo | Instrução executada | a | b | Condição | Valor devolvido |
| ---: | --- | ---: | ---: | --- | --- |
| 0 | os argumentos passam para os parâmetros | 3 | 8 | nenhuma | nenhum ainda |
| 1 | `Se a > b` | 3 | 8 | `3 > 8` dá `false` | nenhum ainda |
| 2 | `devolver b` | 3 | 8 | nenhuma | 8, e a função termina |

Leitura guiada: como a condição é falsa, o algoritmo passa para o bloco do `Senão` e devolve `b`, que vale 8. Em `maior(8, 3)`, a condição `8 > 3` dá `true`, e devolve-se `a`, que também vale 8. Em cada chamada executa-se exatamente um dos dois `devolver`.

Há uma regra que esta função cumpre, e que todas as funções deste guia têm de cumprir. Em todos os caminhos possíveis, a função chega a um `devolver`. Pensa numa função que, para algum valor, chegasse ao fim do corpo sem passar por nenhum `devolver`. Não teria nada para entregar, e a linha que a chamou ficaria com um buraco por tapar. É o erro mais frequente com funções, e a secção "Erros frequentes" mostra-o com números.

### `devolver` não é `Escreve:`

As duas parecem dar um resultado, e fazem coisas muito diferentes. `Escreve:` mostra um valor a quem está a usar o algoritmo, no ecrã, e o valor não vai para mais lado nenhum. `devolver` entrega o valor ao algoritmo que chamou a função. Esse algoritmo pode guardá-lo, fazer contas com ele ou decidir o que fazer a seguir.

Por isso, nas aulas, as funções que calculam devolvem, e quem escreve no ecrã é o algoritmo principal. Separar o cálculo da apresentação é o que permite reutilizar a função noutro algoritmo, com outro ecrã.

## Funções que devolvem `true` ou `false`

Uma função pode devolver o resultado de uma condição, que é `true` ou `false`. São as funções que respondem a perguntas de sim ou não, e usam-se diretamente num `Se` ou num `Enquanto`.

```text
const NOTA_MINIMA = 0
const NOTA_MAXIMA = 20

Função notaValida(nota)
    Se nota >= NOTA_MINIMA e nota <= NOTA_MAXIMA
        devolver true
    Senão
        devolver false
```

O contrato: recebe uma nota, um número inteiro. Devolve `true` se estiver na escala de 0 a 20, incluindo os extremos, e `false` se não estiver.

Os casos de teste escolhem-se nas fronteiras, como no guia 03. Para cada fronteira, testa-se o valor imediatamente abaixo, o próprio valor da fronteira e o valor imediatamente acima. Aqui há duas fronteiras, a do 0 e a do 20. Antes de leres a tabela, prevê o que a função devolve em cada caso.

| Chamada | Devolve | Porque é que este caso foi escolhido |
| --- | --- | --- |
| `notaValida(-1)` | `false` | Imediatamente abaixo da fronteira do 0 |
| `notaValida(0)` | `true` | O valor da fronteira de baixo, que é válido |
| `notaValida(1)` | `true` | Imediatamente acima da fronteira do 0 |
| `notaValida(19)` | `true` | Imediatamente abaixo da fronteira do 20 |
| `notaValida(20)` | `true` | O valor da fronteira de cima, que é válido |
| `notaValida(21)` | `false` | Imediatamente acima da fronteira do 20 |

Como a condição já dá `true` ou `false`, a função pode devolvê-la diretamente, numa linha só:

```text
Função notaValida(nota)
    devolver nota >= NOTA_MINIMA e nota <= NOTA_MAXIMA
```

As duas versões estão certas e devolvem o mesmo nos seis casos. A primeira mostra melhor a decisão, e a segunda é mais curta. Usa a que perceberes melhor.

No algoritmo principal, depois das constantes e da função, a chamada aparece no sítio da condição. Antes de leres a resposta, prevê o que aparece no ecrã se a pessoa escrever 20, e se escrever 21.

```text
Escreve: "Nota?"
int nota = ler valor
Se notaValida(nota)
    Escreve: "Nota aceite"
Senão
    Escreve: "Nota inválida"
```

Com 20, `notaValida(20)` devolve `true`, e aparece "Nota aceite". Com 21, devolve `false`, e aparece "Nota inválida".

Leitura guiada: o `Se` precisa de um `true` ou de um `false`, e é isso que a chamada lhe dá. A linha lê-se como uma frase: se a nota é válida, aceita-a.

A validação repetida do guia 04 também fica mais legível com uma função. O ciclo pergunta o contrário: `Enquanto notaValida(nota) == false`.

## Funções que recebem arrays

Um parâmetro pode receber um array inteiro. Dentro da função, percorre-se como qualquer array, com `Para cada` ou com o índice.

```text
Função media(valores)
    int quantidade = 0
    int total = 0
    Para cada valor em valores
        quantidade = quantidade + 1
        total = total + valor
    devolver total / quantidade
```

É o contador e o acumulador do guia 04, agora dentro de uma função. A função conta os elementos porque, no pseudocódigo das aulas, ainda não se pede a um array quantos elementos tem.

Antes de leres a tabela, calcula de cabeça o que devolve `media([12, 7, 20, 5])`. É o array das pontuações do guia 04.

A chamada `media([12, 7, 20, 5])`, em tabela própria, com uma linha por volta:

| Volta | valor | quantidade no fim da volta | total no fim da volta |
| --- | ---: | ---: | ---: |
| antes do ciclo | sem valor | 0 | 0 |
| 1.ª | 12 | 1 | 12 |
| 2.ª | 7 | 2 | 19 |
| 3.ª | 20 | 3 | 39 |
| 4.ª | 5 | 4 | 44 |

A função devolve 44 / 4, que é 11.

Leitura guiada: na fase 1, o array passa inteiro para o parâmetro `valores`. O ciclo dá uma volta por elemento, e no fim `quantidade` vale 4 e `total` vale 44. O `devolver` faz a conta e termina a função.

O contrato desta função tem uma parte nova, e é das mais importantes deste guia:

- recebe: um array de números, com pelo menos um elemento;
- devolve: a média desses números, com parte decimal;
- exemplos: `media([12, 7, 20, 5])` devolve `11`; `media([10])` devolve `10`.

A frase "com pelo menos um elemento" é uma condição que tem de ser verdadeira antes de a função ser chamada. A uma condição destas chama-se **pré-condição**. Com um array vazio, o ciclo dá zero voltas, e a função faria 0 / 0, que não tem resultado. O contrato não esconde o problema. Diz que esse caso não está coberto, e passa a responsabilidade a quem chama. Antes de chamar `media`, o algoritmo principal tem de garantir que o array não está vazio.

É a mesma decisão dos livros em caixas, no guia 01. Com 0 livros, o contrato dizia por palavras que não há última caixa. O que interessa é que alguém tenha pensado no caso e o tenha escrito.

Também se podia escolher outra solução, como devolver 0 para o array vazio. Mas uma média de 0 também pode ser a média de notas todas iguais a 0. Quem recebesse o 0 não saberia qual dos dois casos era. Uma pré-condição escrita é mais honesta.

## Decompor um problema em funções

Agora que sabes escrever e chamar funções, falta decidir que funções escrever. É a decomposição do guia 01, com uma regra a mais. Os passos são sempre estes, e o exemplo guiado segue-os um a um.

1. **Escrever o contrato do problema inteiro**: as entradas, as saídas, as restrições e os exemplos concretos, calculados à mão.
2. **Decompor em partes**, cada uma com um objetivo que se diz numa frase. Cada parte que recebe dados e produz um resultado é candidata a função.
3. **Escrever o contrato de cada função**: o que recebe, o que devolve, as pré-condições e dois ou três exemplos, incluindo um caso extremo.
4. **Escrever cada função e testá-la sozinha**, antes de a usar, com os exemplos do contrato e com os valores de cada fronteira.
5. **Escrever o algoritmo principal**, que lê os dados, chama as funções e mostra os resultados.
6. **Fazer o teste completo**: executar à mão um dos exemplos do passo 1, do princípio ao fim, chamada a chamada, sem computador.

Os testes do passo 4 escolhem-se a partir do contrato, antes de olhar para a solução. A estes testes chama-se **testes independentes da solução**. Testam o que a função devia fazer, e não o que tu achas que ela faz.

Uma boa função faz uma coisa só, e o seu nome diz qual. Quando escreveres o objetivo de uma função, repara se precisas de dizer "e", como em "calcula a média e conta as positivas". Se precisares, provavelmente são duas funções.

## Duas soluções certas, uma mais eficiente

Dois algoritmos podem estar os dois certos e dar sempre os mesmos resultados, e um deles fazer muito mais trabalho do que o outro. Nesta disciplina não vais medir esse trabalho com fórmulas, que ficam para o 11.º ano. Vais medi-lo de forma intuitiva, contando as voltas dos ciclos num exemplo pequeno.

Imagina que queres contar quantas notas de um array `notas` estão acima da média. Esta solução está certa:

```text
int acima = 0
Para cada nota em notas
    Se nota > media(notas)
        acima = acima + 1
```

Antes de leres a conta, tenta prever: com 6 notas, quantas voltas de ciclo faz esta solução, contando também as voltas dentro da função `media`?

Olha para o que acontece em cada volta. A condição chama `media(notas)`, e a função percorre o array inteiro para calcular a média. O ciclo de fora dá 6 voltas, e em cada uma a função dá mais 6. São 6 vezes 6, ou seja, 36 voltas dentro da função, mais as 6 do ciclo de fora. Ao todo, 42 voltas. E a média calculada é sempre a mesma, porque as notas não mudam.

Esta solução dá os mesmos resultados com muito menos trabalho:

```text
float mediaDasNotas = media(notas)
int acima = 0
Para cada nota em notas
    Se nota > mediaDasNotas
        acima = acima + 1
```

A média calcula-se uma vez, antes do ciclo, e guarda-se numa variável. São 6 voltas dentro da função e 6 no ciclo: 12 voltas.

| Notas no array | Voltas com a média dentro do ciclo | Voltas com a média calculada antes |
| ---: | ---: | ---: |
| 4 | 20 | 8 |
| 6 | 42 | 12 |
| 10 | 110 | 20 |

Repara como a diferença cresce. Com 10 notas, a primeira solução já faz mais de cinco vezes o trabalho da segunda. A regra que daqui sai é simples. Um valor que não muda dentro de um ciclo calcula-se antes do ciclo. O resultado não muda, e o trabalho diminui.

## Ler funções num fluxograma

Como nos guias anteriores, os fluxogramas são para saberes ler, e este tema não tem laboratório. Num fluxograma, cada função desenha-se à parte, como um fluxograma pequeno. O oval de início tem o nome da função e os parâmetros, como `( Função media(valores) )`. O oval do fim tem o `devolver`, como `( devolver total / quantidade )`.

No fluxograma do algoritmo principal, a linha da chamada aparece num retângulo, como qualquer atribuição, por exemplo `[ float m = media(notas) ]`. Quem lê sabe que, nesse retângulo, o caminho salta para o fluxograma da função e volta com o valor.

Antes de leres a explicação, segue com o dedo o algoritmo da área nestes dois fluxogramas. Por que figuras passas, e por que ordem?

```text
     O algoritmo principal                       A função

          ( Início )                ( Função areaRetangulo(comprimento, largura) )
               |                                        |
               ↓                                        ↓
[ float area = areaRetangulo(3, 2) ]        ( devolver comprimento * largura )
               |
               ↓
   / Escreve: "Área: ", area /
               |
               ↓
            ( Fim )
```

O dedo parte do início do algoritmo principal e chega ao retângulo da chamada. Aí salta para o fluxograma da função, com o 3 e o 2. Passa do oval de início ao oval do `devolver` e volta ao retângulo com o 6. Depois segue para o `Escreve:` e acaba no fim. É a mesma ordem das quatro fases de uma chamada.

## Exemplo guiado: o resumo das notas de um teste

### Passo 1: o enunciado

> Um professor guardou num array as notas de um teste, todas inteiras: `notas = [14, 9, 17, 10, 6, 16]`. Quer um algoritmo que, antes de mais nada, confirme que todas as notas estão na escala de 0 a 20. Se houver alguma nota fora da escala, o algoritmo escreve "Há notas inválidas" e não calcula mais nada. Se estiverem todas certas, escreve a média da turma e quantas notas são positivas, ou seja, 10 ou mais.

### Passo 2: o contrato do problema

A entrada é um array de notas inteiras, com pelo menos uma nota. O enunciado dá um array concreto, mas o algoritmo tem de servir para qualquer turma. Por isso, os testes vão usar outros arrays.

As saídas dependem do caso. Quando alguma nota está fora da escala, a saída é a mensagem "Há notas inválidas". Quando estão todas certas, são duas: a média, com parte decimal, e o número de positivas.

As restrições são as do enunciado. A escala vai de 0 a 20, com os extremos. Uma positiva é 10 ou mais. Com uma nota inválida, não se calcula nada.

Os exemplos concretos calculam-se à mão. Antes de leres a tabela, calcula tu a saída de cada array.

| Notas | Saída esperada | Porque é que este caso foi escolhido |
| --- | --- | --- |
| `[14, 9, 17, 10, 6, 16]` | Média 12; 4 positivas | O caso do enunciado: 14 + 9 + 17 + 10 + 6 + 16 = 72, e 72 / 6 = 12; positivas: 14, 17, 10 e 16 |
| `[10]` | Média 10; 1 positiva | Uma só nota, e na fronteira da positiva |
| `[9]` | Média 9; 0 positivas | Uma só nota, do outro lado da fronteira |
| `[0, 20]` | Média 10; 1 positiva | Os dois extremos da escala, que são válidos |
| `[12, 21, 8]` | Há notas inválidas | Uma nota fora da escala, no meio do array |

Estes exemplos são do problema inteiro. As fronteiras de cada regra, com os três valores do guia 03, testam-se no passo 5, função a função.

### Passo 3: decompor em funções

O problema tem três perguntas, e cada uma é uma função:

| Função | Objetivo numa frase |
| --- | --- |
| `notaValida(nota)` | Diz se uma nota está na escala |
| `media(valores)` | Calcula a média de um array de números |
| `contarPositivas(notas)` | Conta quantas notas de um array são positivas |

O algoritmo principal usa as três. Percorre as notas com `notaValida` para confirmar que estão todas certas. Se estiverem, chama `media` e `contarPositivas` e mostra os resultados.

Repara que `media` recebe "valores" e não "notas". A média é uma conta que serve para qualquer array de números, e o nome do parâmetro diz isso. A mesma função calcularia a média de temperaturas ou de pontuações. `contarPositivas` é própria das notas, porque "positiva" é uma regra das notas.

### Passo 4: o contrato de cada função

**`notaValida(nota)`**: recebe uma nota inteira; devolve `true` se estiver entre 0 e 20, incluindo os extremos, e `false` se não estiver. Exemplos: -1 dá `false`; 0 dá `true`; 20 dá `true`; 21 dá `false`.

**`media(valores)`**: recebe um array de números com pelo menos um elemento, a pré-condição; devolve a média. Exemplos: `[14, 9, 17, 10, 6, 16]` dá 12; `[10]` dá 10; `[0, 20]` dá 10.

**`contarPositivas(notas)`**: recebe um array de notas válidas; devolve quantas são 10 ou mais. Exemplos: `[14, 9, 17, 10, 6, 16]` dá 4; `[9]` dá 0; `[10]` dá 1; `[]` dá 0.

Repara no último exemplo de `contarPositivas`. Esta função, ao contrário de `media`, funciona com um array vazio. O ciclo dá zero voltas, e o contador fica a 0, que é a resposta certa. Por isso, o seu contrato não precisa de pré-condição sobre o tamanho.

### Passo 5: as funções e os seus testes

```text
const NOTA_MINIMA = 0
const NOTA_MAXIMA = 20
const LIMIAR_POSITIVA = 10

Função notaValida(nota)
    devolver nota >= NOTA_MINIMA e nota <= NOTA_MAXIMA

Função media(valores)
    int quantidade = 0
    int total = 0
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

Antes de escrever o algoritmo principal, testa-se cada função sozinha. Um teste de uma função é uma chamada com um argumento escolhido e o valor que se espera que ela devolva. Os casos vêm do contrato e das fronteiras. Para cada fronteira, há o valor de baixo, o da fronteira e o de cima, como no guia 03. Para as funções que recebem arrays, há um array com um elemento e um com vários, como no guia 04. Há também um array vazio, quando o contrato o deixa.

| Chamada | Esperado | Devolvido no trace | Certo? |
| --- | --- | --- | --- |
| `notaValida(-1)` | `false` | `-1 >= 0` dá `false`; `false` e qualquer coisa dá `false` | sim |
| `notaValida(0)` | `true` | `0 >= 0` e `0 <= 20`: `true` e `true` dá `true` | sim |
| `notaValida(1)` | `true` | `true` e `true` dá `true` | sim |
| `notaValida(19)` | `true` | `true` e `true` dá `true` | sim |
| `notaValida(20)` | `true` | `20 >= 0` e `20 <= 20`: `true` e `true` dá `true` | sim |
| `notaValida(21)` | `false` | `21 <= 20` dá `false`; `true` e `false` dá `false` | sim |
| `media([10])` | 10 | uma volta; 10 / 1 = 10 | sim |
| `media([0, 20])` | 10 | duas voltas; 20 / 2 = 10 | sim |
| `media([14, 9, 17, 10, 6, 16])` | 12 | seis voltas; 72 / 6 = 12, com a tabela no passo 7 | sim |
| `contarPositivas([])` | 0 | zero voltas | sim |
| `contarPositivas([9])` | 0 | uma volta; `9 >= 10` dá `false` | sim |
| `contarPositivas([10])` | 1 | uma volta; `10 >= 10` dá `true` | sim |
| `contarPositivas([11])` | 1 | uma volta; `11 >= 10` dá `true` | sim |
| `contarPositivas([14, 9, 17, 10, 6, 16])` | 4 | seis voltas, com a tabela no passo 7 | sim |

As três funções passam em todos os testes. A partir daqui, se o algoritmo completo der um resultado errado, o erro não está dentro delas. Está na forma como o algoritmo principal as usa.

### Passo 6: o algoritmo principal

O algoritmo principal escreve-se a seguir às funções, encostado à margem:

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

As decisões, uma a uma:

1. A validação usa uma bandeira, como a pesquisa do guia 04, mas ao contrário. Aqui a bandeira começa em `true`, porque se parte do princípio de que as notas estão todas certas. Passa a `false` à primeira nota inválida, e o `Parar` evita olhar para o resto, porque basta uma.
2. `Se todasValidas` usa a bandeira diretamente como condição, porque ela já é `true` ou `false`. É o mesmo que `Se todasValidas == true`.
3. As duas funções de cálculo só são chamadas dentro do `Se`, quando se sabe que as notas são válidas. A pré-condição de `media` fica garantida pelo contrato do problema, que diz que há pelo menos uma nota.
4. Os valores devolvidos guardam-se em variáveis com nomes que dizem o que são, e só depois se escrevem. Quem escreve no ecrã é o algoritmo principal, e não as funções.

### Passo 7: o teste completo, chamada a chamada

Antes de leres as tabelas, faz tu o teste completo com o array do enunciado. Confirma que dá o que o passo 2 previu.

O ciclo da validação, com as chamadas a `notaValida`:

| Volta | nota | Chamada | Devolvido | `== false`? | todasValidas no fim da volta |
| ---: | ---: | --- | --- | --- | --- |
| 1.ª | 14 | `notaValida(14)` | `true` | `false` | `true` |
| 2.ª | 9 | `notaValida(9)` | `true` | `false` | `true` |
| 3.ª | 17 | `notaValida(17)` | `true` | `false` | `true` |
| 4.ª | 10 | `notaValida(10)` | `true` | `false` | `true` |
| 5.ª | 6 | `notaValida(6)` | `true` | `false` | `true` |
| 6.ª | 16 | `notaValida(16)` | `true` | `false` | `true` |

A bandeira ficou em `true`, e o algoritmo entra no `Se`.

A chamada `media(notas)`, em tabela própria. O argumento é o array inteiro, que passa para o parâmetro `valores`:

| Volta | valor | quantidade no fim da volta | total no fim da volta |
| ---: | ---: | ---: | ---: |
| antes do ciclo | sem valor | 0 | 0 |
| 1.ª | 14 | 1 | 14 |
| 2.ª | 9 | 2 | 23 |
| 3.ª | 17 | 3 | 40 |
| 4.ª | 10 | 4 | 50 |
| 5.ª | 6 | 5 | 56 |
| 6.ª | 16 | 6 | 72 |

A função devolve 72 / 6, que é 12, e o algoritmo regressa à linha `float mediaDaTurma = media(notas)`. Essa linha passa a valer `float mediaDaTurma = 12`.

A chamada `contarPositivas(notas)`, em tabela própria:

| Volta | nota | `nota >= 10`? | positivas no fim da volta |
| ---: | ---: | --- | ---: |
| 1.ª | 14 | `true` | 1 |
| 2.ª | 9 | `false` | 1 |
| 3.ª | 17 | `true` | 2 |
| 4.ª | 10 | `true` | 3 |
| 5.ª | 6 | `false` | 3 |
| 6.ª | 16 | `true` | 4 |

A função devolve 4. O ecrã mostra "Média: 12" e "Positivas: 4", como o contrato previa.

Repara que as tabelas das duas funções têm cada uma as suas variáveis. A variável `nota` de `contarPositivas` não tem nada a ver com a variável `nota` do ciclo de validação do algoritmo principal. Têm o mesmo nome, mas são caixas diferentes, de sítios diferentes.

Com `[12, 21, 8]`, o ciclo da validação para na segunda volta. `notaValida(21)` devolve `false`, a bandeira passa a `false` e o `Parar` termina o ciclo. O `Se todasValidas` é falso, e o ecrã mostra "Há notas inválidas". `media` e `contarPositivas` nunca chegam a ser chamadas.

### Passo 8: o dossiê do problema

O que fizeste nos passos 2 a 7 é um **dossiê algorítmico**. Tem tudo o que é preciso para outra pessoa perceber, verificar e implementar a solução numa linguagem de programação, sem te fazer nenhuma pergunta. Um dossiê tem sempre estas partes:

| Parte | No exemplo guiado |
| --- | --- |
| Análise: o contrato do problema, com exemplos concretos | Passo 2 |
| Decomposição em funções, com o objetivo de cada uma | Passo 3 |
| O contrato de cada função | Passo 4 |
| O pseudocódigo das funções e do algoritmo principal | Passos 5 e 6 |
| Os testes de cada função e o teste completo | Passos 5 e 7 |

É este dossiê que leva o algoritmo para o Python. Os testes que escreveste aqui, à mão, vão ser os mesmos que vais pôr o computador a executar. Se o programa em Python der outro resultado, o erro está na tradução, e não no raciocínio.

## Erros frequentes

Quando uma função tua falha, procura o erro pela mesma ordem do guia 04. Escreve o caso que falhou, com o resultado que o enunciado pede e o que apareceu. Escreve numa frase o que achas que causa o erro. Confirma essa frase no caso mais curto que ainda mostra o erro, e numa função isso faz-se com a tabela própria da chamada. Depois corrige a instrução que causa o erro, e volta a testar todos os casos, também os que já davam certo.

Os erros desta secção encontram-se assim. A troca da ordem dos argumentos ficou na secção "A ordem dos argumentos conta".

### A função calcula, mas não devolve

```text
Função media(valores)
    int quantidade = 0
    int total = 0
    Para cada valor em valores
        quantidade = quantidade + 1
        total = total + valor
    float resultado = total / quantidade
```

O que se vê: a conta está certa, e o resultado fica guardado em `resultado`. Mas a função acaba sem `devolver`, e `resultado` é uma variável local, que desaparece quando a função termina. No algoritmo principal, a linha `float m = media(notas)` fica sem nada para pôr em `m`. No trace vê-se logo, porque a tabela da chamada não tem nenhuma linha com valor devolvido.

Porque acontece: guardar o resultado numa variável parece o fim do trabalho. Mas guardar não é entregar.

Como se corrige: acrescenta `devolver resultado` como última linha do corpo.

### `devolver` dentro do ciclo, no sítio errado

```text
Função existe(valores, procurado)
    Para cada valor em valores
        Se valor == procurado
            devolver true
        Senão
            devolver false
```

O que se vê: esta função devia dizer se `procurado` está no array. Com `existe([3, 8], 8)`, a primeira volta compara 3 com 8, a condição é falsa, e o `Senão` devolve `false`. A função termina na primeira volta, sem nunca olhar para o 8.

Porque acontece: a função decide "não está" ao primeiro elemento diferente. Só se pode decidir isso depois de ver todos.

Como se corrige: tira o `Senão` e põe o `devolver false` depois do ciclo, encostado ao `Para cada`. Só se chega lá se o ciclo acabar sem ter encontrado o valor. Com um array vazio, a versão errada nem sequer chega a nenhum `devolver`, e a versão certa devolve `false`.

### Usar uma variável do algoritmo principal dentro da função

```text
Função precoFinal(preco)
    devolver preco - desconto

int desconto = 5
float total = precoFinal(30)
```

O que se vê: a função usa `desconto`, que não recebeu. Testada sozinha, com `precoFinal(30)`, a tabela da chamada só tem a coluna `preco`, e não há de onde tirar o valor de `desconto`. Usada noutro algoritmo, onde `desconto` não exista ou tenha outro valor, dá outro resultado, ou nenhum.

Porque acontece: no algoritmo principal, `desconto` está à vista, e parece que a função também a vê. Mas a função só tem o que lhe chega pelos parâmetros.

Como se corrige: tudo o que a função usa chega pelos parâmetros, exceto as constantes. Aqui, o cabeçalho passa a `Função precoFinal(preco, desconto)`, e a chamada passa a `precoFinal(30, desconto)`, que devolve 25.

### Chamar a função e não usar o valor devolvido

O que se vê: uma linha só com `media(notas)`, sem guardar nem escrever o resultado. A função executa-se e devolve a média, mas o valor perde-se. Nada aparece no ecrã, e nenhuma variável muda.

Porque acontece: parece que chamar a função chega para ela fazer o trabalho. Mas o trabalho de uma função que devolve é entregar um valor, e alguém tem de o receber.

Como se corrige: uma chamada a uma função que devolve um valor aparece sempre dentro de alguma coisa. Pode ser uma atribuição, uma conta, um `Escreve:` ou uma condição, como em `float m = media(notas)`.

### `Escreve:` em vez de `devolver`

```text
Função media(valores)
    int quantidade = 0
    int total = 0
    Para cada valor em valores
        quantidade = quantidade + 1
        total = total + valor
    Escreve: "Média: ", total / quantidade
```

O que se vê: a média aparece no ecrã, e por isso a função parece certa. Mas só serve para mostrar a média. O algoritmo principal não a consegue comparar com outra coisa nem usá-la numa conta. Uma linha como `Se media(notas) >= 10` não tem com que comparar, porque a função não devolveu nada.

Porque acontece: nos guias anteriores, os algoritmos escreviam os resultados no fim, e é natural continuar a fazê-lo. Numa função, escrever não é entregar.

Como se corrige: troca o `Escreve:` por `devolver total / quantidade`. Quem escreve no ecrã é o algoritmo principal, com o valor que a função devolveu.

### Esquecer a pré-condição

O que se vê: o algoritmo dá os resultados certos com todos os arrays testados, e falha com o array vazio. A função `media` dá zero voltas, `quantidade` e `total` ficam a 0, e a conta do `devolver` é 0 / 0, que não tem resultado.

Porque acontece: chamou-se `media` com um array que pode estar vazio, sem confirmar antes que ele tem pelo menos um elemento. Com qualquer array que tenha elementos, a chamada funciona. Por isso, o erro só aparece a quem testa o caso vazio.

Como se corrige: antes de chamar uma função, lê o seu contrato e confirma que cumpres as pré-condições. Se o array pode estar vazio, conta primeiro os elementos, como no guia 04. Depois chama `media` só dentro de um `Se` que confirma que há pelo menos um. No exemplo guiado, é o contrato do problema que garante a pré-condição, porque diz que a entrada tem pelo menos uma nota.

### Cálculos repetidos dentro de um ciclo

O que se vê: o resultado está certo, e por isso nenhuma entrada mostra este erro no ecrã. O que o revela é contar as voltas com um array de vários elementos. Com 6 notas, a versão com a média dentro do ciclo faz 42 voltas, e a versão com a média calculada antes faz 12.

Porque acontece: dentro do ciclo chama-se uma função cujo resultado não muda de volta para volta. É o caso de `media(notas)` na comparação de cada nota com a média. Parece natural escrever a chamada no sítio onde o valor é preciso.

Como se corrige: calcula o valor uma vez, antes do ciclo, e guarda-o numa variável, como na secção "Duas soluções certas, uma mais eficiente". Quanto mais elementos tiver o array, maior é a diferença.

## Palavras novas deste guia

- Função: um pedaço de algoritmo com nome e com contrato, que recebe valores e devolve um resultado.
- Cabeçalho: a primeira linha de uma função, com `Função`, o nome e os parâmetros entre parênteses.
- Parâmetro: o nome que a função dá, no cabeçalho, a um valor que vai receber.
- Corpo: as instruções indentadas por baixo do cabeçalho, que a função executa.
- `devolver`: entrega um valor ao sítio onde a função foi chamada e termina a função.
- Contrato de uma função: o que a função recebe, o que devolve e alguns exemplos, com o valor devolvido calculado à mão.
- Algoritmo principal: a parte do algoritmo que usa as funções, escrita depois delas, encostada à margem.
- Chamar uma função: escrever o seu nome com valores entre parênteses, para ela se executar.
- Argumento: o valor que se dá a uma função na chamada.
- Valor devolvido: o valor que a função entrega, e que substitui a chamada na linha onde ela está.
- Tabela própria: a tabela de trace de uma chamada, só com as variáveis da função.
- Variável local: um parâmetro, ou uma variável que nasce dentro de uma função; só existe enquanto a função se executa.
- Pré-condição: uma condição que tem de ser verdadeira antes de a função ser chamada, como "com pelo menos um elemento".
- Testes independentes da solução: testes com casos escolhidos a partir do contrato, antes de olhar para a solução.
- Teste completo: a execução à mão de um exemplo, do princípio ao fim, chamada a chamada.
- Dossiê algorítmico: a análise, a decomposição, os contratos, o pseudocódigo e os testes de um problema, para outra pessoa o perceber, verificar e implementar.

## Verificar o que aprendeste

Usa estas perguntas para te testares. Responde a cada uma sem olhar para o guia. Se não conseguires, volta à secção que explica a ideia.

1. Quais são as três razões para escrever funções? Dá um exemplo teu para cada uma.
2. Escreve a função `triplo(numero)`, que devolve o triplo de um número, e o seu contrato, com dois exemplos.
3. Na linha `float valor = precoComDesconto(80, 25)`, quais são os argumentos? E os parâmetros? Quanto fica em `valor`?
4. Explica por palavras tuas as quatro fases de uma chamada. Depois faz o trace de `areaRetangulo(4, 5)` em tabela própria.
5. Uma função e o algoritmo principal têm, cada um, uma variável `total`. Se a função mudar o seu `total`, o que acontece ao do algoritmo principal? Porque é que uma função só usa os seus parâmetros?
6. Escreve a função `sinal(numero)`, que devolve `"positivo"`, `"negativo"` ou `"zero"`. Com que valores confirmas que todos os caminhos chegam a um `devolver`?
7. Qual é a diferença entre `devolver` e `Escreve:`? Dá um exemplo em que só a versão com `devolver` serve.
8. Escreve a função `idadeValida(idade)`, que devolve `true` para idades de 0 a 120, incluindo os extremos, e usa-a num `Se`. Que seis valores escolhes para a testar?
9. Porque é que `media` tem uma pré-condição e `contarPositivas` não? O que devolve `contarPositivas([])`?
10. Quais são os seis passos para decompor um problema em funções? Em que passo se escolhem os testes, e porque é que se escolhem antes de olhar para a solução?
11. Com 8 notas no array, quantas voltas faz a solução com a média dentro do ciclo? E a solução com a média calculada antes?
12. Na função `existe` errada, da secção "Erros frequentes", que chamada mostra o erro? Com `existe([8, 3], 8)`, a versão errada dá a resposta certa? Porquê?
13. Quais são as cinco partes de um dossiê algorítmico? Em que passo do exemplo guiado está cada uma?

## O que vem a seguir

Para praticar este tema, faz a [ficha de exercícios](05-funcoes-e-modelo-integrado-exercicios.md). Tem sete exercícios, do mais simples ao mais completo. O último é o dossiê de um problema pequeno, que junta toda a algoritmia. Os testes desse dossiê estão na secção opcional "Para ires mais longe", para quem quiser completá-lo. Este tema não tem laboratório.

A algoritmia fecha com três projetos, todos jogos, cada um um pouco mais difícil do que o anterior. Num projeto juntas tudo o que aprendeste num problema só. Leva-lo do enunciado até um algoritmo testado. Pelo caminho fazes o contrato, a tabela de casos escrita antes do algoritmo, o algoritmo, os testes e a correção do que falhar.

O [projeto 1, Duelo de dados](05-projeto-1-duelo-de-dados.md), fazes com o professor ao quadro. É aí que treinas por extenso a rotina da depuração, os cinco passos que os guias 04 e 05 apresentam nos erros frequentes. O [projeto 2, Adivinha o número](05-projeto-2-adivinha-o-numero.md), fazes em pares, com o professor a confirmar cada passo. Os dois ficam no teu portefólio. Não contam para a avaliação prática, mas o trabalho neles conta no empenho e na autonomia. O terceiro projeto é a avaliação prática individual da unidade, com um problema novo, e nela podes consultar os dois primeiros. O dossiê do exercício 7 da ficha é um bom treino para os três.

Com este tema acaba a algoritmia. O tema seguinte é o primeiro do Python, Do pseudocódigo ao Python. O Python é a primeira linguagem de programação do ano, e vais reconhecer quase tudo. O pseudocódigo das aulas foi escrito para passar para o Python quase linha a linha:

- `Função media(valores)` passa a `def media(valores):`;
- `devolver` passa a `return`;
- `Enquanto` passa a `while`;
- `Para cada` passa a `for`.

A indentação continua a mostrar o que está dentro de quê. O que muda é que, em vez de fazeres o trace à mão, vais pôr o computador a executar os teus algoritmos. Os teus dossiês vão dizer-te se ele faz o que devia.

![Rodapé](../imagens/rodape.png)
