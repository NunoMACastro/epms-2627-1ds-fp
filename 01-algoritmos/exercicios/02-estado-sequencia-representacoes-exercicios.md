![Cabeçalho](../../imagens/cabecalho.png)

# Ficha de exercícios: Estado, sequência e representações

Escolhes tipos, segues o estado numa tabela de trace, fazes contas com `div` e `resto`, e escreves e corriges algoritmos sequenciais. Os exercícios 1 a 6 são obrigatórios. Precisas de papel e lápis, e entregas as respostas em papel ou num ficheiro de texto, com as tabelas preenchidas. Escreve os algoritmos em pseudocódigo ou em frases claras: o que conta é a lógica. Para rever: o [guia do tema](../02-estado-sequencia-representacoes.md).

## Exercício 1: Escolher o tipo

Para cada valor, escolhe o tipo, `int`, `float`, `string` ou `bool`, e justifica numa frase pelo que o valor representa:

a) o número de alunos de uma turma;

b) a altura de uma pessoa, em metros;

c) o nome de uma cidade;

d) a resposta à pergunta "o portão da escola está aberto?";

e) o preço de um gelado, em euros;

f) o código postal de uma morada, como 4000-123.

Rever: [O tipo diz que valores uma variável guarda](../02-estado-sequencia-representacoes.md#o-tipo-diz-que-valores-uma-variável-guarda).

<details>
<summary>Pista</summary>

Pergunta-te o que farias com o valor. Se fosses fazer contas com ele, é um número: tem parte decimal? Se não fosses, que tipo serve?

</details>

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

b) Agora imagina que a segunda e a terceira linhas trocam de lugar, ficando `x = x * 3` antes de `int y = x + 2`. Faz a tabela de trace de raiz, com as mesmas colunas. Quanto valem `x` e `y` no fim? Explica numa frase porque é que o resultado mudou, se as instruções são as mesmas.

Rever: [Atribuição: dar um valor não é perguntar se é igual](../02-estado-sequencia-representacoes.md#atribuição-dar-um-valor-não-é-perguntar-se-é-igual) e [Tabela de trace](../02-estado-sequencia-representacoes.md#tabela-de-trace).

<details>
<summary>Pista</summary>

Copia os valores da linha de cima e muda só a coluna da variável à esquerda do `=`. Numa conta, usa os valores que as variáveis têm nesse momento.

</details>

## Exercício 3: Contas com `div` e `resto`

Calcula à mão e confirma cada par: o divisor vezes a divisão inteira, mais o resto, tem de dar o número de partida.

a) `47 div 6` e `47 resto 6`

b) `6 div 47` e `6 resto 47`

c) `0 div 9` e `0 resto 9`

d) Quantas semanas completas há em 23 dias, e quantos dias sobram? Escreve as duas contas, com `div` e `resto`, e calcula-as.

Escolhe o par que te fez pensar mais e explica o resultado com rebuçados e amigos, como no guia.

Rever: [Operadores aritméticos](../02-estado-sequencia-representacoes.md#operadores-aritméticos).

<details>
<summary>Pista</summary>

Na alínea d), pergunta-te o que faz aqui o papel dos amigos.

</details>

## Exercício 4: A placa de madeira

Lê o enunciado:

> Um carpinteiro corta placas retangulares de madeira. Para cada placa, quer saber o comprimento da fita que vai colar à volta do rebordo, que é o perímetro. Quer saber também a área da placa, para saber quanto verniz vai gastar. Mede o comprimento e a largura em metros, e podem ter parte decimal, como 1,2 metros.

a) Escreve o contrato: as entradas, com a unidade e os limites, as saídas, com a unidade, e três exemplos concretos calculados à mão. O que o enunciado não disser, decides e escreves. Um dos exemplos tem de ser uma placa quadrada.

b) Escreve o algoritmo. O resultado tem de aparecer no ecrã com as unidades: o perímetro em metros e a área em metros quadrados.

c) Faz o trace do teu algoritmo para um dos teus exemplos e confirma que dá o que o contrato previu.

Rever: [Exemplo guiado: converter minutos em horas e minutos](../02-estado-sequencia-representacoes.md#exemplo-guiado-converter-minutos-em-horas-e-minutos).

<details>
<summary>Pista</summary>

Para o perímetro, pensa nos quatro lados da placa. Para o ecrã, as unidades vão dentro das aspas do `Escreve:`.

</details>

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

a) Calcula à mão quanto devia pagar quem compra 4 cadernos de 2 euros, já com o desconto. Depois faz o trace com esses valores. Em que passo é que um valor passa a ser diferente do que devia, e o que diz a tabela nesse passo?

b) Corrige o algoritmo, mudando o menos possível e sem deixar linhas inúteis. Faz outra vez o trace com os mesmos valores e confirma que dá o que calculaste.

Rever: [Tabela de trace](../02-estado-sequencia-representacoes.md#tabela-de-trace).

<details>
<summary>Pista</summary>

Faz cada conta com os valores que estão na linha de cima, e não com os que achas que deviam estar. Quando o total não for o que calculaste, procura a linha onde foi calculado e vê que valores usou.

</details>

## Exercício 6: Andares do elevador

Num prédio, o rés-do-chão é o andar 0 e a garagem é o andar -1. Os andares de cima são 1, 2, 3 e assim por diante. O elevador está num andar, e alguém o chama de outro.

a) Escreve o algoritmo que lê o andar onde o elevador está e o andar de onde foi chamado. O algoritmo mostra quantos andares o elevador vai percorrer.

b) Testa-o com três casos: o elevador no 3 chamado do 7, no 7 chamado do 3, e no 2 chamado da garagem. Escreve o que aparece no ecrã em cada um. Compara os dois primeiros: o que aparece faz sentido para um elevador? Explica numa frase.

Rever: [Exemplo guiado: converter minutos em horas e minutos](../02-estado-sequencia-representacoes.md#exemplo-guiado-converter-minutos-em-horas-e-minutos).

<details>
<summary>Pista</summary>

Experimenta o teu algoritmo com os dois primeiros casos. Pode um elevador percorrer esse número de andares?

</details>

## Desafios

### Desafio 1: Trocar os valores de duas variáveis

No guia viste que as duas linhas `a = b` e `b = a` não trocam os valores de duas variáveis.

Escreve as linhas que trocam mesmo os valores de duas variáveis inteiras `a` e `b`, sem perder nenhum. Depois faz o trace com `a` a valer 4 e `b` a valer 9. No fim, `a` tem de valer 9 e `b` tem de valer 4.

## Critérios de conclusão

- No exercício 1, escolheste cada tipo pelo que o valor representa, e justificaste.
- Nas tabelas de trace, mudaste em cada linha só a variável da esquerda do `=` e fizeste as contas que estavam escritas.
- No exercício 2, as duas versões têm o estado final certo, e a tua explicação fala da ordem.
- No exercício 3, calculaste os quatro pares e verificaste cada um, e explicaste com rebuçados e amigos o par que te fez pensar mais.
- No exercício 4, o contrato tem unidades, limites e uma placa quadrada. O ecrã mostra as unidades, e o trace deu o que o contrato previa.
- No exercício 5, encontraste o passo onde o algoritmo se engana e corrigiste-o, e a versão corrigida dá o que calculaste à mão.
- No exercício 6, o ecrã mostra, nos três casos, os andares que o elevador percorre mesmo, e explicaste o que viste nos dois primeiros.

![Rodapé](../../imagens/rodape.png)
