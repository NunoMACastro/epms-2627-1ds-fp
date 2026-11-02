![Cabeçalho](../imagens/cabecalho.png)

# Listas

Módulo Criar aplicações em linguagem de programação Python. Neste guia, os teus programas passam a guardar muitos valores com um só nome, numa lista. Depois percorrem a lista para contar, somar, procurar e saltar valores. Para praticar, há o [laboratório](laboratorios/05-listas-laboratorio.md) e a [ficha de exercícios](exercicios/05-listas-exercicios.md) deste tema.

Na algoritmia, já trabalhaste com arrays: as pontuações de uma equipa, as notas de um teste, os quilos de cada turma. Em Python, um array chama-se lista, e escreve-se como no pseudocódigo das aulas. Por isso, vais reconhecer muita coisa. O que é novo é a forma de escrever em Python os ciclos sobre uma lista, o `break` e o `continue`. É nova também a função `len`, que diz quantos elementos tem uma lista.

Neste tema, as listas já vêm escritas no código, e só mudas elementos que já existem. Acrescentar e tirar elementos de uma lista fica para o tema 07, Textos e listas que mudam. Os exemplos deste guia são de jogos. Nas secções, são as moedas que apanhas em cada nível de um jogo de plataformas. No exemplo guiado, são os pontos de uma equipa.

## Neste guia

1. O que vais aprender
2. O que já sabes e vais usar
3. Uma lista guarda vários valores com um só nome
4. O índice: a posição de cada elemento
5. O `len`: quantos elementos tem a lista
6. Percorrer a lista pelo valor, com `for`
7. Percorrer a lista pelo índice, com `range` e `len`
8. Escolher entre o valor e o índice
9. Mudar um elemento pelo índice
10. Procurar um valor: a pesquisa com bandeira
11. Parar a pesquisa com `break`
12. Saltar uma volta com `continue`
13. A lista vazia e os três casos de teste
14. Exemplo guiado: os jogos da equipa, do pseudocódigo ao Python
15. Erros frequentes
16. Palavras novas deste guia
17. Verificar o que aprendeste
18. O que vem a seguir

## O que vais aprender

No fim deste guia, consegues:

- criar uma lista em Python e usar cada elemento pelo seu índice, sem sair da lista;
- dizer quantos elementos tem uma lista, com o `len`, e qual é o último índice válido;
- percorrer uma lista pelo valor e pelo índice, e escolher a forma que serve cada problema;
- mudar elementos de uma lista pelo índice;
- procurar um valor numa lista com uma bandeira, parar com `break` e saltar valores com `continue`;
- testar cada programa com a lista vazia, com um elemento e com vários.

## O que já sabes e vais usar

- Correr um script no terminal, o `print` com vários valores separados por vírgulas e os comentários: guia [01 Do pseudocódigo ao Python](01-do-pseudocodigo-ao-python.md).
- Os três tipos de erro, o traceback lido de baixo para cima e a rotina de cinco passos: guia [01 Do pseudocódigo ao Python](01-do-pseudocodigo-ao-python.md).
- As variáveis, os nomes com traço baixo e as constantes em maiúsculas: guia [02 Dados e interação](02-dados-e-interacao.md).
- Os tipos `int`, `float`, `str` e `bool`, as contas, a função `type` e o erro da divisão por zero: guia [02 Dados e interação](02-dados-e-interacao.md).
- As funções predefinidas, como o `abs`, que recebem um valor entre parênteses e devolvem um resultado: guia [02 Dados e interação](02-dados-e-interacao.md).
- O `if`, o `elif` e o `else`, as comparações, o `True`, o `False` e o `not`: guia [03 Seleção](03-selecao.md).
- O `while`, o contador e o acumulador: guia [04 Ciclos while e for](04-ciclos-while-e-for.md).
- O ciclo que nunca acaba e o Ctrl+C, que o para: guia [04 Ciclos while e for](04-ciclos-while-e-for.md).
- O `for` com `range`, em que o primeiro número entra e o segundo não: guia [04 Ciclos while e for](04-ciclos-while-e-for.md).
- Os arrays em pseudocódigo e o índice a partir de 0: secção "Criar um array" do guia [04 Repetição e arrays](../01-algoritmos/04-repeticao-e-arrays.md) da algoritmia.
- O último índice válido e o índice fora do array: secção "O índice" do mesmo guia.
- O `Para cada` e o `Para` com o índice: secções "Percorrer um array com `Para cada`" e "Percorrer um array com `Para`" do mesmo guia.
- Porque é que o `Para cada` não muda o array: secção "O `Para cada` não muda o array" do mesmo guia.
- O `Parar`, o `Continuar` e a bandeira: secções "`Parar`: sair do ciclo já" e "`Continuar`: saltar para a volta seguinte" do mesmo guia.
- Os três casos de teste de um ciclo, com zero voltas, uma volta e várias voltas: secção "Testar só o caso normal" do mesmo guia.

## Uma lista guarda vários valores com um só nome

Num jogo de plataformas, cada nível dá moedas. Jogaste cinco níveis. Apanhaste 15 moedas no primeiro, 8 no segundo, 22 no terceiro, nenhuma no quarto e 25 no quinto. Com o que sabes do tema 02, guardavas estes valores em cinco variáveis, `moedas_nivel_1`, `moedas_nivel_2` e assim por diante. Para as somar, escrevias uma conta com os cinco nomes. Com 50 níveis, precisavas de 50 variáveis e de uma conta com 50 nomes.

Na algoritmia, este problema resolvia-se com um array, uma variável que guarda vários valores, uns a seguir aos outros, numa ordem fixa. Em Python, a um array chama-se **lista**. Escreve-se como no pseudocódigo das aulas: os valores entre parênteses retos, `[` e `]`, separados por vírgulas.

```python
moedas = [15, 8, 22, 0, 25]
```

A cada valor guardado numa lista chama-se **elemento**. Esta lista tem cinco elementos, um por nível. A ordem conta. O 15 é o primeiro elemento, porque é o do primeiro nível, e o 25 é o último.

O nome da lista vai no plural, `moedas`, porque guarda vários valores. É a regra que já seguias nos arrays, e ajuda a ler o programa. O nome segue também a forma do Python, em minúsculas e com traço baixo entre as palavras, como `pontos_de_vida`.

Antes de correres este script, tenta prever as duas linhas que aparecem no ecrã.

```python
# moedas_niveis.py: as moedas que apanhaste em cada nível de um jogo de plataformas.
moedas = [15, 8, 22, 0, 25]
print("Moedas por nível:", moedas)
print(type(moedas))
```

O resultado é este:

```text
Moedas por nível: [15, 8, 22, 0, 25]
<class 'list'>
```

