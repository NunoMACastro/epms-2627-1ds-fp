![Cabeçalho](../imagens/cabecalho.png)

# Do enunciado ao problema delimitado

| Identificação | Valor |
| --- | --- |
| Disciplina | Fundamentos de Programação, 10.º ano, Desenvolvimento de Software |
| Unidade de competência | UC00245, Desenvolver algoritmos |
| Percurso | Algoritmos, primeiro guia |

## O que vais aprender

Este guia é para estudares com calma o que se fez na primeira aula da disciplina, quando jogaste os Missionários e Canibais, e o que se faz a seguir: aprender a olhar para um enunciado e a transformá-lo num problema bem delimitado, antes de pensar em qualquer solução.

No fim deves conseguir:

- explicar por palavras tuas o que é um algoritmo e o que distingue algoritmia de programação;
- ler um enunciado e separar os dados de que precisas dos pormenores que só servem para contar a história;
- escrever o contrato de entrada e saída de um problema, com entradas, saídas, regras e exemplos concretos com o resultado esperado;
- partir um problema grande em partes pequenas, escolher o mínimo de informação que é preciso guardar para o representar e reparar no que se repete;
- encontrar num enunciado a informação que falta ou que se pode ler de duas maneiras, e mostrar o problema com o exemplo mais pequeno possível.

## O que já sabes e vais usar

Não precisas de saber programar. Nada neste guia exige um computador, e a maior parte do que aqui está faz-se com papel, lápis e atenção.

Vais precisar de três coisas que já tens. A primeira é o jogo dos Missionários e Canibais, que resolveste na aula: vais voltar a ele, desta vez devagar, para perceberes o que fizeste quando o resolveste. A segunda é saber fazer contas de dividir com resto, como "30 a dividir por 12 dá 2 e sobram 6", porque um dos exemplos fala de livros arrumados em caixas. A terceira é a paciência de ler um texto duas vezes, com atenção, antes de fazer seja o que for.

## Programar é dar instruções a quem as cumpre à letra

Um **programa** é um conjunto de instruções que um computador executa, uma de cada vez, pela ordem em que estão escritas. **Programar** é escrever essas instruções.

Para perceberes o que isto implica, imagina que tens de explicar a um robô como se faz uma sandes de manteiga. Dizes "põe manteiga no pão". Uma pessoa percebia logo: abria a embalagem, tirava manteiga com uma faca e espalhava-a numa fatia. O robô não percebe nada disso. Pega na embalagem de manteiga fechada e pousa-a em cima do pão, que é exatamente o que lhe disseste. Não fez de propósito para te contrariar. Fez o que estava escrito, porque é a única coisa que sabe fazer.

Um computador é esse robô. Não adivinha intenções, não completa frases a meio, não pensa "ele de certeza queria dizer outra coisa". É muito rápido e nunca se cansa, mas faz à letra o que lhe mandam, incluindo os erros. É por isso que a parte difícil de programar raramente é a linguagem. A parte difícil é saber com toda a precisão o que se quer pedir.

## Algoritmo: os passos antes da linguagem

Um **algoritmo** é uma sequência finita de passos, cada um claro e possível de executar, que parte de uns dados e chega a um resultado.

Cada palavra desta definição tem uma razão de estar lá, e vale a pena vê-las uma a uma:

- "Finita" quer dizer que acaba. Uma lista de passos que nunca termina não resolve nada, porque nunca chega a dar a resposta.
- "Claro" quer dizer que cada passo só se pode ler de uma maneira. Se dois colegas lerem o mesmo passo e fizerem coisas diferentes, o passo não está claro.
- "Possível de executar" quer dizer que quem segue o algoritmo consegue fazer o passo com o que tem. "Adivinha o número que o colega pensou" não é um passo executável.
- "Parte de uns dados e chega a um resultado" quer dizer que o algoritmo tem um ponto de partida e um ponto de chegada bem conhecidos. Mais à frente neste guia vais dar-lhes nomes: entradas e saídas.

Usas algoritmos todos os dias sem lhes chamar isso. Uma receita de bolo é um algoritmo: parte de ingredientes, segue passos por ordem e chega a um bolo. As instruções de montagem de um móvel são um algoritmo. As indicações que dás a alguém para chegar a tua casa também são, se forem boas.

A forma mais honesta de testar se um conjunto de passos é mesmo um algoritmo é dá-lo a outra pessoa, que não sabe o que estás a pensar, e ver se ela chega ao mesmo resultado que tu. Se a pessoa tiver de te perguntar alguma coisa, há um passo que não está claro.

