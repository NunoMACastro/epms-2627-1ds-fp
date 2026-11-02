![Cabeçalho](../imagens/cabecalho.png)

# Dados e interação

Módulo Criar aplicações em linguagem de programação Python. Neste guia, os teus programas passam a guardar valores, a fazer contas e a ler o que a pessoa escreve no teclado. Para praticar, há o [laboratório](laboratorios/02-dados-e-interacao-laboratorio.md) e a [ficha de exercícios](exercicios/02-dados-e-interacao-exercicios.md) deste tema.

No tema anterior, os programas só escreviam no ecrã textos e números fixos, sempre iguais. A partir de agora, um programa guarda valores com nome, calcula com eles e responde ao que a pessoa escreve. Vais passar para Python quase tudo o que fizeste no guia 02 da algoritmia. São as variáveis, as constantes, os tipos, as contas, o `ler valor` e o `Escreve:`. Ainda não há decisões nem repetições. Todos os programas deste guia são sequências: cada linha executa-se uma vez, de cima para baixo. As decisões são do tema seguinte, e as repetições do outro a seguir.

Lê o guia ao teu ritmo, em várias vezes, com o computador ao lado. Cada exemplo pode ser copiado para um ficheiro na tua pasta `fp-python`, ou escrito na consola do Python, e corrido.

## Neste guia

1. O que vais aprender
2. O que já sabes e vais usar
3. Guardar um valor numa variável
4. Atribuir outra vez: o valor antigo perde-se
5. Os nomes das variáveis
6. As constantes
7. Os tipos dos valores
8. As contas e os operadores
9. A divisão com `/` dá sempre um `float`
10. A divisão inteira e o resto: `//` e `%`
11. A potência: `**`
12. A ordem das contas
13. A divisão por zero
14. Funções predefinidas
15. Ler do teclado com `input`
16. Converter o texto lido num número: `int` e `float`
17. Quando a conversão não é possível
18. Juntar textos com `+` e `str`
19. O Python 2 na leitura e na divisão
20. Exemplo guiado: converter minutos em horas e minutos, em Python
21. Erros frequentes
22. Palavras novas deste guia
23. Verificar o que aprendeste
24. O que vem a seguir
25. Para saber mais

## O que vais aprender

No fim deste guia, consegues:

- guardar valores em variáveis e em constantes, com nomes escritos à maneira do Python, e seguir numa tabela de trace uma variável que muda;
- dizer de que tipo é um valor, `int`, `float`, `str` ou `bool`, reconhecer o `None` e confirmar o tipo com `type`;
- escrever contas com os operadores do Python e prever o resultado e o tipo, também na divisão inteira, no resto e na potência;
- usar as funções predefinidas `abs`, `max`, `min`, `round`, `int`, `float`, `str` e `type`;
- ler um valor do teclado, convertê-lo no tipo certo antes de fazer contas e juntar textos com `+`;
- traduzir para Python um algoritmo de sequência e confirmá-lo com os casos de teste calculados à mão;
- reconhecer os erros mais frequentes deste tema e o código antigo do Python 2 na leitura e na divisão.

## O que já sabes e vais usar

- Criar, guardar e correr um ficheiro `.py` na pasta `fp-python`, no terminal ou com o botão de correr: guia [01 Do pseudocódigo ao Python](01-do-pseudocodigo-ao-python.md).
- A consola do Python, com o `>>>`, e o `exit()` para sair dela: guia [01 Do pseudocódigo ao Python](01-do-pseudocodigo-ao-python.md).
- O `print` com vários valores separados por vírgulas, o espaço que ele põe entre eles e o `print()` vazio: guia [01 Do pseudocódigo ao Python](01-do-pseudocodigo-ao-python.md).
- Os comentários com `#`: guia [01 Do pseudocódigo ao Python](01-do-pseudocodigo-ao-python.md).
- Os três tipos de erro, o traceback lido de baixo para cima e a rotina de cinco passos: guia [01 Do pseudocódigo ao Python](01-do-pseudocodigo-ao-python.md).
- As variáveis, as constantes e os quatro tipos, em pseudocódigo: guia [02 Estado, sequência e representações](../01-algoritmos/02-estado-sequencia-representacoes.md), secções "Variáveis", "Constantes" e "Tipos de dados".
- A atribuição, como `total = total + 5`: guia [02](../01-algoritmos/02-estado-sequencia-representacoes.md), secção "Atribuição: dar um valor não é perguntar se é igual".
- As contas com `/`, `div` e `resto`, e a ordem das contas: guia [02](../01-algoritmos/02-estado-sequencia-representacoes.md), secção "Operadores aritméticos".
- O `ler valor` e o `Escreve:`: guia [02](../01-algoritmos/02-estado-sequencia-representacoes.md), secção "Entrada e saída: `ler valor` e `Escreve:`".
- A tabela de trace: guia [02](../01-algoritmos/02-estado-sequencia-representacoes.md), secção "Tabela de trace".
- O algoritmo que converte minutos em horas e minutos: guia [02](../01-algoritmos/02-estado-sequencia-representacoes.md), secção "Exemplo guiado: converter minutos em horas e minutos".
- Os casos de teste escolhidos à volta do sítio onde a resposta muda: guia [03 Decisões e validação](../01-algoritmos/03-decisoes-e-validacao.md), secção "Fronteiras e casos de teste".
- Chamar uma função, com argumentos, e o valor que ela devolve: guia [05 Funções e modelo integrado](../01-algoritmos/05-funcoes-e-modelo-integrado.md), secções "Chamar uma função" e "`devolver`".
- As quatro operações, a divisão com resto, as potências e a ordem das operações, da matemática do ensino básico.

## Guardar um valor numa variável

No tema anterior, um programa que escrevesse "Passaram 2 horas" tinha o 2 escrito dentro do texto. Para escrever outro número, era preciso mudar o programa. E se o programa precisasse do mesmo número em três sítios, o número aparecia três vezes. Falta um sítio para guardar o valor, com um nome, para o usar quando for preciso.

Na algoritmia, esse sítio era uma **variável**: um espaço com um nome, onde se guarda um valor que pode mudar. Em Python é igual. A diferença está na forma de escrever. Em pseudocódigo escrevias `int horas = 2`, com o tipo à frente. Em Python escreve-se só o nome, o sinal `=` e o valor:

```python
horas = 2
```

O `=` é a **atribuição**, como no pseudocódigo. Guarda o valor da direita na variável da esquerda. Lê-se "horas recebe 2", e não "horas é igual a 2". É uma ordem, e não uma pergunta.

A variável nasce nesta linha, a primeira que lhe dá um valor. Antes dela, para o Python, o nome `horas` não existe. Depois dela, o nome `horas` vale 2 até alguém lhe dar outro valor.

Para usar o valor, escreve-se o nome. É aqui que as aspas fazem toda a diferença, como no `Escreve:` do pseudocódigo. Com aspas, `"horas"` é um texto, e aparece a palavra. Sem aspas, `horas` é o nome de uma variável, e aparece o valor dela.

Antes de correres este exemplo, tenta prever o que escreve cada um dos três `print`.

```python
# horas.py: o mesmo nome escrito com aspas e sem aspas.
horas = 2
print("horas")
print(horas)
print("Passaram", horas, "horas")
```

O resultado é este:

```text
horas
2
Passaram 2 horas
```

Leitura guiada: a variável `horas` nasce na linha 2, com o valor 2. O primeiro `print` recebe um texto, entre aspas, e escreve-o tal e qual. O segundo recebe o nome da variável, sem aspas, e escreve o valor que lá está. O terceiro recebe três valores, separados por vírgulas: o texto "Passaram", o valor de `horas` e o texto "horas". Escreve-os com um espaço entre cada dois, como viste no tema anterior.

Repara que a palavra `horas` aparece duas vezes na última linha, primeiro sem aspas e depois com aspas. São coisas diferentes. A primeira, sem aspas, é um nome que o Python procura. A segunda, com aspas, são cinco letras que ele escreve.

Lembra-te também dos espaços. No pseudocódigo escrevias `Escreve: "Passaram ", horas, " horas"`, com os espaços dentro das aspas. No Python, o `print` já os põe. Se os copiares para dentro das aspas, ficam dois espaços seguidos no ecrã.

## Atribuir outra vez: o valor antigo perde-se

Num jogo, as moedas de um jogador mudam a toda a hora. Apanha um baú e ganha moedas, compra um escudo e gasta-as. Um programa que acompanhe as moedas tem de mudar o valor da variável muitas vezes.