Leitura guiada: a linha 2 cria a lista e guarda-a na variável `moedas`. O primeiro `print` escreve um texto e, a seguir, a lista inteira, com os parênteses retos e as vírgulas, tal como a escreveste. O segundo `print` escreve o tipo do valor guardado em `moedas`. Para um inteiro, o `type` mostra `<class 'int'>`, e para um texto, `<class 'str'>`. Aqui mostra `<class 'list'>`, isto é, "da classe lista". Uma lista é um tipo de valor, como os números e os textos.

Uma lista também pode guardar textos. Os mundos do mesmo jogo guardam-se assim. Antes de correres, prevê: os nomes aparecem com aspas ou sem aspas?

```python
# mundos.py: os nomes dos mundos do mesmo jogo, numa lista de textos.
mundos = ["Floresta", "Deserto", "Gelo"]
print("Mundos:", mundos)
```

O resultado é `Mundos: ['Floresta', 'Deserto', 'Gelo']`.

Leitura guiada: quando o `print` escreve um texto sozinho, as aspas não aparecem. Quando escreve uma lista, mostra cada texto entre aspas simples, `'`, para se ver onde começa e acaba cada elemento. Em Python, as aspas simples e as duplas servem para o mesmo. O que escreves no código continua com as aspas duplas.

Nas listas deste guia, os elementos de cada lista são todos do mesmo tipo: só números, ou só textos. O Python aceita misturas, como `[15, "Gelo"]`. Mas numa lista com um só tipo de valor, todos os elementos se tratam da mesma maneira, e isso torna mais fácil percorrê-la.

## O índice: a posição de cada elemento

Para usar um só elemento, como as moedas do terceiro nível, é preciso dizer qual. Cada elemento tem uma posição na lista, a que se chama **índice**. Como nos arrays, os índices começam em 0. O primeiro elemento tem o índice 0, o segundo tem o índice 1, e assim por diante.

| Índice | 0 | 1 | 2 | 3 | 4 |
| --- | ---: | ---: | ---: | ---: | ---: |
| Elemento | 15 | 8 | 22 | 0 | 25 |

Para usar um elemento, escreve-se o nome da lista e o índice entre parênteses retos. `moedas[0]` é o 15, e `moedas[2]` é o 22. É a escrita do pseudocódigo. Um elemento usa-se como qualquer variável: numa conta, num `print`, numa comparação, ou para dar valor a outra variável.

Porque é que se começa no 0? O índice diz quantas posições andas a partir do início da lista. O primeiro elemento está logo no início, a zero posições. Por isso, o número do nível, para as pessoas, é o índice mais 1. O nível 3 tem o índice 2.

Antes de correres, prevê as três linhas que aparecem.

```python
# moedas_indice.py: usa os elementos da lista das moedas pelo índice.
moedas = [15, 8, 22, 0, 25]
primeiro = moedas[0]
print("Primeiro nível:", primeiro)
print("Terceiro nível:", moedas[2])
print("Os dois primeiros juntos:", moedas[0] + moedas[1])
```

O resultado é este:

```text
Primeiro nível: 15
Terceiro nível: 22
Os dois primeiros juntos: 23
```

Leitura guiada: a linha 3 guarda na variável `primeiro` o elemento de índice 0, o 15. A lista não muda: o 15 continua lá, e passou a estar também em `primeiro`. A linha 5 usa o elemento de índice 2 diretamente no `print`, sem passar por outra variável. O terceiro nível tem o índice 2, e não o 3, porque se conta do 0. A linha 6 soma dois elementos, o de índice 0 e o de índice 1, ou seja, 15 mais 8. Quem previu 8 na segunda linha contou as posições a partir do 1. Para essa pessoa, `moedas[2]` era o segundo elemento.

### O índice fora da lista

Numa lista com 5 elementos, os índices vão de 0 a 4. Ao maior índice que existe chama-se **último índice válido**, e é sempre o número de elementos menos 1. E `moedas[5]`? Não existe. Na algoritmia, um índice fora do array deixava o algoritmo errado no papel. Em Python, o programa para com uma mensagem.

Antes de correres este script, prevê quantas linhas aparecem antes do erro.

```python
# moedas_fora.py: pede o elemento de índice 5, que não existe.
moedas = [15, 8, 22, 0, 25]
print("Último nível:", moedas[4])
print("Sexto nível:", moedas[5])
```

O resultado é este:

```text
Último nível: 25
Traceback (most recent call last):
  File "C:\Users\aluno\Documents\fp-python\moedas_fora.py", line 4, in <module>
    print("Sexto nível:", moedas[5])
                          ~~~~~~^^^
IndexError: list index out of range
```

