![Cabeçalho](../imagens/cabecalho.png)

# Laboratório: Estado, sequência e representações

Laboratório do tema Estado, sequência e representações, do módulo Desenvolver algoritmos. Cerca de 70 minutos, e mais cerca de 25 se fizeres o primeiro desafio. Vais desenhar no diagrams.net o fluxograma do algoritmo que converte minutos em horas e minutos, e guardá-lo no teu computador. Cada passo diz o que fazer, porquê e o que deves ver. Tudo o que precisas está aqui; o [guia do tema](02-estado-sequencia-representacoes.md) tem a teoria completa, para quem quiser saber mais. A lista "Palavras que vais usar" é para consultar quando precisares, e não para ler de seguida antes de começar.

Este laboratório é todo de fluxogramas, e é opcional. Só o fazes quando o professor o indicar, e nenhum exercício da ficha depende dele.

## O que vais construir

Vais fazer duas coisas. Primeiro, passo a passo, desenhas na aplicação o fluxograma do algoritmo que converte minutos em horas e minutos. Depois, no primeiro desafio, desenhas sozinho o fluxograma de outro algoritmo, o que divide a conta de um jantar.

No fim do passo a passo, tens na tua pasta `algoritmos` dois ficheiros do mesmo fluxograma. Um é o desenho que se pode editar, `fluxograma-converter-minutos.drawio`. O outro é uma imagem, `fluxograma-converter-minutos.png`, que qualquer computador abre.

Pelo caminho, ficas a saber guardar um desenho no teu computador e escolher a figura certa para cada instrução. Ficas também a saber ligar as figuras com setas, confirmar que o desenho diz o mesmo que o pseudocódigo e exportar uma imagem.

| Fase | O que muda | O que funciona no fim |
| --- | --- | --- |
| 1 | O ficheiro `fluxograma-converter-minutos.drawio`, guardado na pasta `algoritmos` | O nome do ficheiro aparece no topo da aplicação |
| 2 | As sete figuras: o Início, as cinco instruções e o Fim | As sete figuras em coluna, com as formas certas |
| 3 | As seis setas | As setas presas às figuras, de cima para baixo |
| 4 | A verificação contra o pseudocódigo | Seguido com o dedo para 60 minutos, o fluxograma mostra "1 h e 0 min" |
| 5 | A imagem `fluxograma-converter-minutos.png` | A imagem mostra o fluxograma inteiro, e o `.drawio` volta a abrir |

## Palavras que vais usar

Consulta esta lista quando um passo usar uma palavra que não conheces.

- Algoritmo: uma sequência finita de passos, cada um claro e possível de executar, que parte de uns dados e chega a um resultado.
- Pseudocódigo: texto escrito com um vocabulário pequeno e sempre igual, que toda a turma lê da mesma maneira, com uma instrução por linha. Para saber mais, vê a secção "Uma forma de escrever algoritmos" do [guia](02-estado-sequencia-representacoes.md).
- Instrução: cada linha do pseudocódigo, que manda fazer uma coisa.
- Variável: um espaço com um nome, onde se guarda um valor que pode mudar, como `horas`. Nasce na primeira linha onde aparece, e só essa linha leva o tipo à frente.
- `int`: o tipo dos números inteiros, sem parte decimal.
- `float`: o tipo dos números com parte decimal, como `12.5`. Só aparece no primeiro desafio.
- Constante: um valor fixo do problema, com o nome em maiúsculas, escrito com `const`, como `const MINUTOS_POR_HORA = 60`.
- Atribuição: a instrução que dá um valor a uma variável, com um só sinal de igual, `=`, que se lê "recebe".
- `ler valor`: a instrução que recebe um valor escrito por quem usa o algoritmo.
- `Escreve:`: a instrução que mostra texto e valores no ecrã.
- `div` e `resto`: a divisão inteira, que diz quantas vezes um número cabe noutro, e o que sobra dela. Com 135 minutos, `135 div 60` dá 2 e `135 resto 60` dá 15.
- Fluxograma: o desenho de um algoritmo, com figuras ligadas por setas. Para saber mais, vê a secção "Fluxogramas" do [guia](02-estado-sequencia-representacoes.md).
- Figura: cada forma do fluxograma. A forma diz que tipo de instrução está lá dentro.
- Oval: a figura onde o algoritmo começa, com `Início`, e acaba, com `Fim`. Na aplicação tem as pontas redondas e chama-se Terminator.
- Paralelogramo: a figura das entradas e das saídas, com `ler valor` ou `Escreve:`. Na aplicação chama-se Data.
- Retângulo: a figura das atribuições e das contas. Na aplicação chama-se Process.
- Losango: a figura de uma decisão, que só se usa a partir do tema 03. Na aplicação chama-se Decision.
- Seta: a ligação de uma figura à seguinte, que diz a ordem do percurso.
- Trace: seguir um algoritmo à mão, instrução a instrução, a anotar o valor das variáveis e o que aparece no ecrã. Para saber mais, vê a secção "Tabela de trace" do [guia](02-estado-sequencia-representacoes.md).
- Browser: o programa que abre as páginas da internet, como o Chrome, o Edge, o Firefox ou o Safari.
- Separador: cada página aberta no browser, com o seu título no topo da janela.
- Ficheiro `.drawio`: o desenho que a aplicação volta a abrir para continuares a editar.
- Imagem PNG: uma imagem do desenho, que qualquer computador ou telemóvel abre, mas que não se edita.
- Exportar: criar a imagem PNG a partir do desenho.