Para mudar o valor, faz-se outra atribuição, com o mesmo nome à esquerda. A atribuição executa-se em duas fases, por esta ordem, tal como no pseudocódigo. Primeiro calcula-se o lado direito, com os valores que as variáveis têm nesse momento. Depois guarda-se o resultado na variável da esquerda, e o valor antigo perde-se.

Antes de correres este exemplo, tenta prever as três linhas que aparecem no ecrã.

```python
# moedas.py: as moedas de um jogador mudam ao longo de um nível.
moedas = 40
print("No início:", moedas)
moedas = moedas + 25
print("Depois do baú:", moedas)
moedas = moedas - 30
print("Depois de comprar um escudo:", moedas)
```

O resultado é este:

```text
No início: 40
Depois do baú: 65
Depois de comprar um escudo: 35
```

Leitura guiada: lê o programa de cima para baixo e segue o valor de `moedas`. Na linha 2, a variável nasce com 40. Na linha 4, o lado direito calcula-se primeiro, com o valor que `moedas` tem nesse momento: 40 mais 25 dá 65. Só depois o 65 fica guardado em `moedas`, e o 40 perde-se. Na linha 6 acontece o mesmo com a subtração: 65 menos 30 dá 35.

Lida como uma equação da matemática, a linha `moedas = moedas + 25` seria impossível, porque nenhum número é igual a ele próprio mais 25. Lida como atribuição, faz todo o sentido: "moedas recebe o valor que moedas tem agora, mais 25".

Quando segues uma variável que muda, a ferramenta é a da algoritmia, a tabela de trace. Cada linha da tabela é uma instrução executada, com o valor de cada variável depois dela e o que aparece no ecrã. A coluna "Linha" diz o número da linha no ficheiro, o que aparece à esquerda no VS Code. O comentário da linha 1 não se executa e não tem passo.

| Passo | Linha | Instrução executada | `moedas` | Ecrã |
| ---: | ---: | --- | ---: | --- |
| 0 | | antes de começar | sem valor | nada |
| 1 | 2 | `moedas = 40` | 40 | nada |
| 2 | 3 | `print("No início:", moedas)` | 40 | No início: 40 |
| 3 | 4 | `moedas = moedas + 25` | 65 | nada |
| 4 | 5 | `print("Depois do baú:", moedas)` | 65 | Depois do baú: 65 |
| 5 | 6 | `moedas = moedas - 30` | 35 | nada |
| 6 | 7 | `print("Depois de comprar um escudo:", moedas)` | 35 | Depois de comprar um escudo: 35 |

Compara cada linha da tabela com a de cima. A de cima é o estado antes da instrução, e a própria linha é o estado depois. Um `print` nunca muda nenhuma variável. Só escreve no ecrã os valores que elas têm nesse momento.

A perda do valor antigo tem consequências, e há um caso clássico que as mostra. Alguém quer trocar os valores de duas variáveis e escreve o programa seguinte. Antes de correres, tenta prever os dois números que aparecem.

```python
# troca.py: uma tentativa de trocar os valores de duas variáveis.
a = 4
b = 9
a = b
b = a
print(a, b)
```

O resultado é este:

```text
9 9
```

Leitura guiada: na linha 4, `a` recebe o valor de `b` e passa a valer 9. O 4 perdeu-se, porque não ficou guardado em lado nenhum. Na linha 5, `b` recebe o valor que `a` tem nesse momento, que já é 9. Quem esperava `9 4` esqueceu-se de que, depois da linha 4, o 4 já não existe. Uma tabela de trace com duas colunas, uma para `a` e outra para `b`, mostra-o na linha 4.

Há outro erro que vem da mesma regra: uma variável só existe a partir da linha onde nasce. Se uma linha usar a variável antes disso, o Python não conhece o nome. Antes de correres, tenta prever o que acontece.

```python
# antes.py: usa uma variável antes da linha onde ela nasce.
print("Pontos:", pontos)
pontos = 10
```

O programa para logo na linha 2:

```text
Traceback (most recent call last):
  File "C:\Users\aluno\Documents\fp-python\antes.py", line 2, in <module>
    print("Pontos:", pontos)
                     ^^^^^^
NameError: name 'pontos' is not defined
```

Leitura guiada: lê a mensagem de baixo para cima, como aprendeste no tema anterior. A última linha quer dizer "erro de nome: o nome 'pontos' não está definido". As de cima dizem onde: no ficheiro `antes.py`, na linha 2, e os sinais `^` estão debaixo de `pontos`. O caminho do ficheiro, a seguir a `File`, muda de computador para computador. É um erro de execução: o programa estava bem escrito, começou a correr e parou na linha 2, porque `pontos` só nasce na linha 3. Corrige-se trocando as duas linhas, para a variável nascer antes de ser usada.

## Os nomes das variáveis

Um nome bom diz o que a variável guarda. `moedas` diz muito mais do que `m` ou `x`. Quem lê o programa uma semana depois, tu incluído, percebe-o sem ter de adivinhar. Os nomes curtos, como `a` e `b`, ficam para os exemplos de treino, que só seguem contas, sem um problema por trás.

O Python tem regras para os nomes, e recusa os que não as cumprem:

- um nome tem letras, algarismos e o traço baixo, `_`;
- não começa por um algarismo: `2equipas` é recusado, e `equipas_2` é aceite;
- não tem espaços nem hífenes: `total pontos` e `total-pontos` são recusados;
- as maiúsculas contam: `moedas` e `Moedas` são duas variáveis diferentes.

Um nome com um espaço dá um erro de sintaxe, e o programa nem começa a correr. Pensa neste programa:

```python
# nome_com_espaco.py: um nome de variável com um espaço no meio.
total pontos = 0
```

O que aparece, em vez de o programa correr:

```text
  File "C:\Users\aluno\Documents\fp-python\nome_com_espaco.py", line 2
    total pontos = 0
          ^^^^^^
SyntaxError: invalid syntax
```

Quer dizer "erro de sintaxe: escrita inválida". O Python leu `total` como um nome e não percebeu o que fazia ali a palavra `pontos`, logo a seguir.

Além das regras, há uma forma de escrever os nomes que toda a gente segue em Python. As palavras escrevem-se todas em minúsculas, com um traço baixo entre elas: `total_pontos`, `moedas_por_nivel`. No pseudocódigo das aulas escrevias de outra maneira, com uma maiúscula a separar as palavras: `totalPontos`. O Python aceitava esse nome, mas não é a forma da linguagem.

| Pseudocódigo | Python |
| --- | --- |
| `int totalPontos = 0` | `total_pontos = 0` |
| `float alturaMedia = 1.65` | `altura_media = 1.65` |
| `string nomeJogador = "Rita"` | `nome_jogador = "Rita"` |
| `const MINUTOS_POR_HORA = 60` | `MINUTOS_POR_HORA = 60` |

Uma forma combinada entre as pessoas, que a linguagem não obriga a cumprir, chama-se uma **convenção**. Quase todo o código Python que vais ler, na documentação e nos exemplos, segue esta convenção, e é ela que usamos nas aulas. Um programa com `totalPontos` corre na mesma, mas destoa de todo o código à volta.

Escreve os nomes sem acentos nem cedilhas, como `numero`, `preco` e `vitorias`. O Python aceita `número`, mas um nome sem acentos escreve-se igual em qualquer teclado e em qualquer computador. Os acentos ficam para os textos entre aspas, que aparecem no ecrã, como em `print("Vitórias:", vitorias)`.

Há palavras que não podem ser nomes, porque já pertencem à linguagem. Chamam-se **palavras reservadas**. Neste guia vais conhecer três, `True`, `False` e `None`. As outras, como o `if`, aparecem nos temas seguintes, cada uma quando for precisa. O VS Code pinta as palavras reservadas de outra cor, e isso ajuda a reconhecê-las.

## As constantes

Num jogo, cada estrela vale 50 pontos. Esse 50 é uma regra do jogo, e não muda enquanto o programa corre. Se aparecer solto no meio de uma conta, quem lê não sabe o que quer dizer. E se a regra mudar, tens de o procurar e trocar em todos os sítios onde aparece.

Na algoritmia, um valor destes era uma constante, com `const` à frente. O Python não tem a palavra `const`. Uma **constante**, em Python, é uma variável com o nome todo em maiúsculas, que se combina não mudar: `const PONTOS_POR_ESTRELA = 50` passa a `PONTOS_POR_ESTRELA = 50`.

