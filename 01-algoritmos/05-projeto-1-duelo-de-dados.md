![Cabeçalho](../imagens/cabecalho.png)

# Projeto 1: Duelo de dados

Dois jogadores lançam dados durante cinco rondas, e o algoritmo diz quem ganhou cada ronda e quem ganhou o duelo. O projeto faz-se numa aula de cerca de 60 minutos, com o professor ao quadro.

## Para que servem os três projetos

Até aqui, cada exercício treinou uma coisa de cada vez: um ciclo, uma cadeia de decisões, um contador, uma tabela de casos, uma função. Um projeto junta tudo isso num problema só e leva-o do enunciado até um algoritmo testado. É um salto grande. Por isso, a algoritmia acaba com três projetos, em vez de um só, e cada um é um pouco mais difícil do que o anterior.

| Projeto | Como se faz | Tempo |
| --- | --- | --- |
| 1, duelo de dados | O professor resolve-o ao quadro, a pensar em voz alta; tu acompanhas, respondes e escreves no caderno | Cerca de 60 minutos |
| 2, adivinha o número | Em pares, um passo de cada vez, com o professor a confirmar cada passo antes do seguinte | Cerca de 120 minutos |
| 3, avaliação prática | Individual, com um problema novo | 120 minutos |

Os três seguem o mesmo processo, sempre pela mesma ordem:

1. o contrato;
2. a tabela de casos esperados, escrita antes do algoritmo;
3. o algoritmo;
4. a tabela de iterações e os testes;
5. a depuração, com o seu registo.

No projeto 2 e na avaliação junta-se mais um passo, que este projeto ainda não tem. É melhorar o algoritmo e mostrar que a versão melhorada faz menos trabalho, contando voltas e perguntas num exemplo pequeno. É este processo que a avaliação observa, e por isso vais fazê-lo duas vezes com ajuda antes de o fazeres sozinho.

A ordem dos passos não é um capricho. A tabela de casos vem antes do algoritmo, por uma razão que o passo 2 explica. Os testes vêm depois do algoritmo, porque só se pode executar o que já está escrito. E a depuração vem no fim, porque só se procura um erro depois de um teste o mostrar.

Este é o primeiro projeto, e é o teu primeiro contacto com um projeto completo e com a forma que a avaliação vai pedir. É também aqui que vais fazer por extenso duas coisas que os guias só começaram. A primeira é escolher os casos de teste de um algoritmo inteiro, dizendo de que tipo é cada um. A segunda é seguir a rotina da depuração do princípio ao fim, e escrevê-la num registo. Os guias 04 e 05 apresentam essa rotina em resumo, nos erros frequentes. O exercício 6 da ficha do tema 05 treina o registo numa função. Este documento explica as duas coisas por extenso, nos passos em que aparecem, e o professor mostra-as ao quadro.

Os projetos 1 e 2 ficam no teu portefólio e não contam para a avaliação prática, porque são feitos com ajuda. O trabalho que fazes neles conta, como o das outras aulas, no empenho e na autonomia. Mas vais poder consultá-los durante a avaliação, e por isso vale a pena que o caderno fique completo e arrumado. Não esperes encontrar lá a resposta da avaliação. Cada projeto pede decisões que os anteriores não pediram, e a avaliação não é uma cópia deste projeto nem do projeto 2. O que vais poder aproveitar é a forma de trabalhar, passo a passo.

## O que precisas de saber

Este projeto não traz pseudocódigo novo. Usa o que está nos guias 01 a 05, e cada passo deste documento diz onde está explicada a ferramenta de que precisa.

- O contrato de entrada e saída, com as entradas, as saídas, as restrições e os exemplos concretos calculados à mão. Está no guia [01 Do enunciado ao problema delimitado](01-do-enunciado-ao-problema.md), secção "O contrato de entrada e saída".
- A regra da informação que falta, do guia 01, secção "Dados relevantes e pormenores do contexto". Quando o enunciado não diz o que acontece numa situação, não se inventa em silêncio. Decide-se, e escreve-se a decisão.
- O exemplo mínimo, a entrada mais pequena e simples que ainda mostra uma falha: guia 01, secção "Reproduzir a falha com um exemplo mínimo".
- As variáveis, com o tipo à frente na linha onde nascem, e as constantes, escritas com `const`. Estão no guia [02 Estado, sequência e representações](02-estado-sequencia-representacoes.md), secções "A linha onde a variável nasce" e "Constantes".
- A leitura com `ler valor` e a escrita no ecrã com `Escreve:`, do guia 02.
- A tabela de trace, em que se executa um algoritmo à mão, instrução a instrução: guia 02, secção "Tabela de trace". Faz-se o que está escrito, e não o que achas que o algoritmo devia fazer.
- As comparações e a cadeia `Se`, `Senão se`, `Senão`: guia [03 Decisões e validação](03-decisoes-e-validacao.md), secção "Seleção encadeada". A primeira condição verdadeira ganha, e o `Senão` apanha tudo o que sobra.
- As fronteiras e os três valores que se testam em cada uma: guia 03, secção "Fronteiras e casos de teste".
- Os resultados esperados escritos antes de haver algoritmo, no passo 4 do exemplo guiado do guia 03. É o ponto de partida do passo 2 deste projeto.
- O `Para` na primeira forma, com a sua condição escondida: guia [04 Repetição e arrays](04-repeticao-e-arrays.md), secção "A primeira forma: `Para ... de ... até ...`".
- A pergunta que decide entre `Enquanto` e `Para`: guia 04, secção "Escolher entre `Enquanto` e `Para`".
- O contador: guia 04, secção "O contador".
- A tabela de iterações, do guia 04, na secção com o mesmo nome. Cada linha é a fotografia do estado no momento em que o ciclo testa a condição.
- A rotina da depuração, em resumo: guia 04, no início de "Erros frequentes".
- Os testes escolhidos antes de olhar para a solução: guia [05 Funções e modelo integrado](05-funcoes-e-modelo-integrado.md), secção "Decompor um problema em funções".
- O dossiê de um problema: guia 05, passo 8 do exemplo guiado.

