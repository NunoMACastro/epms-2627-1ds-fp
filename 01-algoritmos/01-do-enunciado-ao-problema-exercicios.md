![Cabeçalho](../imagens/cabecalho.png)

# Ficha de exercícios: Do enunciado ao problema delimitado

Ficha do tema Do enunciado ao problema delimitado, do módulo Desenvolver algoritmos. Praticas o que o guia ensinou. Reconheces algoritmos, separas os dados do contexto, escreves o contrato de um problema, segues o estado de uma situação e encontras falhas. Cerca de 85 minutos, para fazeres sozinho, e mais 25 se fizeres o desafio opcional.

## O que precisas de saber

O [guia do tema](01-do-enunciado-ao-problema.md). Este tema não tem laboratório.

Antes de começares, deves conseguir explicar:

- as quatro propriedades de um algoritmo: finito, claro, executável, e parte de dados e chega a um resultado (secção "Algoritmo: os passos antes da linguagem");
- a pergunta que separa um dado do contexto, "se isto mudasse, a resposta mudava?" (secção "Dados relevantes e pormenores do contexto");
- as quatro partes do contrato: entradas, saídas, restrições e exemplos concretos (secção "O contrato de entrada e saída").

Se alguma destas ideias não estiver clara, volta à secção do guia que a explica antes de começares. Vais precisar também de fazer contas simples, da matemática do ensino básico.

## Como trabalhar

Não precisas de computador. Nada nesta ficha se escreve em pseudocódigo nem numa linguagem de programação. Quando te pedirem passos, escreve-os em português, numerados, com uma ação por passo, como no guia. Se uma resposta te sair em frases em vez de passos, também vale, desde que se perceba sem dúvidas o que queres dizer.

Faz os exercícios pela ordem. Cada um usa uma ideia do guia de cada vez, e o último junta várias.

| Exercício | O que treina | Tempo |
| --- | --- | ---: |
| 1 | Reconhecer um algoritmo pelas quatro propriedades | 10 min |
| 2 | Separar os dados do contexto | 10 min |
| 3 | Escrever o contrato de um problema, com os exemplos concretos | 25 min |
| 4 | Decompor e seguir o estado numa tabela | 25 min |
| 5 | Encontrar uma falha e o exemplo mínimo | 15 min |
| Total da parte obrigatória | Exercícios 1 a 5 | 85 min |
| Desafio opcional | Os Missionários e Canibais com dois e dois | 25 min, fora do total |
| Para ires mais longe | O dia em que o Tiago acaba o livro | 40 min, fora do total |

Os exercícios 1 a 5 são obrigatórios e cabem nos 85 minutos da ficha. O desafio e a secção "Para ires mais longe" são opcionais, e nenhum dos dois conta para concluíres a ficha. Servem para quem terminar e quiser mais prática, ou para estudares em casa.

Entregas as respostas em papel ou num ficheiro de texto, com as contas que fizeste, e não só os resultados.

## Exercício 1: Reconhecer um algoritmo (10 minutos)

Cada uma das listas seguintes pretende ser um algoritmo. Para cada uma, diz se é mesmo um algoritmo. Se não for, diz qual das quatro propriedades falha e explica porquê numa frase.

a) Para escrever números: escreve o número 1. Soma 1 ao último número que escreveste e escreve o resultado. Repete o passo anterior sempre.

b) Para fazer arroz: põe arroz q.b. numa panela, junta água e deixa cozer um bocado.

c) Para saber se um número inteiro é par: divide o número por 2. Se o resto da divisão for 0, a resposta é "par". Se não for, a resposta é "ímpar".

d) Para ganhar o Euromilhões: escolhe os números que vão sair no próximo sorteio e regista a aposta com esses números.

Concluíste quando tiveres uma resposta para as quatro listas e, nas que não são algoritmos, souberes apontar a propriedade que falha.

## Exercício 2: Dados e contexto (10 minutos)

Lê este enunciado duas vezes, a segunda com o lápis na mão:

> O Tiago tem 15 anos e joga futsal ao sábado. Quer saber em quantas noites acaba de ler um livro de aventuras com 240 páginas, que lhe ofereceram no Natal. Lê na cama antes de adormecer, com o candeeiro azul ligado, e lê sempre 15 páginas por noite.

a) Faz uma tabela com três colunas: o pormenor do enunciado, se é um dado ou contexto, e porquê. Usa a pergunta do guia para cada pormenor. Põe na tabela pelo menos sete pormenores.

b) Calcula à mão a resposta ao que o Tiago quer saber e escreve a conta.

