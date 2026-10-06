![Cabeçalho](../imagens/cabecalho.png)

# Laboratório: fluxogramas com ciclos no diagrams.net

| Identificação | Valor |
| --- | --- |
| Disciplina | Fundamentos de Programação, 10.º ano, Desenvolvimento de Software |
| Unidade de competência | UC00245, Desenvolver algoritmos |
| Material | Laboratório do quarto tema, acompanha o [guia](04-repeticao-e-arrays.md) |
| Duração | 60 minutos, no computador, e é opcional |
| Evidência a guardar | Os ficheiros `.drawio` e as imagens `.png` dos dois fluxogramas deste laboratório, e a folha da parte autónoma, se o professor o indicar |

**Laboratório opcional.** Este laboratório é todo de fluxogramas, e só o fazes quando o professor o indicar. Nenhum exercício da ficha depende dele. Como se lê um fluxograma com um ciclo, com a seta que volta ao losango, está explicado no [guia](04-repeticao-e-arrays.md), na secção "A seta que volta ao losango".

## O que vais fazer

Vais desenhar no diagrams.net o fluxograma da primeira parte do exemplo guiado do guia, a campanha de recolha de alimentos. É um fluxograma com um ciclo, e por isso tem uma coisa que os fluxogramas dos laboratórios anteriores não tinham: uma seta que volta atrás, para cima, até ao losango da condição do ciclo.

Essa seta é a única técnica nova deste laboratório. O objetivo é aprender a desenhá-la de forma que qualquer pessoa, ao olhar para o desenho, perceba sem hesitar de onde sai, onde chega, e que não se confunde com as outras setas.

No fim há uma parte autónoma, com a tabuada do guia, que desenhas sozinho.

## O que precisas de saber antes

Dos laboratórios dos temas [2](02-estado-sequencia-representacoes-laboratorio.md) e [3](03-decisoes-e-validacao-laboratorio.md) precisas de saber, no diagrams.net:

- abrir a aplicação no browser, sem criar conta, e guardar o ficheiro na tua pasta `algoritmos`, com Ficheiro, Guardar como... e o campo "Onde:" em "Aparelho" ou "Descarregar";
- encontrar o grupo Fluxograma no painel da esquerda e reconhecer as figuras pelo nome: Terminator para o início e o fim, Process para o retângulo, Data para o paralelogramo e Decision para o losango;
- escrever o texto dentro de uma figura, com um duplo clique;
- ligar duas figuras com uma seta presa nas duas pontas;
- escrever `Sim` e `Não` nas setas que saem de um losango, seguindo a convenção do laboratório do tema 3: num `Se`, o `Não` sai por baixo e o `Sim` sai pela direita;
- juntar os dois ramos de uma decisão numa mesma figura;
- exportar o desenho como imagem PNG.

Este laboratório não volta a explicar esses passos em pormenor. Se te esqueceres de algum, volta à parte do laboratório que o explica.

Do guia precisas da secção "A seta que volta ao losango" e do exemplo guiado, sobretudo o passo 4, com o pseudocódigo da primeira parte, e o passo 5, com o trace. Tem o guia aberto ao lado.

Material: o computador com um browser, e papel e caneta para a parte autónoma.

## Parte 1: Preparar o ficheiro (5 min)

1. Abre o browser, maximiza a janela e vai a `https://app.diagrams.net/?lang=pt`.
2. A aplicação abre logo um diagrama em branco, chamado "Diagrama sem nome".
3. Guarda-o já, antes de desenhares. Na barra de menus, no topo, escolhe Ficheiro e depois Guardar como....
4. No campo "Guardar como:", escreve `fluxograma-campanha-de-alimentos.drawio`. Deixa o campo "Tipo:" em Ficheiro XML (.drawio).
5. No campo "Onde:", a aplicação sugere o Google Drive. Muda para "Aparelho". Se "Aparelho" não funcionar no teu computador, escolhe "Descarregar".
6. Carrega em Guardar e escolhe a pasta `algoritmos`. Com "Descarregar", o ficheiro vai para a pasta de transferências, e no fim do laboratório passas a cópia mais recente para a pasta `algoritmos`.

A partir daqui, guarda com Ctrl+S, ou Cmd+S num Mac, sempre que acabares uma parte.

Se a janela do browser estiver estreita, a barra de menus não aparece, e o menu abre no botão redondo com reticências, no canto superior direito, onde encontras Ficheiro e, ao mesmo nível, Exportar como. O mais simples é maximizar a janela.