O nome em maiúsculas é um aviso para quem lê: este valor é uma regra do problema, e o programa não o muda. O Python não impede a mudança. É uma convenção, como a dos nomes com traço baixo, e respeita-se. As constantes escrevem-se no início do programa, logo a seguir ao comentário, para se encontrarem depressa.

Antes de correres este exemplo, tenta prever o número de pontos.

```python
# estrelas.py: os pontos que um jogador ganha pelas estrelas de um nível.
PONTOS_POR_ESTRELA = 50

estrelas = 7
pontos = estrelas * PONTOS_POR_ESTRELA
print("Estrelas:", estrelas)
print("Pontos:", pontos)
```

O resultado é este:

```text
Estrelas: 7
Pontos: 350
```

Leitura guiada: a constante vem primeiro, separada do resto por uma linha em branco. A linha 5 lê-se como uma frase: os pontos são as estrelas vezes os pontos de cada estrela. Com o número no lugar da constante, `pontos = estrelas * 50`, o programa dava o mesmo resultado, mas o leitor tinha de adivinhar de onde vem o 50. E se o jogo passar a dar 60 pontos por estrela, muda-se só a linha 2.

## Os tipos dos valores

Na algoritmia, cada variável nascia com o tipo à frente: `int`, `float`, `string` ou `bool`. Em Python, o tipo não se escreve, mas continua a existir. Cada valor tem um tipo, e o tipo diz que contas se podem fazer com ele. Somar dois números dá um número. Somar dois textos faz outra coisa, e a secção "Juntar textos com `+` e `str`" mostra o quê.

O Python descobre o tipo pelo próprio valor. Quando escreves `moedas = 40`, ele vê que 40 é um número inteiro e guarda-o como tal. Diz-se por isso que o tipo está no valor, e não na variável. A esta forma de funcionar chama-se **tipagem dinâmica**: o Python descobre o tipo de cada valor enquanto o programa corre, sem o escreveres.

Os tipos que conheces do pseudocódigo existem todos, com um nome abreviado e uma novidade:

| Tipo | O que guarda | Exemplos em Python |
| --- | --- | --- |
| `int` | um número inteiro, de *integer*, inteiro | `7`, `0`, `-3` |
| `float` | um número com parte decimal, de *floating point*, vírgula flutuante | `7.0`, `2.5`, `-0.1` |
| `str` | um texto, a abreviatura de *string*, uma cadeia de caracteres | `"7"`, `"Olá"`, `""` |
| `bool` | só verdadeiro ou falso, de George Boole, o matemático | `True`, `False` |
| `NoneType` | só o valor `None`, que quer dizer "nenhum valor" | `None` |

O tipo `string` do pseudocódigo escreve-se `str` no Python. O texto `""`, com as duas aspas juntas, é o texto vazio: um texto sem nenhum carácter lá dentro.

Os valores lógicos escrevem-se `True` e `False`, com a primeira letra maiúscula. Neste tema só os vais ver como valores. No tema seguinte, as comparações, como "a nota é maior do que 10?", dão `True` ou `False`, e o programa decide por elas.

O `None` é novo. É o valor que quer dizer "aqui não há nada". Vais vê-lo neste guia na secção das funções predefinidas.

Os números com parte decimal escrevem-se com ponto, `2.5`, e nunca com vírgula. Já era assim no pseudocódigo. No Python, a vírgula tem outro trabalho: separa valores, como no `print`.

Para saber de que tipo é um valor, pergunta-se ao Python com `type`. Escreve-se `type` e, entre parênteses, o valor. O `type` é uma função, como o `print` do tema anterior: um nome seguido de parênteses, com o valor lá dentro. O `print` escreve no ecrã. O `type` dá uma resposta, e na consola a resposta aparece logo na linha de baixo.

Antes de leres as respostas, tenta prever o tipo de cada um destes valores, escritos na consola do Python.

```text
>>> type(7)
<class 'int'>
>>> type(7.0)
<class 'float'>
>>> type("7")
<class 'str'>
>>> type(True)
<class 'bool'>
>>> type(None)
<class 'NoneType'>
```

Leitura guiada: o Python responde com `<class '...'>`, e o nome entre as aspas simples é o tipo. No Python, cada tipo é uma "classe", e é daí que vem a palavra. Por agora, lê `<class 'int'>` como "o tipo é `int`". Repara que `7`, `7.0` e `"7"` são três valores diferentes. O primeiro é um inteiro. O segundo tem parte decimal, mesmo que seja zero. O terceiro é um texto com um algarismo lá dentro, e com ele não se fazem contas.

O `type` também serve para uma variável. Responde com o tipo do valor que ela tem nesse momento. E como o tipo está no valor, a mesma variável pode receber um valor de outro tipo. Antes de leres, tenta prever as duas respostas.

```text
>>> x = 7
>>> type(x)
<class 'int'>
>>> x = "sete"
>>> type(x)
<class 'str'>
```

Leitura guiada: na primeira linha, `x` nasce com um inteiro. Na terceira, recebe um texto, e o inteiro perde-se, como em qualquer atribuição. O Python deixa fazer isto, mas nas aulas evita-se. Uma variável guarda sempre o mesmo género de coisa, para o nome dizer sempre o mesmo. As linhas com `=` na consola não mostram nada, porque uma atribuição guarda um valor, e não dá resposta.

O erro típico desta secção é escrever os valores lógicos como no pseudocódigo, em minúsculas:

```text
>>> encontrado = true
Traceback (most recent call last):
  File "<python-input-0>", line 1, in <module>
    encontrado = true
                 ^^^^
NameError: name 'true' is not defined. Did you mean: 'True'?
```

Quer dizer "erro de nome: o nome 'true' não está definido. Querias dizer 'True'?". Para o Python, `true` em minúsculas é o nome de uma variável que nunca nasceu. Na consola, o ficheiro aparece como `<python-input-0>`, e o número conta as linhas que já escreveste nela. Corrige-se escrevendo `True`.

## As contas e os operadores

As contas escrevem-se quase como no pseudocódigo, com **operadores**: os sinais que dizem que conta se faz. Mudam a divisão inteira e o resto, que passam de palavras a sinais. E há um operador novo, a potência.

| Pseudocódigo | Python | O que faz | Exemplo | Resultado |
| --- | --- | --- | --- | ---: |
| `+` | `+` | soma | `7 + 2` | `9` |
| `-` | `-` | subtração | `7 - 2` | `5` |
| `*` | `*` | multiplicação | `7 * 2` | `14` |
| `/` | `/` | divisão, com parte decimal | `7 / 2` | `3.5` |
| `div` | `//` | divisão inteira: quantas vezes cabe | `7 // 2` | `3` |
| `resto` | `%` | o que sobra da divisão inteira | `7 % 2` | `1` |
| não havia | `**` | potência | `7 ** 2` | `49` |

As secções seguintes tratam um operador ou uma regra de cada vez.

## A divisão com `/` dá sempre um `float`

Na algoritmia, 21 a dividir por 3 dava 7. No Python também dá 7, mas escrito de outra maneira, e isso surpreende quem não sabe a regra.

Antes de leres os resultados, tenta prever o que a consola mostra em cada linha. Repara bem na primeira.

```text
>>> 21 / 3
7.0
>>> 7 / 2
3.5
>>> 10 - 4
6
>>> 2 * 1.5
3.0
>>> 3 + 2.0
5.0
```

Leitura guiada: `21 / 3` dá `7.0`, e não `7`. No Python, a divisão com `/` dá sempre um `float`, mesmo quando a conta é exata. O valor é o mesmo, sete, mas o tipo é outro. É por isso que, nos teus programas, uma média de 21 pontos em 3 jogos aparece como `7.0`. As outras contas seguem uma regra simples. Entre dois `int`, a soma, a subtração e a multiplicação dão um `int`, como `10 - 4`. Basta um `float` na conta para o resultado ser `float`, como em `2 * 1.5` e em `3 + 2.0`.

O `7.0` não é um erro. Quando quiseres mostrar menos casas decimais, ou nenhuma, há a função `round`, da secção "Funções predefinidas". E quando quiseres mesmo um inteiro, como "quantas vezes cabe", a conta certa é outra, a da secção seguinte.

## A divisão inteira e o resto: `//` e `%`

Imagina 17 rebuçados para repartir por 5 amigos, sem partir nenhum. Cada amigo recebe 3, e sobram 2. Na algoritmia, eram as contas `17 div 5` e `17 resto 5`. No Python, o `div` escreve-se `//`, com duas barras, e o `resto` escreve-se `%`.

