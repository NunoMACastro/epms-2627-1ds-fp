![Cabeçalho](../imagens/cabecalho.png)

# Do enunciado ao problema delimitado

Módulo Desenvolver algoritmos. Este guia ensina-te a olhar para um enunciado e a transformá-lo num problema bem delimitado, antes de pensares em qualquer solução. Lê-se ao teu ritmo, e não precisa de ser de uma vez. Para praticar, há a [ficha de exercícios](01-do-enunciado-ao-problema-exercicios.md) deste tema.

Serve também para estudares com calma o jogo dos Missionários e Canibais, que se joga na primeira aula da disciplina. Não precisas de saber programar. Nada neste guia exige um computador, e a maior parte do que aqui está faz-se com papel, lápis e atenção. Neste tema, os algoritmos escrevem-se em português, em passos numerados. A notação própria para os escrever é o assunto do tema seguinte.

## Neste guia

1. O que vais aprender
2. O que já sabes e vais usar
3. Programar é dar instruções a quem as cumpre à letra
4. Algoritmo: os passos antes da linguagem
5. Algoritmia e programação
6. Enunciado, problema e solução
7. Dados relevantes e pormenores do contexto
8. Pensamento computacional
9. Ação e estado
10. O contrato de entrada e saída
11. Exemplo guiado: os Missionários e Canibais
12. Erros frequentes
13. Palavras novas deste guia
14. Verificar o que aprendeste
15. O que vem a seguir

## O que vais aprender

No fim deste guia, consegues:

- explicar por palavras tuas o que é um algoritmo e o que distingue a algoritmia da programação;
- ler um enunciado e separar os dados de que precisas dos pormenores que só servem para contar a história;
- escrever o contrato de entrada e saída de um problema, com as entradas, as saídas, as regras e exemplos concretos com o resultado esperado;
- partir um problema grande em partes pequenas, escolher o mínimo de informação que é preciso guardar para o representar e reparar no que se repete;
- encontrar num enunciado a informação que falta ou que se pode ler de duas maneiras, e mostrar o problema com o exemplo mais pequeno possível.

## O que já sabes e vais usar

- Ler com atenção um texto curto, do ensino básico. Neste guia vais ler cada enunciado duas vezes, a segunda com um lápis na mão.
- Fazer contas de dividir com resto, da matemática do ensino básico, como "30 a dividir por 12 dá 2 e sobram 6". Um dos exemplos fala de livros arrumados em caixas, e precisa destas contas.

Se já jogaste os Missionários e Canibais na aula, vais voltar a esse jogo no exemplo guiado. Desta vez vais vê-lo devagar, para perceberes o que fizeste quando o resolveste. Se não jogaste, não faz mal, porque o guia explica-o desde o enunciado.

## Programar é dar instruções a quem as cumpre à letra

Um **programa** é um conjunto de instruções que um computador executa, uma de cada vez, pela ordem em que estão escritas. Chama-se **programar** a escrever essas instruções.

Para perceberes o que isto implica, imagina que tens de explicar a um robô como se faz uma sandes de manteiga. Dizes "põe manteiga no pão". Uma pessoa percebia logo: abria a embalagem, tirava manteiga com uma faca e espalhava-a numa fatia. O robô não percebe nada disso. Pega na embalagem de manteiga fechada e pousa-a em cima do pão, que é exatamente o que lhe disseste. Não fez de propósito para te contrariar. Fez o que estava escrito, porque é a única coisa que sabe fazer.

Um computador é esse robô. Não adivinha intenções, não completa frases a meio e não pensa "ele de certeza queria dizer outra coisa". É muito rápido e nunca se cansa, mas faz à letra o que lhe mandam, incluindo os erros. É por isso que a parte difícil de programar raramente é a linguagem. A parte difícil é saber com toda a precisão o que se quer pedir.

## Algoritmo: os passos antes da linguagem

Usas listas de passos todos os dias, mesmo sem lhes dares um nome. Uma receita de bolo parte de ingredientes, segue passos por ordem e chega a um bolo. As instruções de montagem de um móvel fazem o mesmo. As indicações que dás a alguém para chegar a tua casa também, se forem boas. Todas têm um ponto de partida, passos por uma ordem e um ponto de chegada.

A estas listas de passos chama-se algoritmos. Um **algoritmo** é uma sequência finita de passos, cada um claro e possível de executar, que parte de uns dados e chega a um resultado.

Cada palavra desta definição tem uma razão de estar lá. Vê-as uma a uma:

- "Finita" quer dizer que acaba. Uma lista de passos que nunca termina não resolve nada, porque nunca chega a dar a resposta.
- "Claro" quer dizer que cada passo só se pode ler de uma maneira. Se dois colegas lerem o mesmo passo e fizerem coisas diferentes, o passo não está claro.
- "Possível de executar" quer dizer que quem segue o algoritmo consegue fazer o passo com o que tem. "Adivinha o número que o colega pensou" não é um passo executável.
- "Parte de uns dados e chega a um resultado" quer dizer que o algoritmo tem um ponto de partida e um ponto de chegada. Os dois são bem conhecidos. Mais à frente neste guia vais dar-lhes nomes: entradas e saídas.

Há uma forma simples e honesta de testar se um conjunto de passos é mesmo um algoritmo. Dá-o a outra pessoa, que não sabe o que estás a pensar, e vê se ela chega ao mesmo resultado que tu. Se a pessoa tiver de te perguntar alguma coisa, há um passo que não está claro.

O erro típico de quem começa é escrever passos vagos. "Junta farinha quanto baste", "espera um bocado" e "vira na rua do costume" têm a forma de instruções, mas nenhuma diz exatamente o que fazer. Quanto é "quanto baste"? Quanto tempo é "um bocado"? Qual é "a rua do costume"? Para quem escreveu, a resposta é óbvia, porque a tem na cabeça. Para quem executa, não há resposta nenhuma. Um passo que depende do que está na cabeça de quem o escreveu não é um passo de algoritmo.

