![Cabeçalho](../imagens/cabecalho.png)

# Do pseudocódigo ao Python

Neste guia, ficas a saber onde se escreve um programa e com que ferramentas, e escreves e corres os teus primeiros scripts em Python. Na algoritmia, quem executava os algoritmos eras tu. A partir de agora, é o computador.

Usa o pseudocódigo da algoritmia. Rever: [Entrada e saída](../01-algoritmos/02-estado-sequencia-representacoes.md#entrada-e-saída-ler-valor-e-escreve) e [Tabela de trace](../01-algoritmos/02-estado-sequencia-representacoes.md#tabela-de-trace). Para praticar: [laboratório](laboratorios/01-do-pseudocodigo-ao-python-laboratorio.md) e [ficha de exercícios](exercicios/01-do-pseudocodigo-ao-python-exercicios.md).

## Neste guia

**As ferramentas**

1. [Um programa é um algoritmo que o computador executa](#um-programa-é-um-algoritmo-que-o-computador-executa)
2. [Um script escreve-se em texto simples](#um-script-escreve-se-em-texto-simples)
3. [Um editor de código ajuda enquanto escreves](#um-editor-de-código-ajuda-enquanto-escreves)
4. [Um IDE junta as ferramentas numa janela](#um-ide-junta-as-ferramentas-numa-janela)
5. [As ferramentas do VS Code](#as-ferramentas-do-vs-code)
6. [Correr um script](#correr-um-script)
7. [O botão de correr escreve o comando por ti](#o-botão-de-correr-escreve-o-comando-por-ti)
8. [A consola do Python experimenta uma linha](#a-consola-do-python-experimenta-uma-linha)
9. [Quando é preciso um IDE, e quando não](#quando-é-preciso-um-ide-e-quando-não)

**O Python**

10. [Escrever no ecrã com `print`](#escrever-no-ecrã-com-print)
11. [Os comentários são notas para quem lê o código](#os-comentários-são-notas-para-quem-lê-o-código)
12. [Os três tipos de erro](#os-três-tipos-de-erro)
13. [O Python 3 e o código antigo](#o-python-3-e-o-código-antigo)
14. [Exemplo guiado: o ecrã das regras do duelo de dados](#exemplo-guiado-o-ecrã-das-regras-do-duelo-de-dados)

## Um programa é um algoritmo que o computador executa

Um computador executa milhões de instruções por segundo, sem saltar linhas, mas as instruções têm de estar numa forma que ele perceba. Uma linguagem de programação é uma maneira de escrever algoritmos com regras exatas, e um algoritmo escrito nela é um programa. A linguagem que vais aprender agora é o Python.

Para executar um programa em Python, é preciso outro programa, o **interpretador**. Lê o teu ficheiro, confirma que está bem escrito e executa as instruções, de cima para baixo. Faz o trabalho que tu fazias na tabela de trace. Um ficheiro com instruções em Python chama-se **script**, e o nome acaba em `.py`, como `ola.py`.

O pseudocódigo aceitava frases claras. O Python não adivinha o que quiseste dizer: se faltar um sinal, recusa o programa e diz em que linha encontrou o problema.

O Python foi publicado em 1991. Lê-se quase como inglês, é gratuito, corre em Windows, macOS e Linux, e traz uma coleção grande de funções já feitas, a biblioteca padrão. Usa-se na análise de dados, na inteligência artificial, nos servidores de sites e para automatizar tarefas. Depois do Python, vais aprender C: são ferramentas diferentes, como um alicate e um martelo.

## Um script escreve-se em texto simples

Um script é só um ficheiro de **texto simples**, sem negrito, nem tipos de letra, nem cores guardadas no ficheiro. O Bloco de Notas já serve para o escrever. O Word não serve: guarda a formatação no ficheiro e troca as aspas retas por aspas curvas. Para o Python, as aspas curvas não são aspas.

```text
  File "C:\Users\aluno\Documents\fp-python\aspas.py", line 1
    print(“Olá”)
          ^
SyntaxError: invalid character '“' (U+201C)
```

A mensagem lê-se de baixo para cima. A última linha diz o que correu mal, um erro de sintaxe, isto é, nas regras de escrita. O `^` aponta para a primeira aspa curva. Se copiares código de um documento, confirma as aspas.

## Um editor de código ajuda enquanto escreves

O Bloco de Notas não ajuda em nada. Um **editor de código** guarda o ficheiro da mesma maneira, mas mostra-o de outra forma e ajuda enquanto escreves:

- pinta as partes do código com cores diferentes, o que se chama realce de sintaxe;
- mostra o número de cada linha;
- fecha sozinho as aspas e os parênteses;
- mantém a indentação quando carregas em Enter.

Se uma aspa ficar por fechar, o resto da linha fica todo da cor dos textos, e vês o erro antes de correres o programa. Nas aulas, o editor é o VS Code, de Visual Studio Code.

## Um IDE junta as ferramentas numa janela

Para fazer um programa, não basta escrevê-lo: é preciso guardá-lo, corrê-lo, ler as mensagens e corrigi-lo. Um **IDE**, das iniciais em inglês de ambiente de desenvolvimento integrado, junta numa só janela o que é preciso para isso. Tem um editor de código, um explorador de ficheiros e ajuda para escrever e para encontrar erros. Tem um terminal, uma janela onde escreves ordens, os comandos, uma por linha. Tem também um depurador, que corre o programa linha a linha.

"Integrado" quer dizer que as ferramentas trabalham em conjunto. O botão de correr sabe que ficheiro tens aberto, e o terminal abre-se na pasta do projeto.

O VS Code ganha estas ferramentas com **extensões**, programas pequenos que se lhe acrescentam. Com a extensão Python, da Microsoft, funciona como um IDE para Python. O IDE não é o Python: um computador com o VS Code e sem o Python deixa-te escrever scripts, mas não os consegue correr.

## As ferramentas do VS Code

Não precisas de as decorar. Precisas de saber que existem e para que servem.

| Ferramenta | Onde está | Para que serve |
| --- | --- | --- |
| Explorador (Explorer) | Painel da esquerda | Ver os ficheiros da pasta e criar ficheiros novos |
| Editor e separadores | Ao centro | Escrever o código; cada ficheiro aberto tem um separador |
| Números das linhas e cores | Na margem e no texto do editor | Encontrar a linha de que uma mensagem fala |
| Sugestões | Uma lista que aparece enquanto escreves | Escrever mais depressa e sem erros nos nomes |
| Sublinhado dos erros e painel dos problemas (Problems) | No editor e no painel de baixo | Ver um erro de escrita antes de correres |
| Terminal integrado | No painel de baixo | Correr o programa e ver o que ele escreve |
| Botão de correr | No canto de cima, à direita do editor | Correr o ficheiro aberto, sem escreveres o comando |
| Depurador (Run and Debug) | Nos ícones da esquerda | Correr o programa linha a linha e ver os valores |
| Extensões (Extensions) | Nos ícones da esquerda | Acrescentar ferramentas ao VS Code |
| Barra de estado | Na faixa de baixo da janela | Ver a linha do cursor e que versão do Python o VS Code vai usar |

A pasta do projeto, que vais criar no laboratório, abre-se uma vez, no menu File, com a opção Open Folder... Quando há alterações por guardar, aparece uma bola cheia no separador, no lugar do X. Guarda-se com Ctrl+S, ou Cmd+S no macOS.

O VS Code encontra os erros de escrita, e não os de raciocínio. As sugestões propõem o que existe, e não o que está certo para o teu problema.

## Correr um script

O terminal abre-se no menu Terminal, com a opção New Terminal, já dentro da pasta que tens aberta. Para correr um script, escreve-se `python`, um espaço e o nome do ficheiro:

```bash
python ola.py
```

Se o Windows não conhecer o `python`, experimenta `py ola.py`. No macOS e no Linux, o comando é `python3 ola.py`.

```python
# ola.py: o primeiro script, para confirmar que o Python corre neste computador.
print("Olá, Python!")
print("O meu primeiro script correu.")
```

Aparecem `Olá, Python!` e `O meu primeiro script correu.`, por esta ordem. O interpretador desce pelas linhas, e a primeira, com `#`, é um comentário, que ele ignora. As aspas não aparecem no ecrã.

O interpretador lê o ficheiro que está guardado no disco, e não o que está no ecrã. Guarda sempre antes de correr.

## O botão de correr escreve o comando por ti

Com a extensão Python, o triângulo no canto de cima corre o ficheiro do separador ativo, e o resultado aparece no terminal. Antes do resultado, aparece uma linha comprida que tu não escreveste: é o mesmo comando, com o sítio completo do Python e do ficheiro. No Windows, começa por `&`.

As duas formas dão o mesmo resultado. O botão é mais rápido, e o comando funciona em qualquer computador com o Python.

## A consola do Python experimenta uma linha

Escreve no terminal só o teu comando do Python, sem nome de ficheiro. Abre-se a consola, que mostra `>>>` e fica à espera de uma linha.

```text
>>> print("Olá da consola")
Olá da consola
>>> 2 + 3
5
```

As linhas com `>>>` foram escritas por ti, e as outras foram escritas pelo Python. Na consola, o Python mostra sozinho o valor de cada linha. Num script, só o `print` escreve no ecrã.

O que escreves na consola não fica guardado. Para sair, escreve `exit()`. Se escreveres `python ola.py` a seguir ao `>>>`, aparece `SyntaxError: invalid syntax`. Com `>>>`, escreves Python. Sem `>>>`, escreves comandos.

## Quando é preciso um IDE, e quando não

| O que vais fazer | O que te chega |
| --- | --- |
| Experimentar uma linha ou uma conta | A consola do Python |
| Ver que versão do Python tens | O terminal, com o comando `python --version` |
| Corrigir uma palavra num ficheiro | Qualquer editor de texto simples |
| Escrever e testar um programa | Um IDE, como o VS Code com a extensão Python |
| Encontrar um erro num programa grande | Um IDE, com o depurador |

Um programa não precisa de um IDE para correr: um script escrito no Bloco de Notas dá o mesmo resultado. Um IDE é pesado, e demora mais a abrir. E não pensa por ti: um programa sem nada sublinhado pode estar errado.

## Escrever no ecrã com `print`

O `Escreve:` do pseudocódigo passa a `print`, com o que se quer mostrar entre parênteses. Os parênteses estão lá porque o `print` é uma função que já vem com o Python. Chama-se como as funções da algoritmia, e o trabalho dela é escrever no ecrã.

Um texto entre aspas, a que também se chama string, aparece tal e qual. Um número escreve-se sem aspas. Para mostrar vários valores, separam-se por vírgulas, e o `print` põe sozinho um espaço entre cada dois. No pseudocódigo, eras tu que punhas os espaços.

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

Na segunda linha, os textos já trazem espaços, e o `print` acrescenta os seus. O `print()` vazio escreve uma linha em branco. Cada `print` acaba a linha.

## Os comentários são notas para quem lê o código

Um **comentário** começa com `#` e vai até ao fim da linha, e o Python ignora-o. Pode ocupar uma linha inteira ou vir no fim de uma linha de código.

```python
# comentarios.py: mostra as duas formas de escrever um comentário.

# Esta linha inteira é um comentário.
print("Primeira linha")  # Este comentário vem no fim de uma linha de código.
# print("Esta linha não aparece, porque começa com #.")
print("Segunda linha")
```

Aparecem só `Primeira linha` e `Segunda linha`. Pôr um `#` no início de uma linha de código desliga-a, sem a apagar. No VS Code, a opção Toggle Line Comment, do menu Edit, põe ou tira o `#`.

Nas aulas, a primeira linha de cada script é um comentário com o nome do ficheiro e o que ele faz. Um bom comentário diz o que não se vê no código, ou separa as partes de um programa.

## Os três tipos de erro

| Tipo de erro | Quando o Python dá por ele | O que aparece |
| --- | --- | --- |
| De sintaxe | Antes de executar qualquer linha | Só a mensagem, com `SyntaxError` |
| De execução | Na linha que não se consegue executar | O que as linhas anteriores escreveram, e a mensagem que começa por `Traceback` |
| De lógica | Nunca | O programa acaba, mas o resultado é diferente do esperado |

Um erro de sintaxe é um erro nas regras de escrita da linguagem. Aqui, falta a aspa que fecha o texto:

```python
# erro_sintaxe.py: ao segundo print falta a aspa que fecha o texto.
print("Olá, Python!")
print("O meu primeiro script correu.)
```

Aparece só a mensagem, sem o "Olá, Python!" da linha 2, e o `^` aponta a aspa que abre o texto:

```text
  File "C:\Users\aluno\Documents\fp-python\erro_sintaxe.py", line 3
    print("O meu primeiro script correu.)
          ^
SyntaxError: unterminated string literal (detected at line 3)
```

Um erro de execução acontece numa linha que não se consegue executar:

```python
# erro_execucao.py: o print do Três tem o nome mal escrito.
print("Um")
print("Dois")
prnt("Três")
print("Quatro")
```

Aparecem `Um` e `Dois`, e depois a mensagem:

```text
Um
Dois
Traceback (most recent call last):
  File "C:\Users\aluno\Documents\fp-python\erro_execucao.py", line 4, in <module>
    prnt("Três")
    ^^^^
NameError: name 'prnt' is not defined. Did you mean: 'print'?
```

A esta mensagem chama-se **traceback**, e lê-se de baixo para cima: o tipo de erro, a instrução, e o ficheiro e a linha. Para o Python, um nome com uma letra a menos, ou com uma maiúscula trocada, como `Print`, é outro nome, que não existe.

Num erro de lógica, o programa corre até ao fim, mas o resultado está errado. O Python não dá por nada, e só encontras o erro se comparares o ecrã com o que devia mostrar.

Quando um programa falha, segue sempre a mesma rotina:

1. Observa o erro: o resultado esperado, o obtido e o tipo de erro.
2. Escreve numa frase o que achas que o causa.
3. Confirma, com a mensagem e a linha que ela aponta, ou comparando o ecrã linha a linha.
4. Corrige a causa, e não o sítio onde o erro se vê.
5. Volta a testar o ecrã inteiro.

## O Python 3 e o código antigo

O Python 2 deixou de ser mantido em 2020, e hoje usa-se o Python 3. Na internet, ainda há muito código antigo, e o sinal mais fácil de reconhecer é o `print` sem parênteses:

| No Python 2 | No Python 3 |
| --- | --- |
| `print "Olá"` | `print("Olá")` |

O Python 3 recusa essa linha, com `SyntaxError: Missing parentheses in call to 'print'. Did you mean print(...)?`. Para saberes que versão tens, escreve `python --version` no terminal. O primeiro número tem de ser 3. As mensagens de erro dos materiais são as do Python 3.14, e numa versão mais antiga algumas têm outras palavras.

## Exemplo guiado: o ecrã das regras do duelo de dados

### O problema

Queremos um programa que escreva as regras do duelo de dados, o jogo do [projeto 1 da algoritmia](../01-algoritmos/projetos-guiados/05-projeto-1-duelo-de-dados.md). Este é o resultado esperado:

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

### O programa, parte a parte

Em pseudocódigo, cada linha seria um `Escreve:`. Em Python, cada `Escreve:` passa a `print`. As linhas em branco, que o pseudocódigo não tinha, são `print()` vazios. Começa-se pelo título e pelos números:

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
```

Corre-se, para confirmar esta parte. A seguir, no fim do mesmo ficheiro, acrescentam-se as regras:

```python
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

### Comparar com o resultado esperado

Compara o ecrã com o esperado, linha a linha: são catorze linhas, três delas em branco. Se os números estivessem trocados, com `3` no máximo de rondas e `5` nas vitórias, o programa corria sem nenhuma mensagem. Seria um erro de lógica, e só a comparação o apanhava.

## Erros frequentes

### O programa corre e não escreve nada

Com `Escreve: "Olá"` num script, o Python não dá erro e não escreve nada. Por coincidência, aceita uma palavra seguida de dois pontos e de um texto. Com vírgulas, como em `Escreve: "Vidas:", 3`, já dá `SyntaxError`. Troca cada `Escreve:` por um `print`.

### O Python não encontra o ficheiro

Com `can't open file` e `No such file or directory`, ou o terminal está noutra pasta, ou o nome no comando é diferente do verdadeiro. Confirma que o texto antes do cursor acaba na pasta do projeto, e que o nome é igual ao do explorador, com o `.py`.

## Palavras novas deste guia

- Programa: um algoritmo escrito numa linguagem de programação.
- Interpretador: o programa que lê um script, confirma que está bem escrito e executa as instruções.
- Script: um ficheiro de texto com instruções em Python, com o nome a acabar em `.py`.
- Texto simples: texto só com os caracteres escritos, sem formatação guardada no ficheiro.
- Editor de código: um editor de texto simples feito para escrever código.
- IDE: um programa que junta numa só janela as ferramentas para escrever, correr e corrigir programas.
- Extensão: um programa pequeno que se acrescenta ao VS Code para lhe dar ferramentas novas.
- Terminal: uma janela onde se escrevem comandos para o computador, um por linha.
- Consola do Python: o modo em que o Python executa uma linha de cada vez, a seguir ao `>>>`.
- Comentário: uma nota para quem lê o código, a seguir a `#`, que o Python ignora.
- Erro de sintaxe: um erro na escrita do código, que faz o Python recusar o programa.
- Erro de execução: um erro que para o programa numa linha que não se consegue executar.
- Erro de lógica: um erro sem mensagem; o programa corre até ao fim, mas o resultado está errado.
- Traceback: a mensagem de um erro de execução, que se lê de baixo para cima.

## O que vem a seguir

No tema seguinte, [Dados e interação](02-dados-e-interacao.md), os programas guardam valores em variáveis, fazem contas e leem o que a pessoa escreve no teclado.

![Rodapé](../imagens/rodape.png)
