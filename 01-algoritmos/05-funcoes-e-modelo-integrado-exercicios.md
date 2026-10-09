![Cabeçalho](../imagens/cabecalho.png)

# Ficha de exercícios: Funções e modelo integrado

| Identificação | Valor |
| --- | --- |
| Disciplina | Fundamentos de Programação, 10.º ano, Desenvolvimento de Software |
| Unidade de competência | UC00245, Desenvolver algoritmos |
| Material | Ficha do quinto tema, acompanha o [guia](05-funcoes-e-modelo-integrado.md) |
| Tempo | 105 minutos de exercícios e 20 minutos de desafio opcional. A secção "Para ires mais longe", no fim da ficha, também é opcional e fica fora destes minutos |
| Entrega | As respostas em papel ou num ficheiro de texto; o exercício 7 é o teu dossiê algorítmico |

## Antes de começares

Esta ficha treina o que aprendeste no guia: ler e chamar funções, distinguir parâmetros de argumentos, escrever funções com `Função` e `devolver`, usar funções que devolvem `true` ou `false`, passar um valor que muda o comportamento de uma função, encontrar erros em funções e montar um dossiê completo.

Antes de começar, deves conseguir explicar as quatro fases de uma chamada, a diferença entre `devolver` e `Escreve:` e porque é que uma função só usa os seus parâmetros. Se alguma destas ideias não estiver clara, volta à secção do guia que a explica.

Escreve as funções na forma que usamos nas aulas: o cabeçalho com `Função`, o nome e os parâmetros entre parênteses, o corpo indentado, e o resultado entregue com `devolver`. As funções escrevem-se antes do algoritmo principal. Escreve sempre o contrato de cada função que escreveres: o que recebe, o que devolve e um ou dois exemplos. Se souberes a lógica e não te lembrares da forma, escreve frases claras que digam o que a função recebe, o que faz e o que devolve.

Os exercícios 5, 6 e 7 usam funções dos exercícios anteriores. Guarda as tuas respostas à medida que avanças.

Os exercícios 1 a 7 são obrigatórios e cabem nos 105 minutos da ficha. Depois deles há um desafio opcional e, no fim, a secção "Para ires mais longe", também opcional, com os testes do dossiê do exercício 7, para quem terminar e quiser mais prática ou para estudares em casa. Nenhuma das duas conta para concluíres a ficha.

## Exercício 1: Ler uma função (10 min)

```text
Função maior(a, b)
    Se a > b
        devolver a
    Senão
        devolver b
```

a) O que devolve `maior(3, 8)`? E `maior(8, 3)`? E `maior(5, 5)`?

b) Que valor fica em `x` depois de `int x = maior(4, 9) + maior(2, 1)`?

c) Escreve o contrato desta função.

Concluíste quando tiveres os quatro valores e o contrato disser o que acontece quando os dois números são iguais.

## Exercício 2: Parâmetros e argumentos (10 min)

Uma escola calcula a nota final de uma disciplina com 70% da nota do teste e 30% da nota do trabalho:

```text
Função notaFinal(teste, trabalho)
    devolver teste * 0.7 + trabalho * 0.3
```

a) Quais são os parâmetros desta função? Na chamada `notaFinal(15, 10)`, quais são os argumentos?

b) Calcula o que devolvem `notaFinal(15, 10)` e `notaFinal(10, 15)`.

c) Um aluno teve 15 no teste e 10 no trabalho. Qual das duas chamadas da alínea b) dá a sua nota final? Explica porque é que a outra dá um valor diferente.

Concluíste quando souberes apontar parâmetros e argumentos e explicar, com as duas contas, porque é que a ordem conta.

## Exercício 3: Escrever uma função com um ciclo (15 min)

a) Escreve a função `contarPares(numeros)`, que recebe um array de números inteiros e devolve quantos deles são pares. Um número é par quando o resto da divisão por 2 é 0.

b) Escreve o contrato da função, com exemplos para `[4, 7, 10, 3]`, para `[]` e para `[5]`.

c) Faz o trace da chamada `contarPares([4, 7, 10, 3])`, em tabela própria.