Do guia 05 não precisas de mais nada, porque este algoritmo não precisa de funções. Se quiseres pôr uma parte dele numa função, podes, e não perdes nada por isso.

Testar e depurar não tiveram uma aula só para eles. Foste fazendo as duas coisas ao longo dos guias. Os exemplos guiados comparam o trace com o que o contrato previa. As secções de erros frequentes mostram, para cada erro, a entrada que o revela. O que ainda não fizeste foi escolher os casos de um algoritmo inteiro antes de o escrever. Também ainda não seguiste a rotina da depuração do princípio ao fim, por escrito. Neste projeto fazes tudo isso, com a forma que a avaliação pede. Se ainda não leste alguma das secções dos guias, ou se alguma ainda não foi trabalhada em aula, não faz mal. O professor recorda cada ferramenta no passo em que ela aparece, e depois da aula podes relê-las com calma.

Neste projeto não há arrays nem validação de dados. No passo 1 vais perceber porque é que a validação não faz falta.

## Como vais trabalhar

Não tens de resolver este projeto sozinho. O professor resolve-o contigo, no quadro, a pensar em voz alta. O teu trabalho é acompanhar cada passo e pensar nas perguntas antes de o professor avançar. Respondes quando ele perguntar, e escreves no caderno tudo o que fica no quadro.

Muitas vezes o professor vai parar e perguntar o que se faz a seguir. É nesse momento que se aprende, porque és tu que decides antes de veres a decisão escrita. Uma resposta errada dita em voz alta, numa aula destas, não custa nada e ajuda a turma inteira. Muitas vezes é o erro que outros também iam cometer.

Precisas só do caderno e de um lápis. Não precisas de dados na aula, e há uma boa razão para isso.

O algoritmo deste projeto não lança dados. São os jogadores que lançam dados verdadeiros, e cada um escreve o valor que saiu. O algoritmo só faz o que é preciso fazer com esses valores: comparar, contar e decidir. Se fosse o algoritmo a inventar os valores, cada execução dava um duelo diferente, e um caso de teste nunca se podia repetir. Quando um resultado parecesse errado, não havia maneira de voltar a ver o mesmo duelo para procurar o erro. Assim, cada caso de teste é uma lista de valores escrita por ti. Executa-se as vezes que quiseres, sempre com o mesmo resultado.

Este documento é mais comprido do que o tempo da aula deixa ler, e é de propósito. Na aula, o professor diz em poucas palavras o que os passos 2, 5 e 6 explicam por extenso. Em casa, relê essas explicações com calma. São elas que vais consultar no projeto 2 e na avaliação.

No fim, guardas o projeto no teu portefólio. A secção "O que fica no teu portefólio", no fim deste documento, diz que peças guardas e com que nomes.

## O jogo

> Dois jogadores fazem um duelo de dados de cinco rondas. Em cada ronda, cada jogador lança um dado verdadeiro, de seis faces, e escreve o valor que saiu. Primeiro escreve o jogador 1, e depois o jogador 2. Quem tirar mais ganha a ronda, e o algoritmo escreve "Ronda para o jogador 1" ou "Ronda para o jogador 2". Se os dois tirarem o mesmo, escreve "Ronda empatada". No fim das cinco rondas, ganha o duelo quem tiver ganho mais rondas. O algoritmo escreve então "Ganhou o jogador 1" ou "Ganhou o jogador 2".

Por exemplo, numa ronda em que o jogador 1 tira 4 e o jogador 2 tira 2, o algoritmo escreve "Ronda para o jogador 1". Numa ronda em que o jogador 1 tira 3 e o jogador 2 tira 6, escreve "Ronda para o jogador 2".

Lê o enunciado duas vezes, como no passo 1 do exemplo guiado do guia 01. Na primeira leitura, percebe o jogo. Na segunda, de lápis na mão, sublinha os números e as mensagens que o algoritmo tem de escrever. Sublinha também as palavras que dizem quando acontece cada coisa, como "em cada ronda" e "no fim das cinco rondas". São essas palavras que vão decidir, no passo 3, o que fica dentro do ciclo e o que fica fora dele.

Antes do passo 1, inventa um duelo com o colega do lado. São cinco rondas, com valores à vossa escolha, escritos em duas colunas, uma por jogador. Decidam, só com o enunciado, o que o algoritmo devia escrever em cada ronda e no fim. Guardem esse duelo. Pode vir a ser um dos vossos casos de teste, e pode também levar-vos à pergunta que o passo 1 vai fazer.

## Passo 1: o contrato (7 min)