Antes de leres os resultados, tenta prever o que dá cada linha.

```text
>>> 17 // 5
3
>>> 17 % 5
2
>>> 5 * 3 + 2
17
>>> 18 % 2
0
>>> 17 % 2
1
```

Leitura guiada: `17 // 5` diz quantas vezes o 5 cabe inteiro no 17, e dá 3, um `int`. `17 % 5` diz o que sobra, e dá 2. A terceira linha é a confirmação da algoritmia: o divisor vezes a divisão inteira, mais o resto, dá o número de partida. As duas últimas linhas mostram um uso frequente do resto. Um número a dividir por 2 tem resto 0 quando é par e resto 1 quando é ímpar.

O `//` e o `%` usam-se quando as quantidades são inteiras e a parte decimal não faz sentido: pessoas, cartas, minutos, moedas. O `/` usa-se quando a parte decimal interessa, como numa média. Nas aulas, usamos o `//` e o `%` só com números inteiros, e com o divisor maior do que zero, como na algoritmia.

Antes de correres este programa, tenta prever as duas linhas que aparecem.

```python
# cartas.py: reparte as cartas de um baralho pelos jogadores, sem partir nenhuma.
CARTAS_DO_BARALHO = 52

jogadores = 5
cartas_por_jogador = CARTAS_DO_BARALHO // jogadores
cartas_que_sobram = CARTAS_DO_BARALHO % jogadores
print("Cada jogador recebe", cartas_por_jogador, "cartas")
print("Sobram", cartas_que_sobram, "cartas")
```

O resultado é este:

```text
Cada jogador recebe 10 cartas
Sobram 2 cartas
```

Leitura guiada: o 52 é uma regra do baralho, e por isso é uma constante. O número de jogadores é um dado, que muda de jogo para jogo, e por isso é uma variável. A linha 5 diz quantas vezes o 5 cabe inteiro no 52, 10 vezes, e são essas as cartas de cada jogador. A linha 6 diz o que sobra, 2. Confirma: 5 vezes 10, mais 2, dá 52.

O erro típico é usar `/` onde devia estar `//`. Com `CARTAS_DO_BARALHO / jogadores`, cada jogador receberia `10.4` cartas, o que não existe. Pergunta-te sempre se o resultado pode ter parte decimal. Cartas inteiras não podem.

## A potência: `**`

O Python tem um operador que o pseudocódigo das aulas não tinha. A **potência** escreve-se com dois asteriscos: `2 ** 3` é 2 elevado a 3, ou seja, 2 vezes 2 vezes 2.

Antes de leres os resultados, tenta prever cada linha.

```text
>>> 2 ** 3
8
>>> 10 ** 2
100
>>> 2 ** 10
1024
```

Leitura guiada: são potências como as da matemática. 2 elevado a 3 é 2 vezes 2 vezes 2, e dá 8. 10 elevado a 2 é 10 vezes 10, e dá 100. 2 elevado a 10 é o 2 multiplicado por si próprio dez vezes, e dá 1024. Entre dois `int`, a potência dá um `int`.

Não confundas `**` com `*`. `2 * 3` é uma multiplicação e dá 6. `2 ** 3` é uma potência e dá 8.

## A ordem das contas

Numa conta com vários operadores, a ordem é a da matemática, como no pseudocódigo:

1. primeiro, o que está entre parênteses;
2. depois, as potências, com `**`;
3. depois, as multiplicações e as divisões, com `*`, `/`, `//` e `%`;
4. por fim, as somas e as subtrações.

Entre operações do mesmo nível, faz-se da esquerda para a direita. Antes de leres os resultados, tenta prever cada linha.

```text
>>> 2 + 3 * 4
14
>>> (2 + 3) * 4
20
>>> 2 * 3 ** 2
18
>>> 20 / 2 * 5
50.0
>>> 20 / (2 * 5)
2.0
```

Leitura guiada: em `2 + 3 * 4`, a multiplicação faz-se primeiro, 3 vezes 4 dá 12, e só depois a soma, que dá 14. Os parênteses mudam a ordem, e `(2 + 3) * 4` dá 20. Em `2 * 3 ** 2`, a potência vem antes da multiplicação: 3 ao quadrado dá 9, e 2 vezes 9 dá 18. Em `20 / 2 * 5`, a divisão e a multiplicação estão no mesmo nível, e fazem-se da esquerda para a direita. 20 a dividir por 2 dá 10, e 10 vezes 5 dá 50. Com os parênteses da última linha, a multiplicação faz-se primeiro.

Onde isto mais engana é na média. A média de dois testes é a soma dos dois, a dividir por 2. Antes de correres este programa, tenta prever as duas linhas.

```python
# media.py: a média de dois testes, com e sem parênteses.
teste1 = 14
teste2 = 17
print("Sem parênteses:", teste1 + teste2 / 2)
print("Com parênteses:", (teste1 + teste2) / 2)
```

O resultado é este:

```text
Sem parênteses: 22.5
Com parênteses: 15.5
```

Leitura guiada: sem parênteses, a divisão faz-se primeiro, e só o segundo teste é dividido. 17 a dividir por 2 dá 8.5, e 14 mais 8.5 dá 22.5. Uma média de 22.5 em testes de 0 a 20 é impossível, e isso devia levantar logo a suspeita. Com os parênteses, a soma faz-se primeiro, 31, e a divisão depois, 15.5.

É um erro de lógica. O programa corre até ao fim, sem mensagem nenhuma, e dá o resultado errado. Só o encontras se calculares à mão o resultado esperado e o comparares com o que o programa mostra. Na dúvida sobre a ordem, põe parênteses. Não custam nada e tiram a dúvida a quem ler.

## A divisão por zero

Na matemática, uma divisão por zero não tem resultado. No Python também não. Se um programa tentar dividir por zero, para nessa linha.

Pensa no `cartas.py` com `jogadores = 0`, na linha 4. Antes de leres, tenta prever o que acontece.

```text
Traceback (most recent call last):
  File "C:\Users\aluno\Documents\fp-python\cartas.py", line 5, in <module>
    cartas_por_jogador = CARTAS_DO_BARALHO // jogadores
                         ~~~~~~~~~~~~~~~~~~^^~~~~~~~~~~
ZeroDivisionError: division by zero
```

Leitura guiada: a última linha quer dizer "erro de divisão por zero". As de cima dizem que foi na linha 5. Por baixo da linha, os `~` sublinham as partes da conta, e os `^` apontam a operação que falhou, o `//`. O mesmo acontece com o `/` e com o `%`, porque as três contas são divisões. É um erro de execução: o programa estava bem escrito, mas aquela linha não se consegue fazer com aqueles valores.

Repara que a mensagem aponta a linha 5, mas o valor que causou o erro nasceu na linha 4. A linha apontada é onde o Python deu pelo problema, e a causa pode estar antes. É por isso que a mensagem é uma pista, e não a resposta.

Os programas deste tema ainda não conseguem evitar a divisão por zero, porque não sabem decidir. Por agora, um programa que divide por um valor dado tem um limite: esse valor não pode ser zero. No tema seguinte, vais aprender a fazer a conta só quando o divisor não é zero.

## Funções predefinidas

Há cálculos que aparecem em quase todos os programas: a distância entre dois números, o maior de dois valores, um arredondamento. Escrevê-los à mão de cada vez seria perder tempo, e cada pessoa escrevia-os à sua maneira. Por isso, o Python traz-nos já feitos.

### O que é uma função predefinida

Já usaste duas funções do Python: o `print`, no tema anterior, e o `type`, neste guia. Nas duas, escreves o nome e, entre parênteses, os valores que lhe dás. Fazes o mesmo com todas as funções que vais conhecer.

Uma **função predefinida** é uma função que já vem com o Python, pronta a usar. Usá-la chama-se **chamar** a função. Os valores que lhe dás, entre parênteses, chamam-se **argumentos**. A função faz o seu trabalho e devolve um resultado, o **valor devolvido**.

É como as funções que escreveste na algoritmia, com `Função` e `devolver`, só que foi outra pessoa a escrevê-las. Não precisas de saber como estão feitas por dentro. Chega-te saber o que recebem e o que devolvem. Também não precisas de saber como funciona uma máquina de venda automática para tirar uma garrafa de água.

O valor devolvido pode ser guardado numa variável, usado numa conta ou escrito com o `print`. Pensa na chamada como um buraco na linha onde está escrita, como na algoritmia. O Python vai à função buscar o valor, volta, e tapa o buraco com ele. Só depois continua a executar a linha.

