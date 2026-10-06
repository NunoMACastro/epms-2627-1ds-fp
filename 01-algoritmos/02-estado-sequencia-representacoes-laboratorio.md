![Cabeçalho](../imagens/cabecalho.png)

# Laboratório: o primeiro fluxograma no diagrams.net

| Identificação | Valor |
| --- | --- |
| Disciplina | Fundamentos de Programação, 10.º ano, Desenvolvimento de Software |
| Unidade de competência | UC00245, Desenvolver algoritmos |
| Material | Laboratório do segundo tema, acompanha o [guia](02-estado-sequencia-representacoes.md) |
| Duração | 40 minutos, e é opcional |
| Evidência a guardar | Os ficheiros `.drawio` e as imagens `.png` dos dois fluxogramas deste laboratório, se o professor o indicar |

**Laboratório opcional.** Este laboratório é todo de fluxogramas, e só o fazes quando o professor o indicar. Nenhum exercício da ficha depende dele. O que é um fluxograma, o que quer dizer cada figura e como se lê está explicado no [guia](02-estado-sequencia-representacoes.md), na secção "Fluxogramas" e no passo 5 do exemplo guiado.

Este laboratório diz o que fazer, passo a passo, com a aplicação de fluxogramas aberta ao lado. As explicações do porquê estão no guia: quando um passo usa uma ideia do guia, o texto diz em que secção ela está explicada.

Vais fazer duas coisas. Primeiro, com a ajuda deste documento, desenhas na aplicação o fluxograma do exemplo guiado, o que converte minutos em horas e minutos. Depois, na última parte, desenhas sozinho o fluxograma de outro algoritmo.

## Antes de começar

Antes do laboratório deves ter lido, no guia, a secção "Fluxogramas" e o exemplo guiado até ao passo 5, onde está o fluxograma. O laboratório não repete essas explicações: aplica-as.

Precisas de um computador com um browser (Chrome, Edge, Firefox ou Safari) e ligação à internet. Tem o guia aberto noutro separador do browser, ou o pseudocódigo do exemplo guiado escrito em papel, porque vais copiar o texto de cada instrução.

A aplicação chama-se diagrams.net, e também é conhecida por draw.io, que é o nome antigo. Usa-se no browser, é gratuita e não precisa de conta. Os ficheiros que ela cria terminam em `.drawio`. Se o professor indicar outra aplicação de diagramas, os passos são parecidos: muda o sítio dos menus, mas não o que tens de fazer.

Decide antes de começar onde vais guardar os ficheiros desta disciplina: numa pasta do computador, numa pen ou no sítio que o professor indicar. Cria lá uma pasta chamada `algoritmos`. Todos os ficheiros deste laboratório têm nomes em minúsculas, com hífenes entre as palavras e sem acentos nem espaços, como `fluxograma-converter-minutos.drawio`. Um nome assim funciona em qualquer computador e diz o que o ficheiro contém sem ser preciso abri-lo.

A aplicação muda de aspeto de vez em quando. Os nomes dos menus e dos botões deste laboratório foram confirmados em setembro de 2026, com a aplicação em português. Se um nome no teu ecrã não for exatamente igual, procura o que faz a mesma coisa: os passos são os mesmos.

## Parte 1: abrir a aplicação e conhecer o ecrã

1. Abre o browser, maximiza a janela para ocupar o ecrã todo, e escreve na barra de endereços `https://app.diagrams.net/?lang=pt`. A parte final, `?lang=pt`, pede à aplicação que apareça em português. Sem ela, a aplicação usa a língua do browser, que pode ser o inglês.
2. A aplicação abre logo um diagrama em branco, chamado "Diagrama sem nome". Não te pergunta nada nem te pede conta.

Repara nas quatro zonas do ecrã, porque vais usá-las todas:

| Zona | Onde está | Para que serve |
| --- | --- | --- |
| Painel das figuras | à esquerda | tem as figuras, arrumadas em grupos, e no topo uma caixa de pesquisa onde se lê "Escreva / para pesquisar" |
| Página | ao centro, a zona branca com uma grelha de quadrados | é onde desenhas; a grelha só serve para ajudar a alinhar |
| Painel de formatação | à direita, com os separadores "Diagrama" e "Estilo" | muda o aspeto do que estiver selecionado; neste laboratório quase não precisas dele |
| Barra de menus | no topo, com Ficheiro, Editar, Visualização, Ordenar, Extras e Ajuda | o menu "Ficheiro" tem tudo o que é guardar, abrir e exportar |

