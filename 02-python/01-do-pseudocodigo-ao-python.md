![Cabeçalho](../imagens/cabecalho.png)

# Do pseudocódigo ao Python

Módulo Criar aplicações em linguagem de programação Python. Neste guia passas para Python os algoritmos que já sabes escrever em pseudocódigo, e pões o computador a executá-los. Para praticar, há o [laboratório](01-do-pseudocodigo-ao-python-laboratorio.md) e a [ficha de exercícios](01-do-pseudocodigo-ao-python-exercicios.md) deste tema.

Na algoritmia, quem executava os algoritmos eras tu, linha a linha, numa tabela de trace. A partir de agora é o computador. O pseudocódigo das aulas foi pensado para passar para Python quase linha a linha, e por isso vais reconhecer quase tudo. O que muda é a forma de escrever. E o computador não aceita nada que não esteja escrito exatamente como a linguagem manda. Este tema ainda não trata os textos e as listas a fundo, nem a leitura e a escrita de ficheiros de dados. Isso fica para os temas seguintes.

Lê-se ao teu ritmo, em várias vezes, com o computador ao lado. Cada exemplo pode ser copiado para um ficheiro e corrido, e é assim que se aprende mais.

## Neste guia

1. O que vais aprender
2. O que já sabes e vais usar
3. Um programa é um algoritmo que o computador executa
4. Correr um script
5. Escrever no ecrã com `print`
6. Variáveis sem tipo à frente
7. Os tipos dos valores
8. Contas e divisões
9. Funções predefinidas
10. Ler do teclado com `input`, e converter
11. Decidir com `if`, `elif` e `else`
12. Escolher entre valores certos com `match`
13. Repetir com `while`
14. Contar voltas com `for` e `range`
15. Percorrer uma lista com `for`
16. Parar e continuar: `break` e `continue`
17. Funções com `def` e `return`
18. Os três tipos de erro
19. O Python 3 e o código antigo
20. Exemplo guiado: o resumo das notas de um teste, em Python
21. Erros frequentes
22. Palavras novas deste guia
23. Verificar o que aprendeste
24. O que vem a seguir

## O que vais aprender

No fim deste guia, consegues:

- escrever um script em Python no VS Code e corrê-lo no terminal, e experimentar uma linha na consola do Python;
- traduzir para Python as instruções do pseudocódigo das aulas: as variáveis, as contas, a leitura e a escrita, a seleção, os ciclos e as funções;
- dizer de que tipo é um valor, `int`, `float`, `str` ou `bool`, reconhecer o `None` e converter o que se lê do teclado;
- usar as funções predefinidas `abs`, `max`, `min`, `round`, `int`, `float`, `str`, `type` e `len`;
- correr os casos de teste de um algoritmo no computador e comparar o resultado com o que calculaste à mão;
- dizer se um erro é de sintaxe, de execução ou de lógica, e ler a mensagem que o Python mostra;
- reconhecer código escrito para o Python 2 e dizer o que muda no Python 3.

## O que já sabes e vais usar

- A forma do pseudocódigo das aulas e a indentação: guia [02 Estado, sequência e representações](../01-algoritmos/02-estado-sequencia-representacoes.md), secção "A forma de escrever pseudocódigo nas aulas".
- As variáveis, as constantes e os tipos `int`, `float`, `string` e `bool`: guia [02](../01-algoritmos/02-estado-sequencia-representacoes.md), secções "Variáveis", "Constantes" e "Tipos de dados".
- A atribuição, como `total = total + 5`: guia [02](../01-algoritmos/02-estado-sequencia-representacoes.md), secção "Atribuição: dar um valor não é perguntar se é igual".
- As contas com `/`, `div` e `resto`: guia [02](../01-algoritmos/02-estado-sequencia-representacoes.md), secção "Operadores aritméticos".
- `ler valor` e `Escreve:`: guia [02](../01-algoritmos/02-estado-sequencia-representacoes.md), secção "Entrada e saída: `ler valor` e `Escreve:`".
- A tabela de trace: guia [02](../01-algoritmos/02-estado-sequencia-representacoes.md), secção "Tabela de trace".
- As condições e as comparações: guia [03 Decisões e validação](../01-algoritmos/03-decisoes-e-validacao.md), secções "Condições e o tipo `bool`" e "Operadores de comparação".
- Os operadores `e`, `ou` e `não`: guia [03](../01-algoritmos/03-decisoes-e-validacao.md), secção "Operadores lógicos: `e`, `ou` e `não`".
- O `Se`, o `Senão se` e o `Senão`: guia [03](../01-algoritmos/03-decisoes-e-validacao.md), secções "Seleção simples", "Seleção composta" e "Seleção encadeada".
- As fronteiras e os casos de teste, com o resultado esperado calculado à mão: guia [03](../01-algoritmos/03-decisoes-e-validacao.md), secção "Fronteiras e casos de teste".
- O `Enquanto` e a tabela de iterações: guia [04 Repetição e arrays](../01-algoritmos/04-repeticao-e-arrays.md), secção "Enquanto: repetir enquanto a condição for verdadeira".
- As duas formas do `Para`: guia [04](../01-algoritmos/04-repeticao-e-arrays.md), secção "Para: o ciclo contado".
- Os arrays, o índice a partir de 0 e o `Para cada`: guia [04](../01-algoritmos/04-repeticao-e-arrays.md), secção "Arrays".
- O contador, o acumulador e a média calculada só quando há valores: guia [04](../01-algoritmos/04-repeticao-e-arrays.md), secção "Contadores e acumuladores".
- A sentinela e a validação repetida: guia [04](../01-algoritmos/04-repeticao-e-arrays.md), secções "A sentinela: ler até aparecer o valor que diz "acabou"" e "Validação repetida".
- O `Parar`, o `Continuar` e a bandeira: guia [04](../01-algoritmos/04-repeticao-e-arrays.md), secção "Parar e Continuar".
- As funções com parâmetros e `devolver`: guia [05 Funções e modelo integrado](../01-algoritmos/05-funcoes-e-modelo-integrado.md), secções "Escrever uma função" e "`devolver`".
- Os argumentos e o que acontece numa chamada: guia [05](../01-algoritmos/05-funcoes-e-modelo-integrado.md), secção "Chamar uma função".
- A rotina para procurar um erro, em cinco passos: guia [04](../01-algoritmos/04-repeticao-e-arrays.md), secção "Erros frequentes", e o [projeto 1, Duelo de dados](../01-algoritmos/05-projeto-1-duelo-de-dados.md).
- Criar uma pasta e guardar um ficheiro no computador, do dia a dia.

## Um programa é um algoritmo que o computador executa

Na algoritmia, fizeste muitas tabelas de trace à mão. São lentas, e é fácil enganarmo-nos numa conta ou saltar uma linha. Um computador executa milhões de instruções por segundo, sem se cansar e sem saltar linhas. Só tem uma exigência: as instruções têm de estar escritas numa forma que ele perceba.

Essa forma é uma **linguagem de programação**: uma maneira de escrever algoritmos com regras exatas, que o computador consegue executar. Um algoritmo escrito numa linguagem de programação chama-se **programa**. O Python é a linguagem que vais aprender agora.

Pensa numa receita. Escrita num caderno, com "uma pitada de sal", uma pessoa percebe-a. Uma máquina de cozinha só a segue se cada passo vier com a quantidade exata e pela ordem certa. O pseudocódigo é a receita para pessoas. O Python é a receita para a máquina.

Para o computador executar um programa em Python, é preciso outro programa, o **interpretador**. O interpretador lê o teu ficheiro do princípio ao fim e confirma que está bem escrito. Depois executa as instruções, uma a uma, de cima para baixo. Faz o trabalho que tu fazias na tabela de trace. Quando instalas "o Python" num computador, é o interpretador que instalas.

Um ficheiro com instruções em Python chama-se **script**. É um ficheiro de texto, como os outros, com o nome a acabar em `.py`, como `ola.py` ou `campanha.py`.

Há uma diferença grande entre o pseudocódigo e o Python. No pseudocódigo, um algoritmo em frases claras era válido, e uma palavra com maiúscula a mais não mudava nada. O Python não aceita frases, e não adivinha o que quiseste dizer. Se faltar um sinal, o interpretador recusa o programa todo e diz em que linha encontrou o problema. A parte difícil continua a ser a mesma, a lógica. O que se acrescenta é escrever cada linha exatamente como a linguagem manda.

O Python foi criado por Guido van Rossum e publicado pela primeira vez em 1991. Estas são as características que mais vais notar:

- lê-se quase como inglês, e escreve-se com poucas linhas;
- os blocos marcam-se pela indentação, como no pseudocódigo das aulas;
- é gratuito, e corre em Windows, em macOS e em Linux;
- traz consigo uma coleção grande de funções já feitas, a **biblioteca padrão**.

Por isso, usa-se em muitas áreas. Usa-se na análise de dados e na inteligência artificial, e na parte dos sites que corre nos servidores. Usa-se também na ciência, no ensino e para automatizar tarefas repetitivas. Não é a melhor linguagem para tudo. Depois do Python vais aprender C, uma linguagem que deixa controlar o que o Python faz sozinho, como a memória. São ferramentas diferentes, como um alicate e um martelo, e cada uma serve melhor para certos trabalhos.

## Correr um script

Para escrever e correr scripts, precisas de duas coisas no computador: o interpretador de Python e um editor de código. Nas aulas, o editor é o **VS Code**, um programa para escrever código. Numera as linhas, pinta as palavras da linguagem com cores e tem um terminal lá dentro.