Há passos vagos de outra forma, como "levar as pessoas certas para o outro lado" ou "arrumar os livros pelas caixas". Estas frases são o problema inteiro com outras palavras, e não dizem o que fazer. Um passo tem de dizer exatamente o que fazer, de forma que outra pessoa o execute sem te perguntar nada.

## Algoritmia e programação

A **algoritmia** é o trabalho de pensar, escrever e verificar algoritmos. Não depende de nenhuma linguagem de programação. Um algoritmo pode escrever-se em português, em passos numerados, ou numa notação própria, que vais aprender no guia seguinte.

A **programação** é o trabalho de passar um algoritmo para uma linguagem de programação, como C ou Python, que o computador consegue executar. Ao longo deste ano vais aprender as duas coisas, por esta ordem: primeiro algoritmos, depois Python, depois C.

A ordem não é por acaso. Se não sabes que passos resolvem um problema, nenhuma linguagem te ajuda, porque a linguagem só serve para escrever passos que já conheces. Além disso, um erro de raciocínio encontrado no papel custa cinco minutos a corrigir. O mesmo erro, escondido no meio de um programa, pode custar uma tarde. Por isso se diz que primeiro se resolve o problema e só depois se escreve o código.

## Enunciado, problema e solução

Imagina que a professora pede à turma para "organizar os livros da estante da sala". Organizar por ordem alfabética do título? Por tema? Por tamanho, para caberem melhor? Pôr em caixas, porque a turma vai mudar de sala? Enquanto não perceberes qual destas é a pedida, qualquer coisa que faças é um palpite. Podes arrumar a estante na perfeição por ordem alfabética e ter de refazer tudo, porque o que se queria eram caixas para a mudança. Resolver bem o problema errado continua a ser errado.

Para não cair nisto, separam-se três coisas: o enunciado, o problema e a solução. No dia a dia, estas palavras usam-se umas pelas outras, mas cada uma nomeia uma coisa diferente. Confundi-las é a origem de muitos trabalhos bem feitos que resolvem a coisa errada.

O **enunciado** é o texto que te dão: a descrição da situação, escrita por alguém, com a linguagem e os pormenores que essa pessoa escolheu.

O **problema** é o que fica depois de perceberes o que o enunciado pede. Diz de onde se parte, onde se quer chegar e que regras têm de ser respeitadas pelo caminho. O problema não está escrito no enunciado de forma arrumada. És tu que o tens de extrair.

A **solução** é o caminho que leva do ponto de partida ao ponto de chegada, respeitando as regras. Quando esse caminho está escrito em passos claros e finitos, é um algoritmo.

Chama-se **delimitar** um problema a decidir com rigor o que está dentro e o que está fora dele. Decide-se que dados se recebem, que resultado se tem de produzir, que regras se aplicam e que situações não são da nossa conta. É este trabalho que tem de vir primeiro, como mostrou a estante: antes de arrumar, é preciso saber o que se pede.

## Dados relevantes e pormenores do contexto

Os enunciados costumam contar uma pequena história, e uma história tem pormenores. Alguns são dados de que precisas para resolver o problema. Outros existem para tornar o texto agradável de ler e não mudam nada na solução.

Pensa neste enunciado:

> A Rita anda no 10.º ano e gosta de basquetebol. Compra um sumo de 80 cêntimos no bar da escola, em cada um dos 5 dias de aulas da semana. Quer saber quanto gasta por semana.

O nome da Rita, o ano dela e o desporto de que gosta não mudam o que ela gasta. O preço do sumo e o número de dias mudam. Com um sumo mais caro, ou com uma semana de 4 dias de aulas por causa de um feriado, a resposta seria outra.

A pergunta que separou uns pormenores dos outros é esta. Se este pormenor fosse diferente, a resposta mudava? Se muda, é um **dado relevante** e tem de entrar no problema. Se não muda, é **contexto**, e podes deixá-lo de fora.

Há dois erros opostos a evitar. O primeiro é deitar fora uma frase que parece decoração e afinal é uma regra. Vais ver no exemplo guiado dos Missionários e Canibais uma frase curta e discreta que muda o problema inteiro. O segundo é guardar tudo por precaução e depois perder-te no meio de pormenores que não interessam. A pergunta "se isto mudasse, a resposta mudava?" protege-te dos dois.

Às vezes a pergunta revela outra coisa: falta informação. O enunciado não diz uma coisa de que precisas, ou diz de uma forma que se pode ler de duas maneiras. Nesse caso não inventes. Pergunta a quem escreveu o enunciado. Se não for possível, escreve com clareza a decisão que tomaste. Assim, quem ler a tua solução sabe de que decisão ela parte.

## Pensamento computacional

O **pensamento computacional** é uma forma de pensar sobre problemas que torna a solução possível de executar por outra pessoa ou por uma máquina. Costuma apresentar-se em quatro ideias: decomposição, reconhecimento de padrões, abstração e algoritmo. Não se usam por ordem, uma de cada vez, como numa receita. Usam-se em conjunto, e vai-se saltando entre elas enquanto se pensa.

Esta secção usa como exemplo o jogo dos Missionários e Canibais. Se não o conheces, a ideia é esta. Três missionários e três canibais têm de passar um rio num barco pequeno. Numa margem onde haja missionários, os canibais nunca podem ficar em maior número do que eles. É a regra de segurança do jogo. O exemplo guiado, mais à frente neste guia, resolve o jogo do princípio ao fim, com todas as regras.

### Decomposição

**Decompor** é partir um problema grande em partes mais pequenas, cada uma suficientemente simples para se resolver e verificar sozinha.

No dia a dia fazes isto sem dar por isso. Organizar uma festa de anos parece uma tarefa enorme. Partida em "convidados", "comida", "música" e "espaço", cada parte já se consegue pensar. E "comida" ainda se parte em "o que comprar", "quem compra" e "onde se guarda até ao dia".