Neste laboratório só vais usar o menu "Ficheiro", da barra de menus. Os passos seguintes dizem sempre o caminho completo, por exemplo "Ficheiro" e depois "Guardar como...": carregas em "Ficheiro", abre-se uma lista, e escolhes a opção nessa lista.

A aplicação muda de aspeto conforme a largura da janela. Se a janela do browser estiver estreita, por exemplo a ocupar só metade do ecrã, a barra de menus desaparece e aparece em vez dela um botão redondo com reticências (três pontos), no canto superior direito. Esse botão abre um menu com "Ficheiro" e "Exportar como" lado a lado. A forma mais simples de seguir este laboratório é maximizar a janela; se não puderes, usa esse botão sempre que os passos falarem da barra de menus, e procura "Exportar como" diretamente no menu, e não dentro de "Ficheiro".

Neste momento, o diagrama só existe dentro do separador do browser. Se fechares o separador, perdes tudo. É por isso que a parte seguinte é guardar, antes de desenhar.

## Parte 2: guardar o ficheiro no teu computador

Guardar logo no início dá um nome e um sítio ao ficheiro. A partir daí, cada vez que guardares, o trabalho vai para o mesmo ficheiro.

1. Na barra de menus, carrega em "Ficheiro".
2. Na lista que se abre, escolhe "Guardar como...".
3. Abre-se a janela "Guardar como", com três campos. No campo "Guardar como:", apaga o que lá estiver e escreve `fluxograma-converter-minutos.drawio`. Mantém o `.drawio` no fim.
4. No campo "Tipo:" deixa ficar "Ficheiro XML (.drawio)". É o formato próprio da aplicação, o único que ela consegue voltar a abrir para continuares a editar.
5. O campo "Onde:" é o mais importante, e vem com "Google Drive" escolhido. Tens de o mudar: escolhe "Aparelho", que guarda o ficheiro numa pasta do teu computador. Se "Aparelho" não funcionar no teu browser, escolhe "Descarregar", que põe o ficheiro na pasta de transferências.
6. Carrega em "Guardar". Com "Aparelho", abre-se a janela habitual do sistema para escolheres a pasta: escolhe a pasta `algoritmos` que criaste e confirma. Com "Descarregar", o ficheiro vai para a pasta de transferências do browser, e no fim do laboratório passas a cópia mais recente para a pasta `algoritmos`.
7. Confirma que o nome que escreveste aparece agora no topo da aplicação, onde antes estava "Diagrama sem nome".

As outras opções do campo "Onde:" não servem aqui. Google Drive, OneDrive, Microsoft 365 e GitHub pedem uma conta nesses serviços. "Navegador" guarda o ficheiro dentro do próprio browser, e basta alguém limpar os dados do browser, ou mudares de computador, para o perderes.

Daqui para a frente, para guardar basta carregar em Ctrl+S, ou Cmd+S num Mac, ou escolher "Ficheiro" e depois "Guardar", na barra de menus. Guarda muitas vezes: no fim de cada parte deste laboratório, pelo menos. Se escolheste "Descarregar", cada vez que guardas é descarregada uma cópia nova, e o browser pode acrescentar um número ao nome. No fim, fica com a mais recente.

## Parte 3: encontrar as figuras de fluxograma

O painel da esquerda tem as figuras arrumadas em grupos com nome: Rascunho, Geral, Diversos, Avançado, Básico, Setas, Fluxograma e outros. As figuras que te interessam estão no grupo "Fluxograma".

1. Desce no painel da esquerda com a roda do rato, ou com o dedo no trackpad. O grupo "Fluxograma" fica perto do fim da lista.
2. Carrega no nome "Fluxograma" para abrir o grupo e ver as figuras.
3. Se o grupo não aparecer na lista, carrega no botão "+ Mais formas", no fundo do painel da esquerda. Abre-se a janela "Formas". Confirma que "Fluxograma" está marcado e fecha a janela com o botão de confirmar. O grupo passa a aparecer no painel.

Passa o rato por cima das figuras do grupo, devagar. Ao lado de cada uma aparece uma pré-visualização com o nome da figura. Os nomes aparecem em inglês, mesmo com a aplicação em português, e por isso convém saberes o que cada um quer dizer:

| Figura | Nome que aparece | O que quer dizer | Para que a usas |
| --- | --- | --- | --- |
| Retângulo de pontas redondas | Terminator | terminal, o sítio onde o algoritmo começa ou acaba | `Início` e `Fim`; é o oval do guia |
| Paralelogramo | Data | dados, que entram ou saem do algoritmo | as leituras, com `ler valor`, e as saídas, com `Escreve:` |
| Retângulo | Process | processo, ou seja, processamento | atribuições e contas |
| Losango | Decision | decisão | só a partir do guia 3 |

