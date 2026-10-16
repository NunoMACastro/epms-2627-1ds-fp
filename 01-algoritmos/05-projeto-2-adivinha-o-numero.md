![Cabeçalho](../imagens/cabecalho.png)

# Projeto 2: Adivinha o número

Um jogador escreve um número secreto de 1 a 100, e o outro tenta adivinhá-lo, com pistas, em 10 tentativas no máximo. O projeto faz-se em pares, em cerca de duas horas de aula: 70 minutos para a Parte 1 e 50 para a Parte 2.

## Para que serve este projeto

Nos exercícios das fichas treinaste cada coisa à parte: um ciclo, uma validação, um contador, uma tabela de casos, a procura de um erro. Num problema a sério, tudo isto aparece junto, e é preciso saber por que ordem se faz cada coisa. É para isso que servem os três projetos que fecham a algoritmia.

Os três seguem o mesmo processo:

1. o contrato;
2. a tabela de casos esperados, escrita antes de haver algoritmo;
3. o algoritmo;
4. a tabela de iterações e os testes;
5. se algum teste falhar, a depuração, com o seu registo, e voltar a testar a tabela inteira;
6. por fim, a melhoria, com o trabalho de cada versão contado num exemplo pequeno.

O passo 6, a melhoria, entra a partir deste projeto.

No projeto 1, o duelo de dados, viste o professor fazer este processo ao quadro, a pensar em voz alta. Neste projeto és tu que o fazes, com um colega, um passo de cada vez, e o professor confirma cada passo antes de avançarem. No projeto 3, a avaliação prática, vais fazê-lo sozinho, num problema novo.

Por isso este projeto é um ensaio. O que interessa não é acabar depressa. É perceber porque se faz cada passo e porque se faz por aquela ordem. Assim, no dia da avaliação, a ordem já é tua.

O jogo deste projeto leva mais longe uma ideia que viste no guia 04, na pesquisa com `Parar`. É um ciclo que pode acabar por duas razões diferentes, com uma variável que diz, depois do ciclo, qual delas aconteceu. Aqui o jogo acaba quando o jogador acerta, mas também acaba quando se esgotam as tentativas. No fim, o algoritmo tem de saber qual das duas coisas aconteceu, para escrever a mensagem certa. É uma estrutura que aparece em muitos problemas, e que vais voltar a encontrar.

Este projeto fica no teu portefólio e não conta para a avaliação prática, porque é feito com ajuda. O trabalho que fazes nele conta, como o das outras aulas, no empenho e na autonomia. Podes consultá-lo durante a avaliação prática.

## O que precisas de saber

Este projeto não traz nenhuma instrução nova de pseudocódigo. Usa o que aprendeste nos guias e o processo que o professor mostrou no projeto 1, juntando tudo num problema maior.

- O contrato de entrada e saída: guia [01 Do enunciado ao problema delimitado](01-do-enunciado-ao-problema.md), secção "O contrato de entrada e saída".
- A regra do que o enunciado não diz, que não se inventa em silêncio: decide-se e escreve-se. Está no guia 01, no passo 3 do exemplo guiado dos Missionários e Canibais.
- O exemplo mínimo: guia 01, secção "Reproduzir a falha com um exemplo mínimo".
- A tabela de trace: guia [02 Estado, sequência e representações](02-estado-sequencia-representacoes.md), secção "Tabela de trace". A sua regra mais importante é executar o que está escrito, e não o que achas que o algoritmo devia fazer.
- O tipo à frente só na linha onde a variável nasce: guia 02, secção "A linha onde a variável nasce".
- A cadeia de `Se`, `Senão se` e `Senão`, em que a primeira condição verdadeira ganha: guia [03 Decisões e validação](03-decisoes-e-validacao.md), secção "Seleção encadeada".
- Os operadores `e`, `ou` e `não`: guia 03, secção "Operadores lógicos: `e`, `ou` e `não`".
- Os intervalos e o contrário de um intervalo, escrito com `ou`: guia 03, secções "Intervalos" e "O contrário de um intervalo".
- As condições que não se sobrepõem e que cobrem todos os casos: guia 03, secção com esse nome.
- As fronteiras, testadas imediatamente abaixo, em cima e imediatamente acima: guia 03, secção "Fronteiras e casos de teste".
- Os resultados esperados escritos antes de haver algoritmo: guia 03, passo 4 do exemplo guiado.
- As três peças de um ciclo, a inicialização, a condição e a atualização: guia [04 Repetição e arrays](04-repeticao-e-arrays.md), secção "As três peças de um ciclo".
- A regra de que a condição de um ciclo diz quando continuar, e não quando parar: guia 04, secção "O ciclo que nunca começa".
- A pergunta que escolhe entre `Enquanto` e `Para`: guia 04, secção "Escolher entre `Enquanto` e `Para`".
- A tabela de iterações e o contador: guia 04, secções "A tabela de iterações" e "O contador".
- A bandeira: guia 04, secção "`Parar`: sair do ciclo já".
- A validação repetida, que volta a pedir um valor enquanto ele for inválido: guia 04, secção "Validação repetida".
- A ideia de que, depois de um ciclo que termina pela condição, essa condição é falsa, e isso diz alguma coisa sobre o estado. Está na mesma secção do guia 04.
- A comparação de duas soluções certas, contando o trabalho de cada uma num exemplo pequeno. Está no guia [05 Funções e modelo integrado](05-funcoes-e-modelo-integrado.md), secção "Duas soluções certas, uma mais eficiente".
- O processo inteiro, do [projeto 1](05-projeto-1-duelo-de-dados.md). Tem o contrato com as condições, as decisões e as suposições. Tem o resultado esperado decidido antes de executar, e os casos normais, de fronteira e inválidos.
- A rotina da depuração, em cinco passos, o registo de depuração, com as suas quatro partes, e o teste de regressão, também do projeto 1.

