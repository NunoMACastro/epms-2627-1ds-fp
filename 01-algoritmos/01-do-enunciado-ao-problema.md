![Cabeçalho](../imagens/cabecalho.png)

# Do enunciado ao problema delimitado

Neste guia, aprendes a olhar para um enunciado e a transformá-lo num problema bem delimitado, antes de pensares em qualquer solução. Não precisas de computador: faz-se com papel, lápis e atenção.

Precisas das contas de dividir com resto, do ensino básico. Para praticar: [ficha de exercícios](exercicios/01-do-enunciado-ao-problema-exercicios.md).

## Neste guia

1. [Programar é dar instruções a quem as cumpre à letra](#programar-é-dar-instruções-a-quem-as-cumpre-à-letra)
2. [Um algoritmo é uma sequência de passos claros](#um-algoritmo-é-uma-sequência-de-passos-claros)
3. [Primeiro os passos, depois a linguagem](#primeiro-os-passos-depois-a-linguagem)
4. [O enunciado não é o problema](#o-enunciado-não-é-o-problema)
5. [Um dado relevante muda a resposta](#um-dado-relevante-muda-a-resposta)
6. [O pensamento computacional tem quatro ideias](#o-pensamento-computacional-tem-quatro-ideias)
7. [O estado é uma fotografia, e a ação muda-o](#o-estado-é-uma-fotografia-e-a-ação-muda-o)
8. [O contrato diz o que entra, o que sai e que regras há](#o-contrato-diz-o-que-entra-o-que-sai-e-que-regras-há)
9. [Exemplo guiado: os Missionários e Canibais](#exemplo-guiado-os-missionários-e-canibais)

## Programar é dar instruções a quem as cumpre à letra

Um **programa** é um conjunto de instruções que um computador executa, uma de cada vez, pela ordem em que estão escritas. Imagina que explicas a um robô como se faz uma sandes de manteiga, e dizes "põe manteiga no pão". O robô pega na embalagem fechada e pousa-a em cima do pão.

Um computador é esse robô. É muito rápido, mas faz à letra o que lhe mandam, incluindo os erros. Por isso, a parte difícil de programar é saber com toda a precisão o que se quer pedir.

## Um algoritmo é uma sequência de passos claros

Uma receita de bolo parte de ingredientes, segue passos por ordem e chega a um bolo. Um **algoritmo** é uma sequência finita de passos, cada um claro e possível de executar, que parte de uns dados e chega a um resultado:

- finita quer dizer que acaba;
- claro quer dizer que dois colegas fazem o mesmo ao ler o passo;
- possível de executar quer dizer que quem o segue consegue fazê-lo com o que tem.

O teste é simples. Dá os passos a outra pessoa, e vê se ela chega ao mesmo resultado sem te perguntar nada.

O erro típico é escrever passos vagos, como "junta farinha quanto baste" ou "arruma os livros pelas caixas". Têm a forma de instruções, mas dependem do que está na cabeça de quem os escreveu.

## Primeiro os passos, depois a linguagem

A **algoritmia** é o trabalho de pensar, escrever e verificar algoritmos, e não depende de nenhuma linguagem. A **programação** é o trabalho de passar um algoritmo para uma linguagem que o computador executa, como o Python ou o C. Ao longo deste ano, aprendes algoritmos, depois Python e depois C.

A ordem não é por acaso. Se não sabes que passos resolvem um problema, nenhuma linguagem te ajuda. E um erro de raciocínio encontrado no papel custa cinco minutos, mas no meio de um programa pode custar uma tarde.

## O enunciado não é o problema

Imagina que a professora pede para "organizar os livros da estante". Podes arrumá-los na perfeição por ordem alfabética e ter de refazer tudo, porque o que se queria eram caixas para uma mudança. Resolver bem o problema errado continua a ser errado.

O **enunciado** é o texto que te dão. O problema é o que ele pede: de onde se parte, onde se quer chegar e que regras se respeitam. A solução é o caminho que leva de um ponto ao outro. Quando esse caminho está escrito em passos claros e finitos, é um algoritmo.

**Delimitar** um problema é decidir com rigor o que está dentro e o que está fora dele.

## Um dado relevante muda a resposta

> A Rita anda no 10.º ano e gosta de basquetebol. Compra um sumo de 80 cêntimos no bar da escola, em cada um dos 5 dias de aulas da semana. Quer saber quanto gasta por semana.

O nome, o ano e o desporto não mudam o que ela gasta. O preço e o número de dias mudam. A pergunta que os separa é esta: se este pormenor fosse diferente, a resposta mudava? Se muda, é um **dado relevante**. Se não muda, é **contexto**.

Há dois erros opostos. Um é deitar fora uma frase que parece decoração e afinal é uma regra. O outro é guardar tudo e perder-te no meio dos pormenores. Às vezes, falta informação: o enunciado não diz uma coisa de que precisas. Nesse caso, não inventes. Pergunta a quem escreveu, ou escreve a decisão que tomaste.

## O pensamento computacional tem quatro ideias

O pensamento computacional é uma forma de pensar que torna a solução possível de executar por outra pessoa ou por uma máquina. Tem quatro ideias, que se usam em conjunto.

**Decompor** é partir um problema grande em partes mais pequenas, cada uma simples de resolver e de verificar sozinha. Organizar uma festa parte-se em convidados, comida e música. O erro típico é parar cedo de mais, com uma parte que continua a ser o problema inteiro.

Reconhecer padrões é reparar no que se repete, para resolver uma vez e aproveitar muitas. Numa soma em coluna, repetes o mesmo processo em cada coluna. Um padrão ajuda a pensar, mas não dispensa a verificação.

**Abstrair** é ficar só com o que interessa para a decisão, na forma mais simples possível. O mapa do metro não mostra as ruas, só as estações e as linhas. O erro típico é deitar fora uma coisa de que precisas.

A quarta ideia é o próprio algoritmo: depois de decompor, de reparar nos padrões e de abstrair, sobra escrever os passos. Neste guia, escrevem-se em português, numerados.

## O estado é uma fotografia, e a ação muda-o

O **estado** é o conjunto de valores que descrevem a situação num dado momento, como o resultado e o minuto de um jogo de futebol. Uma **ação** é um passo que muda o estado, como um golo. Encontrar um erro é, quase sempre, descobrir em que ação o estado passou a ser diferente do que devia.

## O contrato diz o que entra, o que sai e que regras há

Numa máquina de venda automática, não precisas de saber como funciona por dentro. Basta saberes o que lhe dás, o que ela te devolve e que regras cumpre. O **contrato de entrada e saída** de um problema descreve, antes de haver algoritmo:

- as entradas: que dados se recebem, de que tipo, em que unidade e com que limites;
- as saídas: que resultado se produz;
- as restrições: as regras que têm de ser respeitadas;
- os exemplos concretos: entradas escolhidas com cuidado, cada uma com a saída esperada, calculada à mão.

> A biblioteca da escola vai arrumar os livros em caixas. Cada caixa leva no máximo 12 livros. A biblioteca quer saber de quantas caixas vai precisar e quantos livros vão ficar na última caixa.

As entradas são duas. Uma é o número de livros, um inteiro igual ou maior do que zero. A outra é a capacidade da caixa, em número de livros, um inteiro maior do que zero. A capacidade fica como entrada para o mesmo algoritmo servir para caixas de outro tamanho. As saídas são o número de caixas e os livros da última. As restrições são que nenhuma caixa passa da capacidade, que todos os livros ficam numa caixa e que não há caixas vazias.

| Livros | Capacidade | Caixas | Livros na última caixa | Que caso é |
| ---: | ---: | ---: | --- | --- |
| 30 | 12 | 3 | 6 | Caso normal: duas caixas cheias e uma incompleta |
| 24 | 12 | 2 | 12 | Caso no limite de uma regra: a última caixa fica cheia |
| 5 | 12 | 1 | 5 | **Caso extremo**: nem uma caixa se enche |
| 0 | 12 | 0 | não há última caixa | Caso extremo: não há nada para arrumar |

Com 30 livros, 30 a dividir por 12 dá 2 e sobram 6, que vão numa terceira caixa. Um caso no limite fica exatamente em cima do limite que uma regra põe. Um caso extremo fica nas pontas do problema, como o zero ou o muito pouco. O zero obriga a uma decisão que o enunciado não tomou, e o contrato escreve-a. Os exemplos servem para duas coisas: antes do algoritmo, mostram se percebeste o problema, e depois, servem de teste.

## Exemplo guiado: os Missionários e Canibais

### O enunciado

> Numa manhã de verão, três missionários e três canibais chegam à margem esquerda de um rio largo, de águas castanhas. Querem todos passar para a margem direita. Encontram um pequeno barco de madeira, pintado de vermelho. O barco leva no máximo duas pessoas e não atravessa o rio sozinho. Há um perigo. Se, em alguma das margens, os canibais ficarem em maior número do que os missionários, os missionários são atacados e o jogo está perdido.

Lê-se duas vezes, a segunda com lápis na mão, a sublinhar tudo o que parece um número, um limite ou uma regra.

### Os dados e o contexto

A manhã de verão, as águas castanhas e a cor do barco não mudam nada. Os dados são as quantidades, as duas margens, "no máximo duas pessoas", "não atravessa sozinho" e o perigo, a que se chama regra de segurança. A frase "não atravessa o rio sozinho" parece um pormenor, e é ela que obriga a haver viagens de regresso com alguém dentro.

### O que falta no enunciado

Quem está dentro do barco conta logo na margem, ou só quando sai dele? As duas leituras são possíveis, e por isso toma-se uma decisão e escreve-se. A regra das aulas é esta: quem está no barco conta na margem onde o barco está. Assim, as contas só mudam quando o barco muda de lado, e basta verificar a regra de segurança depois de cada travessia.

Numa margem sem nenhum missionário, não há ninguém para atacar. Só há perigo onde haja pelo menos um missionário e mais canibais do que missionários.

### O contrato e o estado

A entrada é a situação inicial, e a saída é uma lista de travessias que acaba com as seis pessoas na margem direita. As restrições são que vão uma ou duas pessoas em cada travessia, que o barco parte da margem onde está, e a regra de segurança. Como exemplos, levar dois canibais na primeira travessia é permitido. Levar dois missionários não é, porque a margem esquerda ficava com 1 missionário e 3 canibais.

O estado escreve-se com três valores: os missionários na esquerda, os canibais na esquerda e o lado do barco. O início é (3, 3, esquerda), e o objetivo é (0, 0, direita). A margem direita não é precisa, porque se deduz da esquerda. Cada travessia é uma ação que muda o estado.

### Uma travessia de cada vez

O problema decompõe-se em travessias, e cada uma faz sempre o mesmo:

1. Escolher quem vai, entre cinco hipóteses: um ou dois missionários, um ou dois canibais, ou um de cada. Se várias servirem, escolhe-se uma.
2. Calcular a nova situação.
3. Verificar a regra de segurança nas duas margens. Se falhar, escolher outra hipótese.
4. Confirmar que a situação ainda não aconteceu, contando também o lado do barco. Se já aconteceu, escolher outra hipótese, porque é andar para trás.
5. Se nenhuma hipótese servir, desfazer a travessia anterior e escolher outra hipótese nessa.

### A solução

M quer dizer missionários, e C quer dizer canibais. Há quatro soluções com 11 travessias, e esta é uma delas.

| Travessia | Quem vai no barco | Sentido | Margem esquerda | Margem direita |
| ---: | --- | --- | --- | --- |
| início | ninguém | o barco está na esquerda | 3 M, 3 C | 0 M, 0 C |
| 1 | 2 canibais | esquerda → direita | 3 M, 1 C | 0 M, 2 C |
| 2 | 1 canibal | direita → esquerda | 3 M, 2 C | 0 M, 1 C |
| 3 | 2 canibais | esquerda → direita | 3 M, 0 C | 0 M, 3 C |
| 4 | 1 canibal | direita → esquerda | 3 M, 1 C | 0 M, 2 C |
| 5 | 2 missionários | esquerda → direita | 1 M, 1 C | 2 M, 2 C |
| 6 | 1 missionário e 1 canibal | direita → esquerda | 2 M, 2 C | 1 M, 1 C |
| 7 | 2 missionários | esquerda → direita | 0 M, 2 C | 3 M, 1 C |
| 8 | 1 canibal | direita → esquerda | 0 M, 3 C | 3 M, 0 C |
| 9 | 2 canibais | esquerda → direita | 0 M, 1 C | 3 M, 2 C |
| 10 | 1 canibal | direita → esquerda | 0 M, 2 C | 3 M, 1 C |
| 11 | 2 canibais | esquerda → direita | 0 M, 0 C | 3 M, 3 C |

A travessia 6 é a mais difícil. Das cinco hipóteses, só uma faz avançar. Experimenta as outras quatro, com objetos ou numa folha, e descobre porque é que não servem. Quem seguisse o padrão "vão dois, volta um" sem verificar não encontrava esta saída.

### Confirmar a solução

Em todas as travessias vão uma ou duas pessoas, os sentidos alternam, a regra cumpre-se em todas as linhas e a última é o objetivo. Em cada linha, as margens somam 3 missionários e 3 canibais. Se somassem outra coisa, havia um erro de contas nessa travessia.

## Erros frequentes

### Unidade de medida ambígua

Se o enunciado dissesse "cada caixa leva no máximo 10", seriam 10 livros ou 10 quilos? O mesmo enunciado dava duas respostas. No contrato, cada entrada leva a sua unidade por extenso, e quando o enunciado não a diz, pergunta-se.

### Etapa omitida

É um passo que falta e não se nota enquanto se testa só o caso que se tinha em mente. Nos livros, quem só divide e fica com a parte inteira obtém 2 caixas para 30 livros, e os 6 que sobram ficam no chão. Segue os passos com os exemplos do contrato, incluindo os casos extremos.

### Reproduzir a falha com um exemplo mínimo

O exemplo mínimo é a entrada mais pequena que ainda mostra a falha. No erro da caixa incompleta, 1 livro dá 0 caixas, o que é evidentemente absurdo. Depois de corrigires o erro, é o primeiro caso que voltas a experimentar.

## Palavras novas deste guia

- Algoritmo: uma sequência finita de passos, cada um claro e possível de executar, que parte de uns dados e chega a um resultado.
- Algoritmia: o trabalho de pensar, escrever e verificar algoritmos.
- Programação: o trabalho de passar um algoritmo para uma linguagem que o computador executa.
- Enunciado: o texto que te dão, com a descrição da situação.
- Delimitar um problema: decidir com rigor o que está dentro e o que está fora dele.
- Dado relevante: um pormenor que, se fosse diferente, mudava a resposta.
- Contexto: um pormenor que não muda a resposta.
- Decompor: partir um problema grande em partes mais pequenas.
- Reconhecer padrões: reparar no que se repete, para resolver uma vez e aproveitar muitas.
- Abstrair: ficar só com o que interessa para a decisão.
- Estado: o conjunto de valores que descrevem a situação num dado momento.
- Ação: um passo que muda o estado.
- Contrato de entrada e saída: as entradas, as saídas, as restrições e os exemplos de um problema, escritos antes de haver algoritmo.
- Caso extremo: um caso nas pontas do problema, como o zero ou o muito pouco.
- Exemplo mínimo: a entrada mais pequena que ainda mostra uma falha.

## O que vem a seguir

No tema seguinte, [Estado, sequência e representações](02-estado-sequencia-representacoes.md), escreves algoritmos em pseudocódigo, e o estado passa a ter nomes próprios, as variáveis.

![Rodapé](../imagens/rodape.png)
