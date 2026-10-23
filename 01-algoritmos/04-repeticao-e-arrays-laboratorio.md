![Cabeçalho](../imagens/cabecalho.png)

# Laboratório: Repetição e arrays

Laboratório do tema Repetição e arrays, do módulo Desenvolver algoritmos. Vais desenhar no diagrams.net o fluxograma de um algoritmo com um ciclo, com a seta que volta atrás até ao losango da condição. Cada passo diz o que fazer, porquê e o que deves ver, e avanças ao teu ritmo. O que não acabares na aula, acabas na aula seguinte, ou em casa se tiveres computador. Tudo o que precisas está aqui; o [guia do tema](04-repeticao-e-arrays.md) tem a teoria completa, para quem quiser saber mais.

Este laboratório é todo de fluxogramas, e é opcional. Só o fazes quando o professor o indicar, e nenhum exercício da ficha depende dele.

## O que vais construir

No fim, tens na tua pasta `algoritmos` o fluxograma de um algoritmo que conta os quilos de uma campanha de recolha de alimentos. Fica em dois ficheiros. Um é o desenho que se pode editar, `fluxograma-campanha-de-alimentos.drawio`. O outro é uma imagem, `fluxograma-campanha-de-alimentos.png`, que qualquer computador abre.

Este algoritmo tem um ciclo. Por isso, o fluxograma tem uma seta que volta atrás, para cima, até ao losango da condição do ciclo. Os fluxogramas sem ciclos não têm nenhuma seta assim. Essa seta é a técnica nova deste laboratório. O objetivo é desenhá-la de forma que qualquer pessoa perceba, sem hesitar, de onde sai e onde chega, sem a confundir com as outras setas.

O problema é este:

> A escola organiza uma campanha de recolha de alimentos. Cada turma entrega os alimentos que juntou, e a funcionária escreve quantos quilos a turma trouxe, um número inteiro. Uma turma pode não ter trazido nada, e nesse caso a funcionária escreve 0. Quando não há mais turmas, escreve -1. O algoritmo mostra quantas turmas entregaram, o total de quilos e a média por turma, mas a média só se houver pelo menos uma turma.

O algoritmo, em pseudocódigo:

```text
const SENTINELA = -1
int turmas = 0
int totalQuilos = 0
Escreve: "Quilos entregues pela turma (-1 para terminar)?"
int quilos = ler valor
Enquanto quilos != SENTINELA
    turmas = turmas + 1
    totalQuilos = totalQuilos + quilos
    Escreve: "Quilos entregues pela turma (-1 para terminar)?"
    quilos = ler valor
Escreve: "Turmas que entregaram: ", turmas
Escreve: "Total: ", totalQuilos, " kg"
Se turmas > 0
    float media = totalQuilos / turmas
    Escreve: "Média por turma: ", media, " kg"
Senão
    Escreve: "Não houve entregas, por isso não há média."
```

Leitura guiada: a linha `const` dá nome ao valor que marca o fim, o -1. A um valor assim, combinado para dizer "acabou", chama-se sentinela. Não pode ser o 0, porque o 0 é um dado, já que uma turma pode trazer 0 quilos. As duas linhas seguintes põem a 0 a contagem das turmas e o total dos quilos. Depois, o algoritmo faz a pergunta e lê o primeiro valor, antes do ciclo.

A linha do `Enquanto` é o ciclo. Repete as quatro linhas indentadas debaixo dela enquanto o valor lido não for a sentinela. O sinal `!=` quer dizer "é diferente de". Essas quatro linhas contam mais uma turma, somam os quilos dela ao total, e perguntam e leem o valor seguinte. Depois da última, o algoritmo não continua para baixo. Volta à linha do `Enquanto` e testa o valor novo. Quando o valor lido é -1, o ciclo termina, e o algoritmo continua na primeira linha sem indentação.

Depois do ciclo, o algoritmo escreve as turmas e o total. O `Se` final calcula a média só quando houve pelo menos uma turma. Com zero turmas, a conta seria 0 / 0, que não tem resultado, e por isso o `Senão` escreve uma mensagem.

Pelo caminho, ficas a saber planear a disposição de um fluxograma com um ciclo e desenhar a seta de volta. Ficas também a saber seguir o desenho com o dedo, volta a volta. Num ecrã, o dedo pode ser o ponteiro do rato: neste laboratório, "seguir com o dedo" quer dizer as duas coisas.

| Fase | O que muda | O que funciona no fim |
| --- | --- | --- |
| 1 | Planeias no papel onde fica cada figura | Um esquema em três faixas, com um caminho livre para a seta de volta |
| 2 | Pões as figuras e as setas que descem | Todas as figuras ligadas, menos a seta de volta e a saída do ciclo |
| 3 | Desenhas a seta de volta e a saída do ciclo | O losango do ciclo com duas setas a entrar e duas a sair, cada uma no seu ponto |
| 4 | Segues o desenho com um caso de teste | Quatro passagens pelo losango do ciclo, e os resultados certos no fim |
| 5 | Exportas uma imagem do desenho | O `.drawio` e o `.png` na pasta `algoritmos` |

## Palavras que vais usar