Este projeto faz-se depois da aula em que a validação e a validação repetida são dadas. Se ainda tiveres dúvidas, relê a secção "Validação repetida" do guia 04 antes de começares.

Testar e depurar não tiveram uma aula só para eles. Fizeste-o nos exercícios, sempre que comparaste um resultado com o que tinhas previsto ou procuraste a entrada que revela um erro. No projeto 1, viste o professor fazê-lo de forma explícita, por escrito. Neste projeto fazes o mesmo, e cada passo recorda a ferramenta de que precisas quando chegares a ele.

Três notas antes de começares. Podes escrever o algoritmo em pseudocódigo, na forma das aulas, ou em frases claras. As frases valem, desde que não deixem dúvidas: quanto, quando, e o que acontece se não der. Não precisas de funções; se quiseres usar alguma, como as do guia 05, podes. E o número secreto não é sorteado. É escrito por uma pessoa, o jogador 1. Assim, cada jogo de teste pode ser repetido exatamente, com os mesmos números, as vezes que for preciso. É isso que torna possível testar e depurar o algoritmo.

## Como vais trabalhar

Trabalham os dois juntos, um passo de cada vez. Em cada passo, um escreve e o outro confere, com o enunciado e com o guia abertos. No passo seguinte, trocam. Os dois têm de conseguir explicar tudo o que está escrito, porque o professor pode fazer a pergunta a qualquer um. No fim, cada um guarda uma cópia do projeto no seu portefólio.

Cada passo acaba com a frase "Mostra ao professor antes de avançar". Quer dizer o que diz: chamas o professor, mostras o que fizeram, e só passas ao passo seguinte depois de ele o confirmar. Há uma razão para isto. Cada passo usa o anterior. Uma decisão esquecida no contrato dá um resultado esperado errado na tabela. E um resultado esperado errado faz-te procurar um erro onde ele não está. Se o professor encontrar alguma coisa a corrigir, não te vai dar a resposta. Vai fazer-te uma pergunta, ou apontar para um caso da tua tabela, e tu corriges e voltas a mostrar. Enquanto esperas, relê a secção do guia de que vais precisar no passo seguinte.

Precisas de papel e lápis, dos guias 01 a 05 à mão e do projeto 1, que está no teu portefólio.

O tempo de cada passo, no título dele, é uma estimativa para um par médio. Há passos que vão demorar mais e outros menos. O que conta é fazer cada um com cuidado.

## O jogo

> Dois jogadores jogam ao "adivinha o número". Primeiro, o jogador 1 escreve um número secreto de 1 a 100, sem o jogador 2 ver. O jogador 1 escreve sempre um número de 1 a 100.
>
> Depois, o jogador 2 tenta adivinhar o número, e tem no máximo 10 tentativas. Em cada tentativa escreve um número. Se o número estiver fora de 1 a 100, o algoritmo escreve "Esse número não vale. Escreve um número de 1 a 100." e pede outra vez, até o número ser válido. Um número que não vale não conta como tentativa. Se o número for igual ao secreto, o jogador 2 acertou. Se for menor do que o secreto, o algoritmo escreve "Mais alto". Se for maior, escreve "Mais baixo".
>
> O jogo acaba quando o jogador 2 acerta ou quando esgota as 10 tentativas. Se o jogador 2 acertou, o algoritmo escreve no fim "Acertaste à tentativa N!". No lugar do N fica o número da tentativa em que acertou. Se acertou em 7 tentativas ou menos, escreve também "Muito bem!". Se não acertou, escreve "Perdeste! O número era S.", com o número secreto no lugar do S.

As mensagens entre aspas são estas, palavra por palavra. As perguntas que o algoritmo faz antes de cada leitura, como a que pede o número secreto, escolhe-as tu. "Mais alto" quer dizer que o número secreto é mais alto do que o número que o jogador 2 acabou de escrever. "Mais baixo" quer dizer que é mais baixo.

Por exemplo, se o número secreto for 63 e o jogador 2 escrever 50, o algoritmo escreve "Mais alto". Se a seguir o jogador 2 escrever 120, o algoritmo escreve "Esse número não vale. Escreve um número de 1 a 100." e pede outro número. O 120 não conta como tentativa.

## Parte 1: do enunciado ao algoritmo testado (70 min)

### Passo 1: o contrato (12 min)

A ferramenta está no guia 01, na secção "O contrato de entrada e saída". Está também no passo 3 do exemplo guiado do mesmo guia, "procurar o que falta ou se pode ler de duas maneiras".