O **terminal** é uma janela onde se escrevem comandos para o computador, um por linha, e se carrega em Enter. Um **comando** é uma ordem escrita, como "corre este script". No VS Code, o terminal abre-se no menu Terminal, com a opção New Terminal, isto é, "novo terminal". Abre-se na parte de baixo da janela, já dentro da pasta que tens aberta no VS Code.

Para correr um script, escreve-se no terminal a palavra `python`, um espaço e o nome do ficheiro. Nos computadores da escola, que são Windows, o comando é este:

```bash
python ola.py
```

Se o Windows responder que não conhece o `python`, experimenta `py ola.py`, que faz o mesmo. No macOS e no Linux, o comando é `python3 ola.py`.

Antes de correres este primeiro exemplo, tenta prever: o que aparece no terminal, e por que ordem?

```python
# ola.py: o primeiro script, que escreve duas linhas no ecrã.
print("Olá, Python!")
print("Cada linha executa-se por ordem, de cima para baixo.")
```

O resultado é este:

```text
Olá, Python!
Cada linha executa-se por ordem, de cima para baixo.
```

Leitura guiada: o interpretador começa na primeira linha e desce. A primeira linha começa com `#`, e por isso é um **comentário**: uma nota para quem lê o código, que o Python ignora. A segunda linha escreve o texto que está entre aspas, e a terceira escreve o outro. As aspas não aparecem no ecrã, porque só servem para dizer onde o texto começa e acaba.

Em todos os scripts das aulas, a primeira linha é um comentário com o nome do ficheiro e o que ele faz. Quem abrir o ficheiro uma semana depois percebe logo para que serve.

Há um cuidado que vale para todos os scripts. O interpretador lê o ficheiro que está guardado no disco, e não o que está no ecrã. Se mudares o código e não o guardares, corres a versão antiga. Guarda sempre antes de correr, com Ctrl+S no Windows ou Cmd+S no macOS. No VS Code, um ficheiro por guardar tem uma bola cheia no separador, no lugar do X que o fecha.

### A consola do Python, para experimentar uma linha

Às vezes só queres saber quanto dá uma conta, ou o que faz uma linha. Para isso não precisas de criar um ficheiro. Escreve no terminal só a palavra `python`, sem nome de ficheiro, e carrega em Enter. No macOS, é `python3`. Abre-se a **consola do Python**, que mostra `>>>` e fica à espera de uma linha.

Escreves uma linha, carregas em Enter, e o Python mostra logo o resultado. Por exemplo:

```text
>>> 2 + 3
5
>>> 2 + 3 * 4
14
```

Na consola não precisas de `print`: o Python mostra sozinho o valor de cada linha. O que escreves na consola não fica guardado em lado nenhum. Serve para experimentar, e o programa a sério escreve-se num ficheiro. Para sair, escreve `exit()` e carrega em Enter.

O erro típico é esquecer onde se está. Se escreveres `python ola.py` dentro da consola, a seguir ao `>>>`, aparece `SyntaxError: invalid syntax`, isto é, "erro de sintaxe: escrita inválida". A consola espera uma linha de Python, e `python ola.py` é um comando do terminal. Sai com `exit()` e escreve o comando no terminal.

As mensagens de erro deste guia são as do Python 3.14. Numa versão mais antiga, algumas têm outras palavras, ou apontam a linha seguinte. O tipo de erro, a palavra antes dos dois pontos, é o mesmo.

## Escrever no ecrã com `print`

O `Escreve:` do pseudocódigo passa a `print`, com o que se quer mostrar entre parênteses. Os parênteses estão lá porque o `print` é uma função que vem com o Python: dás-lhe valores entre parênteses, e ela escreve-os no ecrã.

Tal como no pseudocódigo, o que está entre aspas aparece tal e qual, e o que está sem aspas é o nome de uma variável. No Python, um texto pode ir entre aspas duplas, `"Olá"`, ou simples, `'Olá'`. Nas aulas usamos as duplas.

Para mostrar vários valores, separam-se por vírgulas, como no pseudocódigo. Há uma diferença: o `print` põe sozinho um espaço entre cada dois valores. No pseudocódigo eras tu que punhas os espaços dentro das aspas.

Antes de correres este exemplo, tenta prever: o que escreve cada um dos dois `print`?

```python
# horas.py: a mesma frase escrita de duas maneiras, para comparar os espaços.
horas = 2
print("Passaram", horas, "horas")
print("Passaram ", horas, " horas")
```

O resultado é este:

```text
Passaram 2 horas
Passaram  2  horas
```

Leitura guiada: a variável `horas` nasce na segunda linha, com o valor 2. O primeiro `print` recebe três valores, o texto "Passaram", o valor de `horas` e o texto "horas", e escreve-os com um espaço entre cada dois. O segundo `print` recebe os mesmos três valores, mas os textos já trazem espaços dentro das aspas. O `print` acrescenta os seus, e ficam dois espaços seguidos.

É o erro típico de quem traduz o pseudocódigo à letra: copiar os espaços de dentro das aspas. No Python, deixa os espaços de fora e deixa o `print` pô-los.

Um `print()` sem nada lá dentro escreve uma linha em branco. Serve para separar partes do que aparece no ecrã.

## Variáveis sem tipo à frente

No pseudocódigo, uma variável nascia com o tipo à frente: `int total = 0`. No Python, escreve-se só `total = 0`. A variável nasce na mesma, na primeira linha em que lhe dás um valor, mas sem o tipo.

Isto não quer dizer que o Python não tenha tipos. Quer dizer que o tipo está no valor, e não na variável. Quando escreves `total = 0`, o Python vê que 0 é um número inteiro e guarda-o como tal. A esta forma de funcionar chama-se **tipagem dinâmica**: o tipo de cada valor é descoberto pelo Python enquanto o programa corre, sem o escreveres.

Antes de leres a resposta, tenta prever: o que escreve este bocado de código?

```python
pontos = 10
pontos = pontos + 5
print(pontos)
```

Escreve `15`. A atribuição funciona exatamente como no pseudocódigo. Primeiro calcula-se o lado direito com o valor antigo, 10 + 5, e depois o resultado substitui o valor antigo.

Leitura guiada: lê como farias a tabela de trace. Na primeira linha, `pontos` nasce com 10. Na segunda, o lado direito dá 15, e `pontos` passa a valer 15. Na terceira, o `print` escreve o valor de `pontos`.

### As constantes

O Python não tem a palavra `const`. Uma constante escreve-se como uma variável, com o nome todo em maiúsculas: `const SENTINELA = -1` passa a `SENTINELA = -1`. O Python não te impede de mudar o valor de uma constante. O nome em maiúsculas é uma promessa a quem lê: este valor não muda em lado nenhum do programa.

### Os nomes

Os nomes seguem quase as mesmas regras do pseudocódigo. Usam letras, algarismos e o traço baixo, `_`. Não começam por um algarismo, não têm espaços, e nas aulas não levam acentos. O Python distingue maiúsculas de minúsculas, e por isso `total` e `Total` seriam duas variáveis diferentes.

Há uma diferença na forma. No pseudocódigo das aulas, cada palavra a partir da segunda começava com maiúscula: `totalQuilos`. No Python, a convenção é outra. As palavras escrevem-se todas em minúsculas, separadas por um traço baixo: `total_quilos`. As constantes ficam em maiúsculas, com traço baixo entre as palavras, como no pseudocódigo.

| Pseudocódigo | Python |
| --- | --- |
| `int totalQuilos = 0` | `total_quilos = 0` |
| `quilosPorTurma = [12, 0, 9]` | `quilos_por_turma = [12, 0, 9]` |
| `Função contarPositivas(notas)` | `def contar_positivas(notas):` |
| `const NUMERO_DE_TURMAS = 6` | `NUMERO_DE_TURMAS = 6` |

Uma **convenção** é uma regra combinada entre as pessoas, que a linguagem não obriga a cumprir. O Python aceitaria `totalQuilos`. Mas quase todo o código Python que vais ler, na documentação e nos exemplos, usa `total_quilos`, e é essa a forma que usamos nas aulas.

Há palavras que não podem ser nomes, porque já pertencem à linguagem. São, entre outras, `if`, `else`, `while`, `for`, `def`, `return`, `and`, `or`, `not`, `True`, `False` e `None`. São as **palavras reservadas** do Python, que o guia 02 anunciava.

## Os tipos dos valores

Os tipos que conheces do pseudocódigo existem todos no Python, com uma mudança de nome e uma novidade.

| Tipo | O que guarda | Exemplos em Python |
| --- | --- | --- |
| `int` | um número inteiro | `7`, `0`, `-3` |
| `float` | um número com parte decimal, escrita com ponto | `7.0`, `2.5`, `-0.1` |
| `str` | um texto, entre aspas | `"7"`, `"Olá"`, `""` |
| `bool` | só verdadeiro ou falso | `True`, `False` |
| `NoneType` | só o valor `None`, que quer dizer "nenhum valor" | `None` |

O tipo `string` do pseudocódigo escreve-se `str` no Python, uma abreviatura da mesma palavra. Os valores lógicos escrevem-se `True` e `False`, com a primeira letra maiúscula. O `None` é novo. É o valor que quer dizer "aqui não há nada", e vais vê-lo na secção das funções.

Os números com parte decimal escrevem-se com ponto, `2.5`, e nunca com vírgula. A vírgula, no Python, separa valores, como no `print`.