### `abs`, a distância a zero

O **valor absoluto** de um número é a distância desse número a zero, ou seja, o número sem sinal. A função `abs` recebe um número e devolve o seu valor absoluto: `abs(-7)` dá `7`, e `abs(7)` também. Serve sempre que interessa o tamanho de uma diferença, e não o seu sentido.

O João tem 12 anos e a irmã tem 15. A diferença de idades é 3 anos, seja qual for a ordem da conta. `12 - 15` dá `-3`, mas uma diferença de idades de -3 anos não quer dizer nada. Antes de correres este exemplo, tenta prever a linha que aparece.

```python
# idades.py: a diferença de idades entre dois irmãos, sem sinal.
idade_joao = 12
idade_irma = 15
diferenca = abs(idade_joao - idade_irma)
print("Diferença de idades:", diferenca, "anos")
```

O resultado é este:

```text
Diferença de idades: 3 anos
```

Leitura guiada: na linha 4, primeiro calcula-se o que está dentro dos parênteses, `12 - 15`, que dá `-3`. Depois chama-se a função com esse valor, e `abs(-3)` devolve `3`. O 3 fica em `diferenca`, e a última linha escreve-o. Se trocasses a ordem da conta, `abs(idade_irma - idade_joao)`, o resultado era o mesmo: `abs(3)` também devolve `3`.

### `max` e `min`, o maior e o menor

Na algoritmia escreveste uma função `maior(a, b)`, que devolvia o maior de dois valores. O Python traz uma já feita, o `max`, que aceita dois ou mais valores. O `min` faz o contrário e devolve o menor.

Antes de leres as respostas, tenta prever cada linha.

```text
>>> max(12, 30)
30
>>> min(12, 30)
12
>>> max(8, 21, 15)
21
>>> min(8, 21, 15)
8
```

Leitura guiada: os argumentos separam-se por vírgulas, e a ordem deles não muda a resposta. Com três valores, o `max` compara-os todos e devolve o maior, e o `min` devolve o menor.

### `round`, o arredondamento

O `round` arredonda um número. Tem duas formas, e a diferença está no número de argumentos.

Com um só argumento, arredonda às unidades e devolve um `int`. Com um segundo argumento, esse número diz quantas casas decimais ficam, e o resultado é um `float`. Antes de leres as respostas, tenta prever cada linha.

```text
>>> round(7.6)
8
>>> round(7.4)
7
>>> round(3.14159, 2)
3.14
>>> round(7.6, 1)
7.6
>>> type(round(7.6))
<class 'int'>
>>> type(round(7.6, 1))
<class 'float'>
```

Leitura guiada: `round(7.6)` vai para o inteiro mais próximo, 8, e `round(7.4)` vai para 7. Em `round(3.14159, 2)`, o 2 diz que ficam duas casas decimais. A linha `type(round(7.6))` tem uma chamada dentro de outra, e lê-se de dentro para fora. Primeiro, `round(7.6)` devolve 8. Depois, `type(8)` devolve o tipo desse 8.

Há um pormenor que surpreende. Quando o número está exatamente a meio entre dois inteiros, como 2.5, o `round` escolhe o inteiro par. Por isso, `round(2.5)` dá `2`, e `round(3.5)` dá `4`. Os números que não estão exatamente a meio arredondam como na escola.

O `round` serve sobretudo para mostrar um resultado com as casas decimais que fazem sentido. Uma média de pontos com dezasseis casas decimais, como `1.6666666666666667`, não ajuda ninguém. Com `round(..., 2)`, fica `1.67`.

### O `print` não devolve nada

O `print` é uma função diferente das outras desta secção. O trabalho dele é escrever no ecrã, e não calcular um resultado. Então, o que devolve? Antes de leres, tenta prever o que aparece.

```text
>>> resultado = print("Olá")
Olá
>>> print(resultado)
None
```

Leitura guiada: na primeira linha, o `print` escreve "Olá" no ecrã, e o que ele devolve fica em `resultado`. A segunda linha mostra o que ficou guardado: `None`, o valor que quer dizer "nenhum valor". O `print` escreve, mas não devolve nada que sirva.

É a diferença que conheces da algoritmia entre `Escreve:` e `devolver`. Uma função como o `abs` devolve um valor, que podes guardar e usar numa conta. O `print` só mostra.

Nas secções seguintes aparecem mais três funções predefinidas, `int`, `float` e `str`, que convertem valores de um tipo noutro.

## Ler do teclado com `input`

Os programas que viste até aqui dão sempre o mesmo resultado, porque os valores estão escritos dentro deles. Para o `cartas.py` repartir as cartas por 4 jogadores, era preciso mudar a linha 4 e correr outra vez. Um programa útil pergunta os valores a quem o usa.

No pseudocódigo, uma leitura levava duas linhas: um `Escreve:` com a pergunta e um `ler valor`. No Python, as duas juntam-se numa só, com a função `input`. O `input` escreve a pergunta, espera que a pessoa escreva alguma coisa e carregue em Enter, e devolve o que ela escreveu.

| Pseudocódigo | Python |
| --- | --- |
| `Escreve: "Como te chamas?"` e `string nome = ler valor` | `nome = input("Como te chamas? ")` |

O espaço depois do ponto de interrogação, dentro das aspas, separa a pergunta da resposta. Aqui o `print` não ajuda, e o espaço tem de ser teu. Sem ele, o que a pessoa escreve fica colado à pergunta.

Há uma regra que é a fonte do erro mais frequente deste tema: o `input` devolve sempre um texto, um `str`. Mesmo que a pessoa escreva `14`, o que chega ao programa é o texto `"14"`, com dois algarismos, e não o número catorze.

Antes de leres as respostas, tenta prever o que a consola mostra a seguir a `idade` e a seguir a `type(idade)`.

```text
>>> nome = input("Como te chamas? ")
Como te chamas? Rita
>>> nome
'Rita'
>>> idade = input("Que idade tens? ")
Que idade tens? 14
>>> idade
'14'
>>> type(idade)
<class 'str'>
```

Leitura guiada: na primeira linha, o `input` escreve a pergunta e fica à espera. A pessoa escreve `Rita` e carrega em Enter, e o texto fica em `nome`. Na consola, escrever só o nome de uma variável mostra o valor dela. Os textos aparecem entre aspas simples, para se ver que são textos. Por isso, `'14'` aparece com aspas: é um texto. O `type` confirma: `str`.

Quando um programa chega a um `input`, para e espera. No terminal vês a pergunta e o cursor a piscar à frente dela. O programa não está avariado: está à tua espera. Escreve a resposta e carrega em Enter.

## Converter o texto lido num número: `int` e `float`

Um texto não serve para fazer contas. Antes de correres este programa, tenta prever o que acontece se a pessoa escrever 14.

```python
# proximo_ano.py: lê a idade e diz quantos anos a pessoa faz no próximo ano.
idade = input("Que idade tens? ")
print("No próximo ano fazes", idade + 1, "anos")
```

O programa faz a pergunta, lê o 14 e para na linha 3:

```text
Que idade tens? 14
Traceback (most recent call last):
  File "C:\Users\aluno\Documents\fp-python\proximo_ano.py", line 3, in <module>
    print("No próximo ano fazes", idade + 1, "anos")
                                  ~~~~~~^~~
TypeError: can only concatenate str (not "int") to str
```

O 14 a seguir à pergunta é o que a pessoa escreveu. No terminal, a resposta aparece na mesma linha da pergunta.

Leitura guiada: lê a mensagem de baixo para cima. A última linha quer dizer "erro de tipo: só se consegue juntar um texto a outro texto, e não um `int`". A palavra inglesa *concatenate* quer dizer juntar, pôr um a seguir ao outro. As linhas de cima dizem onde: na linha 3, e os sinais apontam para `idade + 1`.

O que aconteceu foi isto. `idade` guarda o texto `"14"`. Entre dois textos, o `+` não soma: junta-os. Entre um texto e um número, o Python não sabe se deve juntar ou somar, e para. Repara também que a mensagem aponta a linha 3, mas a causa está na linha 2, na leitura que ficou como texto.

A correção é **converter** o texto num número, logo na leitura. Converter é transformar um valor de um tipo noutro, e faz-se com a função que tem o nome do tipo. Para um número inteiro, é o `int`:

```python
# proximo_ano.py: lê a idade e diz quantos anos a pessoa faz no próximo ano.
# O int converte o texto escrito no teclado num número inteiro.
idade = int(input("Que idade tens? "))
print("No próximo ano fazes", idade + 1, "anos")
```