O erro típico de quem começa é escrever passos vagos. "Junta farinha quanto baste", "espera um bocado", "vira na rua do costume" parecem instruções e não são. Quanto é "quanto baste"? Quanto tempo é "um bocado"? Qual é "a rua do costume"? Para quem escreveu, a resposta é óbvia, porque a tem na cabeça. Para quem executa, não há resposta nenhuma. Um passo que depende do que está na cabeça de quem o escreveu não é um passo de algoritmo.

## Algoritmia e programação

A **algoritmia** é o trabalho de pensar, escrever e verificar algoritmos. Não depende de nenhuma linguagem de programação: um algoritmo escreve-se em português, em passos numerados, em desenhos com setas ou numa notação própria que vais aprender no guia seguinte.

A **programação** é o trabalho de passar um algoritmo para uma linguagem de programação, como C ou Python, que o computador consegue executar. Ao longo deste ano vais aprender as duas coisas, por esta ordem: primeiro algoritmos, depois C, depois Python.

A ordem não é por acaso. Se não sabes que passos resolvem um problema, nenhuma linguagem te ajuda, porque a linguagem só serve para escrever passos que já conheces. E um erro de raciocínio encontrado no papel custa cinco minutos a corrigir, enquanto o mesmo erro escondido no meio de um programa pode custar uma tarde. Por isso se diz que primeiro se resolve o problema e só depois se escreve o código.

## Enunciado, problema e solução

Estas três palavras parecem sinónimas e não são. Confundi-las é a origem de muitos trabalhos bem feitos que resolvem a coisa errada.

O **enunciado** é o texto que te dão: a descrição da situação, escrita por alguém, com a linguagem e os pormenores que essa pessoa escolheu.

O **problema** é o que fica depois de perceberes o que o enunciado pede: de onde se parte, onde se quer chegar e que regras têm de ser respeitadas pelo caminho. O problema não está escrito no enunciado de forma arrumada. És tu que o tens de extrair.

A **solução** é o caminho que leva do ponto de partida ao ponto de chegada respeitando as regras. Quando esse caminho está escrito em passos claros e finitos, é um algoritmo.

**Delimitar** um problema é decidir com rigor o que está dentro e o que está fora dele: que dados se recebem, que resultado se tem de produzir, que regras se aplicam e que situações não são da nossa conta.

Um exemplo do dia a dia mostra porque é que este trabalho vem primeiro. A professora pede à turma para "organizar os livros da estante da sala". Organizar por ordem alfabética do título? Por tema? Por tamanho, para caberem melhor? Pôr em caixas, porque a turma vai mudar de sala? Enquanto não perceberes qual destas é a pedida, qualquer coisa que faças é um palpite. Podes arrumar a estante na perfeição por ordem alfabética e ter de refazer tudo porque o que se queria eram caixas para a mudança. Resolver bem o problema errado continua a ser errado.

## Dados relevantes e pormenores do contexto

Os enunciados costumam contar uma pequena história, e uma história tem pormenores. Alguns são dados de que precisas para resolver o problema. Outros existem para tornar o texto legível e não mudam nada na solução.

Há uma pergunta que ajuda a separar uns dos outros: se este pormenor fosse diferente, a resposta mudava? Se muda, é um **dado relevante** e tem de entrar no problema. Se não muda, é **contexto** e podes deixá-lo de fora.

Pensa num enunciado que diga "a Rita, que anda no 10.º ano e gosta de basquetebol, compra um sumo de 80 cêntimos no bar da escola em cada um dos 5 dias de aulas da semana, e quer saber quanto gasta por semana". O nome da Rita, o ano dela e o desporto de que gosta não mudam o que ela gasta. O preço do sumo e o número de dias mudam: com um sumo mais caro, ou com uma semana de 4 dias de aulas por causa de um feriado, a resposta seria outra.

Há dois erros opostos a evitar. O primeiro é deitar fora uma frase que parece decoração e afinal é uma regra. Vais ver já a seguir, nos Missionários e Canibais, uma frase curta e discreta que muda o problema inteiro. O segundo é guardar tudo por precaução e depois perder-se no meio de pormenores que não interessam. A pergunta "se isto mudasse, a resposta mudava?" protege-te dos dois.