Para saber de que tipo é um valor, há a função `type`. Antes de leres as respostas, tenta prever o tipo de cada um destes valores, escritos na consola do Python:

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

Leitura guiada: o Python responde com `<class '...'>`, e o nome entre as aspas é o tipo. No Python, cada tipo é uma "classe", e é daí que vem a palavra. Por agora, lê `<class 'int'>` como "o tipo é `int`". Repara que `7`, `7.0` e `"7"` são três valores diferentes. O primeiro é um inteiro, o segundo tem parte decimal, e o terceiro é um texto com um algarismo lá dentro.

O erro típico é escrever os valores lógicos como no pseudocódigo, em minúsculas. Com `encontrado = true`, o programa para com esta mensagem:

```text
NameError: name 'true' is not defined. Did you mean: 'True'?
```

Quer dizer "erro de nome: o nome 'true' não está definido. Querias dizer 'True'?". Para o Python, `true` em minúsculas é o nome de uma variável que nunca nasceu. Corrige-se escrevendo `True`.

## Contas e divisões

As contas escrevem-se quase como no pseudocódigo. Mudam as palavras da divisão inteira e do resto, que passam a sinais, e há um operador novo.

| Pseudocódigo | Python | O que faz | Exemplo | Resultado |
| --- | --- | --- | --- | ---: |
| `+`, `-`, `*` | `+`, `-`, `*` | soma, subtração, multiplicação | `7 * 2` | `14` |
| `/` | `/` | divisão, com parte decimal | `7 / 2` | `3.5` |
| `div` | `//` | divisão inteira: quantas vezes cabe | `7 // 2` | `3` |
| `resto` | `%` | o que sobra da divisão inteira | `7 % 2` | `1` |
| não havia | `**` | potência | `2 ** 3` | `8` |

Antes de leres os resultados, tenta prever o que a consola mostra em cada linha. Repara bem na primeira.

```text
>>> 21 / 3
7.0
>>> 17 // 5
3
>>> 17 % 5
2
>>> 2 * 1.5
3.0
>>> 9 ** 0.5
3.0
```

Leitura guiada: `21 / 3` dá `7.0`, e não `7`. No Python, a divisão com `/` dá sempre um `float`, mesmo quando a conta é exata. É por isso que, nos teus programas, a média de 21 quilos por 3 turmas vai aparecer como `7.0`. As linhas do `//` e do `%` são os 17 rebuçados repartidos por 5 amigos, do guia 02: cada um recebe 3, e sobram 2. Uma conta entre um `int` e um `float` dá um `float`, como `2 * 1.5`. A última linha usa a potência para calcular uma raiz quadrada. Elevar a 0.5 é tirar a raiz, e a raiz de 9 é 3.

A ordem das contas é a da matemática, como no pseudocódigo. Primeiro os parênteses, depois a potência, depois as multiplicações e as divisões, e por fim as somas e as subtrações. Na dúvida, põe parênteses.

Duas coisas podem surpreender-te nas contas.

A primeira é a divisão por zero. Tal como na matemática, não tem resultado. O programa para com `ZeroDivisionError: division by zero`, isto é, "erro de divisão por zero". É por isso que a média continua a precisar do cuidado do guia 04: só se calcula quando há pelo menos um valor.

A segunda é que alguns números com parte decimal não são guardados exatamente. Na consola, `0.1 + 0.2` dá `0.30000000000000004`. O computador guarda os números em binário, só com zeros e uns, e números como 0.1 não têm uma escrita exata em binário. O erro é minúsculo e não estraga as contas do dia a dia. Quando o quiseres esconder no ecrã, arredonda o valor com a função `round`, da secção seguinte.

## Funções predefinidas

Há cálculos que aparecem em quase todos os programas: a distância de um número a zero, o maior de dois valores, um arredondamento. Escrevê-los de cada vez seria perder tempo. Por isso, o Python traz funções já feitas para eles.

Uma **função predefinida** é uma função que já vem com o Python, pronta a usar. Escreves o nome e, entre parênteses, os valores que ela recebe, os argumentos. A função devolve um resultado, que podes guardar numa variável, usar numa conta ou escrever com o `print`. É como as funções que escreveste no guia 05, só que foi outra pessoa a escrevê-las. Não precisas de saber como estão feitas por dentro. Chega-te saber o que recebem e o que devolvem. Já usaste duas, o `print` e o `type`.

A primeira desta secção é `abs`, o **valor absoluto**. Recebe um número e devolve a distância desse número a zero, ou seja, o mesmo número sem sinal. `abs(-7)` dá `7`, e `abs(7)` também. Serve sempre que interessa o tamanho de uma diferença, e não o seu sentido.

Antes de correres este exemplo, tenta prever as duas linhas que aparecem no ecrã.

```python
# idades.py: a diferença de idades entre dois irmãos, sem sinal.
idade_joao = 12
idade_irma = 15
diferenca = abs(idade_joao - idade_irma)
print("Diferença de idades:", diferenca, "anos")
print("O mais velho tem", max(idade_joao, idade_irma), "anos")
```

O resultado é este:

```text
Diferença de idades: 3 anos
O mais velho tem 15 anos
```

Leitura guiada: na quarta linha, primeiro calcula-se o que está dentro dos parênteses, `12 - 15`, que dá `-3`. Depois aplica-se a função, e `abs(-3)` dá `3`, que fica em `diferenca`. Na última linha, a chamada `max(idade_joao, idade_irma)` está dentro do `print`. A chamada faz-se primeiro e devolve 15, e o `print` escreve esse 15 no sítio dela. É o "buraco tapado com o valor devolvido" do guia 05.

O `max` é a função `maior` que escreveste no guia 05, já feita, e aceita dois ou mais valores. O `min` faz o contrário e devolve o menor.

O `round` arredonda um número. Com um só argumento, arredonda às unidades: `round(7.6)` dá `8`. Com um segundo argumento, diz quantas casas decimais ficam: `round(3.14159, 2)` dá `3.14`. Há um pormenor que surpreende. Quando o número está exatamente a meio, como 2.5, o `round` escolhe o inteiro par mais próximo. Por isso, `round(2.5)` dá `2` e `round(3.5)` dá `4`. Num número que não está exatamente a meio, arredonda como na escola.

O `round` também ajuda a comparar números com parte decimal. Por causa do erro minúsculo da secção anterior, `0.1 + 0.2 == 0.3` dá `False`. Já `round(0.1 + 0.2, 2) == 0.3` dá `True`.

O `int`, aplicado a um número com parte decimal, corta a parte decimal, sem arredondar. `int(7.9)` dá `7`, e `int(-7.9)` dá `-7`.

| Função | O que devolve | Exemplo | Resultado |
| --- | --- | --- | ---: |
| `abs(x)` | a distância de `x` a zero | `abs(4 - 9)` | `5` |
| `max(a, b)` | o maior dos valores | `max(12, 30)` | `30` |
| `min(a, b)` | o menor dos valores | `min(12, 30)` | `12` |
| `round(x)` | `x` arredondado às unidades | `round(7.6)` | `8` |
| `round(x, n)` | `x` arredondado a `n` casas decimais | `round(0.1 + 0.2, 2)` | `0.3` |
| `int(x)` | `x` sem a parte decimal | `int(9.99)` | `9` |
| `type(x)` | o tipo de `x` | `type(2.5)` | `<class 'float'>` |

Nas secções seguintes aparecem mais três: o `float` e o `str`, que convertem valores, e o `len`, que conta os elementos de uma lista.

## Ler do teclado com `input`, e converter

No pseudocódigo, uma leitura levava duas linhas: um `Escreve:` com a pergunta e um `ler valor`. No Python, as duas juntam-se numa só. A função `input` escreve a pergunta, espera que a pessoa escreva alguma coisa e carregue em Enter, e devolve o que ela escreveu.

```python
nome = input("Como te chamas? ")
```

O espaço depois do ponto de interrogação, dentro das aspas, separa a pergunta da resposta. Aqui o `print` não ajuda, e o espaço tem de ser teu.

Há uma regra que é a fonte do erro mais frequente deste tema: o `input` devolve sempre um texto, um `str`. Mesmo que a pessoa escreva `14`, o que chega ao programa é o texto `"14"`, com dois algarismos, e não o número catorze.

Antes de correres este exemplo, tenta prever: o que acontece se a pessoa escrever 14?

```python
# proximo_ano.py: lê a idade e diz quantos anos a pessoa faz no próximo ano.
idade = input("Que idade tens? ")
print("No próximo ano fazes", idade + 1, "anos")
```

O programa faz a pergunta, lê o 14 e para na terceira linha com esta mensagem:

```text
Que idade tens? 14
Traceback (most recent call last):
  File "C:\Users\aluno\fp-python\proximo_ano.py", line 3, in <module>
    print("No próximo ano fazes", idade + 1, "anos")
                                  ~~~~~~^~~
TypeError: can only concatenate str (not "int") to str
```

Leitura guiada: lê a mensagem de baixo para cima. A última linha diz o que correu mal: "erro de tipo: só se consegue juntar texto a texto, e não um `int`". As linhas de cima dizem onde: no ficheiro `proximo_ano.py`, na linha 3, e os sinais `~` e `^` apontam para `idade + 1`. O caminho do ficheiro, a seguir a `File`, muda de computador para computador.

O que aconteceu foi isto. `idade` guarda o texto `"14"`. Entre dois textos, o `+` não soma: junta-os, um a seguir ao outro. Entre um texto e um número, o Python não sabe se deve juntar ou somar, e para.