- Algoritmo: uma sequência finita de passos, cada um claro e possível de executar, que parte de uns dados e chega a um resultado.
- Pseudocódigo: a forma de escrever algoritmos que usamos nas aulas, com um vocabulário pequeno e sempre igual e uma instrução por linha.
- Fluxograma: o desenho de um algoritmo, com figuras ligadas por setas. A forma de cada figura diz que tipo de instrução está lá dentro, e as setas dizem a ordem.
- Terminal: a figura de pontas redondas onde o algoritmo começa, com `Início`, e acaba, com `Fim`. Na aplicação chama-se Terminator.
- Retângulo: a figura das contas e das instruções que dão um valor a uma variável. Na aplicação chama-se Process.
- Paralelogramo: a figura das entradas e das saídas, com `ler valor` ou `Escreve:`. Na aplicação chama-se Data.
- Losango: a figura de uma condição, com uma entrada e duas saídas. Na aplicação chama-se Decision.
- `ler valor`: a instrução que recebe um valor escrito por quem usa o algoritmo.
- `Escreve:`: a instrução que mostra texto e valores no ecrã.
- Constante: um valor fixo do problema, com o nome em maiúsculas, escrito com `const`, como `const SENTINELA = -1`.
- Tipo: o que diz que espécie de valor uma variável guarda. `int` é um número inteiro, e `float` é um número com casas decimais. Escreve-se à frente da variável só na linha onde ela nasce.
- Condição: uma pergunta cuja resposta só pode ser verdadeira ou falsa, `true` ou `false`, como `turmas > 0`. Escreve-se dentro do losango.
- Ciclo: uma parte de um algoritmo que se repete. Com `Enquanto`, repete-se enquanto a condição for verdadeira. Para saber mais, vê a secção "Enquanto: repetir enquanto a condição for verdadeira" do [guia](04-repeticao-e-arrays.md).
- Corpo do ciclo: as linhas que se repetem, indentadas debaixo do `Enquanto`.
- Inicialização: a instrução, antes do ciclo, que dá o primeiro valor a uma variável que o ciclo usa, como `int turmas = 0`.
- Atualização: a instrução do corpo que muda a variável de que a condição depende, aqui `quilos = ler valor`.
- Volta: cada vez que o corpo do ciclo se executa. Também se diz iteração.
- Indentação: o recuo de quatro espaços que mostra, no pseudocódigo, que uma linha está dentro de um ciclo, de um `Se` ou de um `Senão`.
- Sentinela: o valor combinado que quer dizer "acabou". Neste algoritmo é o -1, guardado na constante `SENTINELA`.
- Leitura antecipada: a leitura do primeiro valor, feita antes do ciclo, para a condição ter um valor para testar.
- Contador: uma variável que conta quantas vezes uma coisa aconteceu, como `turmas`.
- Acumulador: uma variável que vai somando valores, como `totalQuilos`.
- Saídas `Sim` e `Não`: as duas setas que saem de um losango. Segue-se a do `Sim` quando a resposta à condição é verdadeira, e a do `Não` quando é falsa.
- Ramo: cada um dos caminhos que saem de um losango.
- Seta de volta: a seta que sobe da última figura do corpo até ao losango do ciclo, para a condição ser testada outra vez. Para saber mais, vê a secção "A seta que volta ao losango" do [guia](04-repeticao-e-arrays.md).
- Seta ambígua: uma seta de que não se percebe bem de onde vem ou para onde vai. Acontece, por exemplo, com duas setas a entrar no mesmo ponto de uma figura.
- Caso de teste: uma entrada escolhida para testar o algoritmo, com o resultado que o enunciado pede.
- `Para`: um ciclo que repete o corpo um número de vezes que se sabe antes de começar. `Para corredor de 1 até 3` repete-o com `corredor` a valer 1, 2 e 3. Aparece no desafio.
- Browser: o programa que abre as páginas da internet, como o Chrome, o Edge, o Firefox ou o Safari.
- Ficheiro `.drawio`: o desenho que a aplicação volta a abrir para continuares a editar.
- Imagem PNG: uma imagem do desenho, que qualquer computador ou telemóvel abre, mas que não se edita.
- Exportar: criar a imagem PNG a partir do desenho.

## O que precisas

- Um computador com um browser e ligação à internet.
- O diagrams.net, a aplicação de diagramas deste laboratório. Também é conhecida por draw.io, que é o nome antigo, e os ficheiros que cria terminam em `.drawio`. Usa-se no browser, é gratuita e não precisa de conta. Confirma que chegas a ela: abre `https://app.diagrams.net/?lang=pt`. Deve aparecer um diagrama em branco, chamado "Diagrama sem nome", o que quer dizer que a aplicação está pronta a usar.
- A pasta `algoritmos`, onde guardas os ficheiros desta disciplina. Se fizeste o laboratório do tema 02 ou o do tema 03, já a tens. Se não, cria-a antes de começar, numa pasta do computador, numa pen ou no sítio que o professor indicar.
- Papel e caneta, para as fases 1 e 4.

Se fizeste os laboratórios dos temas [02](02-estado-sequencia-representacoes-laboratorio.md) e [03](03-decisoes-e-validacao-laboratorio.md), já conheces a aplicação, e podes passar depressa pelos passos que já sabes. Se não os fizeste, não faz mal, porque cada ação está explicada na primeira vez que aparece.

## Se alguma coisa falhar

