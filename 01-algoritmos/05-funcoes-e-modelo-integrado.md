![Cabeçalho](../imagens/cabecalho.png)

# Funções e modelo integrado

| Identificação | Valor |
| --- | --- |
| Disciplina | Fundamentos de Programação, 10.º ano, Desenvolvimento de Software |
| Unidade de competência | UC00245, Desenvolver algoritmos |
| Percurso | Algoritmos, quinto guia |

## O que vais aprender

Os algoritmos do guia anterior já eram grandes, e começavam a repetir partes de problema para problema: somar um array, calcular uma média com cuidado com o zero, procurar um valor, validar uma nota. Neste guia vais aprender a dar nome a essas partes, escrevendo as tuas próprias funções, e a juntar tudo o que aprendeste na algoritmia num algoritmo completo, organizado em funções, testado e pronto para passar para o Python.

No fim deves conseguir:

- escrever uma função com `Função` e `devolver`, com parâmetros, e dizer o que ela recebe e o que devolve;
- distinguir parâmetro de argumento, e explicar o que acontece numa chamada: os argumentos passam para os parâmetros e o valor devolvido regressa ao ponto da chamada;
- seguir uma chamada numa tabela de trace, com as variáveis da função à parte;
- escrever o contrato de uma função e testá-la sozinha, com casos normais e extremos, antes de a usar;
- decompor um problema em funções e escrever o algoritmo principal que as chama;
- comparar duas soluções corretas pelo número de passos e retirar um cálculo repetido;
- encontrar e corrigir os erros mais frequentes com funções, como uma função que calcula mas não devolve.

## O que já sabes e vais usar

Na aula de 29 de setembro já escreveste as primeiras funções em pseudocódigo, com parâmetros, argumentos e devolver. Este guia arruma essa matéria na forma que usamos nas aulas, explica o que acontece por dentro de uma chamada e mostra como se decompõe um problema inteiro em funções.

Dos guias anteriores vais usar tudo, e de propósito: este é o guia que junta a algoritmia. Do [guia 1](01-do-enunciado-ao-problema.md), o contrato de entrada e saída e a decomposição. Do [guia 2](02-estado-sequencia-representacoes.md), as variáveis, a atribuição, a tabela de trace e a primeira função que conheceste, a função predefinida `abs`. Do [guia 3](03-decisoes-e-validacao.md), as condições, a seleção e a validação. Do [guia 4](04-repeticao-e-arrays.md), os ciclos, os arrays, o contador e o acumulador.

Tal como nos guias anteriores, um algoritmo escrito em frases claras também é válido, desde que não deixe dúvidas. Com funções, isso quer dizer sobretudo deixar claro o que cada função recebe, o que devolve e em que casos.

## Razões para escrever funções

No guia 2 usaste a função `abs`. Bastava escrever `abs(-7)` para obter 7, sem saber como a conta era feita por dentro: chegava-te o contrato, "recebe um número e devolve a distância desse número a zero". Uma função é exatamente isso, um pedaço de algoritmo com nome e com contrato, que se usa sem pensar no que tem lá dentro.

As funções predefinidas já vêm feitas. Mas as partes que se repetem nos teus algoritmos, como validar uma nota ou calcular uma média, não vêm feitas em lado nenhum. Neste guia vais aprender a escrevê-las tu.

Há três razões para o fazer, e todas já as sentiste nos guias anteriores.

A primeira é não repetir. A validação de uma nota, `nota < 0 ou nota > 20`, apareceu no guia 3, voltou no guia 4 e vai voltar sempre que houver notas. Escrevê-la uma vez, com um nome, e usá-la em todo o lado, quer dizer que, se a escala mudar, se muda num sítio só.

A segunda é ler melhor. Uma linha como `Se notaValida(nota)` lê-se como uma frase. A mesma linha com a condição inteira obriga quem lê a descodificar a condição antes de perceber o que se está a perguntar.

