![Cabeçalho](../../imagens/cabecalho.png)

# Laboratório: Do pseudocódigo ao Python

## O que vais construir

Vais preparar a pasta dos teus scripts e conhecer as ferramentas do VS Code. No fim, escreves o `adivinha_abertura.py`, o ecrã de abertura do adivinha o número, o jogo do projeto 2 da algoritmia.

No fim, o ecrã fica assim:

```text
ADIVINHA O NÚMERO
Um jogo para dois jogadores.

O número secreto está entre 1 e 100
Tentativas: 10

Como se joga:
1. O jogador 1 escreve o número secreto, sem o jogador 2 ver.
2. O jogador 2 tenta adivinhar o número.
3. Depois de cada tentativa, o jogo diz se o secreto é mais alto ou mais baixo.
4. Quem acertar até à tentativa 7 recebe os parabéns.

Boa sorte!
```

1. [Fase 1: Correr um script](#fase-1-correr-um-script)
2. [Fase 2: A consola do Python experimenta uma linha](#fase-2-a-consola-do-python-experimenta-uma-linha)
3. [Fase 3: As ferramentas do VS Code](#fase-3-as-ferramentas-do-vs-code)
4. [Fase 4: O botão de correr escreve o comando por ti](#fase-4-o-botão-de-correr-escreve-o-comando-por-ti)
5. [Fase 5: Os três tipos de erro](#fase-5-os-três-tipos-de-erro)
6. [Fase 6: Escrever no ecrã com `print`](#fase-6-escrever-no-ecrã-com-print)
7. [Fase 7, opcional: Quando é preciso um IDE, e quando não](#fase-7-opcional-quando-é-preciso-um-ide-e-quando-não)

## O que precisas

- O Python 3 e o VS Code. Para confirmares o Python, abre o terminal, como a fase 1 explica, e escreve `python --version`, ou `py --version` se o Windows não conhecer o `python`. No macOS, é `python3 --version`. O primeiro número tem de ser 3.
- A extensão Python do VS Code, que dá o botão de correr, as sugestões do Python e o sublinhado dos erros. A fase 3 mostra como confirmar que está instalada.

As mensagens de erro são as do Python 3.14. Numa versão mais antiga, podem ter outras palavras ou apontar outra linha. O caminho a seguir a `File` muda de computador para computador.

## Preparar o projeto

1. Cria uma pasta para os teus scripts de Python, com o nome `fp-python`, no sítio onde costumas guardar os trabalhos, por exemplo em Documentos. Se já a criaste na primeira aula, usa essa.

2. Abre a pasta no VS Code. No menu File, escolhe Open Folder... e escolhe `fp-python`. Se o VS Code perguntar se confias nos autores dos ficheiros, responde que sim, porque a pasta é tua. O que deves ver: à esquerda, no painel Explorer, o nome `FP-PYTHON`.

## Fase 1: Correr um script

Escreves as instruções num ficheiro, o script, e mandas o interpretador executá-lo. O `Escreve:` do pseudocódigo passa a chamar-se `print`. Rever: [Correr um script](../01-do-pseudocodigo-ao-python.md#correr-um-script).

1. No painel Explorer, passa o rato por cima de `FP-PYTHON` e carrega no primeiro ícone, New File. Escreve o nome `ola.py`, carrega em Enter e escreve no ficheiro. Se já tiveres o `ola.py` da primeira aula, abre-o e confirma que tem estas linhas:

   ```python
   # ola.py: o primeiro script, para confirmar que o Python corre neste computador.
   print("Olá, Python!")
   print("O meu primeiro script correu.")
   ```

2. Guarda, com Ctrl+S, ou Cmd+S no macOS.

3. No menu Terminal, escolhe New Terminal. O que deves ver: uma janela na parte de baixo, com o nome da pasta, `fp-python`, no fim da linha.

4. No terminal, corre o programa:

   ```bash
   python ola.py
   ```

   No macOS e no Linux, o comando é `python3 ola.py`. O que deves ver:

   ```text
   Olá, Python!
   O meu primeiro script correu.
   ```

   Se o Windows não conhecer o `python`, ou abrir a Microsoft Store, fecha a loja e experimenta `py ola.py`. Daqui em diante, usa o comando que funcionou. Se aparecer outra coisa, vê [Se alguma coisa falhar](#se-alguma-coisa-falhar).

5. Provoca um erro: apaga a aspa que fecha o texto da terceira linha. Guarda e corre outra vez. O que deves ver:

   ```text
     File "C:\Users\aluno\Documents\fp-python\ola.py", line 3
       print("O meu primeiro script correu.)
             ^
   SyntaxError: unterminated string literal (detected at line 3)
   ```

   O "Olá, Python!" da linha 2 também não apareceu. Volta a pôr a aspa, guarda e corre outra vez.

### Paragem 1

O `ola.py` corre e escreve as duas linhas.

Pensa antes de continuares: se o erro estivesse na linha 2, e a linha 3 estivesse certa, aparecia alguma frase? A resposta: não, porque o Python recusa o programa inteiro.

## Fase 2: A consola do Python experimenta uma linha

Às vezes só queres saber o que faz uma linha, sem criar um ficheiro. A consola executa uma linha de cada vez e mostra logo o resultado. Rever: [A consola do Python experimenta uma linha](../01-do-pseudocodigo-ao-python.md#a-consola-do-python-experimenta-uma-linha).

1. No terminal, escreve o teu comando do Python, sem nome de ficheiro, e carrega em Enter. O que deves ver: `>>>` na última linha.

2. Escreve só o que está a seguir a cada `>>>`, e confirma as respostas:

   ```text
   >>> print("Olá da consola")
   Olá da consola
   >>> print("Vidas:", 3)
   Vidas: 3
   >>> 2 + 3
   5
   ```

3. Provoca um erro: escreve `python ola.py` a seguir ao `>>>`. O que deves ver no fim da mensagem: `SyntaxError: invalid syntax`. A consola espera Python, e isso é um comando do terminal.

4. Sai da consola com `exit()` e Enter.

### Paragem 2

Sabes abrir e fechar a consola e usá-la para experimentar uma linha.

Pensa antes de continuares: como sabes se estás na consola ou no terminal? A resposta: na consola, a linha começa por `>>>`.

## Fase 3: As ferramentas do VS Code

Encontras as ferramentas do VS Code uma a uma. Não precisas de as decorar. Rever: [As ferramentas do VS Code](../01-do-pseudocodigo-ao-python.md#as-ferramentas-do-vs-code).

1. No explorador, à esquerda, carrega no `ola.py`. O que deves ver: o ficheiro abre-se ao centro, com um separador no topo. Repara nos números das linhas, na margem, e nas cores de cada parte do código.

2. No fim da linha 3, carrega em Enter e não guardes. O que deves ver: no separador, uma bola cheia no lugar do X. Guarda, e a bola volta a ser um X.

3. Na linha nova, escreve só `print(`. O que deves ver: o VS Code escreve sozinho o `)`. Escreve uma aspa, e ele escreve a que fecha.

4. Apaga o que escreveste e, na mesma linha, escreve só `pri`. O que deves ver: uma lista com `print`. Carrega em Tab para aceitar. Depois apaga a linha 4 inteira e guarda.

5. Olha para a barra de estado, no fundo da janela. O que deves ver: a posição do cursor, como `Ln 3, Col 12`, e a palavra `Python`.

6. Passa o rato pelos ícones da coluna da esquerda, carrega em Extensions e escreve `Python` na caixa de procura. O que deves ver: a extensão "Python", da Microsoft, sem botão Install, se já estiver instalada. Se tiver o botão, avisa o professor. Volta ao explorador, com o primeiro ícone da coluna.

### Paragem 3

Já encontraste o explorador, o editor e os separadores, os números das linhas e as cores, as sugestões, a barra de estado e as extensões.

Pensa antes de continuares: porque é que as cores não aparecem se abrires o ficheiro no Bloco de Notas? A resposta: não estão guardadas no ficheiro, e é o editor de código que as mostra.

## Fase 4: O botão de correr escreve o comando por ti

Com a extensão Python, um botão corre o ficheiro aberto. Se a extensão não estiver instalada, lê esta fase sem a fazer. Rever: [O botão de correr escreve o comando por ti](../01-do-pseudocodigo-ao-python.md#o-botão-de-correr-escreve-o-comando-por-ti).

1. Com o `ola.py` aberto, procura o triângulo no canto de cima, à direita do editor. Passa o rato por cima dele. O que deves ver: o texto Run Python File.

2. Carrega no triângulo. O que deves ver: no terminal, uma linha comprida que não escreveste e, por baixo, as duas linhas do `ola.py`.

### Paragem 4

Sabes correr um script com o comando e com o botão.

Pensa antes de continuares: com dois ficheiros abertos, qual corre o botão? A resposta: o do separador ativo, o que tens à frente.

## Fase 5: Os três tipos de erro

Provocas dois erros e vês o que o VS Code e o terminal mostram. O erro de lógica fica para a fase 6. Rever: [Os três tipos de erro](../01-do-pseudocodigo-ao-python.md#os-três-tipos-de-erro).

1. No `ola.py`, apaga o `)` do fim da linha 2, e não guardes. O que deves ver, com a extensão Python: uma linha ondulada, vermelha, perto do erro.

2. No menu View, escolhe Problems. O que deves ver: uma lista com o problema e o número da linha. Carrega no problema, e o cursor salta para a linha.

3. Guarda e corre. O que deves ver:

   ```text
     File "C:\Users\aluno\Documents\fp-python\ola.py", line 2
       print("Olá, Python!"
            ^
   SyntaxError: '(' was never closed
   ```

   Não apareceu nenhuma das duas frases. Volta a pôr o `)`, guarda e corre.

4. Na linha 3, apaga o `i` do `print`, para ficar `prnt`. Guarda e corre. O que deves ver:

   ```text
   Olá, Python!
   Traceback (most recent call last):
     File "C:\Users\aluno\Documents\fp-python\ola.py", line 3, in <module>
       prnt("O meu primeiro script correu.")
       ^^^^
   NameError: name 'prnt' is not defined. Did you mean: 'print'?
   ```

   O programa começou a correr e só parou na linha 3. Corrige o nome, guarda e corre.

### Paragem 5

O `ola.py` voltou a escrever as duas linhas.

Pensa antes de continuares: porque é que no primeiro erro não apareceu nenhuma frase, e no segundo apareceu uma? A resposta: o primeiro é de sintaxe, e o Python recusa o programa. O segundo é de execução, e o programa só para nessa linha.

## Fase 6: Escrever no ecrã com `print`

Traduzes o pseudocódigo, `Escreve:` a `Escreve:`, e confirmas que o ecrã fica igual ao de "O que vais construir". O `print` põe sozinho um espaço entre cada dois valores. Rever: [Escrever no ecrã com `print`](../01-do-pseudocodigo-ao-python.md#escrever-no-ecrã-com-print).

1. Este é o pseudocódigo do ecrã:

   ```text
   Escreve: "ADIVINHA O NÚMERO"
   Escreve: "Um jogo para dois jogadores."
   Escreve: "O número secreto está entre ", 1, " e ", 100
   Escreve: "Tentativas: ", 10
   Escreve: "Como se joga:"
   Escreve: "1. O jogador 1 escreve o número secreto, sem o jogador 2 ver."
   Escreve: "2. O jogador 2 tenta adivinhar o número."
   Escreve: "3. Depois de cada tentativa, o jogo diz se o secreto é mais alto ou mais baixo."
   Escreve: "4. Quem acertar até à tentativa ", 7, " recebe os parabéns."
   Escreve: "Boa sorte!"
   ```

2. Cria `adivinha_abertura.py` e escreve nele, à mão:

   ```python
   # adivinha_abertura.py: escreve o ecrã de abertura do adivinha o número, o jogo do projeto 2.

   # O título e a apresentação do jogo.
   print("ADIVINHA O NÚMERO")
   print("Um jogo para dois jogadores.")
   print()

   # Os números do jogo: o print põe os espaços, e por isso não vão dentro das aspas.
   print("O número secreto está entre", 1, "e", 100)
   print("Tentativas:", 10)
   print()

   # Como se joga, um passo por linha.
   print("Como se joga:")
   print("1. O jogador 1 escreve o número secreto, sem o jogador 2 ver.")
   print("2. O jogador 2 tenta adivinhar o número.")
   print("3. Depois de cada tentativa, o jogo diz se o secreto é mais alto ou mais baixo.")
   print("4. Quem acertar até à tentativa", 7, "recebe os parabéns.")
   print()
   print("Boa sorte!")
   ```

3. Guarda e corre. O que deves ver: o ecrã de "O que vais construir", com treze linhas, três delas em branco. Se for diferente, procura a primeira diferença, linha a linha.

4. Provoca um erro de lógica: na linha do "Tentativas:", troca o 10 por 12. Guarda e corre. O que deves ver: `Tentativas: 12`, sem nenhuma mensagem nem sublinhado. Volta a pôr o 10, guarda e corre.

### Paragem 6

O `adivinha_abertura.py` escreve o ecrã de abertura, igual ao esperado.

Pensa antes de continuares: porque é que o VS Code não sublinhou o 12? A resposta: o código estava bem escrito, e o VS Code não sabe o que o programa devia fazer.

## Fase 7, opcional: Quando é preciso um IDE, e quando não

Esta fase é para quem tiver Windows. Vês que um script não precisa do VS Code para correr. Rever: [Quando é preciso um IDE, e quando não](../01-do-pseudocodigo-ao-python.md#quando-é-preciso-um-ide-e-quando-não).

1. Abre o Bloco de Notas e escreve:

   ```python
   # sem_ide.py: um script escrito no Bloco de Notas.
   print("Este script não foi escrito num IDE.")
   ```

2. Guarda na pasta `fp-python`, com o nome `sem_ide.py`. Em "Guardar com o tipo", escolhe "Todos os ficheiros", e em "Codificação", confirma que está UTF-8.

3. No terminal, corre o `sem_ide.py`. O que deves ver: `Este script não foi escrito num IDE.`

### Paragem 7

O `sem_ide.py` corre, e foi escrito sem o VS Code.

Pensa antes de continuares: se o Bloco de Notas também serve, para que serve o IDE? A resposta: não muda o que o programa faz, mas ajuda quem o escreve.

## Se alguma coisa falhar

1. Guardaste o ficheiro? O Python corre o que está no disco, e não o que vês no ecrã.
2. Estás na pasta certa? No terminal, o texto antes do cursor tem de ter `fp-python` no fim, antes do `>` ou do `%`. Se não tiver, abre outro terminal, no menu Terminal.
3. Estás na consola do Python sem quereres? Se a linha começa por `>>>`, escreve `exit()` e carrega em Enter.
4. Copiaste o código à mão? Cada aspa e cada parêntese que abre tem de fechar, e as aspas são as retas.

### O Windows diz que não conhece o `python`, ou abre a Microsoft Store

Fecha a loja, se abriu, e usa `py` em vez de `python`. Se nenhum dos dois funcionar, avisa o professor.

### `can't open file` e `No such file or directory`

O terminal não está na pasta do ficheiro, ou o nome tem um erro. No Bloco de Notas, o ficheiro pode ter ficado com o nome `sem_ide.py.txt`: guarda-o outra vez, com o tipo "Todos os ficheiros".

### `SyntaxError: invalid syntax` ao escrever `python ola.py`

Estás dentro da consola do Python. Escreve `exit()`, carrega em Enter e escreve o comando outra vez.

### Não há triângulo no canto de cima do editor

O botão vem com a extensão Python, e só aparece nos ficheiros `.py`. Enquanto não houver botão, corre os scripts com o comando.

### `SyntaxError: invalid character '“' (U+201C)`

O código tem aspas curvas, que vêm de um documento de texto. Apaga-as e escreve-as outra vez no VS Code.

## Desafios

Faz cada desafio num ficheiro novo, como `desafio_1.py`, com o código do programa copiado para lá.

1. O título aparece dentro de uma caixa desenhada com os sinais `+`, `-` e `|`, com três linhas, assim:

   ```text
   +---------------------+
   |  ADIVINHA O NÚMERO  |
   +---------------------+
   ```

2. Acrescenta uma linha que escreva esta frase, com as aspas à vista: `O jogo responde "Mais alto" ou "Mais baixo".` Pista: o Python aceita textos entre aspas simples.
3. Põe as quatro linhas numeradas de "Como se joga", de uma vez, em comentário, e corre o programa. Depois volta a ligá-las. Pista: seleciona as linhas e usa a opção Toggle Line Comment, no menu Edit.

## Antes de terminares

- [ ] O `ola.py` escreve as duas linhas.
- [ ] O `adivinha_abertura.py` escreve o ecrã de "O que vais construir".
- [ ] Corres os scripts com o comando que funciona no teu computador.

![Rodapé](../../imagens/rodape.png)
