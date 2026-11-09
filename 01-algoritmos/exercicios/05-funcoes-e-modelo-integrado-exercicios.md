![Cabeçalho](../../imagens/cabecalho.png)

# Ficha de exercícios: Funções e modelo integrado

Lês e chamas funções, distingues parâmetros de argumentos e escreves funções com `devolver`. Passas um valor que muda o que uma função conta, encontras erros e começas o dossiê de um problema pequeno. Os exercícios 1 a 7 são obrigatórios, e fazem-se em papel ou num ficheiro de texto. Escreve sempre o contrato de cada função que escreveres, e guarda as respostas, porque o exercício 7 usa a função do exercício 5. Para rever: o [guia do tema](../05-funcoes-e-modelo-integrado.md).

## Exercício 1: Ler uma função

```text
Função maior(a, b)
    Se a > b
        devolver a
    Senão
        devolver b
```

a) O que devolve `maior(7, 12)`? E `maior(12, 7)`? E `maior(5, 5)`?

b) Que valor fica em `x` depois de `int x = maior(4, 9) + maior(2, 1)`?

c) Escreve o contrato desta função. Tem de dizer o que acontece quando os dois números são iguais.

Rever: [Escrever uma função](../05-funcoes-e-modelo-integrado.md#escrever-uma-função) e [`devolver`](../05-funcoes-e-modelo-integrado.md#devolver).

<details>
<summary>Pista</summary>

Substitui `a` e `b` pelos argumentos e segue o `Se`. Na alínea b), resolve cada chamada sozinha e só depois soma.

</details>

## Exercício 2: Parâmetros e argumentos

Uma escola calcula a nota final de uma disciplina com 70% da nota do teste e 30% da nota do trabalho:

```text
Função notaFinal(teste, trabalho)
    devolver teste * 0.7 + trabalho * 0.3
```

a) Quais são os parâmetros desta função? Na chamada `notaFinal(15, 10)`, quais são os argumentos?

b) Calcula o que devolvem `notaFinal(15, 10)` e `notaFinal(10, 15)`.

c) Um aluno teve 15 no teste e 10 no trabalho. Qual das duas chamadas da alínea b) dá a sua nota final? Explica porque é que a outra dá um valor diferente.

Rever: [Chamar uma função](../05-funcoes-e-modelo-integrado.md#chamar-uma-função) e [A ordem dos argumentos conta](../05-funcoes-e-modelo-integrado.md#a-ordem-dos-argumentos-conta).

<details>
<summary>Pista</summary>

Os parâmetros estão no cabeçalho, e os argumentos estão na chamada.

</details>

## Exercício 3: Escrever uma função com um ciclo

Vais escrever a função `contarPares(numeros)`. Recebe um array de números inteiros e devolve quantos deles são pares. Um número é par quando o resto da divisão por 2 é 0.

a) Antes de escreveres a função, escreve o seu contrato. Dá exemplos para `[4, 7, 10, 3]`, para `[]` e para `[5]`, com o valor devolvido contado à mão.

b) Escreve a função.

c) Faz o trace da chamada `contarPares([4, 7, 10, 3])` em tabela própria, com uma linha por volta. A tabela já tem as duas primeiras linhas. Completa as outras com a tua função. Se o teu contador ou a tua variável do ciclo tiverem outro nome, usa esse nome na coluna. No fim, escreve o valor que a função devolve.

| Volta | numero | A condição do teu `Se` dá | pares no fim da volta |
| --- | ---: | --- | ---: |
| antes do ciclo | sem valor | nenhuma | 0 |
| 1.ª | 4 | `true` | 1 |
| 2.ª | | | |
| 3.ª | | | |
| 4.ª | | | |

Rever: [Funções que recebem arrays](../05-funcoes-e-modelo-integrado.md#funções-que-recebem-arrays), [O trace de uma chamada](../05-funcoes-e-modelo-integrado.md#o-trace-de-uma-chamada) e [Operadores aritméticos](../02-estado-sequencia-representacoes.md#operadores-aritméticos).

<details>
<summary>Pista</summary>

Que operação do guia 02 te dá o resto de uma divisão? O que tem de entregar a função, no fim do ciclo?

</details>

## Exercício 4: Uma função que responde sim ou não

a) Escreve a função `horaValida(hora, minuto)`. Devolve `true` se a hora estiver entre 0 e 23 e os minutos entre 0 e 59, incluindo os extremos. Devolve `false` em todos os outros casos.