1. A aplicação aparece em inglês? Abre-a com o endereço `https://app.diagrams.net/?lang=pt`, com o `?lang=pt` no fim.
2. Vês a barra de menus no topo da aplicação, com Ficheiro, Editar, Visualização, Ordenar, Extras e Ajuda? Se não a vês, a janela do browser está estreita. Maximiza-a, ou usa o botão redondo com reticências, no canto superior direito, que tem as mesmas opções.
3. O teu ficheiro está guardado no computador? O nome que lhe deste aparece no topo da aplicação. Se o "Guardar como" te pedir para entrar numa conta, o campo "Onde:" ficou em Google Drive. Muda-o para "Aparelho" ou "Descarregar".
4. As setas estão presas às figuras? Arrasta uma figura um pouco para o lado. Se as setas a acompanharem, estão presas. Depois carrega em Ctrl+Z, ou Cmd+Z num Mac, para a figura voltar ao sítio.
5. Enganaste-te? Ctrl+Z, ou Cmd+Z num Mac, desfaz a última ação. Podes repetir para desfazer várias.

## Preparar o projeto

A aplicação muda de aspeto de vez em quando. Os passos descrevem cada opção pelo que faz. Se um nome no teu ecrã não for exatamente igual, procura o que faz a mesma coisa, porque os passos são os mesmos.

1. Abre a aplicação em português. Abre o browser, maximiza a janela para ocupar o ecrã todo, e escreve na barra de endereços `https://app.diagrams.net/?lang=pt`. A parte final, `?lang=pt`, pede à aplicação que apareça em português.

   O que deves ver: um diagrama em branco, chamado "Diagrama sem nome". A aplicação não te pergunta nada nem te pede conta.

2. Guarda o ficheiro já, antes de desenhares. Neste momento, o diagrama só existe dentro do browser, e se fechares a página perdes tudo. Guardar logo dá-lhe um nome e um sítio.

   1. Na barra de menus, no topo da aplicação, carrega em "Ficheiro" e, na lista que se abre, em "Guardar como...".
   2. Abre-se a janela "Guardar como". No campo "Guardar como:", apaga o que lá estiver e escreve `fluxograma-campanha-de-alimentos.drawio`.
   3. No campo "Tipo:", deixa ficar "Ficheiro XML (.drawio)". É o formato que a aplicação volta a abrir para continuares a editar.
   4. O campo "Onde:" vem com "Google Drive". Muda-o para "Aparelho", que guarda o ficheiro numa pasta do teu computador. Se "Aparelho" não funcionar no teu computador, escolhe "Descarregar", e o ficheiro vai para a pasta de transferências.
   5. Carrega em "Guardar". Com "Aparelho", abre-se a janela do sistema para escolheres a pasta. Escolhe a pasta `algoritmos` e confirma.

   O que deves ver: o nome `fluxograma-campanha-de-alimentos.drawio` no topo da aplicação, onde antes estava "Diagrama sem nome". Daqui para a frente, para guardar, carrega em Ctrl+S, ou Cmd+S num Mac, no fim de cada fase. Se escolheste "Descarregar", cada vez que guardas vai uma cópia nova para as transferências. No fim, passa a mais recente para a pasta `algoritmos`.

   As outras opções do campo "Onde:" não servem aqui. Google Drive, OneDrive e GitHub pedem uma conta nesses serviços. "Navegador" guarda o ficheiro dentro do próprio browser, e perde-lo se alguém limpar os dados do browser ou se mudares de computador.

3. Encontra as figuras de fluxograma. O painel da esquerda tem as figuras arrumadas em grupos com nome. As que te interessam estão no grupo "Fluxograma", perto do fim da lista. Desce no painel e carrega no nome "Fluxograma" para o abrir. Se o grupo não estiver na lista, carrega no botão "+ Mais formas", no fundo do painel. Na janela "Formas", marca "Fluxograma" e confirma.

   Passa o rato devagar por cima das figuras do grupo. Ao lado de cada uma aparece o nome dela, em inglês, mesmo com a aplicação em português. Neste laboratório usas estas quatro:

   | Figura | Nome que vais ver | O que quer dizer | Para que serve |
   | --- | --- | --- | --- |
   | Retângulo de pontas redondas | Terminator | "terminal": onde o algoritmo começa ou acaba | `Início` e `Fim` |
   | Retângulo | Process | "processamento" | as contas e as instruções que dão um valor a uma variável |
   | Paralelogramo | Data | "dados": é por ali que os dados entram e saem | ler um valor (`ler valor`) e escrever no ecrã (`Escreve:`) |
   | Losango | Decision | "decisão" | uma condição, com duas saídas |

   O grupo tem muitas outras figuras, que pertencem a convenções mais pormenorizadas do que a nossa. Usa sempre estas quatro, do grupo "Fluxograma".

## Fase 1: planear a disposição antes de desenhar

Num fluxograma, cada figura liga-se à seguinte por uma seta, e as setas descem. Num ciclo, há uma seta que sobe. Depois da última linha do corpo, o algoritmo não continua para baixo. Volta à linha do `Enquanto` e testa a condição outra vez. No desenho, essa volta é a seta de volta, que sobe da última figura do corpo até ao losango do ciclo.

Um fluxograma com um ciclo fica confuso quando as figuras são postas à sorte e as setas se arranjam depois. A seta de volta precisa de um caminho livre para subir, e esse caminho tem de ser planeado antes de pores a primeira figura.