## Parte 2: As figuras e a disposição (5 min)

O fluxograma da campanha tem 17 figuras. Esta é a lista, pela ordem do pseudocódigo do passo 4 do guia. A linha `const SENTINELA = -1` não tem figura, como nos laboratórios anteriores.

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

Um fluxograma com um ciclo fica confuso quando as figuras são postas à sorte e as setas se arranjam depois. A seta de volta precisa de um caminho livre para subir, e esse caminho tem de ser planeado antes de pores a primeira figura. A disposição que vais usar tem três faixas, lado a lado:

```text
  faixa livre        faixa do meio                        faixa da direita
  (a seta de volta   (o caminho principal,                (o ramo Sim do Se depois do ciclo;
   sobe por aqui)     de cima para baixo)                  mais à direita ainda, a saída do ciclo)

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

Repara em três pormenores, porque são eles que tornam o desenho inequívoco.

O losango do ciclo tem uma disposição diferente da do `Se`: o `Sim` sai por baixo, para o corpo do ciclo, e o `Não` sai pela direita, para fora do ciclo. Há uma razão. O losango de um ciclo tem quatro setas, e não três: a que chega de cima, as duas saídas e a seta de volta. Com o `Sim` por baixo, o corpo fica na faixa do meio e a ponta esquerda do losango fica livre para a seta de volta. O losango do `Se`, o 13, segue a convenção habitual: `Não` por baixo e `Sim` pela direita. Para distinguires os dois losangos à primeira vista: ao losango do ciclo chega uma seta pela esquerda; ao do `Se`, não.

A faixa da esquerda fica vazia de figuras. É por ali que a seta de volta sobe, da figura 10 até à ponta esquerda do losango 6, sem passar por cima de nada. A seta que vem da figura 5 chega ao mesmo losango pela ponta de cima. São duas setas a chegar ao mesmo losango, cada uma por um lado.

A saída `Não` do ciclo desce por fora de tudo, à direita, até à figura 11. Entre a figura 10 e a figura 11 fica um espaço vazio, sem seta: quem sai do corpo volta sempre ao losango, e só a saída `Não` chega aos resultados.

## Parte 3: Desenhar as figuras e as setas que já sabes fazer (15 min)

1. No painel da esquerda, abre o grupo Fluxograma.
2. Desenha a faixa do meio, de cima para baixo, com as figuras 1 a 13, 16 e 17 da tabela, deixando um espaço vazio entre a 10 e a 11. Desenha a faixa da direita com as figuras 14 e 15, à direita do losango 13, a 14 à mesma altura dele.
3. Escreve em cada figura o texto da tabela, igual ao do pseudocódigo do guia. Tudo se escreve diretamente no teclado. Repara que as figuras 2, 3 e 5 levam o tipo à frente, porque é aí que as variáveis nascem, e que as figuras 7, 8 e 10 não o levam.
4. Os losangos e alguns paralelogramos têm texto comprido. Seleciona-os e puxa um dos cantos para fora até o texto caber.

Para poupar tempo, desenha uma figura, escreve-lhe o texto, e depois duplica-a e muda só o texto: seleciona a figura e usa Ctrl+D, ou Cmd+D num Mac. As figuras 4 e 9, por exemplo, têm exatamente o mesmo texto.

5. Liga com setas, de cima para baixo, as figuras 1 a 6, e as figuras 7 a 10. Não ligues a figura 10 a nada ainda: essa é a seta da parte 4.
6. Liga a ponta de baixo do losango 6 à figura 7 e escreve `Sim` nessa seta.
7. Liga as figuras 11, 12 e 13, de cima para baixo.
8. No losango 13, liga a ponta de baixo à figura 16 e escreve `Não`. Liga a ponta direita à figura 14 e escreve `Sim`. Liga a figura 14 à 15.
9. Junta os dois ramos do `Se`: liga a figura 16 ao Fim, por cima, e a figura 15 ao Fim, fazendo a seta chegar pelo lado direito do Fim.

Guarda o ficheiro.

## Parte 4: A seta que volta ao losango (15 min)

Esta é a parte nova. Faz os passos devagar e confirma cada um antes de passares ao seguinte.

**1. Começar na figura certa.** A seta de volta sai da última figura do corpo do ciclo, a figura 10, `quilos = ler valor`. Não sai do losango, nem da pergunta que está acima da leitura. Para confirmares, procura no pseudocódigo do guia a última linha indentada debaixo do `Enquanto`: é dessa figura que a seta sai.

**2. Sair pelo lado esquerdo.** Passa o rato por cima da figura 10. Aparecem as pequenas setas azuis nos quatro lados. Carrega na seta azul do lado esquerdo e, sem largar o botão do rato, arrasta para cima, até ao losango 6.

**3. Largar na ponta esquerda do losango.** Nos laboratórios anteriores largavas a seta quando a figura de destino ficava com o contorno azul. Isso prende a seta à figura, mas deixa a aplicação escolher o lado por onde a seta entra, e muitas vezes ela escolhe a ponta de cima, onde já chega a seta da figura 5. Ficavas com duas setas a entrar no mesmo ponto, e quem olhasse para o desenho já não conseguia ver qual delas vem de onde.

Para a seta de volta, és tu que escolhes o lado. Quando o rato passa por cima do losango, aparecem no seu contorno pequenas marcas, que são os pontos onde uma seta se pode prender. Leva o rato até à marca que está na ponta esquerda do losango e só então larga o botão.

**4. Ver o caminho que a seta fez.** A aplicação desenha as setas com ângulos retos: a seta deve sair da figura 10 para a esquerda, subir pela faixa livre e virar à direita para entrar na ponta esquerda do losango. Se a seta aparecer como uma linha inclinada, a direito, seleciona-a com um clique e, no painel da direita, no separador Estilo, procura a opção Pontos de passagem e escolhe Ortogonal, que é a opção das linhas com ângulos retos.

**5. Afastar a seta das figuras.** Se a parte vertical da seta passar por cima de alguma figura, ou muito encostada a elas, clica na seta e arrasta o ponto que aparece a meio dessa parte vertical para a esquerda, até a seta subir pela faixa livre. Se a seta ficar com um caminho estranho e não a conseguires endireitar, clica nela com o botão direito do rato e procura a opção Limpar pontos de passagem, que devolve a seta ao caminho automático. Depois tenta outra vez.

**6. Confirmar o sentido.** A ponta da seta tem de estar no losango, e não na figura 10. Se estiver ao contrário, é porque arrastaste do losango para a leitura. Seleciona a seta, apaga-a com a tecla Delete e faz de novo, a partir da figura 10.

**7. Deixar a seta sem texto.** Não escrevas nada na seta de volta. O `Sim` e o `Não` pertencem às saídas do losango, e uma palavra na seta de volta faria parecer que ela é uma saída.

**8. Desenhar a saída do ciclo.** Liga a ponta direita do losango 6 à figura 11. A seta deve sair para a direita, descer por fora de tudo e entrar na figura 11 pelo lado direito. Se passar por cima de alguma figura, afasta-a como no passo 5. Escreve `Não` nesta seta.

Agora olha para o losango 6. Devem chegar-lhe duas setas, uma por cima e uma pela esquerda, e sair duas, o `Sim` por baixo e o `Não` pela direita. Nenhuma das quatro partilha o mesmo ponto do contorno.

## Parte 5: Verificar o desenho com um caso de teste (5 min)

Um fluxograma verifica-se percorrendo-o. Usa o primeiro caso do passo 5 do guia: a funcionária escreve 12, depois 0, depois 9 e depois -1.

Com o ponteiro do rato, segue o caminho desde o início, e diz em voz baixa o valor de cada variável sempre que ele muda. Em cada losango, escolhe a saída pela condição, com os valores do momento. Conta quantas vezes passas pelo losango do ciclo.

Se o desenho estiver certo, passas quatro vezes pelo losango 6, uma vez pelo losango 13, e chegas ao fim com 3 turmas, 21 quilos e a média de 7, os mesmos valores da tabela do guia. Se deres por ti numa figura de onde não sai nenhuma seta, ou a voltar a uma inicialização, há uma seta errada. Corrige-a antes de continuares.

Confirma depois esta lista:

- há um único início e um único fim;
- todas as figuras têm pelo menos uma seta a entrar e uma a sair, menos o início, que só tem saída, e o fim, que só tem entrada;
- cada losango tem exatamente duas saídas, uma com `Sim` e outra com `Não`;
- a seta de volta sai da figura 10 e chega ao losango 6, e não a outra figura;
- nenhuma seta cruza outra, e nenhuma passa por cima de uma figura;
- o texto de cada figura é o mesmo do pseudocódigo.

## Parte 6: Guardar e exportar (5 min)

1. Guarda o `.drawio`, com Ctrl+S ou Cmd+S.
2. Na barra de menus, escolhe Ficheiro, depois Exportar como e depois PNG....
3. Abre-se a janela Imagem. Em "Tamanho", escolhe "Diagrama", e confirma que a opção Fundo Transparente está desligada.
4. Carrega em Exportar. Se a aplicação pedir um nome e um sítio, o nome é `fluxograma-campanha-de-alimentos.png` e o sítio é "Aparelho" ou "Descarregar", nunca o Google Drive.
5. Abre a imagem exportada e confirma que se lê todo o texto e que se veem todas as setas, incluindo a de volta.

## Parte autónoma: a tabuada com `Para` (10 min)

Esta parte fazes sozinho. Cria um ficheiro novo, em Ficheiro, Novo..., e guarda-o logo na pasta `algoritmos`, com o nome `fluxograma-tabuada.drawio`.

Vais desenhar o fluxograma da tabuada do guia, escrita com `Para`:

```text
const NUMERO = 7
const ULTIMO = 3
Para vezes de 1 até ULTIMO
    Escreve: NUMERO, " x ", vezes, " = ", NUMERO * vezes
