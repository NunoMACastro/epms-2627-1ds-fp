![Cabeçalho](../imagens/cabecalho.png)

# Ficha de exercícios: Estado, sequência e representações

Ficha do tema Estado, sequência e representações, do módulo Desenvolver algoritmos. Treinas o que aprendeste no guia, uma ideia em cada exercício. Fazes sozinho, ao teu ritmo: o que não acabares na aula, acabas em casa ou na aula seguinte.

## O que precisas de saber

O [guia do tema](02-estado-sequencia-representacoes.md). Antes de começar, deves conseguir explicar:

- a diferença entre uma variável e uma constante;
- porque é que o tipo só se escreve na linha onde a variável nasce;
- o que quer dizer `total = total + 5`.

Se alguma destas ideias não estiver clara, volta à secção do guia que a explica. São as secções "Variáveis", "Constantes" e "Atribuição: dar um valor não é perguntar se é igual".

O [laboratório](02-estado-sequencia-representacoes-laboratorio.md) deste tema é de fluxogramas, e é opcional. Os desenhos de fluxogramas não fazem parte desta ficha. Se o professor indicar o laboratório, é lá que os desenhas.

## Como trabalhar

Resolve os exercícios pela ordem. Cada um treina uma ideia do guia:

| Exercício | O que treina |
| --- | --- |
| 1 | Escolher o tipo de cada valor |
| 2 | Seguir o estado de um algoritmo numa tabela de trace |
| 3 | Fazer contas com `div` e `resto` |
| 4 | Escrever um algoritmo sequencial completo, com o contrato e o trace |
| 5 | Encontrar um erro com o trace |
| 6 | Calcular a distância entre dois andares |
| Desafio opcional | Trocar os valores de duas variáveis |

Os exercícios 1 a 6 são obrigatórios. O desafio é opcional e não conta para concluíres a ficha. É para quem terminar e quiser mais prática, ou para estudares em casa.

Escreve os algoritmos na forma que usamos nas aulas, como no exemplo guiado do guia. Se souberes a lógica e não te lembrares da forma, escreve frases claras, que também valem. Nesta fase, o que conta é a lógica.

Nas tabelas de trace, segue as regras do guia. Faz uma coluna por variável e uma linha por instrução, e escreve "sem valor" até a variável nascer. Faz a conta que está escrita, e não a que achas que devia estar. No exercício 2 a), a tabela já vem meio preenchida, para começares. Nas outras, fazes a tabela toda.

Precisas de papel, de preferência quadriculado, e de lápis. Entregas as respostas em papel ou num ficheiro de texto, com as tabelas de trace preenchidas.

## Exercício 1: Escolher o tipo

Para cada valor, escolhe o tipo, `int`, `float`, `string` ou `bool`, e justifica numa frase pelo que o valor representa:

a) o número de alunos de uma turma;

b) a altura de uma pessoa, em metros;

c) o nome de uma cidade;

d) a resposta à pergunta "o portão da escola está aberto?";

e) o preço de um gelado, em euros;

f) o código postal de uma morada, como 4000-123.

## Exercício 2: Prever o estado

Lê este algoritmo:

```text
int x = 5
int y = x + 2
x = x * 3
y = y - x
```

a) Copia esta tabela de trace e completa as colunas `x` e `y` nos passos 2 a 4. Quanto valem `x` e `y` no fim?

| Passo | Instrução executada | x | y | Ecrã |
| ---: | --- | ---: | ---: | --- |
| 0 | antes de começar | sem valor | sem valor | nada |
| 1 | `int x = 5` | 5 | sem valor | nada |
| 2 | `int y = x + 2` | | | nada |
| 3 | `x = x * 3` | | | nada |
| 4 | `y = y - x` | | | nada |

b) Agora imagina que a segunda e a terceira linhas trocam de lugar, ficando `x = x * 3` antes de `int y = x + 2`. Faz a tabela de trace, desta vez em branco, com as mesmas colunas. Quanto valem `x` e `y` no fim? Explica numa frase porque é que o resultado mudou, se as instruções são as mesmas.

## Exercício 3: Contas com `div` e `resto`

Calcula à mão, e confirma cada par com a verificação do guia. O divisor vezes a divisão inteira, mais o resto, tem de dar o número de partida.

a) `47 div 6` e `47 resto 6`

b) `6 div 47` e `6 resto 47`

c) `0 div 9` e `0 resto 9`

d) Quantas semanas completas há em 23 dias, e quantos dias sobram? Escreve as duas contas, com `div` e `resto`, e calcula-as.

Um destes pares costuma surpreender. Diz qual foi o que te fez parar e explica o resultado com rebuçados e amigos, como no guia.

## Exercício 4: A placa de madeira

Lê o enunciado:

> Um carpinteiro corta placas retangulares de madeira. Para cada placa, quer saber o comprimento da fita que vai colar à volta do rebordo, que é o perímetro. Quer saber também a área da placa, para saber quanto verniz vai gastar. Mede os dois lados em metros, e os lados podem ter parte decimal, como 1,2 metros.

