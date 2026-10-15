![Cabeçalho](../imagens/cabecalho.png)

# Ficha de exercícios: Funções e modelo integrado

Ficha do tema Funções e modelo integrado, do módulo Desenvolver algoritmos. Treinas o que aprendeste no guia, uma ideia em cada exercício. Lês e chamas funções, distingues parâmetros de argumentos e escreves funções com `Função` e `devolver`. Usas funções que devolvem `true` ou `false`, passas um valor que muda o que uma função conta e encontras erros em funções. No fim, montas o dossiê de um problema pequeno. Cerca de 130 minutos, para fazeres sozinho: 110 na parte obrigatória e 20 no desafio opcional.

## O que precisas de saber

O [guia do tema](05-funcoes-e-modelo-integrado.md). Antes de começar, deves conseguir explicar:

- as quatro fases de uma chamada;
- a diferença entre `devolver` e `Escreve:`;
- porque é que uma função só usa os seus parâmetros, as suas variáveis e as constantes.

Se alguma destas ideias não estiver clara, volta à secção do guia que a explica. São as secções "Chamar uma função" e "`devolver`". Para o exercício 3 precisas também do `resto`, do [guia 02](02-estado-sequencia-representacoes.md), secção "Operadores aritméticos".

Este tema não tem laboratório. Os exercícios fazem-se em papel.

## Como trabalhar

Resolve os exercícios pela ordem. Cada um treina uma ideia do guia:

| Exercício | O que treina | Tempo |
| --- | --- | ---: |
| 1 | Ler uma função e escrever o seu contrato | 10 min |
| 2 | Parâmetros e argumentos | 10 min |
| 3 | Escrever uma função que percorre um array, com o trace da chamada | 15 min |
| 4 | Uma função que devolve `true` ou `false`, usada num `Se` | 10 min |
| 5 | Uma função que recebe o limiar | 15 min |
| 6 | Encontrar o erro numa função, com o registo de depuração | 20 min |
| 7 | O dossiê de um problema, com três funções | 30 min |
| Total da parte obrigatória | Exercícios 1 a 7 | 110 min |
| Desafio opcional | Duas soluções certas, contadas em voltas | 20 min |

Os exercícios 1 a 7 são obrigatórios e cabem nos 110 minutos. Depois do desafio, a secção "Para ires mais longe" tem os testes do dossiê do exercício 7, também opcionais. É para quem terminar e quiser mais prática, ou para estudares em casa. Nem o desafio nem essa secção contam para concluíres a ficha.

Escreve as funções na forma que usamos nas aulas. O cabeçalho leva `Função`, o nome e os parâmetros entre parênteses. O corpo vai indentado, e o resultado entrega-se com `devolver`. As funções escrevem-se antes do algoritmo principal.

Escreve sempre o contrato de cada função que escreveres: o que recebe, o que devolve e um ou dois exemplos. Se souberes a lógica e não te lembrares da forma, escreve frases claras. Têm de dizer o que a função recebe, o que faz e o que devolve.

O exercício 5 parte do exercício 3, e o exercício 7 usa a função do exercício 5. Guarda as tuas respostas à medida que avanças.

Entregas as respostas em papel ou num ficheiro de texto. O exercício 7 é o teu dossiê algorítmico.

## Exercício 1: Ler uma função (10 minutos)

```text
Função maior(a, b)
    Se a > b
        devolver a
    Senão
        devolver b
```

a) O que devolve `maior(3, 8)`? E `maior(8, 3)`? E `maior(5, 5)`?

b) Que valor fica em `x` depois de `int x = maior(4, 9) + maior(2, 1)`?

c) Escreve o contrato desta função. Tem de dizer o que acontece quando os dois números são iguais.

## Exercício 2: Parâmetros e argumentos (10 minutos)

Uma escola calcula a nota final de uma disciplina com 70% da nota do teste e 30% da nota do trabalho:

```text
Função notaFinal(teste, trabalho)
    devolver teste * 0.7 + trabalho * 0.3
```

a) Quais são os parâmetros desta função? Na chamada `notaFinal(15, 10)`, quais são os argumentos?

b) Calcula o que devolvem `notaFinal(15, 10)` e `notaFinal(10, 15)`.

c) Um aluno teve 15 no teste e 10 no trabalho. Qual das duas chamadas da alínea b) dá a sua nota final? Explica porque é que a outra dá um valor diferente.

## Exercício 3: Escrever uma função com um ciclo (15 minutos)

Vais escrever a função `contarPares(numeros)`. Recebe um array de números inteiros e devolve quantos deles são pares. Um número é par quando o resto da divisão por 2 é 0.

a) Antes de escreveres a função, escreve o seu contrato. Dá exemplos para `[4, 7, 10, 3]`, para `[]` e para `[5]`, com o valor devolvido contado à mão.

b) Escreve a função.

c) Faz o trace da chamada `contarPares([4, 7, 10, 3])` em tabela própria, com uma linha por volta. A tabela já tem as duas primeiras linhas. Completa as outras com a tua função. Se o teu contador tiver outro nome, usa-o na última coluna. No fim, escreve o valor que a função devolve.