O contrato vem primeiro porque diz exatamente o que o algoritmo tem de fazer, antes de se pensar em como o vai fazer. O enunciado está escrito para pessoas, e as pessoas preenchem as falhas sem dar por isso. O contrato transforma-o em respostas precisas, e é dele que vão sair os resultados esperados do passo 2. O enunciado e o contrato são a única autoridade sobre o que o algoritmo deve fazer. Sem contrato, os resultados esperados seriam palpites, e um teste que compara o obtido com um palpite não prova nada.

No guia 01, o contrato tinha quatro partes: as entradas, as saídas, as restrições e os exemplos concretos. Num projeto acrescentam-se duas, que tornam explícito o que no guia ficava dito pelo meio do texto. A primeira são as condições, isto é, as situações diferentes que podem acontecer e que obrigam o algoritmo a fazer coisas diferentes. A segunda são as decisões sobre o que o enunciado não diz. Os exemplos concretos dão tanto trabalho num projeto que ganham um passo só para eles: são a tabela de casos do passo 2.

O professor escreve o contrato no quadro, parte a parte, e tu copias. A coluna da direita não é a resposta. Diz o que cada parte tem de responder.

| Parte do contrato | O que tem de responder |
| --- | --- |
| Entradas | Que valores o algoritmo recebe, quantos são, por que ordem chegam, de que tipo são, entre que limites ficam e porquê |
| Saídas | O que o algoritmo escreve e em que momento: durante o jogo e no fim |
| Restrições | As regras fixas, que valem em todos os duelos, incluindo os valores do enunciado que nunca mudam e que vão ser constantes |
| Condições | As situações diferentes que podem acontecer numa ronda e no fim do duelo, e que obrigam o algoritmo a fazer coisas diferentes |
| Decisões | O que o enunciado não diz e tem de ser decidido, cada coisa numa frase que começa por "Decisão:" |
| Exemplos concretos | Ficam para o passo 2, onde se tornam a tabela de casos |

Pensa nestas perguntas antes de o professor avançar, e escreve as tuas respostas a lápis, na margem do caderno:

1. Quantos valores escreve cada jogador ao longo de um duelo? E os dois juntos? Por que ordem chegam ao algoritmo?
2. Que valores pode ter cada entrada? Pode aparecer um 0, um 7 ou um 2,5? Que palavras do enunciado te deixam responder a isto?
3. Há algum número no enunciado que nunca muda de um duelo para outro? Como é que se escreve um valor destes no pseudocódigo? (Guia 02, "Constantes".)
4. O que é que o algoritmo escreve durante o jogo, e quantas vezes? E o que escreve no fim?
5. Que situações diferentes podem acontecer numa ronda? E no fim do duelo, quando se comparam as rondas que cada jogador ganhou?

### O que o enunciado não diz

A pergunta 5 leva-te a uma situação de que o enunciado não fala. Pensa em todos os finais possíveis, contando as rondas ganhas de cada jogador. Há algum para o qual a última frase do enunciado não diga o que escrever?

É o caso a que o guia 01 chama informação que falta. Não há nenhuma palavra vaga para sublinhar, mas há uma pergunta sem resposta. E é dos mais perigosos, porque um algoritmo escrito sem pensar nela não se queixa. Escreve qualquer coisa no fim, e essa coisa depende da forma como calhou ficar escrita a última decisão do algoritmo. Não depende de alguém ter pensado no que era justo.

O guia 01 diz o que fazer, na secção "Dados relevantes e pormenores do contexto". Não se inventa em silêncio. Pergunta-se a quem escreveu o enunciado. Se não for possível, toma-se uma decisão e escreve-se, para que quem ler a solução saiba em que pressuposto ela assenta. Foi o que o contrato dos livros em caixas fez com os zero livros, quando decidiu dizer por palavras que não há última caixa. Na aula, quem escreveu o enunciado está ali, e a decisão toma-se em conjunto, no quadro.

6. Que final é esse, e o que diz o enunciado sobre ele?
7. Que decisões possíveis vês? Para cada uma, pensa em duas coisas: é justa para os dois jogadores? Obriga a mudar alguma coisa que o enunciado fixou, como o número de rondas?
8. Porque é que esta decisão tem de ficar escrita já, no passo 1, e não depois de o algoritmo estar feito?

### A suposição que dispensa a validação

No guia 01, na secção "O contrato de entrada e saída", viste porque é que um contrato se chama assim: é um acordo. Quem usa o algoritmo compromete-se a dar entradas dentro do combinado, e o algoritmo compromete-se a dar a saída prometida. Se alguém der uma entrada fora do combinado, há duas hipóteses. Ou o contrato diz o que acontece nesse caso, ou deixa claro que esse caso não está coberto.

Validar uma entrada é verificar se o valor é aceitável e decidir o que fazer quando não é. Está explicado no guia 03, na secção "Casos válidos, casos inválidos e validação". Vai ser trabalhado em aula antes do projeto 2, que vai precisar disso. Este projeto pode dispensar a validação, desde que o contrato diga porquê, numa frase escrita. A resposta à pergunta 2 é o sítio onde essa frase nasce. Repara na forma como o enunciado descreve o dado e de onde vem cada valor que o jogador escreve.

Uma frase destas, no contrato, chama-se uma **suposição**: uma coisa que o contrato dá como certa e que o algoritmo não verifica. Escreve-se nas entradas, ao pé dos valores a que diz respeito. Uma suposição escrita é honesta, porque quem lê o contrato fica a saber em que condições o algoritmo funciona. Uma suposição que ninguém escreveu é um erro à espera de acontecer. Só se descobre no dia em que a coisa dada como certa falha.