O contrato é o que diz, sem margem para dúvidas, o que o algoritmo tem de fazer. É dele que vão sair os resultados esperados da tabela do passo 2, e por isso tem de estar completo antes de a tabela começar. No guia 01, o contrato tinha quatro partes: as entradas, as saídas, as restrições e os exemplos concretos. No projeto 1 viste que, num projeto, se acrescentam duas. São as condições, isto é, as situações diferentes que podem acontecer e que obrigam o algoritmo a fazer coisas diferentes. E são as decisões sobre o que o enunciado não diz. Neste passo escreves tudo menos os exemplos concretos, que são a tabela de casos do passo 2. Num jogo como este são muitos, e tão importantes, que têm um passo só para eles.

Há uma razão para fazer o contrato por escrito, mesmo num jogo que parece simples. Quando lês um enunciado, a tua cabeça preenche sozinha o que ele não diz. E preenche-o de uma maneira que pode não ser a do teu colega. Escrever o contrato obriga-te a ver essas lacunas. Quando uma pergunta não tem resposta no enunciado, ou tem duas respostas possíveis, isso é uma **ambiguidade**. Nos Missionários e Canibais, era saber se quem está no barco conta numa margem. O guia 01 diz o que se faz: não se inventa em silêncio, toma-se uma decisão e escreve-se. No contrato, escreve-a numa linha que começa por "Decisão:" e diz a razão. Uma ambiguidade que fica por decidir volta a aparecer mais à frente, quando tiveres de escrever um resultado esperado e não souberes qual é.

**a)** Escreve as entradas. Para cada uma, diz o tipo, os limites e se o algoritmo a valida ou não, e porquê. Repara que o enunciado trata os dois jogadores de maneira diferente. Se uma entrada não for validada, o contrato diz porquê numa frase, como a suposição do projeto 1. Uma suposição é uma coisa que o contrato dá como certa e que o algoritmo não verifica.

**b)** Escreve as saídas: as mensagens que podem aparecer durante o jogo e as que podem aparecer no fim.

**c)** Escreve as restrições, isto é, as regras do jogo que o algoritmo tem de cumprir, com os números do enunciado.

**d)** Escreve as condições: as situações diferentes que podem acontecer numa tentativa e no fim do jogo. Esta lista vai ser o ponto de partida da tabela do passo 2.

**e)** Há uma situação que o enunciado não decide. Para a encontrares, imagina um jogador 2 distraído: o que pode ele escrever que o enunciado não diga como se conta? Quando a encontrares, escreve a decisão e a razão. Para decidires, pensa no que o algoritmo teria de guardar, ao longo do jogo, para tratar essa situação de outra maneira. Pensa também no trabalho que isso dava.

Mostra ao professor antes de avançar: o contrato, com a decisão e a sua razão.

### Passo 2: a tabela de casos esperados, antes do algoritmo (12 min)

A ferramenta está no guia 03, na secção "Fronteiras e casos de teste". Está também no passo 4 do exemplo guiado desse guia, "escolher os casos de teste e prever os resultados". No guia 04, está nas secções "O ciclo que nunca começa" e "Testar só o caso normal". E está no projeto 1, onde viste a tabela com o tipo de cada caso.

Lembra-te do que o projeto 1 mostrou. Testar é comparar o resultado obtido com o resultado esperado, e o resultado esperado decide-se antes de executar, a partir do contrato. Ainda não há algoritmo, e é de propósito. Um resultado esperado calculado a olhar para o algoritmo concorda sempre com ele, e então não serve para nada. Quando, no passo 6, executares o algoritmo, é com esta tabela que vais comparar.

Cada caso da tabela tem um tipo. Um caso **normal** é o que qualquer pessoa imagina ao ler o enunciado. Um caso **de fronteira** fica em cima, ou mesmo ao lado, de um sítio onde a resposta muda. É aí que os erros se escondem, como o guia 03 explica. Um caso **inválido** tem uma entrada que o contrato não aceita, e serve para confirmar que o algoritmo a trata como o enunciado manda.

Neste jogo, cada caso de teste é um jogo inteiro. Tem o número secreto que o jogador 1 escreve e todos os números que o jogador 2 escreve, pela ordem, incluindo os que não valem. Escreve só os números até o jogo acabar. Se o jogo acaba à terceira tentativa, o caso não tem mais nenhum número depois dessa, porque o algoritmo já não o leria.

Na coluna do resultado esperado, escreve todas as mensagens do jogo, pela ordem em que aparecem, sem as perguntas. Para caber na tabela, podes abreviar a mensagem do número que não vale como "Esse número não vale". Uma pista repetida três ou mais vezes seguidas escreve-se uma vez, com o número de vezes, como "Mais alto (4 vezes)".

Pensa também nas fronteiras do ciclo, que são fáceis de esquecer. O guia 04 manda testar um ciclo com zero voltas, com uma volta e com várias. Neste jogo, o ciclo das tentativas não pode dar zero voltas, porque o jogador 2 escreve sempre pelo menos um número. Mas tem um jogo mais curto possível e um jogo mais comprido possível. E o mais comprido pode acabar de mais do que uma maneira.

**a)** Faz a tabela com as colunas que se preenchem antes de executar: N.º, Tipo, Número secreto, Números escritos pelo jogador 2, Resultado esperado e Porque foi escolhido. Deixa espaço à direita para as duas colunas que se preenchem depois, Resultado obtido e Passou?.

**b)** A tabela tem de ter, pelo menos, casos para estas situações:

- um jogo normal, curto, com pistas dos dois tipos;
- o jogo mais curto possível;
- o jogo mais comprido possível, de cada uma das maneiras como pode acabar;
- os dois lados da fronteira do "Muito bem!";
- números que não valem, dos dois lados do intervalo de 1 a 100, cada um ao lado do número válido mais perto;
- dois números que não valem, escritos seguidos;
- a situação que decidiste no passo 1.

Um caso pode testar duas coisas ao mesmo tempo, e isso é bom, desde que a coluna "Porque foi escolhido" diga as duas.

Há duas dicas para não perderes tempo. Nos jogos compridos, escolhe números fáceis de seguir, por exemplo de 10 em 10. E quando dois casos servem para mostrar os dois lados de uma fronteira, faz com que sejam quase iguais e só difiram no fim. Assim, se um passar e o outro falhar, sabes logo que o problema está na fronteira.

Mostra ao professor antes de avançar: a tabela com as colunas de antes de executar preenchidas. Para cada fronteira, diz quais são os casos que ficam de um lado e do outro.

### Passo 3: as peças do algoritmo (8 min)

A ferramenta está no guia 04, nas secções "As três peças de um ciclo", "Escolher entre `Enquanto` e `Para`" e "Validação repetida". A bandeira está na secção "`Parar`: sair do ciclo já". Está também no guia 03, nas secções "O contrário de um intervalo" e "O operador `não`".

Antes de escreveres vinte linhas, decide a estrutura. É o que faz o passo 3 do exemplo guiado do guia 04, "as peças do ciclo". Responde às perguntas das peças antes de escrever o pseudocódigo. Uma estrutura decidida com calma escreve-se depressa. Uma estrutura decidida a meio da escrita costuma obrigar a apagar e recomeçar.

Este algoritmo tem duas coisas que ainda não tinhas juntado.

A primeira é um ciclo com duas maneiras de acabar. No guia 04 já viste uma pesquisa com `Parar` que podia acabar por duas razões: porque encontrou o valor, ou porque os índices se esgotaram. Uma bandeira dizia, depois do ciclo, qual delas tinha acontecido. Neste jogo também há duas razões, e qualquer uma delas chega para o jogo acabar. Lembra-te da regra do guia 04: a condição de um ciclo diz quando continuar, e não quando parar. Por isso, tens de pensar primeiro em quando o jogo para e, a partir daí, escrever a situação em que continua.

Para passares de uma à outra, precisas do contrário de uma condição com duas partes. No guia 03 viste que o contrário de um intervalo, que se escreve com `e`, se escreve com `ou`, trocando cada comparação pela sua contrária. A regra funciona também no outro sentido. O contrário de uma condição com `ou` escreve-se com `e`, trocando cada parte pela sua contrária. Por exemplo, o contrário de "a nota está fora da escala", `nota < 0 ou nota > 20`, é "a nota está dentro da escala", `nota >= 0 e nota <= 20`.

E há um cuidado a ter depois do ciclo. Quando o ciclo acaba pela condição, sabes que a sua condição deu falso. Num ciclo com uma só razão para acabar, isso diz-te tudo. Num ciclo com duas, diz-te só que pelo menos uma das razões aconteceu, e não diz qual. O algoritmo precisa de saber qual foi, para escrever a mensagem certa.

A segunda é um ciclo dentro de outro. No guia 04, na secção "Arrays de arrays: uma tabela", viste dois `Para`, um dentro do outro. Para cada volta do de fora, o de dentro dá todas as suas voltas. Com a validação repetida é igual. A validação repetida do guia 04 era um ciclo que pedia um valor até ele ser válido. Quando está dentro do corpo de outro ciclo, faz todas as suas voltas durante uma só volta do ciclo de fora. O ciclo de fora só continua para a linha seguinte quando o de dentro tiver acabado. No pseudocódigo, o corpo do ciclo de dentro fica oito espaços para dentro, porque está dentro de dois blocos. Na tabela de iterações do ciclo de fora, o que o ciclo de dentro faz escreve-se na coluna "Durante a iteração".

Um exemplo, noutro contexto. Um professor escreve a nota de dois alunos num teste, e cada nota tem de ser um inteiro de 0 a 20. A validação repetida do guia 04 fica dentro de um `Para` de dois alunos:

```text
const NOTA_MINIMA = 0
const NOTA_MAXIMA = 20
const NUMERO_DE_ALUNOS = 2
Para aluno de 1 até NUMERO_DE_ALUNOS
    Escreve: "Nota do aluno ", aluno, " (inteiro de 0 a 20)?"
    int nota = ler valor
    Enquanto nota < NOTA_MINIMA ou nota > NOTA_MAXIMA
        Escreve: "Nota inválida. Escreve um inteiro de 0 a 20."
        nota = ler valor
    Escreve: "Nota aceite: ", nota
```

O professor escreve 25, -3, 14 e 9. Antes de leres a tabela, tenta prever: quantas vezes aparece "Nota inválida", e que notas são aceites?