## O que precisas

- Um computador com um browser, como o Chrome, o Edge, o Firefox ou o Safari, e ligação à internet.
- O diagrams.net, a aplicação de diagramas deste laboratório. Também é conhecida por draw.io, que é o nome antigo, e os ficheiros que cria terminam em `.drawio`. Usa-se no browser, é gratuita e não precisa de conta. Confirma que chegas a ela: abre `https://app.diagrams.net/?lang=pt`. Deve aparecer um diagrama em branco, chamado "Diagrama sem nome", o que quer dizer que a aplicação está pronta a usar. Se o professor indicar outra aplicação de diagramas, os passos são parecidos: muda o sítio dos menus, mas não o que tens de fazer.
- Uma pasta chamada `algoritmos`, onde vais guardar os ficheiros desta disciplina. Cria-a antes de começar, numa pasta do computador, numa pen ou no sítio que o professor indicar. No Windows, carrega com o botão direito do rato num sítio vazio da pasta onde a queres, e escolhe "Novo" e depois "Pasta". Depois escreve o nome. No Mac, no Finder, carrega com o botão direito num sítio vazio, escolhe "Nova pasta" e escreve o nome. Todos os ficheiros deste laboratório têm nomes em minúsculas, com hífenes entre as palavras e sem acentos nem espaços, como `fluxograma-converter-minutos.drawio`. Um nome assim funciona em qualquer computador e diz o que o ficheiro contém sem ser preciso abri-lo.
- Papel e lápis, para o primeiro desafio. O algoritmo do passo a passo está na fase 2, e não precisas de mais nada à mão.

## Se alguma coisa falhar

1. Vês a barra de menus no topo da aplicação, com Ficheiro, Editar, Visualização, Ordenar, Extras e Ajuda? Se não a vês, a janela do browser está estreita. Maximiza-a, ou usa o botão redondo com reticências, no canto superior direito, que tem as mesmas opções.
2. O teu ficheiro está guardado no computador? O nome que lhe deste aparece no topo da aplicação. Se o "Guardar como" te pedir para entrar numa conta, o campo "Onde:" ficou em Google Drive. Muda-o para "Aparelho" ou "Descarregar".
3. As setas estão presas às figuras? Arrasta uma figura um pouco para o lado. Se as setas a acompanharem, estão presas. Depois carrega em Ctrl+Z, ou Cmd+Z num Mac, para a figura voltar ao sítio.
4. Enganaste-te? Ctrl+Z, ou Cmd+Z num Mac, desfaz a última ação. Podes repetir para desfazer várias.

## Preparar o projeto

Esta preparação leva cerca de 5 minutos. A aplicação muda de aspeto de vez em quando. Os nomes dos menus e dos botões deste laboratório foram confirmados em setembro de 2026, com a aplicação em português. Se um nome no teu ecrã não for exatamente igual, procura o que faz a mesma coisa, porque os passos são os mesmos.

1. Abre a aplicação em português. Abre o browser, maximiza a janela para ocupar o ecrã todo, e escreve na barra de endereços `https://app.diagrams.net/?lang=pt`. A parte final, `?lang=pt`, pede à aplicação que apareça em português. Sem ela, a aplicação usa a língua do browser, que pode ser o inglês.

   O que deves ver: um diagrama em branco, chamado "Diagrama sem nome". A aplicação não te pergunta nada nem te pede conta.