A correção é **converter** o texto num número, logo na leitura, com a função `int`:

```python
# proximo_ano.py: lê a idade e diz quantos anos a pessoa faz no próximo ano.
# O int() converte o texto escrito no teclado num número inteiro.
idade = int(input("Que idade tens? "))
print("No próximo ano fazes", idade + 1, "anos")
```

Com o 14, aparece `No próximo ano fazes 15 anos`.

Leitura guiada: a terceira linha lê-se de dentro para fora. Primeiro o `input` faz a pergunta e devolve o texto `"14"`. Depois o `int` recebe esse texto e devolve o número 14. Só então o 14 fica guardado em `idade`. É a mesma ideia do "buraco tapado", agora com uma chamada dentro de outra.

Cada `int quantidade = ler valor` do pseudocódigo passa a `quantidade = int(input("pergunta "))`. Para um número com parte decimal, usa-se `float` em vez de `int`. Há três funções de conversão:

| Função | Converte para | Exemplo | Resultado |
| --- | --- | --- | --- |
| `int(x)` | número inteiro | `int("12") + 3` | `15` |
| `float(x)` | número com parte decimal | `float("2.5")` | `2.5` |
| `str(x)` | texto | `str(12)` | `"12"` |

E se a pessoa escrever `doze`, em vez de `12`? O `int` não consegue converter esse texto, e o programa para com `ValueError: invalid literal for int() with base 10: 'doze'`. Quer dizer "erro de valor: escrita inválida para um `int` na base 10". O mesmo acontece com `int("2.5")`, porque 2.5 não é inteiro, e com `float("2,5")`, por causa da vírgula. Por agora, quem usa o programa tem de escrever um número. No tema 04 vais aprender a apanhar estes erros e a pedir o valor outra vez.

O `str` serve para o contrário: juntar um número a um texto com `+`, sem espaços. `"Turma " + str(3)` dá o texto `"Turma 3"`. Usa-se quando a mensagem tem de ficar exatamente igual a um enunciado, como "Acertaste à tentativa 3!". Com as vírgulas, o `print` poria um espaço antes do ponto de exclamação.

## Decidir com `if`, `elif` e `else`

A seleção traduz-se palavra a palavra:

| Pseudocódigo | Python |
| --- | --- |
| `Se condição` | `if condição:` |
| `Senão se condição` | `elif condição:` |
| `Senão` | `else:` |
| `e`, `ou`, `não` | `and`, `or`, `not` |
| `==`, `!=`, `<`, `<=`, `>`, `>=` | os mesmos |
| `true`, `false` | `True`, `False` |

Há uma novidade: os **dois pontos** no fim da linha do `if`, do `elif` e do `else`. Dizem ao Python que a seguir vem um bloco, as linhas indentadas que pertencem a essa linha. A indentação é a do pseudocódigo, quatro espaços por nível. No VS Code, quando carregas em Enter depois dos dois pontos, a linha seguinte já começa com os quatro espaços.

Como no pseudocódigo, a indentação decide o que está dentro de quê. Uma linha recuada a mais ou a menos muda de bloco, e o programa passa a fazer outra coisa.

Este é o algoritmo do exemplo guiado do guia 03, que valida e classifica a nota de um teste:

```text
const NOTA_MINIMA = 0
const NOTA_MAXIMA = 20
const LIMIAR_POSITIVA = 10
Escreve: "Nota do teste (inteiro de 0 a 20)?"
int nota = ler valor
Se nota < NOTA_MINIMA ou nota > NOTA_MAXIMA
    Escreve: "Nota inválida"
Senão se nota >= LIMIAR_POSITIVA
    Escreve: "Positiva"
Senão
    Escreve: "Negativa"
```

Em Python fica assim:

```python
# nota.py: classifica a nota de um teste como positiva, negativa ou inválida.
NOTA_MINIMA = 0
NOTA_MAXIMA = 20
LIMIAR_POSITIVA = 10

nota = int(input("Nota do teste (inteiro de 0 a 20)? "))
if nota < NOTA_MINIMA or nota > NOTA_MAXIMA:
    print("Nota inválida")
elif nota >= LIMIAR_POSITIVA:
    print("Positiva")
else:
    print("Negativa")
```

Antes de correres o script, tenta prever o que aparece com cada um destes seis valores. São os valores à volta das fronteiras do 0, do 10 e do 20.

| Nota escrita | O que aparece |
| ---: | --- |
| -1 | Nota inválida |
| 0 | Negativa |
| 9 | Negativa |
| 10 | Positiva |
| 20 | Positiva |
| 21 | Nota inválida |

Corrido seis vezes, o script dá exatamente esta tabela.

Leitura guiada: as constantes ficam no início, separadas do resto por uma linha em branco. A leitura junta a pergunta e o `ler valor`, e converte logo o texto num `int`. A cadeia lê-se como no pseudocódigo: o Python testa as condições por ordem e executa só o bloco da primeira que for verdadeira. Se nenhuma for, executa o bloco do `else`. Repara nos dois pontos no fim de cada uma das três linhas que abrem um bloco.

O erro típico desta ideia é escrever `=` numa condição, em vez de `==`. Com `if nota = 20:`, o Python recusa o programa:

```text
SyntaxError: invalid syntax. Maybe you meant '==' or ':=' instead of '='?
```

Quer dizer "erro de sintaxe: escrita inválida. Talvez quisesses `==` ou `:=` em vez de `=`". O `==` é o que querias. O `:=` é outra coisa, que não se usa nas aulas. Tal como no pseudocódigo, o `=` dá um valor e o `==` pergunta se são iguais.

## Escolher entre valores certos com `match`

Imagina o menu de um jogo. A pessoa escolhe 1 para jogar, 2 para ver as instruções e 3 para sair. Com o que já sabes, escreve-se uma cadeia de `if`, em que cada condição compara a mesma variável com um número diferente:

```python
# menu_if.py: o menu de um jogo, com if, elif e else.
opcao = int(input("1 Jogar, 2 Instruções, 3 Sair. Escolhe: "))
if opcao == 1:
    print("A começar o jogo.")
elif opcao == 2:
    print("Adivinha o número secreto em 10 tentativas ou menos.")
elif opcao == 3:
    print("Até à próxima!")
else:
    print("Essa opção não existe.")
```

Está certa, mas repete `opcao ==` em todas as linhas. Para este caso, em que se compara um só valor com vários valores fixos, o Python tem uma forma mais curta, o `match`:

```python
# menu.py: o menu de um jogo, com uma mensagem para cada opção.
opcao = int(input("1 Jogar, 2 Instruções, 3 Sair. Escolhe: "))
match opcao:
    case 1:
        print("A começar o jogo.")
    case 2:
        print("Adivinha o número secreto em 10 tentativas ou menos.")
    case 3:
        print("Até à próxima!")
    case _:
        print("Essa opção não existe.")
```

Antes de correres, tenta prever o que aparece se a pessoa escrever 2, e se escrever 7.

Com 2, aparece "Adivinha o número secreto em 10 tentativas ou menos.". Com 7, aparece "Essa opção não existe.". As duas versões dão sempre o mesmo resultado.

Leitura guiada: a linha `match opcao:` diz que valor se vai comparar. Cada `case` traz um valor fixo, e o Python executa o bloco do primeiro `case` igual ao valor de `opcao`. O `case _:`, com o traço baixo, apanha qualquer outro valor, como o `else` de uma cadeia de `if`. Os `case` ficam indentados debaixo do `match`, e os blocos de cada `case` ficam mais quatro espaços para dentro.

O `match` serve só para comparar com valores fixos, como números ou textos. Para uma condição como `nota >= 10`, usa-se o `if`. O pseudocódigo das aulas não tinha nada parecido. O `match` é uma forma mais curta de uma cadeia de `Se` que compara sempre a mesma variável.

O `match` só existe a partir da versão 3.10 do Python. Numa versão mais antiga, o programa é recusado com um erro de sintaxe na linha do `match`. Para saberes que versão tens, escreve no terminal `python --version`, ou `python3 --version` no macOS. A secção "O Python 3 e o código antigo" diz mais sobre as versões.

## Repetir com `while`

O `Enquanto` passa a `while`, com os dois pontos no fim e o corpo indentado. Tudo o resto se mantém: as três peças de um ciclo, a tabela de iterações, o caso de zero voltas.

Este é o algoritmo da validação repetida, do guia 04:

```text
const NOTA_MINIMA = 0
const NOTA_MAXIMA = 20
Escreve: "Nota do teste (inteiro de 0 a 20)?"
int nota = ler valor
Enquanto nota < NOTA_MINIMA ou nota > NOTA_MAXIMA
    Escreve: "Nota inválida. Escreve um inteiro de 0 a 20."
    nota = ler valor
Escreve: "Nota aceite: ", nota
```

Em Python, cada par `Escreve:` e `ler valor` junta-se num `input`:

```python
# validar_nota.py: pede a nota de um teste até ela estar na escala de 0 a 20.
NOTA_MINIMA = 0
NOTA_MAXIMA = 20

nota = int(input("Nota do teste (inteiro de 0 a 20)? "))
while nota < NOTA_MINIMA or nota > NOTA_MAXIMA:
    nota = int(input("Nota inválida. Escreve um inteiro de 0 a 20: "))
print("Nota aceite:", nota)
```

