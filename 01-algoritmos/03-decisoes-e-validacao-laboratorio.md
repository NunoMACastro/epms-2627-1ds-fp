![Cabeçalho](../imagens/cabecalho.png)

# Laboratório: Decisões e validação

Laboratório do tema Decisões e validação, do módulo Desenvolver algoritmos. Vais desenhar no diagrams.net o fluxograma de um algoritmo que decide, o que valida e classifica a nota de um teste. Depois segues nele, com o dedo, o caminho de cada caso. Cada passo diz o que fazer, porquê e o que deves ver, e avanças ao teu ritmo. O que não acabares na aula, acabas na aula seguinte, ou em casa se tiveres computador. Tudo o que precisas está aqui; o [guia do tema](03-decisoes-e-validacao.md) tem a teoria completa, para quem quiser saber mais.

Este laboratório é todo de fluxogramas, e é opcional. Só o fazes quando o professor o indicar, e nenhum exercício da ficha depende dele.

## O que vais construir

Vais fazer três coisas. Primeiro, num desenho de ensaio, pões na página um losango com uma condição e ligas as suas duas saídas, `Sim` e `Não`. Depois desenhas o fluxograma do algoritmo que valida e classifica a nota de um teste, com dois losangos em cadeia. Por fim, segues nele com o dedo o caminho de nove notas, e confirmas que cada uma chega à mensagem certa.

No fim do passo a passo, tens na tua pasta `algoritmos` dois ficheiros do fluxograma da nota. Um é o desenho que se pode editar, `fluxograma-classificar-nota.drawio`. O outro é uma imagem, `fluxograma-classificar-nota.png`, que qualquer computador abre. Na tua folha fica a tabela dos caminhos que seguiste com o dedo.

Pelo caminho, ficas a saber pôr num fluxograma um losango com uma condição e ligar as suas duas saídas. Ficas também a saber levar os ramos de uma decisão a juntarem-se de novo antes de o algoritmo continuar. E ficas a saber confirmar, caso a caso, que cada entrada tem um caminho, e um só.

| Fase | O que muda | O que funciona no fim |
| --- | --- | --- |
| 1 | Um losango com as saídas `Sim` e `Não`, num desenho de ensaio | Seguido com o dedo com 8 e com 20 graus, os dois caminhos chegam à mesma figura |
| 2 | O fluxograma da nota, com dois losangos em cadeia | Nove figuras e dez setas, e os três caminhos chegam ao mesmo Fim |
| 3 | A tabela das nove notas, seguidas com o dedo, e a imagem | Cada nota chega à mensagem certa por um só caminho, e os dois ficheiros estão guardados |

## Palavras que vais usar

- Algoritmo: uma sequência finita de passos, cada um claro e possível de executar, que parte de uns dados e chega a um resultado.
- Pseudocódigo: a forma de escrever algoritmos que usamos nas aulas, com um vocabulário pequeno e sempre igual e uma instrução por linha.
- Fluxograma: o desenho de um algoritmo, com figuras ligadas por setas. A forma de cada figura diz que tipo de instrução está lá dentro, e as setas dizem a ordem.
- Oval: a figura onde o algoritmo começa, com `Início`, e acaba, com `Fim`. Na aplicação tem as pontas redondas e chama-se Terminator.
- Paralelogramo: a figura das entradas e das saídas, com `ler valor` ou `Escreve:`. Na aplicação chama-se Data.
- Losango: a figura de uma decisão, com uma entrada e duas saídas. Na aplicação chama-se Decision.
- `ler valor`: a instrução que recebe um valor escrito por quem usa o algoritmo.
- `Escreve:`: a instrução que mostra texto e valores no ecrã.
- Constante: um valor fixo do problema, com o nome em maiúsculas, escrito com `const`, como `const NOTA_MAXIMA = 20`.
- Condição: uma pergunta cuja resposta só pode ser verdadeira ou falsa, `true` ou `false`, como `temperatura < 12`. Escreve-se dentro do losango. Para saber mais, vê a secção "Condições e o tipo `bool`" do [guia](03-decisoes-e-validacao.md).
- Sinais de comparação: `<` lê-se "é menor do que", `>` lê-se "é maior do que", e `>=`, "é maior ou igual a".
- `ou`: junta duas condições numa só, que é verdadeira quando pelo menos uma das duas é verdadeira.
- Saídas `Sim` e `Não`: as duas setas que saem de um losango. Segue-se a do `Sim` quando a resposta à condição é verdadeira, e a do `Não` quando é falsa.
- Ramo: cada um dos caminhos que saem de um losango.
- Ponto de junção: a figura onde os ramos de uma decisão se voltam a juntar, antes de o algoritmo continuar.
- Indentação: o recuo de quatro espaços que mostra, no pseudocódigo, que uma linha está dentro de um `Se`, de um `Senão se` ou de um `Senão`. Essa linha só se executa nesse caso.
- Seleção encadeada: um `Se` seguido de um ou mais `Senão se` e, muitas vezes, um `Senão` no fim. No fluxograma, é uma cadeia de losangos, cada um pendurado na saída `Não` do anterior. Para saber mais, vê a secção "Seleção encadeada" do [guia](03-decisoes-e-validacao.md).
- Caso de teste: uma entrada escolhida para testar o algoritmo, com o resultado que o enunciado pede.
- Browser: o programa que abre as páginas da internet, como o Chrome, o Edge, o Firefox ou o Safari.
- Ficheiro `.drawio`: o desenho que a aplicação volta a abrir para continuares a editar.
- Imagem PNG: uma imagem do desenho, que qualquer computador ou telemóvel abre, mas que não se edita.
- Exportar: criar a imagem PNG a partir do desenho.