O primeiro `print` correu, e aparece o 25. A linha 4 parou o programa. É um erro de execução: a linha está bem escrita, mas não se consegue executar com esta lista. O traceback lê-se de baixo para cima. A última linha diz o tipo de erro, `IndexError: list index out of range`, isto é, "erro de índice: índice da lista fora dos limites". Por cima, os sinais `~~~~~~^^^` sublinham a parte que falhou, `moedas[5]`. Num Python mais antigo, estes sinais podem não aparecer. Mais acima está o número da linha, a 4. O caminho do ficheiro, como `C:\Users\aluno\Documents\fp-python\`, muda de computador para computador.

A um índice que não existe na lista chama-se **índice fora da lista**. Para o corrigir, pergunta-te que elemento querias. Aqui, a lista só tem cinco níveis, e não há sexto. Se querias o último, o índice certo é o 4.

## O `len`: quantos elementos tem a lista

Na algoritmia, o número de elementos de um array vinha no enunciado, numa constante, como `const NUMERO_DE_JOGOS = 4`. Era assim porque ainda não tinhas aprendido a perguntar a um array quantos elementos tem. Uma constante destas funciona enquanto a lista não muda. Mas se jogares mais um nível e acrescentares um valor à lista, tens de te lembrar de mudar também o número. Se te esqueceres, o programa usa os valores errados e não avisa.

O Python tem uma função predefinida para isto, o **`len`**, do inglês *length*, "comprimento". Recebe uma lista entre parênteses, como o `abs` recebe um número, e devolve quantos elementos ela tem. `len(moedas)` dá 5.

Com o `len`, o último índice válido escreve-se `len(moedas) - 1`, que dá 4. E o último elemento é `moedas[len(moedas) - 1]`, seja qual for o tamanho da lista.

Antes de correres, prevê as três linhas que aparecem.

```python
# moedas_len.py: quantos níveis tem a lista, e qual é o último.
moedas = [15, 8, 22, 0, 25]
numero_de_niveis = len(moedas)
print("Níveis jogados:", numero_de_niveis)
print("Último índice válido:", numero_de_niveis - 1)
print("Moedas do último nível:", moedas[numero_de_niveis - 1])
```

O resultado é este:

```text
Níveis jogados: 5
Último índice válido: 4
Moedas do último nível: 25
```

Leitura guiada: a linha 3 chama o `len` com a lista e guarda o resultado, 5, na variável `numero_de_niveis`. A linha 5 tira 1 a esse número, para chegar ao último índice. A linha 6 usa a mesma conta como índice. O Python faz primeiro a conta de dentro dos parênteses retos, `5 - 1`, e só depois vai buscar `moedas[4]`, que é o 25.

Agora acrescenta um sexto nível à lista, com 30 moedas: `moedas = [15, 8, 22, 0, 25, 30]`. Antes de correres outra vez, prevê o que muda. O resultado passa a ser 6, 5 e 30, sem mudares mais nenhuma linha. É a vantagem do `len` sobre um número escrito à mão: o programa acompanha a lista.

Ou seja, `len(moedas)` é o número de elementos, e `len(moedas) - 1` é o último índice. Os dois andam sempre juntos, e trocar um pelo outro é a origem de muitos índices fora da lista. `moedas[len(moedas)]` dá sempre `IndexError`, porque o número de elementos já está um a seguir ao último índice.

## Percorrer a lista pelo valor, com `for`

Para somar as moedas dos cinco níveis, podias escrever `moedas[0] + moedas[1] + moedas[2] + moedas[3] + moedas[4]`. Com 50 níveis, a conta tinha 50 parcelas. Na algoritmia, a solução era percorrer o array com um ciclo.

**Percorrer** uma lista é passar por todos os seus elementos, um a um, e fazer alguma coisa com cada um.

No pseudocódigo das aulas, escrevias `Para cada quantidade em moedas`. Em Python, o `Para cada` passa a `for`, sem `range`:

| Pseudocódigo | Python |
| --- | --- |
| `Para cada quantidade em moedas` | `for quantidade in moedas:` |

O `for` lê-se "para cada quantidade em moedas". Leva os dois pontos no fim, e o corpo do ciclo vai indentado com quatro espaços, como no `for` com `range`. Em cada volta, a variável `quantidade` recebe o elemento seguinte da lista. Na primeira volta recebe o 15, na segunda o 8, e assim até ao último. O ciclo dá tantas voltas quantos os elementos, e acaba sozinho quando eles se esgotam.

Num `for` que percorre uma lista pelo valor, a variável que recebe um elemento em cada volta chama-se **variável de iteração**. No `for` com `range` do tema 04, a variável recebe números, e continua a chamar-se variável de controlo. O nome da variável de iteração diz o que é cada elemento. Aqui, cada elemento é a quantidade de moedas de um nível, e por isso a variável chama-se `quantidade`. Numa lista `notas`, a variável chamava-se `nota`.

Antes de correres este script, calcula de cabeça o total e a média das moedas.

```python
# moedas_total.py: soma as moedas de todos os níveis e calcula a média por nível.
moedas = [15, 8, 22, 0, 25]
total = 0
for quantidade in moedas:
    total = total + quantidade
print("Total de moedas:", total)
print("Média por nível:", total / len(moedas))
```

O resultado é este:

```text
Total de moedas: 70
Média por nível: 14.0
```

A tabela de iterações mostra uma linha por volta, com o elemento dessa volta e o total no fim dela:

| Volta | quantidade | total no fim da volta |
| --- | ---: | ---: |
| antes do ciclo | sem valor | 0 |
| 1.ª | 15 | 15 |
| 2.ª | 8 | 23 |
| 3.ª | 22 | 45 |
| 4.ª | 0 | 45 |
| 5.ª | 25 | 70 |

Leitura guiada: o acumulador `total` nasce antes do ciclo, com 0, como no tema 04. O corpo do ciclo tem uma só linha, a soma, indentada. Os dois `print` estão encostados à margem, fora do ciclo, e escrevem-se uma só vez, no fim. A média divide o total pelo número de níveis, `len(moedas)`. Aparece `14.0`, e não 14, porque a divisão com `/` dá sempre um `float`.

Neste `for` não há índice nenhum, e por isso não há maneira de sair da lista. O ciclo só passa pelos elementos que existem. Mas a variável de iteração só sabe o valor do elemento, e não em que posição ele está. Para dizer "o nível 3 teve 22 moedas", isso não chega.

## Percorrer a lista pelo índice, com `range` e `len`

Queres escrever uma linha por nível, como "Nível 1 teve 15 moedas". Para isso, cada volta precisa da posição do elemento, e não só do valor. Na algoritmia, usavas o `Para` com as três peças à vista, `Para i = 0, i < NUMERO_DE_NIVEIS, i++`. Em Python, é o `for` com `range` do tema 04.

O `range(0, len(moedas))` é o `range(0, 5)`, e dá os números 0, 1, 2, 3 e 4. São exatamente os índices válidos da lista. Começa no 0, o primeiro índice, e para logo antes do número de elementos, tal como a condição `i < NUMERO_DE_NIVEIS`.

| Pseudocódigo | Python |
| --- | --- |
| `Para i = 0, i < NUMERO_DE_NIVEIS, i++` | `for i in range(0, len(moedas)):` |

Antes de correres, prevê a primeira e a última linha que aparecem.

```python
# moedas_por_nivel.py: escreve as moedas de cada nível, com o número do nível.
moedas = [15, 8, 22, 0, 25]
for i in range(0, len(moedas)):
    # O i + 1 faz com que o nível de índice 0 seja, para as pessoas, o nível 1.
    print("Nível", i + 1, "teve", moedas[i], "moedas")
```

O resultado são cinco linhas:

```text
Nível 1 teve 15 moedas
Nível 2 teve 8 moedas
Nível 3 teve 22 moedas
Nível 4 teve 0 moedas
Nível 5 teve 25 moedas
```

A tabela de iterações tem uma linha por volta, com o índice e o elemento nessa posição:

| Volta | i | moedas[i] | Ecrã |
| --- | ---: | ---: | --- |
| 1.ª | 0 | 15 | Nível 1 teve 15 moedas |
| 2.ª | 1 | 8 | Nível 2 teve 8 moedas |
| 3.ª | 2 | 22 | Nível 3 teve 22 moedas |
| 4.ª | 3 | 0 | Nível 4 teve 0 moedas |
| 5.ª | 4 | 25 | Nível 5 teve 25 moedas |

Leitura guiada: em cada volta, a variável `i` recebe um índice, de 0 a 4, e `moedas[i]` é o elemento nessa posição. A variável chama-se `i`, de índice, como no pseudocódigo. É a variável de controlo do `for`, e recebe um índice em cada volta. O `i + 1` só aparece no que se mostra às pessoas, que contam os níveis a partir do 1. No índice, `moedas[i]`, o 1 não se soma. Com o `len`, o mesmo ciclo serve para uma lista de qualquer tamanho.

Também vais ver escrito `range(len(moedas))`, só com o fim. Um `range` só com um número começa no 0, e por isso dá os mesmos índices. Neste guia, os percursos que passam pela lista toda escrevem sempre o 0, para se ver onde começam.

O erro típico é o `range` com um número a mais, `range(0, len(moedas) + 1)`. É o `<=` em vez do `<` da algoritmia. O programa escreve as cinco linhas certas e, na sexta volta, para:

```text
Traceback (most recent call last):
  File "C:\Users\aluno\Documents\fp-python\moedas_por_nivel.py", line 5, in <module>
    print("Nível", i + 1, "teve", moedas[i], "moedas")
                                  ~~~~~~^^^