| Teste | aluno | nota | Condição | Durante a iteração |
| --- | ---: | ---: | --- | --- |
| 1.º | 1 | sem valor | `1 <= 2` dá `true` | lê 25; a validação testa `25 < 0 ou 25 > 20`, que dá `true`: escreve "Nota inválida. Escreve um inteiro de 0 a 20." e lê -3; testa `-3 < 0 ou -3 > 20`, que dá `true`: escreve a mesma mensagem e lê 14; testa `14 < 0 ou 14 > 20`, que dá `false`, e a validação termina; escreve "Nota aceite: 14" |
| 2.º | 2 | 14 | `2 <= 2` dá `true` | lê 9; a validação testa `9 < 0 ou 9 > 20`, que dá `false`, e não dá nenhuma volta; escreve "Nota aceite: 9" |
| 3.º | 3 | 9 | `3 <= 2` dá `false` | o ciclo termina |

"Nota inválida" aparece duas vezes, as duas na primeira volta do `Para`, e as notas aceites são 14 e 9. A validação do primeiro aluno, com as suas duas voltas e três testes, cabe toda numa só linha da tabela do `Para`. A nota do segundo aluno é válida à primeira: a validação testa a condição uma vez e não dá nenhuma volta. Na linha de cada teste do `Para`, a coluna `nota` tem o último valor lido, o que a validação deixou passar.

Responde por escrito, em poucas palavras:

**a)** O enunciado fala em 10 tentativas. Usa a pergunta do guia 04 que escolhe entre `Enquanto` e `Para`. Quando o algoritmo chega ao ciclo das tentativas, já se sabe quantas vezes ele se vai repetir? Responde numa frase, e diz que ciclo escolhes.

**b)** Escreve as duas maneiras de o jogo acabar, cada uma como uma condição que dá `true` quando essa maneira aconteceu.

**c)** Escreve a condição de continuar, a situação em que o jogo continua.

**d)** Depois do ciclo, como fica o algoritmo a saber por qual das duas maneiras o jogo acabou? Atenção: há uma forma de decidir que parece certa e falha num dos casos da tua tabela. Diz qual é esse caso.

**e)** Diz onde fica a validação repetida e onde fica a linha que soma 1 às tentativas. Um número que não vale não pode contar.

Mostra ao professor antes de avançar: as cinco respostas.

### Passo 4: o algoritmo (18 min)

A ferramenta está em todos os exemplos do guia 04. Está sobretudo no passo 4 do exemplo guiado, "o pseudocódigo da primeira parte", e na secção "Validação repetida".

Agora escreve o algoritmo completo, com as peças que decidiste no passo 3. Se usares pseudocódigo, usa a forma das aulas:

- uma constante, com `const`, para cada número fixo do enunciado;
- o tipo à frente de cada variável só na linha onde ela nasce, como manda o guia 02, em "A linha onde a variável nasce";
- uma leitura dentro de um ciclo onde a variável aparece pela primeira vez leva o tipo, como `int nota = ler valor` no exemplo do passo 3;
- a indentação a mostrar o que está dentro de cada ciclo e de cada `Se`.

Se preferires frases claras, numera-as, e diz em cada repetição que passos se repetem, como no exemplo em frases do guia 04.

Antes de mostrares, confere estas cinco coisas, com o dedo por baixo de cada linha:

- cada variável recebe um valor antes de ser usada pela primeira vez, também as da condição do ciclo das tentativas, logo no primeiro teste;
- a validação repetida tem a condição do número que não vale, e o seu corpo volta a ler o número, como no guia 04;
- a linha que soma 1 às tentativas é executada uma vez por cada número válido, e nunca por um número que não vale;
- dentro do ciclo das tentativas, há uma atualização que, mais cedo ou mais tarde, faz o ciclo acabar;
- a decisão do fim depende da razão por que o ciclo parou, como respondeste no passo 3.

Mostra ao professor antes de avançar: o algoritmo completo.

### Passo 5: a tabela de iterações do caso normal (6 min)

A ferramenta está no guia 04, na secção "A tabela de iterações" e no passo 5 do exemplo guiado, "o trace dos três casos".

A tabela de iterações tem uma linha por cada teste da condição do ciclo das tentativas, com a fotografia do estado nesse momento. A última linha é a do teste que dá falso. Lembra-te de que um valor lido durante uma iteração só aparece na coluna dessa variável na linha seguinte. Viste-o na tabela da bilheteira do guia 04.

**a)** Faz a tabela de iterações do teu caso normal, com estas colunas:

- uma para cada variável que muda durante o jogo;
- uma para a condição do ciclo, com o resultado de cada parte e o do conjunto;
- uma para o que acontece durante a iteração: o número lido, o que a validação faz com ele e o que aparece no ecrã.

Não precisas de escrever as perguntas.

**b)** Por baixo da tabela, escreve o que acontece depois do ciclo: que condições são avaliadas, com que resultado, e o que aparece no ecrã.

**c)** Compara o ecrã com o resultado esperado do caso normal, na tabela do passo 2.

Mostra ao professor antes de avançar: a tabela de iterações e a comparação.

### Passo 6: executar a tabela de casos (10 min)

A ferramenta está no guia 02, na secção "Tabela de trace", e no guia 03, no passo 10 do exemplo guiado, "comparar com o previsto".

Agora executa os outros casos da tua tabela. Não precisas de fazer a tabela de iterações de cada um. Segue o algoritmo, tentativa a tentativa, e anota num rascunho o número lido, o valor das tentativas e o que aparece no ecrã. Executa o que está escrito, linha a linha, e não o que achas que o algoritmo devia fazer. É a regra do guia 02, e é ela que impede o trace de concordar sempre contigo.