O grupo "Fluxograma" tem muitas outras figuras, com nomes como Display, Document ou Manual Input. Pertencem a convenções de fluxograma mais pormenorizadas do que a desta disciplina, e não as vais usar. Usa sempre as quatro da tabela, e sempre do grupo "Fluxograma", mesmo que encontres figuras parecidas noutros grupos, como o "Geral".

## Parte 4: pôr as figuras na página, com o texto

O fluxograma que converte minutos tem 7 figuras: uma por cada uma das cinco instruções do pseudocódigo, mais o início e o fim. A linha da constante, `const MINUTOS_POR_HORA = 60`, não tem figura. A razão das duas coisas está no guia, no passo 5 do exemplo guiado. Esta é a lista completa, pela ordem de cima para baixo:

| Ordem | Figura | Nome que aparece | Texto a escrever |
| --- | --- | --- | --- |
| 1 | Retângulo de pontas redondas | Terminator | `Início` |
| 2 | Paralelogramo | Data | `Escreve: "Quantos minutos?"` |
| 3 | Paralelogramo | Data | `int totalMinutos = ler valor` |
| 4 | Retângulo | Process | `int horas = totalMinutos div MINUTOS_POR_HORA` |
| 5 | Retângulo | Process | `int minutos = totalMinutos resto MINUTOS_POR_HORA` |
| 6 | Paralelogramo | Data | `Escreve: horas, " h e ", minutos, " min"` |
| 7 | Retângulo de pontas redondas | Terminator | `Fim` |

### Pôr a primeira figura

1. No grupo "Fluxograma", carrega na figura Terminator e, sem largar o botão do rato, arrasta-a para a página. Larga-a perto do topo, ao centro.
2. A figura fica selecionada, com um contorno azul e uns quadradinhos nos cantos. Se carregares numa zona vazia da página, deixa de estar selecionada; se carregares nela, volta a ficar.

### Escrever o texto dentro da figura

1. Faz duplo clique dentro da figura. Aparece um cursor a piscar.
2. Se a figura já tiver algum texto, apaga-o. Escreve `Início`.
3. Para acabar de escrever, carrega numa zona vazia da página. O texto fica dentro da figura.

Se te enganares, faz outra vez duplo clique e corrige. Se fizeres uma asneira maior, como apagar a figura sem querer, carrega em Ctrl+Z, ou Cmd+Z num Mac, que desfaz a última ação. Podes carregar várias vezes para desfazer várias ações.

### Pôr as outras figuras

Repete o arrastar e o duplo clique para as figuras 2 a 7, sempre com a figura e o texto da tabela. Três conselhos poupam-te tempo:

- Deixa espaço entre as figuras, mais ou menos a altura de uma figura, para caberem as setas.
- Mantém as figuras em coluna. Quando arrastas uma figura, a aplicação mostra linhas de guia coloridas quando ela fica alinhada com outra. Larga a figura quando a linha de guia vertical aparecer: ficam todas centradas umas por baixo das outras.
- Para repetir uma figura já feita, copia-a. Seleciona um paralelogramo, carrega em Ctrl+C e depois em Ctrl+V (Cmd+C e Cmd+V num Mac). Aparece uma cópia ao lado, que arrastas para o sítio certo, e só tens de mudar o texto.

Se o texto não couber na figura, seleciona-a e arrasta um dos quadradinhos azuis dos cantos para a alargar. As instruções das figuras 4, 5 e 6 são compridas: vale a pena alargar essas três figuras para cada instrução caber numa só linha.

Todo o texto das figuras se escreve com as teclas normais do teclado. Repara no sinal das figuras 3, 4 e 5: é um só sinal de igual, `=`, porque são atribuições, em que a variável recebe um valor. Não escrevas `==`, que é uma pergunta. A secção "Atribuição: dar um valor não é perguntar se é igual", no guia, explica a diferença.

Quando tiveres as 7 figuras com o texto, guarda (Ctrl+S ou Cmd+S).

## Parte 5: ligar as figuras com setas

O fluxograma tem 6 setas, uma entre cada par de figuras seguidas. Sete figuras em coluna precisam de seis ligações.

1. Passa o rato por cima da figura 1, a do Início, sem carregar. Aparecem quatro pequenas setas azuis, uma de cada lado da figura.
2. Carrega na seta azul de baixo e, sem largar o botão do rato, arrasta até à figura 2.
3. Quando a figura 2 ficar com um contorno azul, larga o botão. Fica uma seta desenhada da figura 1 para a figura 2, com a ponta virada para a figura 2.
4. Faz o mesmo da figura 2 para a 3, da 3 para a 4, e assim até à 7.

