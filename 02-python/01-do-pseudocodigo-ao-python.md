![Cabeçalho](../imagens/cabecalho.png)

# Do pseudocódigo ao Python

Módulo Criar aplicações em linguagem de programação Python. Neste guia ficas a saber onde se escreve um programa e com que ferramentas, e escreves e corres os teus primeiros scripts em Python. Para praticar, há o [laboratório](laboratorios/01-do-pseudocodigo-ao-python-laboratorio.md) e a [ficha de exercícios](exercicios/01-do-pseudocodigo-ao-python-exercicios.md) deste tema.

Na algoritmia, quem executava os algoritmos eras tu, linha a linha, numa tabela de trace. A partir de agora é o computador. Antes da primeira linha de Python, há uma pergunta a que tens de saber responder: onde se escreve um programa, e com que ferramentas? Este tema responde-lhe, e fica pelos programas que só escrevem no ecrã. As variáveis, as contas e a leitura do teclado ficam para o tema seguinte, Dados e interação.

Lê-se ao teu ritmo, em várias vezes, com o computador ao lado. Cada exemplo pode ser copiado para um ficheiro e corrido, e é assim que se aprende mais.

## Neste guia

1. O que vais aprender
2. O que já sabes e vais usar
3. Um programa é um algoritmo que o computador executa
4. Onde se escreve um programa
5. Do editor de texto ao editor de código
6. O ambiente de desenvolvimento integrado, o IDE
7. As ferramentas do VS Code
8. Correr um script
9. A consola do Python, para experimentar uma linha
10. Quando é preciso um IDE, e quando não
11. Escrever no ecrã com `print`
12. Comentários: notas para quem lê o código
13. Os três tipos de erro
14. O Python 3 e o código antigo
15. Exemplo guiado: o ecrã das regras do duelo de dados
16. Erros frequentes
17. Palavras novas deste guia
18. Verificar o que aprendeste
19. O que vem a seguir

## O que vais aprender

No fim deste guia, consegues:

- dizer o que é um programa, um interpretador e um script;
- explicar a diferença entre um editor de texto, um editor de código e um IDE;
- dizer para que serve cada ferramenta do VS Code que usas nas aulas;
- decidir quando precisas de um IDE e quando te chegam a consola ou um editor simples;
- correr um script no terminal e com o botão de correr, e experimentar uma linha na consola do Python;
- escrever no ecrã, com `print`, textos e números, e pôr comentários no código;
- dizer se um erro é de sintaxe, de execução ou de lógica, e ler a mensagem que o Python mostra;
- reconhecer código escrito para o Python 2.

## O que já sabes e vais usar

- As variáveis: guia [02 Estado, sequência e representações](../01-algoritmos/02-estado-sequencia-representacoes.md), secção "Variáveis".
- A tabela de trace: guia [02](../01-algoritmos/02-estado-sequencia-representacoes.md), secção "Tabela de trace".
- A forma do pseudocódigo das aulas e a indentação: guia [02](../01-algoritmos/02-estado-sequencia-representacoes.md), secção "A forma de escrever pseudocódigo nas aulas".
- O `Escreve:`, com textos e valores separados por vírgulas: guia [02](../01-algoritmos/02-estado-sequencia-representacoes.md), secção "Entrada e saída: `ler valor` e `Escreve:`".
- As regras do duelo de dados: [projeto 1, Duelo de dados](../01-algoritmos/projetos-guiados/05-projeto-1-duelo-de-dados.md), secção "O jogo".
- As funções e o que acontece numa chamada: guia [05 Funções e modelo integrado](../01-algoritmos/05-funcoes-e-modelo-integrado.md), secção "Chamar uma função".
- Os casos de teste e o resultado esperado, escrito antes de executar: [projeto 1](../01-algoritmos/projetos-guiados/05-projeto-1-duelo-de-dados.md), secção "Passo 2: a tabela de casos esperados, antes do algoritmo".
- A rotina da depuração, em cinco passos: [projeto 1](../01-algoritmos/projetos-guiados/05-projeto-1-duelo-de-dados.md), secção "Passo 6: depurar com a rotina da depuração".
- Criar uma pasta e guardar um ficheiro no computador, do dia a dia.

## Um programa é um algoritmo que o computador executa

Na algoritmia, fizeste muitas tabelas de trace à mão. São lentas, e é fácil enganarmo-nos numa conta ou saltar uma linha. Um computador executa milhões de instruções por segundo, sem se cansar e sem saltar linhas. Só tem uma exigência: as instruções têm de estar escritas numa forma que ele perceba.

Essa forma é uma **linguagem de programação**: uma maneira de escrever algoritmos com regras exatas, que o computador consegue executar. Um algoritmo escrito numa linguagem de programação chama-se **programa**. O Python é a linguagem que vais aprender agora.

Pensa numa receita. Escrita num caderno, com "uma pitada de sal", uma pessoa percebe-a. Uma máquina de cozinha só a segue se cada passo vier com a quantidade exata e pela ordem certa. O pseudocódigo é a receita para pessoas. O Python é a receita para a máquina.

Para o computador executar um programa em Python, é preciso outro programa, o **interpretador**. O interpretador lê o teu ficheiro do princípio ao fim e confirma que está bem escrito. Depois executa as instruções, uma a uma, de cima para baixo. Faz o trabalho que tu fazias na tabela de trace. Quando instalas "o Python" num computador, é o interpretador que instalas.

Um ficheiro com instruções em Python chama-se **script**. É um ficheiro de texto, como os outros, com o nome a acabar em `.py`, como `ola.py` ou `regras.py`.

Há uma diferença grande entre o pseudocódigo e o Python. No pseudocódigo, um algoritmo em frases claras era válido, e uma palavra com maiúscula a mais não mudava nada. O Python não aceita frases, e não adivinha o que quiseste dizer. Se faltar um sinal, o interpretador recusa o programa todo e diz em que linha encontrou o problema. A parte difícil continua a ser a mesma, a lógica. O que se acrescenta é escrever cada linha exatamente como a linguagem manda.

O Python foi criado por Guido van Rossum e publicado pela primeira vez em 1991. Estas são as características que mais vais notar:

- lê-se quase como inglês, e escreve-se com poucas linhas;
- os blocos marcam-se pela indentação, como no pseudocódigo das aulas;
- é gratuito, e corre em Windows, em macOS e em Linux;
- traz consigo uma coleção grande de funções já feitas, a **biblioteca padrão**.