Nos Missionários e Canibais, "levar toda a gente para o outro lado" é demasiado grande para se pensar de uma vez. Parte-se em "uma travessia de cada vez". Depois, cada travessia parte-se em "escolher quem vai", "verificar se é permitido" e "atualizar quem está em cada margem". O problema passa a ser uma sequência de decisões pequenas.

O erro típico é parar de decompor cedo de mais. Fica uma parte que continua a ser o problema inteiro com outro nome, como "resolver o jogo". O erro contrário também existe: partir em tantos bocados que já não se percebe para que serve cada um. O critério é este. Cada parte tem de se conseguir explicar e verificar sozinha.

### Reconhecimento de padrões

**Reconhecer padrões** é reparar no que se repete, dentro de um problema ou entre problemas diferentes, para resolver uma vez e aproveitar muitas.

Pensa numa soma de números grandes, feita em coluna. Em cada coluna repetes o mesmo processo: somas os algarismos, escreves as unidades e levas o transporte para a coluna seguinte. Não aprendeste um método diferente para as centenas e outro para os milhares. Aprendeste um padrão.

Nos Missionários e Canibais, cada travessia passa pela mesma verificação. Conta-se quem fica em cada margem e vê-se se a regra de segurança se cumpre. Só os números mudam. Reparar nisto significa que só tens de aprender a verificar uma vez.

O erro típico é ver um padrão onde ele não se aplica sempre. Na solução dos Missionários e Canibais, quase todas as idas e voltas seguem o ritmo "vão dois, volta um". Mas há uma que não segue, e vais vê-la no exemplo guiado. Quem confiar no padrão sem verificar cada passo fica bloqueado precisamente aí. Um padrão ajuda a pensar. Não dispensa a verificação.

### Abstração

**Abstrair** é ficar só com o que interessa para a decisão que se está a tomar, e representá-lo da forma mais simples possível.

O mapa do metro é o exemplo clássico. Não mostra as distâncias reais, as ruas por cima, nem as curvas dos túneis. Mostra as estações, a ordem em que aparecem e onde se muda de linha, que é tudo o que precisas para decidir onde sair. Um mapa com todos os pormenores reais seria mais verdadeiro e muito menos útil.

Nos Missionários e Canibais, os nomes das pessoas, a cor do barco e a largura do rio desaparecem. A situação inteira fica descrita com três valores: quantos missionários há na margem esquerda, quantos canibais há nessa margem e onde está o barco. A margem direita não é precisa, porque se deduz da esquerda: há sempre três missionários e três canibais ao todo.

O erro típico é abstrair de mais, e deitar fora uma coisa de que precisas. Se tirares o lado do barco da tua representação, deixas de saber quem pode viajar a seguir. Só pode viajar quem está na margem onde o barco está.

### Algoritmo

Depois de decompor, de reparar nos padrões e de escolher a representação, sobra escrever os passos. É aqui que aparece o algoritmo, tal como foi definido acima. Neste guia, os passos escrevem-se em português, numerados. No guia seguinte vais aprender uma notação própria para os escrever com mais rigor.

## Ação e estado

Os Missionários e Canibais mostram duas ideias que vão acompanhar-te o ano inteiro.

O **estado** é o conjunto de valores que descrevem a situação num dado momento. É uma fotografia: quem está em cada margem e onde está o barco, agora, antes de mais nada acontecer.

Uma **ação** é um passo que muda o estado. Cada travessia é uma ação. Antes dela o estado era um, e depois dela é outro.

O marcador de um jogo de futebol é um bom exemplo do dia a dia. O estado é o resultado e o minuto de jogo. Um golo é uma ação que muda o estado. Se quiseres saber se uma equipa está a ganhar, não precisas de rever o jogo todo. Olhas para o estado.

Verificar uma regra é olhar para o estado. Encontrar um erro é, quase sempre, descobrir em que ação o estado passou a ser diferente do que devia. No guia seguinte, o estado passa a ter nomes próprios, chamados variáveis, e vais aprender a segui-lo ação a ação numa tabela.

## O contrato de entrada e saída

Pensa numa máquina de venda automática. Metes dinheiro e escreves o código de um produto, e a máquina dá-te o produto e o troco. Há regras: só aceita certas moedas, e faz alguma coisa combinada se o código não existir ou se o dinheiro não chegar. Repara que, para usares a máquina, não precisas de saber como ela funciona por dentro. Basta saberes o que lhe dás, o que ela te devolve e que regras cumpre.

Num problema, essa descrição tem um nome. O **contrato de entrada e saída** de um problema é a descrição escrita, antes de haver algoritmo, de quatro coisas:

- as **entradas**: que dados o algoritmo recebe, de que tipo, em que unidade e com que limites. O tipo é a espécie de valor, por exemplo, um número inteiro, um número com casas decimais ou um texto;
- as **saídas**: que resultado o algoritmo produz, e em que forma;
- as **restrições**: as regras que têm de ser respeitadas, sobre as entradas ou sobre o caminho até à saída;
- os **exemplos concretos**: algumas entradas escolhidas com cuidado, cada uma com a saída que se espera, calculada à mão.

A máquina de venda automática tem um contrato destes, mesmo que ninguém o tenha escrito num papel. As entradas são o dinheiro que se mete e o código do produto. As saídas são o produto e o troco. As restrições dizem que moedas aceita e o que acontece se o código não existir ou se o dinheiro não chegar.

Chama-se contrato porque funciona como um acordo entre duas partes. Quem usa o algoritmo compromete-se a dar entradas dentro dos limites combinados. O algoritmo compromete-se a devolver a saída prometida. Pode acontecer alguém dar uma entrada fora do combinado. Nesse caso, o contrato ou diz o que acontece, ou deixa claro que esse caso não está coberto.

Na máquina, o contrato basta para a usares. É essa a grande vantagem de um contrato bem escrito: separa o que o algoritmo faz de como o faz.

### Um contrato completo: livros em caixas