IndexError: list index out of range
```

O `range(0, 6)` chega ao 5, e `moedas[5]` não existe. O erro aparece sempre na última volta, sejam quais forem os valores da lista. É por isso que se testa sempre a última volta.

## Escolher entre o valor e o índice

As duas formas passam por todos os elementos, do primeiro ao último. A escolha faz-se com uma pergunta: preciso de saber em que posição está cada elemento?

Se só precisas dos valores, para os somar, contar, comparar com um limite ou mostrar, percorre pelo valor. A este percurso, com `for quantidade in moedas:`, chama-se **percorrer pelo valor**. É mais curto, e não tens de pensar no último índice.

Se precisas da posição, percorre pelo índice, com `for i in range(0, len(moedas)):`. A este percurso chama-se **percorrer pelo índice**. Precisas da posição em três casos:

- para dizer em que posição está um valor, como "o nível 3 teve 22 moedas";
- para mudar um elemento da lista, como a secção seguinte mostra;
- para comparar um elemento com outro da mesma lista, como o anterior, `moedas[i - 1]`.

O terceiro caso tem um cuidado. O primeiro elemento não tem anterior, e por isso esse percurso começa no índice 1, com `range(1, len(moedas))`. Se começasse no 0, a primeira volta ia buscar `moedas[0 - 1]`, ou seja, `moedas[-1]`. O Python não dá erro nenhum, porque um índice negativo conta a partir do fim, e `moedas[-1]` é o último elemento. O programa compara o primeiro nível com o último, sem avisar. Os índices negativos são matéria do tema 07.

| | Pelo valor | Pelo índice |
| --- | --- | --- |
| A linha do ciclo | `for quantidade in moedas:` | `for i in range(0, len(moedas)):` |
| A variável recebe | o elemento | a posição |
| Para usar o elemento | `quantidade` | `moedas[i]` |
| Pode sair da lista | não | sim, se o `range` estiver errado |
| Serve para | somar, contar, comparar com um limite, mostrar | dizer a posição, mudar, comparar com outro elemento |

Pelo índice também se soma, com `total = total + moedas[i]`, e o resultado é o mesmo. Mas o programa fica mais comprido e com mais sítios onde errar. A regra prática é usar a forma mais simples que responde à pergunta.

## Mudar um elemento pelo índice

O quarto nível ficou registado com 0 moedas, mas afinal apanhaste 5. Para corrigir, dás um valor novo ao elemento de índice 3, como darias a uma variável. Do lado esquerdo do `=` fica o elemento, `moedas[3]`. Antes de correres, prevê a lista que aparece.

```python
# moedas_corrigir.py: corrige as moedas do quarto nível, que ficaram mal registadas.
moedas = [15, 8, 22, 0, 25]
moedas[3] = 5
print("Moedas por nível:", moedas)
```

O resultado é `Moedas por nível: [15, 8, 22, 5, 25]`.

Leitura guiada: a linha 3 lê-se "o elemento de índice 3 passa a valer 5". O 0 que lá estava perde-se, e os outros elementos ficam como estavam. A lista continua a ter cinco elementos.

Agora um caso com todos os elementos. Num fim de semana de evento, o jogo dá o dobro das moedas de cada nível. A lista tem de ficar `[30, 16, 44, 0, 50]`. Esse resultado sai do enunciado, e não de nenhum programa. A primeira ideia de muita gente é percorrer pelo valor.

### Primeira tentativa, pelo valor

Antes de correres, prevê o que aparece.

```python
# moedas_evento_errado.py: a primeira tentativa, que muda a variável e não a lista.
moedas = [15, 8, 22, 0, 25]
for quantidade in moedas:
    quantidade = quantidade * 2
print("Com o evento:", moedas)
```

O resultado é `Com o evento: [15, 8, 22, 0, 25]`. A lista não mudou. O programa não deu nenhuma mensagem de erro, e correu até ao fim. É um erro de lógica.

A tabela mostra a variável e a lista lado a lado:

| Volta | quantidade no início da volta | quantidade no fim da volta | moedas no fim da volta |
| --- | ---: | ---: | --- |
| 1.ª | 15 | 30 | [15, 8, 22, 0, 25] |
| 2.ª | 8 | 16 | [15, 8, 22, 0, 25] |
| 3.ª | 22 | 44 | [15, 8, 22, 0, 25] |
| 4.ª | 0 | 0 | [15, 8, 22, 0, 25] |
| 5.ª | 25 | 50 | [15, 8, 22, 0, 25] |

A coluna `quantidade` muda em todas as voltas, e a coluna `moedas` nunca muda. Em cada volta, a variável de iteração recebe o valor do elemento. A linha `quantidade = quantidade * 2` dá um valor novo à variável, e só à variável. A lista não sabe nada disso. E a variável também não sabe de que posição veio o valor, por isso nunca conseguia mudar o elemento certo. É o que acontecia com o `Para cada` da algoritmia: para mudar um elemento, é preciso a sua posição.

### A versão certa, pelo índice

Antes de correres, prevê outra vez o que aparece.

```python
# moedas_evento.py: num fim de semana de evento, o jogo dá o dobro das moedas de cada nível.
moedas = [15, 8, 22, 0, 25]
for i in range(0, len(moedas)):
    moedas[i] = moedas[i] * 2