Às vezes a pergunta revela outra coisa: falta informação. O enunciado não diz uma coisa de que precisas, ou diz de uma forma que se pode ler de duas maneiras. Nesse caso não inventes. Pergunta a quem escreveu o enunciado ou, se não for possível, escreve com clareza a decisão que tomaste, para que quem ler a tua solução saiba em que pressuposto assenta.

## Pensamento computacional

O **pensamento computacional** é uma forma de pensar sobre problemas que torna a solução possível de executar por outra pessoa ou por uma máquina. Costuma apresentar-se em quatro ideias: decomposição, reconhecimento de padrões, abstração e algoritmo. Não se usam por ordem, uma de cada vez, como numa receita. Usam-se em conjunto e vai-se saltando entre elas enquanto se pensa.

### Decomposição

**Decompor** é partir um problema grande em partes mais pequenas, cada uma suficientemente simples para se resolver e verificar sozinha.

No dia a dia fazes isto sem dar por isso. Organizar uma festa de anos parece uma tarefa enorme. Partida em "convidados", "comida", "música" e "espaço", cada parte já se consegue pensar. E "comida" ainda se parte em "o que comprar", "quem compra" e "onde se guarda até ao dia".

Nos Missionários e Canibais, "levar toda a gente para o outro lado" é demasiado grande para se pensar de uma vez. Partido em "uma travessia de cada vez", e cada travessia partida em "escolher quem vai", "verificar se é permitido" e "atualizar quem está em cada margem", o problema passa a ser uma sequência de decisões pequenas.

O erro típico é parar de decompor cedo demais, com uma parte que continua a ser o problema inteiro com outro nome, como "resolver o jogo". O erro contrário também existe: partir em tantos bocados que já não se percebe para que serve cada um. O critério é este: cada parte tem de se conseguir explicar e verificar sozinha.

### Reconhecimento de padrões

**Reconhecer padrões** é reparar no que se repete, dentro de um problema ou entre problemas diferentes, para resolver uma vez e aproveitar muitas.

Quando fazes uma soma de números grandes em coluna, repetes o mesmo processo em cada coluna: somar os algarismos, escrever as unidades, levar o transporte para a coluna seguinte. Não aprendeste um método diferente para as centenas e outro para os milhares. Aprendeste um padrão.

Nos Missionários e Canibais, cada travessia passa exatamente pela mesma verificação: contar quem fica em cada margem e ver se a regra de segurança se cumpre. Só os números mudam. Reparar nisto significa que só tens de aprender a verificar uma vez.

O erro típico é ver um padrão onde ele não se aplica sempre. Vais ver na solução dos Missionários e Canibais que quase todas as idas e voltas seguem o ritmo "vão dois, volta um", mas há uma que não segue. Quem confiar no padrão sem verificar cada passo fica bloqueado precisamente aí. Um padrão ajuda a pensar. Não dispensa a verificação.

### Abstração

**Abstrair** é ficar só com o que interessa para a decisão que se está a tomar, e representá-lo da forma mais simples possível.

O mapa do metro é o exemplo clássico. Não mostra as distâncias reais, as ruas por cima, nem as curvas dos túneis. Mostra as estações, a ordem em que aparecem e onde se muda de linha, que é tudo o que precisas para decidir onde sair. Um mapa com todos os pormenores reais seria mais verdadeiro e muito menos útil.

Nos Missionários e Canibais, os nomes das pessoas, a cor do barco e a largura do rio desaparecem. A situação inteira fica descrita com três coisas: quantos missionários estão na margem esquerda, quantos canibais estão na margem esquerda e de que lado está o barco. Vais ver no exemplo guiado porque é que isto chega.

O erro típico é abstrair demais, e deitar fora uma coisa de que precisas. Se tirares o lado do barco da tua representação, deixas de saber quem pode viajar a seguir, porque só pode viajar quem está na margem onde o barco está.

### Algoritmo

Depois de decompor, de reparar nos padrões e de escolher a representação, sobra escrever os passos. É aqui que aparece o algoritmo, tal como foi definido acima. Neste guia os passos escrevem-se em português, numerados. No guia seguinte vais aprender uma notação própria para os escrever com mais rigor.

## Ação e estado

Os Missionários e Canibais mostram duas ideias que vão acompanhar-te o ano inteiro.

O **estado** é o conjunto de valores que descrevem a situação num dado momento. É uma fotografia: quem está em cada margem e onde está o barco, agora, antes de mais nada acontecer.

Uma **ação** é um passo que muda o estado. Cada travessia é uma ação: antes dela o estado era um, depois dela é outro.