## O que precisas

- Um computador com um browser e ligação à internet.
- O diagrams.net, a aplicação de diagramas deste laboratório. Também é conhecida por draw.io, que é o nome antigo, e os ficheiros que cria terminam em `.drawio`. Usa-se no browser, é gratuita e não precisa de conta. Confirma que chegas a ela: abre `https://app.diagrams.net/?lang=pt`. Deve aparecer um diagrama em branco, chamado "Diagrama sem nome", o que quer dizer que a aplicação está pronta a usar.
- A pasta `algoritmos`, onde guardas os ficheiros desta disciplina. Se fizeste o laboratório do tema 02, já a tens. Se não, cria-a antes de começar, numa pasta do computador, numa pen ou no sítio que o professor indicar. No Windows, carrega com o botão direito do rato num sítio vazio da pasta onde a queres, e escolhe "Novo" e depois "Pasta". Depois escreve o nome. No Mac, no Finder, carrega com o botão direito num sítio vazio, escolhe "Nova pasta" e escreve o nome.
- Papel e caneta, para a tabela da fase 3.

Se fizeste o [laboratório do tema 02](02-estado-sequencia-representacoes-laboratorio.md), já conheces a aplicação, e podes passar depressa pelos passos que já sabes. Se não o fizeste, não faz mal, porque cada ação está explicada na primeira vez que aparece.

## Se alguma coisa falhar

1. Vês a barra de menus no topo da aplicação, com Ficheiro, Editar, Visualização, Ordenar, Extras e Ajuda? Se não a vês, a janela do browser está estreita. Maximiza-a, ou usa o botão redondo com reticências, no canto superior direito, que tem as mesmas opções.
2. O teu ficheiro está guardado no computador? O nome que lhe deste aparece no topo da aplicação. Se o "Guardar como" te pedir para entrar numa conta, o campo "Onde:" ficou em Google Drive. Muda-o para "Aparelho" ou "Descarregar".
3. As setas estão presas às figuras? Arrasta uma figura um pouco para o lado. Se as setas a acompanharem, estão presas. Depois carrega em Ctrl+Z, ou Cmd+Z num Mac, para a figura voltar ao sítio.
4. Enganaste-te? Ctrl+Z, ou Cmd+Z num Mac, desfaz a última ação. Podes repetir para desfazer várias.

## Preparar o projeto

A aplicação muda de aspeto de vez em quando. Os nomes dos menus e dos botões deste laboratório foram confirmados em setembro de 2026, com a aplicação em português. Se um nome no teu ecrã não for exatamente igual, procura o que faz a mesma coisa, porque os passos são os mesmos.

1. Abre a aplicação em português. Abre o browser, maximiza a janela para ocupar o ecrã todo, e escreve na barra de endereços `https://app.diagrams.net/?lang=pt`. A parte final, `?lang=pt`, pede à aplicação que apareça em português.

   O que deves ver: um diagrama em branco, chamado "Diagrama sem nome". A aplicação não te pergunta nada nem te pede conta.

2. Guarda o ficheiro já, antes de desenhares. Neste momento, o diagrama só existe dentro do browser, e se fechares a página perdes tudo. Guardar logo dá-lhe um nome e um sítio.

   1. Na barra de menus, no topo da aplicação, carrega em "Ficheiro" e, na lista que se abre, em "Guardar como...".
   2. Abre-se a janela "Guardar como". No campo "Guardar como:", apaga o que lá estiver e escreve `fluxograma-classificar-nota.drawio`.
   3. No campo "Tipo:", deixa ficar "Ficheiro XML (.drawio)". É o formato que a aplicação volta a abrir para continuares a editar.
   4. O campo "Onde:" vem com "Google Drive". Muda-o para "Aparelho", que guarda o ficheiro numa pasta do teu computador. Se "Aparelho" não funcionar no teu computador, escolhe "Descarregar", e o ficheiro vai para a pasta de transferências.
   5. Carrega em "Guardar". Com "Aparelho", abre-se a janela do sistema para escolheres a pasta. Escolhe a pasta `algoritmos` e confirma.

   O que deves ver: o nome `fluxograma-classificar-nota.drawio` no topo da aplicação, onde antes estava "Diagrama sem nome". Daqui para a frente, para guardar, carrega em Ctrl+S, ou Cmd+S num Mac, ou escolhe "Ficheiro" e "Guardar". Se escolheste "Descarregar", cada vez que guardas vai uma cópia nova para as transferências. No fim, passa a mais recente para a pasta `algoritmos`.

   As outras opções do campo "Onde:" não servem aqui. Google Drive, OneDrive e GitHub pedem uma conta nesses serviços. "Navegador" guarda o ficheiro dentro do próprio browser, e perde-lo se alguém limpar os dados do browser ou se mudares de computador.