Imagina este enunciado:

> A biblioteca da escola vai mudar de sala e quer arrumar os livros em caixas. Cada caixa leva no máximo 12 livros. A biblioteca quer saber de quantas caixas vai precisar e quantos livros vão ficar na última caixa.

O contrato escreve-se assim.

As entradas são duas:

- o número de livros, um número inteiro igual ou maior do que zero;
- a capacidade de cada caixa, medida em número de livros, um número inteiro maior do que zero.

O enunciado diz 12 livros, mas a capacidade fica como entrada, e não como um número fixo. Assim, o mesmo algoritmo serve para caixas de outro tamanho. Repara também que a capacidade não pode ser zero. Uma caixa onde não cabe nenhum livro não serve para nada, e o contrato deixa isso claro logo à partida.

As saídas também são duas: o número de caixas necessárias e o número de livros que vão na última caixa.

As restrições são as regras do enunciado, escritas com rigor:

- nenhuma caixa leva mais livros do que a capacidade;
- todos os livros ficam dentro de uma caixa;
- não se usam caixas vazias.

Os exemplos concretos calculam-se à mão, sem algoritmo nenhum, e escolhem-se de propósito para cobrir situações diferentes. Antes de leres a tabela, calcula tu as duas saídas para 30, 24, 5 e 0 livros, com caixas de 12. Depois confirma com a tabela.

| Livros | Capacidade | Caixas | Livros na última caixa | Porque é que este caso foi escolhido |
| ---: | ---: | ---: | --- | --- |
| 30 | 12 | 3 | 6 | Caso normal: duas caixas cheias e uma incompleta |
| 24 | 12 | 2 | 12 | A divisão é exata e a última caixa fica cheia |
| 5 | 12 | 1 | 5 | Há menos livros do que cabem numa caixa |
| 0 | 12 | 0 | não há última caixa | Quantidade nula: não há nada para arrumar |

Cada linha ensina uma coisa diferente.

A primeira linha é o **caso normal**, o que qualquer pessoa imagina ao ler o enunciado. Com 30 livros enchem-se duas caixas de 12, que levam 24, e sobram 6 livros. Esses 6 também têm de ir numa caixa, porque a restrição diz que todos os livros ficam dentro de uma caixa. São portanto 3 caixas, e a última leva 6.

A segunda linha mostra que a última caixa pode estar cheia. É um **caso no limite de uma regra**, porque fica exatamente em cima do limite que a regra põe. As duas caixas levam 12 livros cada, nem mais um. Quem só pensou no primeiro caso pode ter ficado com a ideia de que a última caixa está sempre incompleta. Este exemplo desfaz essa ideia antes de ela chegar ao algoritmo.

A terceira linha é o caso em que nem uma caixa se enche. A resposta é uma caixa com 5 livros, e não zero caixas, porque os 5 livros têm de ir para algum lado.

A quarta linha obriga a tomar uma decisão que o enunciado não tomou. Com zero livros não é preciso nenhuma caixa, e por isso não há última caixa. Quantos livros vão "na última caixa" quando ela não existe? O enunciado não responde. O contrato tem de responder, e aqui a decisão foi dizer por palavras que não há última caixa. Podia ter sido outra, desde que ficasse escrita. O que não pode acontecer é ninguém ter pensado nisso e o algoritmo fazer uma coisa qualquer quando aparecer o zero.

As duas últimas linhas ficam nas pontas do problema: muito poucos livros, menos do que cabem numa caixa, e nenhum livro. Um caso nas pontas do problema chama-se **caso extremo**. Pode ser o zero, o muito pouco, ou um valor que uma regra não deixa passar, como uma caixa de capacidade zero. Os casos extremos são os que costumam obrigar a decisões que o enunciado não tomou.

Estes exemplos servem para duas coisas. Antes de escrever o algoritmo, mostram se percebeste o problema. Se não conseguires calcular à mão o resultado de um exemplo, ainda não o percebeste. Depois de escrever o algoritmo, servem de teste. O algoritmo tem de dar exatamente estes resultados, e se não der, está errado.

## Exemplo guiado: os Missionários e Canibais

Vais agora aplicar tudo o que viste ao jogo dos Missionários e Canibais, do enunciado até à solução completa, passo a passo.

Para seguires este exemplo, ajuda ter seis objetos pequenos de dois tipos, como três clipes e três tampas de caneta. Junta-lhes uma folha com um rio desenhado ao meio. Mexer nos objetos enquanto lês torna o exemplo mais fácil de seguir.

### O enunciado

Esta versão tem pormenores a mais de propósito, para praticares a separação entre dados e contexto:

> Numa manhã de verão, três missionários e três canibais chegam à margem esquerda de um rio largo, de águas castanhas e corrente fraca. Querem todos passar para a margem direita. Encontram um pequeno barco de madeira, pintado de vermelho, com dois remos. O barco leva no máximo duas pessoas e não atravessa o rio sozinho. Há um perigo. Se, em alguma das margens, os canibais ficarem em maior número do que os missionários, os missionários são atacados e o jogo está perdido. Como é que os seis chegam todos à margem direita?

### Passo 1: ler duas vezes

A primeira leitura serve para perceber a história. Há pessoas de um lado, querem ir para o outro, há um barco pequeno e há um perigo. A segunda leitura faz-se com lápis na mão, a sublinhar tudo o que parece um número, um limite ou uma regra. Não saltes a segunda leitura. É nela que se encontram as frases curtas que mudam tudo.

### Passo 2: separar dados de contexto

Para cada pormenor, faz a pergunta "se isto fosse diferente, a resposta mudava?":

