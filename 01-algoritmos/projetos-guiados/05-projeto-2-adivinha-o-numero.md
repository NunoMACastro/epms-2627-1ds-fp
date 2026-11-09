![Cabeçalho](../../imagens/cabecalho.png)

# Projeto 2: Adivinha o número

Um jogador escreve um número secreto de 1 a 100, e o outro tenta adivinhá-lo, com pistas, em 10 tentativas no máximo. Este projeto repete o processo do projeto 1 e acrescenta um passo novo, melhorar um algoritmo e contar o trabalho que ele faz. Fazes em pares, em várias aulas: um escreve, o outro confere, e trocam em cada passo. Precisas de papel e lápis, dos guias e do projeto 1. Para rever: os guias [01](../01-do-enunciado-ao-problema.md), [02](../02-estado-sequencia-representacoes.md), [03](../03-decisoes-e-validacao.md), [04](../04-repeticao-e-arrays.md) e [05](../05-funcoes-e-modelo-integrado.md), e o [projeto 1](05-projeto-1-duelo-de-dados.md).

Cada passo acaba com "Mostra ao professor antes de avançar". Só passas ao passo seguinte depois de ele confirmar, porque cada passo usa o anterior. Se houver alguma coisa a corrigir, ele faz-te uma pergunta, e tu corriges.

## O jogo

> Dois jogadores jogam ao "adivinha o número". Primeiro, o jogador 1 escreve um número secreto de 1 a 100, sem o jogador 2 ver. O jogador 1 escreve sempre um número inteiro de 1 a 100.
>
> Depois, o jogador 2 tenta adivinhar o número, e tem no máximo 10 tentativas. Em cada tentativa escreve um número inteiro. Se o número estiver fora de 1 a 100, o algoritmo escreve "Esse número não vale. Escreve um número de 1 a 100." e pede outra vez, até o número ser válido. Um número que não vale não conta como tentativa. Se o número for igual ao secreto, o jogador 2 acertou. Se for menor do que o secreto, o algoritmo escreve "Mais alto". Se for maior, escreve "Mais baixo".
>
> O jogo acaba quando o jogador 2 acerta ou quando esgota as 10 tentativas. Se o jogador 2 acertou, o algoritmo escreve no fim "Acertaste à tentativa N!". No lugar do N fica o número da tentativa em que acertou. Se acertou em 7 tentativas ou menos, escreve a seguir "Muito bem!". Se não acertou, escreve "Perdeste! O número era S.", com o número secreto no lugar do S.

As mensagens entre aspas são estas, palavra por palavra. As perguntas antes de cada leitura escolhe-as tu.

Por exemplo, se o número secreto for 63 e o jogador 2 escrever 50, o algoritmo escreve "Mais alto". Se a seguir escrever 120, o algoritmo escreve "Esse número não vale. Escreve um número de 1 a 100." e pede outro.

## Parte 1: do enunciado ao algoritmo testado

### Passo 1: o contrato

O contrato tem de estar completo antes de a tabela do passo 2 começar. Tem as cinco partes do projeto 1, e os exemplos concretos ficam para o passo 2. Quando uma pergunta não tem resposta no enunciado, toma-se uma decisão, numa linha que começa por "Decisão:", com a razão. Rever: [O contrato diz o que entra, o que sai e que regras há](../01-do-enunciado-ao-problema.md#o-contrato-diz-o-que-entra-o-que-sai-e-que-regras-há) e [Passo 1 do projeto 1](05-projeto-1-duelo-de-dados.md#passo-1-o-contrato).

**a)** Escreve as entradas. Para cada uma, diz o tipo, os limites e se o algoritmo a valida ou não, e porquê. Se uma entrada não for validada, o contrato diz porquê numa frase, como a suposição do projeto 1.

**b)** Escreve as saídas: as mensagens que podem aparecer durante o jogo e as que podem aparecer no fim.

**c)** Escreve as restrições, com os números do enunciado.

**d)** Escreve as condições: as situações diferentes que podem acontecer numa tentativa e no fim do jogo.

**e)** Há uma situação que o enunciado não decide. Imagina um jogador 2 distraído: o que pode ele escrever que o enunciado não diga como se conta? Escreve a decisão e a razão.

Mostra ao professor antes de avançar: o contrato, com a decisão e a sua razão.

### Passo 2: a tabela de casos esperados, antes do algoritmo