Por isso, usa-se em muitas áreas. Usa-se na análise de dados e na inteligência artificial, e na parte dos sites que corre nos servidores. Usa-se também na ciência, no ensino e para automatizar tarefas repetitivas. Não é a melhor linguagem para tudo. Depois do Python vais aprender C, uma linguagem que deixa controlar o que o Python faz sozinho, como a memória. São ferramentas diferentes, como um alicate e um martelo, e cada uma serve melhor para certos trabalhos.

## Onde se escreve um programa

Antes de escrever um programa, é preciso saber onde o escrever. A resposta é mais simples do que parece: um script é só um ficheiro de texto. Qualquer programa que escreva texto simples, sem formatação, serve para o escrever. No Windows, o Bloco de Notas já serve. Escreves as linhas, guardas o ficheiro com um nome acabado em `.py`, e o interpretador consegue executá-lo.

**Texto simples** é texto só com os caracteres que escreveste: letras, algarismos, espaços, sinais e mudanças de linha. Não tem negrito, nem tipos de letra, nem cores guardadas no ficheiro.

Um processador de texto, como o Word, não serve, mesmo que o texto pareça certo no ecrã. Guarda o documento num formato próprio, com a formatação lá dentro, que o interpretador não sabe ler. E faz uma coisa que estraga o código sem se ver. Troca as aspas retas, `"`, por aspas curvas, `“` e `”`, que ficam mais bonitas num texto. Para o Python, as aspas curvas não são aspas.

Antes de leres o resultado, tenta prever: o que acontece quando o Python tenta correr esta linha, copiada de um documento do Word?

```python
print(“Olá”)
```

O programa não corre. Aparece esta mensagem:

```text
  File "C:\Users\aluno\Documents\fp-python\aspas.py", line 1
    print(“Olá”)
          ^
SyntaxError: invalid character '“' (U+201C)
```

Leitura guiada: lê a mensagem de baixo para cima. A última linha diz o que correu mal: "erro de sintaxe: carácter inválido". O sinal `^` aponta para a primeira aspa curva. O Python não a reconhece como o início de um texto, e recusa o programa inteiro. O `U+201C` é o número que identifica esse carácter, e podes ignorá-lo. A primeira linha diz em que ficheiro e em que linha está o problema. O caminho do ficheiro, a seguir a `File`, muda de computador para computador.

A regra é esta: escreve o código num programa feito para texto simples. Se copiares código de um documento ou de uma apresentação, confirma as aspas.

## Do editor de texto ao editor de código

O Bloco de Notas escreve texto simples, e por isso serve. Mas não ajuda em nada. Mostra o código todo da mesma cor e não mostra o número de cada linha ao lado do texto. Também não repara num parêntese que ficou por fechar. Num programa de três linhas não faz falta. Num programa de cinquenta, quando uma mensagem de erro diz "linha 37", faz.

Um **editor de código** é um editor de texto simples feito para escrever código. Guarda o ficheiro da mesma maneira, em texto simples, mas mostra-o de outra forma e ajuda enquanto escreves:

- pinta as partes do código com cores diferentes: os textos entre aspas de uma cor, as palavras do Python de outra, os comentários de outra. A isto chama-se **realce de sintaxe**. As cores não ficam guardadas no ficheiro: são só a forma de o editor to mostrar;
- mostra o número de cada linha, na margem da esquerda;
- fecha sozinho as aspas e os parênteses: quando escreves `(`, aparece logo o `)`;
- mantém a indentação: quando carregas em Enter numa linha recuada, a linha seguinte começa recuada.

As cores ajudam mais do que parece. Se uma aspa ficar por fechar, o resto da linha, e às vezes o resto do ficheiro, fica todo da cor dos textos. Vês o erro antes de correres o programa.

Nas aulas, o editor é o **VS Code**, de Visual Studio Code. É gratuito e usa-se em Windows, em macOS e em Linux.

## O ambiente de desenvolvimento integrado, o IDE

Para fazer um programa, não basta escrevê-lo. Também é preciso guardá-lo numa pasta, corrê-lo, ler as mensagens de erro, encontrar a linha que as causa e voltar a corrê-lo. Com um editor simples, cada uma destas coisas faz-se num sítio diferente: o editor numa janela, os ficheiros noutra, o terminal noutra. Passas o tempo a mudar de janela.

Um **ambiente de desenvolvimento integrado** é um programa que junta numa só janela tudo o que é preciso para escrever, correr e corrigir programas. Em inglês, diz-se *integrated development environment*. Chama-se, pelas iniciais em inglês, **IDE**. Um IDE tem, pelo menos:

- um editor de código;
- um explorador de ficheiros, para veres e criares os ficheiros do projeto;
- um **terminal**: uma janela onde escreves ordens para o computador, uma por linha. A cada ordem chama-se **comando**, como a ordem para correr um programa;
- ajuda para escrever, como as sugestões de palavras;
- ajuda para encontrar erros antes de correres o programa;
- um depurador, que corre o programa linha a linha e mostra os valores, para encontrares um erro.

"Integrado" quer dizer que estas ferramentas estão no mesmo sítio e trabalham em conjunto. O botão de correr sabe que ficheiro tens aberto. Um erro na lista dos problemas leva-te à linha onde ele está. O terminal abre-se na pasta do projeto, sem teres de a procurar.

Pensa numa oficina. Podes ter as ferramentas em gavetas espalhadas pela casa, e consegues arranjar uma bicicleta na mesma. Mas, se estiverem todas na mesma bancada, à mão, trabalhas mais depressa e enganas-te menos. O IDE é a bancada.

O VS Code, de origem, é um editor de código. Ganha o resto com **extensões**: programas pequenos que se acrescentam ao VS Code para lhe dar ferramentas novas. Com a extensão Python, da Microsoft, o VS Code passa a funcionar como um IDE para Python. Ganha o botão de correr, sugestões que conhecem as palavras do Python e o sublinhado dos erros. Há IDEs que já vêm completos, feitos para uma só linguagem. Nas aulas usa-se o VS Code, porque serve também para outras linguagens que vais usar no curso, como o C, ainda este ano.

Há uma coisa que o IDE não é: não é o Python. O VS Code e o interpretador do Python são dois programas diferentes, instalados à parte. Um computador com o VS Code e sem o Python deixa-te escrever scripts, mas não os consegue correr. É o erro típico da primeira semana: pensar que instalar o VS Code é instalar o Python.