| Volta | numero | A condição do teu `Se` dá | pares no fim da volta |
| --- | ---: | --- | ---: |
| antes do ciclo | sem valor | nenhuma | 0 |
| 1.ª | 4 | `true` | 1 |
| 2.ª | | | |
| 3.ª | | | |
| 4.ª | | | |

## Exercício 4: Uma função que responde sim ou não (10 minutos)

a) Escreve a função `horaValida(hora, minuto)`. Devolve `true` se a hora estiver entre 0 e 23 e os minutos entre 0 e 59, incluindo os extremos. Devolve `false` em todos os outros casos.

b) Escreve as linhas do algoritmo principal que leem uma hora e uns minutos. Escrevem "Hora válida" ou "Hora inválida", e usam a tua função num `Se`.

c) Olha para estas quatro horas: 23:59, 24:00, 12:60 e 0:00. Antes de seguires a tua função, decide a partir do enunciado se cada uma é válida. Depois diz o que a tua função devolve para cada uma, e confirma que dá o que decidiste.

## Exercício 5: Um limiar que muda (15 minutos)

As temperaturas máximas de uma semana ficaram neste array:

```text
temperaturas = [18, 25, 31, 22, 35, 28]
```

a) Escreve a função `contarAcima(valores, limiar)`. Recebe um array e um número, e devolve quantos valores do array são maiores do que esse número.

b) Conta à mão, no array, quantos dias tiveram mais de 30 graus e quantos tiveram mais de 25 graus. Depois escreve as linhas do algoritmo principal que mostram as duas contagens, chamando a mesma função duas vezes.

c) Explica, numa ou duas frases, o que mudou entre as duas chamadas. Porque é que não foi preciso mudar nada dentro da função?

## Exercício 6: Encontrar o erro (20 minutos)

Cada uma destas funções tem um erro. Procura-o pela ordem que o guia dá no início de "Erros frequentes". Escreve o que encontrares num registo de depuração, com quatro partes:

- o que observaste: a chamada que mostra o erro e o que a função devolve com ela;
- o que era esperado: o que a função devia devolver nessa chamada, tirado do enunciado;
- a causa: a linha que produz o erro, confirmada com o trace da chamada;
- a correção: a função corrigida, mudando o mínimo possível.

Depois volta a fazer as duas chamadas de cada alínea com a função corrigida, e confirma que as duas dão o esperado.

a) Esta função devia devolver o preço, em euros, de um bilhete de cinema. Custa 3 euros para quem tem menos de 12 anos e 4 euros para quem tem 65 anos ou mais. Para as outras idades custa 6 euros.

```text
Função precoBilhete(idade)
    Se idade < 12
        devolver 3
    Senão se idade > 12 e idade < 65
        devolver 6
    Senão se idade >= 65
        devolver 4
```

Usa as chamadas `precoBilhete(40)` e `precoBilhete(12)` como exemplos.

b) Esta função devia devolver o total de golos marcados por uma equipa num torneio, com os golos de cada jogo guardados num array:

```text
Função totalGolos(golosPorJogo)
    int total = 0
    Para cada golos em golosPorJogo
        total = total + golos
        devolver total
```

Usa as chamadas `totalGolos([2, 0, 3])` e `totalGolos([4])` como exemplos. Uma delas dá o resultado certo por acaso.

## Exercício 7: O dossiê da semana de passos (30 minutos)

Este exercício junta toda a algoritmia, e é o teu dossiê. Aqui fazes as partes do dossiê que vêm antes dos testes: a análise, a decomposição, o contrato de cada função e o algoritmo. Os testes, a última parte, estão no Mais longe 1, no fim da ficha, que é opcional.

Vais usar três funções. A função `media` é a do guia, e a função `contarAcima` é a do exercício 5. Estas duas já estão escritas, e não precisas de as escrever outra vez. Escreve só o nome e o contrato de cada uma. A terceira é a função `existe`, na versão corrigida que a secção "Erros frequentes" do guia descreve por palavras. Como o guia não a escreve por inteiro, escreve-a tu, com o seu contrato, antes do algoritmo principal.

> Uma aplicação de exercício guardou os passos dados em cada dia de uma semana: `passos = [8200, 0, 10300, 7500, 12000, 6000, 5000]`. O objetivo diário é passar dos 8000 passos. O algoritmo mostra a média de passos por dia e em quantos dias o objetivo foi cumprido. Se houver algum dia com 0 passos, escreve também "Houve pelo menos um dia sem passos".

a) Análise. Escreve o contrato do problema, com as entradas, as saídas e as restrições. Calcula à mão o resultado esperado para a semana do enunciado.

b) Decomposição. Completa a tabela das funções que vais usar, com o que cada uma recebe e o que devolve. A primeira linha já está feita. Depois escreve o contrato de cada função e a função `existe`.

| Função | Recebe | Devolve |
| --- | --- | --- |
| `media(valores)` | um array de números, com pelo menos um elemento | a média desses números |
| `contarAcima(valores, limiar)` | | |
| `existe(valores, procurado)` | | |