2. Repara nas quatro zonas do ecrã, porque vais usá-las todas:

   | Zona | Onde está | Para que serve |
   | --- | --- | --- |
   | Painel das figuras | à esquerda | tem as figuras, arrumadas em grupos, e no topo uma caixa de pesquisa onde se lê "Escreva / para pesquisar" |
   | Página | ao centro, a zona branca com uma grelha de quadrados | é onde desenhas; a grelha só serve para ajudar a alinhar |
   | Painel de formatação | à direita, com os separadores "Diagrama" e "Estilo" | muda o aspeto do que estiver selecionado; neste laboratório quase não precisas dele |
   | Barra de menus | no topo, com Ficheiro, Editar, Visualização, Ordenar, Extras e Ajuda | o menu "Ficheiro" tem tudo o que é guardar, abrir e exportar |

   Neste laboratório só vais usar o menu "Ficheiro", da barra de menus. Os passos dizem sempre o caminho completo, por exemplo "Ficheiro" e depois "Guardar como...". Carregas em "Ficheiro", abre-se uma lista, e escolhes a opção nessa lista.

3. Confirma que a janela continua maximizada, porque a aplicação muda de aspeto conforme a largura da janela. Se a janela do browser estiver estreita, por exemplo a ocupar só metade do ecrã, a barra de menus desaparece. Em vez dela, aparece um botão redondo com reticências (três pontos), no canto superior direito. Esse botão abre um menu com "Ficheiro" e "Exportar como" lado a lado.

   A forma mais simples de seguir este laboratório é maximizar a janela. Se não puderes, usa esse botão sempre que os passos falarem da barra de menus. Nesse caso, procura "Exportar como" diretamente no menu, e não dentro de "Ficheiro".

## Fase 1: o ficheiro guardado no teu computador (8 minutos)

Neste momento, o diagrama só existe dentro do separador do browser. Se fechares o separador, perdes tudo. É por isso que se guarda antes de desenhar. Guardar logo no início dá um nome e um sítio ao ficheiro. A partir daí, cada vez que guardares, o trabalho vai para o mesmo ficheiro.

1. Abre a janela de guardar. Na barra de menus, carrega em "Ficheiro" e, na lista que se abre, escolhe "Guardar como...".

   O que deves ver: a janela "Guardar como", com três campos.

2. Dá o nome ao ficheiro. No campo "Guardar como:", apaga o que lá estiver e escreve `fluxograma-converter-minutos.drawio`. Mantém o `.drawio` no fim.

3. Confirma o tipo. No campo "Tipo:" deixa ficar "Ficheiro XML (.drawio)". É o formato próprio da aplicação, o único que ela consegue voltar a abrir para continuares a editar.

4. Escolhe onde guardar. O campo "Onde:" é o mais importante, e vem com "Google Drive" escolhido. Tens de o mudar. Escolhe "Aparelho", que guarda o ficheiro numa pasta do teu computador. Se "Aparelho" não funcionar no teu browser, escolhe "Descarregar", que põe o ficheiro na pasta de transferências.

   As outras opções do campo "Onde:" não servem aqui. Google Drive, OneDrive, Microsoft 365 e GitHub pedem uma conta nesses serviços. "Navegador" guarda o ficheiro dentro do próprio browser.