1. Copia para o papel este esquema. É a disposição que vais usar, com três faixas lado a lado. Os números são os das figuras da fase 2:

   ```text
     faixa livre        faixa do meio                        faixa da direita
     (a seta de volta   (o caminho principal,                (o ramo Sim do Se; mais à
      sobe por aqui)     de cima para baixo)                  direita ainda, a saída do ciclo)

                        1 Início
                        2 e 3 as inicializações
                        4 e 5 a pergunta e a leitura antecipada
     +--------------->  6 losango do ciclo  ---- Não ------------------------------+
     |                   | Sim                                                     |
     |                  7 e 8 contar e somar                                       |
     |                  9 a pergunta                                               |
     +----------------- 10 a leitura do valor seguinte                             |
                                                                                   |
                        (espaço vazio: aqui não há seta)                           |
                        11 escrever as turmas  <-----------------------------------+
                        12 escrever o total
                        13 losango do Se  ---- Sim ---->  14 calcular a média
                         | Não                            15 escrever a média
                        16 não há média                         |
                        17 Fim  <-------------------------------+
   ```

2. Repara em quatro pormenores do esquema, porque são eles que tornam o desenho claro.

   O losango do ciclo, o 6, tem uma arrumação diferente da habitual. O `Sim` sai por baixo, para o corpo do ciclo, e o `Não` sai pela direita, para fora do ciclo. Há uma razão para isto. O losango de um ciclo tem quatro setas, e não três: a que chega de cima, as duas saídas e a seta de volta. Com o `Sim` por baixo, o corpo do ciclo fica na faixa do meio. E a ponta esquerda do losango fica livre para a seta de volta.

   O losango do `Se`, o 13, segue a arrumação habitual dos fluxogramas destes materiais. O `Não` sai por baixo e o `Sim` sai pela direita, e assim quem lê sabe onde procurar cada saída. Os dois ramos do `Se` juntam-se no Fim, porque não há mais nenhuma instrução depois do `Se`.

   A faixa da esquerda fica vazia de figuras. É por ali que a seta de volta sobe, da figura 10 até à ponta esquerda do losango 6, sem passar por cima de nada. A seta que vem da figura 5 chega ao mesmo losango pela ponta de cima. São duas setas a chegar ao mesmo losango, e cada uma chega por um lado diferente.

   A saída `Não` do ciclo desce por fora de tudo, à direita, até à figura 11. Entre a figura 10 e a figura 11 fica um espaço vazio, sem seta. Quem sai do corpo volta sempre ao losango, e só a saída `Não` chega aos resultados.

### Paragem 1

Tens no papel o esquema das três faixas, com o caminho livre à esquerda para a seta de volta.

Pensa antes de continuares: como distingues, à primeira vista, o losango do ciclo do losango do `Se`? A resposta: ao losango do ciclo chega uma seta pela esquerda, a seta de volta. Ao losango do `Se` não chega nenhuma seta pela esquerda.

## Fase 2: as figuras e as setas que descem

Cada linha do pseudocódigo que faz alguma coisa é uma figura do fluxograma. A linha `const SENTINELA = -1` não tem figura. Dá nome a um valor fixo, e esse nome aparece dentro do losango onde é usado. A palavra `Senão` também não tem figura própria. O ramo dela começa na figura 16, à saída `Não` do losango 13.

O fluxograma da campanha tem 17 figuras. Esta é a lista, pela ordem do pseudocódigo:

| Ordem | Figura | Nome que aparece | Texto a escrever | Onde fica |
| ---: | --- | --- | --- | --- |
| 1 | Retângulo de pontas redondas | Terminator | `Início` | faixa do meio |
| 2 | Retângulo | Process | `int turmas = 0` | faixa do meio |
| 3 | Retângulo | Process | `int totalQuilos = 0` | faixa do meio |
| 4 | Paralelogramo | Data | `Escreve: "Quilos entregues pela turma (-1 para terminar)?"` | faixa do meio |
| 5 | Paralelogramo | Data | `int quilos = ler valor` | faixa do meio |
| 6 | Losango | Decision | `quilos != SENTINELA?` | faixa do meio |
| 7 | Retângulo | Process | `turmas = turmas + 1` | faixa do meio |
| 8 | Retângulo | Process | `totalQuilos = totalQuilos + quilos` | faixa do meio |
| 9 | Paralelogramo | Data | `Escreve: "Quilos entregues pela turma (-1 para terminar)?"` | faixa do meio |
| 10 | Paralelogramo | Data | `quilos = ler valor` | faixa do meio |
| 11 | Paralelogramo | Data | `Escreve: "Turmas que entregaram: ", turmas` | faixa do meio, depois de um espaço vazio |
| 12 | Paralelogramo | Data | `Escreve: "Total: ", totalQuilos, " kg"` | faixa do meio |
| 13 | Losango | Decision | `turmas > 0?` | faixa do meio |
| 14 | Retângulo | Process | `float media = totalQuilos / turmas` | faixa da direita |
| 15 | Paralelogramo | Data | `Escreve: "Média por turma: ", media, " kg"` | faixa da direita |
| 16 | Paralelogramo | Data | `Escreve: "Não houve entregas, por isso não há média."` | faixa do meio |
| 17 | Retângulo de pontas redondas | Terminator | `Fim` | faixa do meio |

O texto de cada figura é o mesmo do pseudocódigo, com o mesmo nome de cada variável e o mesmo `=` para dar um valor. As figuras 2, 3 e 5 levam o tipo à frente, porque é aí que as variáveis nascem. As figuras 7, 8 e 10 não o levam, porque usam variáveis que já existem. Tudo se escreve diretamente no teclado.