Concluíste quando a tua tabela separar bem os dados do contexto e a conta da alínea b) estiver escrita.

Se quiseres continuar com o Tiago, o Mais longe 1, no fim da ficha, muda-lhe a pergunta. É opcional.

## Exercício 3: Delimitar o problema dos bilhetes (25 minutos)

Lê o enunciado:

> A turma vai visitar o Oceanário. O autocarro sai da escola às 8h30 e o almoço é no refeitório do Oceanário, que já está pago. Cada aluno paga o seu bilhete, que custa 9 euros. Os professores não pagam bilhete. Tem de ir um professor por cada 10 alunos. Se sobrarem alunos que não chegam a 10, também é preciso mais um professor para eles. A visita só se faz se se inscreverem pelo menos 15 alunos. A diretora de turma quer saber, a partir do número de alunos inscritos, quanto dinheiro tem de recolher e quantos professores têm de ir.

a) Escreve o contrato deste problema: as entradas, com a unidade e os limites de cada uma, as saídas e as restrições.

b) Escreve os exemplos concretos do contrato, numa tabela com quatro colunas:

- alunos inscritos;
- dinheiro a recolher;
- professores que vão;
- porque é que o caso interessa: caso normal, caso que fica exatamente no limite de uma regra do enunciado, ou caso extremo.

Calcula à mão os casos de 23, 20, 15 e 12 alunos, e escreve as contas.

Um destes quatro casos obriga-te a decidir o que as saídas devem dizer, porque o enunciado não o diz. Descobre qual é, e escreve a decisão que tomaste. Não há uma só decisão certa, mas a tua tem de ficar escrita.

c) Delimitar um problema também é dizer o que fica fora dele. Indica dois pormenores do enunciado que não entram na solução e explica porquê.

Concluíste quando outra pessoa conseguir calcular um caso novo, como 31 alunos, só com o teu contrato e sem ler o enunciado.

## Exercício 4: O estado do parque de estacionamento (25 minutos)

Lê o enunciado:

> O parque de estacionamento dos professores tem 40 lugares. À entrada há uma cancela e um painel que mostra quantos lugares estão livres. Quando entra um carro, o número do painel desce um. Quando sai um carro, sobe um. Quando não há lugares livres, a cancela de entrada não abre e o painel mostra "CHEIO".

a) Decompõe o funcionamento do parque em três ou quatro partes. Escreve o objetivo de cada parte numa frase. Lembra-te do critério do guia: cada parte tem de se conseguir explicar e verificar sozinha.

b) Pensa no estado do parque, a fotografia da situação num momento. Qual é o menor número de valores que precisas de guardar para saber tudo o que o painel tem de mostrar? Explica porque é que chega. Explica também porque é que guardar mais um valor seria guardar a mesma informação duas vezes.

c) Simula esta manhã numa tabela de estado. Às 8h00 há 2 lugares livres. Depois acontece, por esta ordem:

1. entra um carro;
2. entra um carro;
3. chega um carro à cancela de entrada;
4. sai um carro;
5. entra um carro.

Usa as colunas: momento, o que acontece, lugares livres depois e o que mostra o painel. Na linha do carro que chega à cancela, diz também o que acontece a esse carro.

Concluíste quando a tua tabela mostrar o estado depois de cada acontecimento e o painel mostrar "CHEIO" sempre, e só, quando deve.

## Exercício 5: Encontrar a falha (15 minutos)

a) Na papelaria da escola, uma mochila custa 40 euros e tem uma etiqueta que diz apenas "Desconto: 5". A Inês tem 36 euros. Chega para comprar a mochila? Mostra que a resposta depende da unidade que se imagina para o 5, fazendo as contas para duas unidades diferentes. Depois escreve como devia estar escrita a etiqueta.

b) Alguém escreveu estes passos para contar as pessoas de uma fila:

1. Olha para a primeira pessoa da fila e diz "1".
2. Se houver alguém atrás da pessoa para quem estás a olhar, olha para essa pessoa e diz o número a seguir ao último que disseste.
3. Repete o passo 2 até não haver ninguém atrás.
4. O último número que disseste é o número de pessoas da fila.

Experimenta os passos com uma fila de 3 pessoas: funcionam. Agora encontra uma fila para a qual não funcionam. Escolhe o exemplo mínimo, a fila mais pequena e simples que mostra a falha, e explica o que corre mal. Por fim, acrescenta um passo que corrija a falha, e diz em que posição o puseste.

Concluíste quando tiveres as contas das duas unidades na alínea a) e, na alínea b), o exemplo mínimo e o passo novo.

