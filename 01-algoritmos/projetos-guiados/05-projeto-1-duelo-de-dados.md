![Cabeçalho](../../imagens/cabecalho.png)

# Projeto 1: Duelo de dados

Dois jogadores escolhem números entre 1 e 6, durante um máximo de cinco rondas. O algoritmo diz quem ganhou cada ronda e quem ganhou o duelo. Este projeto leva um problema do enunciado até um algoritmo testado, com o processo que a avaliação vai pedir. Faz-se com o professor ao quadro, e o fim pode passar para a aula seguinte. Só precisas do caderno e de um lápis. Para rever: os guias [01](../01-do-enunciado-ao-problema.md), [02](../02-estado-sequencia-representacoes.md), [03](../03-decisoes-e-validacao.md) e [04](../04-repeticao-e-arrays.md).

## O jogo

> Dois jogadores disputam um duelo com um máximo de cinco rondas. Em cada ronda, o jogador 1 escolhe um número inteiro entre 1 e 6 e escreve-o. Depois, o jogador 2 faz o mesmo. Quem escolher o número maior ganha a ronda, e o algoritmo escreve "Ronda para o jogador 1" ou "Ronda para o jogador 2". Se os dois escolherem o mesmo número, escreve "Ronda empatada". O duelo termina logo que um jogador ganhe três rondas, ou depois da quinta ronda. No fim, ganha o duelo quem tiver ganho mais rondas. O algoritmo escreve então "Ganhou o jogador 1" ou "Ganhou o jogador 2".

Por exemplo, numa ronda em que o jogador 1 escolhe 4 e o jogador 2 escolhe 2, o algoritmo escreve "Ronda para o jogador 1".

Lê o enunciado duas vezes. Na segunda, sublinha os números e as mensagens. Sublinha também as palavras que dizem quando acontece cada coisa, como "em cada ronda".

Antes do passo 1, inventa um duelo com o colega do lado. Preparem valores para cinco rondas, em duas colunas. Decidam, só com o enunciado, o que o algoritmo devia escrever em cada ronda e no fim. Guardem esse duelo.

## Passo 1: o contrato