## As ferramentas do VS Code

Quando abres uma pasta no VS Code, a janela divide-se em zonas, e cada zona tem uma ferramenta. Não precisas de as decorar. Precisas de saber que existem e para que servem, para as ires buscar quando fizerem falta. Esta tabela é para consultares:

| Ferramenta | Onde está | Para que serve |
| --- | --- | --- |
| Explorador (Explorer) | Painel da esquerda | Ver os ficheiros da pasta e criar ficheiros novos |
| Editor e separadores | Ao centro | Escrever o código; cada ficheiro aberto tem um separador |
| Números das linhas e cores | Na margem e no texto do editor | Encontrar a linha de que uma mensagem fala e ver o que é cada parte do código |
| Sugestões | Uma lista que aparece enquanto escreves | Escrever mais depressa e sem erros nos nomes |
| Sublinhado dos erros e painel dos problemas (Problems) | No editor e no painel de baixo | Ver um erro de escrita antes de correres o programa |
| Terminal integrado | No painel de baixo | Correr o programa e ver o que ele escreve |
| Botão de correr | No canto de cima, à direita do editor | Correr o ficheiro aberto, sem escreveres o comando |
| Depurador (Run and Debug) | Nos ícones da esquerda | Correr o programa linha a linha e ver os valores |
| Extensões (Extensions) | Nos ícones da esquerda | Acrescentar ferramentas ao VS Code, como a do Python |
| Barra de estado | Na faixa de baixo da janela | Ver em que linha está o cursor e que Python o VS Code vai usar |

O **explorador** mostra os ficheiros da pasta que abriste no VS Code, a pasta do projeto. É lá que crias um ficheiro novo e que o abres com um clique. A pasta abre-se uma vez, no menu File, com a opção Open Folder..., e o VS Code passa a trabalhar dentro dela.

O **editor** é a zona do centro, onde escreves. Cada ficheiro aberto tem um **separador** no topo, com o nome do ficheiro, como as abas de um browser. Repara no separador enquanto escreves. Quando há alterações por guardar, aparece uma bola cheia no lugar do X que o fecha. Guarda-se com Ctrl+S, ou Cmd+S no macOS, e a bola volta a ser um X.

Os **números das linhas** estão na margem da esquerda do editor. Quando o Python diz que há um erro na linha 5, é lá que olhas. As cores são o realce de sintaxe da secção anterior.

As **sugestões** aparecem enquanto escreves. Se escreveres `pri`, aparece uma lista com `print`, e carregas em Tab ou em Enter para o aceitar. Ajudam a não errar o nome de uma palavra. Mas sugerem o que existe, e não o que está certo para o teu problema: escolher continua a ser contigo.

O **sublinhado dos erros** é uma linha ondulada, debaixo do sítio onde o VS Code encontrou um erro de escrita, como um parêntese por fechar. O painel dos **problemas**, Problems, na parte de baixo da janela, faz a lista desses erros, com o número da linha de cada um. Um clique num problema leva-te à linha. Com a extensão Python, o VS Code costuma assinalar também os nomes que não conhece, como um `print` mal escrito. Usa um sublinhado de outra cor. É um aviso: o programa corre na mesma, até chegar a essa linha. O VS Code encontra os erros de escrita, e não os de raciocínio: um programa sem nenhum sublinhado pode fazer outra coisa do que querias.

O **terminal integrado** é um terminal dentro do VS Code, no painel de baixo. Abre-se no menu Terminal, com a opção New Terminal, e já abre dentro da pasta do projeto. É lá que corres os scripts e vês o que eles escrevem.

O **botão de correr** é um triângulo no canto de cima, à direita do editor. Corre o ficheiro que está no separador ativo, o que tens à frente, e mostra o resultado no terminal. A secção "Correr um script" explica-o melhor.

O **depurador** está num dos ícones da esquerda, Run and Debug. Corre o programa uma linha de cada vez e mostra o valor de cada variável a cada passo. É uma tabela de trace feita pelo computador. Os programas deste tema ainda não têm variáveis, por isso não precisas dele já. Vais usá-lo quando os programas tiverem variáveis e ciclos.

As **extensões** estão noutro ícone da esquerda, Extensions. É lá que se vê que extensões estão instaladas e que se procuram outras. Nos ficheiros `.py`, é a extensão Python que dá o botão de correr, as sugestões do Python e o sublinhado dos erros.

A **barra de estado** é a faixa estreita no fundo da janela. Mostra a linha e a coluna onde está o cursor, como `Ln 3, Col 12`, e a linguagem do ficheiro aberto, `Python`. Com a extensão Python, mostra também a versão do Python que o VS Code vai usar para correr os teus scripts.

Se o VS Code do teu computador não tiver a extensão Python, continua a servir para escrever e guardar os scripts. Corres os scripts no terminal. Ficas sem o botão de correr e sem o sublinhado dos erros, e as sugestões só propõem palavras que já estão no ficheiro.

## Correr um script

Para correr um script, o interpretador tem de receber uma ordem: "executa este ficheiro". Essa ordem dá-se no terminal, com um comando: escreves a ordem numa linha e carregas em Enter. No VS Code, o terminal abre-se no menu Terminal, com a opção New Terminal, isto é, "novo terminal". Abre-se na parte de baixo da janela, já dentro da pasta que tens aberta.

Para correr um script, escreve-se no terminal a palavra `python`, um espaço e o nome do ficheiro. Nos computadores da escola, que são Windows, o comando é este:

```bash
python ola.py
```

Se o Windows responder que não conhece o `python`, experimenta `py ola.py`, que faz o mesmo. No macOS e no Linux, o comando é `python3 ola.py`.

Antes de correres este primeiro exemplo, tenta prever: o que aparece no terminal, e por que ordem?

```python
# ola.py: o primeiro script, para confirmar que o Python corre neste computador.
print("Olá, Python!")
print("O meu primeiro script correu.")
```

O resultado é este:

```text
Olá, Python!
O meu primeiro script correu.
```

Leitura guiada: o interpretador começa na primeira linha e desce. A primeira linha começa com `#`, e por isso é um comentário, uma nota para quem lê, que o Python ignora. A secção dos comentários explica-os melhor. A segunda linha escreve o texto que está entre aspas, e a terceira escreve o outro. As aspas não aparecem no ecrã, porque só servem para dizer onde o texto começa e acaba.

Quando carregas em Enter, acontece isto, por esta ordem:

1. O terminal recebe o comando e põe o interpretador do Python a trabalhar.
2. O interpretador procura o ficheiro `ola.py` na pasta onde o terminal está.
3. Lê o ficheiro todo e confirma que está bem escrito, segundo as regras do Python.
4. Executa as instruções uma a uma, de cima para baixo.
5. Quando acaba a última instrução, o programa termina, e o terminal fica outra vez à espera de um comando.

Há um cuidado que vale para todos os scripts. O interpretador lê o ficheiro que está guardado no disco, e não o que está no ecrã. Se mudares o código e não o guardares, corres a versão antiga. Guarda sempre antes de correr.

### Com o botão de correr

Com a extensão Python, há uma segunda forma de correr um script: o botão de correr. É o triângulo no canto de cima, à direita do editor. Corre o ficheiro do separador ativo, e o resultado aparece no terminal, como com o comando.

Repara no que aparece no terminal quando carregas no botão. Antes do resultado, aparece uma linha comprida, que tu não escreveste. Tem o caminho completo do interpretador do Python, um espaço e o caminho completo do teu ficheiro. É o mesmo comando que escreverias, `python ola.py`, só que com os caminhos inteiros, para não haver dúvidas sobre que Python e que ficheiro usar. O botão escreve o comando por ti. No Windows, essa linha começa por `&`, que é a forma de o terminal do Windows correr um programa pelo caminho completo.

As duas formas dão o mesmo resultado. O botão é mais rápido. O comando funciona em qualquer computador com o Python, mesmo sem o VS Code, e é por isso que vale a pena sabê-lo escrever.

## A consola do Python, para experimentar uma linha

Às vezes só queres saber o que faz uma linha. Para isso não precisas de criar um ficheiro. Escreve no terminal só a palavra `python`, sem nome de ficheiro, e carrega em Enter. No macOS, é `python3`. Abre-se a **consola do Python**, que mostra `>>>` e fica à espera de uma linha.

Escreves uma linha, carregas em Enter, e o Python executa-a logo e mostra o resultado. Antes de leres o resultado, tenta prever o que aparece a seguir a cada uma destas linhas:

```text
>>> print("Olá da consola")
Olá da consola
>>> 2 + 3
5
```

Leitura guiada: cada linha que começa por `>>>` foi escrita por ti. Cada linha sem `>>>` foi escrita pelo Python, em resposta à linha de cima. A primeira tem um `print`, e o texto aparece como num script. A segunda é uma conta sem `print`, e o resultado aparece na mesma: na consola, o Python mostra sozinho o valor de cada linha. Num script, isso não acontece, e só o `print` escreve no ecrã. As contas em Python são do tema seguinte. Aqui, a conta só mostra que a consola responde logo.

O que escreves na consola não fica guardado em lado nenhum. Quando sais, perde-se. Por isso, a consola serve para experimentar, e o programa a sério escreve-se num ficheiro. Para sair, escreve `exit()` e carrega em Enter.

O erro típico é esquecer onde se está. Se escreveres `python ola.py` dentro da consola, a seguir ao `>>>`, aparece `SyntaxError: invalid syntax`, isto é, "erro de sintaxe: escrita inválida". A consola espera uma linha de Python, e `python ola.py` é um comando do terminal. A regra que evita a confusão é esta: com `>>>`, escreves Python; sem `>>>`, escreves comandos. Sai com `exit()` e escreve o comando no terminal.

As mensagens de erro deste guia são as do Python 3.14. Numa versão mais antiga, algumas têm outras palavras, ou apontam a linha seguinte. O tipo de erro, a palavra antes dos dois pontos, é o mesmo.

## Quando é preciso um IDE, e quando não

Um IDE ajuda muito, mas não é obrigatório, e nem sempre é a melhor escolha. Para escolher a ferramenta, pergunta-te o que vais fazer.

Para experimentar uma linha, ou saber o que faz uma instrução, chega a consola do Python, da secção anterior. Não é preciso criar um ficheiro.

Para mudar uma palavra num ficheiro de texto que já existe, chega qualquer editor de texto simples. Abrir um IDE para isso é como ligar a máquina de lavar para lavar um copo.

Para escrever um programa com várias linhas, corrê-lo muitas vezes e corrigir erros, o IDE poupa tempo e erros. É o que vais fazer nas aulas, e por isso usas o VS Code.

Para procurar um erro difícil num programa grande, o IDE é quase indispensável, por causa do depurador.

| O que vais fazer | O que te chega |
| --- | --- |
| Experimentar uma linha ou uma conta | A consola do Python |
| Ver que versão do Python tens | O terminal, com o comando `python --version` |
| Corrigir uma palavra num ficheiro | Qualquer editor de texto simples |
| Escrever e testar um programa | Um IDE, como o VS Code com a extensão Python |
| Encontrar um erro num programa grande | Um IDE, com o depurador |

Há três coisas que vale a pena saber sobre os IDEs.

A primeira é que um programa não precisa de um IDE para correr. Um script escrito no Bloco de Notas e corrido no terminal dá exatamente o mesmo resultado. O IDE ajuda quem escreve, e não muda o que o programa faz.

A segunda é que um IDE é um programa pesado. Demora mais a abrir do que um editor simples e gasta mais memória. Num computador lento, ou para uma mudança pequena, um editor simples é mais rápido.

A terceira é que o IDE não pensa por ti. As sugestões propõem nomes que existem, e o sublinhado apanha erros de escrita. Nenhum dos dois sabe o que o teu programa devia fazer. Um programa sem nenhum erro sublinhado pode estar errado, e só os casos de teste o mostram, como na algoritmia.

## Escrever no ecrã com `print`

O `Escreve:` do pseudocódigo passa a `print`, com o que se quer mostrar entre parênteses. Os parênteses estão lá porque o `print` é uma **função** que vem com o Python. Uma função é um pedaço de programa já feito, a que dás valores entre parênteses, e que faz um trabalho com eles. O trabalho do `print` é escrevê-los no ecrã.

Tal como no pseudocódigo, o que está entre aspas aparece tal e qual. A um texto entre aspas chama-se, em Python, **string**, a mesma palavra do pseudocódigo. No Python, um texto pode ir entre aspas duplas, `"Olá"`, ou simples, `'Olá'`. Nas aulas usamos as duplas.