5. Carrega em "Guardar". Com "Aparelho", abre-se a janela habitual do sistema para escolheres a pasta. Escolhe a pasta `algoritmos` que criaste e confirma. Com "Descarregar", o ficheiro vai para a pasta de transferências do browser. Nesse caso, no fim do laboratório, passas a cópia mais recente para a pasta `algoritmos`.

   O que deves ver: o nome que escreveste no topo da aplicação, onde antes estava "Diagrama sem nome". Isto quer dizer que o desenho já tem um ficheiro no teu computador. Se aparecer outra coisa, vê os [problemas frequentes](#problemas-frequentes).

Daqui para a frente, para guardar basta carregar em Ctrl+S, ou Cmd+S num Mac. Também podes escolher "Ficheiro" e depois "Guardar", na barra de menus. Guarda muitas vezes, pelo menos no fim de cada fase. Se escolheste "Descarregar", cada vez que guardas é descarregada uma cópia nova, e o browser pode acrescentar um número ao nome. No fim, fica com a mais recente.

### Paragem 1

O ficheiro `fluxograma-converter-minutos.drawio` está na tua pasta `algoritmos`, ou na pasta de transferências, e o nome dele aparece no topo da aplicação.

Pensa antes de continuares: porque é que não serve guardar no "Navegador", se o ficheiro também fica guardado? A resposta: o "Navegador" guarda o ficheiro dentro do próprio browser. Basta alguém limpar os dados do browser, ou mudares de computador, para o perderes. Numa pasta tua, o ficheiro fica contigo.

## Fase 2: uma figura para cada instrução (25 minutos)

Um fluxograma é o desenho de um algoritmo. Cada instrução do pseudocódigo passa a ser uma figura, e a forma da figura diz que tipo de instrução é. As leituras, com `ler valor`, e as saídas, com `Escreve:`, comunicam com quem usa o algoritmo, e vão em paralelogramos. As atribuições e as contas vão em retângulos. O algoritmo começa e acaba num oval, com as palavras `Início` e `Fim`. Para saber mais, lê a secção "Fluxogramas" do [guia](02-estado-sequencia-representacoes.md).

O algoritmo que vais desenhar é o que converte minutos em horas e minutos. Um treinador regista o tempo de treino de cada atleta em minutos, e os atletas preferem vê-lo em horas e minutos. Por exemplo, 135 minutos são 2 horas e 15 minutos:

```text
const MINUTOS_POR_HORA = 60
Escreve: "Quantos minutos?"
int totalMinutos = ler valor
int horas = totalMinutos div MINUTOS_POR_HORA
int minutos = totalMinutos resto MINUTOS_POR_HORA
Escreve: horas, " h e ", minutos, " min"
```

Leitura guiada: lê-se de cima para baixo, uma linha de cada vez. A primeira linha dá nome a uma regra do problema, a constante `MINUTOS_POR_HORA`, que vale 60. A segunda mostra a pergunta no ecrã. A terceira guarda em `totalMinutos` o número que a pessoa escrever. É a linha onde essa variável nasce, e por isso leva o tipo `int` à frente. As duas linhas seguintes fazem as contas. `div` diz quantas vezes o 60 cabe inteiro nos minutos, e isso são as horas completas. `resto` diz quantos minutos sobram. A última linha mostra o resultado, com o texto entre aspas tal e qual e o valor das variáveis no lugar dos nomes. Com 135 minutos, o ecrã mostra "2 h e 15 min".

O fluxograma tem 7 figuras: uma por cada uma das cinco instruções, mais o início e o fim. A linha da constante não tem figura. O fluxograma desenha o caminho que a execução percorre, passo a passo, e a constante não é um passo desse caminho. É uma regra do problema, que vale 60 em todas as figuras, do início ao fim.

1. Encontra as figuras de fluxograma. O painel da esquerda tem as figuras arrumadas em grupos com nome: Rascunho, Geral, Diversos, Avançado, Básico, Setas, Fluxograma e outros. As que te interessam estão no grupo "Fluxograma", perto do fim da lista. Desce no painel com a roda do rato, ou com o dedo no trackpad, a superfície do portátil que faz de rato. Depois carrega no nome "Fluxograma" para abrir o grupo.

   O que deves ver: as figuras do grupo "Fluxograma". Se o grupo não aparecer na lista, carrega no botão "+ Mais formas", no fundo do painel da esquerda. Abre-se a janela "Formas". Confirma que "Fluxograma" está marcado e fecha a janela com o botão de confirmar. O grupo passa a aparecer no painel.

2. Conhece os nomes das figuras. Passa o rato por cima das figuras do grupo, devagar. Ao lado de cada uma aparece uma pré-visualização com o nome da figura. Os nomes aparecem em inglês, mesmo com a aplicação em português, e por isso convém saberes o que cada um quer dizer:

   | Figura | Nome que aparece | O que quer dizer | Para que a usas |
   | --- | --- | --- | --- |
   | Retângulo de pontas redondas | Terminator | terminal, o sítio onde o algoritmo começa ou acaba | `Início` e `Fim`; é o oval |
   | Paralelogramo | Data | dados, que entram ou saem do algoritmo | as leituras, com `ler valor`, e as saídas, com `Escreve:` |
   | Retângulo | Process | processo, ou seja, processamento | atribuições e contas |
   | Losango | Decision | decisão | só a partir do tema 03 |

   O grupo "Fluxograma" tem muitas outras figuras, com nomes como Display, Document ou Manual Input. Pertencem a convenções de fluxograma mais pormenorizadas do que a desta disciplina, e não as vais usar. Usa sempre as quatro da tabela, e sempre do grupo "Fluxograma", mesmo que encontres figuras parecidas noutros grupos, como o "Geral".

3. Põe a primeira figura na página. No grupo "Fluxograma", carrega na figura Terminator e, sem largar o botão do rato, arrasta-a para a página. Larga-a perto do topo, ao centro.

   O que deves ver: a figura selecionada, com um contorno azul e uns quadradinhos nos cantos. Se carregares numa zona vazia da página, deixa de estar selecionada. Se carregares nela, volta a ficar.

4. Escreve o texto dentro da figura. Faz duplo clique dentro da figura, e aparece um cursor a piscar. Se a figura já tiver algum texto, apaga-o. Escreve `Início`. Para acabar de escrever, carrega numa zona vazia da página.

   O que deves ver: a palavra Início dentro da figura. Se te enganares, faz outra vez duplo clique e corrige. Se fizeres uma asneira maior, como apagar a figura sem querer, carrega em Ctrl+Z, ou Cmd+Z num Mac, que desfaz a última ação. Podes carregar várias vezes para desfazer várias ações.

5. Põe as outras seis figuras, de cima para baixo, repetindo o arrastar e o duplo clique. Usa a figura e o texto desta tabela. O texto de cada figura é a instrução do pseudocódigo, tal como está escrita:

   | Ordem | Figura | Nome que aparece | Texto a escrever |
   | --- | --- | --- | --- |
   | 1 | Retângulo de pontas redondas | Terminator | `Início` |
   | 2 | Paralelogramo | Data | `Escreve: "Quantos minutos?"` |
   | 3 | Paralelogramo | Data | `int totalMinutos = ler valor` |
   | 4 | Retângulo | Process | `int horas = totalMinutos div MINUTOS_POR_HORA` |
   | 5 | Retângulo | Process | `int minutos = totalMinutos resto MINUTOS_POR_HORA` |
   | 6 | Paralelogramo | Data | `Escreve: horas, " h e ", minutos, " min"` |
   | 7 | Retângulo de pontas redondas | Terminator | `Fim` |

   Três conselhos poupam-te tempo:

   - Deixa espaço entre as figuras, mais ou menos a altura de uma figura, para caberem as setas.
   - Mantém as figuras em coluna. Quando arrastas uma figura, a aplicação mostra linhas de guia coloridas quando ela fica alinhada com outra. Larga a figura quando a linha de guia vertical aparecer, e ficam todas centradas umas por baixo das outras.
   - Para repetir uma figura já feita, copia-a. Seleciona um paralelogramo, carrega em Ctrl+C e depois em Ctrl+V (Cmd+C e Cmd+V num Mac). Aparece uma cópia ao lado, que arrastas para o sítio certo, e só tens de mudar o texto.

   Se o texto não couber na figura, seleciona-a e arrasta um dos quadradinhos azuis dos cantos para a alargar. As instruções das figuras 4, 5 e 6 são compridas. Vale a pena alargar essas três figuras, para cada instrução caber numa só linha.

   Todo o texto das figuras se escreve com as teclas normais do teclado. Repara no sinal das figuras 3, 4 e 5. É um só sinal de igual, `=`, porque são atribuições, em que a variável recebe um valor. Não escrevas `==`. Dois sinais seguidos fazem uma pergunta, "é igual a?", e não guardam nada.

6. Guarda (Ctrl+S ou Cmd+S).

### Paragem 2

Tens sete figuras numa coluna, o Início, as cinco instruções e o Fim, cada uma com o seu texto. São dois ovais, três paralelogramos e dois retângulos, pela ordem da tabela.

Pensa antes de continuares: a linha `int totalMinutos = ler valor` tem um `=`, como as atribuições. Porque é que vai num paralelogramo, e não num retângulo? A resposta: o que decide a figura é o que a linha faz. Esta linha recebe um valor de fora, escrito pela pessoa, e por isso é uma entrada. As entradas desenham-se no paralelogramo.

## Fase 3: as setas dão a ordem (10 minutos)

As figuras sozinhas não dizem por que ordem se executam. É a seta que diz para onde se vai a seguir, de uma figura para a próxima. Este algoritmo é uma sequência: as instruções executam-se uma depois da outra, de cima para baixo, cada uma uma vez. Por isso, o percurso é uma linha reta, e sete figuras em coluna precisam de seis setas, uma entre cada par de figuras seguidas. Para saber mais, lê a secção "Fluxogramas" do [guia](02-estado-sequencia-representacoes.md).

1. Liga a primeira figura à segunda. Passa o rato por cima da figura 1, a do Início, sem carregar. Aparecem quatro pequenas setas azuis, uma de cada lado da figura. Carrega na seta azul de baixo e, sem largar o botão do rato, arrasta até à figura 2. Quando a figura 2 ficar com um contorno azul, larga o botão.

   O que deves ver: uma seta desenhada da figura 1 para a figura 2, com a ponta virada para a figura 2. A ponta de cada seta tem de apontar para a figura seguinte, que é o sentido em que o algoritmo é executado.

2. Liga as outras figuras da mesma maneira: da figura 2 para a 3, da 3 para a 4, e assim até à 7. Se uma seta ficar ao contrário, seleciona-a e apaga-a com a tecla Delete ou Backspace. Depois desenha-a outra vez a partir da figura certa.

3. Confirma que as seis setas estão presas às duas figuras. Uma seta só está bem feita se estiver presa às duas pontas. Arrasta uma figura do meio um pouco para o lado.

   O que deves ver: as setas que chegam e que saem dela a acompanhá-la, esticando-se. Isto quer dizer que estão presas. Se uma ponta ficar parada no sítio antigo, essa seta está solta. Apaga-a e desenha-a outra vez, largando só quando a figura de destino ficar com o contorno azul. Depois, carrega em Ctrl+Z, ou Cmd+Z num Mac, para a figura voltar ao sítio.

   Num algoritmo sequencial, as setas não levam texto. As setas com texto, com `Sim` e `Não`, aparecem no tema 03, quando houver decisões.

4. Guarda (Ctrl+S ou Cmd+S).

### Paragem 3

O fluxograma está completo, e tem de ficar assim, com o mesmo texto em cada figura. No desenho em caracteres, os parênteses curvos são os ovais, as barras inclinadas são os paralelogramos e os parênteses retos são os retângulos:

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

Pensa antes de continuares: quantas setas teria o fluxograma de um algoritmo sequencial com 10 figuras, contando o início e o fim? A resposta: 9. Num algoritmo sequencial, as figuras estão numa linha só, e há uma seta entre cada par de figuras seguidas. Do Fim não sai nenhuma seta, porque é onde o percurso acaba.

## Fase 4: o fluxograma diz o mesmo que o pseudocódigo (8 minutos)

O fluxograma e o pseudocódigo do mesmo algoritmo têm de dizer exatamente a mesma coisa. Se não disserem, um dos dois está errado. Antes de dares o desenho por acabado, compara-o com o pseudocódigo da fase 2, instrução a instrução. Depois segue-o com o dedo, com um número de minutos concreto, e anota o que aparece no ecrã. Seguir um algoritmo assim, à mão, chama-se fazer o trace. Para saber mais, lê a secção "Tabela de trace" do [guia](02-estado-sequencia-representacoes.md).

1. Verifica o desenho, com o pseudocódigo da fase 2 ao lado:

   - [ ] Tem 7 figuras e 6 setas.
   - [ ] Tem um único Início, no topo, e um único Fim, em baixo, os dois em ovais.
   - [ ] O `Escreve:` com a pergunta, a leitura e o `Escreve:` do fim estão em paralelogramos, e as duas contas estão em retângulos.
   - [ ] O texto de cada figura diz o mesmo que a instrução do pseudocódigo. Tem o tipo à frente das variáveis que nascem, o `=`, o `div` e o `resto`.
   - [ ] Dentro das aspas, tem os mesmos espaços, porque são eles que decidem o que aparece no ecrã.
   - [ ] As figuras estão pela mesma ordem que as instruções do pseudocódigo.
   - [ ] Todas as setas estão presas nas duas pontas e apontam para baixo.

   Se uma das verificações falhar, corrige o desenho antes de continuares.

2. Segue o fluxograma com o dedo, no ecrã, como se a pessoa tivesse escrito 60 minutos. Em cada paralelogramo com `Escreve:`, diz em voz baixa o que aparece no ecrã. Em cada retângulo, faz a conta.

   O que deves ver, por esta ordem: a pergunta "Quantos minutos?" e depois "1 h e 0 min". No primeiro retângulo, `60 div 60` dá 1, porque o 60 cabe uma vez em 60. No segundo, `60 resto 60` dá 0, porque não sobra nada. Se não chegares a este ecrã, há uma figura fora do sítio ou com o texto errado.

### Paragem 4

O fluxograma passou as verificações. Seguido com o dedo para 60 minutos, dá o mesmo ecrã que o pseudocódigo, "1 h e 0 min".

Pensa antes de continuares: seguido com o dedo para 59 minutos, o que aparece no fim do ecrã? A resposta: "0 h e 59 min". O 60 não cabe nenhuma vez em 59, e por isso `59 div 60` dá 0. Como não se tirou nenhuma hora, sobram os 59 minutos inteiros, e `59 resto 60` dá 59. O percurso é o mesmo que com 60, porque num algoritmo sequencial todas as figuras se percorrem sempre. Só mudam os valores.

## Fase 5: a imagem para mostrar, o ficheiro para editar (7 minutos)

O ficheiro `.drawio` é o teu fluxograma editável, o que abres para continuar a trabalhar ou para corrigir. Para mostrar o fluxograma a alguém, ou para o entregar, exporta-se uma imagem. Qualquer computador ou telemóvel a abre, sem precisar da aplicação. Uma imagem não se edita. Se precisares de mudar alguma coisa, mudas o `.drawio` e exportas a imagem outra vez. Por isso guardas sempre os dois ficheiros.

1. Guarda primeiro o `.drawio` (Ctrl+S ou Cmd+S).

2. Na barra de menus, escolhe "Ficheiro", depois "Exportar como" e depois "PNG...". PNG é um formato de imagem que mantém as letras nítidas.

   O que deves ver: uma janela chamada "Imagem", com as opções da imagem.

3. Escolhe as opções da imagem. Em "Tamanho", escolhe "Diagrama", para a imagem ter só o fluxograma, e não a página inteira com espaço vazio à volta. Confirma que "Fundo Transparente" está desligado. Com o fundo transparente, a imagem pode ficar ilegível quando aberta num fundo escuro. Deixa as outras opções, como "Zoom" e "Incluir uma cópia do meu diagrama", como estão. Carrega em "Exportar".

4. Se a aplicação te pedir um nome e um sítio, faz como na fase 1. O nome é `fluxograma-converter-minutos.png`. O sítio é "Aparelho" ou "Descarregar", e nunca Google Drive nem "Navegador".

5. Vai à pasta onde a imagem ficou e abre-a com duplo clique.

   O que deves ver: o fluxograma inteiro, com as sete figuras e o texto legível. Se a imagem tiver muito espaço vazio à volta, vê os [problemas frequentes](#problemas-frequentes).

6. Confirma que o `.drawio` ficou mesmo guardado. Fecha o separador da aplicação e abre outra vez `https://app.diagrams.net/?lang=pt`. Na barra de menus, escolhe "Ficheiro", depois "Abrir de" e o sítio onde o guardaste. Escolhe o ficheiro.

   O que deves ver: o fluxograma como o deixaste, o que quer dizer que está guardado. Se a aplicação te perguntar se queres guardar as alterações a um diagrama sem nome, podes responder que não. O teu trabalho está no ficheiro que acabaste de abrir.

### Paragem 5

Na tua pasta `algoritmos` estão `fluxograma-converter-minutos.drawio` e `fluxograma-converter-minutos.png`. A imagem mostra o fluxograma inteiro, e o `.drawio` volta a abrir na aplicação.

Pensa antes de continuares: dos dois ficheiros, qual entregas ao professor, e qual guardas tu? A resposta: entregas a imagem, pela forma de entrega que o professor indicar, porque qualquer computador a abre. Guardas o `.drawio`, porque é o único que podes voltar a editar, se precisares de corrigir o desenho.

## Problemas frequentes

### A aplicação aparece em inglês

Abriste-a sem o `?lang=pt` no fim do endereço, e ela usou a língua do browser. Abre-a com `https://app.diagrams.net/?lang=pt`.

### Não vês a barra de menus, só um botão redondo com reticências no canto superior direito

A janela do browser está estreita, e a aplicação esconde a barra. Maximiza a janela, ou usa esse botão, onde estão "Ficheiro" e "Exportar como".

### O "Guardar como" pede para entrar numa conta

O campo "Onde:" ficou em Google Drive, que vem escolhido, ou noutro serviço. Muda-o para "Aparelho" ou "Descarregar".

### Guardaste no "Navegador"

O ficheiro ficou dentro do browser, e perde-se se alguém limpar os dados do browser ou se mudares de computador. Faz outra vez "Guardar como" e escolhe "Aparelho" ou "Descarregar".

### Não sabes onde ficou o ficheiro

Com "Descarregar", o ficheiro está na pasta de transferências do computador. Passa-o para a pasta `algoritmos`.

### Não encontras o grupo "Fluxograma"

Desce até ao fim do painel da esquerda. Se não estiver lá, carrega no botão "+ Mais formas", marca "Fluxograma" e confirma.

### O texto não cabe na figura

Seleciona a figura e alarga-a pelos quadradinhos azuis dos cantos.

### A seta não fica presa à figura

Largaste o botão do rato antes de a figura de destino ficar com o contorno azul. Apaga a seta e desenha-a outra vez, largando só quando o contorno azul aparecer.

### Uma leitura ficou num retângulo

Escolheste a figura Process em vez de Data, por a linha ter um `=`. Uma leitura recebe um valor de fora, e por isso é uma entrada, que vai num paralelogramo. Apaga a figura, põe uma Data no lugar e escreve outra vez o texto.

### Desenhaste uma figura para a constante

A linha `const MINUTOS_POR_HORA = 60` não é um passo do caminho, é uma regra do problema, e não tem figura. Apaga essa figura e liga as setas à figura seguinte.

### Escreveste `==` numa figura

O texto da figura ficou a fazer uma pergunta, "é igual a?", em vez de dar um valor. Nas atribuições, a variável recebe um valor, e o sinal é um só, `=`. Faz duplo clique na figura e corrige.

### A imagem tem muito espaço vazio à volta do fluxograma

Na janela "Imagem", o "Tamanho" não ficou em "Diagrama". Exporta outra vez, com "Tamanho" em "Diagrama".

### Apagaste ou estragaste alguma coisa

Ctrl+Z, ou Cmd+Z num Mac, desfaz a última ação. Repete para desfazer mais.

### A grelha de quadrados aparece na página

É só uma ajuda para alinhar, e normalmente não aparece na imagem exportada.

## Desafios

1. A conta do jantar. Um grupo de amigos jantou fora e quer dividir a conta em partes iguais. Este algoritmo lê quanto custou o jantar e quantas pessoas eram, e mostra quanto paga cada uma. A conta usa `/`, a divisão com parte decimal: `7 / 2` dá `3.5`.

   ```text
   Escreve: "Quanto custou o jantar, em euros?"
   float conta = ler valor
   Escreve: "Quantas pessoas eram?"
   int pessoas = ler valor
   float porPessoa = conta / pessoas
   Escreve: "Cada pessoa paga ", porPessoa, " euros"
   ```

   a) Antes de desenhar, conta em papel quantas figuras e quantas setas o fluxograma vai ter, e decide a forma de cada figura. Escreve essa lista, para a comparares com o desenho no fim.

   b) Cria um diagrama novo. Na barra de menus, escolhe "Ficheiro" e depois "Novo...". A aplicação pode abrir o diagrama novo noutro separador do browser. Se te perguntar que tipo de diagrama queres, escolhe o diagrama em branco. Guarda-o logo, como na fase 1, com o nome `fluxograma-conta-do-jantar.drawio`.

   c) Desenha o fluxograma, com as figuras certas, o texto de cada instrução como no pseudocódigo e as setas presas nas duas pontas. Depois verifica-o com a lista da fase 4, adaptada a este algoritmo.

   d) Segue o fluxograma com o dedo para dois jantares, e escreve, para cada um, a linha que aparece no ecrã. No primeiro, a conta foi de 48 euros e eram 4 pessoas. No segundo, a conta foi de 50 euros e eram 4 pessoas. Explica numa frase porque é que a conta usa `/` e não `div`.

   e) Guarda o `.drawio` e exporta a imagem, com o nome `fluxograma-conta-do-jantar.png`.