O contrato diz o que o algoritmo tem de fazer, antes de se pensar em como. É dele que vão sair os resultados esperados do passo 2. Num projeto, o contrato ganha duas partes, as condições e as decisões, e os exemplos concretos ficam para o passo 2. Rever: [O contrato diz o que entra, o que sai e que regras há](../01-do-enunciado-ao-problema.md#o-contrato-diz-o-que-entra-o-que-sai-e-que-regras-há).

| Parte do contrato | O que tem de responder |
| --- | --- |
| Entradas | Que valores o algoritmo recebe, quantos são, por que ordem chegam, de que tipo são e entre que limites ficam |
| Saídas | O que o algoritmo escreve e em que momento |
| Restrições | As regras fixas, incluindo os valores que vão ser constantes |
| Condições | As situações diferentes que podem acontecer numa ronda e no fim do duelo |
| Decisões | O que o enunciado não diz, cada coisa numa frase que começa por "Decisão:" |

Pensa nestas perguntas antes de o professor avançar:

1. Qual é o mínimo e o máximo de valores que cada jogador escreve ao longo de um duelo? E os dois juntos? Por que ordem chegam ao algoritmo?
2. Que valores pode ter cada entrada? Pode aparecer um 0, um 7 ou um 2,5? Que palavras do enunciado te deixam responder a isto?
3. Há algum número no enunciado que nunca muda de um duelo para outro? Como é que se escreve um valor destes no pseudocódigo?
4. O que é que o algoritmo escreve durante o jogo, e quantas vezes? E o que escreve no fim?
5. Que situações diferentes podem acontecer numa ronda? E no fim do duelo, quando se comparam as rondas que cada jogador ganhou?

### O que o enunciado não diz

Pensa em todos os finais possíveis, contando as rondas ganhas de cada jogador. Há algum para o qual a última frase do enunciado não diga o que escrever? Quando falta informação, não se inventa em silêncio. Pergunta-se a quem escreveu o enunciado, ou toma-se uma decisão e escreve-se. Rever: [Um dado relevante muda a resposta](../01-do-enunciado-ao-problema.md#um-dado-relevante-muda-a-resposta).

6. Que final é esse, e o que diz o enunciado sobre ele?
7. Que decisões possíveis vês? Para cada uma, é justa para os dois jogadores? Obriga a mudar alguma coisa que o enunciado fixou, como o número de rondas?
8. Porque é que esta decisão tem de ficar escrita já, no passo 1?

### A suposição que dispensa a validação

Este projeto não valida os números que os jogadores escrevem, porque a validação entra no projeto 2. O contrato tem de o dizer. Uma **suposição** é uma coisa que o contrato dá como certa e que o algoritmo não verifica. Escreve-se nas entradas. Aqui, o contrato assume que os jogadores cumprem o combinado, e as entradas fora disso não estão cobertas.

A decisão escolhe o que o algoritmo faz numa situação que pode acontecer. A suposição diz que uma situação não vai acontecer, e porquê.

Antes de passares ao passo seguinte: o contrato tem as cinco partes, a decisão começa por "Decisão:" e a suposição está nas entradas.

## Passo 2: a tabela de casos esperados, antes do algoritmo

Testar é comparar o que o algoritmo escreve, o **resultado obtido**, com o que devia escrever, o **resultado esperado**. O esperado calcula-se agora, a partir do enunciado e do contrato. Calculado depois, seria o algoritmo a concordar consigo próprio. Rever: [Escolher os casos de teste](../03-decisoes-e-validacao.md#escolher-os-casos-de-teste).

Cada caso é um duelo inteiro. Escreve cada ronda como um par, com o valor do jogador 1 primeiro, como (4, 2). Prepara cinco pares. Se alguém chegar às três vitórias antes, os pares seguintes ficam por ler.

O resultado esperado é a mensagem de cada ronda jogada e a mensagem do fim. As perguntas antes de cada leitura não entram. Para caber na tabela, as rondas abreviam-se: J1, J2 e E, para "Ronda empatada". Para o calcular, decide cada ronda pelo enunciado e faz um risco ao lado de quem a ganhou. Antes do par seguinte, vê se o duelo já acabou. O duelo que inventaste pode ser um dos casos.

| N.º | Tipo | Entradas preparadas, ronda a ronda | Rondas lidas | Resultado esperado | Porque foi escolhido |
| ---: | --- | --- | ---: | --- | --- |

Cada caso diz de que tipo é:

- um caso normal é um caso típico, dos que se imaginam ao ler o enunciado;
- um caso de fronteira está no sítio onde a resposta muda, ou imediatamente ao lado;
- um caso inválido tem uma entrada que não cumpre o contrato.

Nesta tabela não há casos inválidos, porque o contrato diz que essas entradas não estão cobertas. Este jogo tem fronteiras em três sítios: dentro de cada ronda, nas três vitórias e no fim do duelo. Rever: [Fronteiras e casos de teste](../03-decisoes-e-validacao.md#fronteiras-e-casos-de-teste).

Antes de o professor avançar, pensa nisto:

1. Numa ronda, onde é que a resposta muda de "Ronda para o jogador 1" para "Ronda para o jogador 2"? Que par fica exatamente em cima dessa fronteira, e que pares ficam de um lado e do outro?
2. No fim do duelo, onde é que a resposta muda de um vencedor para o outro? Que duelo fica exatamente em cima dessa fronteira?
3. Há algum duelo em que nenhum jogador chega a ganhar uma ronda? O que esperas que o algoritmo escreva nesse duelo?
4. Consegues escrever o resultado esperado de um duelo em que os dois ganharam o mesmo número de rondas sem a decisão do passo 1? Porquê?
5. A ordem dos pares preparados pode mudar o momento da paragem? Que caso escolherias para mostrar que o resultado depende da contagem, e não só da última ronda jogada?
6. Em que situações o duelo termina antes da quinta ronda? Depois de cinco rondas, pode alguém ganhar com menos de três vitórias?
7. Cada mensagem do enunciado aparece no resultado esperado de pelo menos um caso? E a mensagem que a decisão do passo 1 vier a criar?

Antes de passares ao passo seguinte: a tabela tem paragens à terceira e à quarta ronda, para os dois jogadores. Tem também casos que chegam à quinta ronda.

## Passo 3: o algoritmo

A tabela do passo 2 é o alvo. Antes da primeira linha, decompõe o problema em três partes: o que vem antes do ciclo, o que se repete e o que vem depois. As palavras que sublinhaste dizem o que vai para cada parte. O professor escreve o algoritmo em pseudocódigo, e tu copias. Se preferires, escreve ao lado o mesmo algoritmo em frases claras. Rever: [As três peças de um ciclo](../04-repeticao-e-arrays.md#as-três-peças-de-um-ciclo).

Pensa nisto antes de o professor continuar:

1. `Enquanto` ou `Para`? Antes de o ciclo começar, já se sabe quantas vezes ele se vai repetir? Com um `Para` e um `Parar`, onde ficava escrita a regra do fim?
2. O que acontece em cada ronda, e por que ordem? Escreve as ações por palavras, uma por linha.
3. Para decidir, no fim, quem ganhou o duelo, o que é que o algoritmo tem de ir guardando ao longo das rondas? Que padrão do guia 04 é este?
4. Quantas variáveis dessas são precisas? Decide e justifica.
5. Onde nascem essas variáveis, antes do ciclo ou dentro dele? O que acontecia se nascessem dentro?
6. Os números escolhidos aparecem pela primeira vez dentro do ciclo. Em que linha levam o tipo? O que acontece, em cada ronda, ao valor da ronda anterior? Porque é que, para estes números, a linha pode ficar dentro do ciclo?
7. Dentro do ciclo, a ronda tem três resultados possíveis. Por que ordem fazes as perguntas, e qual dos três fica no `Senão`?
8. Onde fica o `Se` que decide o vencedor: dentro do ciclo ou depois dele? O que aparecia no ecrã se ficasse no sítio errado?
9. Que ramo do `Se` do fim existe só por causa da decisão do passo 1?
10. O enunciado diz quando o duelo termina, e o `Enquanto` diz quando continua. Como passas de um para o outro? Que variável precisas para saber em que ronda vais?

Antes de passares ao passo seguinte: confirma se há algum ramo de um `Se` por onde nenhum caso da tabela passa. Se houver, acrescenta um caso que passe por ele, com o esperado calculado pelo enunciado.

## Passo 4: a tabela de iterações

O professor escolhe um dos casos e faz a tabela no quadro, com a turma a dizer cada valor. As colunas são a ronda, cada valor lido, cada contador, a condição e o que acontece durante a volta. Um valor lido durante uma volta só aparece na sua coluna na linha seguinte. Rever: [A tabela de iterações](../04-repeticao-e-arrays.md#a-tabela-de-iterações).

O professor vai perguntar-te isto:

1. Se só pudesses fazer a tabela de um dos casos, qual escolhias? Porquê?
2. Antes de começar: quantas linhas vai ter a tabela? Porquê esse número, e não o número de rondas?
3. Na primeira linha, que valores têm as colunas dos números escolhidos? Porquê?
4. Depois de uma ronda empatada, que colunas mudam na linha seguinte, e quais ficam iguais?
5. Quanto vale `ronda` na última linha? Que parte da condição fez o ciclo terminar? O que aconteceria se faltasse a atualização de `ronda`?
6. Depois da última linha, que instruções são executadas, e que mensagem aparece no fim? Bate certo com o resultado esperado?

Antes de passares ao passo seguinte: a tabela tem a linha do último teste, o que dá falso e faz sair do ciclo.

## Passo 5: executar os outros casos e comparar o obtido com o esperado

A tabela de iterações mostra um caso. Agora executam-se os outros, sem uma tabela inteira para cada um. Segue cada ronda pela cadeia de decisões, anota a mensagem e faz um risco no contador que muda. Executa o que está escrito, e não o que achas que o algoritmo devia fazer. Na aula, cada dois colegas executam um caso, e o professor regista o resultado. Acrescentam-se à tabela as colunas "Resultado obtido" e "Passou?".

Quando um caso falha, o erro pode estar no algoritmo ou no resultado esperado. Nunca copies o obtido para a coluna do esperado.

Tenta responder antes de o professor avançar:

1. Se um dos casos falhar, o que confirmas antes de mexer no algoritmo, e a partir de onde?
2. Depois de executares todos os casos, todos os ramos do algoritmo foram percorridos?
3. Todos os casos passarem prova que o algoritmo está certo? Qual dos teus casos apanharia mais erros, se o algoritmo os tivesse?

Antes de passares ao passo seguinte: todos os casos têm o resultado obtido e a coluna "Passou?" preenchida.

## Passo 6: depurar o erro

Depurar é encontrar a causa de um erro e corrigi-la. Este passo faz-se sempre. Se nenhum caso falhou, o professor mostra uma versão do algoritmo com um erro. Guarda as duas versões, a com erro e a corrigida. O registo e o último passo da rotina podem acabar-se no início da aula seguinte. Rever: [Reproduzir a falha com um exemplo mínimo](../01-do-enunciado-ao-problema.md#reproduzir-a-falha-com-um-exemplo-mínimo).

Quem começa costuma mudar uma linha à sorte, até o caso passar. Com método, seguem-se sempre os mesmos cinco passos:

1. Observar e reproduzir o erro. Escreve o caso que falhou, o esperado e o obtido, e executa-o outra vez, devagar.
2. Formular uma hipótese. Uma **hipótese** é uma frase com o que achas que causa o erro, que os valores do trace podem confirmar ou desmentir.
3. Verificar a hipótese. Segue os valores no exemplo mínimo, até à primeira linha da tabela onde uma variável fica diferente do que devia.
4. Corrigir a causa, mudando o mínimo possível. A causa é a instrução que produz o valor errado, ou a que falta.
5. Voltar a testar tudo. Executa outra vez todos os casos da tabela, também os que já passavam. A isto chama-se **teste de regressão**.

Volta-se a testar tudo porque uma correção pode acertar o caso que falhava e estragar outros que estavam certos.

Cada depuração escreve-se num registo de depuração:

| Parte do registo | O que se escreve |
| --- | --- |
| O que se observou | O caso que falhou, o resultado obtido e a mensagem errada; e o exemplo mínimo, com o que ele dá |
| O que se esperava | O resultado esperado desse caso e o do exemplo mínimo, calculado pelo enunciado |
| A causa | A hipótese, e a primeira linha da tabela onde uma variável fica com um valor diferente do que devia |
| A correção | A instrução que mudou, e onde |

Por baixo do registo, numa linha, escreve quantos casos da tabela passam depois da correção.

Pensa nestas perguntas antes da correção:

1. Pensa nos erros frequentes dos guias 03 e 04. Qual deles te parece mais provável num algoritmo como este? Que caso da tabela o apanhava?
2. Como podes simplificar os valores sem mudar a situação que revela o erro? Com o erro, o duelo ainda acaba às três vitórias?
3. A correção que vais escrever explica porque é que o valor ficou errado, ou só acerta o resultado do caso que falhou?
4. Que casos da tabela já passavam antes da correção? O que te garante que continuam a passar?

## Antes de terminares

Os projetos 1 e 2 ficam no teu portefólio: uma pasta no computador, ou as páginas do caderno, como o professor indicar. Não contam para a avaliação prática, mas podes consultá-los nela. Se guardares em ficheiros, usa um por peça:

| Peça | Nome do ficheiro |
| --- | --- |
| O enunciado e o contrato, com a suposição e a decisão | `duelo-de-dados-contrato` |
| A tabela de casos, com os resultados obtidos, e a tabela de iterações | `duelo-de-dados-testes` |
| O algoritmo corrigido | `duelo-de-dados-algoritmo` |
| A versão com o erro | `duelo-de-dados-algoritmo-com-erro` |
| O registo de depuração, com a linha do teste de regressão | `duelo-de-dados-registo-depuracao` |

- [ ] O contrato tem as cinco partes, com a suposição e a decisão.
- [ ] A tabela de casos foi escrita antes do algoritmo, e cada caso tem o tipo e a razão da escolha.
- [ ] Cada mensagem do enunciado, e a da decisão, aparece no resultado esperado de pelo menos um caso.
- [ ] Há paragens à terceira e à quarta ronda para os dois jogadores, e casos que chegam à quinta.
- [ ] Nenhum ramo de um `Se` ficou sem caso.
- [ ] A tabela de iterações tem a linha do último teste.
- [ ] Todos os casos têm o resultado obtido e a coluna "Passou?".
- [ ] O registo tem as quatro partes, as duas versões do algoritmo e a linha do teste de regressão.

A seguir vem o [projeto 2, Adivinha o número](05-projeto-2-adivinha-o-numero.md), em pares.

![Rodapé](../../imagens/rodape.png)