Um número escreve-se sem aspas, como `5` ou `120`. Sem aspas, só podes escrever números, por agora. Como no pseudocódigo, uma palavra sem aspas é o nome de uma variável. As variáveis em Python são do tema seguinte. Por agora, se não houver nenhuma variável com esse nome, o programa para com um `NameError`. É o erro de nome, que vais ver em "Os três tipos de erro".

Para mostrar vários valores na mesma linha, separam-se por vírgulas, como no pseudocódigo. Há uma diferença: o `print` põe sozinho um espaço entre cada dois valores. No pseudocódigo eras tu que punhas os espaços dentro das aspas.

Antes de correres este exemplo, tenta prever: o que escreve cada um dos dois primeiros `print`, e o que faz o terceiro?

```python
# espacos.py: a mesma frase escrita de duas maneiras, para comparar os espaços.
print("Passaram", 2, "horas")
print("Passaram ", 2, " horas")
print()
print("Fim do jogo")
```

O resultado é este:

```text
Passaram 2 horas
Passaram  2  horas

Fim do jogo
```

Leitura guiada: o primeiro `print` recebe três valores, o texto "Passaram", o número 2 e o texto "horas". Escreve-os com um espaço entre cada dois. O segundo recebe os mesmos três valores, mas os textos já trazem espaços dentro das aspas. O `print` acrescenta os seus, e ficam dois espaços seguidos de cada lado do 2. O terceiro `print` não tem nada entre os parênteses, e escreve uma linha em branco. O quarto escreve o texto.

É o erro típico de quem traduz o pseudocódigo à letra: copiar os espaços de dentro das aspas. No Python, deixa os espaços de fora e deixa o `print` pô-los.

Um `print()` vazio serve para separar partes do que aparece no ecrã, como os parágrafos de um texto. No pseudocódigo não te preocupavas com isso. No ecrã de um programa, as linhas em branco ajudam quem o usa a ler.

Cada `print` acaba a linha. O `print` seguinte começa sempre numa linha nova, mesmo que o texto anterior tenha sido curto.

## Comentários: notas para quem lê o código

Um programa não é lido só pelo computador. Também o leem pessoas: tu, uma semana depois, o professor, ou um colega que te ajuda a encontrar um erro. Por isso, às vezes, é preciso explicar a essas pessoas o que uma parte do programa faz, ou porquê.

Um **comentário** é uma nota para quem lê o código, que o Python ignora. Começa com o sinal `#` e vai até ao fim da linha. Pode ocupar uma linha inteira ou vir no fim de uma linha de código.

Antes de correres este exemplo, tenta prever: quantas linhas aparecem no ecrã?

```python
# comentarios.py: mostra as duas formas de escrever um comentário.

# Esta linha inteira é um comentário.
print("Primeira linha")  # Este comentário vem no fim de uma linha de código.
# print("Esta linha não aparece, porque começa com #.")
print("Segunda linha")
```

O resultado são duas linhas:

```text
Primeira linha
Segunda linha
```

Leitura guiada: o Python lê o ficheiro de cima para baixo e salta tudo o que vem depois de um `#`. A linha 1 e a linha 3 são só comentários. A linha 2, em branco, não faz nada. Uma linha em branco no ficheiro não escreve nada no ecrã: só um `print()` escreve uma linha em branco. Na quarta linha, executa o `print` e salta o comentário que vem a seguir. A quinta linha tem um `print`, mas começa com `#`, e por isso é um comentário inteiro: não se executa. Só a quarta e a sexta escrevem no ecrã.

A quinta linha mostra um uso prático: pôr um `#` no início de uma linha de código desliga-a, sem a apagar. Quando procuras um erro, serve para experimentar o programa sem uma linha e voltar a ligá-la depois. No VS Code, o menu Edit, com a opção Toggle Line Comment, põe ou tira o `#` da linha onde está o cursor.

Nas aulas, há uma convenção: a primeira linha de cada script é um comentário com o nome do ficheiro e o que ele faz. Quem abrir o ficheiro uma semana depois percebe logo para que serve. Um bom comentário diz o que não se vê no código, como o porquê de uma escolha. Um comentário que repete o código, como `# escreve Olá` por cima de `print("Olá")`, não acrescenta nada.

## Os três tipos de erro

Quando um programa falha, o primeiro passo é dizer que tipo de erro é. Há três, e cada um aparece de maneira diferente.

Um **erro de sintaxe** acontece quando o código não cumpre as regras da linguagem: falta uma aspa, um parêntese ou uma vírgula. A **sintaxe** são as regras de escrita de uma linguagem. O Python recusa o programa antes de executar qualquer linha, e nada aparece no ecrã além da mensagem. Antes de leres o resultado, tenta prever: o que aparece no ecrã, se ao segundo `print` faltar a aspa que fecha o texto?

```python
# erro_sintaxe.py: ao segundo print falta a aspa que fecha o texto.
print("Olá, Python!")
print("O meu primeiro script correu.)
```

Aparece só a mensagem:

```text
  File "C:\Users\aluno\Documents\fp-python\erro_sintaxe.py", line 3
    print("O meu primeiro script correu.)
          ^
SyntaxError: unterminated string literal (detected at line 3)
```

Leitura guiada: a mensagem quer dizer "erro de sintaxe: texto por terminar, detetado na linha 3". O `^` aponta para a aspa que abre o texto que não foi fechado. Repara que o "Olá, Python!" da linha 2, que estava certa, também não apareceu. Antes de executar, o interpretador lê o ficheiro todo e confirma que está bem escrito. Ao encontrar um erro de sintaxe, recusa o programa inteiro, também as linhas que estão antes do erro.

Um **erro de execução** acontece quando o código está bem escrito, mas uma linha não se consegue executar. O programa corre até essa linha e para a meio. A estes erros o Python chama **exceções**. Antes de leres o resultado, tenta prever: neste script, que linhas aparecem no ecrã?

```python
# erro_execucao.py: a quarta linha tem o nome print mal escrito.
print("Primeira linha")
print("Segunda linha")
prnt("Terceira linha")
print("Quarta linha")
```

Aparecem as duas primeiras linhas, e depois a mensagem:

```text
Primeira linha
Segunda linha
Traceback (most recent call last):
  File "C:\Users\aluno\Documents\fp-python\erro_execucao.py", line 4, in <module>
    prnt("Terceira linha")
    ^^^^
NameError: name 'prnt' is not defined. Did you mean: 'print'?
```