3. Encontra as figuras de fluxograma. O painel da esquerda tem as figuras arrumadas em grupos com nome. As que te interessam estão no grupo "Fluxograma", perto do fim da lista. Desce no painel e carrega no nome "Fluxograma" para o abrir. Se o grupo não estiver na lista, carrega no botão "+ Mais formas", no fundo do painel. Na janela "Formas", marca "Fluxograma" e confirma.

   Passa o rato devagar por cima das figuras do grupo. Ao lado de cada uma aparece o nome dela, em inglês, mesmo com a aplicação em português. Neste laboratório usas estas três:

   | Figura | Nome que vais ver | O que quer dizer | Para que serve |
   | --- | --- | --- | --- |
   | Oval, com as pontas redondas | Terminator | "terminal": onde o algoritmo começa ou acaba | `Início` e `Fim` |
   | Paralelogramo | Data | "dados": é por ali que os dados entram e saem | ler um valor (`ler valor`) e escrever no ecrã (`Escreve:`) |
   | Losango | Decision | "decisão" | uma condição, com duas saídas |

   A figura nova é a Decision, o losango. O grupo tem também o retângulo, chamado Process, que quer dizer "processamento". Serve para as contas e para as instruções que dão um valor a uma variável. Aqui não o usas, porque os algoritmos deste laboratório não fazem contas. Usa sempre as figuras do grupo "Fluxograma", mesmo que encontres outras parecidas noutros grupos.

## Fase 1: o losango e as saídas Sim e Não

Os algoritmos que fazem sempre as mesmas instruções, pela mesma ordem, desenham-se numa linha reta. Um algoritmo que decide faz uma pergunta e escolhe o caminho conforme a resposta. Vê este, de uma aplicação de meteorologia que te avisa quando está frio. A temperatura já está guardada na variável `temperatura`, porque foi lida mais acima:

```text
Se temperatura < 12
    Escreve: "Leva um casaco."
Escreve: "Bom dia."
```

Leitura guiada: a linha do `Se` faz uma pergunta, "a temperatura é menor do que 12?", que é a condição. A linha do casaco está quatro espaços mais para dentro, e essa indentação quer dizer que ela só se executa quando a resposta é sim. A última linha está encostada à margem, alinhada com o `Se`. Por isso está fora da decisão, e executa-se sempre.

No fluxograma, a pergunta vai dentro de um losango. Do losango saem duas setas, uma marcada `Sim` e outra marcada `Não`. Os dois caminhos voltam a juntar-se na figura de "Bom dia.", que é a instrução que se executa sempre. Neste laboratório, as saídas arrumam-se sempre da mesma maneira: a saída `Não` sai por baixo do losango, e a saída `Sim` sai pela direita. Assim, quem ler os teus fluxogramas sabe onde procurar cada uma. Para saber mais, lê a secção "Seleção simples" do [guia](03-decisoes-e-validacao.md).

Este primeiro desenho é de ensaio, para aprenderes a técnica com um algoritmo pequeno. Na fase 2 apagas este desenho e começas o da nota na página limpa.

1. Põe o losango na página. No grupo "Fluxograma", encontra a figura Decision. Carrega nela e, sem largar o botão do rato, arrasta-a para a página, perto do topo. Depois faz duplo clique dentro do losango, escreve `temperatura < 12?` e carrega numa zona vazia da página para acabar.

   O ponto de interrogação não é obrigatório, mas ajuda. Lembra a quem lê que dentro do losango está uma pergunta, e que a resposta é sim ou não. Os sinais `<` e `>` estão numa tecla própria, que nos teclados portugueses fica muitas vezes junto ao Z, e o `>` faz-se com Shift. Se não a encontrares, pede ajuda, porque os teclados variam de computador para computador.

   O que deves ver: o losango com o texto `temperatura < 12?` lá dentro.