A ponta de cada seta tem de apontar para a figura seguinte, que é o sentido em que o algoritmo é executado. Se uma seta ficar ao contrário, seleciona-a, apaga-a com a tecla Delete ou Backspace, e desenha-a outra vez a partir da figura certa.

Uma seta só está bem feita se estiver presa às duas figuras. Há uma forma simples de o confirmar: arrasta uma figura um pouco para o lado. Se as setas a acompanharem, esticando-se, estão presas. Se uma ponta ficar parada no sítio antigo, essa seta está solta: apaga-a e desenha-a outra vez, largando só quando a figura de destino ficar com o contorno azul. Depois, carrega em Ctrl+Z para a figura voltar ao sítio.

Num algoritmo sequencial, as setas não levam texto. As setas com texto, com Sim e Não, aparecem no guia 3, quando houver decisões.

Guarda outra vez (Ctrl+S ou Cmd+S).

## Parte 6: verificar o fluxograma contra o pseudocódigo

Antes de dares o desenho por acabado, verifica-o como o guia ensina no passo 5 do exemplo guiado, com o pseudocódigo ao lado:

- [ ] Tem 7 figuras e 6 setas.
- [ ] Tem um único Início, no topo, e um Fim, em baixo, os dois em retângulos de pontas redondas.
- [ ] O `Escreve:` com a pergunta, a leitura e o `Escreve:` do fim estão em paralelogramos, e as duas contas estão em retângulos.
- [ ] O texto de cada figura diz o mesmo que a instrução correspondente do pseudocódigo: o tipo à frente das variáveis que nascem, o `=`, o `div` e o `resto`, e, dentro das aspas, os mesmos espaços, porque são eles que decidem o que aparece no ecrã.
- [ ] As figuras estão pela mesma ordem que as instruções do pseudocódigo.
- [ ] Todas as setas estão presas nas duas pontas e apontam para baixo.

Depois percorre o fluxograma com o dedo no ecrã, como se a pessoa tivesse escrito 60 minutos. No paralelogramo do último `Escreve:`, diz em voz baixa o que aparece no ecrã. Tens de chegar ao mesmo que a primeira tabela de trace do passo 6 do guia: "1 h e 0 min". Se não chegares, há uma figura fora do sítio ou com o texto errado.

## Parte 7: exportar uma imagem do fluxograma

O ficheiro `.drawio` é o teu fluxograma editável: é esse que abres para continuar a trabalhar ou para corrigir. Para mostrar o fluxograma a alguém, ou para o entregar, exporta-se uma imagem, que qualquer computador ou telemóvel abre sem precisar da aplicação. Uma imagem não se edita: se precisares de mudar alguma coisa, mudas o `.drawio` e exportas a imagem outra vez. Por isso guardas sempre os dois ficheiros.

1. Guarda primeiro o `.drawio` (Ctrl+S ou Cmd+S).
2. Na barra de menus, escolhe "Ficheiro", depois "Exportar como" e depois "PNG...". PNG é um formato de imagem que mantém as letras nítidas.
3. Abre-se uma janela chamada "Imagem", com as opções da imagem. Em "Tamanho", escolhe "Diagrama", para a imagem ter só o fluxograma e não a página inteira com espaço vazio à volta. Confirma que "Fundo Transparente" está desligado: com o fundo transparente, a imagem pode ficar ilegível quando aberta num fundo escuro. Deixa as outras opções, como "Zoom" e "Incluir uma cópia do meu diagrama", como estão.
4. Carrega em "Exportar".
5. Se a aplicação pedir um nome e um sítio, faz como na parte 2: o nome é `fluxograma-converter-minutos.png`, e o sítio é "Aparelho" ou "Descarregar", nunca Google Drive nem "Navegador".
6. Vai à pasta onde a imagem ficou e abre-a com duplo clique. Confirma que se vê o fluxograma inteiro, com as sete figuras e o texto legível.

Por fim, confirma que o `.drawio` ficou mesmo guardado. Fecha o separador da aplicação, abre outra vez `https://app.diagrams.net/?lang=pt`, e na barra de menus escolhe "Ficheiro", "Abrir de" e o sítio onde o guardaste. Escolhe o ficheiro. Se o fluxograma aparecer como o deixaste, está guardado. Se a aplicação te perguntar se queres guardar alterações a um diagrama sem nome, podes responder que não: o teu trabalho está no ficheiro que acabaste de abrir.