O marcador de um jogo de futebol é um bom exemplo do dia a dia. O estado é o resultado e o minuto de jogo. Um golo é uma ação que muda o estado. Se quiseres saber se uma equipa está a ganhar, não precisas de rever o jogo todo: olhas para o estado.

Verificar uma regra é olhar para o estado. Encontrar um erro é, quase sempre, descobrir em que ação o estado passou a ser diferente do que devia. No guia seguinte o estado passa a ter nomes próprios, chamados variáveis, e vais aprender a segui-lo ação a ação numa tabela.

## O contrato de entrada e saída

O **contrato de entrada e saída** de um problema é a descrição escrita, antes de haver algoritmo, de quatro coisas:

- as **entradas**: que dados o algoritmo recebe, de que tipo, em que unidade e com que limites;
- as **saídas**: que resultado o algoritmo produz, e em que forma;
- as **restrições**: as regras que têm de ser respeitadas, sobre as entradas ou sobre o caminho até à saída;
- os **exemplos concretos**: algumas entradas escolhidas com cuidado, cada uma com a saída que se espera, calculada à mão.

Chama-se contrato porque funciona como um acordo entre duas partes. Quem usa o algoritmo compromete-se a dar entradas dentro dos limites combinados. O algoritmo compromete-se a devolver a saída prometida. Se alguém der uma entrada fora do combinado, o contrato ou diz o que acontece nesse caso, ou deixa claro que esse caso não está coberto.

Uma máquina de venda automática tem um contrato destes, mesmo que ninguém o tenha escrito num papel. As entradas são o dinheiro que se mete e o código do produto. As saídas são o produto e o troco. As restrições dizem que moedas aceita e o que acontece se o código não existir ou se o dinheiro não chegar. Repara numa coisa: para usares a máquina não precisas de saber como ela funciona por dentro. O contrato basta. É essa a grande vantagem de um contrato bem escrito: separa o que o algoritmo faz de como o faz.

### Um contrato completo: livros em caixas

Imagina este enunciado:

> A biblioteca da escola vai mudar de sala e quer arrumar os livros em caixas. Cada caixa leva no máximo 12 livros. A biblioteca quer saber quantas caixas vai precisar e quantos livros vão ficar na última caixa.

O contrato escreve-se assim.

As entradas são duas: o número de livros, que é um número inteiro igual ou maior do que zero, e a capacidade de cada caixa, medida em número de livros, que é um número inteiro maior do que zero. Repara que a capacidade não pode ser zero: uma caixa onde não cabe nenhum livro não serve para nada, e o contrato deixa isso claro logo à partida.

As saídas também são duas: o número de caixas necessárias e o número de livros que vão na última caixa.

As restrições são as regras do enunciado escritas com rigor: nenhuma caixa leva mais livros do que a capacidade, todos os livros ficam dentro de uma caixa e não se usam caixas vazias.

Os exemplos concretos calculam-se à mão, sem algoritmo nenhum, e escolhem-se de propósito para cobrir situações diferentes:

| Livros | Capacidade | Caixas | Livros na última caixa | Porque é que este caso foi escolhido |
| ---: | ---: | ---: | --- | --- |
| 30 | 12 | 3 | 6 | Caso normal: duas caixas cheias e uma incompleta |
| 24 | 12 | 2 | 12 | A divisão é exata e a última caixa fica cheia |
| 5 | 12 | 1 | 5 | Há menos livros do que cabem numa caixa |
| 0 | 12 | 0 | não há última caixa | Quantidade nula: não há nada para arrumar |

Vale a pena perceber o que cada linha ensina.

A primeira linha é o caso que qualquer pessoa imagina ao ler o enunciado. Com 30 livros enchem-se duas caixas de 12, que levam 24, e sobram 6 livros. Esses 6 também têm de ir numa caixa, porque a restrição diz que todos os livros ficam dentro de uma caixa. São portanto 3 caixas, e a última leva 6.

A segunda linha mostra que a última caixa pode estar cheia. Quem só pensou no primeiro caso pode ter ficado com a ideia de que a última caixa está sempre incompleta, e este exemplo desfaz essa ideia antes de ela chegar ao algoritmo.

A terceira linha é o caso em que nem uma caixa se enche. A resposta é uma caixa com 5 livros, e não zero caixas, porque os 5 livros têm de ir para algum lado.