A terceira é a mais importante: testar por partes. Um algoritmo grande, com ciclos dentro de seleções dentro de ciclos, é difícil de testar de uma vez. Se estiver dividido em funções pequenas, cada uma com o seu contrato, testa-se cada função sozinha, com poucos casos, e só depois se junta tudo. Quando aparece um erro, já sabes que as funções estão certas, e o erro está na forma como as juntaste. É a decomposição do guia 1, levada até ao fim.

## Escrever uma função

Na forma que usamos nas aulas, uma função escreve-se assim:

```text
Função nome(parametro1, parametro2)
    instruções da função
    devolver resultado
```

A primeira linha é o **cabeçalho**. Começa com a palavra `Função`, com maiúscula, como as outras palavras que começam uma instrução, a seguir vem o nome da função, e entre parênteses os **parâmetros**, separados por vírgulas. Os parâmetros são os nomes que a função dá aos valores que vai receber. Por baixo do cabeçalho, quatro espaços mais para dentro, está o **corpo** da função. Tal como num `Se` ou num `Enquanto`, não há nenhuma palavra a fechar a função: é a indentação que diz onde ela acaba.

A palavra `devolver` termina a função e entrega um valor a quem a chamou. Escreve-se em minúsculas, seguida do valor a devolver, que pode ser uma variável, uma conta ou uma condição.

Um primeiro exemplo, com a área de um retângulo:

```text
Função areaRetangulo(comprimento, largura)
    devolver comprimento * largura
```

O contrato desta função diz-se em três linhas, e vale a pena escrevê-lo sempre, por cima ou ao lado da função:

- recebe: o comprimento e a largura de um retângulo, números maiores do que zero, na mesma unidade;
- devolve: a área, na unidade ao quadrado;
- exemplos: `areaRetangulo(3, 2)` devolve 6; `areaRetangulo(1.5, 1.5)` devolve 2.25.

Repara em três pormenores da forma.

Os parâmetros não levam tipo. A função recebe os valores que lhe derem, e o contrato diz que valores são esses.

O nome da função segue as regras dos nomes das variáveis do guia 2: começa com minúscula, sem espaços nem acentos, e cada palavra a partir da segunda começa com maiúscula. Deve dizer o que a função faz ou o que devolve: `areaRetangulo`, `media`, `notaValida`. Um nome como `calcular` ou `funcao1` não diz nada.

E as funções escrevem-se antes do algoritmo principal, que é a parte que as usa. O algoritmo principal começa na primeira linha, encostada à margem, depois da última função. Num algoritmo com funções, as linhas encostadas à margem são as do algoritmo principal e os cabeçalhos das funções, e tudo o resto está indentado debaixo de alguma coisa.

## Chamar uma função

Escrever uma função não a executa. A função fica à espera, como uma receita num livro. Só se executa quando alguém a **chama**, escrevendo o seu nome com valores entre parênteses:

```text
Função areaRetangulo(comprimento, largura)
    devolver comprimento * largura

float area = areaRetangulo(3, 2)
Escreve: "Área: ", area
```

A terceira linha é a primeira do algoritmo principal, e é nela que a função é chamada. Os valores escritos entre parênteses na chamada, o 3 e o 2, chamam-se **argumentos**.

A diferença entre parâmetro e argumento é a diferença entre a etiqueta de uma caixa e o que se põe lá dentro. O parâmetro é o nome que está no cabeçalho da função, `comprimento`. O argumento é o valor que se dá na chamada, o 3. Os parâmetros escrevem-se uma vez, na função. Os argumentos mudam de chamada para chamada.

### O que acontece numa chamada

Uma chamada executa-se sempre em quatro fases, por esta ordem:

1. **Os argumentos passam para os parâmetros**, pela ordem em que estão escritos. O primeiro argumento vai para o primeiro parâmetro, o segundo para o segundo. Na chamada `areaRetangulo(3, 2)`, `comprimento` fica com 3 e `largura` fica com 2.
2. **O algoritmo salta para dentro da função** e executa o corpo, de cima para baixo, como qualquer outro algoritmo.
3. **Ao chegar a um `devolver`**, a função calcula o valor a devolver e termina imediatamente.
4. **O algoritmo regressa ao ponto onde a função foi chamada**, e a chamada é substituída pelo valor devolvido. A linha `float area = areaRetangulo(3, 2)` passa a ser, na prática, `float area = 6`, e continua a executar-se como qualquer atribuição.