print("Com o evento:", moedas)
```

O resultado é `Com o evento: [30, 16, 44, 0, 50]`, o que o enunciado pedia.

| Volta | i | moedas[i] antes | moedas[i] depois | moedas no fim da volta |
| --- | ---: | ---: | ---: | --- |
| 1.ª | 0 | 15 | 30 | [30, 8, 22, 0, 25] |
| 2.ª | 1 | 8 | 16 | [30, 16, 22, 0, 25] |
| 3.ª | 2 | 22 | 44 | [30, 16, 44, 0, 25] |
| 4.ª | 3 | 0 | 0 | [30, 16, 44, 0, 25] |
| 5.ª | 4 | 25 | 50 | [30, 16, 44, 0, 50] |

Leitura guiada: em cada volta, a linha do corpo lê o elemento da posição `i`, multiplica-o por 2 e escreve o resultado na mesma posição. Do lado direito do `=` está o valor antigo, e do lado esquerdo o sítio onde fica o novo. Agora é a coluna `moedas` que muda, um elemento por volta.

A regra prática: para ler os elementos, percorre pelo valor; para mudar os elementos da lista, percorre pelo índice.

Há um limite. Só mudas elementos que já existem. `moedas[5] = 12`, numa lista de cinco elementos, para o programa com `IndexError: list assignment index out of range`, isto é, "erro de índice: índice da atribuição fora dos limites da lista". Uma lista não cresce assim, e acrescentar elementos é matéria do tema 07.

## Procurar um valor: a pesquisa com bandeira

Houve algum nível em que apanhaste mais de 20 moedas? A resposta é sim ou não. Para a dar, o programa olha para os elementos um a um. Se encontrar um com mais de 20, já sabe que a resposta é sim. Mas só pode responder que não depois de ver a lista toda. A esta forma de procurar, que olha para os elementos um a um, pela ordem da lista, chama-se **pesquisa linear**.

Na algoritmia, a resposta ficava guardada numa bandeira. Uma **bandeira** é uma variável `bool` que começa em `False` e passa a `True` quando acontece o que se procura. Em Python, o `false` e o `true` do pseudocódigo escrevem-se `False` e `True`, com maiúscula.

Antes de correres, prevê a mensagem que aparece.

```python
# nivel_rico.py: diz se houve algum nível com mais de 20 moedas.
LIMITE = 20

moedas = [15, 8, 22, 0, 25]
encontrado = False
for quantidade in moedas:
    if quantidade > LIMITE:
        encontrado = True
if encontrado:
    print("Houve pelo menos um nível com mais de", LIMITE, "moedas.")
else:
    print("Nenhum nível passou das", LIMITE, "moedas.")
```

O resultado é `Houve pelo menos um nível com mais de 20 moedas.`

| Volta | quantidade | `quantidade > LIMITE` | encontrado no fim da volta |
| --- | ---: | --- | --- |
| antes do ciclo | sem valor | não se avalia | `False` |
| 1.ª | 15 | `False` | `False` |
| 2.ª | 8 | `False` | `False` |
| 3.ª | 22 | `True` | `True` |
| 4.ª | 0 | `False` | `True` |
| 5.ª | 25 | `True` | `True` |

Leitura guiada: a bandeira `encontrado` nasce antes do ciclo, com `False`, porque antes de olhar para a lista ainda não se encontrou nada. Dentro do ciclo, só lhe pode acontecer uma coisa: passar a `True`. Na 4.ª volta, o 0 não é maior do que 20, e a bandeira continua `True`, porque nada a volta a pôr em `False`. Depois do ciclo, o `if` lê a bandeira e escreve uma das duas mensagens, uma só vez. O `if encontrado:` lê-se "se encontrado", e é o mesmo que `if encontrado == True:`.

Agora muda a lista para `[15, 8, 20, 0, 10]` e prevê a mensagem. Aparece `Nenhum nível passou das 20 moedas.`, porque o 20 não é maior do que 20. É por isso que um caso com o valor da fronteira faz parte dos testes.

O erro típico é escrever a mensagem de "não encontrado" dentro do ciclo, num `else`:

```python
for quantidade in moedas:
    if quantidade > LIMITE:
        print("Houve pelo menos um nível com mais de", LIMITE, "moedas.")
    else:
        print("Nenhum nível passou das", LIMITE, "moedas.")
```

Com a lista `[15, 8, 22, 0, 25]`, este ciclo escreve cinco linhas, uma por nível:

```text
Nenhum nível passou das 20 moedas.
Nenhum nível passou das 20 moedas.
Houve pelo menos um nível com mais de 20 moedas.
Nenhum nível passou das 20 moedas.
Houve pelo menos um nível com mais de 20 moedas.
```

As mensagens contradizem-se. O `else` dentro do ciclo responde à pergunta "este nível tem mais de 20?", e não à pergunta "algum nível tem mais de 20?". A resposta "não" só se pode dar depois de ver a lista toda, e é por isso que a bandeira existe.

## Parar a pesquisa com `break`

Agora a pergunta muda: qual foi o primeiro nível com mais de 20 moedas? A resposta é uma posição, e por isso a lista percorre-se pelo índice. Há mais uma diferença. Depois de encontrar o primeiro, o resto da lista não interessa. Na algoritmia, saías do ciclo com o `Parar`. Em Python, escreve-se **`break`**, do inglês "partir, interromper". O `break` termina o ciclo imediatamente, e o programa continua na primeira linha a seguir ao ciclo.

Antes de correres, prevê o que aparece e quantas voltas dá o ciclo.

```python
# primeiro_nivel_rico.py: diz qual foi o primeiro nível com mais de 20 moedas.
LIMITE = 20

moedas = [15, 8, 22, 0, 25]
encontrado = False
for i in range(0, len(moedas)):
    if moedas[i] > LIMITE:
        print("Primeiro nível com mais de", LIMITE, "moedas: nível", i + 1)
        encontrado = True
        # Depois de encontrar o primeiro, o resto da lista não interessa.
        break
if not encontrado:
    print("Nenhum nível passou das", LIMITE, "moedas.")
```

O resultado é `Primeiro nível com mais de 20 moedas: nível 3`, depois de três voltas.

| Volta | i | moedas[i] | `moedas[i] > LIMITE` | O que acontece |
| --- | ---: | ---: | --- | --- |
| 1.ª | 0 | 15 | `False` | nada |
| 2.ª | 1 | 8 | `False` | nada |
| 3.ª | 2 | 22 | `True` | escreve a resposta, `encontrado` passa a `True`, `break` |

O ciclo terminou na 3.ª volta. O 0 e o 25 nunca foram vistos. Como a bandeira ficou `True`, a última mensagem não aparece.

Leitura guiada: o `break` está dentro do `if`, com oito espaços. Por isso, só se executa na volta em que se encontra o que se procura. A bandeira continua a fazer falta. Quando o ciclo acaba, pode ter acabado por duas razões: ou o `break` o fez sair, ou os índices esgotaram-se sem encontrar nada. Depois do ciclo, a bandeira diz qual das duas aconteceu. O `if not encontrado:` lê-se "se não encontrado", com o `not`, que é o `não` do pseudocódigo.

Sem o `break`, o ciclo continuava depois do nível 3, e o 25 também passava no `if`. O programa escrevia duas linhas:

```text
Primeiro nível com mais de 20 moedas: nível 3
Primeiro nível com mais de 20 moedas: nível 5
```

A segunda está errada, porque o nível 5 não é o primeiro.

O `break` também pode estar no sítio errado. Se tiver quatro espaços, encostado ao `if` em vez de estar dentro dele, faz parte do corpo do ciclo e executa-se logo na primeira volta:

```python
for i in range(0, len(moedas)):
    if moedas[i] > LIMITE:
        print("Primeiro nível com mais de", LIMITE, "moedas: nível", i + 1)
        encontrado = True
    break