Cada caso é um jogo inteiro. Tem o número secreto e todos os números que o jogador 2 escreve até o jogo acabar, incluindo os que não valem. O resultado esperado tem todas as mensagens do jogo, pela ordem, sem as perguntas. Podes abreviar a mensagem do número que não vale como "Esse número não vale", e escrever "Mais alto (4 vezes)". Rever: [Fronteiras e casos de teste](../03-decisoes-e-validacao.md#fronteiras-e-casos-de-teste) e [Passo 2 do projeto 1](05-projeto-1-duelo-de-dados.md#passo-2-a-tabela-de-casos-esperados-antes-do-algoritmo).

**a)** Faz a tabela com as colunas N.º, Tipo, Número secreto, Números escritos pelo jogador 2, Resultado esperado e Porque foi escolhido. Deixa espaço à direita para Resultado obtido e Passou?.

**b)** A tabela tem de ter, pelo menos, casos para estas situações:

- um jogo normal, curto, com pistas dos dois tipos;
- o jogo mais curto possível;
- o jogo com mais tentativas, de cada uma das maneiras como pode acabar;
- os dois lados da fronteira do "Muito bem!";
- os dois lados do 1 e do 100: o número que não vale mais perto e, no mesmo jogo, o válido mais perto;
- dois números que não valem, escritos seguidos;
- a situação que decidiste no passo 1.

Nos jogos compridos, escolhe números fáceis de seguir, por exemplo de 10 em 10. Um caso pode testar duas coisas, desde que a última coluna diga as duas.

Mostra ao professor antes de avançar: a tabela preenchida e, para cada fronteira, os casos que ficam de um lado e do outro.

### Passo 3: as peças do algoritmo

Antes de escreveres o algoritmo, decide a estrutura. Rever: [As três peças de um ciclo](../04-repeticao-e-arrays.md#as-três-peças-de-um-ciclo), [`Parar`: sair do ciclo já](../04-repeticao-e-arrays.md#parar-sair-do-ciclo-já) e [Intervalos](../03-decisoes-e-validacao.md#intervalos).

Este algoritmo junta duas coisas pela primeira vez. A primeira é um ciclo com duas maneiras de acabar. A condição de um ciclo diz quando continuar. Por isso, pensa em quando o jogo para e escreve o contrário. O contrário de uma condição com `ou` escreve-se com `e`, trocando cada parte pela sua contrária: `nota < 0 ou nota > 20` passa a `nota >= 0 e nota <= 20`.

Depois do ciclo, sabes que a condição deu falso, mas não sabes qual das duas razões aconteceu. O algoritmo precisa de o saber, para escrever a mensagem certa.

A segunda é um ciclo dentro de outro. Uma validação repetida dentro do corpo de outro ciclo faz todas as suas voltas durante uma só volta do ciclo de fora:

```text
const NOTA_MINIMA = 0
const NOTA_MAXIMA = 20
const NUMERO_DE_ALUNOS = 2
Para aluno de 1 até NUMERO_DE_ALUNOS
    Escreve: "Nota do aluno ", aluno, " (inteiro de 0 a 20)?"
    int nota = ler valor
    Enquanto nota < NOTA_MINIMA ou nota > NOTA_MAXIMA
        Escreve: "Nota inválida. Escreve um inteiro de 0 a 20."
        nota = ler valor
    Escreve: "Nota aceite: ", nota
```

Com 25, -3, 14 e 9, "Nota inválida" aparece duas vezes, as duas na primeira volta do `Para`. As notas aceites são 14 e 9. Numa tabela de iterações do ciclo de fora, o que o ciclo de dentro faz escreve-se na coluna "Durante a iteração".

Responde por escrito, em poucas palavras:

**a)** Quando o algoritmo chega ao ciclo das tentativas, já se sabe quantas vezes ele se vai repetir? Com um `Para` e um `Parar`, onde ficava escrita a regra do fim? Diz que ciclo escolhes.

**b)** Escreve as duas maneiras de o jogo acabar, cada uma como uma condição que dá `true` quando essa maneira aconteceu.

**c)** Escreve a condição de continuar.

**d)** Depois do ciclo, como fica o algoritmo a saber por qual das duas maneiras o jogo acabou? Atenção: há uma forma de decidir que parece certa e falha num dos casos da tua tabela. Diz qual é essa forma e esse caso.

**e)** Diz onde fica a validação repetida e onde fica a linha que soma 1 às tentativas.

Mostra ao professor antes de avançar: as cinco respostas.

### Passo 4: o algoritmo