Já viste coisas da mesma família nos guias. O guia 03, na secção da validação, assume que a pessoa escreve sempre um número inteiro numa linha com `ler valor`. Diz também que o que fazer com letras fica para o Python. E a função que calcula a média, no guia 05, tem a pré-condição "com pelo menos um elemento". Essa frase deixa claro que o array vazio não está coberto. Em todos estes casos, alguém pensou na situação e escreveu-a.

Repara que a suposição e a decisão são coisas diferentes. A decisão escolhe o que o algoritmo faz numa situação que pode mesmo acontecer. A suposição diz que uma situação não vai acontecer, e porquê.

## Passo 2: a tabela de casos esperados, antes do algoritmo (10 min)

Este passo faz-se sem algoritmo nenhum, e é de propósito. Já o fizeste duas vezes nos guias, talvez sem dar por isso. No guia 01, os exemplos concretos do contrato dos livros calculam-se à mão, sem algoritmo nenhum. No guia 03, no passo 4 do exemplo guiado, os resultados esperados das notas escrevem-se antes de haver algoritmo, a partir do enunciado. Num projeto, esta ordem passa a ser uma regra, e vale a pena perceberes porquê.

### O resultado esperado decide-se antes de executar

Testar um algoritmo é comparar o que ele escreve com o que devia escrever. O que ele escreve chama-se **resultado obtido**. O que devia escrever chama-se **resultado esperado**. Um teste só serve se o esperado vier de outro sítio que não o próprio algoritmo: do enunciado e do contrato.

Se calculares o esperado depois de veres o que o algoritmo escreve, o teu cérebro aceita o resultado porque o viu escrito. É fácil convencer-te de que era isso mesmo que esperavas. Na prática, estás a perguntar ao algoritmo se ele concorda consigo próprio. A resposta é sempre sim, e o teste não apanha erro nenhum. Escrito antes, a partir do enunciado e do contrato, o resultado esperado fica à espera do obtido, e qualquer diferença salta à vista.

Há uma segunda vantagem. Enquanto não há algoritmo, não há nada para olhar senão o enunciado. Por isso, os casos que escolhes não herdam os pontos cegos de quem vai escrever o algoritmo. Se te esqueceres de uma situação quando escreveres o algoritmo, a tabela lembra-se dela por ti. O guia 05, na secção "Decompor um problema em funções", chama a estes testes, escolhidos antes de olhar para a solução, testes independentes da solução. Testam o que o algoritmo devia fazer, e não o que tu achas que ele faz.

### Como se escreve um caso deste jogo

Neste jogo, cada caso de teste é um duelo inteiro: dez valores, dois por ronda. Para os escreveres depressa e sem confusões, escreve cada ronda como um par entre parênteses, com o valor do jogador 1 primeiro. O par (4, 2) quer dizer que o jogador 1 tirou 4 e o jogador 2 tirou 2. Um caso são cinco pares, pela ordem das rondas.

O resultado esperado de um caso é tudo o que o algoritmo tem de escrever, além das perguntas aos jogadores. São a mensagem de cada uma das cinco rondas e a mensagem do fim. Para caber na tabela, podes abreviar as mensagens das rondas:

- J1 quer dizer "Ronda para o jogador 1";
- J2 quer dizer "Ronda para o jogador 2";
- E quer dizer "Ronda empatada".

A mensagem do fim escreve-se por inteiro. Não deixes as mensagens das rondas de fora. Um algoritmo que acerta no fim e escreve mal uma ronda está errado, e só uma tabela com as rondas o mostra.

Para calcular o resultado esperado de um caso não precisas de algoritmo nenhum. Decide cada ronda pelo enunciado e faz um risco ao lado do jogador que a ganhou. No fim, compara os riscos dos dois.

### Os três tipos de caso

A tabela tem estas colunas, que se preenchem agora:

| N.º | Tipo | Entradas, ronda a ronda | Resultado esperado | Porque foi escolhido |
| ---: | --- | --- | --- | --- |

No passo 5, depois de executar, acrescentam-se mais duas, "Resultado obtido" e "Passou?".

A coluna "Tipo" é nova. Nos guias, as tabelas de casos tinham as entradas, o resultado esperado e a razão da escolha. Num projeto, cada caso diz também de que tipo é, e há três tipos:

- Um caso **normal** é um caso típico, dos que se imaginam ao ler o enunciado. São exemplos os 30 livros do guia 01 e os 135 minutos do guia 02. Mostra que o algoritmo faz o que se espera no dia a dia, mas sozinho apanha poucos erros.
- Um caso de **fronteira** está no sítio onde a resposta do algoritmo muda, ou imediatamente ao lado dele. São exemplos a nota 10 e a nota 9 do guia 03. Viste na secção "Fronteiras e casos de teste" porque é que os erros de decisão se concentram aí. Uma comparação com o igual a mais ou a menos dá o mesmo resultado em todos os valores, menos no da fronteira. Para cada fronteira, testa-se o valor que está em cima dela e os vizinhos de um lado e do outro. O caso no limite de uma regra do guia 01, como os 24 livros, é um caso destes. Os casos extremos do guia 01, como o zero, também se marcam como fronteira, porque estão na ponta do que pode acontecer.
- Um caso **inválido** tem uma entrada que não cumpre o contrato, como a nota 21 do guia 03. Serve para ver o que o algoritmo faz com ela: se a trata como o contrato manda, ou se a aceita como se fosse boa.