A quarta linha é a mais interessante, porque obriga a tomar uma decisão que o enunciado não tomou. Com zero livros não é preciso nenhuma caixa, e por isso não há última caixa. Quantos livros vão "na última caixa" quando ela não existe? O enunciado não responde. O contrato tem de responder, e aqui a decisão foi dizer por palavras que não há última caixa. Podia ter sido outra, desde que ficasse escrita. O que não pode acontecer é ninguém ter pensado nisso e o algoritmo fazer uma coisa qualquer quando aparecer o zero.

Estes exemplos servem para duas coisas. Antes de escrever o algoritmo, mostram se percebeste o problema: se não conseguires calcular à mão o resultado de um exemplo, ainda não o percebeste. Depois de escrever o algoritmo, servem de teste: o algoritmo tem de dar exatamente estes resultados, e se não der, está errado.

## Exemplo guiado: os Missionários e Canibais

Vais agora aplicar tudo o que viste ao jogo da primeira aula, do enunciado até à solução completa, passo a passo.

### O enunciado

Esta versão tem pormenores a mais de propósito, para praticares a separação entre dados e contexto:

> Numa manhã de verão, três missionários e três canibais chegam à margem esquerda de um rio largo, de águas castanhas e corrente fraca. Querem todos passar para a margem direita. Encontram um pequeno barco de madeira, pintado de vermelho, com dois remos. O barco leva no máximo duas pessoas e não atravessa o rio sozinho. Há um perigo: se, em alguma das margens, os canibais ficarem em maior número do que os missionários, os missionários são atacados e o jogo está perdido. Como é que os seis chegam todos à margem direita?

### Passo 1: ler duas vezes

A primeira leitura serve para perceber a história: há pessoas de um lado, querem ir para o outro, há um barco pequeno e há um perigo. A segunda leitura faz-se com lápis na mão, a sublinhar tudo o que parece um número, um limite ou uma regra. Não saltes a segunda leitura. É nela que se encontram as frases curtas que mudam tudo.

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

A frase "não atravessa o rio sozinho" é a frase curta e discreta de que se falou atrás. Parece um pormenor, e é ela que obriga a que haja viagens de regresso com alguém dentro. Sem ela, o barco podia voltar vazio e bastavam três viagens com pessoas, todas da esquerda para a direita.

Repara também numa leitura cuidadosa da regra de segurança. Ela fala de os missionários serem atacados. Numa margem onde não há nenhum missionário, não há ninguém para atacar, e por isso dois canibais sozinhos numa margem não fazem perder o jogo. Só há perigo numa margem onde haja pelo menos um missionário e mais canibais do que missionários.

### Passo 3: procurar o que falta ou se pode ler de duas maneiras

O enunciado não diz uma coisa importante: quem está dentro do barco conta para alguma das margens? Imagina que o barco chega à margem direita com um canibal. Esse canibal conta como estando na margem direita, ou fica "no barco" e não conta?

As duas leituras são possíveis, e podem dar respostas diferentes. Não se inventa em silêncio. Toma-se uma decisão e escreve-se. A regra usada nas aulas é esta: quem está no barco conta na margem onde o barco está.

Vê o que isto quer dizer em cada momento de uma travessia:

- Enquanto o barco está encostado à margem esquerda, quem já entrou nele continua a contar na margem esquerda. Entrar no barco não é sair da margem.
- Quando o barco chega à margem direita, quem vai nele passa a contar na margem direita, quer saia do barco quer fique lá dentro. Ficar sentado no barco não protege ninguém.

Voltando ao exemplo: o canibal que chega à margem direita conta como estando na margem direita, mesmo que não ponha um pé em terra.

Esta regra tem uma consequência útil. Entrar no barco não muda as contas de nenhuma margem, porque quem entra continua a contar na margem de onde vai partir. As contas só mudam quando o barco muda de lado. Por isso chega verificar a regra de segurança depois de cada travessia, e é isso que se faz daqui em diante.

Há mais duas perguntas que se respondem com o próprio enunciado. O barco pode levar uma só pessoa? Pode, porque "no máximo duas" inclui uma. O barco pode atravessar vazio? Não, porque não atravessa sozinho.

### Passo 4: escrever o contrato

A entrada é a situação inicial: três missionários e três canibais na margem esquerda, ninguém na margem direita e o barco na margem esquerda.

A saída é uma lista de travessias, em que cada travessia diz quem vai no barco e em que sentido, e que termina com as seis pessoas na margem direita.

As restrições são as regras do jogo, escritas com rigor:

1. em cada travessia vão uma ou duas pessoas no barco;
2. o barco só parte da margem onde está, e por isso as travessias alternam de sentido;
3. depois de cada travessia, em nenhuma margem onde haja pelo menos um missionário pode haver mais canibais do que missionários, contando quem está no barco na margem onde o barco está.

Como exemplos concretos, num jogo destes faz sentido verificar à mão uma ou duas jogadas antes de tentar a solução toda. Levar dois canibais na primeira travessia é permitido: a margem esquerda fica com 3 missionários e 1 canibal, e a direita com 2 canibais e nenhum missionário, pelo que ninguém corre perigo. Levar dois missionários na primeira travessia não é permitido: a margem esquerda fica com 1 missionário e 3 canibais, e a regra falha.

Repara numa diferença em relação ao exemplo dos livros. Num jogo como este a entrada é sempre a mesma, porque o jogo começa sempre da mesma maneira. Na maior parte dos problemas desta disciplina, a entrada muda de cada vez que o algoritmo é usado, como os livros da biblioteca, e é por isso que os exemplos concretos do contrato vão ganhar tanta importância.

### Passo 5: abstrair, representando a situação com números

Para acompanhar o jogo não precisas de desenhar o rio. Chega uma representação com três valores: quantos missionários estão na margem esquerda, quantos canibais estão na margem esquerda e de que lado está o barco. A situação inicial escreve-se (3, 3, esquerda) e o objetivo escreve-se (0, 0, direita).

Porque é que não se escreve também a margem direita? Porque se deduz: há sempre três missionários ao todo, e por isso os que estão na direita são 3 menos os que estão na esquerda. O mesmo para os canibais. Guardar os dois lados seria guardar a mesma informação duas vezes, e isso abre a porta a um erro chato: escrever 3 missionários na esquerda e 1 na direita, o que daria 4 missionários, que não existem. Uma boa representação guarda o mínimo necessário, e com isso torna alguns erros impossíveis.

Nas tabelas deste guia vais ver as duas margens escritas, porque é mais fácil verificar a regra de segurança com os números à frente. Mas a direita é sempre calculada a partir da esquerda.

### Passo 6: decompor numa travessia de cada vez

O problema grande é "chegar de (3, 3, esquerda) a (0, 0, direita)". Decompõe-se numa sequência de travessias, e cada travessia decompõe-se nestes passos:

1. Ver em que margem está o barco.
2. Escolher quem vai no barco. Há apenas cinco hipóteses: um missionário, dois missionários, um canibal, dois canibais, ou um missionário e um canibal.
3. Confirmar que essas pessoas estão mesmo na margem onde está o barco.
4. Calcular a nova situação: tirar essas pessoas da margem de partida, pô-las na margem de chegada e mudar o barco de lado.
5. Verificar a regra de segurança nas duas margens.
6. Se a regra falhar, desfazer a travessia e voltar ao passo 2 com outra hipótese.
7. Se a regra se cumprir, confirmar que a nova situação não é uma que já aconteceu antes. Se for, também se volta ao passo 2, porque regressar a uma situação conhecida é andar para trás.
8. Se a nova situação for (0, 0, direita), o jogo está resolvido. Se não for, volta-se ao passo 1 para a travessia seguinte.

O passo 7 merece uma explicação. Sem ele, podias passar a tarde a levar um canibal para a direita e a trazê-lo de volta, sempre dentro das regras e sem nunca avançar. Recusar situações repetidas é o que garante que o processo acaba.

O passo 8 manda voltar ao início e fazer tudo outra vez para a travessia seguinte. Fazer os mesmos passos várias vezes chama-se repetição, e vai ter uma notação própria mais à frente no percurso. Por agora, basta dizê-lo em português com clareza, como está acima.

### Passo 7: reconhecer o padrão da verificação

Os passos 1 a 8 são iguais em todas as travessias. Só mudam os números. É o padrão de que se falou na teoria: aprendes a verificar uma travessia e sabes verificar todas.

Vê o padrão a funcionar logo na primeira travessia, experimentando as cinco hipóteses a partir de (3, 3, esquerda):

| Quem vai | Margem esquerda fica com | Margem direita fica com | A regra cumpre-se? |
| --- | --- | --- | --- |
| 1 missionário | 2 missionários e 3 canibais | 1 missionário | Não: na esquerda, 3 canibais contra 2 missionários |
| 2 missionários | 1 missionário e 3 canibais | 2 missionários | Não: na esquerda, 3 canibais contra 1 missionário |
| 1 canibal | 3 missionários e 2 canibais | 1 canibal | Sim |
| 2 canibais | 3 missionários e 1 canibal | 2 canibais | Sim |
| 1 missionário e 1 canibal | 2 missionários e 2 canibais | 1 missionário e 1 canibal | Sim |

