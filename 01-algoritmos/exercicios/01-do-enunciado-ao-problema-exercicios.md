![Cabeçalho](../../imagens/cabecalho.png)

# Ficha de exercícios: Do enunciado ao problema delimitado

Praticas o que o guia ensinou: reconheces algoritmos, separas os dados do contexto e escreves o contrato de um problema. Segues também o estado de uma situação e encontras falhas. Os exercícios 1 a 5 são obrigatórios. Não precisas de computador: as respostas ficam em papel ou num ficheiro de texto, com as contas, e os passos escrevem-se em português, numerados. Para rever: o [guia do tema](../01-do-enunciado-ao-problema.md).

## Exercício 1: Reconhecer um algoritmo

Cada uma das listas seguintes pretende ser um algoritmo. Para cada uma, diz se é mesmo um algoritmo. Se não for, diz o que lhe falta e explica porquê numa frase.

a) Para escrever números: escreve o número 1. Soma 1 ao último número que escreveste e escreve o resultado. Repete o passo anterior sempre.

b) Para fazer arroz: põe arroz quanto baste numa panela, junta água e deixa cozer um bocado.

c) Para saber se um número inteiro é par: divide o número por 2. Se o resto da divisão for 0, a resposta é "par". Se não for, a resposta é "ímpar".

d) Para ganhar o Euromilhões: escolhe os números que vão sair no próximo sorteio e regista a aposta com esses números.

Rever: [Um algoritmo é uma sequência de passos claros](../01-do-enunciado-ao-problema.md#um-algoritmo-é-uma-sequência-de-passos-claros).

<details>
<summary>Pista</summary>

Para cada lista, pergunta-te: isto acaba? Cada passo só se lê de uma maneira? Consigo fazer cada passo com o que tenho?

</details>

## Exercício 2: Dados e contexto

Lê este enunciado duas vezes, a segunda com o lápis na mão:

> O Tiago tem 15 anos e joga futsal ao sábado. Quer saber em quantas noites acaba de ler um livro de aventuras com 240 páginas, que lhe ofereceram no Natal. Lê na cama antes de adormecer, com o candeeiro azul ligado, e lê sempre 15 páginas por noite.

a) Faz uma tabela com três colunas: o pormenor do enunciado, se é um dado ou contexto, e porquê. Usa a pergunta do guia para cada pormenor. Põe na tabela pelo menos sete pormenores.

b) Calcula à mão a resposta ao que o Tiago quer saber e escreve a conta.

Rever: [Um dado relevante muda a resposta](../01-do-enunciado-ao-problema.md#um-dado-relevante-muda-a-resposta).

<details>
<summary>Pista</summary>

Troca mentalmente cada pormenor por outro valor e vê se a resposta à pergunta do Tiago muda.

</details>

## Exercício 3: Delimitar o problema dos bilhetes

Lê o enunciado:

> A turma vai visitar o Oceanário. O autocarro sai da escola às 8h30 e o almoço é no refeitório do Oceanário, que já está pago. Cada aluno paga o seu bilhete, que custa 9 euros. Os professores não pagam bilhete. Tem de ir um professor por cada 10 alunos. Se sobrarem alunos que não chegam a 10, também é preciso mais um professor para eles. A visita só se faz se se inscreverem pelo menos 15 alunos. A diretora de turma quer saber, a partir do número de alunos inscritos, quanto dinheiro tem de recolher e quantos professores têm de ir.

a) Escreve o contrato deste problema: as entradas, com a unidade e os limites de cada uma, as saídas e as restrições. Conta como entrada só o que muda de cada vez que se faz a conta. O mínimo de 15 alunos escreve-se nas restrições.

b) Escreve os exemplos concretos do contrato, numa tabela com quatro colunas:

- alunos inscritos;
- dinheiro a recolher;
- professores que vão;
- porque é que o caso interessa: caso normal, caso que fica exatamente no limite de uma regra do enunciado, ou caso extremo.

Calcula à mão os casos de 23, 20, 15 e 12 alunos, e escreve as contas. Um caso pode ter mais do que uma classificação. Se tiver, diz porquê.

Um destes quatro casos obriga-te a decidir o que as saídas devem dizer, porque o enunciado não o diz. Descobre qual é, e escreve a decisão que tomaste. Não há uma só decisão certa, mas a tua tem de ficar escrita.

c) Delimitar um problema também é dizer o que fica fora dele. Indica dois pormenores do enunciado que não entram na solução e explica porquê.

Rever: [O contrato diz o que entra, o que sai e que regras há](../01-do-enunciado-ao-problema.md#o-contrato-diz-o-que-entra-o-que-sai-e-que-regras-há).

<details>
<summary>Pista</summary>

Em cada um dos quatro casos, pergunta-te se todas as regras do enunciado se cumprem.

</details>

## Exercício 4: O estado do parque de estacionamento

Lê o enunciado:

> O parque de estacionamento dos professores tem 40 lugares. À entrada há uma cancela e um painel que mostra quantos lugares estão livres. Quando entra um carro, o número do painel desce um. Quando sai um carro, sobe um. Quando não há lugares livres, a cancela de entrada não abre e o painel mostra "CHEIO".

a) Decompõe o funcionamento do parque em três ou quatro partes. Escreve o objetivo de cada parte numa frase. Lembra-te do critério do guia: cada parte tem de se conseguir explicar e verificar sozinha.