b) Olha para estas seis horas: 23:59, 24:00, 12:60, 0:00, -1:30 e 10:-1. As duas últimas têm um número negativo, a hora -1 e os minutos -1. Antes de seguires a tua função, decide a partir do enunciado se cada uma é válida. Depois diz o que a tua função devolve para cada uma, e confirma que dá o que decidiste.

Rever: [Funções que devolvem `true` ou `false`](../05-funcoes-e-modelo-integrado.md#funções-que-devolvem-true-ou-false).

<details>
<summary>Pista</summary>

Escreve primeiro uma condição só para a hora, e outra só para os minutos. Depois pensa numa hora como 10:75, em que a hora está bem e os minutos não.

</details>

## Exercício 5: A mesma função, duas contagens

As temperaturas máximas de seis dias seguidos ficaram neste array:

```text
temperaturas = [18, 25, 31, 22, 35, 28]
```

a) Escreve a função `contarAcima(valores, limiar)`. Recebe um array e um número, e devolve quantos valores do array são maiores do que esse número.

b) Conta à mão, no array, quantos dias tiveram mais de 30 graus e quantos tiveram mais de 25 graus. Depois escreve as linhas do algoritmo principal que mostram as duas contagens, chamando a mesma função duas vezes.

c) Explica, numa ou duas frases, o que mudou entre as duas chamadas. Porque é que não foi preciso mudar nada dentro da função?

Rever: [Funções que recebem arrays](../05-funcoes-e-modelo-integrado.md#funções-que-recebem-arrays) e [Chamar uma função](../05-funcoes-e-modelo-integrado.md#chamar-uma-função).

<details>
<summary>Pista</summary>

A condição compara cada valor com o que chegou pelo parâmetro.

</details>

## Exercício 6: Encontrar o erro

A função devia devolver o preço, em euros, de um bilhete de cinema. Custa 3 euros para quem tem menos de 12 anos e 4 euros para quem tem 65 anos ou mais. Para as outras idades custa 6 euros.

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

Esta função tem um erro. Procura-o pela ordem que o guia dá no início de "Erros frequentes". Depurar é encontrar e corrigir um erro. Escreve o que encontrares num registo de depuração, com quatro partes:

- o que se observou: a chamada que mostra o erro e o que acontece nessa chamada;
- o que se esperava: o que a função devia devolver nessa chamada, tirado do enunciado;
- a causa: primeiro, numa frase, o que achas que causa o erro; depois, a linha do trace da chamada que o confirma;
- a correção: a função corrigida, mudando o mínimo possível.

Depois volta a fazer as duas chamadas com a função corrigida, e confirma que as duas dão o esperado.

Rever: [Erros frequentes](../05-funcoes-e-modelo-integrado.md#erros-frequentes) e [O trace de uma chamada](../05-funcoes-e-modelo-integrado.md#o-trace-de-uma-chamada).

<details>
<summary>Pista</summary>

Escreve primeiro o que a função devia devolver em cada chamada, tirado do enunciado. Depois faz o trace, em tabela própria, com uma coluna para cada condição, da chamada que não dá o esperado.

</details>

## Exercício 7: O dossiê da semana de passos

Este exercício junta toda a algoritmia, e é o começo do teu dossiê. Aqui fazes as partes do dossiê que vêm antes do algoritmo: a análise, a decomposição e o contrato de cada função. As duas últimas partes, o algoritmo e os testes, estão nos desafios 4 e 5.

Vais usar três funções. A função `media` é a do guia, e a função `contarAcima` é a do exercício 5. A terceira é a função `existe`, na versão corrigida que a secção "Erros frequentes" do guia descreve por palavras. Aqui não escreves nenhuma das três: escreves a chamada e o contrato de cada uma.

> Uma aplicação do telemóvel guardou os passos dados em cada dia de uma semana: `passos = [8200, 0, 10300, 7500, 12000, 6000, 5000]`. O objetivo diário é passar dos 8000 passos. O algoritmo mostra a média de passos por dia e em quantos dias o objetivo foi cumprido. Se houver algum dia com 0 passos, escreve também "Houve pelo menos um dia sem passos".

a) Análise. Escreve o contrato do problema, com as entradas, as saídas e as restrições. Calcula à mão o resultado esperado para a semana do enunciado.

b) Decomposição. Completa a tabela das funções que vais usar, com o que cada uma recebe e o que devolve. Na última coluna, escreve a chamada que responde à pergunta do enunciado, com os argumentos. A primeira linha já está feita.