Das cinco hipóteses, duas falham logo. As outras três são permitidas. A solução que se segue começa com dois canibais, mas começar com um missionário e um canibal também leva a uma solução.

### Passo 8: simular até ao fim

Esta é a solução completa. Cada linha é o estado depois de uma travessia. A coluna da direita mostra a verificação da regra, feita em todas as linhas e não só nas que parecem perigosas.

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

Na tabela, M quer dizer missionários e C quer dizer canibais.

A travessia 6 é o momento mais difícil do jogo, e é onde muita gente fica presa na aula. Depois da travessia 5 o barco está na margem direita, que tem 2 missionários e 2 canibais. Alguém tem de levar o barco de volta. Vê as cinco hipóteses, uma a uma, com o padrão da verificação:

- Se voltar 1 missionário, a direita fica com 1 missionário e 2 canibais. A regra falha.
- Se voltarem 2 missionários, a situação passa a ser a mesma que havia depois da travessia 4. É permitido, mas é andar para trás, e o passo 7 da decomposição recusa-o.
- Se voltar 1 canibal, a esquerda fica com 1 missionário e 2 canibais. A regra falha.
- Se voltarem 2 canibais, a esquerda fica com 1 missionário e 3 canibais. A regra falha.
- Se voltarem 1 missionário e 1 canibal, a esquerda fica com 2 e 2 e a direita com 1 e 1. A regra cumpre-se e a situação é nova.

Só uma hipótese faz avançar, e é a menos intuitiva de todas, porque leva de volta um missionário que tinha acabado de atravessar. É também aqui que o padrão "vão dois, volta um" deixa de funcionar: nas travessias 5 e 6 vão dois e voltam dois. Quem seguisse o padrão sem verificar não encontrava esta saída.

Não há nenhuma solução com menos de 11 travessias. Há outras sequências com 11, que diferem no início ou no fim, e qualquer uma delas é uma solução correta, desde que cumpra o contrato.

### Passo 9: confirmar a solução contra o contrato

Uma solução não está terminada quando chega ao fim. Está terminada quando se verificou que cumpre o contrato. Para esta, confirma-se o seguinte:

- em todas as travessias vão uma ou duas pessoas;
- os sentidos alternam, a começar na esquerda, e por isso o barco parte sempre da margem onde está;
- em todas as linhas da tabela a regra de segurança se cumpre, nas duas margens;
- a última linha é (0, 0, direita), com toda a gente na margem direita;
- em todas as linhas há 3 missionários e 3 canibais ao todo, somando as duas margens.

Esta última verificação não vem do enunciado e é na mesma muito útil. Se numa linha a soma desse 5 ou 7, terias a certeza de que houve um erro de contas nessa travessia, mesmo antes de verificares a regra. Procurar coisas que têm de se manter sempre iguais é uma forma rápida de apanhar erros, e vais usá-la muitas vezes.

## Erros frequentes

### Unidade de medida ambígua

Imagina que o enunciado dos livros dizia "cada caixa leva no máximo 10" em vez de "12 livros". Dez quê? Dez livros, ou dez quilos? Se forem dez livros, 30 livros precisam de 3 caixas. Se forem dez quilos e cada livro pesar meio quilo, cabem 20 livros por caixa e 30 livros precisam só de 2 caixas. O mesmo enunciado dá duas respostas diferentes, conforme a unidade que se imagina.

Pior ainda: se for em quilos, o enunciado não diz quanto pesa cada livro, e sem esse dado o problema não se resolve. Não é um problema de contas. É informação que falta.

Como se evita: no contrato, cada entrada leva a sua unidade escrita por extenso, como "capacidade da caixa, em número de livros". Quando o enunciado não diz a unidade, não se escolhe uma em silêncio. Pergunta-se, ou escreve-se a decisão.

### Etapa omitida

Uma etapa omitida é um passo que falta no algoritmo e que não se nota enquanto se testa só o caso que se tinha em mente.

Nos Missionários e Canibais, a etapa que costuma faltar é o regresso do barco. Quem escreve "1. levar dois canibais; 2. levar dois canibais; 3. levar dois missionários" esqueceu-se de que o barco não volta sozinho. A tabela da simulação denuncia o erro de imediato: depois da primeira travessia o barco está na direita, e a segunda travessia diz "esquerda → direita", o que é impossível.