Escreve: "Fim da tabuada"
```

A única coisa nova é o `Para`. No guia viste que, nos fluxogramas, o `Para` se desenha como o `Enquanto` equivalente. Por isso o desenho tem figuras que não aparecem escritas como linhas no pseudocódigo acima.

**a)** No papel, escreve as duas instruções que o `Para` faz sem aparecerem escritas como linhas, a inicialização e a atualização, e diz onde fica cada uma no fluxograma: antes do losango, ou no fim do corpo, mesmo antes da seta de volta.

**b)** Desenha o fluxograma no diagrams.net, com essas duas figuras, o losango `vezes <= ULTIMO?` e a seta de volta a chegar à ponta esquerda do losango, como na parte 4. O `Sim` sai por baixo e o `Não` pela direita.

**c)** Percorre o desenho com o ponteiro do rato. Escreve no papel quantas vezes passaste pelo losango e o que apareceu no ecrã, linha a linha.

Guarda e exporta a imagem como `fluxograma-tabuada.png`, como na parte 6. Se o tempo da aula não chegar para esta parte, termina-a no início da aula seguinte.

## Quando alguma coisa corre mal na aplicação

| O que acontece | O que fazer |
| --- | --- |
| A seta de volta entra no losango por cima, no mesmo ponto da seta da leitura antecipada | Apaga-a e desenha-a outra vez, largando na marca da ponta esquerda do losango, e não no meio dele |
| A seta de volta atravessa figuras | Clica nela e arrasta o ponto do meio da parte vertical para a esquerda |
| A seta ficou torta ou com um caminho estranho | Botão direito sobre a seta, Limpar pontos de passagem, e ajusta outra vez |
| A ponta da seta está na leitura e não no losango | Arrastaste ao contrário: apaga a seta e desenha-a a partir da leitura |
| O texto não cabe no losango | Seleciona o losango e puxa um dos cantos para fora |
| O ficheiro foi guardado no Google Drive | Volta a guardar com Ficheiro, Guardar como... e, no campo "Onde:", escolhe "Aparelho" ou "Descarregar" |
| Não aparece a barra de menus no topo | A janela está estreita: maximiza o browser, ou usa o botão redondo com reticências, no canto superior direito |
| Apagaste uma figura sem querer | Ctrl+Z, ou Cmd+Z num Mac, desfaz a última ação |

## O que entregar

Na tua pasta `algoritmos` tens de ter quatro ficheiros novos:

- `fluxograma-campanha-de-alimentos.drawio` e `fluxograma-campanha-de-alimentos.png`;
- `fluxograma-tabuada.drawio` e `fluxograma-tabuada.png`.

E em papel, a folha da parte autónoma, com as duas instruções que o `Para` faz sem aparecerem escritas, o número de passagens pelo losango e o que apareceu no ecrã.

Antes de entregares, confirma:

- [ ] A seta de volta de cada ciclo sai da última figura do corpo e chega ao losango desse ciclo, sem cruzar nenhuma seta nem passar por cima de nenhuma figura.
- [ ] Em cada losango de ciclo chegam duas setas e saem duas, cada uma no seu ponto do contorno.
- [ ] Cada losango tem uma saída `Sim` e uma saída `Não`, e as setas de volta não têm texto.

![Rodapé](../imagens/rodape.png)