**a)** Para cada caso, preenche as duas colunas que faltam: o resultado obtido e se o teste passou.

**b)** Agora olha para o algoritmo, e não para a tabela, e faz a pergunta que o projeto 1 fez depois de escrever o algoritmo. Há alguma linha por onde nenhum caso passou? Uma tabela escrita a partir do contrato pode deixar uma parte do algoritmo sem nenhum teste, e esta pergunta encontra-a. Se houver, acrescenta um caso que passe por essa linha, com o resultado esperado escrito antes de o executares.

Mostra ao professor antes de avançar: a tabela com todas as colunas e a resposta da alínea b).

### Passo 7: depurar o que falhou (4 min, ou mais se for preciso)

A ferramenta é a rotina da depuração que o professor mostrou no projeto 1. É também o registo de depuração com as quatro partes que já usaste no exercício 6 da ficha do tema 05, "Encontrar o erro".

Se algum caso falhou, não mudes linhas ao acaso. Segue os cinco passos da rotina do projeto 1, sempre pela mesma ordem:

1. observar e reproduzir o erro, com o caso que falhou, o resultado esperado e o resultado obtido;
2. formular uma hipótese, numa frase que os valores possam confirmar ou desmentir;
3. verificar a hipótese, com o trace do caso mais curto que ainda mostra o erro, o exemplo mínimo;
4. corrigir a causa, uma de cada vez, mudando o mínimo possível;
5. voltar a testar tudo, a tabela inteira, porque uma correção pode estragar um caso que antes passava.

Escreve o registo de depuração com as quatro partes. A primeira é o que se observou, com o caso e o resultado obtido. A segunda é o que se esperava. A terceira é a causa, isto é, que linha está errada e o que o trace mostrou. A quarta é a correção. Por baixo do registo, numa linha, escreve o resultado do teste de regressão: quantos casos da tabela passam depois da correção. Não apagues a versão com o erro. Escreve a versão corrigida noutra folha, porque o portefólio mostra as duas.

Se nenhum caso falhou, escreve-o por baixo da tabela. O professor pode dar-te um caso que ainda não experimentaste, para veres se o teu algoritmo também passa nele.

Mostra ao professor antes de avançar: o registo de depuração e a versão corrigida, ou a tabela com todos os casos a passar.

## Parte 2: depurar e melhorar o algoritmo de um colega (50 min)

Quando o professor confirmar o teu passo 7, entrega-te duas coisas em papel. A primeira é o algoritmo que um colega de outra turma escreveu para este mesmo jogo. A segunda é o relato de um erro que esse colega observou quando o experimentou com um jogo de teste. O relato diz qual era o número secreto, que números o jogador 2 escreveu, o que apareceu no ecrã e o que devia ter aparecido.

Esse algoritmo não está neste documento, e há uma razão para isso. Resolve o mesmo jogo, e lê-lo antes de escreveres o teu tirava-te o mais importante da Parte 1. O mais importante é decidires tu como o ciclo acaba e como o algoritmo sabe porque acabou. Por isso só o recebes depois de teres o teu algoritmo escrito, testado e confirmado.

O colega fez algumas escolhas diferentes das tuas, e isso não quer dizer que estejam erradas. Dois algoritmos diferentes podem estar ambos certos. Para encontrares o erro, não procures as diferenças em relação ao teu algoritmo. Segue a rotina da depuração do projeto 1, a partir do erro observado. Guarda a folha que o professor te dá, porque faz parte do teu portefólio.

### Passo 8: ler o algoritmo do colega e observar e reproduzir o erro (13 min)

A ferramenta está no primeiro passo da rotina da depuração do projeto 1, observar e reproduzir o erro. Está também no guia 04, na secção "A tabela de iterações", e no guia 01, na secção "Reproduzir a falha com um exemplo mínimo".

Antes de procurares um erro num algoritmo que não escreveste, tens de o perceber. Lê-o pela indentação. Vê onde começa e acaba cada ciclo e que linhas estão dentro de cada `Se`. Vê também o que se executa uma vez só, antes e depois do ciclo das tentativas.

Depois, reproduz o erro. **Reproduzir** um erro é fazê-lo acontecer outra vez, tu próprio, no papel, com o mesmo caso. Enquanto não o reproduzires, não sabes se o relato está certo, e não tens onde verificar uma hipótese.

**a)** Faz a tabela de iterações do jogo relatado, na versão do colega. Usa uma coluna para cada variável que muda durante o jogo e uma para a condição do ciclo das tentativas. Junta uma coluna para o que acontece durante a iteração. Confirma que o ecrã que obténs é o do relato.

**b)** Procura o exemplo mínimo, de que vais precisar no passo 9 para verificar a hipótese. O guia 01 define-o como a entrada mais pequena e simples que ainda mostra a falha. Aqui, é o jogo mais pequeno e simples que ainda mostra o mesmo erro. Experimenta, na versão do colega, jogos parecidos com o relatado, mas mais curtos. Não precisas de fazer outra tabela de iterações completa. Em cada jogo, segue só o que precisares para saber se o erro aparece ou não.

**c)** Qual é o jogo mais pequeno que ainda mostra o erro? Porque é que não pode ser mais pequeno? Responde numa ou duas frases, e diz o que se pode simplificar nesse jogo, mesmo que não se possa encurtar.