| Pormenor do enunciado | É um dado? | Porquê |
| --- | --- | --- |
| "Numa manhã de verão" | Não | De noite ou no inverno, as travessias seriam as mesmas |
| "três missionários e três canibais" | Sim | Com outras quantidades o problema muda. Com quatro e quatro, por exemplo, deixa de ter solução com este barco |
| "margem esquerda" e "margem direita" | Sim | Dizem de onde se parte e onde se quer chegar |
| "rio largo, de águas castanhas e corrente fraca" | Não | Nada disto muda quem pode viajar com quem |
| "barco de madeira, pintado de vermelho, com dois remos" | Não | A cor, o material e os remos não mudam as travessias |
| "leva no máximo duas pessoas" | Sim | Limita cada travessia a uma ou duas pessoas |
| "não atravessa o rio sozinho" | Sim | Obriga a que alguém traga o barco de volta sempre que é preciso |
| "se os canibais ficarem em maior número do que os missionários" | Sim | É a regra que decide se uma travessia é permitida |

A frase "não atravessa o rio sozinho" é a frase curta e discreta de que se falou na secção dos dados relevantes. Parece um pormenor, e é ela que obriga a que haja viagens de regresso com alguém dentro. Sem ela, o barco podia voltar vazio, e bastavam três viagens com pessoas, todas da esquerda para a direita.

Lê também com cuidado a regra de segurança. Ela fala de os missionários serem atacados. Numa margem onde não há nenhum missionário, não há ninguém para atacar. Por isso, dois canibais sozinhos numa margem não fazem perder o jogo. Só há perigo numa margem onde haja pelo menos um missionário e mais canibais do que missionários.

### Passo 3: procurar o que falta ou se pode ler de duas maneiras

O enunciado não diz uma coisa importante. Quem está dentro do barco conta para alguma das margens? Imagina que o barco chega à margem direita com um canibal. Esse canibal conta como estando na margem direita, ou fica "no barco" e não conta?

As duas leituras são possíveis, e podem dar respostas diferentes. Não se inventa em silêncio. Toma-se uma decisão e escreve-se. A regra usada nas aulas é esta. Quem está no barco conta na margem onde o barco está.

Vê o que isto quer dizer em cada momento de uma travessia:

- Enquanto o barco está encostado à margem esquerda, quem já entrou nele continua a contar na margem esquerda. Entrar no barco não é sair da margem.
- Quando o barco chega à margem direita, quem vai nele passa a contar na margem direita, quer saia do barco quer fique lá dentro. Ficar sentado no barco não protege ninguém.

Voltando ao exemplo, o canibal que chega à margem direita conta como estando na margem direita, mesmo que não ponha um pé em terra.

Esta regra tem uma consequência útil. Entrar no barco não muda as contas de nenhuma margem, porque quem entra continua a contar na margem de onde vai partir. As contas só mudam quando o barco muda de lado. Por isso chega verificar a regra de segurança depois de cada travessia, e é isso que se faz daqui em diante.

Há mais duas perguntas que se respondem com o próprio enunciado. O barco pode levar uma só pessoa? Pode, porque "no máximo duas" inclui uma. O barco pode atravessar vazio? Não, porque não atravessa sozinho.

### Passo 4: escrever o contrato

A entrada é a situação inicial: três missionários e três canibais na margem esquerda, ninguém na margem direita e o barco na margem esquerda.

A saída é uma lista de travessias. Cada travessia diz quem vai no barco e em que sentido, e a lista termina com as seis pessoas na margem direita.

As restrições são as regras do jogo, escritas com rigor:

1. em cada travessia vão uma ou duas pessoas no barco;
2. o barco só parte da margem onde está, e por isso as travessias alternam de sentido;
3. depois de cada travessia, em nenhuma margem onde haja pelo menos um missionário pode haver mais canibais do que missionários. Quem está no barco conta na margem onde o barco está.

Como exemplos concretos, num jogo destes faz sentido verificar à mão uma ou duas jogadas antes de tentar a solução toda. Levar dois canibais na primeira travessia é permitido. A margem esquerda fica com 3 missionários e 1 canibal, e a direita com 2 canibais e nenhum missionário. Ninguém corre perigo. Levar dois missionários na primeira travessia não é permitido. A margem esquerda fica com 1 missionário e 3 canibais, e a regra falha.

Repara numa diferença em relação ao exemplo dos livros. Num jogo como este, a entrada é sempre a mesma, porque o jogo começa sempre da mesma maneira. Na maior parte dos problemas desta disciplina, a entrada muda de cada vez que o algoritmo é usado, como o número de livros da biblioteca. É por isso que os exemplos concretos do contrato vão ganhar tanta importância.

### Passo 5: abstrair, representando a situação com números

Para acompanhar o jogo, não precisas de desenhar o rio. Chega uma representação com três valores: quantos missionários estão na margem esquerda, quantos canibais estão na margem esquerda e de que lado está o barco. A situação inicial escreve-se (3, 3, esquerda), e o objetivo escreve-se (0, 0, direita).

Estes três valores são o estado do jogo, a fotografia de que se falou na secção "Ação e estado". Cada travessia é uma ação que muda o estado. Por exemplo, levar dois canibais a partir do início muda o estado de (3, 3, esquerda) para (3, 1, direita).

Porque é que não se escreve também a margem direita? Porque se deduz. Há sempre três missionários ao todo, e por isso os que estão na direita são 3 menos os que estão na esquerda. O mesmo para os canibais. Guardar os dois lados seria guardar a mesma informação duas vezes. E isso abre a porta a um erro chato, como escrever 3 missionários na esquerda e 1 na direita. Dava 4 missionários, que não existem. Uma boa representação guarda o mínimo necessário, e com isso torna alguns erros impossíveis.

Nas tabelas deste guia vais ver as duas margens escritas, porque é mais fácil verificar a regra de segurança com os números à frente. Mas a direita é sempre calculada a partir da esquerda.

### Passo 6: decompor numa travessia de cada vez

O problema grande é "chegar de (3, 3, esquerda) a (0, 0, direita)". Decompõe-se numa sequência de travessias, e cada travessia decompõe-se nesta lista. Para não se confundir com os passos do exemplo guiado, cada linha da lista tem uma letra, e chama-se alínea.