b) Pensa no estado do parque, a fotografia da situação num momento. Qual é o menor número de valores que precisas de guardar para saber tudo o que o painel tem de mostrar? Explica porque é que chega. Se guardasses também outro número, o que podia correr mal?

c) Simula esta manhã numa tabela de estado. Às 8h00 há 2 lugares livres. Depois acontece, por esta ordem:

1. entra um carro;
2. entra um carro;
3. chega um carro à cancela de entrada;
4. sai um carro;
5. entra um carro.

Usa as colunas: momento (o número do acontecimento, com 0 para as 8h00), o que acontece, lugares livres depois e o que mostra o painel. Na linha do carro que chega à cancela, diz também o que acontece a esse carro.

Rever: [O pensamento computacional tem quatro ideias](../01-do-enunciado-ao-problema.md#o-pensamento-computacional-tem-quatro-ideias) e [O estado é uma fotografia, e a ação muda-o](../01-do-enunciado-ao-problema.md#o-estado-é-uma-fotografia-e-a-ação-muda-o).

## Exercício 5: Encontrar a falha

a) A Inês encomendou uma mochila numa loja online, para levar na visita de estudo. A página da loja diz apenas "Entrega em 3 dias". A Inês fez a encomenda numa sexta-feira, e a visita é na terça-feira seguinte. A mochila chega a tempo? Mostra que a resposta depende da maneira de contar os 3 dias, com as contas de duas maneiras diferentes. Depois escreve como devia estar escrita a frase da loja.

b) Alguém escreveu estes passos para contar as pessoas de uma fila:

1. Olha para a primeira pessoa da fila e diz "1".
2. Se houver alguém atrás da pessoa para quem estás a olhar, olha para essa pessoa e diz o número a seguir ao último que disseste.
3. Repete o passo 2 até não haver ninguém atrás.
4. O último número que disseste é o número de pessoas da fila.

Experimenta os passos com uma fila de 3 pessoas: funcionam. Agora encontra uma fila para a qual não funcionam. Escolhe o exemplo mínimo, a fila mais pequena e simples que mostra a falha, e explica o que corre mal. Por fim, acrescenta um passo que corrija a falha, e diz em que posição o puseste. Se a numeração mudar, acerta o "Repete o passo 2".

Rever: [Reproduzir a falha com um exemplo mínimo](../01-do-enunciado-ao-problema.md#reproduzir-a-falha-com-um-exemplo-mínimo).

<details>
<summary>Pista</summary>

Na alínea b), segue os passos à letra, como o robô da sandes: faz só o que cada passo diz.

</details>

## Desafios

### Desafio 1: Os Missionários e Canibais com dois e dois

Volta aos Missionários e Canibais, com dois missionários e dois canibais. O barco continua a levar no máximo duas pessoas e não atravessa sozinho. A regra de segurança é a mesma do guia.

a) Encontra uma solução e mostra-a numa tabela como a do exemplo guiado. Verifica a regra em todas as linhas e nas duas margens.

b) Quantas travessias tem a tua solução? Se conseguires fazer com menos, refaz a tabela. Explica porque é que não é possível descer abaixo desse número.

c) No jogo com três e três, o padrão "vão dois, volta um" falhava numa travessia. No jogo com dois e dois, esse padrão funciona do princípio ao fim? Justifica com a tua tabela.

Rever: [Exemplo guiado: os Missionários e Canibais](../01-do-enunciado-ao-problema.md#exemplo-guiado-os-missionários-e-canibais).

<details>
<summary>Pista</summary>

Para a alínea b), conta quantas pessoas a mais ficam na direita depois de cada ida e volta.

</details>

### Desafio 2: O dia em que o Tiago acaba o livro

Usa o enunciado do exercício 2. A mãe do Tiago acrescenta: "Ao domingo ele não lê, porque se deita mais cedo." E o Tiago quer saber em que dia da semana vai acabar o livro. Com estas duas mudanças, o enunciado deixa de chegar. Que informação passa a faltar? Mostra que falta mesmo, com dois exemplos em que essa informação é diferente e o livro acaba em dias da semana diferentes.

<details>
<summary>Pista</summary>

Faz a conta dia a dia, numa lista, e salta os domingos.

</details>

## Critérios de conclusão

- Em cada lista do exercício 1, disseste se é um algoritmo e, quando não é, o que lhe falta.
- No exercício 2, separaste os dados do contexto com a pergunta do guia, e escreveste a conta.
- O contrato do exercício 3 tem entradas, saídas, restrições e os exemplos calculados à mão.
- No mesmo exercício, escreveste a decisão que tomaste e os dois pormenores que ficam de fora.
- No exercício 4, decompuseste o parque, explicaste o estado e seguiste-o numa tabela, linha a linha.
- No exercício 5, mostraste as duas contagens da mochila, encontraste o exemplo mínimo da fila e corrigiste os passos.

![Rodapé](../../imagens/rodape.png)