A fase 4 é a que mais vezes se esquece. A chamada é como um buraco na linha onde está escrita: o algoritmo vai à função buscar o valor, volta, e tapa o buraco com ele. Por isso uma chamada pode aparecer em qualquer sítio onde caberia um valor: numa atribuição, numa conta, num `Escreve:` ou numa condição. `Escreve: areaRetangulo(4, 5)` escreve 20. `areaRetangulo(3, 2) + areaRetangulo(1, 1)` dá 6 mais 1, 7.

### A ordem dos argumentos conta

Os argumentos passam para os parâmetros pela ordem, e não pelo nome. Numa função em que a ordem muda o resultado, trocar os argumentos dá outro resultado, sem nenhum aviso. Com uma função `Função precoComDesconto(preco, percentagem)`, a chamada `precoComDesconto(50, 10)` aplica 10% a 50 euros, e `precoComDesconto(10, 50)` aplica 50% a 10 euros. São duas contas certas para dois problemas diferentes. Quem chama uma função tem de saber a ordem dos parâmetros, e é por isso que o contrato a diz.

### O trace de uma chamada

Uma chamada faz-se no trace com uma regra simples: cada chamada tem a sua própria tabela, com as variáveis da função. Na tabela do algoritmo principal, a linha da chamada mostra o valor que regressou.

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

Repara na linha 0 da tabela da chamada: os parâmetros não começam "sem valor", como as variáveis do algoritmo principal. Começam com os argumentos, porque é isso que a fase 1 faz antes de a primeira linha do corpo se executar.

### As variáveis da função são da função

Os parâmetros e as variáveis que nascem dentro de uma função existem só enquanto a função está a ser executada. Quando a função devolve o seu valor, essas variáveis desaparecem. A estas variáveis chama-se **variáveis locais** da função.

Isto tem duas consequências que vais usar sempre.

A primeira: uma variável com o mesmo nome dentro e fora de uma função são duas caixas diferentes. Se o algoritmo principal tiver uma variável `total`, e a função tiver também uma variável `total`, mexer numa não mexe na outra. É por isso que, no trace, cada chamada tem a sua tabela.

A segunda é uma regra das aulas: uma função só usa os seus parâmetros e as suas variáveis locais. Tudo aquilo de que precisa chega-lhe pelos parâmetros, e tudo o que tem para dar sai pelo `devolver`. Uma função que fosse buscar uma variável do algoritmo principal, sem a receber, deixava de se poder testar sozinha, porque o resultado dependeria de uma coisa que não está no seu contrato. As constantes são a exceção: escrevem-se no início, antes das funções, e valem em todo o lado, porque são regras do problema.

## `devolver`

A palavra `devolver` faz duas coisas ao mesmo tempo: entrega o valor e termina a função. As linhas que estiverem abaixo dela não se executam.

Uma função pode ter vários `devolver`, um em cada caminho de uma seleção:

```text
Função maior(a, b)
    Se a > b
        devolver a
    Senão
        devolver b
```

`maior(3, 8)` devolve 8, e `maior(8, 3)` também. Em cada chamada executa-se exatamente um dos dois `devolver`.

Há uma regra que esta função cumpre e que todas as funções deste guia têm de cumprir: em todos os caminhos possíveis, a função chega a um `devolver`. Uma função que, para algum valor, chegasse ao fim do corpo sem passar por nenhum `devolver`, não teria nada para entregar, e a linha que a chamou ficaria com um buraco por tapar. É o erro mais frequente com funções, e vais vê-lo com números na secção dos erros.

### `devolver` não é `Escreve:`

As duas parecem dar um resultado, e fazem coisas muito diferentes. `Escreve:` mostra um valor a quem está a usar o algoritmo, no ecrã, e o valor não vai para mais lado nenhum. `devolver` entrega o valor ao algoritmo que chamou a função, que pode guardá-lo, fazer contas com ele ou decidir o que fazer a seguir.