## Parte 8: desenhar sozinho

Agora sem a lista de figuras. Um grupo de amigos jantou fora e quer dividir a conta em partes iguais. Este algoritmo lê quanto custou o jantar e quantas pessoas eram, e mostra quanto paga cada uma.

```text
Escreve: "Quanto custou o jantar, em euros?"
float conta = ler valor
Escreve: "Quantas pessoas eram?"
int pessoas = ler valor
float porPessoa = conta / pessoas
Escreve: "Cada pessoa paga ", porPessoa, " euros"
```

1. Cria um diagrama novo: na barra de menus, escolhe "Ficheiro" e depois "Novo...". A aplicação pode abrir o diagrama novo noutro separador do browser. Se te perguntar que tipo de diagrama queres, escolhe o diagrama em branco. Guarda-o logo, como na parte 2, com o nome `fluxograma-conta-do-jantar.drawio`.
2. Antes de desenhar, conta em papel quantas figuras e quantas setas o fluxograma vai ter, e decide a forma de cada figura. Escreve essa lista: é o que vais comparar com o desenho no fim.
3. Desenha o fluxograma, com as figuras certas, o texto de cada instrução como no pseudocódigo e as setas presas nas duas pontas. Depois verifica-o com a lista da parte 6, adaptada a este algoritmo.
4. Percorre o fluxograma com o dedo para dois jantares e escreve, para cada um, a linha que aparece no ecrã. Primeiro: a conta foi de 48 euros e eram 4 pessoas. Segundo: a conta foi de 50 euros e eram 4 pessoas. Explica numa frase porque é que a conta usa `/` e não `div`.
5. Guarda o `.drawio` e exporta a imagem, com o nome `fluxograma-conta-do-jantar.png`.

Concluíste quando o teu fluxograma tiver uma figura por instrução, mais o início e o fim, com as formas certas, quando os dois jantares do ponto 4 estiverem escritos e quando os dois ficheiros deste fluxograma estiverem guardados na tua pasta.

Se acabares antes do tempo, troca de computador com um colega. Cada um verifica o fluxograma do outro com a lista da parte 6 e diz-lhe se encontrou uma figura a mais, uma a menos, uma forma errada, um texto que diz outra coisa que não o pseudocódigo ou uma seta solta.

## Se alguma coisa correr mal

| O que acontece | O que fazer |
| --- | --- |
| A aplicação aparece em inglês | Abre-a com o endereço `https://app.diagrams.net/?lang=pt` |
| Não vejo a barra de menus, só um botão redondo com reticências no canto superior direito | A janela está estreita: maximiza-a, ou usa esse botão, onde estão "Ficheiro" e "Exportar como" |
| A imagem tem muito espaço vazio à volta do fluxograma | Exporta outra vez com "Tamanho" em "Diagrama", na janela "Imagem" |
| Não encontro o grupo "Fluxograma" | Desce até ao fim do painel da esquerda; se não estiver lá, usa o botão "+ Mais formas" |
| Apaguei ou estraguei alguma coisa | Ctrl+Z, ou Cmd+Z num Mac, desfaz a última ação; repete para desfazer mais |
| A seta não fica presa à figura | Larga o botão do rato só quando a figura de destino ficar com contorno azul |
| O texto não cabe na figura | Seleciona a figura e alarga-a pelos quadradinhos azuis dos cantos |
| O "Guardar como" pede para entrar numa conta | O campo "Onde:" ficou em Google Drive ou noutro serviço: muda para "Aparelho" ou "Descarregar" |
| Guardei no "Navegador" | Faz outra vez "Guardar como" e escolhe "Aparelho" ou "Descarregar" |
| Não sei onde ficou o ficheiro | Com "Descarregar", está na pasta de transferências do computador |
| A grelha de quadrados aparece na página | É só uma ajuda para alinhar, e normalmente não aparece na imagem exportada |

## O que fica guardado no fim

Na tua pasta `algoritmos` tens de ter quatro ficheiros:

- `fluxograma-converter-minutos.drawio` e `fluxograma-converter-minutos.png`;
- `fluxograma-conta-do-jantar.drawio` e `fluxograma-conta-do-jantar.png`.

As imagens são a evidência que entregas, pela forma de entrega que o professor indicar. Os ficheiros `.drawio` guardas tu, porque podes voltar a precisar deles: o laboratório do guia 3, também opcional, acrescenta a figura que ainda falta, o losango das decisões.

![Rodapé](../imagens/rodape.png)