Uma tabela bem feita tem casos dos três tipos, a não ser que o contrato diga porque é que um deles não pode aparecer. É para isso que o tipo se escreve: quem lê a tabela vê logo se falta algum, e porquê.

### Os casos deste jogo

Este jogo tem fronteiras em dois sítios diferentes. Uma está dentro de cada ronda, quando se comparam os dois dados. A outra está no fim do duelo, quando se comparam as rondas ganhas. No quadro, a tabela vai ter cerca de seis casos.

Nesta tabela não vão aparecer casos do tipo inválido. Não é esquecimento, e não pode parecer esquecimento a quem ler o teu portefólio. Uma tabela sem casos inválidos só está completa se o contrato disser porque é que não há entradas inválidas. Se o contrato não o disser, falta uma linha à tabela, ou falta uma frase ao contrato. Quando o professor escrever a tabela, confirma que a razão ficou escrita no passo 1.

Antes de o professor avançar, pensa nestas perguntas:

1. Numa ronda, onde é que a resposta muda de "Ronda para o jogador 1" para "Ronda para o jogador 2"? Que par de valores fica exatamente em cima dessa fronteira, e que pares ficam imediatamente de um lado e do outro?
2. No fim do duelo, onde é que a resposta muda de um vencedor para o outro? Que duelo fica exatamente em cima dessa fronteira? E qual é a menor diferença de rondas ganhas com que um jogador ainda ganha o duelo?
3. O duelo tem sempre cinco rondas, por isso este jogo não tem o caso de zero voltas do guia 04. Há algum duelo em que nenhum jogador chega a ganhar uma ronda? O que esperas que o algoritmo escreva nesse duelo?
4. Consegues escrever o resultado esperado de um duelo em que os dois ganharam o mesmo número de rondas sem a decisão do passo 1? Porquê?
5. A ordem pela qual as rondas são ganhas pode mudar o vencedor do duelo? Que duelo escolherias para mostrar que um algoritmo não se deixa enganar pelo que aconteceu na última ronda?
6. Para ganhar o duelo, um jogador precisa de ganhar três rondas? Pode alguém ganhar com menos?
7. Olha para a tua tabela. Cada mensagem do enunciado aparece no resultado esperado de pelo menos um caso? E a mensagem que a decisão do passo 1 vier a criar?

## Passo 3: o algoritmo (14 min)

Agora, e só agora, escreve-se o algoritmo. A tabela de casos do passo 2 é o alvo. O algoritmo tem de escrever, para cada caso, exatamente o resultado esperado que lá está.

Antes de escrever a primeira linha, decompõe o problema, como aprendeste no guia 01. Quase todos os algoritmos com um ciclo têm três partes:

- o que se faz uma vez, antes do ciclo;
- o que se repete, uma vez por volta;
- o que se faz uma vez, depois do ciclo.

As palavras que sublinhaste no enunciado, as que dizem quando acontece cada coisa, dizem-te o que vai para cada parte. No pseudocódigo, é a indentação que mostra essa separação. O que está indentado por baixo do ciclo repete-se, e o que está encostado à margem executa-se uma vez só. O guia 04, na secção "A indentação mostra o que está dentro do ciclo", mostra como a mesma linha com outra margem faz outro algoritmo. A mensagem de fim da tabuada, com mais quatro espaços, aparecia três vezes.

O professor escreve o algoritmo no quadro na forma de pseudocódigo das aulas, e tu copias. Lembra-te de como é essa forma:

- não tem cabeçalho nem linhas de início e de fim;
- as constantes escrevem-se com `const`;
- cada variável tem o tipo à frente na linha onde nasce, e não o tem daí para a frente;
- os blocos marcam-se só pela indentação, com quatro espaços por nível.

Se preferires, podes escrever ao lado o mesmo algoritmo em frases claras. Também vale, aqui e na avaliação, desde que não deixe dúvidas: quanto, quando, e o que acontece se não der. E se quiseres pôr uma parte dele numa função, como aprendeste no guia 05, também podes. O professor escreve a versão sem funções, porque não fazem falta.

Pensa nestas perguntas antes de o professor avançar:

1. `Enquanto` ou `Para`? Antes de o ciclo começar, já se sabe quantas vezes ele se vai repetir? (Guia 04, "Escolher entre `Enquanto` e `Para`".)
2. O que acontece em cada ronda, e por que ordem? Escreve as ações por palavras, uma por linha, antes de pensares em pseudocódigo.
3. Para decidir, no fim, quem ganhou o duelo, o que é que o algoritmo tem de ir guardando ao longo das rondas? Que padrão do guia 04 é este?
4. Quantas variáveis dessas são precisas? O enunciado manda escrever quantas rondas ficaram empatadas? Uma variável que é atualizada e nunca é usada faz falta? Decide e justifica.
5. Onde nascem essas variáveis, antes do ciclo ou dentro dele? O que acontecia se nascessem dentro? (Guia 04, "Inicializar fora do ciclo".)
6. Os valores dos dados aparecem pela primeira vez dentro do ciclo. Em que linha levam o tipo? (Guia 02, "A linha onde a variável nasce".) Essa linha escreve-se uma vez e executa-se cinco. O que acontece, em cada ronda, ao valor da ronda anterior? E porque é que, para os dados, a linha pode ficar dentro do ciclo? Compara com a tua resposta à pergunta 5.
7. Dentro do ciclo, a ronda tem três resultados possíveis. Por que ordem fazes as perguntas, e qual dos três fica no `Senão`? Precisas de escrever a condição desse último, ou o `Senão` chega? Porquê? (Guia 03, "Seleção encadeada".)
8. Onde fica a decisão do duelo: dentro do ciclo ou depois dele? O que aparecia no ecrã se ficasse no sítio errado?
9. Que ramo da decisão do fim existe só por causa da decisão do passo 1?