1. Põe a primeira figura e escreve-lhe o texto. No grupo "Fluxograma", carrega na figura Terminator e, sem largar o botão do rato, arrasta-a para a página. Larga-a perto do topo, na faixa do meio. Depois faz duplo clique dentro da figura, escreve `Início` e carrega numa zona vazia da página para acabar.

   O que deves ver: o terminal com o texto `Início` lá dentro. Se te enganares no texto, faz outra vez duplo clique e corrige.

2. Põe as figuras 2 a 13, 16 e 17, pela ordem da tabela, em coluna na faixa do meio. Deixa entre elas um espaço de mais ou menos a altura de uma figura. Entre a figura 10, a leitura do valor seguinte, e a figura 11, a primeira escrita dos resultados, deixa um espaço maior, sem nada. É o espaço vazio do esquema.

   Para poupar tempo, desenha uma figura, escreve-lhe o texto, e depois duplica-a e muda só o texto. Para duplicar, seleciona a figura e carrega em Ctrl+D, ou Cmd+D num Mac. As figuras 4 e 9, por exemplo, têm exatamente o mesmo texto. Quando arrastas uma figura, a aplicação mostra linhas de guia coloridas quando ela fica alinhada com outra. Larga a figura quando a linha de guia vertical aparecer, e as figuras ficam centradas umas por baixo das outras.

   O que deves ver: quinze figuras em coluna, do Início ao Fim, com um espaço vazio entre a 10 e a 11.

3. Põe as figuras 14 e 15 na faixa da direita, à direita do losango 13. A 14 fica à mesma altura do losango, e a 15 por baixo dela.

4. Alarga as figuras com texto comprido. Algumas, como os paralelogramos 4, 9 e 16, têm mais texto do que cabe numa figura pequena. Carrega uma vez na figura para a selecionar. Aparecem pequenos pontos nos cantos e a meio dos lados. Puxa um dos cantos para fora até o texto caber, de preferência numa ou duas linhas.

5. Liga as figuras da faixa do meio com setas, de cima para baixo. Passa o rato por cima da figura 1, sem carregar. Aparecem quatro pequenas setas azuis, uma de cada lado da figura. Carrega na seta azul de baixo e, sem largar o botão do rato, arrasta até à figura 2. Larga quando a figura 2 ficar com o contorno azul. É esse contorno que mostra que a seta ficou presa à figura.

   Faz o mesmo da figura 2 para a 3, e assim por diante até à figura 6, o losango do ciclo. Depois liga, também de cima para baixo, a figura 7 à 8, a 8 à 9 e a 9 à 10. Não ligues a figura 10 a nada, e não ligues nada à figura 11. Essas duas setas são as da fase 3.

   O que deves ver: setas presas nas duas pontas, todas a apontar para baixo. Se uma ficar ao contrário, seleciona-a, apaga-a com a tecla Delete ou Backspace, e desenha-a outra vez a partir da figura de cima.

6. Liga o losango do ciclo, a figura 6, à figura 7, pela ponta de baixo. Falta o nome desta saída. Faz duplo clique a meio da seta, escreve `Sim` e carrega numa zona vazia.

   O que deves ver: a seta do losango 6 para a figura 7, com a palavra `Sim` em cima.

7. Liga as figuras 11, 12 e 13, de cima para baixo.

8. Dá nome às saídas do `Se`. Liga a ponta de baixo do losango 13 à figura 16 e escreve `Não` nessa seta. Depois liga a ponta direita do losango 13 à figura 14 e escreve `Sim` nessa seta. Liga a figura 14 à 15.

9. Junta os dois ramos do `Se` no Fim. Liga a figura 16 ao Fim, por cima. Depois liga a figura 15 ao Fim, e faz a seta chegar ao Fim pelo lado direito. Assim, as duas setas não entram no mesmo ponto. Estas setas não levam texto, porque não saem de um losango.

   Guarda o ficheiro, com Ctrl+S ou Cmd+S.

### Paragem 2

Conta as figuras e as setas do teu desenho. Deve ter dezassete figuras e dezasseis setas. Três setas têm texto: o `Sim` do losango 6, e o `Sim` e o `Não` do losango 13. Os dois ramos do `Se` chegam ao Fim, um por cima e outro pela direita.

Pensa antes de continuares: porque é que a figura 10 ainda não tem nenhuma seta a sair, e a figura 11 nenhuma a chegar? A resposta: a seta que sai da figura 10 é a seta de volta, que vai ao losango 6. A única seta que chega à figura 11 é a saída `Não` do ciclo. As duas desenham-se na fase 3, com um cuidado especial.

## Fase 3: a seta que volta ao losango

A seta de volta vai sempre ao losango do ciclo, porque é lá que o ciclo decide se continua. Se fosse à primeira inicialização, a contagem e o total voltavam a zero em cada volta. Se fosse para uma figura do corpo, a condição nunca mais era testada, e o ciclo nunca acabava. Esta fase faz-se devagar. Confirma cada passo antes de passares ao seguinte.

1. Começa na figura certa. A seta de volta sai da última figura do corpo do ciclo, a figura 10, `quilos = ler valor`. Não sai do losango, nem da pergunta que está acima da leitura. Para confirmares, procura no pseudocódigo a última linha com quatro espaços, antes das linhas sem indentação do fim. É dessa figura que a seta sai.

2. Sai pelo lado esquerdo. Passa o rato por cima da figura 10. Aparecem as pequenas setas azuis nos quatro lados. Carrega na seta azul do lado esquerdo e, sem largar o botão do rato, arrasta para cima, até ao losango 6.