2. Verifica o fluxograma de um colega. Troca de computador com um colega que tenha feito o desafio 1, e verifica o fluxograma dele com a lista da fase 4. Diz-lhe se encontraste uma figura a mais, uma a menos ou uma forma errada. Diz-lhe também se há um texto que diz outra coisa que não o pseudocódigo, ou uma seta solta.

## Antes de terminares

- [ ] Na tua pasta `algoritmos` estão `fluxograma-converter-minutos.drawio` e `fluxograma-converter-minutos.png`.
- [ ] O fluxograma tem 7 figuras e 6 setas, com um só Início e um só Fim.
- [ ] Seguido com o dedo para 60 minutos, o fluxograma dá "1 h e 0 min".
- [ ] Se fizeste o desafio 1, o fluxograma do jantar tem uma figura por instrução, mais o Início e o Fim, com as formas certas. Escreveste a linha do ecrã dos dois jantares.
- [ ] Se fizeste o desafio 1, estão também na pasta `fluxograma-conta-do-jantar.drawio` e `fluxograma-conta-do-jantar.png`.
- [ ] Consegues explicar, por palavras tuas, porque é que cada instrução do pseudocódigo tem uma figura, e a linha `const` não tem.

As imagens são o que entregas, pela forma de entrega que o professor indicar. Os ficheiros `.drawio` guardas tu, porque podes voltar a precisar deles. O laboratório do tema 03, também opcional, acrescenta a figura que ainda falta, o losango das decisões.

![Rodapé](../imagens/rodape.png)