Mostra ao professor antes de avançar: a tabela de iterações e as respostas às alíneas b) e c).

### Passo 9: formular uma hipótese, verificá-la e corrigir a causa (8 min)

A ferramenta está nos passos 2, 3 e 4 da rotina do projeto 1: formular uma hipótese, verificar a hipótese e corrigir a causa. Está também no guia 03, na secção "Fronteiras e casos de teste".

Uma hipótese diz onde procurar e o que verificar. "O algoritmo do colega tem um erro" não é uma hipótese, porque não diz que instrução, nem com que valores. Uma boa hipótese pode ser deitada abaixo por uma única linha do trace, e é isso que a torna útil.

Quando encontrares a linha, corrige a causa, e não o sintoma. O sintoma é o que se vê no ecrã; a causa é a linha que o produz. Uma correção da causa explica porque é que o resultado estava errado. Uma correção que só faz o resultado ficar certo esconde o erro e deixa-o lá, à espera do próximo caso. Costuma mudar outra coisa qualquer que já estava certa. A pergunta que separa as duas é esta: a minha alteração explica porque é que o resultado ficou errado, ou só o acerta?

**a)** Escreve a tua hipótese numa frase que possa ser verdadeira ou falsa.

**b)** Faz o trace linha a linha da parte do algoritmo onde a tua hipótese põe o erro, com o exemplo mínimo do passo 8. Começa no estado em que o algoritmo lá chega, que tiras do que seguiste no passo 8. Usa uma coluna para cada variável que essa parte usa, uma para a condição e o seu resultado e uma para o ecrã. Diz se o trace confirma a hipótese, e qual é a linha que causa o erro. Se a deitar abaixo, formula outra hipótese com o que o trace te mostrou.

**c)** Escreve a causa numa frase. Diz o que faz essa linha, e porque é que, com ela, o algoritmo não faz o que o enunciado diz. Não basta escrever "a linha está mal".

**d)** Corrige a causa com uma única alteração, na linha que causa o erro, de forma que o algoritmo diga o que o enunciado diz. Escreve a linha corrigida e explica a correção com as palavras do enunciado.

Mostra ao professor antes de avançar: a hipótese, o trace, a causa e a correção.

### Passo 10: o registo de depuração e voltar a testar tudo (14 min)

A ferramenta é o registo de depuração do projeto 1, com as quatro partes do exercício 6 da ficha do tema 05. É também o quinto passo da rotina do projeto 1, voltar a testar tudo.

Uma correção pode estragar um caso que antes funcionava. Por isso, depois de corrigir, volta-se a testar a tabela inteira, e não só o caso que falhava. Viste no projeto 1 que a isto se chama **teste de regressão**. Repara numa coisa: a tua tabela de casos da Parte 1 foi escrita a partir do contrato, e não a partir do teu algoritmo. Como o jogo é o mesmo, o contrato é o mesmo, e a tabela serve tal e qual para testar o algoritmo do colega. É uma das vantagens de escrever os casos antes. Uma tabela feita a partir do contrato testa qualquer algoritmo que resolva aquele problema.

**a)** Antes de executares, confirma que a tua tabela tem os dois lados da fronteira onde o erro apareceu. Precisa de um caso em cima da fronteira, como o do relato, e de outro logo do outro lado dela. Se não tiver, acrescenta esses casos agora, com o resultado esperado escrito a partir do contrato, antes de executares.

**b)** Escreve o registo de depuração desta correção, com as quatro partes. São o que se observou, com o jogo relatado e o exemplo mínimo; o que se esperava; a causa; e a correção. Outra pessoa tem de conseguir perceber o erro e a correção só pelo registo, sem ter estado contigo.

**c)** Faz o teste de regressão. Executa a tabela inteira na versão corrigida do algoritmo do colega, como no passo 6, e preenche o resultado obtido e se passou. Por baixo do registo, escreve numa linha quantos casos passam.

Mostra ao professor antes de avançar: o registo de depuração e a tabela executada.

### Passo 11: melhorar sem mudar o que o algoritmo faz (8 min)

A ferramenta está no guia 05, na secção "Duas soluções certas, uma mais eficiente". Está também no guia 03, nas secções "Seleção encadeada" e "Condições que não se sobrepõem e que cobrem todos os casos". Nos erros frequentes desse guia, lê "Dois `Se` separados em vez de uma cadeia".

A versão corrigida passa em todos os testes. Agora, e só agora, pergunta-se se ela faz trabalho desnecessário. O guia 05 mostrou que duas soluções podem estar ambas certas, e uma fazer muito mais trabalho do que a outra. Lá, a média era calculada outra vez em cada volta do ciclo, e a melhoria foi calculá-la uma vez só, antes do ciclo. Aqui o trabalho a mais é de outro tipo. Há uma parte do corpo do ciclo das tentativas que faz perguntas cujas respostas o algoritmo já conhece. A melhoria é não voltar a perguntar o que já se sabe.

Lembra-te da regra principal. A versão melhorada tem de escrever exatamente o mesmo que a corrigida, para qualquer jogo que o contrato aceite. Muda o trabalho que o algoritmo faz, e não o que ele escreve. A equivalência mostra-se de duas maneiras, e as duas são precisas: com uma explicação, que cobre todos os jogos, e com testes.