- a) Ver em que margem está o barco.
- b) Escolher quem vai no barco, entre as hipóteses que ainda não experimentaste nesta travessia. São cinco: um missionário, dois missionários, um canibal, dois canibais, ou um missionário e um canibal. Se já experimentaste as cinco e nenhuma serviu, a travessia anterior foi uma má escolha: desfá-la e volta à alínea b) dessa travessia.
- c) Confirmar que essas pessoas estão mesmo na margem onde está o barco. Se não estiverem, voltar à alínea b) com outra hipótese.
- d) Calcular a nova situação: tirar essas pessoas da margem de partida, pô-las na margem de chegada e mudar o barco de lado.
- e) Verificar a regra de segurança nas duas margens.
- f) Se a regra falhar, desfazer a travessia e voltar à alínea b) com outra hipótese.
- g) Se a regra se cumprir, confirmar que a nova situação não é uma que já aconteceu antes. Se for, desfazer a travessia e voltar à alínea b) com outra hipótese, porque regressar a uma situação conhecida é andar para trás.
- h) Se a nova situação for (0, 0, direita), o jogo está resolvido. Se não for, volta-se à alínea a) para a travessia seguinte.

A alínea g) desta lista merece uma explicação. Sem ela, podias passar a tarde a levar um canibal para a direita e a trazê-lo de volta. Estavas sempre dentro das regras, e nunca avançavas. Recusar situações repetidas é o que garante que o processo acaba.

A última frase da alínea b) trata o caso em que uma travessia não deixa avançar. Volta-se atrás e experimenta-se outra. A alínea h) manda voltar ao início e fazer tudo outra vez para a travessia seguinte. Fazer os mesmos passos várias vezes chama-se **repetição**, e vai ter uma forma própria de se escrever no tema 04, Repetição e arrays. Por agora, basta dizê-lo em português com clareza, como está acima.

### Passo 7: reconhecer o padrão da verificação

As alíneas a) a h) da lista do passo 6 são iguais em todas as travessias. Só mudam os números. É o padrão de que se falou na secção "Reconhecimento de padrões". Aprendes a verificar uma travessia e sabes verificar todas.

Vê o padrão a funcionar logo na primeira travessia, experimentando as cinco hipóteses a partir de (3, 3, esquerda). Antes de leres a tabela, experimenta-as tu, com os objetos ou numa folha. Quais são permitidas?

| Quem vai | Margem esquerda fica com | Margem direita fica com | A regra cumpre-se? |
| --- | --- | --- | --- |
| 1 missionário | 2 missionários e 3 canibais | 1 missionário | Não: na esquerda, 3 canibais contra 2 missionários |
| 2 missionários | 1 missionário e 3 canibais | 2 missionários | Não: na esquerda, 3 canibais contra 1 missionário |
| 1 canibal | 3 missionários e 2 canibais | 1 canibal | Sim |
| 2 canibais | 3 missionários e 1 canibal | 2 canibais | Sim |
| 1 missionário e 1 canibal | 2 missionários e 2 canibais | 1 missionário e 1 canibal | Sim |

Das cinco hipóteses, duas falham logo. As outras três são permitidas. Começar com 1 canibal é permitido, mas só deixa voltar ao início. Na margem direita fica só esse canibal, e é ele que tem de trazer o barco de volta. Voltar ao início é regressar a uma situação conhecida, e a alínea g) da lista do passo 6 recusa-o. Como nenhuma outra hipótese serve, a alínea b) manda desfazer a primeira travessia e experimentar outra. A solução que se segue começa com dois canibais, mas começar com um missionário e um canibal também leva a uma solução.

### Passo 8: simular até ao fim

Esta é a solução completa. Cada linha é o estado depois de uma travessia. A coluna da direita mostra a verificação da regra, feita em todas as linhas e não só nas que parecem perigosas. Na tabela, M quer dizer missionários e C quer dizer canibais.

| Travessia | Quem vai no barco | Sentido | Margem esquerda | Margem direita | A regra cumpre-se? |
| ---: | --- | --- | --- | --- | --- |
| início | ninguém | o barco está na esquerda | 3 M, 3 C | 0 M, 0 C | Sim |
| 1 | 2 canibais | esquerda → direita | 3 M, 1 C | 0 M, 2 C | Sim: na direita não há missionários |
| 2 | 1 canibal | direita → esquerda | 3 M, 2 C | 0 M, 1 C | Sim |
| 3 | 2 canibais | esquerda → direita | 3 M, 0 C | 0 M, 3 C | Sim: na direita não há missionários |
| 4 | 1 canibal | direita → esquerda | 3 M, 1 C | 0 M, 2 C | Sim |
| 5 | 2 missionários | esquerda → direita | 1 M, 1 C | 2 M, 2 C | Sim: empates são permitidos |
| 6 | 1 missionário e 1 canibal | direita → esquerda | 2 M, 2 C | 1 M, 1 C | Sim |
| 7 | 2 missionários | esquerda → direita | 0 M, 2 C | 3 M, 1 C | Sim: na esquerda não há missionários |
| 8 | 1 canibal | direita → esquerda | 0 M, 3 C | 3 M, 0 C | Sim |
| 9 | 2 canibais | esquerda → direita | 0 M, 1 C | 3 M, 2 C | Sim |
| 10 | 1 canibal | direita → esquerda | 0 M, 2 C | 3 M, 1 C | Sim |
| 11 | 2 canibais | esquerda → direita | 0 M, 0 C | 3 M, 3 C | Sim, e é o objetivo |

A travessia 6 é o momento mais difícil do jogo, e é onde muita gente fica presa na aula. Depois da travessia 5, o barco está na margem direita, que tem 2 missionários e 2 canibais. A esquerda tem 1 missionário e 1 canibal. Alguém tem de levar o barco de volta. Antes de leres a explicação, experimenta tu as cinco hipóteses, com os objetos, e tenta perceber porque é que quatro delas não servem. Depois confirma com a lista, uma hipótese de cada vez, com o padrão da verificação:

- Se voltar 1 missionário, a direita fica com 1 missionário e 2 canibais. A regra falha.
- Se voltarem 2 missionários, a situação passa a ser a mesma que havia depois da travessia 4. É permitido, mas é andar para trás, e a alínea g) da lista do passo 6 recusa-o.
- Se voltar 1 canibal, a esquerda fica com 1 missionário e 2 canibais. A regra falha.
- Se voltarem 2 canibais, a esquerda fica com 1 missionário e 3 canibais. A regra falha.
- Se voltarem 1 missionário e 1 canibal, a esquerda fica com 2 e 2 e a direita com 1 e 1. A regra cumpre-se e a situação é nova.

Só uma hipótese faz avançar, e é a menos intuitiva de todas, porque leva de volta um missionário que tinha acabado de atravessar. É também aqui que o padrão "vão dois, volta um" deixa de funcionar. Nas travessias 5 e 6 vão dois e voltam dois. Quem seguisse o padrão sem verificar não encontrava esta saída.

Não há nenhuma solução com menos de 11 travessias. Há quatro sequências diferentes com 11 travessias, e só diferem nas duas primeiras e nas duas últimas. Qualquer uma delas é uma solução correta, porque todas cumprem o contrato. Quem seguir a lista do passo 6 à letra, com as hipóteses pela ordem da alínea b), chega a outra destas quatro soluções. Essa acaba com 1 missionário e depois 1 missionário e 1 canibal, e está igualmente certa.

### Passo 9: confirmar a solução contra o contrato

Uma solução não está terminada quando chega ao fim. Está terminada quando se verificou que cumpre o contrato. Para esta, confirma-se o seguinte:

- em todas as travessias vão uma ou duas pessoas;
- os sentidos alternam, a começar na esquerda, e por isso o barco parte sempre da margem onde está;
- em todas as linhas da tabela a regra de segurança se cumpre, nas duas margens;
- a última linha é (0, 0, direita), com toda a gente na margem direita;
- em todas as linhas há 3 missionários e 3 canibais ao todo, somando as duas margens.

Esta última verificação não vem do enunciado e é na mesma muito útil. Se numa linha a soma desse 5 ou 7, terias a certeza de que houve um erro de contas nessa travessia. E sabias isso mesmo antes de verificares a regra. Procurar coisas que têm de se manter sempre iguais é uma forma rápida de apanhar erros, e vais usá-la muitas vezes.

## Erros frequentes

Estes são os erros que mais aparecem neste tema. Para cada um, vês como se reconhece, porque acontece e como se corrige. O erro típico de cada ideia, como os passos vagos, parar de decompor cedo de mais ou abstrair de mais, ficou na secção dessa ideia.

### Unidade de medida ambígua

Imagina que o enunciado dos livros dizia "cada caixa leva no máximo 10" em vez de "12 livros". Dez quê? Dez livros, ou dez quilos? Se forem dez livros, 30 livros precisam de 3 caixas. Se forem dez quilos e cada livro pesar meio quilo, cabem 20 livros por caixa e 30 livros precisam só de 2 caixas. O mesmo enunciado dá duas respostas diferentes, conforme a unidade que se imagina.

Pior ainda: se for em quilos, o enunciado não diz quanto pesa cada livro. Falta informação, e sem ela nenhuma conta resolve o problema.

Acontece porque quem escreve o enunciado tem a unidade na cabeça e não a escreve. Como se evita: no contrato, cada entrada leva a sua unidade escrita por extenso, como "capacidade da caixa, em número de livros". Quando o enunciado não diz a unidade, não se escolhe uma em silêncio. Pergunta-se, ou escreve-se a decisão.

### Etapa omitida

Uma etapa omitida é um passo que falta no algoritmo. Não se nota enquanto se testa só o caso que se tinha em mente.

Nos Missionários e Canibais, a etapa que costuma faltar é o regresso do barco. Quem escreve "1. levar dois canibais; 2. levar dois canibais; 3. levar dois missionários" esqueceu-se de que o barco não volta sozinho. A tabela da simulação denuncia o erro de imediato. Depois da primeira travessia, o barco está na direita, e a segunda travessia diz "esquerda → direita", o que é impossível.

Nos livros, a etapa que costuma faltar é a caixa incompleta. Quem escreve "dividir os livros pela capacidade e ficar com a parte inteira" obtém 2 caixas para 30 livros. Os 6 que sobram ficam no chão. Com 24 livros, esse passo dá a resposta certa. É por isso que o erro passa despercebido a quem só experimenta divisões exatas.

Para corrigir, simula o algoritmo numa tabela com os exemplos do contrato, incluindo os casos extremos. Depois reproduz a falha com um exemplo mínimo, como se explica a seguir.

### Reproduzir a falha com um exemplo mínimo

Quando se descobre um erro, o passo seguinte é encontrar o **exemplo mínimo** que o reproduz. O exemplo mínimo é a entrada mais pequena e simples que ainda mostra a falha.

No caso da caixa incompleta, 30 livros mostram o erro, mas obrigam a fazer contas. 13 livros também mostram: dá 1 caixa e fica 1 livro de fora. E 1 livro mostra ainda melhor. O passo errado dá 0 caixas para 1 livro, o que é evidentemente absurdo. Com o exemplo mínimo, a causa salta à vista. Depois de corrigires o algoritmo, é o primeiro caso que voltas a experimentar, porque é o mais rápido de verificar.

Nos Missionários e Canibais, o exemplo mínimo do regresso esquecido são só duas travessias seguidas no mesmo sentido. Não é preciso simular o jogo inteiro para mostrar o erro.

### Começar a resolver antes de acabar de ler

