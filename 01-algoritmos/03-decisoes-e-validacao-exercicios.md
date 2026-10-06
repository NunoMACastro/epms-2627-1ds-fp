![Cabeçalho](../imagens/cabecalho.png)

# Ficha de exercícios: Decisões e validação

| Identificação | Valor |
| --- | --- |
| Disciplina | Fundamentos de Programação, 10.º ano, Desenvolvimento de Software |
| Unidade de competência | UC00245, Desenvolver algoritmos |
| Material | Ficha do terceiro tema, acompanha o [guia](03-decisoes-e-validacao.md) |
| Tempo | 85 minutos de exercícios e 20 minutos de desafio opcional |
| Entrega | As respostas em papel ou num ficheiro de texto, com as tabelas de casos e os traces |

## Antes de começares

Esta ficha treina o que aprendeste no guia: avaliar comparações, juntar condições com `e`, `ou` e `não`, prever por que ramo segue uma seleção encadeada, escrever um intervalo e o seu contrário, escolher casos de teste nas fronteiras, validar uma entrada e encontrar o valor que mostra um erro.

Antes de começar, deves conseguir explicar a diferença entre `<` e `<=`, as tabelas de verdade do `e` e do `ou`, e a regra da seleção encadeada: a primeira condição verdadeira ganha. Se alguma destas ideias não estiver clara, volta à secção do guia que a explica.

Escreve os algoritmos na forma que usamos nas aulas, com a indentação a mostrar o que está dentro de cada caso. Se souberes a lógica e não te lembrares da forma, escreve frases claras que digam o que acontece em cada caso, incluindo quando um valor não serve.

Os desenhos de fluxogramas não fazem parte desta ficha. Se o professor indicar o [laboratório](03-decisoes-e-validacao-laboratorio.md) deste tema, é lá que os desenhas.

## Exercício 1: Verdadeiro ou falso (10 min)

A variável `idade` vale 16. Para cada condição, diz se dá `true` ou `false`:

a) `idade >= 16`

b) `idade > 16`

c) `idade == 18`

d) `idade != 16`

e) `idade < 18`

f) `idade <= 15`

Depois escolhe duas das condições que deram resultados diferentes só por causa do igual, e explica a diferença numa frase.

Concluíste quando tiveres os seis resultados e a explicação.

## Exercício 2: Juntar condições (10 min)

Num parque de diversões, a montanha-russa tem duas regras: só entra quem tiver pelo menos 12 anos e pelo menos 1.40 metros de altura.

a) A variável `idade` vale 15 e a variável `altura` vale 1.45. Diz se cada condição dá `true` ou `false`:

- `idade >= 12 e altura >= 1.40`
- `idade >= 18 e altura >= 1.40`
- `idade >= 18 ou altura >= 1.40`
- `não (idade >= 18)`

b) Qual das quatro condições é a regra da montanha-russa? Explica porque é que tem de ser com `e`, e não com `ou`.

Concluíste quando tiveres os quatro resultados e a explicação da alínea b).

## Exercício 3: Prever o ramo (10 min)

Lê este algoritmo de um cinema, sem o executar:

```text
Escreve: "Idade?"
int idade = ler valor
Se idade < 12
    Escreve: "Bilhete de criança"
Senão se idade < 65
    Escreve: "Bilhete normal"
Senão
    Escreve: "Bilhete sénior"
```

a) Diz que mensagem aparece para cada uma destas idades: 5, 11, 12, 40, 64 e 65.

b) A condição do `Senão se` é só `idade < 65`. Porque é que não precisa de dizer também `idade >= 12`?

Concluíste quando tiveres as seis mensagens e a explicação da alínea b) usar a regra da seleção encadeada.

## Exercício 4: A estufa (15 min)

Numa estufa de tomates, a temperatura está boa entre 18 e 26 graus, incluindo os dois extremos. As temperaturas são números inteiros.

a) Escreve a condição que diz se a temperatura está boa.

b) Escreve a condição que diz se a temperatura está fora do bom, sem usar `não`.

c) Para as temperaturas 17, 18, 22, 26 e 27, diz se a temperatura está boa ou fora, e confirma que as tuas duas condições dão sempre respostas contrárias.

Concluíste quando as duas condições derem respostas contrárias nos cinco casos.

## Exercício 5: O preço das fotocópias (25 min)

Lê o enunciado:

> A papelaria da escola cobra as fotocópias por esta tabela: de 1 a 10 cópias, cada cópia custa 0.10 euros; de 11 a 50 cópias, cada cópia custa 0.08 euros; mais de 50 cópias, cada cópia custa 0.05 euros. O preço de cada cópia aplica-se a todas as cópias do pedido: 20 cópias custam 20 vezes 0.08 euros. Um pedido com 0 cópias, ou com um número negativo, é inválido, e o algoritmo escreve "Pedido inválido" em vez de um preço.

Usa só as regras da tabela. Não acrescentes descontos, arredondamentos nem outras regras que conheças de lojas verdadeiras.

a) Desenha a reta dos números de cópias, como no passo 3 do guia, e marca as regiões e as fronteiras.

b) Escreve a tabela de casos de teste, com o resultado esperado calculado à mão. Para cada fronteira, testa os dois valores que ficam um de cada lado dela, como o 10 e o 11.

c) Escreve o algoritmo em pseudocódigo, ou em frases claras. Usa constantes para os preços e para os limites.

d) Faz o trace de dois casos de fronteira à tua escolha e confirma que dão o que previste.

Concluíste quando todos os casos da tua tabela derem, no trace ou à mão pelo teu algoritmo, o resultado que previste antes de o escrever.

## Exercício 6: Encontrar o erro (15 min)

Cada um destes bocados de algoritmo tem um erro. Para cada um, diz qual é a entrada que mostra o erro, o que aparece com essa entrada e o que devia aparecer, e escreve a linha corrigida.

a) Os dias do mês vão de 1 a 31. Este bocado devia apanhar os dias inválidos:

```text
Se dia < 1 e dia > 31
    Escreve: "Dia inválido"
```

b) A loja dá um desconto a quem compra 3 ou mais cadernos:

```text
Se quantidade > 3
    Escreve: "Tem desconto"
Senão
    Escreve: "Sem desconto"
```

Concluíste quando, para cada alínea, tiveres uma entrada concreta que mostra o erro e a correção.

## Apoio

Se estiveres encravado, usa estas pistas pela ordem em que aparecem, e passa à seguinte só se a anterior não tiver chegado.

Exercício 1. Substitui `idade` por 16 e lê cada condição em voz alta: "dezasseis é maior ou igual a dezasseis?". Nas que têm igual, pergunta-te se o 16 está incluído.

Exercício 2. Avalia primeiro cada comparação sozinha, e só depois junta com a tabela de verdade do `e` ou do `ou`.

Exercício 3. Para cada idade, começa na primeira condição e desce. Para assim que uma condição for verdadeira: as de baixo já não contam.

Exercício 4. O intervalo é "entre isto e aquilo", com `e`. O contrário é "abaixo disto ou acima daquilo", com `ou`, e cada limite muda de lado: `>= 18` passa a `< 18`.

Exercício 5. As fronteiras estão entre 0 e 1, entre 10 e 11 e entre 50 e 51. Põe a validação no primeiro `Se`, como no exemplo guiado, e repara que depois de cada `Senão se` já sabes que as condições de cima foram falsas.

Exercício 6. Na alínea a), experimenta um dia que de certeza é inválido, como 0 ou 32, e calcula a condição com as duas comparações. Na alínea b), o erro só aparece num valor: o da própria fronteira.

## Desafio opcional (20 min)

Um ano é bissexto, e tem 29 de fevereiro, quando é divisível por 4 e não é divisível por 100, ou quando é divisível por 400. Um número é divisível por outro quando o resto da divisão é 0, e o resto escreve-se com `resto`, como aprendeste no guia anterior.

a) Escreve a condição que diz se um ano é bissexto. Como mistura `e` com `ou`, usa parênteses para mostrar o que se avalia primeiro.

b) Testa-a com os anos 2024, 2023, 1900 e 2000, e diz quais são bissextos.

c) Qual destes quatro anos mostra que a regra dos 100 é precisa? E qual mostra que a regra dos 400 é precisa?

## Critérios de conclusão

- [ ] Avaliei cada comparação com o valor que a variável tinha, incluindo os casos em que o valor era igual ao limite.
- [ ] Usei `e` para "entre" e `ou` para "fora", e pus cada limite do lado certo.
- [ ] Previ o ramo de cada caso numa seleção encadeada, parando na primeira condição verdadeira.
- [ ] Escolhi os casos de teste nas fronteiras e escrevi o resultado esperado antes de escrever o algoritmo.
- [ ] Pus a validação antes da classificação.
- [ ] Para cada erro, mostrei a entrada que o revela.
- [ ] Usei só as regras que os enunciados deram.

## Autoavaliação breve

O que já consigo fazer sozinho:

Uma dificuldade que tive e o que fiz para a resolver:

![Rodapé](../imagens/rodape.png)