**a)** Escreve a parte do algoritmo que muda, já melhorada. Basta essa parte, porque o resto fica igual.

**b)** Explica, numa ou duas frases, porque é que a versão melhorada escreve sempre o mesmo que a corrigida. A explicação tem de dizer porque é que os casos que juntaste não podem acontecer ao mesmo tempo.

**c)** Volta a testar. Executa na versão melhorada três casos da tua tabela: o caso normal, o caso que mostrou o erro e o que acaba sem acertar. Confirma que dão exatamente o mesmo ecrã que na versão corrigida.

Mostra ao professor antes de avançar: a parte melhorada, a explicação e os três testes.

### Passo 12: contar as perguntas antes e depois (7 min)

A ferramenta está no guia 05, na secção "Duas soluções certas, uma mais eficiente".

Nesta disciplina, a eficiência mede-se de forma intuitiva, como no guia 05. Escolhe-se um exemplo pequeno e conta-se o trabalho que cada versão faz nele. No guia 05 contaram-se voltas. Aqui as voltas são as mesmas nas duas versões, porque a melhoria não mexeu em nenhum ciclo. O que mudou foi o número de perguntas, e por isso aqui contam-se perguntas.

A regra da contagem é esta:

- cada vez que o algoritmo avalia a condição de um `Se` ou de um `Senão se`, faz uma pergunta;
- uma condição com `e` ou com `ou` é uma só pergunta, porque se avalia de uma vez;
- o `Senão` não faz pergunta nenhuma: é o caminho que sobra quando as perguntas de cima deram todas falso;
- conta só as perguntas da parte que mudou, dentro do ciclo das tentativas.

O resto do algoritmo faz as mesmas perguntas nas duas versões, e por isso não muda a diferença.

Conta as perguntas de um jogo curto: o número secreto é 30, e o jogador 2 escreve 50, 20 e 30.

**a)** Faz uma tabela com uma linha por tentativa e uma coluna para cada versão, a corrigida e a melhorada. Escreve em cada célula quantas perguntas faz a parte que mudou nessa tentativa.

**b)** Soma as perguntas de cada versão neste jogo e calcula a diferença.

**c)** Diz, numa frase, em que tentativa a versão melhorada poupa mais perguntas, e porquê.

Mostra ao professor antes de avançar: a tabela, os dois totais e a resposta da alínea c).

## O que fica no teu portefólio

O projeto vai para o portefólio de cada um dos dois elementos do par, ao lado do projeto 1. Guarda-o numa pasta no computador ou nas páginas do caderno, como o professor indicar. Se guardares em ficheiros, usa um por peça, com nomes como os do projeto 1: em minúsculas, com hífenes e sem acentos nem espaços. Os traces feitos em papel também contam. Fotografa-os ou passa-os a limpo.

| Peça | Nome do ficheiro |
| --- | --- |
| O enunciado e o contrato, com a decisão | `adivinha-o-numero-contrato` |
| A tabela de casos, com os resultados obtidos, e a tabela de iterações do caso normal | `adivinha-o-numero-testes` |
| O teu algoritmo e, se o corrigiste, a versão com o erro e o registo de depuração | `adivinha-o-numero-algoritmo`, e se for preciso `adivinha-o-numero-algoritmo-com-erro` e `adivinha-o-numero-registo-depuracao` |
| A folha com a versão do colega e o erro observado, a tabela de iterações do erro, o trace, o registo de depuração e a tabela executada outra vez | `adivinha-o-numero-colega-depuracao` |
| A versão melhorada, a explicação da equivalência e a contagem de perguntas | `adivinha-o-numero-colega-melhorado` |

Confirma, antes de dares o projeto por acabado:

- [ ] A tabela de casos foi escrita antes do algoritmo. Tem as fronteiras do ciclo, as do "Muito bem!" e as do intervalo de 1 a 100.
- [ ] O algoritmo passa em todos os casos da tabela, e consigo explicar como ele sabe, depois do ciclo, porque é que o jogo acabou.
- [ ] O registo de depuração do algoritmo do colega tem as quatro partes. Outra pessoa consegue perceber o erro e a correção só por ele.
- [ ] Depois de corrigir, voltei a testar a tabela inteira, e não só o caso que falhava.
- [ ] Contei as perguntas das duas versões com a mesma regra, e sei explicar onde está a diferença.

## O que vem a seguir

O projeto 3 é a avaliação prática individual que fecha a algoritmia, e dura 120 minutos. Vais receber um problema novo, que não é nenhum dos jogos dos projetos 1 e 2. Fazes sozinho o processo que fizeste aqui em par: o contrato, a tabela de casos antes do algoritmo, o algoritmo e os testes. Depois, com um algoritmo escrito por outra pessoa, fazes a depuração, com o registo, e voltas a testar tudo. Por fim, fazes a melhoria, com o trabalho contado. O que se observa é a lógica e o processo, e não a forma da escrita nem a rapidez. Podes ter contigo o portefólio, com os projetos 1 e 2. As outras regras vêm escritas no enunciado, e o professor dá-te antes a grelha com os critérios.

A melhor preparação é rever este projeto, sobretudo as respostas do passo 3 e o registo de depuração do passo 10. Percebe também porque é que cada passo vem antes do seguinte.

![Rodapé](../imagens/rodape.png)