É o erro mais comum de todos, e explica muitos dos outros. Vê-se quando a solução não usa uma regra do enunciado. Quem lê a primeira frase dos Missionários e Canibais e começa logo a mexer no barco não repara em "não atravessa sozinho". Também não repara que a regra de segurança só vale nas margens onde há missionários. Acontece porque a primeira leitura só apanha a história. O remédio está no exemplo guiado, na secção "Passo 1: ler duas vezes": ler o enunciado duas vezes, a segunda com lápis.

### Esquecer os casos extremos no contrato

Um contrato só com o caso normal, como os 30 livros, parece completo e não está. Os casos extremos, como zero livros ou menos livros do que cabem numa caixa, são os que obrigam a decisões que o enunciado não tomou. Se não aparecerem no contrato, vão aparecer mais tarde. Nessa altura o algoritmo já está escrito, e é mais caro corrigir. Para que não aconteça, pergunta sempre "e se for zero?" e "e se for muito pouco?" antes de dares o contrato por terminado.

## Palavras novas deste guia

- Programa: um conjunto de instruções que um computador executa, uma de cada vez, pela ordem em que estão escritas.
- Programar: escrever as instruções de um programa.
- Algoritmo: uma sequência finita de passos, cada um claro e possível de executar, que parte de uns dados e chega a um resultado.
- Algoritmia: o trabalho de pensar, escrever e verificar algoritmos.
- Programação: o trabalho de passar um algoritmo para uma linguagem de programação, que o computador consegue executar.
- Enunciado: o texto que te dão, com a descrição da situação.
- Problema: o que o enunciado pede, depois de o perceberes: de onde se parte, onde se quer chegar e que regras se respeitam.
- Solução: o caminho que leva do ponto de partida ao ponto de chegada, respeitando as regras.
- Delimitar um problema: decidir com rigor o que está dentro e o que está fora dele.
- Dado relevante: um pormenor do enunciado que, se fosse diferente, mudava a resposta.
- Contexto: um pormenor do enunciado que não muda a resposta.
- Pensamento computacional: uma forma de pensar sobre problemas que torna a solução possível de executar por outra pessoa ou por uma máquina.
- Decompor: partir um problema grande em partes mais pequenas, que se resolvem e verificam sozinhas.
- Reconhecer padrões: reparar no que se repete, para resolver uma vez e aproveitar muitas.
- Abstrair: ficar só com o que interessa para a decisão e representá-lo da forma mais simples possível.
- Estado: o conjunto de valores que descrevem a situação num dado momento, como uma fotografia.
- Ação: um passo que muda o estado.
- Contrato de entrada e saída: as entradas, as saídas, as restrições e os exemplos concretos de um problema, escritos antes de haver algoritmo.
- Entradas: os dados que o algoritmo recebe, com o tipo, a unidade e os limites. O tipo é a espécie de valor, como um número inteiro, um número com casas decimais ou um texto.
- Saídas: o resultado que o algoritmo produz.
- Restrições: as regras que têm de ser respeitadas, sobre as entradas ou sobre o caminho até à saída.
- Exemplos concretos: entradas escolhidas com cuidado, cada uma com a saída esperada, calculada à mão.
- Caso normal: o caso que qualquer pessoa imagina ao ler o enunciado.
- Caso no limite de uma regra: um caso exatamente em cima do limite que uma regra põe, como a caixa com 12 livros.
- Caso extremo: um caso nas pontas do problema, como o zero, o muito pouco ou um valor que uma regra não deixa passar.
- Repetição: fazer os mesmos passos várias vezes.
- Etapa omitida: um passo que falta no algoritmo e que não se nota enquanto se testa só o caso que se tinha em mente.
- Exemplo mínimo: a entrada mais pequena e simples que ainda mostra uma falha.

## Verificar o que aprendeste

Responde sem olhar para o guia. Se não conseguires responder a uma pergunta, volta à secção dela.

1. Qual é a diferença entre algoritmia e programação? Explica-a como se fosse a um colega que faltou à aula, com um exemplo teu que não esteja neste guia.
2. O que distingue um enunciado de um problema? O que quer dizer delimitar um problema?
3. Pega num enunciado que não esteja neste guia, por exemplo de um problema de matemática, e sublinha os pormenores. Para cada um, diz se é um dado ou contexto. Justifica com a pergunta "se isto mudasse, a resposta mudava?".
4. Escreve o contrato de um problema teu, com entradas, saídas, restrições e pelo menos três exemplos concretos. Um dos exemplos tem de ser um caso extremo.
5. No problema dos livros, quantas caixas são precisas para 25 livros em caixas de 8? Quantos livros vão na última caixa? Explica cada passo da conta.
6. Dá um exemplo teu de decomposição, outro de reconhecimento de padrões e outro de abstração.
7. Porque é que a representação (3, 3, esquerda) chega para descrever o jogo? O que se perdia se tirasses o lado do barco?
8. Refaz numa folha a simulação dos Missionários e Canibais, sem olhar para a tabela. Verifica a regra em cada travessia.
9. Porque é que, na travessia 6, a única escolha que faz avançar é levar de volta um missionário e um canibal?
10. Pensa num enunciado ambíguo, teu ou de um exercício que já fizeste. Que informação falta? Qual é o exemplo mais pequeno em que as duas leituras dão resultados diferentes?

## O que vem a seguir

Para praticar este tema, faz a [ficha de exercícios](01-do-enunciado-ao-problema-exercicios.md). Tem cinco exercícios, do mais simples ao mais completo, e um desafio opcional com os Missionários e Canibais. O tema seguinte é [Estado, sequência e representações](02-estado-sequencia-representacoes.md).

No tema seguinte vais aprender a escrever algoritmos numa notação própria, chamada pseudocódigo. O estado dos Missionários e Canibais, que aqui eram três valores escritos numa tabela, passa a ter nomes próprios, chamados variáveis. Vais aprender a segui-lo passo a passo numa tabela de trace. O contrato continua a ser o primeiro passo de todos os problemas. Antes de escrever uma única instrução, vais sempre escrever as entradas, as saídas, as restrições e os exemplos.

![Rodapé](../imagens/rodape.png)
