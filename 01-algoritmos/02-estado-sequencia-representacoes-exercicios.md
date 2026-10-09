![Cabeçalho](../imagens/cabecalho.png)

# Ficha de exercícios: Estado, sequência e representações

| Identificação | Valor |
| --- | --- |
| Disciplina | Fundamentos de Programação, 10.º ano, Desenvolvimento de Software |
| Unidade de competência | UC00245, Desenvolver algoritmos |
| Material | Ficha do segundo tema, acompanha o [guia](02-estado-sequencia-representacoes.md) |
| Tempo | 80 minutos de exercícios e 20 minutos de desafio opcional |
| Entrega | As respostas em papel ou num ficheiro de texto, com as tabelas de trace preenchidas |

## Antes de começares

Esta ficha treina o que aprendeste no guia: escolher o tipo de cada valor, seguir o estado de um algoritmo numa tabela de trace, fazer contas com `div` e `resto`, escrever um algoritmo sequencial completo, encontrar um erro de ordem e usar a função `abs`.

Antes de começar, deves conseguir explicar a diferença entre uma variável e uma constante, porque é que o tipo só se escreve na linha onde a variável nasce, e o que quer dizer `total = total + 5`. Se alguma destas ideias não estiver clara, volta à secção do guia que a explica.

Escreve os algoritmos na forma que usamos nas aulas, como no exemplo guiado do guia. Se souberes a lógica e não te lembrares da forma, escreve frases claras, que também valem: nesta fase, o que conta é a lógica.

Nas tabelas de trace, segue as regras do guia: uma coluna por variável, uma linha por instrução, "sem valor" até a variável nascer, e a conta que está escrita, não a que achas que devia estar.

Os desenhos de fluxogramas não fazem parte desta ficha. Se o professor indicar o [laboratório](02-estado-sequencia-representacoes-laboratorio.md) deste tema, é lá que os desenhas.

## Exercício 1: Escolher o tipo (10 min)

Para cada valor, escolhe o tipo, `int`, `float`, `string` ou `bool`, e justifica numa frase pelo que o valor representa:

a) o número de alunos de uma turma;

b) a altura de uma pessoa, em metros;

c) o nome de uma cidade;

d) a resposta à pergunta "o portão da escola está aberto?";

e) o preço de um gelado, em euros;

f) o código postal de uma morada, como 4000-123.

Concluíste quando tiveres um tipo para cada valor e souberes explicar a escolha da alínea f), que é a que obriga a pensar duas vezes.

## Exercício 2: Prever o estado (10 min)

Lê este algoritmo:

```text
int x = 5
int y = x + 2
x = x * 3
y = y - x
```

a) Faz a tabela de trace, com as colunas passo, instrução, `x` e `y`. Quanto valem `x` e `y` no fim?

b) Agora imagina que a segunda e a terceira linhas trocam de lugar, ficando `x = x * 3` antes de `int y = x + 2`. Quanto valem `x` e `y` no fim? Explica numa frase porque é que o resultado mudou, se as instruções são as mesmas.

Concluíste quando as duas versões tiverem o estado final certo e a explicação falar da ordem.

## Exercício 3: Contas com `div` e `resto` (10 min)

Calcula à mão, e confirma cada par com a verificação do guia (o divisor vezes a divisão inteira, mais o resto, tem de dar o número de partida):

a) `47 div 6` e `47 resto 6`

b) `30 div 5` e `30 resto 5`

c) `6 div 47` e `6 resto 47`

d) `0 div 9` e `0 resto 9`

Um destes pares costuma surpreender. Diz qual foi o que te fez parar e explica o resultado com rebuçados e amigos, como no guia.

Concluíste quando os quatro pares estiverem calculados e verificados.

## Exercício 4: A placa de madeira (25 min)

Lê o enunciado:

> Um carpinteiro corta placas retangulares de madeira. Para cada placa, quer saber o comprimento da fita que vai colar à volta do rebordo, que é o perímetro, e a área da placa, para saber quanto verniz vai gastar. Mede os dois lados em metros, e os lados podem ter parte decimal, como 1.2 metros.

a) Escreve o contrato: as entradas, com a unidade e os limites, as saídas, com a unidade, e três exemplos concretos calculados à mão. Um dos exemplos tem de ser uma placa quadrada.

b) Escreve o algoritmo em pseudocódigo, ou em frases claras. O resultado tem de aparecer no ecrã com as unidades: o perímetro em metros e a área em metros quadrados.

c) Faz o trace do teu algoritmo para um dos teus exemplos e confirma que dá o que o contrato previu.