```

Com a mesma lista, o programa escreve `Nenhum nível passou das 20 moedas.` Na primeira volta, o 15 não passa no `if`, e o `break` termina o ciclo na mesma. O 22 e o 25 nunca são vistos. O erro esconde-se quando o valor procurado está logo no primeiro elemento, como em `[30, 8, 22]`. Aí, a resposta sai certa por acaso. Por isso, numa pesquisa, testa-se o valor procurado no início, no meio e no fim da lista.

## Saltar uma volta com `continue`

Na lista seguinte, os níveis que ainda não jogaste estão registados com -1. Queres somar as moedas dos níveis que já jogaste. Os -1 não são moedas, e não podem entrar na soma. Na algoritmia, saltavas um valor com o `Continuar`. Em Python, escreve-se **`continue`**, do inglês "continuar". O `continue` termina só a volta atual. As linhas do corpo que estão abaixo dele não se executam nessa volta, e o ciclo passa ao elemento seguinte.

Antes de correres, prevê o total.

```python
# moedas_jogadas.py: soma só as moedas dos níveis já jogados.
# Um nível que ainda não foi jogado tem -1 na lista.
NAO_JOGADO = -1

moedas = [15, -1, 22, 0, -1]
total = 0
for quantidade in moedas:
    if quantidade == NAO_JOGADO:
        # O continue salta o resto da volta: o -1 não entra na soma.
        continue
    total = total + quantidade
print("Moedas dos níveis jogados:", total)
```

O resultado é `Moedas dos níveis jogados: 37`.

| Volta | quantidade | `quantidade == NAO_JOGADO` | O que acontece | total no fim da volta |
| --- | ---: | --- | --- | ---: |
| antes do ciclo | sem valor | não se avalia | nada | 0 |
| 1.ª | 15 | `False` | soma 15 | 15 |
| 2.ª | -1 | `True` | `continue`: salta a soma | 15 |
| 3.ª | 22 | `False` | soma 22 | 37 |
| 4.ª | 0 | `False` | soma 0 | 37 |
| 5.ª | -1 | `True` | `continue`: salta a soma | 37 |

Leitura guiada: o `continue` está dentro do `if`, e só se executa nas voltas do -1. Nessas voltas, a soma, que está abaixo, não chega a executar-se. Nas outras, o `if` não faz nada, e a soma faz-se. O 0 do quarto nível entra na soma, porque é um nível jogado em que não apanhaste moedas. O -1 é diferente: quer dizer que não há valor. Por isso é uma constante com nome, `NAO_JOGADO`, e não um número solto no meio do código.

O mesmo resultado consegue-se sem `continue`, com a soma dentro de um `if quantidade != NAO_JOGADO:`. As duas formas estão certas. O `continue` ajuda quando há valores a pôr de lado logo no início da volta, e o resto do corpo é comprido. O corpo fica com menos indentação e mais fácil de ler.

Há um cuidado que já conheces da algoritmia. Num `while`, se a atualização estiver abaixo do `continue`, também é saltada. A variável da condição não muda, e o ciclo pode nunca acabar. Nesse caso, carrega em Ctrl+C no terminal, para parar o programa. Num `for`, este perigo não existe, porque é o próprio `for` que passa ao elemento seguinte.

## A lista vazia e os três casos de teste

Uma lista pode não ter nenhum elemento. Escreve-se `[]`, e chama-se **lista vazia**. O `len([])` dá 0. Parece um caso inútil, mas aparece muitas vezes. É a lista dos níveis de quem ainda não jogou, ou a dos resultados de uma equipa antes do primeiro jogo. É o caso de zero voltas das listas: um `for` sobre uma lista vazia não dá nenhuma volta.

Muda a lista de `moedas_total.py` para `moedas = []`. Antes de correres, prevê o que acontece em cada linha. O resultado é este:

```text
Total de moedas: 0
Traceback (most recent call last):
  File "C:\Users\aluno\Documents\fp-python\moedas_total.py", line 7, in <module>
    print("Média por nível:", total / len(moedas))
                              ~~~~~~^~~~~~~~~~~~~
ZeroDivisionError: division by zero
```

O ciclo não deu nenhuma volta, e o total ficou 0, o que está certo. Mas a média fez a conta `0 / 0`. Não se pode dividir por zero, e o programa parou com `ZeroDivisionError: division by zero`, isto é, "erro de divisão por zero". É o mesmo cuidado da média sem valores, na algoritmia: antes de dividir pelo número de elementos, confirma que ele não é zero.

```python
# moedas_total.py: soma as moedas de todos os níveis e calcula a média por nível.
moedas = [15, 8, 22, 0, 25]
total = 0
for quantidade in moedas:
    total = total + quantidade
print("Total de moedas:", total)
# Sem este if, com a lista vazia, a conta seria 0 / 0 e o programa parava.
if len(moedas) > 0:
    print("Média por nível:", total / len(moedas))
else:
    print("Sem níveis, não há média.")
```

Antes de correres esta versão, prevê o que aparece com cada uma das três listas da tabela. Depois confirma, mudando a lista, guardando e correndo de cada vez.

| Lista | Total de moedas | A segunda linha |
| --- | ---: | --- |
| `[]` | 0 | Sem níveis, não há média. |
| `[12]` | 12 | Média por nível: 12.0 |
| `[15, 8, 22, 0, 25]` | 70 | Média por nível: 14.0 |

A lista vazia também faz falhar outras linhas. `moedas[0]` dá `IndexError`, porque uma lista vazia não tem o índice 0. Pelo contrário, a pesquisa de `nivel_rico.py` não tem problema nenhum. Com a lista vazia, o ciclo não dá voltas e a bandeira fica `False`. Aparece "Nenhum nível passou das 20 moedas.", o que está certo.

Por isso, cada programa com listas testa-se com três listas:

- **a lista vazia**, que mostra as divisões por zero, o índice 0 que não existe e as mensagens que não fazem sentido sem dados;
- **uma lista com um só elemento**, em que o primeiro é também o último, e que mostra os erros na primeira e na última volta;
- **uma lista com vários elementos**, que mostra os erros que precisam de mais de uma volta, como o acumulador que recomeça em cada volta.

Numa pesquisa, junta-se mais um cuidado: o valor procurado testa-se na primeira posição, no meio, na última posição e ausente. Quando há um limite, como o 20 das moedas, um dos casos tem o valor da fronteira.

## Exemplo guiado: os jogos da equipa, do pseudocódigo ao Python

Neste exemplo, passas para Python um algoritmo do guia 04 da algoritmia. Depois confirmas o resultado com os casos de teste, a começar pela lista vazia.

### Passo 1: o problema e o algoritmo

Uma equipa guarda os pontos que fez em cada jogo, e quer saber em quantos jogos fez 10 ou mais pontos. No guia 04, este problema resolveu-se com um contador, na secção "O contador":

```text
const MINIMO = 10
pontuacoes = [12, 7, 20, 5]
int jogosBons = 0
Para cada pontuacao em pontuacoes
    Se pontuacao >= MINIMO
        jogosBons = jogosBons + 1