Com o algoritmo escrito, faz uma pergunta que só agora se pode fazer, porque precisa do algoritmo à frente. Há algum ramo de um `Se` por onde nenhum caso da tabela passa? Um ramo, como viste no guia 03, é cada um dos caminhos de uma decisão. Um ramo por onde nenhum caso passa nunca foi experimentado, e um erro escondido lá dentro passava em todos os testes. Se houver um, acrescenta um caso que passe por ele. O resultado esperado desse caso calcula-se pelo enunciado, como os outros, e não pelo algoritmo.

## Passo 4: a tabela de iterações (7 min)

Um pseudocódigo não corre num computador. Executá-lo é fazer o trace à mão, como no guia 02. Para um ciclo, a forma mais curta é a tabela de iterações do guia 04. Tem uma linha por cada teste da condição do ciclo. Cada linha mostra a fotografia do estado nesse momento, a condição com os valores substituídos e o que acontece durante a volta seguinte.

No `Para` da primeira forma, a condição está escondida no "até". Como o guia 04 explica na secção "A primeira forma: `Para ... de ... até ...`", quer dizer "continua enquanto a variável de controlo for menor ou igual ao limite". Na tabela, escreve-se por extenso, com os valores.

O professor escolhe um dos casos da tabela, normalmente o que passa por mais ramos do algoritmo. Faz a tabela de iterações no quadro, com a turma a dizer cada valor antes de ele o escrever. A tabela tem estas colunas:

- uma para a variável do `Para`;
- uma para cada valor lido;
- uma para cada contador;
- a da condição;
- a do que acontece durante a volta.

Nesta última coluna escreve-se o que é lido, que condição da ronda dá verdadeiro, que mensagem aparece e que contador muda. Lembra-te da regra do guia 04. As colunas mostram o estado no momento do teste. Por isso, um valor lido durante uma volta só aparece na sua coluna na linha seguinte. E lembra-te da regra do guia 02: uma variável fica "sem valor" até à linha onde nasce, e as constantes não têm coluna.

Pensa nestas perguntas antes de o professor avançar:

1. Se só pudesses fazer a tabela de iterações de um dos casos, qual escolhias? Porquê esse?
2. Antes de começar: quantas linhas vai ter a tabela? Porquê esse número, e não o número de rondas?
3. Na primeira linha, que valores têm as colunas dos dados? Porquê?
4. Depois de uma ronda empatada, que colunas mudam na linha seguinte, e quais ficam iguais?
5. Quanto vale a variável do `Para` na última linha? Pode usar-se esse valor depois do ciclo? (Guia 04, regra 4 do `Para`.)
6. Depois da última linha, que instruções são executadas, e que mensagem aparece no fim? Bate certo com o resultado esperado que escreveste no passo 2?

## Passo 5: executar os outros casos e comparar o obtido com o esperado (6 min)

A tabela de iterações prova que o algoritmo funciona para um caso, e não diz nada sobre os outros. Por isso, executam-se todos os casos da tabela do passo 2, e não só aquele de que se fez a tabela de iterações.

Não precisas de uma tabela de iterações inteira para cada caso. Segue cada ronda pela cadeia de decisões, anota a mensagem que o algoritmo escreve e faz um risco no contador que muda. Depois da quinta ronda, aplica a decisão do fim aos riscos que tens. Mas executa o que está escrito, e não o que achas que o algoritmo devia fazer. É a regra mais importante do trace, na secção "Tabela de trace" do guia 02. O guia 02 mostra o que acontece a quem a esquece, em "Preencher o trace com o que se esperava". O trace fica certo, e o algoritmo continua errado.

Na aula, cada par executa um dos casos e diz o resultado em voz alta. Depois, acrescentam-se à tabela as duas colunas que faltavam, "Resultado obtido" e "Passou?", e preenchem-se caso a caso.

### Testar é comparar o obtido com o esperado

Com as duas colunas novas, a tabela mostra o que é testar. Para cada caso, tens lado a lado o resultado esperado, escrito antes, e o resultado obtido, escrito agora. Se forem iguais, o caso passou, e escreves "Sim". Se forem diferentes, o caso falhou, e escreves "Não".

Quando um caso falha, há dois sítios onde o erro pode estar. Pode estar no algoritmo, que faz uma coisa diferente do que o contrato pede. Ou pode estar no resultado esperado, que foi mal calculado no passo 2. Por isso, antes de mexeres no algoritmo, voltas a calcular o esperado desse caso. Calculas outra vez a partir do enunciado e do contrato, com os riscos. Se o esperado estava errado, corriges o esperado, e o caso passa. Se estava certo, o erro está no algoritmo, e é para isso que serve o passo 6. O que nunca se faz é copiar o obtido para a coluna do esperado só para o caso passar. Era voltar a perguntar ao algoritmo se concorda consigo próprio.

Pensa nestas perguntas antes de o professor avançar:

1. Se um dos casos falhar, o que confirmas antes de mexer no algoritmo, e a partir de onde?
2. Depois de executares todos os casos, todos os ramos do algoritmo foram percorridos por pelo menos um deles?
3. Todos os casos passarem prova que o algoritmo está certo? Qual dos teus casos te dá mais confiança, isto é, qual apanharia mais erros se o algoritmo os tivesse? Responde em voz alta, com o número do caso e a razão.

## Passo 6: depurar com a rotina da depuração (11 min)

Um teste que falha é útil: o erro apareceu no caderno, e não no meio de um jogo a sério. Agora é preciso encontrar a causa e corrigi-la. A isto chama-se **depurar**.

Este passo faz-se sempre, mesmo que todos os casos tenham passado no passo 5. É aqui que vês pela primeira vez a rotina da depuração inteira, com o registo que a avaliação pede. Se algum caso falhou, depura-se esse erro. Se nenhum falhou, o professor mostra uma versão do algoritmo com um erro que costuma aparecer em algoritmos destes. É como se tivesse saído do quadro, e depura-se essa versão. Guarda as duas versões, a com erro e a corrigida. No portefólio, a versão com erro é a prova de que o encontraste.

### A rotina da depuração

Quem começa costuma depurar à sorte: muda uma linha, experimenta, muda outra, até o caso que falhou passar. Às vezes acerta. Mas não sabe porque é que acertou, e muitas vezes a mudança que acertou esse caso estragou outro, que já estava bom. Depurar com método é seguir sempre a mesma rotina, com os mesmos cinco passos, pela mesma ordem. Os guias 04 e 05 apresentam-na em resumo, no início dos erros frequentes. Aqui vês cada passo por extenso, e cada um diz-te o que fazer a seguir. É a mesma rotina em todas as linguagens que vais aprender.

1. **Observar e reproduzir o erro.** Escreve o caso que falhou, o resultado esperado e o resultado obtido, e diz exatamente em que mensagem diferem. O resultado esperado tira-se do enunciado e da tabela, e nunca do algoritmo que falha. Depois executa o caso outra vez, devagar, para confirmares que o erro volta a aparecer. Um erro que se consegue repetir é um erro que se consegue estudar.
2. **Formular uma hipótese.** Escreve, numa frase, o que achas que está a causar o erro. A esta frase chama-se **hipótese**: um palpite com fundamento, que os valores do trace podem confirmar ou desmentir. "O algoritmo está mal" não é uma hipótese, porque não diz que instrução procurar nem que valores olhar.
3. **Verificar a hipótese.** Segue os valores com o trace, no caso mais curto que ainda mostra o erro. Esse caso é o exemplo mínimo do guia 01, na secção "Reproduzir a falha com um exemplo mínimo". Com ele, o trace fica curto e a causa salta à vista. Procura a primeira linha da tabela onde uma variável fica com um valor diferente do que devia ter. É o que o guia 02 manda fazer no passo 7 do exemplo guiado, quando um caso não coincide com o previsto. Se o trace confirmar a hipótese, encontraste a causa. Se a desmentir, a hipótese era falsa, e fazes outra, agora com o que o trace te mostrou.
4. **Corrigir a causa.** A causa é a instrução que produz o valor errado. O sintoma é o que se vê de errado no ecrã. Muda a instrução que produz o erro, uma causa de cada vez, mudando o mínimo possível. Uma correção que acerta o ecrã do caso que falhou, sem mexer nessa instrução, corrige só o sintoma. O erro volta a aparecer noutro caso.
5. **Voltar a testar tudo.** Depois de corrigir, executas outra vez todos os casos da tabela, também os que já passavam, e explicas o que mudou. A este novo teste da tabela inteira chama-se **teste de regressão**. Procura regressões, isto é, coisas que funcionavam e deixaram de funcionar por causa da correção.

O problema dos livros em caixas, do guia 01, mostra porque é que os passos 4 e 5 são precisos. Quem esquece a caixa incompleta divide os livros por 12 e fica só com a parte inteira. Isso dá 2 caixas para 30 livros, quando são 3. Somar sempre mais uma caixa no fim acerta os 30 livros. Mas passa a dar 3 caixas para 24 livros, quando são 2, e 1 caixa para 0 livros, quando não é preciso nenhuma. Essa correção acertou o sintoma, o número de caixas para 30 livros, e estragou dois casos que estavam certos. A causa era outra: a caixa a mais só é precisa quando sobram livros. A correção da causa é somar uma caixa só nesse caso. Quem só voltasse a experimentar os 30 livros ficava convencido de que estava tudo certo. Só o teste de regressão, com a tabela inteira, mostra os dois casos estragados.

### O registo de depuração

Cada depuração escreve-se num **registo de depuração**, com quatro partes. É a forma do exercício 6 da ficha do tema 05, e é a forma que a avaliação pede:

| Parte do registo | O que se escreve |
| --- | --- |
| O que se observou | O caso que falhou, o resultado obtido e a mensagem que está errada; e o exemplo mínimo, com o que ele dá |
| O que se esperava | O resultado esperado desse caso, o que está na tabela, e o do exemplo mínimo, calculado pelo enunciado |
| A causa | A instrução que produz o erro, e o que o trace mostrou: a primeira linha onde uma variável fica com um valor diferente do que devia ter |
| A correção | A instrução que mudou, e onde, mudando o mínimo possível |

Por baixo do registo, numa linha, escreves o resultado do teste de regressão. Diz quantos casos da tabela passam depois da correção, contando os que já passavam antes. Um registo sem esta linha está incompleto, porque não mostra que a correção não estragou nada.