Uma função que calcula uma média e a escreve no ecrã, em vez de a devolver, só serve para mostrar essa média. Não serve para comparar a média com outra coisa, nem para a usar numa conta. Por isso, nas aulas, as funções que calculam devolvem, e quem escreve no ecrã é o algoritmo principal. Separar o cálculo da apresentação é o que permite reutilizar a função noutro algoritmo, com outro ecrã.

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

O contrato: recebe uma nota, um número inteiro; devolve `true` se estiver na escala de 0 a 20, incluindo os extremos, e `false` se não estiver. Os casos de teste são os das fronteiras do guia 3: `notaValida(-1)` devolve `false`, `notaValida(0)` devolve `true`, `notaValida(1)` devolve `true`, `notaValida(19)` devolve `true`, `notaValida(20)` devolve `true` e `notaValida(21)` devolve `false`.

Como a condição já dá `true` ou `false`, a função pode devolvê-la diretamente, numa linha só:

```text
Função notaValida(nota)
    devolver nota >= NOTA_MINIMA e nota <= NOTA_MAXIMA
```

As duas versões estão certas e fazem o mesmo. A primeira mostra melhor a decisão, e a segunda é mais curta. Usa a que perceberes melhor.

No algoritmo principal, a chamada aparece no sítio da condição:

```text
Escreve: "Nota?"
int nota = ler valor
Se notaValida(nota)
    Escreve: "Nota aceite"
Senão
    Escreve: "Nota inválida"
```

Lê-se como uma frase: "se a nota é válida, aceita-a". E a validação repetida do guia 4 fica mais legível com uma função que pergunta o contrário: `Enquanto notaValida(nota) == false`.

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

É o contador e o acumulador do guia 4, agora dentro de uma função. A função conta os elementos porque, no pseudocódigo das aulas, ainda não se pede a um array quantos elementos tem.

O contrato desta função tem uma parte nova, e é das mais importantes deste guia:

- recebe: um array de números, **com pelo menos um elemento**;
- devolve: a média desses números, com parte decimal;
- exemplos: `media([12, 7, 20, 5])` devolve 11; `media([10])` devolve 10.

A frase "com pelo menos um elemento" é uma condição que tem de ser verdadeira antes de a função ser chamada, e a que se chama **pré-condição**. Com um array vazio, a função faria 0 / 0, que não tem resultado. O contrato não esconde o problema: diz que esse caso não está coberto, e passa a responsabilidade a quem chama. Antes de chamar `media`, o algoritmo principal tem de garantir que o array não está vazio. É a mesma decisão do guia 1, quando o contrato dos livros em caixas dizia por palavras que com 0 livros não há última caixa: o que interessa é que alguém tenha pensado no caso e o tenha escrito.

Também se podia escolher outra solução, como devolver 0 para o array vazio. Mas uma média de 0 também pode ser a média de notas todas iguais a 0, e quem recebesse o 0 não saberia qual dos dois casos era. Uma pré-condição escrita é mais honesta.

## Decompor um problema em funções

Agora que sabes escrever e chamar funções, falta a parte mais importante: decidir que funções escrever. É a decomposição do guia 1, com uma regra a mais. Os passos são sempre estes, e o exemplo guiado vai segui-los um a um.

1. **Escrever o contrato do problema inteiro**: entradas, saídas, restrições e exemplos concretos, calculados à mão.
2. **Decompor em partes**, cada uma com um objetivo que se diz numa frase. Cada parte que recebe dados e produz um resultado é candidata a função.
3. **Escrever o contrato de cada função**: o que recebe, o que devolve, as pré-condições e dois ou três exemplos, incluindo um caso extremo.
4. **Escrever cada função e testá-la sozinha**, com os exemplos do seu contrato, antes de a usar. Aos testes feitos com casos escolhidos antes de olhar para a solução chama-se **testes independentes da solução**: testam o que a função devia fazer, e não o que tu achas que ela faz.
5. **Escrever o algoritmo principal**, que lê os dados, chama as funções e mostra os resultados.
6. **Fazer um teste completo à mão**, com um dos exemplos do passo 1, do princípio ao fim, chamada a chamada. Em inglês chama-se a isto um **dry run**, uma execução a seco, sem computador.