c) Algoritmo principal. Escreve o algoritmo principal, que chama as três funções e mostra os resultados. Usa uma constante para o objetivo.

## Apoio

Se estiveres encravado, usa estas pistas pela ordem em que aparecem, e passa à seguinte só se a anterior não tiver chegado.

- Exercício 1. Substitui `a` e `b` pelos argumentos e segue o `Se`. Na alínea b), resolve cada chamada sozinha e só depois soma.
- Exercício 2. Os parâmetros estão no cabeçalho, e os argumentos estão na chamada. Os argumentos passam para os parâmetros pela ordem.
- Exercício 3. É um contador dentro de uma função, como `contarPositivas` no exemplo guiado do guia. Que operação do guia 02 te dá o resto de uma divisão? No fim do ciclo, devolve o contador.
- Exercício 4. Escreve primeiro uma condição só para a hora, e outra só para os minutos. Depois pensa numa hora como 10:75, em que a hora está bem e os minutos não. A função deve devolver `true` ou `false`?
- Exercício 5. É o contador com um `Se`, como no exercício 3. A condição compara cada valor com o parâmetro `limiar`, em vez de um número escrito.
- Exercício 6. Em cada alínea, escreve primeiro o que a função devia devolver em cada chamada, tirado do enunciado. Depois faz o trace de cada chamada em tabela própria, linha a linha, e compara.
- Exercício 7. Volta ao passo 8 do exemplo guiado, que mostra as cinco partes de um dossiê. As alíneas a) a c), com os contratos, são as quatro primeiras, e a quinta, os testes, é o Mais longe 1. Lê a pré-condição de `media`: o array do enunciado cumpre-a?

## Desafio opcional

Leva cerca de 20 minutos.

Na semana de passos, a diretora da aplicação quer saber também quantos dias ficaram acima da média da semana, e não do objetivo.

a) Escreve uma solução que chama `media(passos)` dentro do ciclo, em cada comparação, e outra que a calcula uma vez antes do ciclo.

b) Conta, para os 7 dias, quantas voltas de ciclo faz cada solução. Soma as voltas dentro da função e as do ciclo do algoritmo principal.

c) As duas soluções dão o mesmo resultado? Quantos dias ficaram acima da média?

## Para ires mais longe

Esta secção é opcional e fica fora dos 110 minutos da ficha. Não precisas de fazer nada daqui para concluíres a ficha, e os critérios de conclusão não a contam. Serve para quem terminou a parte obrigatória e quer mais prática, ou para estudares em casa. O tempo é indicativo.

### Mais longe 1: Os testes do dossiê (30 minutos)

Continua o exercício 7, com o teu dossiê da semana de passos. Com estas duas alíneas, o dossiê fica com as cinco partes do passo 8 do guia.

a) Teste completo. Faz o teste completo, chamada a chamada, para a semana do enunciado. Confirma que dá o que previste na alínea a) do exercício 7. Escolhe tu como mostras cada chamada: em tabela própria, como no passo 7 do exemplo guiado, ou só com as voltas e o valor devolvido.

b) Um segundo caso. Escolhe outra semana, com 3 dias e nenhum dia a zero. Escolhe-a de maneira a testar uma coisa que a semana do enunciado não testa. Calcula à mão o resultado esperado, e confirma que o algoritmo o dá.

Os dois testes têm de dar o que previste.

## Critérios de conclusão

- [ ] No exercício 1, tenho os quatro valores, e o contrato diz o que acontece quando os dois números são iguais.
- [ ] No exercício 2, apontei os parâmetros e os argumentos. Expliquei, com as duas contas, porque é que a ordem conta.
- [ ] No exercício 3, contei à mão os pares dos três exemplos antes de escrever a função. A função devolve esses três valores, e o trace confirma o primeiro.
- [ ] No exercício 4, decidi a partir do enunciado, antes de seguir a função, se cada uma das quatro horas é válida. A minha função dá o que decidi nas quatro.
- [ ] No exercício 5, contei à mão os dias acima de cada limiar. As duas chamadas dão essas contagens, e a minha explicação fala do argumento.
- [ ] No exercício 6, cada alínea tem as quatro partes do registo. A função corrigida dá o esperado nas duas chamadas.
- [ ] No exercício 7, o dossiê tem a análise, com o resultado esperado calculado à mão. Tem a tabela da decomposição e o contrato de cada uma das três funções. Tem também a função `existe` escrita e o algoritmo principal a chamar as três.
- [ ] Em todas as minhas funções, todos os caminhos chegam a um `devolver`.
- [ ] As minhas funções devolvem os resultados, e quem escreve no ecrã é o algoritmo principal.
- [ ] As minhas funções só usam os seus parâmetros, as suas variáveis e as constantes.

## Autoavaliação

1. O que já consegues fazer sozinho?
2. Que dificuldade tiveste, e o que fizeste para a resolver?

![Rodapé](../imagens/rodape.png)