Antes de correres, tenta prever quantas voltas dá o ciclo se a pessoa escrever 25, depois -3 e depois 14.

O ecrã fica assim, com os valores que a pessoa escreveu a seguir a cada pergunta:

```text
Nota do teste (inteiro de 0 a 20)? 25
Nota inválida. Escreve um inteiro de 0 a 20: -3
Nota inválida. Escreve um inteiro de 0 a 20: 14
Nota aceite: 14
```

São duas voltas, as mesmas da tabela de iterações do guia 04:

| Teste | nota | Condição | Durante a iteração |
| --- | ---: | --- | --- |
| 1.º | 25 | `25 < 0 or 25 > 20` dá `True` | pede outra vez e lê -3 |
| 2.º | -3 | `-3 < 0 or -3 > 20` dá `True` | pede outra vez e lê 14 |
| 3.º | 14 | `14 < 0 or 14 > 20` dá `False` | o ciclo termina |

Leitura guiada: a inicialização é a primeira leitura, antes do ciclo. A condição é a da nota inválida, com `or`. A atualização é a leitura dentro do corpo, que substitui o valor inválido. Quando o programa chega ao `print` final, a condição do ciclo acabou de dar `False`. Por isso, a nota está de certeza entre 0 e 20.

Se a atualização faltar, o ciclo nunca acaba. No computador, isso vê-se: o programa fica a repetir a mesma coisa, ou fica parado sem fazer nada, e não volta ao terminal. Para o parar, carrega em Ctrl+C no terminal. O programa termina com a palavra `KeyboardInterrupt`, isto é, "interrompido pelo teclado". Depois, procura a peça do ciclo que falta.

## Contar voltas com `for` e `range`

O `Para` do pseudocódigo passa a `for`, com a ajuda de uma função predefinida, o `range`. O `range` produz uma sequência de números inteiros: `range(1, 11)` produz 1, 2, 3 e assim por diante, até 10. O primeiro número entra na sequência, e o segundo não entra. A sequência para logo antes dele.

É isto que liga as duas formas do `Para` ao `range`:

| Pseudocódigo | Python | Valores de `i` |
| --- | --- | --- |
| `Para i de 1 até 10` | `for i in range(1, 11):` | 1, 2, ..., 10 |
| `Para i = 0, i < 10, i++` | `for i in range(0, 10):` | 0, 1, ..., 9 |
| `Para i = 0, i < n, i++` | `for i in range(0, n):` | 0, 1, ..., n - 1 |

A segunda forma do `Para` passa diretamente: o `range(0, 10)` para antes do 10, tal como a condição `i < 10`. A primeira forma precisa de mais 1 no fim, porque o "até 10" do pseudocódigo inclui o 10. O `range(0, n)` também se pode escrever `range(n)`, só com o fim, e começa no 0.

É a tabuada do 7 do guia 04, agora até 7 x 10. Antes de correres o script, tenta prever: qual é a primeira linha que aparece, qual é a última, e quantas linhas são?

```python
# tabuada.py: escreve a tabuada do 7, de 7 x 1 a 7 x 10.
TABUADA = 7

for vezes in range(1, 11):
    print(TABUADA, "x", vezes, "=", TABUADA * vezes)
```

O resultado são dez linhas:

```text
7 x 1 = 7
7 x 2 = 14
7 x 3 = 21
7 x 4 = 28
7 x 5 = 35
7 x 6 = 42
7 x 7 = 49
7 x 8 = 56
7 x 9 = 63
7 x 10 = 70
```

Leitura guiada: o `for` dá à variável `vezes` cada valor do `range`, um por volta, de 1 a 10. Em cada volta, o corpo escreve uma linha, com o `print` a pôr os espaços entre os cinco valores. A conta `TABUADA * vezes` faz-se antes de o `print` escrever. Tal como no `Para`, não há atualização escrita: é o `for` que passa ao valor seguinte.

O erro típico é esquecer que o fim não entra. Com `range(1, 10)`, a tabuada acaba em `7 x 9 = 63`, e a linha do 10 nunca aparece. O Python não dá nenhuma mensagem, porque o programa está bem escrito: faz outra coisa, e só os testes o mostram. Testa sempre a primeira e a última volta, como no guia 04.

## Percorrer uma lista com `for`

Os arrays do pseudocódigo das aulas já se escreviam como as listas do Python. No Python chamam-se **listas**, e escrevem-se da mesma maneira: valores entre parênteses retos, separados por vírgulas. O índice começa em 0, e `pontuacoes[0]` é o primeiro elemento.

Há uma função predefinida nova para as listas, o `len`, do inglês *length*, "comprimento". Recebe uma lista e devolve quantos elementos ela tem. Com `pontuacoes = [12, 7, 20, 5]`, `len(pontuacoes)` dá `4`, e o último índice válido é `len(pontuacoes) - 1`, que é 3.

O `Para cada` passa a `for`, sem `range`:

| Pseudocódigo | Python |
| --- | --- |
| `pontuacoes = [12, 7, 20, 5]` | `pontuacoes = [12, 7, 20, 5]` |
| `pontuacoes[0]` | `pontuacoes[0]` |
| `Para cada pontuacao em pontuacoes` | `for pontuacao in pontuacoes:` |
| `Para i = 0, i < 4, i++` | `for i in range(0, len(pontuacoes)):` |

Este é o contador do guia 04, que conta os jogos da equipa com 10 ou mais pontos. Antes de correres o script, tenta prever quantos jogos conta.

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

Leitura guiada: o `for` dá à variável `pontuacao`, em cada volta, o elemento seguinte da lista: 12, 7, 20 e 5. O contador nasce antes do ciclo, com 0. A linha que o aumenta tem oito espaços, dentro do `if`. Por isso, só conta as voltas em que a condição é verdadeira, a do 12 e a do 20. O `print` está encostado à margem, fora do ciclo, e escreve-se uma só vez, no fim. A tabela de iterações é exatamente a do guia 04.

Quando é preciso o número de cada jogo, percorre-se a lista com o índice:

```python
# jogos_por_numero.py: escreve a pontuação de cada jogo, com o número do jogo.
pontuacoes = [12, 7, 20, 5]
for i in range(0, len(pontuacoes)):
    print("Jogo", i + 1, "teve", pontuacoes[i], "pontos")
```

Antes de correres, tenta prever a primeira e a última linha. O resultado são quatro linhas:

```text
Jogo 1 teve 12 pontos
Jogo 2 teve 7 pontos
Jogo 3 teve 20 pontos
Jogo 4 teve 5 pontos
```

Leitura guiada: o `range(0, len(pontuacoes))` é o `range(0, 4)`, e dá os índices 0, 1, 2 e 3. Em cada volta, `pontuacoes[i]` é o elemento nessa posição, e `i + 1` é o número do jogo para as pessoas, que começam a contar no 1. Com o `len`, o ciclo serve para uma lista de qualquer tamanho, sem escreveres o 4 à mão.

Em cada volta, a variável do `for` recebe um valor da lista. Dar-lhe um valor novo, como `pontuacao = 0`, não muda a lista, tal como no `Para cada`. Para mudar um elemento, usa-se o índice, como no guia 04: `pontuacoes[1] = 9` põe 9 no lugar do 7.

O erro típico é usar um índice que não existe. Com `pontuacoes[4]`, numa lista de 4 elementos, o programa para com `IndexError: list index out of range`, isto é, "erro de índice: índice da lista fora dos limites". O último índice válido é o 3. Com o `for` sem índice, este erro não pode acontecer.

## Parar e continuar: `break` e `continue`

O `Parar` passa a `break`, e o `Continuar` passa a `continue`. Fazem exatamente o mesmo que no pseudocódigo. O `break` termina o ciclo já, e o programa continua na primeira linha a seguir ao ciclo. O `continue` termina só a volta atual, e o ciclo passa à volta seguinte.

Este é o exemplo do `Parar` do guia 04, que procura o primeiro jogo em que a equipa não marcou golos. Antes de correres, tenta prever o que aparece e quantas voltas dá o ciclo.

```python
# golos.py: procura o primeiro jogo em que a equipa não marcou golos.
golos = [2, 1, 0, 3, 0]
encontrado = False
for i in range(0, len(golos)):
    if golos[i] == 0:
        print("Primeiro jogo sem golos: jogo", i + 1)
        encontrado = True
        # O break sai do ciclo: depois de encontrar o primeiro 0, o resto não interessa.
        break
if encontrado == False:
    print("A equipa marcou em todos os jogos.")
```

O resultado é `Primeiro jogo sem golos: jogo 3`, depois de três voltas.

Leitura guiada: a bandeira `encontrado` começa em `False`, com maiúscula. O ciclo percorre a lista pelo índice, porque a resposta é uma posição. Na terceira volta, `golos[2]` vale 0, e o programa escreve a resposta, levanta a bandeira e sai do ciclo com o `break`. O `if` de fora, depois do ciclo, só escreve quando o ciclo acabou sem encontrar nenhum 0. A condição `encontrado == False` também se pode escrever `not encontrado`, que é o `não` do pseudocódigo.

Este é o exemplo do `Continuar`, que soma só as leituras boas de um sensor. Antes de correres, tenta prever o total.

```python
# leituras.py: soma só as leituras boas de um sensor, que regista negativos quando falha.
leituras = [5, -2, 8, -1, 4]
total = 0
for leitura in leituras:
    if leitura < 0:
        # O continue salta o resto da volta: a leitura negativa não é somada.
        continue
    total = total + leitura
print("Total das leituras válidas:", total)
```