2. Desenha a saída `Sim`. Arrasta um paralelogramo, a figura Data, para a direita do losango, à mesma altura. Faz duplo clique nele e escreve `Escreve: "Leva um casaco."`. Depois passa o rato por cima do losango, sem carregar. Aparecem pequenas setas azuis nos quatro lados. Carrega na seta azul do lado direito e, sem largar, arrasta até ao paralelogramo. Larga quando o paralelogramo ficar com o contorno azul. É esse contorno que mostra que a seta ficou presa à figura.

   Falta o nome da saída. Faz duplo clique a meio da seta que acabaste de desenhar. Aparece um espaço para escrever em cima da linha. Escreve `Sim` e carrega numa zona vazia.

   O que deves ver: uma seta do losango para o paralelogramo, com a palavra `Sim` em cima. Se não conseguires escrever na seta, vê os [problemas frequentes](#problemas-frequentes).

3. Desenha a saída `Não` e o ponto de junção. Arrasta outro paralelogramo para baixo do losango, com espaço entre os dois, e escreve dentro `Escreve: "Bom dia."`. Liga a seta azul de baixo do losango a este paralelogramo, e escreve `Não` nessa seta.

   Agora junta os ramos. Passa o rato pelo paralelogramo do casaco e arrasta a seta azul de baixo até ao paralelogramo de "Bom dia.". Larga quando ele ficar com o contorno azul. Esta seta não leva texto, porque não sai de um losango.

   O que deves ver: três figuras e três setas. Do losango saem duas setas, e as duas chegam, por caminhos diferentes, ao paralelogramo de "Bom dia.". O ramo do `Sim` passa pelo aviso do casaco. O ramo do `Não` vai direto a "Bom dia.", sem nenhuma figura pelo caminho.

4. Verifica com o dedo. Põe o dedo no losango, primeiro com a temperatura a valer 8, e depois a valer 20.

   O que deves ver: com 8, `8 < 12` é verdadeiro, por isso sais pelo `Sim`, passas pelo aviso do casaco e chegas a "Bom dia.". Com 20, `20 < 12` é falso, por isso sais pelo `Não` e chegas diretamente a "Bom dia.". Nos dois casos, o dedo chega ao mesmo sítio.

### Paragem 1

Confirma três coisas antes de avançares. Do losango saem exatamente duas setas. Cada uma tem o seu texto, `Sim` ou `Não`. E as duas acabam por chegar à mesma figura.

Pensa antes de continuares: no pseudocódigo, que linha corresponde à figura onde os dois ramos se juntam? A resposta: a linha `Escreve: "Bom dia."`, a primeira que volta a estar alinhada com o `Se`. Por isso já está fora da decisão, e executa-se seja qual for a resposta ao losango. É isto que quer dizer "os ramos voltam a juntar-se": o algoritmo acaba por passar pela mesma figura e continua a partir daí.

## Fase 2: uma cadeia de decisões, o fluxograma da nota

Às vezes há mais do que dois caminhos. Vê este problema:

> Um professor quer um algoritmo que o ajude a classificar os testes. O algoritmo lê a nota de um teste, que é um número inteiro na escala de 0 a 20. Se a nota for igual ou superior a 10, escreve "Positiva". Se for inferior a 10, escreve "Negativa". Se a nota escrita não pertencer à escala, o algoritmo escreve "Nota inválida" e não a classifica.

O algoritmo, em pseudocódigo:

```text
const NOTA_MINIMA = 0
const NOTA_MAXIMA = 20
const LIMIAR_POSITIVA = 10
Escreve: "Nota do teste (inteiro de 0 a 20)?"
int nota = ler valor
Se nota < NOTA_MINIMA ou nota > NOTA_MAXIMA
    Escreve: "Nota inválida"
Senão se nota >= LIMIAR_POSITIVA
    Escreve: "Positiva"
Senão
    Escreve: "Negativa"
```

Leitura guiada: as três linhas `const` dão nome a valores fixos do problema, o 0, o 20 e o 10. Depois o algoritmo faz a pergunta e lê a nota. A seguir vem uma cadeia de `Se`, `Senão se` e `Senão`, que faz as perguntas por ordem, de cima para baixo:

- O `Se` pergunta se a nota está fora da escala, isto é, se é menor do que 0 ou maior do que 20. Com o `ou`, basta falhar um dos lados para a nota ser inválida.
- O `Senão se` só se pergunta quando a resposta ao `Se` foi não, isto é, quando a nota é válida. Pergunta se a nota é maior ou igual a 10.
- O `Senão` não pergunta nada. Apanha o que sobra: uma nota válida e menor do que 10, que é negativa.

Numa cadeia, a primeira condição verdadeira ganha. O algoritmo executa o ramo dela e salta para depois da cadeia, sem fazer as perguntas seguintes. Por isso, no fluxograma, o segundo losango fica pendurado na saída `Não` do primeiro. Só se chega a ele quando a primeira resposta é não.

A cadeia acaba na primeira linha que volta à margem do `Se` sem ser um `Senão se` nem um `Senão`. É nessa linha que os ramos se juntam. Este algoritmo não tem mais nenhuma linha depois da cadeia, e por isso os três ramos juntam-se no Fim.

Algumas linhas do pseudocódigo não dão figura. As três linhas `const` não são passos do caminho: dão nome a valores fixos, e esses nomes aparecem dentro dos losangos, onde são usados. A palavra `Senão` também não tem figura própria. A figura do ramo dela é o paralelogramo "Negativa", à saída `Não` do segundo losango.

O desenho vai ter duas colunas. Ao centro desce o caminho principal, e à direita ficam os resultados que saem pelo `Sim` de cada losango. Esta arrumação não é obrigatória, mas os passos seguem-na.

1. Limpa a página. Carrega numa zona vazia e, sem largar o botão do rato, arrasta um retângulo que envolva as três figuras e as setas da fase 1. Tudo o que ficar dentro do retângulo fica selecionado. Carrega na tecla Delete ou Backspace.

   O que deves ver: a página vazia.

2. Desenha o início e a entrada. Arrasta um Terminator para o topo da página e escreve dentro `Início`. Por baixo, põe um paralelogramo com `Escreve: "Nota do teste (inteiro de 0 a 20)?"`. Por baixo deste, outro paralelogramo com `int nota = ler valor`. Liga as três figuras pela seta azul de baixo de cada uma, e larga sempre com a figura de destino de contorno azul.

   O que deves ver: três figuras em coluna, ligadas por duas setas que apontam para baixo.

3. Desenha o primeiro losango, o da validação. Por baixo do paralelogramo que lê a nota, arrasta um losango e escreve `nota < NOTA_MINIMA ou nota > NOTA_MAXIMA?`. O texto é comprido e não cabe bem num losango pequeno. Carrega uma vez no losango para o selecionar. Aparecem pequenos pontos nos cantos e a meio dos lados. Puxa um dos cantos para fora até o texto caber, de preferência numa ou duas linhas.

   Liga o paralelogramo que lê a nota ao losango. Depois, à direita do losango e à mesma altura, põe um paralelogramo com `Escreve: "Nota inválida"`. Liga a seta azul do lado direito do losango a este paralelogramo, e escreve `Sim` na seta.

   O que deves ver: o losango, com uma seta `Sim` para "Nota inválida". Quem sai por este `Sim` é uma nota fora da escala, e vai direta para a mensagem de erro, sem passar por mais nenhum losango.

4. Desenha o segundo losango, o do `Senão se`. Por baixo do primeiro losango, com espaço entre os dois, põe outro losango com `nota >= LIMIAR_POSITIVA?`. Liga a seta azul de baixo do primeiro losango a este segundo, e escreve `Não` na seta. É assim que se desenha um `Senão se`: o segundo losango pendurado na saída `Não` do primeiro.

   À direita do segundo losango, põe um paralelogramo com `Escreve: "Positiva"`, ligado pela seta azul do lado direito, com `Sim`. Por baixo do segundo losango, põe um paralelogramo com `Escreve: "Negativa"`, ligado pela seta azul de baixo, com `Não`. É o ramo do `Senão`, para onde vai a nota quando as duas condições dão não.

   O que deves ver: dois losangos em coluna, cada um com uma seta `Sim` para a direita e uma seta `Não` para baixo.

5. Desenha o Fim e junta os três caminhos. Por baixo de "Negativa", arrasta um Terminator e escreve `Fim`. Liga "Negativa" ao Fim. Depois liga "Positiva" ao Fim, e "Nota inválida" ao Fim. Estas duas setas descem pela coluna da direita e entram no Fim. Se uma seta atravessar outra figura ou fizer um percurso estranho, carrega nela. Depois arrasta o pequeno ponto que aparece a meio da linha, até ela passar por onde queres.

   Um fluxograma tem um só início e um só fim. Os três caminhos juntam-se no Fim, que no pseudocódigo é o sítio onde a cadeia acaba.

   O que deves ver: os três paralelogramos das mensagens, cada um com uma seta para o mesmo Fim.

### Paragem 2

Conta as figuras e as setas do teu desenho. Deve ter:

- nove figuras: dois ovais (Início e Fim), cinco paralelogramos (a pergunta, a leitura da nota e as três mensagens) e dois losangos;
- dez setas, das quais quatro têm texto, as duas que saem de cada losango;
- cada losango com uma seta `Sim` e uma seta `Não`, e nenhum com uma só saída;
- nenhuma seta solta, sem figura numa das pontas.

O teu desenho deve ter as mesmas figuras e as mesmas ligações que este. A arrumação é a dos passos, e o desenho em caracteres só a aproxima. Nele, os parênteses curvos são os ovais e as barras inclinadas são os paralelogramos. As figuras de três linhas com pontas são os losangos:

```text
                            ( Início )
                                |
                                ↓
        / Escreve: "Nota do teste (inteiro de 0 a 20)?" /
                                |
                                ↓
                     / int nota = ler valor /
                                |
                                ↓
         /                                              \
        <   nota < NOTA_MINIMA ou nota > NOTA_MAXIMA ?   >
         \                                              /
               |                                  |
              Não                                Sim
               |                                  |
               ↓                                  ↓
   /                             \      / Escreve: "Nota inválida" /
  <   nota >= LIMIAR_POSITIVA ?   >                |
   \                             /                 |
     |                         |                   |
    Não                       Sim                  |
     |                         |                   |
     ↓                         ↓                   |
 / Escreve: "Negativa" /  / Escreve: "Positiva" /  |
     |                         |                   |
     ↓                         ↓                   ↓
     +-------------------------+-------------------+
                               |
                               ↓
                            ( Fim )
```

Se o teu desenho tiver uma figura a mais ou a menos, compara-o figura a figura com o pseudocódigo, pela mesma ordem. Assim descobres qual é. Lembra-te de que as três linhas `const` e o `Senão` não dão figura. Guarda o ficheiro, com Ctrl+S ou Cmd+S.

Pensa antes de continuares: porque é que o segundo losango está ligado à saída `Não` do primeiro, e não à saída `Sim`? A resposta: o segundo losango é o `Senão se`, que só se pergunta quando a validação dá não, isto é, quando a nota é válida. Se estivesse ligado ao `Sim`, as notas fora da escala chegavam à pergunta da positiva e eram classificadas, que é o que o enunciado proíbe.

## Fase 3: seguir cada caminho com o dedo

Um fluxograma de decisões está certo quando cada caso de teste tem um caminho, e um só, do Início até ao Fim. Esse caminho tem de acabar na mensagem que o enunciado pede. É isso que vais confirmar agora. Para saber mais, lê a secção "Fronteiras e casos de teste" do [guia](03-decisoes-e-validacao.md).

Os erros de uma decisão escondem-se nos limites, porque é aí que a resposta muda. Por isso, os casos de teste escolhem-se junto de cada limite: o valor imediatamente abaixo, o próprio limite e o valor imediatamente acima. Os limites do enunciado são o 0 e o 20, os extremos da escala, e o 10, a partir do qual a nota é positiva. Ao lado de cada nota está a mensagem que o enunciado pede:

| Nota | Mensagem que o enunciado pede |
| ---: | --- |
| -1 | Nota inválida |
| 0 | Negativa |
| 1 | Negativa |
| 9 | Negativa |
| 10 | Positiva |
| 11 | Positiva |
| 19 | Positiva |
| 20 | Positiva |
| 21 | Nota inválida |

1. Copia esta tabela para a tua folha. As duas primeiras linhas estão preenchidas, para veres como se faz.

   | Nota | Saída do primeiro losango | Saída do segundo losango | Mensagem a que chegaste | Coincide com o enunciado? |
   | ---: | --- | --- | --- | --- |
   | -1 | Sim, porque `-1 < 0` dá `true` | não se chega a ele | Nota inválida | sim |
   | 0 | Não, porque `0 < 0` e `0 > 20` dão `false` | Não, porque `0 >= 10` dá `false` | Negativa | sim |
   | 1 | | | | |
   | 9 | | | | |
   | 10 | | | | |
   | 11 | | | | |
   | 19 | | | | |
   | 20 | | | | |
   | 21 | | | | |

2. Segue cada nota com o dedo. Põe o dedo no Início do teu desenho e segue as setas. Em cada losango, calcula a condição com o valor da nota e sai pelo `Sim` ou pelo `Não`, conforme o resultado. Escreve na folha por onde saíste de cada losango e a mensagem a que chegaste.

3. Confere a tua folha com a tabela completa. Basta teres escrito `Sim` ou `Não` em cada losango. As razões estão aqui para conferires também a conta.

   | Nota | Saída do primeiro losango | Saída do segundo losango | Mensagem a que chegaste | Coincide com o enunciado? |
   | ---: | --- | --- | --- | --- |
   | -1 | Sim, porque `-1 < 0` dá `true` | não se chega a ele | Nota inválida | sim |
   | 0 | Não, porque `0 < 0` e `0 > 20` dão `false` | Não, porque `0 >= 10` dá `false` | Negativa | sim |
   | 1 | Não, porque `1 < 0` e `1 > 20` dão `false` | Não, porque `1 >= 10` dá `false` | Negativa | sim |
   | 9 | Não, porque `9 < 0` e `9 > 20` dão `false` | Não, porque `9 >= 10` dá `false` | Negativa | sim |
   | 10 | Não, porque `10 < 0` e `10 > 20` dão `false` | Sim, porque `10 >= 10` dá `true` | Positiva | sim |
   | 11 | Não, porque `11 < 0` e `11 > 20` dão `false` | Sim, porque `11 >= 10` dá `true` | Positiva | sim |
   | 19 | Não, porque `19 < 0` e `19 > 20` dão `false` | Sim, porque `19 >= 10` dá `true` | Positiva | sim |
   | 20 | Não, porque `20 < 0` e `20 > 20` dão `false` | Sim, porque `20 >= 10` dá `true` | Positiva | sim |
   | 21 | Sim, porque `21 > 20` dá `true` | não se chega a ele | Nota inválida | sim |

   Se alguma linha da tua folha for diferente, segue outra vez esse caso devagar. Se o dedo for parar a outra mensagem, há uma seta ligada à figura errada ou um losango com o texto trocado.

4. Responde na folha a quatro perguntas, e confere cada resposta com a que está logo a seguir.

   1. Cada caso seguiu um caminho só, sem teres de escolher entre duas setas em nenhum losango? A resposta: sim. Em cada losango, a condição é verdadeira ou falsa, e por isso só uma das setas serve.
   2. Cada uma das três mensagens foi alcançada por pelo menos um caso? A resposta: sim. "Nota inválida" com -1 e 21, "Negativa" com 0, 1 e 9, e "Positiva" com 10, 11, 19 e 20. Se houvesse uma mensagem a que nenhum caso chegasse, ou faltava um caso na tabela, ou o desenho tinha um caminho impossível.
   3. Todos os caminhos acabaram no Fim? A resposta: sim, os três caminhos chegam ao mesmo Fim.
   4. Houve alguma nota fora da escala que chegasse ao segundo losango? A resposta: não. Uma nota fora da escala torna verdadeira a condição do primeiro losango e sai pelo `Sim`, que não leva ao segundo losango. Numa cadeia, a primeira condição verdadeira ganha, e as de baixo não são avaliadas.

5. Guarda o ficheiro e exporta a imagem. O ficheiro `.drawio` é o teu desenho editável, e a imagem serve para o mostrar ou entregar. Uma imagem não se edita. Se precisares de mudar alguma coisa, mudas o `.drawio` e exportas outra vez.

   Guarda primeiro o `.drawio`, com Ctrl+S ou Cmd+S. Depois, na barra de menus, carrega em "Ficheiro", depois em "Exportar como" e depois em "PNG...". Abre-se a janela "Imagem". Em "Tamanho", escolhe "Diagrama", para a imagem ter só o fluxograma, e não a página inteira. Confirma que "Fundo Transparente" está desligado e carrega em "Exportar". Se a aplicação te pedir um nome e um sítio, faz como ao guardar o `.drawio`. O nome é `fluxograma-classificar-nota.png`, e o sítio é "Aparelho" ou "Descarregar", na pasta `algoritmos`. Nunca escolhas o Google Drive nem o "Navegador".

   O que deves ver: a imagem na pasta `algoritmos`. Abre-a com duplo clique e confirma que se vê o fluxograma inteiro, com o texto legível.

### Paragem 3

O teu fluxograma da nota leva cada uma das nove notas, por um só caminho, à mensagem que o enunciado pede. Na pasta `algoritmos` tens `fluxograma-classificar-nota.drawio` e `fluxograma-classificar-nota.png`.

Pensa antes de continuares: imagina que, no primeiro losango, tinhas escrito `nota >= NOTA_MAXIMA` no lugar de `nota > NOTA_MAXIMA`. Que nota da tabela chegava a outra mensagem? A resposta: o 20. Com `>=`, `20 >= 20` dá verdadeiro, e o 20 saía pelo `Sim` para "Nota inválida", quando é uma nota possível e positiva. As outras oito notas davam o mesmo, e é por isso que o próprio limite tem de estar na tabela.

## Problemas frequentes

### Não encontras o losango

Desce até ao fim da lista do painel da esquerda e abre o grupo "Fluxograma". A figura chama-se Decision. Também podes escrever `Decision` na caixa de pesquisa, no topo do painel.

### Quando mexes uma figura, a seta não vai atrás dela

A seta não ficou presa à figura. Apaga-a e desenha-a outra vez, largando o botão do rato só quando a figura de destino ficar com o contorno azul.

### Não consegues escrever `Sim` na seta

Faz duplo clique exatamente em cima da linha da seta, e não ao lado. Se o `Sim` ficar parado quando mexes a seta, escreveste-o numa caixa de texto solta. Apaga essa caixa e escreve-o outra vez, com duplo clique na própria seta.

### O texto não cabe no losango

Carrega uma vez no losango para o selecionar e puxa um dos cantos para fora.

### Uma seta passa por cima de outra figura

Carrega na seta e arrasta o pequeno ponto que aparece a meio da linha, até ela passar por onde queres.

### Não aparece a barra de menus no topo

A janela do browser está estreita. Maximiza-a, ou usa o botão redondo com reticências, no canto superior direito. Nesse botão, o "Exportar como" aparece logo ao lado do "Ficheiro", em vez de estar dentro dele.

### O ficheiro foi para o Google Drive, ou o "Guardar como" pede uma conta

O campo "Onde:" ficou no Google Drive, que vem escolhido de início. Volta a guardar com "Guardar como..." e, no campo "Onde:", escolhe "Aparelho" ou "Descarregar". Se guardaste no "Navegador", faz o mesmo.

### Não sabes onde ficou o ficheiro

Se escolheste "Descarregar", o ficheiro está na pasta de transferências do computador. Passa a cópia mais recente para a pasta `algoritmos`.

### A imagem tem muito espaço vazio à volta do fluxograma

Na janela "Imagem", o "Tamanho" não ficou em "Diagrama". Exporta outra vez, com "Tamanho" em "Diagrama".

### Apagaste uma figura sem querer

Ctrl+Z, ou Cmd+Z num Mac, desfaz a última ação. Repete para desfazer mais.

### Um losango tem uma só saída, ou as setas dele não têm texto

Cada losango faz uma pergunta, e a resposta é sempre sim ou não. Por isso tem sempre duas setas, uma com `Sim` e outra com `Não`. Desenha a seta que falta, ou escreve o texto em cada seta com duplo clique em cima dela.

### O segundo losango ficou ligado ao `Sim` do primeiro

Segue com o dedo o caminho da nota 21. Com o desenho assim, a nota inválida chegava à pergunta da positiva. O segundo losango é o `Senão se`, e só se chega a ele pela saída `Não` do primeiro. Liga-o a essa saída.

### Desenhaste um Fim em cada ramo

Um fluxograma tem um só início e um só fim. Os ramos de uma decisão voltam a juntar-se, e todos os caminhos chegam ao mesmo Fim. Apaga os Fim a mais e liga os ramos ao que ficou.

### Desenhaste uma figura para as constantes ou para o `Senão`

As linhas `const` dão nome a valores fixos e não são passos do caminho, e por isso não têm figura. O `Senão` também não tem figura própria: a figura do ramo dele é o paralelogramo "Negativa". Apaga a figura a mais e liga as setas à figura seguinte.

## Desafios

1. A caixa de envio. Uma loja online escolhe a caixa de envio pelo peso da encomenda. Lê o enunciado e o pseudocódigo:

   > Uma loja online escolhe a caixa de envio pelo peso da encomenda, em gramas (um número inteiro). Encomendas até 2000 gramas, inclusive, vão numa caixa pequena; acima de 2000 gramas, vão numa caixa grande. Um peso de zero gramas, ou negativo, é um erro de pesagem, e o algoritmo escreve "Peso inválido" em vez de escolher a caixa. Em todos os casos, no fim, o algoritmo escreve "Pesagem concluída".

   ```text
   const PESO_MAXIMO_CAIXA_PEQUENA = 2000
   Escreve: "Peso da encomenda em gramas?"
   int peso = ler valor
   Se peso <= 0
       Escreve: "Peso inválido"
   Senão se peso <= PESO_MAXIMO_CAIXA_PEQUENA
       Escreve: "Caixa pequena"
   Senão
       Escreve: "Caixa grande"
   Escreve: "Pesagem concluída"
   ```

   O sinal `<=` quer dizer "é menor ou igual a". O pseudocódigo já está escrito, porque neste desafio o que treinas é o desenho e a verificação dos caminhos.

   a) Antes de desenhar, conta na folha quantas figuras e quantas setas o fluxograma vai ter, e decide a forma de cada figura.

   b) Cria o ficheiro do desafio. Na barra de menus, escolhe "Ficheiro" e "Guardar como...", escreve o nome `fluxograma-caixa-de-envio.drawio` e guarda-o na pasta `algoritmos`, como no início. O ficheiro da nota fica guardado como estava, e passas a trabalhar no ficheiro novo, que por enquanto tem o mesmo desenho. Se preferires começar num diagrama em branco, usa antes "Ficheiro" e "Novo...". A aplicação pode abrir o diagrama novo noutro separador do browser. Se te perguntar que tipo de diagrama queres, escolhe o diagrama em branco, e guarda-o logo com o mesmo nome.

   c) Desenha o fluxograma deste pseudocódigo. Podes aproveitar o desenho da nota e mudar os textos. Nesse caso, confirma figura a figura que o desenho corresponde a este pseudocódigo, e não ao da nota.

   d) Copia esta tabela para a folha e segue com o dedo o caminho de cada peso. Os pesos são os valores de um lado e do outro de cada um dos dois limites do enunciado, o 0 e o 2000.

   | Peso | Saída do primeiro losango | Saída do segundo losango | Mensagens a que chegaste | Coincide com o enunciado? |
   | ---: | --- | --- | --- | --- |
   | -1 | | | | |
   | 0 | | | | |
   | 1 | | | | |
   | 1999 | | | | |
   | 2000 | | | | |
   | 2001 | | | | |

   e) Guarda o ficheiro e exporta a imagem, com o nome `fluxograma-caixa-de-envio.png`.

   Terminaste quando os seis pesos tiverem um caminho, e cada caminho chegar às mensagens que o enunciado pede. Pista: repara na margem da última linha do pseudocódigo, e lembra-te do "Bom dia." da fase 1.