## Apoio

Se estiveres encravado, usa estas pistas pela ordem em que aparecem. Passa à seguinte só se a anterior não tiver chegado.

- Exercício 1: para cada lista, faz quatro perguntas, uma por propriedade. Isto acaba? Cada passo só se lê de uma maneira? Consigo fazer cada passo com o que tenho? Sei de onde parto e aonde chego? Basta uma resposta "não" para a lista não ser um algoritmo.
- Exercício 2: para a alínea a), troca mentalmente cada pormenor por outro valor e vê se a resposta à pergunta do Tiago muda. Por exemplo, um candeeiro verde em vez de azul, ou um livro de banda desenhada em vez de aventuras.
- Exercício 3: para as entradas, pergunta-te o que muda de cada vez que a diretora de turma faz esta conta. Para os professores, lembra-te dos livros nas caixas do guia: os alunos que sobram também precisam de alguém. Para a decisão, pergunta-te, em cada um dos quatro casos, se todas as regras do enunciado se cumprem.
- Exercício 4: para a alínea b), olha para o que o painel mostra e pergunta-te se dava para o calcular a partir de outro número. Lembra-te dos Missionários e Canibais: a margem direita não se guardava, porque se deduzia da esquerda.
- Exercício 5: para a alínea a), pergunta-te "5 quê?", como no guia, e lembra-te das maneiras que já viste de escrever um desconto numa montra. Para a alínea b), experimenta filas cada vez mais pequenas: 2 pessoas, 1 pessoa. Depois pergunta-te se ainda há uma fila mais pequena do que a última que experimentaste.

## Desafio opcional

Cerca de 25 minutos. Volta aos Missionários e Canibais, mas agora com dois missionários e dois canibais. O barco continua a levar no máximo duas pessoas e não atravessa sozinho. A regra de segurança é a mesma do guia.

a) Encontra uma solução e mostra-a numa tabela como a do passo 8 do exemplo guiado. Verifica a regra em todas as linhas e nas duas margens.

b) Quantas travessias tem a tua solução? Explica porque é que não é possível fazer com menos.

c) No jogo com três e três, o padrão "vão dois, volta um" falhava numa travessia. No jogo com dois e dois, esse padrão funciona do princípio ao fim? Usa a tua tabela para responder.

## Para ires mais longe

Esta secção é opcional e fica fora dos 85 minutos da ficha. Não precisas de fazer nada daqui para concluíres a ficha, e os critérios de conclusão não a contam. Serve para quem terminou a parte obrigatória e quer mais prática, ou para estudares em casa. O tempo é indicativo.

### Mais longe 1: O dia em que o Tiago acaba o livro (40 minutos)

Continua o exercício 2: usa o mesmo enunciado do Tiago e a conta que fizeste na alínea b). O tempo é grande porque cada exemplo se faz dia a dia, com uma linha por dia, até o livro acabar.

A mãe do Tiago acrescenta uma coisa: "Ao domingo ele não lê, porque se deita mais cedo." E o Tiago muda a pergunta. Agora quer saber em que dia da semana vai acabar o livro. Com estas duas mudanças, o enunciado deixa de chegar para responder. Que informação passa a faltar? Mostra que falta mesmo, com dois exemplos em que essa informação é diferente e o livro acaba em dias da semana diferentes.

Concluíste quando souberes dizer que informação falta e tiveres os dois exemplos feitos dia a dia.

Pista: escolhe um dia da semana para o Tiago começar e faz uma lista dos dias, um por linha. Vai somando as páginas, e salta os domingos. Depois repete com outro dia de início.

## Critérios de conclusão

- [ ] Em cada lista do exercício 1 disse se é um algoritmo e, quando não é, que propriedade falha.
- [ ] Separei os dados do contexto com a pergunta do guia, e não por palpite.
- [ ] Escrevi um contrato com entradas, saídas, restrições e exemplos concretos calculados à mão. Os exemplos incluem um caso no limite de uma regra e um caso extremo.
- [ ] Escrevi as decisões que tomei onde o enunciado não dizia o que fazer.
- [ ] Segui o estado do parque numa tabela, linha a linha.
- [ ] Encontrei um exemplo mínimo para a falha da fila e corrigi os passos.
- [ ] Os meus passos não têm palavras vagas: onde há quantidades, há números com unidade.

## Autoavaliação

1. O que já consegues fazer sozinho, sem voltar ao guia?
2. Que dificuldade tiveste, e o que fizeste para a resolver?

![Rodapé](../imagens/rodape.png)