3. Larga na ponta esquerda do losango. Nas setas da fase 2, largaste a seta quando a figura de destino ficava com o contorno azul. Isso prende a seta à figura, mas deixa a aplicação escolher o lado por onde a seta entra. Muitas vezes ela escolhe a ponta de cima, onde já chega a seta da figura 5. Ficavas com duas setas a entrar no mesmo ponto, e quem olhasse para o desenho já não via qual delas vem de onde. É isto que quer dizer uma seta ambígua.

   Para a seta de volta, és tu que escolhes o lado. Quando o rato passa por cima do losango, aparecem no seu contorno pequenas marcas. São os pontos onde uma seta se pode prender. Leva o rato até à marca que está na ponta esquerda do losango, e só então larga o botão.

   O que deves ver: a seta presa à ponta esquerda do losango, e não à de cima.

4. Vê o caminho que a seta fez. A aplicação desenha as setas com ângulos retos. A seta deve sair da figura 10 para a esquerda, subir pela faixa livre e virar à direita para entrar na ponta esquerda do losango. Se a seta aparecer como uma linha inclinada, a direito, seleciona-a com um clique. Depois, no painel da direita, no separador "Estilo", procura a opção das linhas com ângulos retos. Na aplicação em português, chama-se "Pontos de passagem", e escolhe-se "Ortogonal".

5. Afasta a seta das figuras. A parte vertical da seta pode passar por cima de alguma figura, ou muito encostada a elas. Nesse caso, carrega na seta e arrasta para a esquerda o ponto que aparece a meio dessa parte vertical. Larga quando a seta subir pela faixa livre. Se a seta ficar com um caminho estranho e não a conseguires endireitar, carrega nela com o botão direito do rato. No menu que aparece, procura a opção que devolve a seta ao caminho automático, "Limpar pontos de passagem", e tenta outra vez.

6. Confirma o sentido. A ponta da seta tem de estar no losango, e não na figura 10. Se estiver ao contrário, é porque arrastaste do losango para a leitura. Seleciona a seta, apaga-a com a tecla Delete e faz de novo, a partir da figura 10.

7. Deixa a seta sem texto. O `Sim` e o `Não` pertencem às saídas do losango. Uma palavra na seta de volta faria parecer que ela é uma saída.

8. Desenha a saída do ciclo. Liga a ponta direita do losango 6 à figura 11. A seta deve sair para a direita e passar além da faixa da direita. Depois desce por fora de tudo e entra na figura 11 pelo lado direito. Se passar por cima das figuras 14 e 15, afasta-a como no passo 5. Escreve `Não` nesta seta.

   Guarda o ficheiro.

### Paragem 3

Olha para o losango 6. Chegam-lhe duas setas, uma por cima e outra pela esquerda, e saem duas, o `Sim` por baixo e o `Não` pela direita. Nenhuma das quatro partilha o mesmo ponto do contorno. O desenho tem agora dezassete figuras e dezoito setas, quatro delas com texto.

Pensa antes de continuares: porque é que a seta de volta não leva o `Sim`, se é por ela que o ciclo continua? A resposta: o `Sim` já está na saída de baixo do losango, por onde se entra no corpo. A seta de volta não sai do losango, chega a ele. É o caminho de regresso ao teste, depois de o corpo acabar.

## Fase 4: verificar o desenho com um caso de teste

Um fluxograma verifica-se percorrendo-o com um caso de teste, como se fosses tu o computador. Em cada losango, a saída escolhe-se pela condição, com os valores que as variáveis têm nesse momento.

1. Segue o caminho com o dedo, desde o Início, para este caso: a funcionária escreve 12, depois 0, depois 9 e depois -1. Acompanha o valor de cada variável sempre que ele muda, e escreve no papel o que aparece no ecrã. Conta quantas vezes passas pelo losango 6 e quantas passas pelo losango 13.

2. Confere o teu percurso com este, passagem a passagem:

   | Passagem | Losango | Condição, com os valores do momento | Saída | O que acontece a seguir |
   | --- | --- | --- | --- | --- |
   | 1.ª | 6, do ciclo | `12 != -1` dá `true` | `Sim` | as turmas passam a 1 e o total a 12; lês 0 |
   | 2.ª | 6, do ciclo | `0 != -1` dá `true` | `Sim` | as turmas passam a 2 e o total fica 12; lês 9 |
   | 3.ª | 6, do ciclo | `9 != -1` dá `true` | `Sim` | as turmas passam a 3 e o total a 21; lês -1 |
   | 4.ª | 6, do ciclo | `-1 != -1` dá `false` | `Não` | escreves "Turmas que entregaram: 3" e "Total: 21 kg" |
   | 1.ª | 13, do `Se` | `3 > 0` dá `true` | `Sim` | a média é 21 / 3, que dá 7; escreves "Média por turma: 7 kg" e chegas ao Fim |

   O que deves ver: quatro passagens pelo losango 6 e uma pelo losango 13. No fim, 3 turmas, 21 quilos e a média de 7. Na 2.ª passagem, o 0 passou pela condição e foi contado como turma, porque o 0 é um dado. Se deres por ti numa figura de onde não sai nenhuma seta, ou a voltar a uma inicialização, há uma seta errada. Corrige-a antes de continuares.