Uma boa função faz uma coisa só, e o seu nome diz qual. Se, ao escreveres o objetivo de uma função, precisares de dizer "e", como "calcula a média e conta as positivas", provavelmente são duas funções.

## Duas soluções certas, uma mais eficiente

Dois algoritmos podem estar os dois certos, dar sempre os mesmos resultados, e um deles fazer muito mais trabalho do que o outro. Nesta disciplina não vais medir a eficiência com fórmulas, que ficam para o 11.º ano. Vais medi-la de forma intuitiva, contando passos num exemplo pequeno.

Imagina que queres contar as notas acima da média. Esta solução está certa:

```text
int acima = 0
Para cada nota em notas
    Se nota > media(notas)
        acima = acima + 1
```

Mas olha para o que acontece em cada volta: a condição chama `media(notas)`, e a função percorre o array inteiro para calcular a média. Com 6 notas, o ciclo de fora dá 6 voltas, e em cada uma a função dá mais 6. São 6 vezes 6, ou seja, 36 voltas dentro da função, mais as 6 do ciclo de fora: 42 voltas. E a média calculada é sempre a mesma, porque as notas não mudam.

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

Repara como a diferença cresce: com 10 notas, a primeira solução já faz mais de cinco vezes o trabalho da segunda. A regra que daqui sai é simples: um valor que não muda dentro de um ciclo calcula-se antes do ciclo. O resultado não muda, e o trabalho diminui.

## Ler funções num fluxograma

Como nos guias anteriores, os fluxogramas são para saberes ler, e não há laboratório neste tema. Num fluxograma, cada função desenha-se à parte, como um fluxograma pequeno, com o nome da função e os parâmetros no oval de início, `( Função media(valores) )`, e com o `devolver` no oval do fim, `( devolver total / quantidade )`. No fluxograma do algoritmo principal, a linha da chamada aparece num retângulo, como qualquer atribuição, `[ float m = media(notas) ]`, e quem lê sabe que, nesse retângulo, o caminho salta para o fluxograma da função e volta com o valor.

## Exemplo guiado: o resumo das notas de um teste

### Passo 1: o enunciado

> Um professor guardou num array as notas de um teste, todas inteiras: `notas = [14, 9, 17, 10, 6, 16]`. Quer um algoritmo que, antes de mais nada, confirme que todas as notas estão na escala de 0 a 20. Se houver alguma nota fora da escala, o algoritmo escreve "Há notas inválidas" e não calcula mais nada. Se estiverem todas certas, escreve a média da turma e quantas notas são positivas, ou seja, 10 ou mais.

### Passo 2: o contrato do problema

A entrada é um array de notas inteiras, com pelo menos uma nota. O enunciado dá um array concreto, mas o algoritmo tem de servir para qualquer turma, e por isso os testes vão usar outros arrays.

As saídas são: a mensagem "Há notas inválidas", quando alguma nota está fora da escala; ou, quando estão todas certas, a média, com parte decimal, e o número de positivas.

As restrições são as do enunciado: a escala vai de 0 a 20, com os extremos; uma positiva é 10 ou mais; com uma nota inválida, não se calcula nada.

Os exemplos concretos, calculados à mão:

| Notas | Saída esperada | Porque é que este caso foi escolhido |
| --- | --- | --- |
| `[14, 9, 17, 10, 6, 16]` | Média 12; 4 positivas | O caso do enunciado: 14 + 9 + 17 + 10 + 6 + 16 = 72, e 72 / 6 = 12; positivas: 14, 17, 10 e 16 |
| `[10]` | Média 10; 1 positiva | Uma só nota, e na fronteira da positiva |
| `[9]` | Média 9; 0 positivas | Uma só nota, do outro lado da fronteira |
| `[0, 20]` | Média 10; 1 positiva | Os dois extremos da escala, que são válidos |
| `[12, 21, 8]` | Há notas inválidas | Uma nota fora da escala, no meio do array |