Leitura guiada: desta vez, as linhas 2 e 3 executaram-se, e as duas primeiras frases apareceram. O programa estava bem escrito, por isso o interpretador começou a executá-lo. Parou na linha 4, porque não conhece nenhuma função chamada `prnt`. A mensagem de uma exceção começa por `Traceback (most recent call last)`, isto é, "o rasto, com a chamada mais recente no fim", e lê-se de baixo para cima. A última linha diz o tipo de erro e o que aconteceu: "erro de nome: o nome `prnt` não está definido. Querias dizer `print`?". A linha de cima mostra a instrução, com os sinais `^` debaixo do nome errado. A linha do `File` diz o ficheiro e a linha. A quarta frase nunca apareceu, porque o programa já tinha parado.

No VS Code com a extensão Python, o `prnt` pode aparecer sublinhado antes de correres. Quem decide o tipo de erro é o momento em que o Python dá por ele, e não o VS Code. Aqui, o Python só dá pelo erro quando chega à linha 4, e por isso é um erro de execução.

Para o Python, um nome com uma letra a menos, ou com uma maiúscula trocada, como `Print`, é outro nome, que não existe. A sugestão do fim da mensagem costuma acertar.

Um **erro de lógica** acontece quando o programa corre até ao fim, sem mensagem nenhuma, mas faz outra coisa do que devia. Imagina que o ecrã de um jogo devia dizer "Tens 10 tentativas", e o programa escreve "Tens 7 tentativas". O Python não dá por nada, porque não sabe o que querias. Só encontras o erro se comparares o que o programa mostra com o que devia mostrar, linha a linha. Por isso, antes de correres um programa, escreves o resultado que esperas, como fazias na algoritmia com os casos de teste.

| Tipo de erro | Quando o Python dá por ele | O que aparece |
| --- | --- | --- |
| De sintaxe | Antes de executar qualquer linha | Só a mensagem, com `SyntaxError` |
| De execução | Na linha que não se consegue executar | O que as linhas anteriores escreveram, e a mensagem que começa por `Traceback` |
| De lógica | Nunca | O programa acaba, mas o resultado é diferente do esperado |

Há uma regra que vale para os erros de execução e para os de sintaxe. A linha que a mensagem aponta é onde o Python deu pelo problema, e a causa pode estar antes. Num Python mais antigo, um parêntese por fechar fazia o Python queixar-se só da linha seguinte. Nos temas seguintes, com as variáveis, vais ver erros cuja causa está umas linhas acima da linha apontada. A mensagem é uma pista, e não a resposta.

Quando um programa teu falha, segue sempre a mesma rotina, a da algoritmia, agora com o computador:

1. **Observar e reproduzir o erro.** Escreve o resultado esperado, tirado do enunciado, e o resultado obtido. Diz também que tipo de erro é: de sintaxe, de execução ou de lógica.
2. **Formular uma hipótese.** Escreve numa frase o que achas que causa o erro.
3. **Verificar a hipótese.** Lê a mensagem e a linha que ela aponta, e a linha de cima. Num erro de lógica, compara o ecrã obtido com o esperado, linha a linha, até encontrares a primeira diferença.
4. **Corrigir a causa.** Muda a instrução que produz o erro, e não o sítio onde ele se vê.
5. **Voltar a testar tudo.** Corre outra vez o programa e confirma o ecrã inteiro, também as linhas que já estavam certas.

## O Python 3 e o código antigo

As linguagens de programação também têm versões, como as aplicações do telemóvel. O Python 2 saiu em 2000 e o Python 3 em 2008. O Python 3 mudou várias coisas, e muitos programas escritos para o Python 2 não correm no Python 3. O Python 2 deixou de ser mantido no início de 2020, e hoje usa-se só o Python 3.

Na internet, em livros antigos e em respostas de fóruns, ainda há muito código escrito para o Python 2. O sinal mais fácil de reconhecer está no `print`, que no Python 2 se escrevia sem parênteses:

| No Python 2 | No Python 3 |
| --- | --- |
| `print "Olá"` | `print("Olá")` |

Antes de leres a resposta, tenta prever: o Python 3 aceita a linha `print "Olá"`?

Não aceita. Aparece um erro de sintaxe, e o Python 3 até diz o que se passa:

```text
SyntaxError: Missing parentheses in call to 'print'. Did you mean print(...)?
```

Quer dizer "erro de sintaxe: faltam os parênteses na chamada ao `print`. Querias dizer `print(...)`?". No tema seguinte, com a leitura do teclado e as contas, vais conhecer mais dois sinais do código antigo.

Dentro do Python 3 também há versões, numeradas 3.12, 3.13, 3.14 e assim por diante. Cada uma acrescenta coisas, e as mensagens de erro ficam mais claras de versão para versão. Para saberes que versão tens, escreve no terminal:

```bash
python --version
```

No macOS, o comando é `python3 --version`. Aparece uma linha como `Python 3.13.2`. O primeiro número tem de ser 3. Com a extensão Python, a versão aparece também na barra de estado do VS Code.

## Exemplo guiado: o ecrã das regras do duelo de dados

### Passo 1: o problema

No projeto 1 da algoritmia, escreveste o algoritmo do duelo de dados. Antes de um jogo começar, os jogadores precisam de saber as regras. Queremos um programa que escreva no ecrã exatamente isto:

```text
DUELO DE DADOS
Um jogo para dois jogadores.

Máximo de rondas: 5
Vitórias para ganhar: 3

Regras:
1. Em cada ronda, cada jogador escolhe um número de 1 a 6.
2. Quem escolher o número maior ganha a ronda.
3. Se os dois escolherem o mesmo número, a ronda fica empatada.
4. O duelo acaba quando um jogador ganha 3 rondas, ou depois da ronda 5.
5. Ganha o duelo quem ganhou mais rondas.

Boa sorte!
```

Este é o resultado esperado. Vai servir para confirmar o programa no fim, linha a linha.

### Passo 2: o pseudocódigo

Em pseudocódigo, o ecrã escreve-se com um `Escreve:` por linha:

```text
Escreve: "DUELO DE DADOS"
Escreve: "Um jogo para dois jogadores."
Escreve: "Máximo de rondas: ", 5
Escreve: "Vitórias para ganhar: ", 3
Escreve: "Regras:"
Escreve: "1. Em cada ronda, cada jogador escolhe um número de 1 a 6."
Escreve: "2. Quem escolher o número maior ganha a ronda."
Escreve: "3. Se os dois escolherem o mesmo número, a ronda fica empatada."
Escreve: "4. O duelo acaba quando um jogador ganha 3 rondas, ou depois da ronda 5."
Escreve: "5. Ganha o duelo quem ganhou mais rondas."
Escreve: "Boa sorte!"
```