3. Confirma esta lista:

   - há um único Início e um único Fim;
   - todas as figuras têm pelo menos uma seta a entrar e uma a sair, menos o Início e o Fim;
   - o Início só tem uma seta a sair, e o Fim só tem setas a entrar;
   - cada losango tem exatamente duas saídas, uma com `Sim` e outra com `Não`;
   - a seta de volta sai da figura 10 e chega ao losango 6, e não a outra figura;
   - nenhuma seta cruza outra, e nenhuma passa por cima de uma figura;
   - o texto de cada figura é o mesmo do pseudocódigo.

### Paragem 4

O teu desenho passou no caso de teste. Fizeste quatro passagens pelo losango do ciclo e uma pelo losango do `Se`. No fim, tens 3 turmas, 21 quilos e a média de 7.

Pensa antes de continuares: imagina que a seta de volta chegava à figura 2, `int turmas = 0`. Com o mesmo caso, chegavas ao Fim? A resposta: não. No fim de cada volta, a contagem e o total voltavam a 0. Depois, a leitura antecipada da figura 5 lia logo o valor seguinte. O valor lido no fim do corpo era deitado fora sem passar pelo losango. O 12 era testado, o 0 deitado fora, o 9 testado e o -1 deitado fora. O algoritmo ficava à espera de mais um valor, e o dedo nunca chegava ao Fim.

## Fase 5: uma imagem do fluxograma

O ficheiro `.drawio` é o teu fluxograma editável. É esse que abres para continuar a trabalhar ou para corrigir. Para mostrar o fluxograma a alguém, ou para o entregar, exporta-se uma imagem, que qualquer computador ou telemóvel abre sem precisar da aplicação. Uma imagem não se edita. Se precisares de mudar alguma coisa, mudas o `.drawio` e exportas a imagem outra vez. Por isso, guardas sempre os dois ficheiros.

1. Guarda primeiro o `.drawio`, com Ctrl+S ou Cmd+S.

2. Na barra de menus, escolhe "Ficheiro", depois "Exportar como" e depois "PNG...". PNG é um formato de imagem que mantém as letras nítidas.

3. Abre-se a janela "Imagem". Em "Tamanho", escolhe "Diagrama", para a imagem ter só o fluxograma, e não a página inteira. Confirma também que a opção "Fundo Transparente" está desligada. Com o fundo transparente, a imagem pode ficar ilegível quando aberta num fundo escuro.

4. Carrega em "Exportar". Se a aplicação te pedir um nome e um sítio, o nome é `fluxograma-campanha-de-alimentos.png`. O sítio é "Aparelho" ou "Descarregar", na pasta `algoritmos`. Nunca escolhas o Google Drive nem o "Navegador".

5. Vai à pasta onde a imagem ficou e abre-a com duplo clique.

   O que deves ver: o fluxograma inteiro, com todo o texto legível e todas as setas, incluindo a de volta.

### Paragem 5

Na tua pasta `algoritmos` estão `fluxograma-campanha-de-alimentos.drawio` e `fluxograma-campanha-de-alimentos.png`. Se usaste "Descarregar", passa as cópias mais recentes da pasta de transferências para a pasta `algoritmos`.

Pensa antes de terminares: se descobrires um erro no desenho depois de exportar, qual dos dois ficheiros corriges? A resposta: o `.drawio`, porque a imagem não se edita. Depois de o corrigires, exportas a imagem outra vez.

## Problemas frequentes

### A seta de volta entra no losango por cima, no mesmo ponto da seta da leitura antecipada

Largaste a seta quando o losango ficou com o contorno azul, e a aplicação escolheu o lado. Apaga a seta e desenha-a outra vez. Larga-a na marca da ponta esquerda do losango, e não no meio dele.

### A seta de volta atravessa figuras

O caminho automático passou por cima das figuras. Carrega na seta e arrasta para a esquerda o ponto do meio da parte vertical, até ela subir pela faixa livre.

### A seta ficou torta ou com um caminho estranho

Carrega na seta com o botão direito, escolhe "Limpar pontos de passagem" e ajusta outra vez.

### A ponta da seta de volta está na leitura e não no losango

Arrastaste ao contrário, do losango para a leitura. Apaga a seta e desenha-a a partir da leitura, a figura 10.

### Ao seguir o caso de teste, voltas a uma inicialização ou nunca mais passas pelo losango

A seta de volta chega à figura errada. Se chega à figura 2 ou à 3, a contagem ou o total voltam a zero. Se chega à 4 ou à 5, o valor lido no fim do corpo é deitado fora, como na paragem 4. Se chega a uma figura do corpo, a condição nunca mais é testada, e o ciclo nunca acaba. Liga-a à ponta esquerda do losango 6.

### A saída `Não` do ciclo está ligada a uma figura do corpo

A saída `Não` é por onde se sai do ciclo, e por isso vai para a figura 11, a primeira escrita dos resultados. Apaga-a e liga a ponta direita do losango 6 à figura 11.

### Escreveste `Sim` ou `Não` na seta de volta

A seta de volta não sai de um losango, e por isso não leva texto. Faz duplo clique no texto e apaga-o.

### Quando mexes uma figura, a seta não vai atrás dela

A seta não ficou presa à figura. Apaga-a e desenha-a outra vez. Larga o botão do rato só quando a figura de destino ficar com o contorno azul. Na seta de volta, larga-o sobre a marca da ponta esquerda do losango.

### O `Sim` fica no sítio quando mexes a seta