Concluíste quando tiveres contado à mão, antes de escreveres a função, quantos pares há em cada um dos três exemplos, e a função devolver esses três valores, com o trace da alínea c) a confirmar o primeiro.

## Exercício 4: Uma função que responde sim ou não (10 min)

a) Escreve a função `horaValida(hora, minuto)`, que devolve `true` se a hora estiver entre 0 e 23 e os minutos entre 0 e 59, incluindo os extremos, e `false` caso contrário.

b) Escreve as linhas do algoritmo principal que leem uma hora e uns minutos e escrevem "Hora válida" ou "Hora inválida", usando a tua função num `Se`.

c) Diz o que a função devolve para 23:59, 24:00, 12:60 e 0:00.

Concluíste quando tiveres decidido a partir do enunciado, antes de seguires a função, se cada uma das quatro horas é válida, e a tua função der o resultado que previste nas quatro.

## Exercício 5: Um limiar que muda (15 min)

As temperaturas máximas de uma semana ficaram neste array:

```text
temperaturas = [18, 25, 31, 22, 35, 28]
```

a) Escreve a função `contarAcima(valores, limiar)`, que recebe um array e um número, e devolve quantos valores do array são maiores do que esse número.

b) Escreve as linhas do algoritmo principal que mostram quantos dias tiveram mais de 30 graus, e quantos tiveram mais de 25 graus, chamando a mesma função duas vezes.

c) Explica, numa ou duas frases, o que mudou entre as duas chamadas, e porque é que não foi preciso mudar nada dentro da função.

Concluíste quando tiveres contado à mão, no array, os dias acima de cada limiar, as duas chamadas derem essas contagens, e a tua explicação falar do argumento.

## Exercício 6: Encontrar o erro (15 min)

Cada uma destas funções tem um erro. Para cada uma, escreve quatro coisas: o que observaste (o que a função faz com um exemplo concreto), o que era esperado, a causa do erro e a correção.

a) Devia converter um tempo em horas e minutos num total de minutos:

```text
Função converterParaMinutos(horas, minutos)
    int total = horas * 60 + minutos
```

Usa a chamada `int duracao = converterParaMinutos(2, 15)` como exemplo.

b) Devia devolver `true` se todas as notas do array forem positivas, ou seja, 10 ou mais, e `false` se houver pelo menos uma negativa:

```text
Função todasPositivas(notas)
    Para cada nota em notas
        Se nota >= 10
            devolver true
        Senão
            devolver false
```

Usa as chamadas `todasPositivas([12, 5])` e `todasPositivas([5, 12])` como exemplos. Uma delas dá o resultado certo por acaso.

Concluíste quando cada alínea tiver as quatro partes e a função corrigida fizer o que devia.

## Exercício 7: O dossiê da semana de passos (30 min)

Este exercício junta toda a algoritmia, e é o teu dossiê. Aqui fazes as partes do dossiê que vêm antes dos testes: a análise, a decomposição, o contrato de cada função e o algoritmo. Os testes, a última parte, estão no Mais longe 1, no fim da ficha, que é opcional. Usa a função `media`, do guia, e a função `contarAcima`, do exercício 5. Estas duas já estão escritas, e não precisas de as escrever outra vez: escreve só o nome e o contrato de cada uma. Usa também a função `existe`, na versão corrigida que a secção dos erros frequentes do guia descreve por palavras. Como o guia não a escreve por inteiro, escreve-a tu, com o seu contrato, antes do algoritmo principal.

> Uma aplicação de exercício guardou os passos dados em cada dia de uma semana: `passos = [8200, 0, 10300, 7500, 12000, 6000, 5000]`. O objetivo diário é passar dos 8000 passos. O algoritmo mostra a média de passos por dia, em quantos dias o objetivo foi cumprido e, se houver algum dia com 0 passos, escreve "Houve pelo menos um dia sem passos".

a) **Análise.** Escreve o contrato do problema, com as entradas, as saídas, as restrições e o resultado esperado para a semana do enunciado, calculado à mão.

b) **Decomposição.** Faz uma tabela com as funções que vais usar, o que cada uma recebe e o que devolve.

c) **Algoritmo principal.** Escreve o algoritmo principal, que chama as três funções e mostra os resultados. Usa uma constante para o objetivo.