### Passo 3: decompor em funções

O problema tem três perguntas, e cada uma é uma função:

| Função | Objetivo numa frase |
| --- | --- |
| `notaValida(nota)` | Diz se uma nota está na escala |
| `media(valores)` | Calcula a média de um array de números |
| `contarPositivas(notas)` | Conta quantas notas de um array são positivas |

O algoritmo principal usa as três: percorre as notas com `notaValida` para confirmar que estão todas certas e, se estiverem, chama `media` e `contarPositivas` e mostra os resultados.

Repara que `media` recebe "valores" e não "notas". A média é uma conta que serve para qualquer array de números, e o nome do parâmetro diz isso: a mesma função calcularia a média de temperaturas ou de pontuações. `contarPositivas` é própria das notas, porque "positiva" é uma regra das notas.

### Passo 4: o contrato de cada função

**`notaValida(nota)`**: recebe uma nota inteira; devolve `true` se estiver entre 0 e 20, incluindo os extremos, e `false` se não estiver. Exemplos: -1 dá `false`; 0 dá `true`; 20 dá `true`; 21 dá `false`.

**`media(valores)`**: recebe um array de números com pelo menos um elemento (pré-condição); devolve a média. Exemplos: `[14, 9, 17, 10, 6, 16]` dá 12; `[10]` dá 10; `[0, 20]` dá 10.

**`contarPositivas(notas)`**: recebe um array de notas válidas; devolve quantas são 10 ou mais. Exemplos: `[14, 9, 17, 10, 6, 16]` dá 4; `[9]` dá 0; `[10]` dá 1; `[]` dá 0.

Repara no último exemplo de `contarPositivas`. Esta função, ao contrário de `media`, funciona com um array vazio: o ciclo dá zero voltas e o contador fica 0, que é a resposta certa. Por isso o seu contrato não precisa de pré-condição sobre o tamanho.

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

Antes de escrever o algoritmo principal, testa-se cada função sozinha, com os exemplos do seu contrato. Um teste de uma função é uma chamada com um argumento escolhido e o valor que se espera que ela devolva:

| Chamada | Esperado | Devolvido no trace | Certo? |
| --- | --- | --- | --- |
| `notaValida(-1)` | `false` | `-1 >= 0` dá `false`; `false` e qualquer coisa dá `false` | sim |
| `notaValida(0)` | `true` | `true` e `true` dá `true` | sim |
| `notaValida(20)` | `true` | `true` e `true` dá `true` | sim |
| `notaValida(21)` | `false` | `true` e `false` dá `false` | sim |
| `media([10])` | 10 | uma volta; 10 / 1 = 10 | sim |
| `media([0, 20])` | 10 | duas voltas; 20 / 2 = 10 | sim |
| `contarPositivas([9])` | 0 | uma volta; `9 >= 10` é falso | sim |
| `contarPositivas([10])` | 1 | uma volta; `10 >= 10` é verdadeiro | sim |
| `contarPositivas([])` | 0 | zero voltas | sim |

As três funções passam em todos os testes. A partir daqui, se o algoritmo completo der um resultado errado, o erro não está dentro delas: está na forma como o algoritmo principal as usa.

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

1. A validação é a bandeira do guia 4: começa em `true` e passa a `false` à primeira nota inválida, e o `Parar` evita olhar para o resto, porque basta uma.
2. `Se todasValidas` usa a bandeira diretamente como condição, porque ela já é `true` ou `false`. É o mesmo que `Se todasValidas == true`.
3. As duas funções de cálculo só são chamadas dentro do `Se`, quando se sabe que as notas são válidas. É o algoritmo principal a cumprir a pré-condição de `media`: o array do enunciado tem notas, e por isso não está vazio.
4. Os valores devolvidos guardam-se em variáveis com nomes que dizem o que são, e só depois se escrevem. Quem escreve no ecrã é o algoritmo principal, não as funções.