a) Escreve o contrato: as entradas, com a unidade e os limites, as saídas, com a unidade, e três exemplos concretos calculados à mão. Um dos exemplos tem de ser uma placa quadrada.

b) Escreve o algoritmo em pseudocódigo, ou em frases claras. O resultado tem de aparecer no ecrã com as unidades: o perímetro em metros e a área em metros quadrados.

c) Faz o trace do teu algoritmo para um dos teus exemplos e confirma que dá o que o contrato previu.

## Exercício 5: Encontrar o erro

Esta semana, a papelaria faz um desconto de 0,50 euros em cada caderno. Este algoritmo devia calcular quanto se paga por uma compra de cadernos, já com o desconto:

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

a) Calcula à mão quanto devia pagar quem compra 4 cadernos de 2 euros, já com o desconto. Depois faz o trace com esses valores. Em que passo aparece o problema, e o que diz a tabela nesse passo?

b) Corrige o algoritmo, mudando o menor número de linhas possível. Faz outra vez o trace com os mesmos valores e confirma que dá o que calculaste.

## Exercício 6: Andares do elevador

Num prédio, o rés-do-chão é o andar 0 e a garagem é o andar -1. Os andares de cima são 1, 2, 3 e assim por diante. O elevador está num andar, e alguém o chama de outro.

a) Escreve o algoritmo que lê o andar onde o elevador está e o andar de onde foi chamado. O algoritmo mostra quantos andares o elevador vai percorrer.

b) Testa-o com três chamadas: do andar 3 para o 7, do 7 para o 3, e do 2 para a garagem. Escreve o que aparece no ecrã em cada uma. Explica numa frase porque é que as duas primeiras dão o mesmo número.

## Apoio

Se estiveres encravado, usa estas pistas pela ordem em que aparecem, e passa à seguinte só se a anterior não tiver chegado.

- Exercício 1. Pergunta-te o que farias com o valor. Se fosses fazer contas com ele, é um número: tem parte decimal? Se não fosses, que tipo serve?
- Exercício 2. Copia sempre a linha de cima e muda só a coluna da variável que está à esquerda do `=`. Numa conta, usa os valores que as variáveis têm nesse momento, na linha de cima.
- Exercício 3. Para a alínea b), pergunta-te: se tiveres 6 rebuçados para repartir por 47 amigos, sem partir nenhum, quantos recebe cada um? E quantos sobram? Para a alínea d), pensa nos rebuçados e nos amigos: o que faz aqui o papel dos amigos?
- Exercício 4. Para o perímetro, soma os quatro lados: dois são iguais ao comprimento e dois são iguais à largura. Para os tipos, lembra-te de que os lados podem ter parte decimal. Para o ecrã, escreve as unidades dentro das aspas do `Escreve:`.
- Exercício 5. No trace, faz cada conta com os valores que estão na linha de cima, e não com os que achas que deviam estar. Quando o total da tabela não for o que calculaste, procura a linha onde ele foi calculado e vê que valores usou.
- Exercício 6. Faz a conta do andar de destino menos o andar de partida para as duas primeiras chamadas, e compara os dois resultados. Pode um elevador percorrer um número negativo de andares?

## Desafio opcional

No guia viste que as duas linhas `a = b` e `b = a` não trocam os valores de duas variáveis. No fim, as duas ficam com o mesmo valor, porque o valor antigo de `a` se perde.

Escreve as linhas que trocam mesmo os valores de duas variáveis inteiras `a` e `b`, sem perder nenhum. Depois faz o trace com `a` a valer 4 e `b` a valer 9. Mostra que, no fim, `a` vale 9 e `b` vale 4.

## Critérios de conclusão

- [ ] Escolhi o tipo de cada valor pelo que ele representa, e não pela forma como se escreve. Sei explicar a escolha da alínea f) do exercício 1.
- [ ] Nas tabelas de trace, mudei em cada linha só a variável da esquerda do `=` e fiz as contas que estavam escritas.
- [ ] No exercício 2, as duas versões têm o estado final certo, e a minha explicação fala da ordem.
- [ ] Calculei os quatro pares de `div` e `resto` e verifiquei cada um com a regra do guia.
- [ ] Escrevi um contrato com unidades e exemplos, e o trace do meu algoritmo deu o que o contrato previa. O ecrã mostra as unidades certas.
- [ ] Encontrei, com o trace, o passo onde o algoritmo dos cadernos se engana, e corrigi-o mudando o mínimo possível. A versão corrigida dá o que calculei à mão.
- [ ] O meu algoritmo do elevador nunca mostra um número negativo de andares, e as duas primeiras chamadas dão o mesmo número; sei dizer porquê.

## Autoavaliação

1. O que já consegues fazer sozinho?
2. Que dificuldade tiveste, e o que fizeste para a resolver?

![Rodapé](../imagens/rodape.png)