Repara como os passos da rotina enchem o registo. O primeiro passo dá as duas primeiras partes, e o terceiro acrescenta-lhes o exemplo mínimo. O segundo e o terceiro dão a causa, já confirmada pelo trace: a hipótese só passa a causa depois de o trace a confirmar. O quarto dá a correção. E o quinto dá a linha de baixo.

Pensa nestas perguntas antes de o professor avançar:

1. Pensa nos erros frequentes dos guias 03 e 04, sobretudo nos que envolvem contadores, a indentação e cadeias de `Se`. Qual deles te parece mais provável num algoritmo como este? Que caso da tabela o apanhava?
2. O exemplo mínimo é o caso mais pequeno e simples que ainda mostra o erro. Neste jogo não se podem tirar rondas, porque são sempre cinco. Como é que tornas um caso mais simples?
3. A correção que vais escrever explica porque é que o valor ficou errado, ou só acerta o resultado do caso que falhou?
4. Que casos da tabela já passavam antes da correção? Depois de corrigires, o que te garante que continuam a passar?

## O que fica no teu portefólio

O portefólio é onde guardas os dois projetos feitos com ajuda: uma pasta no computador, ou as páginas do caderno, como o professor indicar. Vais poder consultá-lo na avaliação, e por isso deve ficar completo e arrumado.

O que guardas deste projeto é parecido com o dossiê do problema que o guia 05 descreve no passo 8 do exemplo guiado. Tem a análise, que aqui é o contrato com a tabela de casos. Tem o pseudocódigo. E tem os testes, que aqui são a tabela de iterações e a tabela de casos com os resultados obtidos. Não tem a decomposição em funções nem os contratos das funções, porque este algoritmo não usa funções. Tem uma peça que o dossiê do guia não tem: o registo de depuração.

Para este projeto, guarda:

- o enunciado do jogo;
- o contrato, com a suposição e a decisão;
- a tabela de casos esperados, com o tipo de cada caso, os resultados obtidos e a coluna "Passou?";
- o algoritmo;
- a tabela de iterações;
- o registo de depuração, com a versão com erro, a versão corrigida e a linha do teste de regressão.

Se guardares em ficheiros, usa um ficheiro por peça. Dá-lhes nomes como manda o guia 02, no passo 8 do exemplo guiado: em minúsculas, com hífenes e sem acentos nem espaços. Os nomes são os mesmos no projeto 2, só com o nome do jogo à frente.

| Peça | Nome do ficheiro |
| --- | --- |
| O enunciado e o contrato, com a suposição e a decisão | `duelo-de-dados-contrato` |
| A tabela de casos, com os resultados obtidos, e a tabela de iterações | `duelo-de-dados-testes` |
| O algoritmo corrigido | `duelo-de-dados-algoritmo` |
| A versão com o erro | `duelo-de-dados-algoritmo-com-erro` |
| O registo de depuração, com a linha do teste de regressão | `duelo-de-dados-registo-depuracao` |

As páginas do caderno também contam. Fotografa-as ou passa-as a limpo, e junta-as às peças a que pertencem.

Antes de fechares o caderno, confirma:

- [ ] O contrato tem as entradas, as saídas, as restrições e as condições, cada uma escrita numa frase. A suposição sobre os valores dos dados está nas entradas, e a decisão sobre o que o enunciado não dizia começa por "Decisão:".
- [ ] A tabela de casos foi escrita antes do algoritmo, e cada caso tem o tipo e a razão da escolha.
- [ ] Cada mensagem do enunciado, e a da decisão, aparece no resultado esperado de pelo menos um caso.
- [ ] A tabela de iterações tem a linha do último teste, o que dá falso e faz sair do ciclo.
- [ ] Todos os casos têm o resultado obtido e a coluna "Passou?" preenchida.
- [ ] O registo de depuração tem as quatro partes, as duas versões do algoritmo e, por baixo, o resultado do teste de regressão.

## O que vem a seguir

O [projeto 2](05-projeto-2-adivinha-o-numero.md) é o jogo de adivinhar um número. Faz-se em pares, um passo de cada vez, com o professor a confirmar cada passo antes de passares ao seguinte. Leva cerca de 120 minutos. Vem depois da aula da validação de dados e da validação repetida, dos guias 03 e 04, porque vai precisar das duas. Segue o mesmo processo deste projeto, com a mesma rotina da depuração, o registo nas mesmas quatro partes e o teste de regressão. Junta-lhe o passo que aqui ficou de fora: melhorar o algoritmo e mostrar que a versão melhorada faz menos trabalho. Mede-se contando perguntas num exemplo pequeno, como o guia 05 conta voltas na secção "Duas soluções certas, uma mais eficiente".

Depois vem a avaliação prática: individual, com 120 minutos e um problema novo, que o professor entrega no dia. O processo é o mesmo dos dois projetos, e podes consultar os dois no teu portefólio. Antes da avaliação, o professor mostra-te a grelha com os critérios.

Até lá, a [ficha do tema 05](05-funcoes-e-modelo-integrado-exercicios.md) serve de prática para os passos deste projeto. O exercício 6 treina o registo de depuração, com as mesmas quatro partes. São o que se observou, o que se esperava, a causa e a correção. O exercício 7, o começo do dossiê, treina o contrato, com o resultado esperado calculado à mão antes de haver algoritmo.

![Rodapé](../imagens/rodape.png)