### Passo 7: o teste completo, chamada a chamada

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

A função devolve 72 / 6, que é 12, e o algoritmo regressa à linha `float mediaDaTurma = media(notas)`, que passa a valer `float mediaDaTurma = 12`.

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

Repara que as tabelas das duas funções têm cada uma as suas variáveis, e que a variável `nota` de `contarPositivas` não tem nada a ver com a variável `nota` do ciclo de validação do algoritmo principal: têm o mesmo nome, mas são caixas diferentes, de sítios diferentes.

Com `[12, 21, 8]`, o ciclo da validação para na segunda volta: `notaValida(21)` devolve `false`, a bandeira passa a `false` e o `Parar` termina o ciclo. O `Se todasValidas` é falso, e o ecrã mostra "Há notas inválidas". `media` e `contarPositivas` nunca chegam a ser chamadas.

### Passo 8: o dossiê do problema

O que fizeste nos passos 2 a 7 é um **dossiê algorítmico**: tudo o que é preciso para outra pessoa perceber, verificar e implementar a solução, numa linguagem de programação, sem te fazer nenhuma pergunta. Um dossiê tem sempre estas partes:

| Parte | No exemplo guiado |
| --- | --- |
| Análise: o contrato do problema, com exemplos concretos | Passo 2 |
| Decomposição em funções, com o objetivo de cada uma | Passo 3 |
| O contrato de cada função | Passo 4 |
| O pseudocódigo das funções e do algoritmo principal | Passos 5 e 6 |
| Os testes de cada função e o teste completo | Passos 5 e 7 |

É este dossiê que leva o algoritmo para o Python. Os testes que escreveste aqui, à mão, vão ser os mesmos que vais pôr o computador a executar, e se o programa em Python der outro resultado, o erro está na tradução, não no raciocínio.

## Erros frequentes

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

A conta está certa, e o resultado fica guardado em `resultado`. Mas a função acaba sem `devolver`, e `resultado` é uma variável local, que desaparece quando a função termina. No algoritmo principal, a linha `float m = media(notas)` fica sem nada para pôr em `m`. No trace vê-se logo: a tabela da chamada não tem nenhuma linha com "valor devolvido". A correção é acrescentar `devolver resultado` como última linha do corpo.

### `devolver` dentro do ciclo, no sítio errado

```text
Função existe(valores, procurado)
    Para cada valor em valores
        Se valor == procurado
            devolver true
        Senão
            devolver false
```

Esta função devia dizer se `procurado` está no array. Com `existe([3, 8], 8)`, a primeira volta compara 3 com 8, a condição é falsa, e o `Senão` devolve `false`. A função termina na primeira volta, sem nunca olhar para o 8. O erro é decidir "não está" ao primeiro elemento diferente, quando só se pode decidir isso depois de ver todos. A correção é tirar o `Senão` e pôr o `devolver false` depois do ciclo, encostado ao `Para cada`: só se chega lá se o ciclo acabar sem ter encontrado o valor. Com um array vazio, a versão errada nem sequer chega a nenhum `devolver`, e a versão certa devolve `false`.

### Usar uma variável do algoritmo principal dentro da função

Uma função que use uma variável que não recebeu pelos parâmetros depende de uma coisa que não está no seu contrato. Testada sozinha, não funciona; usada noutro algoritmo, onde essa variável não exista ou tenha outro valor, dá outro resultado. Tudo o que a função usa tem de chegar pelos parâmetros, exceto as constantes.

### Trocar a ordem dos argumentos

Os argumentos passam para os parâmetros pela ordem. `precoComDesconto(10, 50)` não é o mesmo que `precoComDesconto(50, 10)`. Confirma sempre a ordem dos parâmetros no cabeçalho, ou no contrato, antes de escrever a chamada.

### Chamar a função e não usar o valor devolvido

Uma linha só com `media(notas)`, sem guardar nem escrever o resultado, executa a função e deita fora o valor que ela devolveu. Uma chamada a uma função que devolve um valor aparece sempre dentro de alguma coisa: uma atribuição, uma conta, um `Escreve:` ou uma condição.