Repara que o pseudocódigo não tem as linhas em branco do ecrã. No pseudocódigo, o que interessava era o conteúdo. No programa, as linhas em branco fazem parte do ecrã que se quer.

### Passo 3: traduzir instrução a instrução

Cada tipo de linha tem a sua tradução:

| No pseudocódigo | No Python | O que muda |
| --- | --- | --- |
| `Escreve: "DUELO DE DADOS"` | `print("DUELO DE DADOS")` | o texto vai entre parênteses |
| `Escreve: "Máximo de rondas: ", 5` | `print("Máximo de rondas:", 5)` | sem o espaço dentro das aspas, porque o `print` põe-no |
| não havia | `print()` | uma linha em branco, que o ecrã pede |
| não havia | `# comentário` | uma nota para quem lê o código |

Onde ficam as linhas em branco? O ecrã esperado tem três: depois da apresentação, depois dos números e antes do "Boa sorte!". São três `print()`.

### Passo 4: o script completo

Os comentários separam o programa em partes, para se ler melhor:

```python
# regras_duelo.py: escreve no ecrã as regras do duelo de dados, o jogo do projeto 1.

# O título e a apresentação do jogo.
print("DUELO DE DADOS")
print("Um jogo para dois jogadores.")
print()

# Os números do jogo, cada um a seguir à sua frase.
print("Máximo de rondas:", 5)
print("Vitórias para ganhar:", 3)
print()

# As regras, uma por linha.
print("Regras:")
print("1. Em cada ronda, cada jogador escolhe um número de 1 a 6.")
print("2. Quem escolher o número maior ganha a ronda.")
print("3. Se os dois escolherem o mesmo número, a ronda fica empatada.")
print("4. O duelo acaba quando um jogador ganha 3 rondas, ou depois da ronda 5.")
print("5. Ganha o duelo quem ganhou mais rondas.")
print()
print("Boa sorte!")
```

Leitura guiada: o interpretador executa as linhas de cima para baixo e salta as que começam por `#`. Cada `print` escreve uma linha do ecrã, pela ordem em que está no ficheiro. Nas duas linhas dos números, o `print` recebe dois valores, um texto e um número, e escreve-os com um espaço entre eles. Os três `print()` vazios dão as três linhas em branco.

### Passo 5: correr e comparar com o resultado esperado

Antes de correres, conta quantas linhas o programa deve escrever no ecrã, contando as linhas em branco. Depois corre-o, com `python regras_duelo.py`, ou com o botão de correr. O ecrã é igual ao do passo 1: catorze linhas, três delas em branco.

Comparar "parece igual" não chega. Compara linha a linha, de cima para baixo: o texto, os números, os espaços e as linhas em branco. Um programa pode ter um erro de lógica numa só palavra.

### Passo 6: encontrar um erro de lógica

Imagina que, na primeira versão, as duas linhas dos números estavam assim:

```python
print("Máximo de rondas:", 3)
print("Vitórias para ganhar:", 5)
```

O programa corre sem nenhuma mensagem de erro, e nenhuma linha fica sublinhada no VS Code. Mas o ecrã diz "Máximo de rondas: 3" e "Vitórias para ganhar: 5". A rotina da depuração encontra-o:

1. Observar: o esperado é "Máximo de rondas: 5"; o obtido é "Máximo de rondas: 3". O programa acabou sem mensagem, e por isso é um erro de lógica.
2. Hipótese: os dois números estão trocados entre as duas linhas.
3. Verificar: a linha do `print("Máximo de rondas:", 3)` tem o 3, que é o número das vitórias.
4. Corrigir a causa: trocar os dois números, cada um para a sua frase.
5. Voltar a testar tudo: correr outra vez e comparar as catorze linhas, e não só as duas que mudaram.

O computador executou exatamente o que estava escrito. Quem sabia o que o ecrã devia mostrar eras tu.

## Erros frequentes

Os erros desta secção não ficaram em nenhuma das secções anteriores. Para cada um, ficas a saber o que aparece, porque acontece e como se corrige. Os outros estão na secção da ideia que explicam:

- as aspas curvas, copiadas de um processador de texto, em "Onde se escreve um programa";
- o `python ola.py` escrito dentro da consola, em "A consola do Python, para experimentar uma linha";
- os espaços a dobrar no `print`, em "Escrever no ecrã com `print`";
- a aspa por fechar e o nome mal escrito, em "Os três tipos de erro".

### O programa corre e não escreve nada

O que se vê: corres um script que tem várias linhas, e não aparece nada no ecrã, nem nenhuma mensagem de erro. Por exemplo, este:

```python
# saudacao.py: devia escrever duas linhas.
Escreve: "Olá"
Escreve: "Adeus"
```

Acontece quando o `Escreve:` do pseudocódigo fica no programa. Por coincidência, o Python aceita uma palavra seguida de dois pontos e de um texto. É uma forma de escrever outra coisa, que não vais usar nas aulas. O Python não dá erro, e também não escreve nada. Corrige-se trocando cada `Escreve:` por um `print`, com o texto entre parênteses.

### Correr a versão antiga do ficheiro

O que se vê: corriges o código, voltas a correr, e aparece o mesmo erro, ou o mesmo resultado errado, como se nada tivesse mudado.

Acontece quando o ficheiro não foi guardado depois da alteração. O interpretador corre o ficheiro que está no disco. Corrige-se guardando com Ctrl+S, ou Cmd+S no macOS, antes de correr. No VS Code, a bola cheia no separador do ficheiro, no lugar do X, avisa que há alterações por guardar.

### O Python não encontra o ficheiro

O que se vê, ao escrever `python ola.py`:

```text
can't open file 'C:\\Users\\aluno\\Documents\\ola.py': [Errno 2] No such file or directory
```

Antes desta parte, a mensagem mostra o caminho do interpretador, que muda de computador para computador. Quer dizer "não consigo abrir o ficheiro: não existe esse ficheiro nem essa pasta". Acontece por uma de duas razões. Ou o terminal está noutra pasta, e não na do projeto, ou o nome do ficheiro no comando está diferente do nome verdadeiro. Corrige-se assim. Confirma que o texto antes do cursor do terminal acaba na pasta do projeto. Confirma também que o nome no comando é igual ao do explorador do VS Code, com o `.py`. Se o terminal estiver na pasta errada, fecha-o e abre outro, no menu Terminal, com a opção New Terminal. O terminal novo abre-se na pasta que tens aberta no VS Code.