O resultado é `Total das leituras válidas: 17`, que é 5 + 8 + 4.

Leitura guiada: nas voltas do -2 e do -1, a condição é verdadeira e o `continue` salta a soma. Nas outras, a condição é falsa, e a soma faz-se. O cuidado do guia 04 mantém-se: num `while`, o `continue` não pode saltar a atualização, ou o ciclo nunca acaba.

## Funções com `def` e `return`

Uma função do pseudocódigo traduz-se assim:

| Pseudocódigo | Python |
| --- | --- |
| `Função areaRetangulo(comprimento, largura)` | `def area_retangulo(comprimento, largura):` |
| `devolver comprimento * largura` | `return comprimento * largura` |
| `float area = areaRetangulo(3, 2)` | `area = area_retangulo(3, 2)` |

A palavra `def` vem de *define*, "definir". O cabeçalho acaba com dois pontos, e o corpo vai indentado, como num `if`. O `devolver` passa a `return`, e faz o mesmo: entrega o valor e termina a função. A chamada escreve-se como no pseudocódigo, e as quatro fases de uma chamada, do guia 05, são as mesmas.

Antes de correres este exemplo, tenta prever as duas linhas que aparecem.

```python
# area.py: calcula a área de um retângulo com uma função.


def area_retangulo(comprimento, largura):
    """Devolve a área de um retângulo.

    Recebe o comprimento e a largura, números maiores do que zero,
    na mesma unidade. A área vem na unidade ao quadrado.
    """
    return comprimento * largura


area = area_retangulo(3, 2)
print("Área:", area)
print("Outra área:", area_retangulo(1.5, 1.5))
```

O resultado é este:

```text
Área: 6
Outra área: 2.25
```

Leitura guiada: o `def` define a função, e sozinho não executa nada. O programa começa a fazer coisas na linha `area = area_retangulo(3, 2)`. Nessa linha, o 3 passa para `comprimento` e o 2 para `largura`. A função calcula 6, o `return` devolve-o, e o 6 fica em `area`. Na última linha, a chamada está dentro do `print`, com outros argumentos, e devolve 2.25.

Por baixo do cabeçalho, entre três pares de aspas, está a **documentação** da função. Diz o que a função faz, o que recebe e o que devolve, para quem a vai usar sem ler o corpo. O Python guarda-a, mas não a executa. No Python chama-se *docstring*, de *documentation string*, "texto de documentação". Todas as funções das aulas a têm.

Há duas convenções de forma. As funções ficam depois das constantes e antes da parte principal do programa, como no guia 05. E deixam-se duas linhas em branco antes e depois de cada função, para se verem bem.

A ordem não é só uma convenção. O Python executa o ficheiro de cima para baixo, e a linha do `def` é a que cria a função. Se a chamada aparecer antes do `def`, o programa para com `NameError: name 'area_retangulo' is not defined`, porque nessa altura a função ainda não existe.

### Uma função sem `return` devolve `None`

Um erro frequente com funções é a função que calcula, mas não devolve. Num trace à mão, nota-se pela falta de uma linha com o valor devolvido. No Python, vê-se no ecrã. Antes de correres este exemplo, tenta prever o que aparece.

```python
# sem_return.py: uma função que calcula mas se esquece de devolver.


def area_retangulo(comprimento, largura):
    """Devia devolver a área de um retângulo, mas falta-lhe o return."""
    resultado = comprimento * largura


area = area_retangulo(3, 2)
print("Área:", area)
```

Aparece `Área: None`.

Leitura guiada: a função calcula 6 e guarda-o em `resultado`, uma variável local, que desaparece quando a função termina. Como não há `return`, a função devolve `None`, o valor que quer dizer "nenhum valor". É esse `None` que fica em `area` e que o `print` escreve. Quando vires `None` onde esperavas um número, procura um `return` em falta. A correção é acrescentar `return resultado` como última linha do corpo.

Continua a valer a regra do guia 05: as funções que calculam devolvem, e quem escreve no ecrã é a parte principal do programa.

## Os três tipos de erro

Quando um programa falha, o primeiro passo é dizer que tipo de erro é. Há três.

Um **erro de sintaxe** acontece quando o código não cumpre as regras da linguagem: falta uns dois pontos, umas aspas ou um espaço da indentação. O Python recusa o programa antes de executar qualquer linha, e nada aparece no ecrã além da mensagem. A mensagem diz o ficheiro e a linha, mostra a linha com sinais `^` debaixo do sítio do problema, e acaba com `SyntaxError` ou `IndentationError`. Por exemplo, sem a aspa que fecha o texto:

```text
  File "C:\Users\aluno\fp-python\ola.py", line 2
    print("Olá, Python!)
          ^
SyntaxError: unterminated string literal (detected at line 2)
```

Quer dizer "erro de sintaxe: texto por terminar, detetado na linha 2".

Um **erro de execução** acontece quando o código está bem escrito, mas uma linha não se consegue executar com os valores que tem. O programa corre até essa linha e para a meio. A estes erros o Python chama **exceções**. A mensagem começa por `Traceback (most recent call last)`, isto é, "o rasto, com a chamada mais recente no fim". Viste uma na secção do `input`. Lê-se de baixo para cima. A última linha diz o tipo de erro e o que aconteceu. As linhas de cima dizem em que ficheiro e em que linha.

Um **erro de lógica** acontece quando o programa corre até ao fim, sem mensagem nenhuma, mas dá o resultado errado. É a tabuada que acaba no 9, ou um contador que conta de mais. O Python não o pode apanhar, porque não sabe o que querias. Só o encontras se comparares o que o programa mostra com o que calculaste à mão, nos casos de teste.

As exceções que mais vais ver neste tema são estas:

| Mensagem | Em português | Quando acontece |
| --- | --- | --- |
| `NameError` | erro de nome | um nome que não existe: uma variável mal escrita, `true` em vez de `True` |
| `TypeError` | erro de tipo | uma operação com tipos que não combinam, como texto mais número |
| `ValueError` | erro de valor | uma conversão impossível, como `int("doze")` |
| `ZeroDivisionError` | erro de divisão por zero | uma divisão por 0 |
| `IndexError` | erro de índice | um índice fora da lista |

Há uma regra que vale para os erros de execução e para os de sintaxe. A linha que a mensagem aponta é onde o Python deu pelo problema, e a causa pode estar antes. No erro do `input`, a mensagem apontava a linha da conta, mas a causa estava na linha de cima, na leitura sem `int`. A mensagem é uma pista, e não a resposta.

Quando um programa teu falha, segue sempre a mesma rotina, a da algoritmia, agora com o computador:

1. **Observar e reproduzir o erro.** Escreve o caso que falhou, o resultado esperado, tirado do enunciado, e o resultado obtido. Diz também que tipo de erro é: de sintaxe, de execução ou de lógica.
2. **Formular uma hipótese.** Escreve numa frase o que achas que causa o erro.
3. **Verificar a hipótese.** Segue os valores no caso mais curto que ainda mostra o erro. Podes usar a mensagem, uma tabela de trace ou um `print` provisório que mostre o valor de uma variável.
4. **Corrigir a causa.** Muda a instrução que produz o erro, e não o sítio onde ele se vê.
5. **Voltar a testar tudo.** Corre outra vez todos os casos, também os que já passavam, e explica o que mudou.

## O Python 3 e o código antigo

As linguagens de programação também têm versões, como as aplicações do telemóvel. O Python 2 saiu em 2000 e o Python 3 em 2008. O Python 3 mudou várias coisas, e muitos programas escritos para o Python 2 não correm no Python 3. O Python 2 deixou de ser mantido no início de 2020, e hoje usa-se só o Python 3.

Na internet, em livros antigos e em respostas de fóruns, ainda há muito código escrito para o Python 2. Reconhece-se por três sinais:

| No Python 2 | No Python 3 |
| --- | --- |
| `print "Olá"`, sem parênteses | `print("Olá")` |
| `raw_input("Nome? ")` para ler um texto | `input("Nome? ")` |
| `7 / 2` dava `3`, uma divisão inteira | `7 / 2` dá `3.5`; a divisão inteira é `7 // 2` |

Se correres código do Python 2 no Python 3, o mais provável é um erro de sintaxe logo no primeiro `print`. O Python 3 até diz o que se passa:

```text
SyntaxError: Missing parentheses in call to 'print'. Did you mean print(...)?
```

Quer dizer "erro de sintaxe: faltam os parênteses na chamada ao `print`. Querias dizer `print(...)`?". O `raw_input` dá `NameError`, porque no Python 3 não existe. A divisão é a mais perigosa das três. Não dá erro nenhum, e o programa passa a dar outro resultado.

Dentro do Python 3 também há versões, numeradas 3.10, 3.11, 3.12 e assim por diante. Cada uma acrescenta coisas: o `match` apareceu na 3.10, e as mensagens de erro ficam mais claras de versão para versão. As mensagens de erro deste guia, como a secção da consola já dizia, são as do Python 3.14. Para saberes que versão tens, escreve no terminal:

```bash
python --version
```

No macOS, o comando é `python3 --version`. Aparece uma linha como `Python 3.13.2`. O primeiro número tem de ser 3.

## Exemplo guiado: o resumo das notas de um teste, em Python

### Passo 1: o problema

Este problema vem do exemplo guiado do guia 05, onde está resolvido em pseudocódigo:

> Um professor guardou numa lista as notas de um teste, todas inteiras: `notas = [14, 9, 17, 10, 6, 16]`. Quer um programa que, antes de mais nada, confirme que todas as notas estão na escala de 0 a 20. Se houver alguma nota fora da escala, o programa escreve "Há notas inválidas" e não calcula mais nada. Se estiverem todas certas, escreve a média da turma e quantas notas são positivas, ou seja, 10 ou mais.

O pseudocódigo do passo 2 já resolve o problema. Agora falta traduzi-lo, calcular à mão os resultados esperados e pôr o computador a confirmá-los.

### Passo 2: o pseudocódigo

Este é o algoritmo, com três funções e a parte principal. A função `notaValida` diz se uma nota está na escala. A `media` calcula a média de uma lista, e a `contarPositivas` conta as notas de 10 ou mais:

```text
const NOTA_MINIMA = 0
const NOTA_MAXIMA = 20
const LIMIAR_POSITIVA = 10

Função notaValida(nota)
    devolver nota >= NOTA_MINIMA e nota <= NOTA_MAXIMA

Função media(valores)
    int quantidade = 0
    int total = 0
    Para cada valor em valores
        quantidade = quantidade + 1
        total = total + valor
    devolver total / quantidade

Função contarPositivas(notas)
    int positivas = 0
    Para cada nota em notas
        Se nota >= LIMIAR_POSITIVA
            positivas = positivas + 1
    devolver positivas

notas = [14, 9, 17, 10, 6, 16]
bool todasValidas = true
Para cada nota em notas
    Se notaValida(nota) == false
        todasValidas = false
        Parar
Se todasValidas
    float mediaDaTurma = media(notas)
    int positivas = contarPositivas(notas)
    Escreve: "Média: ", mediaDaTurma
    Escreve: "Positivas: ", positivas
Senão
    Escreve: "Há notas inválidas"
```

### Passo 3: traduzir linha a linha

Cada tipo de linha do pseudocódigo tem a sua tradução, e todas estão nas secções deste guia:

| No pseudocódigo | No Python | Porquê |
| --- | --- | --- |
| `const NOTA_MINIMA = 0` | `NOTA_MINIMA = 0` | sem `const`; as maiúsculas dizem que é constante |
| `Função notaValida(nota)` | `def nota_valida(nota):` | `def`, o nome com traço baixo e os dois pontos |
| `devolver nota >= NOTA_MINIMA e nota <= NOTA_MAXIMA` | `return nota >= NOTA_MINIMA and nota <= NOTA_MAXIMA` | `return` e `and` |
| `int quantidade = 0` | `quantidade = 0` | sem o tipo |
| `Para cada valor em valores` | `for valor in valores:` | `for` e os dois pontos |
| `Se nota >= LIMIAR_POSITIVA` | `if nota >= LIMIAR_POSITIVA:` | `if` e os dois pontos |
| `bool todasValidas = true` | `todas_validas = True` | sem o tipo; `True` com maiúscula; o nome com traço baixo |
| `Parar` | `break` | |
| `Senão` | `else:` | |
| `Escreve: "Média: ", mediaDaTurma` | `print("Média:", media_da_turma)` | sem o espaço dentro das aspas |

E há uma linha que se acrescenta: a documentação de cada função, por baixo do cabeçalho.

### Passo 4: o script completo

```python
# resumo_notas.py: confirma que as notas de um teste estão na escala de 0 a 20
# e, se estiverem, mostra a média da turma e quantas notas são positivas.

NOTA_MINIMA = 0
NOTA_MAXIMA = 20
LIMIAR_POSITIVA = 10


def nota_valida(nota):
    """Diz se uma nota está na escala.

    Recebe uma nota inteira. Devolve True se ela estiver entre 0 e 20,
    incluindo os extremos, e False se não estiver.
    """
    return nota >= NOTA_MINIMA and nota <= NOTA_MAXIMA


def media(valores):
    """Calcula a média de uma lista de números.

    A lista tem de ter pelo menos um número: com a lista vazia,
    a conta seria 0 / 0, e o programa parava com um erro.
    Devolve a média, um float.
    """
    quantidade = 0
    total = 0
    for valor in valores:
        quantidade = quantidade + 1
        total = total + valor
    return total / quantidade


def contar_positivas(notas):
    """Conta as notas positivas de uma lista de notas válidas.

    Devolve quantas notas são 10 ou mais. Com a lista vazia, devolve 0.
    """
    positivas = 0
    for nota in notas:
        if nota >= LIMIAR_POSITIVA:
            positivas = positivas + 1
    return positivas


notas = [14, 9, 17, 10, 6, 16]
todas_validas = True
for nota in notas:
    if nota_valida(nota) == False:
        todas_validas = False
        break
if todas_validas:
    media_da_turma = media(notas)
    positivas = contar_positivas(notas)
    print("Média:", media_da_turma)
    print("Positivas:", positivas)
else:
    print("Há notas inválidas")
```

Repara que a função `media` conta os elementos com um contador, como no pseudocódigo. Agora que conheces o `len`, `len(valores)` dava o mesmo número. A tradução linha a linha é a primeira versão, e só depois se procura a forma mais curta.

### Passo 5: testar as funções sozinhas

Antes de se escrever a parte principal, testa-se cada função sozinha, com poucos casos. Assim, se o programa completo falhar, já se sabe que as funções estão certas. Escreve o ficheiro até à última função e, no fim, acrescenta estas linhas provisórias. Cada uma chama as funções com valores escolhidos à volta das fronteiras:

```python
print(nota_valida(-1), nota_valida(0), nota_valida(1))
print(nota_valida(19), nota_valida(20), nota_valida(21))
print(media([10]), media([0, 20]), media([14, 9, 17, 10, 6, 16]))
print(contar_positivas([]), contar_positivas([9]), contar_positivas([10]))
print(contar_positivas([11]), contar_positivas([14, 9, 17, 10, 6, 16]))
```

Antes de correres, calcula à mão o que cada chamada devolve, e escreve o que esperas em cada linha. O resultado é este:

```text
False True True
True True False
10.0 10.0 12.0
0 0 1
1 4
```

Leitura guiada: o `print` recebe várias chamadas, e cada uma é substituída pelo valor que devolve. Os seis testes de `nota_valida` são os valores à volta das duas fronteiras. Os de `media` dão `10.0` e `12.0`, com o ponto zero, porque a divisão com `/` dá sempre um `float`. Os de `contar_positivas` incluem a lista vazia, que a função aceita. Os catorze resultados são os que se calculam à mão. Quando estão todos certos, apagam-se as linhas provisórias e escreve-se a parte principal.

### Passo 6: correr os casos do problema

Os casos de teste do problema são listas diferentes. Antes de correres, calcula à mão a saída de cada um. Para correr cada caso, muda-se a linha `notas = [...]` e corre-se outra vez.

| Notas | Esperado, calculado à mão | O que o Python mostra |
| --- | --- | --- |
| `[14, 9, 17, 10, 6, 16]` | Média 12; 4 positivas | `Média: 12.0` e `Positivas: 4` |
| `[10]` | Média 10; 1 positiva | `Média: 10.0` e `Positivas: 1` |
| `[9]` | Média 9; 0 positivas | `Média: 9.0` e `Positivas: 0` |
| `[0, 20]` | Média 10; 1 positiva | `Média: 10.0` e `Positivas: 1` |
| `[12, 21, 8]` | Há notas inválidas | `Há notas inválidas` |

Os cinco casos dão o que se calculou à mão. A única diferença está na forma da média, `12.0` em vez de 12. Tem a ver com a divisão no Python, e não com a lógica.

### Passo 7: o quadro das diferenças

Ao traduzir, juntaste uma lista do que muda do pseudocódigo para o Python. É bom tê-la escrita, porque vai servir em cada tradução que fizeres:

| O que muda | No pseudocódigo | No Python |
| --- | --- | --- |
| O tipo das variáveis | escreve-se onde a variável nasce | não se escreve |
| As constantes | `const` | só o nome em maiúsculas |
| Os nomes compostos | `mediaDaTurma` | `media_da_turma` |
| Os valores lógicos | `true`, `false` | `True`, `False` |
| Os operadores lógicos | `e`, `ou`, `não` | `and`, `or`, `not` |
| O início de um bloco | só a indentação | os dois pontos e a indentação |
| A escrita no ecrã | `Escreve:`, com os espaços dentro das aspas | `print`, que põe os espaços sozinho |
| A leitura | `Escreve:` e `ler valor` | `input`, e a conversão com `int` ou `float` |
| A divisão | `7 / 2` dá 3.5, e uma conta exata dá um inteiro | `/` dá sempre um `float`, como `12.0` |
| A documentação de uma função | não havia | o texto entre três aspas, por baixo do cabeçalho |

O que não mudou é o mais importante: as decisões, os ciclos, as funções e os casos de teste. Foi isso que pensaste na algoritmia, e foi isso que o computador confirmou.

## Erros frequentes

Os erros desta secção não ficaram em nenhuma das secções anteriores. Para cada um, ficas a saber o que aparece, porque acontece e como se corrige. Os outros estão na secção da ideia que explicam:

- o `python ola.py` escrito dentro da consola, em "A consola do Python, para experimentar uma linha";
- os espaços a dobrar no `print`, em "Escrever no ecrã com `print`";
- o `true` em minúsculas, em "Os tipos dos valores";
- a conversão esquecida e o número escrito com vírgula, em "Ler do teclado com `input`, e converter";
- o `=` numa condição, em "Decidir com `if`, `elif` e `else`";
- o ciclo que nunca acaba, em "Repetir com `while`";
- o fim do `range`, em "Contar voltas com `for` e `range`";
- o índice fora da lista, em "Percorrer uma lista com `for`";
- a chamada antes do `def` e a função sem `return`, em "Funções com `def` e `return`".