Antes de correres, prevê o que aparece com o 14. O resultado é este:

```text
Que idade tens? 14
No próximo ano fazes 15 anos
```

Leitura guiada: a linha 3 tem uma chamada dentro de outra, e lê-se de dentro para fora. Primeiro, o `input` faz a pergunta e devolve o texto `"14"`. Depois, o `int` recebe esse texto e devolve o número 14. Só então o 14 fica guardado em `idade`. Na linha 4, `idade + 1` já é uma soma de dois números, e dá 15.

Cada `int quantidade = ler valor` do pseudocódigo passa a `quantidade = int(input("pergunta "))`. O tipo que estava à frente da variável, no pseudocódigo, reaparece no Python como a função que converte.

Para um número com parte decimal, usa-se o `float` em vez do `int`. Antes de correres este programa, prevê o que aparece se a pessoa escrever 14.5, e depois se escrever 14.

```python
# nota.py: lê a nota de um teste, que pode ter décimas, e diz quanto falta para o 20.
NOTA_MAXIMA = 20

nota = float(input("Nota do teste? "))
print("Faltam", NOTA_MAXIMA - nota, "valores para o", NOTA_MAXIMA)
```

Com 14.5:

```text
Nota do teste? 14.5
Faltam 5.5 valores para o 20
```

Com 14:

```text
Nota do teste? 14
Faltam 6.0 valores para o 20
```

Leitura guiada: o `float` aceita um texto com ponto, como `"14.5"`, e também um texto sem parte decimal, como `"14"`. Nos dois casos devolve um `float`. Por isso, com 14 aparece `6.0`: a conta é entre um `int` e um `float`, e o resultado é `float`. Escolhe o `float` quando o valor pode ter parte decimal, e o `int` quando não pode, como numa idade ou num número de jogadores.

O `int` tem um segundo trabalho. Além de converter um texto, converte também um `float` num inteiro. Mas não arredonda: corta a parte decimal. Antes de leres as respostas, compara-o com o `round`.

```text
>>> int(7.9)
7
>>> round(7.9)
8
```

Leitura guiada: `int(7.9)` deita fora o `.9` e dá 7, e `round(7.9)` vai para o inteiro mais próximo, 8. Quando quiseres arredondar, usa o `round`. O `int` serve quando queres mesmo só a parte inteira.

## Quando a conversão não é possível

E se a pessoa escrever `catorze`, em vez de `14`? O `int` não consegue converter esse texto num número. Com o `proximo_ano.py` corrigido, aparece isto:

```text
Que idade tens? catorze
Traceback (most recent call last):
  File "C:\Users\aluno\Documents\fp-python\proximo_ano.py", line 3, in <module>
    idade = int(input("Que idade tens? "))
ValueError: invalid literal for int() with base 10: 'catorze'
```

Quer dizer "erro de valor: escrita inválida para um `int` na base 10". A base 10 é a numeração que usamos todos os dias, com os algarismos de 0 a 9. No fim da mensagem aparece, entre aspas, o texto que o `int` não conseguiu converter.

O mesmo erro aparece noutros casos, e convém reconhecê-los. Antes de leres, tenta prever quais destas conversões funcionam.

```text
>>> int("2.5")
Traceback (most recent call last):
  File "<python-input-0>", line 1, in <module>
    int("2.5")
    ~~~^^^^^^^
ValueError: invalid literal for int() with base 10: '2.5'
>>> float("2,5")
Traceback (most recent call last):
  File "<python-input-1>", line 1, in <module>
    float("2,5")
    ~~~~~^^^^^^^
ValueError: could not convert string to float: '2,5'
```

Leitura guiada: nenhuma das duas funciona. O `int` recusa `"2.5"`, porque 2.5 não é um número inteiro. O `float` recusa `"2,5"`, por causa da vírgula, e a mensagem diz "não foi possível converter o texto num `float`". Quem usa o programa tem de escrever os números com ponto, como no código.

Há um terceiro caso que acontece por distração. Se a pessoa carregar em Enter sem escrever nada, o `input` devolve o texto vazio, `""`. O `int` também não o consegue converter, e a mensagem acaba com `''`, duas aspas sem nada no meio.

Distingue este erro do da secção anterior pela última linha. O `TypeError` diz que a conversão faltou: o programa tentou fazer contas com um texto. O `ValueError` diz que a conversão estava lá, mas o texto escrito não era um número.

Os programas deste tema ainda não conseguem evitar o `ValueError`. Confiam que a pessoa escreve um número, no formato certo. Quando testares um programa teu, escreve números, e com ponto.

## Juntar textos com `+` e `str`

Já viste que o `+` entre dois textos não soma: junta-os, um a seguir ao outro. `"12" + "3"` dá `"123"`. É isso que, às vezes, se quer.

Pensa numa mensagem que tem de ficar exatamente assim: "Passaste ao nível 3!", sem espaço antes do ponto de exclamação. Com as vírgulas, o `print` põe sempre um espaço entre os valores, e o espaço aparece onde não devia. Para colar um número a um texto, converte-se o número num texto, com a função `str`, e junta-se tudo com `+`.

Antes de correres este exemplo, tenta prever as duas linhas.

```python
# nivel.py: a mensagem do nível, primeiro com vírgulas e depois com + e str.
nivel = 3
print("Passaste ao nível", nivel, "!")
print("Passaste ao nível " + str(nivel) + "!")
```

O resultado é este:

```text
Passaste ao nível 3 !
Passaste ao nível 3!
```

Leitura guiada: na linha 3, o `print` recebe três valores, separados por vírgulas, e põe um espaço entre cada dois, também antes do `!`. Na linha 4, o `print` recebe um só valor, um texto construído com `+`. Primeiro, `str(nivel)` devolve o texto `"3"`. Depois, os três textos juntam-se, sem nada no meio: `"Passaste ao nível "`, `"3"` e `"!"`. Com o `+`, os espaços são todos teus, e por isso o primeiro texto acaba com um espaço dentro das aspas.

Sem o `str`, a linha 4 fica `"Passaste ao nível " + nivel + "!"`, e o programa para:

```text
TypeError: can only concatenate str (not "int") to str
```

É a mesma mensagem do `proximo_ano.py`, e a causa é parecida: um `+` entre um texto e um número. A correção é que muda, conforme o que querias. No `proximo_ano.py` querias somar, e convertias o texto em número, com `int`. Aqui queres juntar, e convertes o número em texto, com `str`.

Usa as vírgulas na maior parte das mensagens, porque são mais simples. Usa o `+` e o `str` quando a mensagem tem de ficar exatamente igual a um enunciado.

Com o `str`, já conheces todas as funções predefinidas deste guia. A tabela junta-as, para consultares depressa.

| Função | O que devolve | Exemplo | Resultado |
| --- | --- | --- | ---: |
| `abs(x)` | a distância de `x` a zero | `abs(4 - 9)` | `5` |
| `max(a, b)` | o maior dos valores | `max(12, 30)` | `30` |
| `min(a, b)` | o menor dos valores | `min(12, 30)` | `12` |
| `round(x)` | `x` arredondado às unidades | `round(7.6)` | `8` |
| `round(x, n)` | `x` arredondado a `n` casas decimais | `round(3.14159, 2)` | `3.14` |
| `type(x)` | o tipo de `x` | `type(2.5)` | `<class 'float'>` |
| `int(x)` | `x` convertido num inteiro | `int("12")` | `12` |
| `float(x)` | `x` convertido num número com parte decimal | `float("2.5")` | `2.5` |
| `str(x)` | `x` convertido num texto | `str(12)` | `'12'` |

## O Python 2 na leitura e na divisão

No tema anterior viste que há código antigo, escrito para o Python 2, que não corre no Python 3. O sinal mais fácil de reconhecer era o `print` sem parênteses. Há mais dois sinais, e são deste tema.

| No Python 2 | No Python 3 |
| --- | --- |
| `raw_input("Nome? ")` para ler um texto | `input("Nome? ")` |
| `7 / 2` dava `3`, uma divisão inteira | `7 / 2` dá `3.5`; a divisão inteira é `7 // 2` |

O `raw_input`, no Python 3, dá um erro de nome, porque a função deixou de existir:

```text
NameError: name 'raw_input' is not defined
```

Quer dizer "erro de nome: o nome 'raw_input' não está definido". Corrige-se trocando-o por `input`.