## Antes de terminares

- [ ] Na tua pasta `algoritmos` estão `fluxograma-classificar-nota.drawio` e `fluxograma-classificar-nota.png`.
- [ ] O fluxograma da nota tem nove figuras e dez setas, com um só Início e um só Fim.
- [ ] Cada losango tem duas saídas, uma `Sim` e outra `Não`.
- [ ] Na tua folha estão a tabela das nove notas e as respostas às quatro perguntas da fase 3.
- [ ] Se fizeste o desafio, estão também na pasta `fluxograma-caixa-de-envio.drawio` e `fluxograma-caixa-de-envio.png`, e na folha a tabela dos seis pesos.
- [ ] Consegues explicar, por palavras tuas, porque é que o segundo losango de uma cadeia fica na saída `Não` do primeiro.
- [ ] Consegues explicar, por palavras tuas, onde se juntam os ramos de uma decisão, e porquê.

As imagens e a folha são o que entregas, se o professor o pedir, pela forma de entrega que ele indicar. Os ficheiros `.drawio` guardas tu, porque podes voltar a precisar deles. Para praticares as decisões sem computador, faz a [ficha de exercícios](03-decisoes-e-validacao-exercicios.md) deste tema. O laboratório do tema 04, também opcional, acrescenta aos fluxogramas a seta que volta atrás, a das repetições.

![Rodapé](../imagens/rodape.png)