Concluíste quando os resultados do trace coincidirem com os do contrato e o ecrã mostrar as unidades certas.

## Exercício 5: Encontrar o erro (15 min)

Esta semana, a papelaria faz um desconto de 0.50 euros em cada caderno. Este algoritmo devia calcular quanto se paga por uma compra de cadernos, já com o desconto:

```text
const DESCONTO_POR_CADERNO = 0.5
Escreve: "Preço de um caderno, em euros?"
float preco = ler valor
Escreve: "Quantos cadernos?"
int quantidade = ler valor
float total = preco * quantidade
preco = preco - DESCONTO_POR_CADERNO
Escreve: "Total a pagar: ", total, " euros"
```

a) Faz o trace para um caderno de 2 euros e 4 cadernos. Em que passo aparece o problema, e o que diz a tabela nesse passo?

b) Corrige o algoritmo, mudando o menor número de linhas possível. Faz outra vez o trace com os mesmos valores e confirma que o total é 6.

Concluíste quando souberes apontar o passo onde o erro aparece e a versão corrigida der o total certo.

## Exercício 6: Andares do elevador (10 min)

Num prédio, o rés-do-chão é o andar 0, a garagem é o andar -1, e os andares de cima são 1, 2, 3 e assim por diante. O elevador está num andar e alguém o chama de outro.

a) Escreve o algoritmo que lê o andar onde o elevador está e o andar de onde foi chamado, e mostra quantos andares o elevador vai percorrer.

b) Testa-o com três chamadas, e escreve o que aparece no ecrã em cada uma: do andar 3 para o 7, do 7 para o 3, e do 2 para a garagem.

Concluíste quando as duas primeiras chamadas derem o mesmo número de andares e souberes dizer porquê.

## Apoio

Se estiveres encravado, usa estas pistas pela ordem em que aparecem, e passa à seguinte só se a anterior não tiver chegado.

Exercício 1. Pergunta-te o que farias com o valor. Se fosses fazer contas com ele, é um número: tem parte decimal? Se não fosses, pensa se não é antes um texto que por acaso tem algarismos.

Exercício 2. Copia sempre a linha de cima e muda só a coluna da variável que está à esquerda do `=`. Numa conta, usa os valores que as variáveis têm nesse momento, na linha de cima.

Exercício 3. Para a alínea c), pergunta-te: se tiveres 6 rebuçados para repartir por 47 amigos, sem partir nenhum, quantos recebe cada um? E quantos sobram?

Exercício 4. Para o perímetro, soma os quatro lados: dois são iguais ao comprimento e dois são iguais à largura. Para os tipos, lembra-te de que os lados podem ter parte decimal. Para o ecrã, escreve as unidades dentro das aspas do `Escreve:`.

Exercício 5. Antes do trace, calcula à mão quanto devia pagar quem compra 4 cadernos de 2 euros com o desconto. No trace, faz cada conta com os valores que estão na linha de cima, e não com os que achas que deviam estar. Quando o total da tabela não for o que calculaste, procura a linha onde ele foi calculado e vê que valores usou.

Exercício 6. Faz a conta do andar de destino menos o andar de partida para as duas primeiras chamadas. Uma dá um número negativo. O guia tem uma função que trata disso.

## Desafio opcional (20 min)

No guia viste que as duas linhas `a = b` e `b = a` não trocam os valores de duas variáveis: no fim, as duas ficam com o mesmo valor, porque o valor antigo de `a` se perde.

Escreve as linhas que trocam mesmo os valores de duas variáveis inteiras `a` e `b`, sem perder nenhum. Depois faz o trace com `a` a valer 4 e `b` a valer 9 e mostra que, no fim, `a` vale 9 e `b` vale 4.

## Critérios de conclusão

- [ ] Escolhi o tipo de cada valor pelo que ele representa, e não pela forma como se escreve.
- [ ] Nas tabelas de trace, mudei em cada linha só a variável da esquerda do `=` e fiz as contas que estavam escritas.
- [ ] Verifiquei cada par de `div` e `resto` com a regra do guia.
- [ ] Escrevi um contrato com unidades e exemplos, e o trace do meu algoritmo deu o que o contrato previa.
- [ ] Encontrei, com o trace, o passo onde o algoritmo dos cadernos se engana, e corrigi-o mudando o mínimo possível.
- [ ] Usei `abs` onde só interessava o tamanho de uma diferença.

## Autoavaliação breve

O que já consigo fazer sozinho:

Uma dificuldade que tive e o que fiz para a resolver:

![Rodapé](../imagens/rodape.png)