Concluíste quando tiveres a análise com o resultado esperado calculado à mão, a tabela da decomposição, o contrato de cada uma das três funções, a função `existe` escrita e o algoritmo principal a chamar as três funções.

## Apoio

Se estiveres encravado, usa estas pistas pela ordem em que aparecem, e passa à seguinte só se a anterior não tiver chegado.

Exercício 1. Substitui `a` e `b` pelos argumentos e segue o `Se`. Na alínea b), resolve cada chamada sozinha e só depois soma.

Exercício 2. Os parâmetros estão no cabeçalho; os argumentos estão na chamada. Os argumentos passam para os parâmetros pela ordem.

Exercício 3. É o contador do guia 4, dentro de uma função. A condição de par é `numero resto 2 == 0`. No fim do ciclo, devolve o contador.

Exercício 4. São dois intervalos, um para a hora e outro para os minutos, e os quatro limites juntam-se todos com `e`.

Exercício 5. É o contador com um `Se`, como no exercício 3, mas a condição compara com o parâmetro `limiar` em vez de um número escrito.

Exercício 6. Na alínea a), procura a palavra `devolver`, e pensa no que fica em `duracao`. Na alínea b), segue a primeira volta de cada exemplo e vê em que momento a função termina. Pergunta-te: quando é que se pode ter a certeza de que todas as notas são positivas?

Exercício 7. Volta ao passo 8 do exemplo guiado, que mostra as cinco partes de um dossiê. As alíneas a) a c), com os contratos que o enunciado pede, são as quatro primeiras; a quinta, os testes, é o Mais longe 1. Para a média, a pré-condição de `media` diz que o array não pode estar vazio: o array do enunciado tem 7 dias.

## Desafio opcional (20 min)

Na semana de passos, a diretora da aplicação quer saber também quantos dias ficaram acima da média da semana, e não do objetivo.

a) Escreve uma solução que chama `media(passos)` dentro do ciclo, em cada comparação, e outra que a calcula uma vez antes do ciclo.

b) Conta, para os 7 dias, quantas voltas de ciclo faz cada solução, somando as voltas dentro da função e as do ciclo do algoritmo principal.

c) As duas soluções dão o mesmo resultado? Quantos dias ficaram acima da média?

## Para ires mais longe

Esta secção é opcional e fica fora dos 105 minutos da ficha. Não precisas de fazer nada daqui para concluíres a ficha, e os critérios de conclusão não a contam. Serve para quem terminou a parte obrigatória e quer mais prática, ou para estudares em casa. O tempo é indicativo.

### Mais longe 1: Os testes do dossiê (30 min)

Continua o exercício 7: usa o teu dossiê da semana de passos. Com estas duas alíneas, o dossiê fica com as cinco partes do passo 8 do guia.

a) **Teste completo.** Faz o teste completo, chamada a chamada, para a semana do enunciado, e confirma que dá o que previste na alínea a) do exercício 7.

b) **Um segundo caso.** Escolhe outra semana, com 3 dias e nenhum dia a zero, calcula à mão o resultado esperado e confirma que o algoritmo o dá.

Concluíste quando os dois testes derem o que previste.

Pista: o teste completo faz-se como no passo 7 do exemplo guiado, com cada chamada na sua tabela própria.

## Critérios de conclusão

- [ ] Escrevi o contrato de cada função: o que recebe, o que devolve e exemplos.
- [ ] Em todas as minhas funções, todos os caminhos chegam a um `devolver`.
- [ ] As minhas funções devolvem os resultados, e quem escreve no ecrã é o algoritmo principal.
- [ ] As minhas funções só usam os seus parâmetros, as suas variáveis e as constantes.
- [ ] Fiz o trace de pelo menos uma chamada em tabela própria.
- [ ] Para cada erro, escrevi o observado, o esperado, a causa e a correção.
- [ ] O meu dossiê tem a análise, com o resultado esperado calculado à mão, a decomposição, o contrato de cada função e o algoritmo principal.

## Autoavaliação breve

O que já consigo fazer sozinho:

Uma dificuldade que tive e o que fiz para a resolver:

![Rodapé](../imagens/rodape.png)