| Função | Recebe | Devolve | A chamada neste problema |
| --- | --- | --- | --- |
| `media(valores)` | um array de números, com pelo menos um elemento | a média desses números | `media(passos)` |
| `contarAcima(valores, limiar)` | | | |
| `existe(valores, procurado)` | | | |

c) Contratos. Escreve o contrato de cada uma das três funções, com dois exemplos cada.

Rever: [O dossiê do problema](../05-funcoes-e-modelo-integrado.md#o-dossiê-do-problema), [Funções que recebem arrays](../05-funcoes-e-modelo-integrado.md#funções-que-recebem-arrays) e [Erros frequentes](../05-funcoes-e-modelo-integrado.md#erros-frequentes).

<details>
<summary>Pista</summary>

Na tabela, pergunta-te que valor faz cada função responder à pergunta do enunciado. O array do enunciado cumpre a pré-condição de `media`?

</details>

## Desafios

### Desafio 1: Duas soluções certas

Na semana de passos, a diretora da aplicação quer saber também quantos dias ficaram acima da média da semana, e não do objetivo.

a) Escreve uma solução que chama `media(passos)` dentro do ciclo, em cada comparação, e outra que a calcula uma vez antes do ciclo.

b) Conta, para os 7 dias, quantas voltas de ciclo faz cada solução. Soma as voltas dentro da função e as do ciclo do algoritmo principal.

c) As duas soluções dão o mesmo resultado? Quantos dias ficaram acima da média?

Rever: [Duas soluções certas, uma mais eficiente](../05-funcoes-e-modelo-integrado.md#duas-soluções-certas-uma-mais-eficiente).

### Desafio 2: A hora no algoritmo principal

Continua o exercício 4. Escreve as linhas do algoritmo principal que leem uma hora e uns minutos. Escrevem "Hora válida" ou "Hora inválida", e usam a tua função `horaValida` num `Se`.

### Desafio 3: Outra função para depurar

Esta função devia devolver o total de golos marcados por uma equipa num torneio, com os golos de cada jogo guardados num array. Tem um erro. Escreve o registo de depuração, com as quatro partes do exercício 6. Depois volta a fazer as duas chamadas com a função corrigida.

```text
Função totalGolos(golosPorJogo)
    int total = 0
    Para cada golos em golosPorJogo
        total = golos
    devolver total
```

Usa as chamadas `totalGolos([2, 0, 3])` e `totalGolos([4])` como exemplos.

### Desafio 4: O algoritmo do dossiê

Continua o exercício 7, com o teu dossiê da semana de passos.

a) Escreve a função `existe`, com o contrato que escreveste no exercício 7.

b) Escreve o algoritmo principal, que chama as três funções e mostra os resultados. Usa uma constante para o objetivo. Não precisas de copiar as funções `media` e `contarAcima`.

### Desafio 5: Os testes do dossiê

Continua o desafio 4. Com este desafio, o dossiê fica com as cinco partes. Começa por fazer à mão as chamadas dos exemplos dos contratos: são os testes de cada função.

a) Teste completo. Faz o teste completo, chamada a chamada, para a semana do enunciado. Confirma que dá o que previste na alínea a) do exercício 7. Escolhe tu como mostras cada chamada: em tabela própria, como no teste completo do exemplo guiado, ou só com as voltas e o valor devolvido.

b) Um segundo caso. Escolhe outro caso, com só 3 dias e nenhum dia a zero. Escolhe-o de maneira a testar mais uma coisa que a semana do enunciado não testa, e escreve qual. Calcula à mão o resultado esperado, e confirma que o algoritmo o dá.

## Critérios de conclusão

- No exercício 1, disseste os quatro valores, e o contrato diz o que acontece quando os dois números são iguais.
- No exercício 2, apontaste os parâmetros e os argumentos, e explicaste com as duas contas porque é que a ordem conta.
- No exercício 3, contaste à mão os três exemplos antes de escrever a função, e o trace confirma o primeiro.
- No exercício 4, decidiste as seis horas a partir do enunciado, e a função dá o que decidiste.
- No exercício 5, contaste à mão os dias acima de cada limiar, chamaste a mesma função duas vezes, e a explicação fala do argumento.
- No exercício 6, o registo tem as quatro partes, e a função corrigida dá o esperado nas duas chamadas.
- No exercício 7, o dossiê tem a análise, com o resultado calculado à mão, a tabela da decomposição e os três contratos.
- As tuas funções têm contrato, devolvem o resultado em todos os caminhos, e só usam os seus parâmetros, variáveis e constantes.

![Rodapé](../../imagens/rodape.png)