### A indentação em falta

O que se vê, no `nota.py` da secção do `if`, com a linha `print("Nota inválida")` encostada à margem:

```text
  File "C:\Users\aluno\fp-python\nota.py", line 8
    print("Nota inválida")
    ^^^^^
IndentationError: expected an indented block after 'if' statement on line 7
```

Quer dizer "erro de indentação: esperava-se um bloco indentado depois do `if` da linha 7". Acontece quando a linha a seguir a uns dois pontos fica encostada à margem. Depois de um `if`, de um `while`, de um `for` ou de um `def`, o Python exige pelo menos uma linha indentada. Corrige-se recuando o bloco quatro espaços.

### Os dois pontos esquecidos

O que se vê, com `if nota >= 10` sem os dois pontos:

```text
SyntaxError: expected ':'
```

Quer dizer "erro de sintaxe: esperavam-se os dois pontos". Acontece a quem traduz o pseudocódigo à letra, porque lá não havia dois pontos. Corrige-se acrescentando os dois pontos no fim da linha. Em qualquer linha que abre um bloco, `if`, `elif`, `else`, `while`, `for`, `def`, `match` e `case`, os dois pontos são obrigatórios.

### Palavras do pseudocódigo no meio do Python

O que se vê, com `if nota >= 0 e nota <= 20:`:

```text
SyntaxError: invalid syntax
```

Os sinais `^` apontam para o `e`. Acontece quando uma palavra do pseudocódigo fica no programa: `e`, `ou`, `Se`, `Enquanto`, `Escreve:`. O Python não as conhece. Corrige-se com a palavra do Python, que está nas tabelas deste guia, aqui `and`.

### Um nome mal escrito

O que se vê, com `print("Total:", total_quilo, "kg")` num programa em que a variável se chama `total_quilos`:

```text
NameError: name 'total_quilo' is not defined. Did you mean: 'total_quilos'?
```

Quer dizer "erro de nome: o nome `total_quilo` não está definido. Querias dizer `total_quilos`?". Acontece com um nome escrito de outra maneira, com uma letra a menos ou uma maiúscula trocada. Para o Python, é outra variável, que nunca nasceu. O mesmo acontece com `prnt` em vez de `print`. Corrige-se escrevendo o nome exatamente igual ao da linha onde ele nasceu. A sugestão do fim da mensagem costuma acertar.

### Correr a versão antiga do ficheiro

O que se vê: corriges o código, voltas a correr, e aparece o mesmo erro, ou o mesmo resultado errado, como se nada tivesse mudado.

Acontece quando o ficheiro não foi guardado depois da alteração. O interpretador corre o ficheiro que está no disco. Corrige-se guardando com Ctrl+S, ou Cmd+S no macOS, antes de correr. No VS Code, a bola cheia no separador do ficheiro, no lugar do X, avisa que há alterações por guardar.

## Palavras novas deste guia

- Linguagem de programação: uma maneira de escrever algoritmos com regras exatas, que o computador consegue executar.
- Programa: um algoritmo escrito numa linguagem de programação.
- Interpretador: o programa que lê um script em Python, confirma que está bem escrito e executa as instruções por ordem.
- Script: um ficheiro de texto com instruções em Python, com o nome a acabar em `.py`.
- Biblioteca padrão: a coleção de funções já feitas que vem com o Python.
- VS Code: o editor de código das aulas, um programa para escrever código, com um terminal lá dentro.
- Terminal: uma janela onde se escrevem comandos para o computador, um por linha.
- Comando: uma ordem escrita no terminal, como `python ola.py`.
- Consola do Python: o modo em que o Python executa uma linha de cada vez e mostra logo o resultado, a seguir ao `>>>`.
- Comentário: uma nota para quem lê o código, a seguir a `#`, que o Python ignora.
- `print`: a função que escreve valores no ecrã, com um espaço entre cada dois.
- Tipagem dinâmica: a forma de o Python funcionar, em que o tipo está no valor e não se escreve na variável.
- Convenção: uma regra combinada entre as pessoas, que a linguagem não obriga a cumprir, como os nomes com traço baixo.
- Palavras reservadas: as palavras que pertencem à linguagem e não podem ser nomes, como `if` ou `def`.
- `str`: o tipo dos textos no Python, a abreviatura de string.
- `True` e `False`: os valores lógicos do Python, com maiúscula.
- `None`: o valor que quer dizer "nenhum valor"; é o que devolve uma função sem `return`.
- `type`: a função que devolve o tipo de um valor.
- `//`: a divisão inteira, o `div` do pseudocódigo.
- `%`: o resto da divisão inteira, o `resto` do pseudocódigo.
- `**`: a potência.
- Função predefinida: uma função que já vem com o Python, pronta a usar, como `abs` ou `round`.
- Valor absoluto: a distância de um número a zero, que a função `abs` devolve.
- `input`: a função que escreve uma pergunta, lê o que a pessoa escreve e o devolve, sempre como texto.
- Converter: transformar um valor de um tipo noutro, como o texto `"14"` no número 14, com `int`, `float` ou `str`.
- Dois pontos: o sinal no fim da linha que abre um bloco, como a de um `if` ou de um `def`.
- `if`, `elif` e `else`: o `Se`, o `Senão se` e o `Senão` do Python.
- `match` e `case`: a forma de comparar um valor com vários valores fixos, com `case _` para qualquer outro.
- `while`: o `Enquanto` do Python.
- `for`: o ciclo que percorre uma sequência, como a de um `range` ou uma lista; é o `Para` e o `Para cada`.
- `range`: a função que produz uma sequência de inteiros, do primeiro número até antes do segundo.
- Lista: o array do pseudocódigo, no Python.
- `len`: a função que devolve quantos elementos tem uma lista.
- `break` e `continue`: o `Parar` e o `Continuar` do Python.
- `def` e `return`: a `Função` e o `devolver` do Python.
- Documentação de uma função: o texto entre três pares de aspas, por baixo do cabeçalho, que diz o que a função recebe e devolve.
- Erro de sintaxe: um erro na escrita do código, que faz o Python recusar o programa antes de executar qualquer linha.
- Erro de execução, ou exceção: um erro que para o programa a meio, numa linha que não se consegue executar com aqueles valores.
- Erro de lógica: um erro que não dá mensagem nenhuma; o programa corre e dá o resultado errado.
- Traceback: a mensagem de um erro de execução, que se lê de baixo para cima.
- Python 2: a versão antiga do Python, que já não se usa, e cujo código muitas vezes não corre no Python 3.

## Verificar o que aprendeste

Usa estas perguntas para te testares. Responde a cada uma sem olhar para o guia. Se não conseguires, volta à secção que explica a ideia.

1. O que faz o interpretador quando corres `python ola.py`? Porque é que um erro de sintaxe na última linha impede a primeira de se executar?
2. Para que serve a consola do Python, e em que é que é diferente de um script?
3. O que escreve `print("Total:", 21, "kg")`? E `print("Total: ", 21, " kg")`?
4. Traduz para Python: `int totalPontos = 0` e `const MAXIMO_JOGADORES = 6`.
5. De que tipo é cada um destes valores: `3`, `3.0`, `"3"`, `True`, `None`?
6. Quanto dá `23 // 4`, `23 % 4` e `23 / 4`? E `8 / 4`, de que tipo é?
7. O que devolve `round(4.5)`? E `int(4.5)`? E `abs(-4.5)`?
8. Porque é que `idade = input("Idade? ")` seguido de `idade + 1` dá erro? Como se corrige, e que erro aparece se a pessoa escrever `quinze`?
9. Traduz para Python: `Se temperatura >= 18 e temperatura < 26`, com o bloco `Escreve: "Temperatura boa"`.
10. Que `range` usas para `Para i de 1 até 5`? E para `Para i = 0, i < 5, i++`?
11. Com `idades = [15, 14, 16]`, quanto vale `len(idades)`, qual é o último índice válido e o que acontece com `idades[3]`?
12. O que aparece no ecrã se uma função não tiver `return` e o resultado dela for escrito com um `print`?
13. Diz que tipo de erro é cada um. Primeiro, o programa não arranca e aponta uma linha com `^`. Depois, o programa para a meio com `TypeError`. Por fim, o programa acaba, mas a média está errada.
14. Viste numa página da internet a linha `print "Olá"`. Que versão do Python é, e como fica no Python 3?

## O que vem a seguir

Para praticar este tema, faz o [laboratório](01-do-pseudocodigo-ao-python-laboratorio.md). Nele passas para Python, fase a fase, o algoritmo da campanha de recolha de alimentos do guia 04. Depois faz a [ficha de exercícios](01-do-pseudocodigo-ao-python-exercicios.md), com traduções, um script com erros para encontrar e uma função desconhecida para explicar.

O tema seguinte é Coleções, strings e escolha de representação. As listas deste tema eram dadas no programa e nunca mudavam de tamanho. No tema seguinte vais aprender a acrescentar e a tirar elementos, e a trabalhar com textos letra a letra. Vais também usar outras formas de guardar dados, como os dicionários. Num dicionário, procura-se um valor por um nome, em vez de uma posição.

![Rodapé](../imagens/rodape.png)