Escreveste o `Sim` numa caixa de texto solta, ao lado da seta, e não na própria seta. Apaga essa caixa e faz duplo clique exatamente em cima da linha da seta.

### O texto não cabe no losango

Carrega uma vez no losango para o selecionar e puxa um dos cantos para fora.

### Não encontras o grupo Fluxograma

Desce até ao fim da lista do painel da esquerda. Se o grupo não estiver lá, carrega em "+ Mais formas", no fundo do painel, marca "Fluxograma" e confirma. Também podes escrever o nome de uma figura, como `Decision`, na caixa de pesquisa, no topo do painel.

### Não aparece a barra de menus no topo

A janela do browser está estreita. Maximiza-a, ou usa o botão redondo com reticências, no canto superior direito. Nesse botão, o "Exportar como" aparece logo ao lado do "Ficheiro", em vez de estar dentro dele.

### O ficheiro foi para o Google Drive, ou o "Guardar como" pede uma conta

O campo "Onde:" ficou no Google Drive, que vem escolhido de início. Volta a guardar com "Guardar como..." e, no campo "Onde:", escolhe "Aparelho" ou "Descarregar". Se guardaste no "Navegador", faz o mesmo.

### Desenhaste uma figura para a constante, ou um Fim em cada ramo

A linha `const` dá nome a um valor fixo e não é um passo do caminho, e por isso não tem figura. Um fluxograma tem um só Início e um só Fim, e os ramos do `Se` juntam-se no mesmo Fim. Apaga as figuras a mais e liga as setas à figura certa.

### Apagaste uma figura sem querer

Ctrl+Z, ou Cmd+Z num Mac, desfaz a última ação. Repete para desfazer mais.

## Desafios

1. Um `Para` no fluxograma. Este algoritmo soma as caixas guardadas nos 3 corredores de um armazém:

   ```text
   const NUMERO_DE_CORREDORES = 3
   int totalCaixas = 0
   Para corredor de 1 até NUMERO_DE_CORREDORES
       Escreve: "Caixas no corredor ", corredor, "?"
       int caixas = ler valor
       totalCaixas = totalCaixas + caixas
   Escreve: "Total de caixas no armazém: ", totalCaixas
   ```

   O `Para corredor de 1 até NUMERO_DE_CORREDORES` repete as três linhas indentadas com `corredor` a valer 1, 2 e 3. Nos fluxogramas destes materiais, o `Para` não tem figura própria. Desenha-se com as figuras que já usaste, como o `Enquanto` que faz o mesmo. Por isso, o desenho tem figuras que não aparecem escritas como linhas no pseudocódigo.

   Cria um ficheiro novo na pasta `algoritmos`. Na barra de menus, escolhe "Ficheiro" e "Novo...". Se a aplicação perguntar que tipo de diagrama queres, escolhe o diagrama em branco. Guarda-o logo, como na preparação, com o nome `fluxograma-inventario-de-corredores.drawio`.

   a) No papel, escreve as duas instruções que o `Para` faz sem aparecerem escritas como linhas, a inicialização e a atualização. Diz onde fica cada uma no fluxograma: antes do losango, ou no fim do corpo, mesmo antes da seta de volta.

   b) Desenha o fluxograma, com essas duas figuras e o losango `corredor <= NUMERO_DE_CORREDORES?`. A seta de volta chega à ponta esquerda do losango, como na fase 3. O `Sim` sai por baixo e o `Não` pela direita.

   c) Segue o desenho com o dedo, com 5, 3 e 4 caixas nos três corredores. Escreve no papel quantas vezes passaste pelo losango e que total apareceu no fim.

   Guarda e exporta a imagem como `fluxograma-inventario-de-corredores.png`, como na fase 5. Se o tempo da aula não chegar para este desafio, termina-o no início da aula seguinte. Pista: escreve primeiro, no papel, um `Enquanto` que faça o mesmo que este `Para`, e desenha o fluxograma desse `Enquanto`.

## Antes de terminares

- [ ] Na tua pasta `algoritmos` estão `fluxograma-campanha-de-alimentos.drawio` e `fluxograma-campanha-de-alimentos.png`.
- [ ] O fluxograma da campanha tem dezassete figuras e dezoito setas, com um só Início e um só Fim.
- [ ] A seta de volta sai da última figura do corpo e chega à ponta esquerda do losango do ciclo.
- [ ] Nenhuma seta cruza outra, e nenhuma passa por cima de uma figura.
- [ ] Ao losango do ciclo chegam duas setas e saem duas, cada uma no seu ponto do contorno.
- [ ] Cada losango tem uma saída `Sim` e uma saída `Não`, e a seta de volta não tem texto.
- [ ] Na tua folha estão o esquema das três faixas e o percurso do caso 12, 0, 9 e -1.
- [ ] Se fizeste o desafio, estão também na pasta `fluxograma-inventario-de-corredores.drawio` e `fluxograma-inventario-de-corredores.png`, e na folha as duas instruções escondidas, as passagens pelo losango e o total.
- [ ] Consegues explicar, por palavras tuas, porque é que a seta de volta vai sempre ao losango do ciclo, e não a outra figura.

As imagens e a folha são o que entregas, se o professor o pedir, pela forma de entrega que ele indicar. Os ficheiros `.drawio` guardas tu, porque podes voltar a precisar deles. Para praticares os ciclos e os arrays sem computador, faz a [ficha de exercícios](04-repeticao-e-arrays-exercicios.md) deste tema.

![Rodapé](../imagens/rodape.png)