Escreve o algoritmo completo, em pseudocódigo ou em frases claras numeradas. Os números fixos do enunciado são constantes. Rever: [A validação repetida insiste até o valor servir](../04-repeticao-e-arrays.md#a-validação-repetida-insiste-até-o-valor-servir).

Antes de mostrares, confere com o dedo por baixo de cada linha:

- cada variável recebe um valor antes de ser usada, também as da condição. Um valor inventado para entrar no ciclo só serve se ficar fora de 1 a 100;
- a validação repetida tem a condição do número que não vale, e o seu corpo volta a ler o número;
- a linha que soma 1 às tentativas é executada uma vez por cada número válido;
- dentro do ciclo das tentativas, há uma atualização que, mais cedo ou mais tarde, faz o ciclo acabar;
- a decisão do fim depende da razão por que o ciclo parou.

Mostra ao professor antes de avançar: o algoritmo completo.

### Passo 5: a tabela de iterações do caso normal

Um valor lido durante uma volta só aparece na sua coluna na linha seguinte. Rever: [A tabela de iterações](../04-repeticao-e-arrays.md#a-tabela-de-iterações).

**a)** Faz a tabela de iterações do teu caso normal. Usa uma coluna para cada variável que muda, outra para a condição do ciclo e outra para o que acontece durante a volta. Na da condição, escreve o resultado de cada parte e o da condição inteira.

**b)** Por baixo, escreve o que acontece depois do ciclo: que condições são avaliadas, com que resultado, e o que aparece no ecrã.

**c)** Compara o ecrã com o resultado esperado do caso normal.

Mostra ao professor antes de avançar: a tabela de iterações e a comparação.

### Passo 6: executar a tabela de casos

Executa os outros casos, sem uma tabela de iterações para cada um. Anota num rascunho o número lido, as tentativas e o que aparece no ecrã. Executa o que está escrito, e não o que achas que o algoritmo devia fazer.

**a)** Para cada caso, preenche o resultado obtido e se o teste passou.

**b)** Olha para o algoritmo, e não para a tabela. Há alguma linha por onde nenhum caso passou? Se houver, acrescenta um caso que passe por ela, com o esperado escrito antes de o executares.

Mostra ao professor antes de avançar: a tabela com todas as colunas e a resposta da alínea b).

### Passo 7: depurar o que falhou

Se algum caso falhou, segue os cinco passos e escreve o registo de depuração, com as quatro partes e a linha do teste de regressão. Não apagues a versão com o erro, porque o portefólio mostra as duas. Rever: [Passo 6 do projeto 1](05-projeto-1-duelo-de-dados.md#passo-6-depurar-o-erro).

Se nenhum caso falhou, escreve-o por baixo da tabela. O professor pode dar-te um caso que ainda não experimentaste.

Mostra ao professor antes de avançar: o registo e a versão corrigida, ou a tabela com todos os casos a passar.

## Parte 2: depurar e melhorar o algoritmo de um colega

Quando o professor confirmar o passo 7, entrega-te o algoritmo de um colega de outra turma para este jogo. Entrega-te também o relato de um erro que ele observou. Para encontrares o erro, não procures as diferenças em relação ao teu algoritmo. Dois algoritmos diferentes podem estar ambos certos.

### Passo 8: ler o algoritmo do colega e observar e reproduzir o erro

Lê o algoritmo pela indentação: vê o que está dentro de cada ciclo e de cada `Se`. Depois, reproduz o erro: faz com que aconteça outra vez, no papel, com o mesmo caso. Rever: [Reproduzir a falha com um exemplo mínimo](../01-do-enunciado-ao-problema.md#reproduzir-a-falha-com-um-exemplo-mínimo).

**a)** Faz a tabela de iterações do jogo relatado, na versão do colega, e confirma que o ecrã é o do relato.

**b)** Procura o exemplo mínimo. Experimenta jogos parecidos com o relatado, mas mais curtos, seguindo só o que precisares para saber se o erro aparece.

**c)** Qual é o jogo mais pequeno que ainda mostra o erro? Porque é que não pode ser mais pequeno? O que se pode simplificar nesse jogo?

Mostra ao professor antes de avançar: a tabela de iterações e as respostas às alíneas b) e c).

### Passo 9: formular uma hipótese, verificá-la e corrigir a causa

Pergunta-te: a minha alteração explica porque é que o resultado ficou errado, ou só o acerta? Rever: [Passo 6 do projeto 1](05-projeto-1-duelo-de-dados.md#passo-6-depurar-o-erro).

**a)** Escreve a tua hipótese numa frase que possa ser verdadeira ou falsa.

**b)** Faz o trace da parte do algoritmo onde a tua hipótese põe o erro, com o exemplo mínimo. Diz se o trace confirma a hipótese, e qual é a linha que causa o erro. Se a deitar abaixo, formula outra.

**c)** Escreve a causa numa frase: o que faz essa linha, e porque é que assim o algoritmo não faz o que o enunciado diz.

**d)** Corrige a causa com uma única alteração, e explica a correção com as palavras do enunciado.