### `Escreve:` em vez de `devolver`

Uma função que escreve o resultado no ecrã em vez de o devolver só serve para mostrar. O algoritmo principal não consegue usar esse valor numa conta nem numa decisão. As funções que calculam devolvem.

### Esquecer a pré-condição

O erro está em chamar `media` com um array que pode estar vazio, sem confirmar antes que ele tem pelo menos um elemento. A entrada que o revela é o array vazio: a função dá zero voltas, `quantidade` e `total` ficam a 0, e a conta do `devolver` é 0 / 0, que não tem resultado. Com qualquer array que tenha elementos, a chamada funciona, e por isso o erro só aparece a quem testa o caso vazio. No exemplo guiado, é o contrato do problema que garante a pré-condição, porque diz que a entrada tem pelo menos uma nota. Antes de chamar uma função, lê o seu contrato e confirma que cumpres as pré-condições.

### Cálculos repetidos dentro de um ciclo

O erro está em chamar, dentro de um ciclo, uma função cujo resultado não muda de volta para volta, como `media(notas)` na comparação de cada nota com a média. O resultado está certo, e por isso nenhuma entrada mostra este erro no ecrã. O que o revela é contar as voltas com um array de vários elementos: com 6 notas, a versão com a média dentro do ciclo faz 42 voltas, e a versão com a média calculada antes faz 12, como viste na secção "Duas soluções certas, uma mais eficiente". Quanto mais elementos tiver o array, maior é a diferença. Calcula o valor uma vez, antes do ciclo, e guarda-o numa variável.

## Verificar o que aprendeste

Usa esta lista para te testares. Para cada ponto, experimenta fazê-lo sem olhar para o guia. Se não conseguires, volta à secção correspondente.

- Consegues explicar as três razões para escrever funções.
- Consegues escrever uma função com `Função` e `devolver`, e o seu contrato: o que recebe, o que devolve e exemplos.
- Consegues apontar, numa chamada, os argumentos, e no cabeçalho, os parâmetros.
- Consegues explicar as quatro fases de uma chamada e fazer o trace de uma chamada em tabela própria.
- Consegues explicar o que são variáveis locais e porque é que uma função só usa os seus parâmetros.
- Consegues escrever uma função com vários `devolver` e confirmar que todos os caminhos chegam a um deles.
- Consegues explicar a diferença entre `devolver` e `Escreve:`.
- Consegues escrever uma função que devolve `true` ou `false` e usá-la num `Se`.
- Consegues escrever uma função que recebe um array, com a pré-condição certa no contrato.
- Consegues decompor um problema em funções, testar cada uma sozinha e escrever o algoritmo principal.
- Consegues comparar duas soluções certas contando voltas, e tirar um cálculo repetido de dentro de um ciclo.
- Consegues encontrar uma função que não devolve, ou que devolve cedo demais, e corrigi-la.
- Consegues montar o dossiê de um problema pequeno, com as cinco partes.

## Praticar

Para praticares o que aprendeste neste guia, faz a [ficha de exercícios](05-funcoes-e-modelo-integrado-exercicios.md) deste tema. O último exercício é o dossiê de um problema pequeno, que junta toda a algoritmia; os testes do dossiê estão na secção opcional "Para ires mais longe", para quem quiser completá-lo.

## O que vem a seguir

Com este guia acaba a algoritmia. O passo seguinte é o Python, a primeira linguagem de programação do ano. Vais reconhecer quase tudo: o pseudocódigo das aulas foi escrito para passar para o Python quase linha a linha. `Função media(valores)` passa a `def media(valores):`, `devolver` passa a `return`, `Enquanto` passa a `while`, `Para cada` passa a `for`, e a indentação continua a mostrar o que está dentro de quê. O que muda é que, em vez de fazeres o trace à mão, vais pôr o computador a executar os teus algoritmos, e os dossiês que fizeste vão dizer-te se ele faz o que devia.

![Rodapé](../imagens/rodape.png)