Nos livros, a etapa que costuma faltar é a caixa incompleta. Quem escreve "dividir os livros pela capacidade e ficar com a parte inteira" obtém 2 caixas para 30 livros, e os 6 que sobram ficam no chão. Repara que com 24 livros esse passo dá a resposta certa, e é por isso que o erro passa despercebido a quem só experimenta divisões exatas.

### Reproduzir a falha com um exemplo mínimo

Quando se descobre um erro, o passo seguinte é encontrar o **exemplo mínimo** que o reproduz: a entrada mais pequena e simples que ainda mostra a falha.

No caso da caixa incompleta, 30 livros mostram o erro, mas obrigam a fazer contas. 13 livros também mostram: dá 1 caixa e fica 1 livro de fora. E 1 livro mostra ainda melhor: o passo errado dá 0 caixas para 1 livro, o que é evidentemente absurdo. Com o exemplo mínimo a causa salta à vista, e depois de corrigires o algoritmo é o primeiro caso que voltas a experimentar, porque é o mais rápido de verificar.

Nos Missionários e Canibais, o exemplo mínimo do regresso esquecido são só duas travessias seguidas no mesmo sentido. Não é preciso simular o jogo inteiro para mostrar o erro.

### Começar a resolver antes de acabar de ler

É o erro mais comum de todos, e explica muitos dos outros. Quem lê a primeira frase dos Missionários e Canibais e começa logo a mexer no barco não repara em "não atravessa sozinho" nem na leitura cuidadosa da regra de segurança. O remédio é o passo 1 do exemplo guiado: ler duas vezes, a segunda com lápis.

### Esquecer os casos extremos no contrato

Um contrato só com o caso normal, como os 30 livros, parece completo e não está. Os casos extremos, como zero livros ou menos livros do que uma caixa, são os que obrigam a decisões que o enunciado não tomou. Se não aparecerem no contrato, vão aparecer mais tarde, quando o algoritmo já estiver escrito e for mais caro corrigir.

### Passos vagos

"Levar as pessoas certas" ou "arrumar os livros pelas caixas" não são passos. São o problema inteiro com outras palavras. Um passo tem de dizer exatamente o que fazer, de forma que outra pessoa o execute sem te perguntar nada.

## Verificar o que aprendeste

Usa esta lista para te testares. Para cada ponto, experimenta fazê-lo sem olhar para o guia. Se não conseguires, volta à secção correspondente.

- Consegues explicar a um colega que faltou à aula a diferença entre algoritmia e programação, com um exemplo teu que não esteja neste guia.
- Consegues dizer o que distingue um enunciado de um problema, e o que quer dizer delimitar um problema.
- Perante um enunciado novo, consegues sublinhar os pormenores e justificar, para cada um, se é um dado ou contexto, usando a pergunta "se isto mudasse, a resposta mudava?".
- Consegues escrever o contrato de um problema com entradas, saídas, restrições e pelo menos três exemplos concretos, incluindo um caso extremo.
- Consegues calcular à mão, para o problema dos livros, um caso que não esteja na tabela, como 25 livros em caixas de 8, e explicar cada passo da conta.
- Consegues dar um exemplo teu de decomposição, de padrão e de abstração.
- Consegues explicar porque é que a representação (3, 3, esquerda) chega para descrever o jogo, e o que se perdia se tirasses o lado do barco.
- Consegues refazer a simulação dos Missionários e Canibais numa folha, sem olhar para a tabela, verificando a regra em cada travessia.
- Consegues explicar porque é que, na travessia 6, a única escolha que faz avançar é levar de volta um missionário e um canibal.
- Perante um enunciado ambíguo, consegues dizer que informação falta e construir o exemplo mais pequeno em que as duas leituras dão resultados diferentes.

## O que vem a seguir

No [guia seguinte](02-estado-sequencia-representacoes.md) vais aprender a escrever algoritmos numa notação própria, chamada pseudocódigo, e a desenhá-los em fluxograma. O estado dos Missionários e Canibais, que aqui eram três números escritos numa tabela, passa a ter nomes próprios, chamados variáveis, e vais aprender a segui-lo passo a passo numa tabela de trace. O contrato continua a ser o primeiro passo de todos os problemas: antes de escrever uma única instrução, vais sempre escrever as entradas, as saídas, as restrições e os exemplos.

![Rodapé](../imagens/rodape.png)