Escreve: "Jogos com ", MINIMO, " ou mais pontos: ", jogosBons
```

### Passo 2: traduzir linha a linha

Antes de escreveres código, decide como fica cada linha em Python:

| Pseudocódigo | Python | O que muda |
| --- | --- | --- |
| `const MINIMO = 10` | `MINIMO = 10` | sem `const`; o nome em maiúsculas diz que é uma constante |
| `pontuacoes = [12, 7, 20, 5]` | `pontuacoes = [12, 7, 20, 5]` | nada: o array escreve-se como uma lista |
| `int jogosBons = 0` | `jogos_bons = 0` | sem tipo à frente; o nome com traço baixo |
| `Para cada pontuacao em pontuacoes` | `for pontuacao in pontuacoes:` | `for`, `in` e os dois pontos |
| `Se pontuacao >= MINIMO` | `if pontuacao >= MINIMO:` | `if` e os dois pontos |
| `jogosBons = jogosBons + 1` | `jogos_bons = jogos_bons + 1` | só o nome com traço baixo |
| `Escreve: "Jogos com ", MINIMO, ...` | `print("Jogos com", MINIMO, ...)` | o `print` põe sozinho os espaços entre os valores |

A estrutura não muda. O `Para cada` passa a um `for` sobre a lista, e o `Se` a um `if`. A indentação continua a dizer o que está dentro de quê. As diferenças são de escrita: os dois pontos, os nomes com traço baixo e as constantes sem `const`.

### Passo 3: o contador em Python

O programa `jogos_bons.py` é a tradução do contador. Antes de o correres, prevê quantos jogos conta.

```python
# jogos_bons.py: conta os jogos da equipa com 10 ou mais pontos.
MINIMO = 10

pontuacoes = [12, 7, 20, 5]
jogos_bons = 0
for pontuacao in pontuacoes:
    if pontuacao >= MINIMO:
        jogos_bons = jogos_bons + 1
print("Jogos com", MINIMO, "ou mais pontos:", jogos_bons)
```

O resultado é `Jogos com 10 ou mais pontos: 2`.

| Volta | pontuacao | `pontuacao >= MINIMO` | jogos_bons no fim da volta |
| --- | ---: | --- | ---: |
| antes do ciclo | sem valor | não se avalia | 0 |
| 1.ª | 12 | `True` | 1 |
| 2.ª | 7 | `False` | 1 |
| 3.ª | 20 | `True` | 2 |
| 4.ª | 5 | `False` | 2 |

Leitura guiada: o contador nasce antes do ciclo, com 0. A linha que o aumenta tem oito espaços, dentro do `if`. Por isso, só conta as voltas em que a condição é verdadeira, a do 12 e a do 20. O `print` está encostado à margem, fora do ciclo, e escreve-se uma só vez. A tabela é a do guia 04, com `True` e `False` no lugar de `true` e `false`.

### Passo 4: testar o contador

Os resultados esperados tiram-se do enunciado, e não do programa. Para cada lista, escreve primeiro o que esperas, e depois muda a linha da lista, guarda e corre.

| Lista | Porquê este caso | Esperado | Obtido |
| --- | --- | ---: | ---: |
| `[]` | a lista vazia, sem jogos | 0 | 0 |
| `[10]` | um só jogo, no valor da fronteira | 1 | 1 |
| `[9]` | um só jogo, logo abaixo da fronteira | 0 | 0 |
| `[12, 7, 20, 5]` | vários jogos, com os dois lados da fronteira | 2 | 2 |

Os quatro casos dão o esperado. Com a lista vazia, o ciclo não dá nenhuma volta, e o contador fica com o 0 do início. Zero jogos dão zero jogos bons, e a resposta está certa. Este programa não divide nem usa índices, e por isso a lista vazia não o faz parar.

O `[10]` confirma que o `>=` está certo: com `>`, o 10 não contava, e o resultado era 0. Sem este caso, a troca passava despercebida, porque os outros três dão o mesmo com `>` e com `>=`.

### Passo 5: porque o contador percorre pelo valor

O contador responde à pergunta "quantos jogos?". Para isso, só precisa de olhar para cada valor e decidir se conta. Por isso percorre pelo valor, sem índice, e não pode sair da lista.

Imagina que a pergunta era "que jogos tiveram 10 ou mais pontos?". A resposta seria uma lista de posições, como "o jogo 1 e o jogo 3". Aí, o ciclo tinha de percorrer pelo índice, com `range(0, len(pontuacoes))`, e escrever `i + 1` para cada jogo que passasse no `if`.

## Erros frequentes

Os erros desta secção são versões erradas dos programas deste guia. Para cada um, ficas a saber o que aparece, porque acontece e como se corrige. Quando um programa teu falha, segue a rotina de cinco passos. Observa e reproduz o erro, formula uma hipótese e verifica-a com os valores. Depois corrige a causa e volta a testar tudo.

Outros erros frequentes ficaram na secção da ideia que explicam:

- o índice fora da lista, em "O índice: a posição de cada elemento";
- o `range` com um número a mais, em "Percorrer a lista pelo índice, com `range` e `len`";
- mudar a variável do `for` para mudar a lista, em "Mudar um elemento pelo índice";
- a mensagem de "não encontrado" dentro do ciclo, em "Procurar um valor: a pesquisa com bandeira";
- o `break` fora do `if`, em "Parar a pesquisa com `break`";
- a média com a lista vazia, em "A lista vazia e os três casos de teste".

### Usar o valor como se fosse o índice

O que se vê: este ciclo devia escrever as moedas de cada nível, e para logo na primeira volta.

```python
# moedas_valor_indice.py: devia escrever as moedas de cada nível. Tem um erro, de propósito.
moedas = [15, 8, 22, 0, 25]
for quantidade in moedas:
    print("Nível com", moedas[quantidade], "moedas")
```

```text
Traceback (most recent call last):
  File "C:\Users\aluno\Documents\fp-python\moedas_valor_indice.py", line 4, in <module>
    print("Nível com", moedas[quantidade], "moedas")
                       ~~~~~~^^^^^^^^^^^^