### O ficheiro guardado como `ola.py.txt`

O que se vê: escreveste o script no Bloco de Notas e guardaste-o com o nome `ola.py`. Mas o Python diz que não encontra o ficheiro, como no erro anterior.

Acontece porque o Bloco de Notas pode acrescentar `.txt` ao nome, quando o tipo do ficheiro está em "Documentos de texto". O ficheiro chama-se, afinal, `ola.py.txt`, e o Windows pode esconder o `.txt` no explorador de ficheiros. Corrige-se guardando outra vez, com o tipo "Todos os ficheiros", ou mudando o nome do ficheiro. O VS Code não tem este problema: o nome que escreves no explorador é o nome do ficheiro.

## Palavras novas deste guia

- Linguagem de programação: uma maneira de escrever algoritmos com regras exatas, que o computador consegue executar.
- Programa: um algoritmo escrito numa linguagem de programação.
- Interpretador: o programa que lê um script em Python, confirma que está bem escrito e executa as instruções por ordem.
- Script: um ficheiro de texto com instruções em Python, com o nome a acabar em `.py`.
- Biblioteca padrão: a coleção de funções já feitas que vem com o Python.
- Texto simples: texto só com os caracteres escritos, sem formatação guardada no ficheiro.
- Editor de código: um editor de texto simples feito para escrever código, com cores, números de linha e ajudas à escrita.
- Realce de sintaxe: as cores com que um editor de código mostra as partes do código; não ficam guardadas no ficheiro.
- IDE, ambiente de desenvolvimento integrado: um programa que junta numa só janela as ferramentas para escrever, correr e corrigir programas.
- Extensão: um programa pequeno que se acrescenta ao VS Code para lhe dar ferramentas novas, como a extensão Python.
- VS Code: o editor de código das aulas, que, com a extensão Python, funciona como um IDE para Python.
- Explorador: o painel do VS Code que mostra os ficheiros da pasta do projeto.
- Separador: o sítio no topo do editor com o nome de um ficheiro aberto; uma bola cheia avisa que há alterações por guardar.
- Sugestões: a lista de palavras que o VS Code propõe enquanto escreves.
- Painel dos problemas: a lista dos erros de escrita que o VS Code encontrou, com a linha de cada um.
- Depurador: a ferramenta que corre o programa linha a linha e mostra os valores, como uma tabela de trace.
- Barra de estado: a faixa no fundo da janela do VS Code, com a linha do cursor, a linguagem e a versão do Python.
- Terminal: uma janela onde se escrevem comandos para o computador, um por linha.
- Comando: uma ordem escrita no terminal, como `python ola.py`.
- Botão de correr: o triângulo do VS Code que corre o ficheiro aberto e escreve o comando por ti.
- Consola do Python: o modo em que o Python executa uma linha de cada vez e mostra logo o resultado, a seguir ao `>>>`.
- Função: um pedaço de programa já feito, a que dás valores entre parênteses e que faz um trabalho com eles, como o `print`.
- `print`: a função que escreve valores no ecrã, com um espaço entre cada dois; vazia, escreve uma linha em branco.
- String: um texto entre aspas.
- Comentário: uma nota para quem lê o código, a seguir a `#`, que o Python ignora.
- Sintaxe: as regras de escrita de uma linguagem.
- Erro de sintaxe: um erro na escrita do código, que faz o Python recusar o programa antes de executar qualquer linha.
- Erro de execução, ou exceção: um erro que para o programa a meio, numa linha que não se consegue executar.
- Erro de lógica: um erro que não dá mensagem nenhuma; o programa corre e faz outra coisa do que devia.
- Traceback: a mensagem de um erro de execução, que se lê de baixo para cima.
- Python 2: a versão antiga do Python, que já não se usa, e cujo código muitas vezes não corre no Python 3.

## Verificar o que aprendeste

Usa estas perguntas para te testares. Responde a cada uma sem olhar para o guia. Se não conseguires, volta à secção que explica a ideia.

1. O que faz o interpretador quando corres `python ola.py`?
2. Porque é que o Word não serve para escrever um script, e o Bloco de Notas serve?
3. Diz três coisas que um editor de código faz e o Bloco de Notas não faz.
4. O que quer dizer "integrado", em "ambiente de desenvolvimento integrado"? Dá um exemplo de duas ferramentas do VS Code que trabalham em conjunto.
5. Um colega instalou o VS Code em casa, escreveu um script e não o consegue correr. O que pode faltar?
6. Para cada tarefa, diz se usas a consola, um editor simples ou o IDE. Primeiro, saber o que escreve `print("A", 1)`. Depois, mudar uma palavra num ficheiro de texto. Por fim, escrever um programa com vinte linhas e testá-lo.
7. O que acontece no terminal quando carregas no botão de correr do VS Code? Porque é que vale a pena saber escrever o comando na mesma?
8. O que escreve `print("Vidas:", 3)`? E `print("Vidas: ", 3)`? E `print()`?
9. Para que serve um comentário? O que acontece a uma linha de código que começa por `#`?
10. Diz que tipo de erro é cada um. Primeiro, o programa não escreve nada e aparece `SyntaxError`. Depois, o programa escreve duas linhas e para com `NameError`. Por fim, o programa acaba, mas o ecrã diz um número errado.
11. Num programa com um erro de sintaxe na última linha, as primeiras linhas executam-se? E com um erro de execução na última linha?
12. Viste numa página da internet a linha `print "Olá"`. Que versão do Python é, e como fica no Python 3?

## O que vem a seguir

Para praticar este tema, faz o [laboratório](laboratorios/01-do-pseudocodigo-ao-python-laboratorio.md). Nele preparas a pasta do projeto, conheces as ferramentas do VS Code uma a uma e escreves o ecrã de abertura de um jogo. Depois faz a [ficha de exercícios](exercicios/01-do-pseudocodigo-ao-python-exercicios.md), com ecrãs para prever e para traduzir, a escolha da ferramenta certa e erros para encontrar.

O tema seguinte é [Dados e interação](02-dados-e-interacao.md). Os programas deste tema escreveram sempre o mesmo ecrã. No tema seguinte, vão guardar valores em variáveis, fazer contas e ler o que a pessoa escreve no teclado.

![Rodapé](../imagens/rodape.png)