A divisão é o sinal mais perigoso dos dois. Não dá erro nenhum. No Python 2, uma divisão entre dois inteiros com `/` deitava fora a parte decimal, e `7 / 2` dava 3. No Python 3, o mesmo código dá 3.5. Um programa antigo que dividia com `/` pode passar a dar outro resultado sem nenhum aviso. Quando encontrares um `/` em código antigo, pergunta-te se o autor queria a divisão com parte decimal ou a divisão inteira.

## Exemplo guiado: converter minutos em horas e minutos, em Python

### Passo 1: o problema

Este problema vem do exemplo guiado do guia 02 da algoritmia, onde está resolvido em pseudocódigo:

> Um treinador regista o tempo de treino de cada atleta em minutos, mas os atletas preferem ver esse tempo em horas e minutos. Escreve um algoritmo que leia um número de minutos e mostre quantas horas completas e quantos minutos restantes correspondem a esse tempo. Por exemplo, 135 minutos são 2 horas e 15 minutos.

O objetivo agora é traduzir esse algoritmo para Python, linha a linha. Depois, confirmas no computador os mesmos casos de teste que lá se calcularam à mão.

### Passo 2: os casos de teste, calculados à mão

Os casos de teste fazem-se antes do programa, a partir do enunciado, e não a partir do código. Se fossem tirados do código, concordavam sempre com ele, mesmo que ele estivesse errado. São os quatro casos do guia 02:

| Minutos | Horas | Minutos restantes | Porque é que este caso foi escolhido |
| ---: | ---: | ---: | --- |
| 135 | 2 | 15 | O caso do enunciado, um caso normal |
| 0 | 0 | 0 | O valor mais pequeno permitido |
| 59 | 0 | 59 | O maior valor que ainda não chega a uma hora |
| 60 | 1 | 0 | O primeiro valor que completa uma hora |

O 59 e o 60 ficam dos dois lados do sítio onde a resposta muda, a fronteira. Com 59 ainda não há nenhuma hora completa, e com 60 já há uma. Se o programa tiver um erro nessa passagem, estes dois casos apanham-no. O 0 confirma que o programa se porta bem quando não há nada para converter.

### Passo 3: o pseudocódigo

Este é o algoritmo do guia 02, na forma das aulas:

```text
const MINUTOS_POR_HORA = 60
Escreve: "Quantos minutos?"
int totalMinutos = ler valor
int horas = totalMinutos div MINUTOS_POR_HORA
int minutos = totalMinutos resto MINUTOS_POR_HORA
Escreve: horas, " h e ", minutos, " min"
```

É uma sequência: seis linhas, todas encostadas à margem, cada uma executada uma vez. Não há nenhuma instrução que o Python deste guia não saiba fazer.

### Passo 4: traduzir linha a linha

Cada linha do pseudocódigo tem uma tradução, com o que aprendeste nas secções deste guia:

| Pseudocódigo | Python | O que muda |
| --- | --- | --- |
| `const MINUTOS_POR_HORA = 60` | `MINUTOS_POR_HORA = 60` | sem `const`; o nome em maiúsculas basta |
| `Escreve: "Quantos minutos?"` e `int totalMinutos = ler valor` | `total_minutos = int(input("Quantos minutos? "))` | as duas linhas juntam-se; o tipo passa a ser a conversão; o nome leva traço baixo |
| `int horas = totalMinutos div MINUTOS_POR_HORA` | `horas = total_minutos // MINUTOS_POR_HORA` | sem o tipo; o `div` passa a `//` |
| `int minutos = totalMinutos resto MINUTOS_POR_HORA` | `minutos = total_minutos % MINUTOS_POR_HORA` | sem o tipo; o `resto` passa a `%` |
| `Escreve: horas, " h e ", minutos, " min"` | `print(horas, "h e", minutos, "min")` | os espaços saem de dentro das aspas, porque o `print` os põe |

Há duas decisões nesta tradução que merecem atenção.

A primeira é a conversão. O pseudocódigo dizia `int totalMinutos`, e o `int` dizia que se esperava um número inteiro. No Python, sem o `int(...)` à volta do `input`, `total_minutos` ficava um texto. A linha das horas parava com um `TypeError`, porque o `//` não divide um texto.

A segunda é o `//`. Com `/`, o caso de 135 minutos dava `2.25` horas. É tentador ler isso como "2 horas e 25 minutos", e está errado. 2.25 horas são 2 horas e um quarto de hora, ou seja, 15 minutos. As horas completas não têm parte decimal, e por isso a conta certa é o `//`.

### Passo 5: o script completo

```python
# minutos.py: converte um tempo de treino em minutos para horas e minutos.
MINUTOS_POR_HORA = 60

total_minutos = int(input("Quantos minutos? "))
# O // dá as horas completas, e o % dá os minutos que sobram depois delas.
horas = total_minutos // MINUTOS_POR_HORA
minutos = total_minutos % MINUTOS_POR_HORA
print(horas, "h e", minutos, "min")
```

Leitura guiada: a constante vem primeiro, antes das contas que a usam. A linha 4 lê-se de dentro para fora. Primeiro a pergunta, depois o texto escrito, a seguir a conversão em inteiro e, por fim, a variável que nasce com ele. As linhas 6 e 7 usam as duas o mesmo valor de `total_minutos`, que não muda, porque usar uma variável numa conta não a altera. O `print` da linha 8 escreve as horas, o texto "h e", os minutos e o texto "min", com um espaço entre cada dois.

Antes de correres, prevê o que aparece com 135.

### Passo 6: correr os casos de teste

Guarda o ficheiro e corre-o quatro vezes, uma por caso. Com 135, o ecrã fica assim:

```text
Quantos minutos? 135
2 h e 15 min
```

Com 60:

```text
Quantos minutos? 60
1 h e 0 min
```

Os outros dois casos dão `0 h e 0 min` e `0 h e 59 min`. A tabela compara o que se calculou à mão com o que o programa mostrou:

| Minutos | Esperado, calculado à mão | Obtido no computador | Coincide? |
| ---: | --- | --- | --- |
| 135 | 2 horas e 15 minutos | `2 h e 15 min` | sim |
| 0 | 0 horas e 0 minutos | `0 h e 0 min` | sim |
| 59 | 0 horas e 59 minutos | `0 h e 59 min` | sim |
| 60 | 1 hora e 0 minutos | `1 h e 0 min` | sim |

Os quatro casos coincidem, e o programa faz o mesmo que o algoritmo. Se algum caso não coincidisse, seguias a rotina de cinco passos. Escrevias o caso, o esperado e o obtido, e procuravas a primeira linha onde um valor ficou diferente do que devia.

### Passo 7: o que o programa ainda não faz

O problema só faz sentido com um número inteiro de minutos, igual ou maior do que zero, porque é um tempo de treino. O programa confia nisso, e é bom saber o que acontece quando alguém não cumpre. Com -30, o programa não dá erro e mostra `-1 h e 30 min`, um resultado sem sentido. Com `doze`, para com um `ValueError` na linha 4.

Os dois casos ficam fora do problema, como na algoritmia. Para recusar um valor negativo, o programa tem de decidir, e é isso que vais aprender no tema seguinte.

## Erros frequentes

Os erros desta secção não ficaram nas secções anteriores. Para cada um, ficas a saber o que aparece, porque acontece e como se corrige. Os outros estão na secção da ideia que explicam:

- o texto e a variável trocados no `print`, em "Guardar um valor numa variável";
- a variável usada antes de nascer, em "Atribuir outra vez: o valor antigo perde-se";
- o nome com um espaço, em "Os nomes das variáveis";
- o `true` em minúsculas, em "Os tipos dos valores";
- o `/` no lugar do `//`, em "A divisão inteira e o resto: `//` e `%`";
- a média sem parênteses, em "A ordem das contas";
- a divisão por zero, em "A divisão por zero";
- a conversão esquecida, em "Converter o texto lido num número: `int` e `float`";
- o texto que não é um número, em "Quando a conversão não é possível";
- o número juntado a um texto sem `str`, em "Juntar textos com `+` e `str`".

### Um nome mal escrito

O que se vê, no `moedas.py` com a linha 5 escrita `print("Depois do baú:", moeda)`, sem o `s`:

```text
No início: 40
Traceback (most recent call last):
  File "C:\Users\aluno\Documents\fp-python\moedas.py", line 5, in <module>
    print("Depois do baú:", moeda)
                            ^^^^^
NameError: name 'moeda' is not defined. Did you mean: 'moedas'?
```