Mostra ao professor antes de avançar: a hipótese, o trace, a causa e a correção.

### Passo 10: o registo de depuração e voltar a testar tudo

A tua tabela foi escrita a partir do contrato, e por isso serve para testar o algoritmo do colega. Só o caso da tua decisão pode mudar, se ele tiver decidido de outra maneira.

**a)** Confirma que a tabela tem os dois lados da fronteira onde o erro apareceu. Se não tiver, acrescenta esses casos, com o esperado escrito a partir do contrato.

**b)** Escreve o registo de depuração desta correção, com as quatro partes. Outra pessoa tem de perceber o erro e a correção só pelo registo.

**c)** Faz o teste de regressão, com a tabela inteira na versão corrigida. Por baixo do registo, escreve quantos casos passam.

Mostra ao professor antes de avançar: o registo e a tabela executada.

### Passo 11: melhorar sem mudar o que o algoritmo faz

A versão corrigida passa em todos os testes. Agora pergunta-se se ela faz trabalho desnecessário. Há uma parte do corpo do ciclo que faz perguntas cujas respostas o algoritmo já conhece. A versão melhorada tem de escrever exatamente o mesmo, para qualquer jogo que o contrato aceite. Rever: [Duas soluções certas, uma mais eficiente](../05-funcoes-e-modelo-integrado.md#duas-soluções-certas-uma-mais-eficiente).

**a)** Escreve a parte do algoritmo que muda, já melhorada.

**b)** Explica porque é que a versão melhorada escreve sempre o mesmo que a corrigida. Diz porque é que as situações que juntaste não podem acontecer ao mesmo tempo.

**c)** Executa na versão melhorada o caso normal, o caso que mostrou o erro e o que acaba sem acertar. Confirma que dão o mesmo ecrã que na versão corrigida.

Mostra ao professor antes de avançar: a parte melhorada, a explicação e os três testes.

### Passo 12: contar as perguntas antes e depois

As voltas são as mesmas nas duas versões, porque a melhoria não mexeu em nenhum ciclo. Aqui contam-se perguntas, com esta regra:

- cada vez que o algoritmo avalia a condição de um `Se` ou de um `Senão se`, faz uma pergunta;
- uma condição com `e` ou com `ou` é uma só pergunta;
- o `Senão` não faz pergunta nenhuma;
- conta só as perguntas da parte que mudou, dentro do ciclo das tentativas.

Conta as perguntas de um jogo curto: o número secreto é 30, e o jogador 2 escreve 50, 20 e 30.

**a)** Faz uma tabela com uma linha por tentativa e uma coluna para cada versão, com as perguntas da parte que mudou.

**b)** Soma as perguntas de cada versão e calcula a diferença.

**c)** Diz, numa frase, em que tentativa a versão melhorada poupa mais perguntas, e porquê.

Mostra ao professor antes de avançar: a tabela, os dois totais e a resposta da alínea c).

## Antes de terminares

O projeto fica no portefólio de cada um dos dois, ao lado do projeto 1. Não conta para a avaliação prática, mas podes consultá-lo nela. Se guardares em ficheiros, usa um por peça:

| Peça | Nome do ficheiro |
| --- | --- |
| O enunciado e o contrato, com a decisão | `adivinha-o-numero-contrato` |
| A tabela de casos, com os resultados obtidos, e a tabela de iterações do caso normal | `adivinha-o-numero-testes` |
| O teu algoritmo e, se o corrigiste, a versão com o erro e o registo | `adivinha-o-numero-algoritmo`, `adivinha-o-numero-algoritmo-com-erro` e `adivinha-o-numero-registo-depuracao` |
| A folha do colega, a tabela de iterações do erro, o exemplo mínimo, o trace, o registo e a tabela executada outra vez | `adivinha-o-numero-colega-depuracao` |
| A versão melhorada, a explicação e a contagem de perguntas | `adivinha-o-numero-colega-melhorado` |

- [ ] O contrato tem a decisão e a razão.
- [ ] A tabela de casos foi escrita antes do algoritmo, com as fronteiras das 10 tentativas, do "Muito bem!" e de 1 a 100.
- [ ] O algoritmo passa em todos os casos, e consigo explicar como ele sabe porque é que o jogo acabou.
- [ ] O registo de depuração do algoritmo do colega tem as quatro partes.
- [ ] Depois de corrigir, voltei a testar a tabela inteira.
- [ ] A versão melhorada dá o mesmo ecrã, contei as perguntas das duas versões e sei explicar a diferença.

A seguir vem o projeto 3, a avaliação prática individual, com um problema novo e o mesmo processo.

![Rodapé](../../imagens/rodape.png)