IndexError: list index out of range
```

Porque acontece: na primeira volta, `quantidade` vale 15, o valor do primeiro elemento. O programa tenta ir buscar `moedas[15]`, e numa lista de cinco elementos o 15 não é um índice válido. O erro está em usar o valor de um elemento como se fosse a sua posição. São coisas diferentes: em `[15, 8, 22, 0, 25]`, o elemento de índice 0 vale 15.

Como se corrige: pelo valor, usa-se diretamente a variável de iteração, `print("Nível com", quantidade, "moedas")`. Se precisas da posição, percorre pelo índice, com `range`, e usa `moedas[i]`.

### Dar à variável do `for` o nome da lista

O que se vê: com `for moedas in moedas:`, o total sai certo, 70, mas a linha da média para o programa.

```python
# moedas_mesmo_nome.py: devia somar as moedas e calcular a média. Tem um erro, de propósito.
moedas = [15, 8, 22, 0, 25]
total = 0
for moedas in moedas:
    total = total + moedas
print("Total de moedas:", total)
print("Média por nível:", total / len(moedas))
```

```text
Total de moedas: 70
Traceback (most recent call last):
  File "C:\Users\aluno\Documents\fp-python\moedas_mesmo_nome.py", line 7, in <module>
    print("Média por nível:", total / len(moedas))
                                      ~~~^^^^^^^^
TypeError: object of type 'int' has no len()
```

A mensagem quer dizer "erro de tipo: um valor do tipo `int` não tem `len`".

Porque acontece: em cada volta, o `for` dá um valor novo à variável `moedas`, que era o nome da lista. No fim do ciclo, `moedas` guarda o último elemento, o 25, um inteiro. A lista perdeu o nome, e o `len` recebeu um número.

Como se corrige: a variável de iteração tem sempre um nome diferente do da lista. O hábito do singular para o elemento e do plural para a lista evita o erro, como em `for nota in notas:`.

### Escrever o número de elementos à mão

O que se vê: depois de jogares um sexto nível, com 30 moedas, a lista passou a `[15, 8, 22, 0, 25, 30]`. O programa continua a dizer 70 moedas, e não 100. Não aparece nenhuma mensagem.

```python
# moedas_numero_a_mao.py: devia somar as moedas de todos os níveis. Tem um erro, de propósito.
moedas = [15, 8, 22, 0, 25, 30]
total = 0
for i in range(0, 5):
    total = total + moedas[i]
print("Total de moedas:", total)
```

Porque acontece: o `range(0, 5)` foi escrito quando a lista tinha cinco elementos. A lista cresceu, e o ciclo continua a parar no índice 4. O sexto nível nunca é somado. É um erro de lógica, e só o vê quem compara com o resultado esperado. Se a lista encolhesse, o mesmo `range` dava `IndexError`.

Como se corrige: usa `range(0, len(moedas))`, ou percorre pelo valor, com `for quantidade in moedas:`. Assim, o ciclo acompanha a lista.

## Palavras novas deste guia

- Lista: o array do pseudocódigo, em Python; guarda vários valores, numa ordem fixa, com um só nome.
- Elemento: cada valor guardado numa lista.
- Índice: a posição de um elemento numa lista, a contar do 0.
- Último índice válido: o número de elementos menos 1, `len(lista) - 1`.
- Índice fora da lista: um índice que não existe na lista, como o 5 numa lista de cinco elementos.
- `IndexError`: o erro de execução que aparece quando se usa um índice fora da lista.
- `len`: a função predefinida que diz quantos elementos tem uma lista.
- Percorrer uma lista: passar por todos os elementos, um a um, fazendo alguma coisa com cada um.
- Variável de iteração: a variável do `for` que percorre uma lista pelo valor, e que recebe um elemento em cada volta. No `for` com `range`, chama-se variável de controlo.
- Percorrer pelo valor: percorrer com `for elemento in lista:`, em que a variável recebe o elemento, e não a posição.
- Percorrer pelo índice: percorrer com `for i in range(0, len(lista)):`, em que a variável recebe a posição.
- Pesquisa linear: procurar um valor olhando para os elementos um a um, pela ordem da lista.
- Bandeira: uma variável `bool` que começa em `False` e passa a `True` quando acontece o que se procura.
- `break`: a instrução que termina o ciclo imediatamente; é o `Parar` do pseudocódigo.
- `continue`: a instrução que termina só a volta atual e passa à seguinte; é o `Continuar` do pseudocódigo.
- Lista vazia: a lista sem nenhum elemento, `[]`, com o `len` igual a 0.
- Três casos de teste: a lista vazia, a lista com um elemento e a lista com vários.

## Verificar o que aprendeste

Usa estas perguntas para te testares. Responde a cada uma sem olhar para o guia, e confirma no computador as que se podem correr. Se não conseguires, volta à secção que explica a ideia.

1. Em `idades = [15, 14, 16, 15]`, quanto vale `idades[1]`? Quanto dá `len(idades)`? Qual é o último índice válido?
2. O que acontece com `print(idades[4])`, e que tipo de erro é?
3. Escreve a linha que mostra o último elemento de uma lista `tempos`, seja qual for o tamanho dela.
4. Para cada tarefa, diz se percorres a lista pelo valor ou pelo índice, e porquê. A primeira é somar os minutos de jogo de uma semana. A segunda é dizer em que dia jogaste mais de duas horas. A terceira é pôr a 0 os valores negativos de uma lista.
5. Porque é que `for nota in notas:`, com o corpo `nota = 0`, não põe as notas a zero? Como se faz?
6. Numa pesquisa, porque é que a mensagem de "não encontrado" se escreve depois do ciclo, e não num `else` dentro dele?
7. Quantas voltas dá o ciclo de `primeiro_nivel_rico.py` com `moedas = [30, 8, 22]`? E com `moedas = [5, 8, 12]`?
8. Qual é a diferença entre o `break` e o `continue`? Dá um exemplo de cada um.
9. Faz a tabela de iterações de um ciclo que soma os elementos de `[4, -1, 6]` e salta os negativos com `continue`. Quanto vale o total no fim?
10. O que acontece a `total / len(lista)` com a lista vazia, e como o evitas?
11. Que três listas usas para testar um programa que conta valores? Numa pesquisa, em que posições pões o valor procurado?
12. Traduz para Python estas três linhas de pseudocódigo: `Para cada nota em notas`, `Se nota >= 10` e `positivas = positivas + 1`.

## O que vem a seguir

Para praticar este tema, faz o [laboratório](laboratorios/05-listas-laboratorio.md) e depois a [ficha de exercícios](exercicios/05-listas-exercicios.md). O laboratório constrói um programa sobre a equipa de um jogo, e a ficha tem exercícios para contar, somar, mudar e procurar em listas.

O tema seguinte é [06 Funções](06-funcoes.md). Os programas deste guia já repetem partes: somar uma lista, calcular uma média, procurar um valor. No tema seguinte, vais dar um nome a cada uma dessas partes, com as funções do Python. Vais também testá-las sozinhas, antes de as juntar.

![Rodapé](../imagens/rodape.png)