Quer dizer "erro de nome: o nome 'moeda' não está definido. Querias dizer 'moedas'?". Acontece com um nome escrito de outra maneira da linha onde nasceu: uma letra a menos, uma maiúscula trocada, um acento a mais. Para o Python, `moeda` é outra variável, que nunca nasceu. Repara que a primeira linha do ecrã apareceu, porque as linhas antes do erro correram. Corrige-se escrevendo o nome exatamente igual ao da linha onde ele nasceu. A sugestão do fim da mensagem costuma acertar.

### O tipo à frente, copiado do pseudocódigo

O que se vê, com a linha `int total = 0` num programa:

```text
  File "C:\Users\aluno\Documents\fp-python\total.py", line 2
    int total = 0
        ^^^^^
SyntaxError: invalid syntax
```

Quer dizer "erro de sintaxe: escrita inválida". Acontece a quem traduz o pseudocódigo à letra. O Python lê `int` como a função que converte, e não percebe o que faz ali o nome `total`, logo a seguir. O programa nem começa a correr. Corrige-se tirando o tipo: `total = 0`. O mesmo acontece com o `const` à frente de uma constante.

### O número escrito com vírgula, dentro do programa

O que se vê, com este programa:

```python
# bilhete.py: o preço de um bilhete, escrito com vírgula em vez de ponto.
preco = 2,5
print("Preço:", preco)
```

O resultado:

```text
Preço: (2, 5)
```

O programa não dá erro nenhum, e o que aparece não é um número. Acontece porque, no Python, a vírgula separa valores. Na linha 2, a vírgula juntou os dois números, o 2 e o 5, num par, e é esse par que fica em `preco`. Os parênteses mostram o par. Os pares são do tema 08. Por agora, basta reconhecê-los como o sinal de uma vírgula no sítio de um ponto. É um erro de lógica, e só o apanhas se olhares para o resultado. Corrige-se escrevendo o número com ponto: `preco = 2.5`.

### A pergunta colada à resposta

O que se vê, com `nome = input("Como te chamas?")`, sem espaço no fim:

```text
Como te chamas?Rita
```

O programa funciona, mas a resposta fica colada à pergunta. Acontece porque o `input` escreve a pergunta tal e qual, e o cursor fica logo a seguir ao último carácter. Corrige-se com um espaço antes de fechar as aspas: `input("Como te chamas? ")`.

## Palavras novas deste guia

- Variável: um espaço com um nome, onde se guarda um valor que pode mudar; nasce na primeira linha que lhe dá um valor.
- Atribuição: a instrução com `=`, que calcula o lado direito e guarda o resultado na variável da esquerda.
- Convenção: uma forma combinada entre as pessoas, que a linguagem não obriga a cumprir, como os nomes com traço baixo.
- Palavras reservadas: as palavras que pertencem à linguagem e não podem ser nomes, como `True`, `False` e `None`.
- Constante: em Python, uma variável com o nome todo em maiúsculas, que se combina não mudar.
- Tipagem dinâmica: o Python descobre o tipo de cada valor enquanto o programa corre, sem o escreveres.
- `int`: o tipo dos números inteiros.
- `float`: o tipo dos números com parte decimal, escrita com ponto.
- `str`: o tipo dos textos, a abreviatura de string.
- `bool`: o tipo que só tem dois valores, `True` e `False`, com maiúscula.
- `None`: o valor que quer dizer "nenhum valor"; é o que o `print` devolve.
- `type`: a função que devolve o tipo de um valor.
- Operador: o sinal que diz que conta se faz, como `+` ou `//`.
- `//`: a divisão inteira, o `div` do pseudocódigo.
- `%`: o resto da divisão inteira, o `resto` do pseudocódigo.
- `**`: a potência.
- Função predefinida: uma função que já vem com o Python, pronta a usar, como `abs` ou `round`.
- Chamar uma função: usá-la, escrevendo o nome e os argumentos entre parênteses.
- Argumento: um valor que se dá a uma função, entre parênteses, na chamada.
- Valor devolvido: o resultado que a função entrega à linha que a chamou.
- Valor absoluto: a distância de um número a zero, que a função `abs` devolve.
- `max` e `min`: as funções que devolvem o maior e o menor dos valores que recebem.
- `round`: a função que arredonda um número, às unidades ou a um número de casas decimais.
- `input`: a função que escreve uma pergunta, lê o que a pessoa escreve e o devolve, sempre como texto.
- Converter: transformar um valor de um tipo noutro, como o texto `"14"` no número 14, com `int`, `float` ou `str`.
- Texto vazio: o texto sem nenhum carácter, `""`.
- `NameError`: o erro de um nome que não existe, como uma variável mal escrita ou usada antes de nascer.
- `TypeError`: o erro de uma operação com tipos que não combinam, como um texto mais um número.
- `ValueError`: o erro de uma conversão impossível, como `int("doze")`.
- `ZeroDivisionError`: o erro de uma divisão por zero.
- `raw_input`: a função de leitura do Python 2, que no Python 3 se chama `input`.

## Verificar o que aprendeste

Usa estas perguntas para te testares. Responde a cada uma sem olhar para o guia. Se não conseguires, volta à secção que explica a ideia.

1. Com `pontos = 8`, o que escreve `print("pontos")`? E `print(pontos)`?
2. Depois de `vidas = 3`, `vidas = vidas - 1` e `vidas = vidas + 2`, quanto vale `vidas`? Faz a tabela de trace.
3. Traduz para Python: `int totalGolos = 0`, `const MAXIMO_JOGADORES = 6` e `float alturaMedia = 1.65`.
4. Quais destes nomes o Python recusa, e porquê: `golos_2`, `2golos`, `golos marcados`? Qual destes dois segue a forma das aulas: `golosMarcados` ou `golos_marcados`?
5. De que tipo é cada um destes valores: `12`, `12.0`, `"12"`, `False`, `None`?
6. Quanto dá cada conta, e de que tipo é o resultado: `30 / 6`, `30 // 7`, `30 % 7`, `2 ** 4`?
7. Quanto dá `10 + 6 / 2`? E `(10 + 6) / 2`? Explica a diferença.
8. O que devolve cada chamada: `abs(3 - 10)`, `max(4, 9, 2)`, `min(4, 9, 2)`, `round(4.678, 1)`, `int(4.9)` e `round(4.9)`?
9. Porque é que `idade = input("Idade? ")`, seguido de `idade + 1`, dá erro? Como se corrige? E que erro aparece, depois de corrigido, se a pessoa escrever `quinze`?
10. Queres ler o preço de um bilhete, como 2.5. Que função usas para converter, e porque é que o `int` não serve?
11. Com `nivel = 7`, como escreves a mensagem `Nível 7!`, sem espaço antes do ponto de exclamação?
12. Num programa antigo, encontraste `nome = raw_input("Nome? ")` e uma conta `7 / 2`. Que versão do Python é? O que mudas para o Python 3, e quanto dava a divisão no Python antigo?
13. Diz que tipo de erro é cada um. Primeiro, o programa para a meio com `ZeroDivisionError`. Depois, o programa acaba e mostra uma média de 22.5 em testes de 0 a 20. Por fim, o programa nem arranca e mostra `SyntaxError`.

## O que vem a seguir

Para praticar este tema, faz o [laboratório](laboratorios/02-dados-e-interacao-laboratorio.md). Nele constróis, fase a fase, um programa que lê os resultados de uma equipa no torneio de futebol da escola. O programa mostra o resumo da equipa, com os pontos, os pontos por jogo e a percentagem de vitórias. Depois faz a [ficha de exercícios](exercicios/02-dados-e-interacao-exercicios.md). Tem previsões na consola, uma tabela de trace, scripts curtos de leitura e contas, e um script com erros para encontrar.

O tema seguinte é [Seleção](03-selecao.md). Os programas deste guia fazem sempre as mesmas contas, por mais estranha que seja a entrada. Com -30 minutos, o `minutos.py` mostra um resultado sem sentido, e com zero jogadores o `cartas.py` para com um erro. No tema seguinte, o programa passa a decidir. Com `if`, `elif` e `else`, o `Se`, o `Senão se` e o `Senão` do pseudocódigo, faz coisas diferentes consoante os dados.

## Para saber mais

- [Funções predefinidas do Python](https://docs.python.org/3/library/functions.html): a lista completa das funções que vêm com o Python, com o que cada uma recebe e devolve. Está em inglês.
- [O tutorial do Python: o Python como calculadora](https://docs.python.org/3/tutorial/introduction.html): os números, as contas e os textos, explicados com exemplos na consola. Está em inglês.

![Rodapé](../imagens/rodape.png)
