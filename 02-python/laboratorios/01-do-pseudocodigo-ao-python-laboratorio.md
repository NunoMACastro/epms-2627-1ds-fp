![Cabeçalho](../../imagens/cabecalho.png)

# Laboratório: Do pseudocódigo ao Python

Laboratório do tema Do pseudocódigo ao Python, do módulo Criar aplicações em linguagem de programação Python. Vais preparar a pasta dos teus scripts, correr o primeiro e conhecer uma a uma as ferramentas do VS Code. No fim, escreves o ecrã de abertura do adivinha o número, o jogo do projeto 2. Cada passo diz o que fazer, porquê e o que deves ver, e avanças ao teu ritmo. Tudo o que precisas está aqui; o [guia do tema](../01-do-pseudocodigo-ao-python.md) tem a teoria completa, para quem quiser saber mais.

## O que vais construir

No fim, tens uma pasta com dois scripts. O primeiro, `ola.py`, escreve duas linhas e confirma que o Python corre no teu computador. O segundo, `adivinha_abertura.py`, escreve o ecrã que aparece antes de um jogo do adivinha o número começar. Tem o título, os números do jogo e as regras.

Pelo caminho, ficas a saber correr um script no terminal e com o botão de correr, e experimentar uma linha na consola do Python. Ficas também a saber usar as ferramentas do VS Code que te ajudam a escrever e a encontrar erros, e para que serve cada uma.

| Fase | O que muda | O que funciona no fim |
| --- | --- | --- |
| 1 | `ola.py` | O primeiro script corre no terminal |
| 2 | Nada no disco; experimentas na consola do Python | Sabes entrar e sair da consola e usá-la para uma linha |
| 3 | Nada no disco; percorres as ferramentas do VS Code | Sabes onde estão as primeiras ferramentas e para que servem |
| 4 | Corres o `ola.py` com o botão | Sabes correr um script com o botão e o que ele escreve no terminal |
| 5 | `ola.py`, com erros provocados | Sabes ver um erro antes de correr e dizer de que tipo é |
| 6 | `adivinha_abertura.py` | O ecrã de abertura do jogo aparece igual ao esperado |
| 7, opcional | `sem_ide.py`, escrito no Bloco de Notas | Um script corre sem o VS Code |

No fim, a tua pasta fica assim:

```text
fp-python/
├── ola.py
└── adivinha_abertura.py
```

## Palavras que vais usar

- Script: um ficheiro de texto com instruções em Python, com o nome a acabar em `.py`. Para saber mais, vê a secção "Um programa é um algoritmo que o computador executa" do [guia](../01-do-pseudocodigo-ao-python.md).
- Interpretador: o programa que lê o teu script, confirma que está bem escrito e executa as instruções por ordem. É o que se instala quando se instala o Python.
- Editor de código: um editor de texto feito para escrever código, com cores, números de linha e ajudas à escrita.
- IDE, ambiente de desenvolvimento integrado: um programa que junta numa só janela as ferramentas para escrever, correr e corrigir programas. Para saber mais, vê a secção "O ambiente de desenvolvimento integrado, o IDE" do [guia](../01-do-pseudocodigo-ao-python.md).
- VS Code: o editor de código das aulas, que, com a extensão Python, funciona como um IDE para Python.
- Extensão: um programa pequeno que se acrescenta ao VS Code para lhe dar ferramentas novas.
- Terminal: uma janela onde se escrevem comandos, um por linha, e se carrega em Enter.
- Comando: uma ordem escrita no terminal, como `python ola.py`.
- Consola do Python: o modo em que o Python executa uma linha de cada vez e mostra logo o resultado, a seguir ao `>>>`.
- Comentário: uma nota para quem lê o código, a seguir a `#`, que o Python ignora.
- `print`: a função que escreve valores no ecrã, o `Escreve:` do pseudocódigo.
- Erro de sintaxe: um erro na escrita do código, que faz o Python recusar o programa antes de executar qualquer linha.
- Erro de execução: um erro que para o programa a meio, numa linha que não se consegue executar.
- Erro de lógica: um erro que não dá mensagem nenhuma; o programa corre e faz outra coisa do que devia.
- Traceback: a mensagem de um erro que para o programa a meio. Lê-se de baixo para cima. Para saber mais, vê a secção "Os três tipos de erro" do [guia](../01-do-pseudocodigo-ao-python.md).

## O que precisas

- O Python 3, o interpretador. Para confirmares que o tens, abre o terminal, como a fase 1 explica, e escreve `python --version`, ou `py --version` se o Windows não conhecer o `python`. Deve aparecer uma linha como `Python 3.13.2`, que quer dizer que o Python 3 está instalado. O primeiro número tem de ser 3. No macOS, o comando é `python3 --version`.
- O VS Code, o editor de código das aulas. Abre-se como qualquer outra aplicação do computador.
- A extensão Python do VS Code, que dá o botão de correr, as sugestões das palavras do Python e o sublinhado dos erros. A fase 3 mostra como confirmar que está instalada. Sem ela, o laboratório faz-se na mesma, e as fases 4 e 5 dizem o que muda.

Os resultados e as mensagens de erro deste laboratório são os do Python 3.14. Num Python mais antigo, uma mensagem pode ter outras palavras, ou apontar a linha seguinte. O tipo de erro, a palavra antes dos dois pontos, é o mesmo.

Os nomes dos menus e dos botões são os do VS Code em inglês. Os da preparação e da fase 1 foram confirmados a 27 de outubro de 2026. Se o teu VS Code estiver em português, estão no mesmo sítio, com o nome traduzido.

## Se alguma coisa falhar

1. Guardaste o ficheiro? O Python corre o que está guardado no disco, e não o que vês no ecrã. Guarda com Ctrl+S, ou Cmd+S no macOS. No VS Code, uma bola cheia no separador do ficheiro, no lugar do X, quer dizer que há alterações por guardar.
2. Estás na pasta certa? No terminal, o texto antes do cursor mostra a pasta onde estás. Tem de ter `fp-python` no fim, antes do sinal `>` no Windows, ou do `%` no macOS. No Windows, é parecido com `PS C:\Users\aluno\Documents\fp-python>`. Se não tiver, fecha o terminal e abre outro, no menu Terminal, com a opção New Terminal. O terminal novo abre-se na pasta que tens aberta no VS Code.
3. Estás na consola do Python sem quereres? Se a linha começa por `>>>`, escreve `exit()` e carrega em Enter, para voltares ao terminal.
4. Copiaste o código à mão? Confirma as aspas e os parênteses: cada um que abre tem de fechar. Confirma também que as aspas são as retas, `"`, e não as curvas de um documento de texto.

## Preparar o projeto

1. Cria uma pasta para os teus scripts de Python, com o nome `fp-python`, no sítio onde costumas guardar os trabalhos, por exemplo em Documentos. Uma pasta própria impede que os scripts se misturem com outros ficheiros. O nome não tem espaços nem acentos, para se escrever sem problemas no terminal. Se já a criaste na primeira aula, usa essa.

2. Abre a pasta no VS Code. No menu File, escolhe Open Folder..., isto é, "abrir pasta", e escolhe `fp-python`. Se o VS Code perguntar se confias nos autores dos ficheiros desta pasta, responde que sim: a pasta é tua. O que deves ver: à esquerda, no painel Explorer, o nome `FP-PYTHON`.

## Fase 1: Correr um script

Na algoritmia, quem executava os algoritmos eras tu, com a tabela de trace. Agora vais pôr o computador a fazê-lo. Para isso, escreves as instruções num ficheiro, o script, e mandas o interpretador do Python executá-lo. O `Escreve:` do pseudocódigo passa a chamar-se `print`, com o texto entre parênteses. Para saber mais, lê a secção "Correr um script" do [guia](../01-do-pseudocodigo-ao-python.md).

Se fizeste esta fase na primeira aula e o teu `ola.py` corre, lê os passos para relembrares e passa à fase 2.

1. Cria o primeiro script. No painel Explorer, passa o rato por cima de `FP-PYTHON` e carrega no primeiro ícone, New File..., isto é, "novo ficheiro". Escreve o nome `ola.py` e carrega em Enter. O `.py` no fim do nome diz ao VS Code e ao Python que é um script de Python. Cria `ola.py` com este conteúdo:

   ```python
   # ola.py: o primeiro script, para confirmar que o Python corre neste computador.
   print("Olá, Python!")
   print("O meu primeiro script correu.")
   ```

   Leitura guiada: a primeira linha começa com `#`, e é um comentário. Diz o nome do ficheiro e para que serve, e o Python ignora-a. As duas linhas seguintes escrevem cada uma o texto que está entre aspas, pela ordem em que estão. As aspas marcam onde o texto começa e acaba, e não aparecem no ecrã.

2. Guarda o ficheiro, com Ctrl+S, ou Cmd+S no macOS. O Python lê o ficheiro guardado no disco, e um ficheiro por guardar ainda não tem estas linhas.

3. Abre o terminal. No menu Terminal, escolhe New Terminal. O que deves ver: uma janela na parte de baixo do VS Code. Tem uma linha com o nome da pasta, `fp-python`, no fim, e o cursor à espera.

4. Antes de correres, prevê: o que aparece no terminal, e por que ordem? Depois, no terminal, corre:

   ```bash
   python ola.py
   ```

   No macOS e no Linux, o comando é `python3 ola.py`.

   O que deves ver:

   ```text
   Olá, Python!
   O meu primeiro script correu.
   ```

   Isto quer dizer que o interpretador encontrou o ficheiro e executou as duas instruções, de cima para baixo. Se o Windows responder que não conhece o `python`, ou se abrir a Microsoft Store, fecha a loja e experimenta `py ola.py`, que faz o mesmo. Daqui em diante, usa sempre o comando que funcionou no teu computador. Se aparecer outra coisa, vê os [problemas frequentes](#problemas-frequentes).

5. Provoca um erro de propósito: apaga a aspa que fecha o texto da terceira linha, para ficar `print("O meu primeiro script correu.)`. Guarda e corre outra vez o mesmo comando. O que deves ver:

   ```text
     File "C:\Users\aluno\Documents\fp-python\ola.py", line 3
       print("O meu primeiro script correu.)
             ^
   SyntaxError: unterminated string literal (detected at line 3)
   ```

   A primeira linha mostra o caminho do ficheiro no teu computador, e muda de computador para computador. A mensagem quer dizer "erro de sintaxe: texto por terminar, detetado na linha 3". Repara que o "Olá, Python!" da linha 2, que estava certa, também não apareceu. Um erro de sintaxe faz o Python recusar o programa inteiro, antes de executar qualquer linha. Para corrigir, volta a pôr a aspa, guarda e corre outra vez, até veres as duas linhas.

### Paragem 1

O `ola.py` corre e escreve as duas linhas. Sabes criar um script, guardá-lo e corrê-lo no terminal.

Pensa antes de continuares: porque é que, com o erro na linha 3, nem o "Olá, Python!" da linha 2 apareceu? A resposta: antes de executar, o interpretador lê o ficheiro todo e confirma que está bem escrito. Ao encontrar um erro de sintaxe, recusa o programa e não executa nenhuma linha, nem as que estão antes do erro.

## Fase 2: Experimentar na consola do Python

Às vezes só queres saber o que faz uma linha, sem criar um ficheiro. Para isso há a consola do Python: executa uma linha de cada vez e mostra logo o resultado. Para saber mais, lê a secção "A consola do Python, para experimentar uma linha" do [guia](../01-do-pseudocodigo-ao-python.md).

1. No terminal, escreve só `python`, sem nome de ficheiro, e carrega em Enter. No macOS, é `python3`. Se na fase 1 só funcionou o `py`, escreve `py`. O que deves ver: umas linhas com a versão do Python e, na última, `>>>`. Isto quer dizer que estás na consola do Python, à espera de uma linha.

2. Antes de escreveres cada linha, prevê o resultado. Depois escreve-a a seguir ao `>>>` e carrega em Enter. Escreve só o que está a seguir a cada `>>>`: as linhas sem `>>>` são as respostas do Python.

   ```text
   >>> print("Olá da consola")
   Olá da consola
   >>> print("Vidas:", 3)
   Vidas: 3
   >>> 2 + 3
   5
   ```

   O primeiro `print` escreve o texto, como num script. O segundo recebe um texto e um número, separados por uma vírgula, e escreve-os com um espaço entre eles. A terceira linha é uma conta sem `print`, e o resultado aparece na mesma: na consola, o Python mostra sozinho o valor de cada linha. Num script, só o `print` escreve no ecrã.

3. Provoca o erro mais comum da consola: escreve, a seguir ao `>>>`, o comando `python ola.py` e carrega em Enter. O que deves ver: uma mensagem que acaba em `SyntaxError: invalid syntax`. Isto acontece porque a consola espera uma linha de Python, e `python ola.py` é um comando do terminal, que o Python não percebe.

4. Sai da consola: escreve `exit()` e carrega em Enter. O que deves ver: a linha do terminal outra vez, com `fp-python` no fim. Agora sim, o `python ola.py` funciona.

### Paragem 2

Sabes abrir e fechar a consola do Python e usá-la para experimentar uma linha. Não ficou nenhum ficheiro novo na pasta, porque o que se escreve na consola não se guarda.

Pensa antes de continuares: como sabes, olhando para o terminal, se estás na consola do Python ou no terminal? A resposta: na consola, a linha começa por `>>>`, e escreves Python. Sem `>>>`, estás no terminal, e escreves comandos.

## Fase 3: Conhecer as ferramentas do VS Code

O VS Code junta numa só janela as ferramentas de que precisas para escrever, correr e corrigir programas. Por isso se chama a estes programas ambientes de desenvolvimento integrados, ou IDE. Nesta fase vais encontrá-las uma a uma. Não precisas de as decorar: precisas de saber que existem, para as ires buscar quando fizerem falta. Para saber mais, lê a secção "As ferramentas do VS Code" do [guia](../01-do-pseudocodigo-ao-python.md).

1. Olha para o explorador, o painel da esquerda, com o título `FP-PYTHON`. Mostra os ficheiros da pasta, e por agora só o `ola.py`. Carrega no `ola.py`. O que deves ver: o ficheiro abre-se ao centro, no editor, com um separador no topo com o nome `ola.py`. O explorador, Explorer, está à esquerda e serve para ver e criar os ficheiros da pasta.

2. Olha para a margem da esquerda do editor. Tem os números das linhas: 1, 2 e 3. Repara também nas cores: o comentário tem uma cor, o `print` outra, e os textos entre aspas outra. Os números servem para encontrar a linha de que uma mensagem fala, e as cores para ver o que é cada parte do código.

3. Experimenta a bola do separador. No fim da linha 3 do `ola.py`, carrega em Enter, para criar uma linha nova, e não guardes. O que deves ver: no separador do `ola.py`, no lugar do X, aparece uma bola cheia. Quer dizer que o que está no ecrã é diferente do que está guardado no disco. Guarda com Ctrl+S, ou Cmd+S no macOS, e a bola volta a ser um X. O editor serve para escrever o código, e cada separador é um ficheiro aberto.

4. Experimenta o fecho automático. Na linha nova, escreve só `print(`. O que deves ver: o VS Code escreve sozinho o `)`, e o cursor fica entre os dois parênteses. Escreve agora uma aspa, `"`, e o VS Code escreve a aspa que fecha. É assim que o editor evita parênteses e aspas por fechar.

5. Experimenta as sugestões. Apaga a linha que escreveste e, numa linha nova, escreve só `pri`. O que deves ver: uma lista pequena, por baixo do cursor, com `print` lá dentro. Carrega em Tab, ou em Enter, e o VS Code completa a palavra. Sem a extensão Python, a lista pode aparecer na mesma, com as palavras que já estão no ficheiro. Depois, apaga a linha 4 inteira, até o cursor voltar ao fim da linha 3. Guarda, e o `ola.py` volta a ter só as três linhas. As sugestões servem para escrever mais depressa e sem erros nos nomes.

6. Olha para a barra de estado, a faixa estreita no fundo da janela. O que deves ver, entre outras coisas: a posição do cursor, por exemplo `Ln 3, Col 12`, que quer dizer linha 3, coluna 12. Vês também a palavra `Python`, a linguagem do ficheiro aberto. Com a extensão Python, aparece também a versão do Python que o VS Code vai usar.

7. Confirma se a extensão Python está instalada. Na coluna de ícones da esquerda, carrega no ícone das extensões, Extensions, o dos quadrados. Na caixa de procura que aparece no topo, escreve `Python`. O que deves ver: uma lista de extensões, e a primeira, "Python", da Microsoft. Se ela tiver um botão Install, não está instalada: avisa o professor antes de instalar. Se não tiver esse botão, já está instalada. As extensões servem para acrescentar ferramentas ao VS Code.

8. Volta ao explorador, com um clique no primeiro ícone da coluna da esquerda, o das folhas, Explorer.

### Paragem 3

Já conheces as primeiras ferramentas. São o explorador, o editor e os separadores, os números das linhas e as cores, as sugestões, a barra de estado e as extensões. Sabes também o que quer dizer a bola cheia no separador.

Pensa antes de continuares: porque é que as cores do VS Code não aparecem quando abres o mesmo ficheiro no Bloco de Notas? A resposta: as cores não estão guardadas no ficheiro. O ficheiro tem só texto simples, e é o editor de código que pinta cada parte quando o mostra.

## Fase 4: Correr com o botão

Escrever `python ola.py` de cada vez funciona, mas, num programa que corres muitas vezes, cansa. Com a extensão Python, o VS Code tem um botão que corre o ficheiro aberto e escreve o comando por ti. Se a extensão não estiver instalada, lê os passos desta fase, sem os fazer, e passa à fase 5. Para saber mais, lê a secção "Com o botão de correr" do [guia](../01-do-pseudocodigo-ao-python.md).

1. Com o `ola.py` aberto no editor, procura no canto de cima, à direita do editor, um triângulo. Passa o rato por cima dele. O que deves ver: uma pequena caixa com o texto Run Python File, isto é, "correr o ficheiro de Python".

2. Antes de carregares, prevê: o que aparece no terminal? Depois carrega no triângulo. O que deves ver: no terminal, uma linha comprida que tu não escreveste e, por baixo, as duas linhas do `ola.py`. A linha comprida tem o caminho completo do interpretador do Python, um espaço e o caminho completo do `ola.py`.

   Isto quer dizer que o botão escreveu o comando por ti. No Windows, a linha começa por `&`. É o mesmo `python ola.py`, só que com os caminhos inteiros, para não haver dúvidas sobre que Python e que ficheiro usar. O resultado é o mesmo das duas formas.

3. O botão corre o ficheiro do separador ativo, o que tens à frente no editor. Quando tiveres dois ficheiros abertos, confirma que o separador ativo é o do ficheiro que queres correr, antes de carregares.

### Paragem 4

Sabes correr um script de duas formas: com o comando, no terminal, e com o botão de correr. Conheces mais duas ferramentas: o terminal integrado, no painel de baixo, e o botão de correr, no canto de cima à direita do editor.

Pensa antes de continuares: se o botão é mais rápido, porque é que vale a pena saber escrever o comando? A resposta: o comando funciona em qualquer computador com o Python, mesmo sem o VS Code ou sem a extensão. O botão só existe no VS Code com a extensão Python.

## Fase 5: Ver os erros antes de correr

Um erro de escrita, como um parêntese que ficou por fechar, faz o Python recusar o programa. Com a extensão Python, o VS Code encontra muitos destes erros enquanto escreves, antes de correres. Nesta fase vais provocar dois erros e ver o que o VS Code e o terminal mostram. No fim, dizes de que tipo é cada um. Para saber mais, lê a secção "Os três tipos de erro" do [guia](../01-do-pseudocodigo-ao-python.md).

1. Provoca um erro de sintaxe. No `ola.py`, apaga o `)` do fim da linha 2, para ficar `print("Olá, Python!"`. Não guardes ainda. O que deves ver, com a extensão Python: uma linha ondulada, vermelha, perto do sítio do erro. Sem a extensão, não aparece nada, e passas ao passo 3.

2. Abre o painel dos problemas. No menu View, escolhe Problems. O que deves ver: no painel de baixo, uma lista com pelo menos um problema, com o número da linha. Carrega no problema. O cursor salta para a linha do erro. É esta a vantagem de as ferramentas estarem integradas.

3. Guarda e corre o `ola.py`, com o comando ou com o botão. O que deves ver:

   ```text
     File "C:\Users\aluno\Documents\fp-python\ola.py", line 2
       print("Olá, Python!"
            ^
   SyntaxError: '(' was never closed
   ```

   A mensagem quer dizer "erro de sintaxe: o `(` nunca foi fechado". O `^` aponta para o parêntese que abre. Não apareceu nenhuma das duas frases, porque é um erro de sintaxe. Volta a pôr o `)`, guarda e corre outra vez, até veres as duas linhas.

4. Provoca agora um erro de execução. Na linha 3, apaga o `i` do `print`, para ficar `prnt("O meu primeiro script correu.")`. Guarda e corre. O que deves ver:

   ```text
   Olá, Python!
   Traceback (most recent call last):
     File "C:\Users\aluno\Documents\fp-python\ola.py", line 3, in <module>
       prnt("O meu primeiro script correu.")
       ^^^^
   NameError: name 'prnt' is not defined. Did you mean: 'print'?
   ```

   Lê a mensagem de baixo para cima. A última linha quer dizer "erro de nome: o nome `prnt` não está definido. Querias dizer `print`?". Antes de correres, o VS Code pode ter sublinhado o `prnt` com outra cor: é um aviso de que não conhece esse nome. Mas o tipo de erro decide-o o momento em que o Python dá por ele. Desta vez, o "Olá, Python!" apareceu: o programa estava bem escrito, o interpretador começou a executá-lo e só parou na linha 3. É um erro de execução. Corrige o nome, guarda e corre outra vez.

### Paragem 5

O `ola.py` voltou a correr e a escrever as duas linhas. Conheces mais duas ferramentas, o sublinhado dos erros e o painel dos problemas: servem para ver um erro de escrita antes de correres o programa. A secção "As ferramentas do VS Code" do [guia](../01-do-pseudocodigo-ao-python.md) tem uma tabela com todas as que usaste nas fases 3, 4 e 5. Diz onde está cada uma e para que serve, e é para consultares quando precisares.

Pensa antes de continuares: nos dois erros desta fase, porque é que no primeiro não apareceu nenhuma frase e no segundo apareceu uma? A resposta: o primeiro é um erro de sintaxe, e o Python recusa o programa antes de o executar. O segundo é um erro de execução. O programa começa a correr, e as linhas anteriores escrevem o que têm a escrever. Só para na linha que não consegue executar.

## Fase 6: O ecrã de abertura do adivinha o número

Agora vais escrever um programa a sério, com o que já sabes. No projeto 2 da algoritmia, fizeste o algoritmo do adivinha o número. Antes de um jogo começar, os jogadores precisam de saber como se joga. O programa desta fase escreve esse ecrã. Vais traduzir o pseudocódigo, `Escreve:` a `Escreve:`, e confirmar que o ecrã fica igual ao esperado. Para saber mais, lê o "Exemplo guiado" do [guia](../01-do-pseudocodigo-ao-python.md).

1. Lê o ecrã que o programa tem de escrever. É o resultado esperado, e vais compará-lo com o que o programa escrever:

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

2. Lê o pseudocódigo. Escreve uma linha do ecrã por `Escreve:`, sem as linhas em branco, que no pseudocódigo não contavam:

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

   Antes de traduzires, decide: onde ficam os espaços que o pseudocódigo tem dentro das aspas, em `"O número secreto está entre "`? A resposta: no Python, saem de dentro das aspas, porque o `print` põe sozinho um espaço entre cada dois valores. E onde ficam as três linhas em branco do ecrã? A resposta: são três `print()` vazios, depois da apresentação, depois dos números e antes do "Boa sorte!".

3. Cria `adivinha_abertura.py`, no explorador, com o ícone New File..., e com este conteúdo:

   ```python
   # adivinha_abertura.py: escreve o ecrã de abertura do adivinha o número, o jogo do projeto 2.

   # O título e a apresentação do jogo.
   print("ADIVINHA O NÚMERO")
   print("Um jogo para dois jogadores.")
   print()

   # Os números do jogo.
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

   Escreve o código tu, em vez de o copiares: é a escrever que vês o fecho automático e as sugestões a trabalhar.

   Leitura guiada: o interpretador lê de cima para baixo e salta os comentários, que separam o programa em três partes. Cada `print` escreve uma linha do ecrã, pela ordem do ficheiro. A linha do número secreto recebe quatro valores, dois textos e dois números, e escreve-os com um espaço entre cada dois. Os três `print()` vazios dão as linhas em branco.

4. Antes de correres, conta: quantas linhas deve escrever o programa, com as linhas em branco? Depois guarda e corre `python adivinha_abertura.py`, ou carrega no botão de correr com o `adivinha_abertura.py` no separador ativo. O que deves ver: o ecrã do passo 1, com treze linhas, três delas em branco. Se for diferente, compara linha a linha e procura a primeira diferença.

5. Provoca um erro de lógica. Na linha do "Tentativas:", troca o 10 por 12. Guarda e corre. O que deves ver: o programa corre até ao fim, sem nenhuma mensagem de erro e sem nenhum sublinhado no editor. Mas o ecrã diz "Tentativas: 12". Isto quer dizer que é um erro de lógica: o Python executou o que estava escrito e não sabe que o jogo tem 10 tentativas. Só o descobres comparando com o ecrã esperado. Volta a pôr o 10, guarda e corre outra vez.

### Paragem 6

O `adivinha_abertura.py` escreve o ecrã de abertura, igual ao esperado, linha a linha.

Pensa antes de continuares: no erro de lógica do passo 5, porque é que o VS Code não sublinhou nada? A resposta: o código estava bem escrito. O VS Code apanha os erros de escrita, e não sabe o que o programa devia fazer. Um 12 é um número tão válido como um 10.

## Fase 7, opcional: Um script sem IDE

Esta fase é para quem tiver um computador com Windows e quiser ver que um programa não precisa do VS Code para correr. Um script é só um ficheiro de texto simples, e o Bloco de Notas também escreve texto simples. Para saber mais, lê a secção "Quando é preciso um IDE, e quando não" do [guia](../01-do-pseudocodigo-ao-python.md).

1. Abre o Bloco de Notas do Windows e escreve estas duas linhas:

   ```python
   # sem_ide.py: um script escrito no Bloco de Notas.
   print("Este script não foi escrito num IDE.")
   ```

   Leitura guiada: a primeira linha é o comentário com o nome e o que o script faz, e a segunda escreve a frase. Repara que tudo aparece da mesma cor, sem números de linha, e que o parêntese não fechou sozinho.

2. Guarda o ficheiro dentro da pasta `fp-python`, com o nome `sem_ide.py`. No menu Ficheiro, escolhe Guardar como. Em "Guardar com o tipo", escolhe "Todos os ficheiros", para o Bloco de Notas não acrescentar `.txt` ao nome. Em "Codificação", confirma que está UTF-8, para os acentos não darem erro.

3. No terminal do VS Code, ou noutro terminal aberto na pasta `fp-python`, corre `python sem_ide.py`. O que deves ver: `Este script não foi escrito num IDE.` Isto quer dizer que o interpretador correu o ficheiro como outro qualquer. Para ele, não importa onde o texto foi escrito. Se aparecer `can't open file`, o ficheiro pode ter ficado com o nome `sem_ide.py.txt`: vê os [problemas frequentes](#problemas-frequentes).

### Paragem 7

O `sem_ide.py` corre, e foi escrito sem o VS Code. Podes apagá-lo, ou deixá-lo na pasta.

Pensa antes de continuares: se o Bloco de Notas também serve, para que serve o IDE? A resposta: o IDE não muda o que o programa faz. Ajuda quem escreve. As cores, os números das linhas, o fecho automático, as sugestões, o sublinhado dos erros e o botão de correr poupam tempo e erros. Fazem mais diferença nos programas com muitas linhas.

## Problemas frequentes

### O Windows diz que não conhece o `python`, ou abre a Microsoft Store

O comando `python` não está disponível com esse nome neste computador. Fecha a loja, se abriu, e usa `py` em vez de `python`, como em `py ola.py`. Se nenhum dos dois funcionar, avisa o professor: o Python pode não estar instalado.

### `can't open file` e `No such file or directory`

A mensagem quer dizer "não consigo abrir o ficheiro: não existe esse ficheiro nem essa pasta". O terminal não está na pasta do ficheiro, ou o nome tem um erro. Confirma que o texto antes do cursor tem `fp-python` no fim. Confirma também que o nome no comando é igual ao do painel Explorer, com o `.py`. Se o ficheiro foi guardado no Bloco de Notas, pode ter ficado com o nome `sem_ide.py.txt`: guarda-o outra vez, com o tipo "Todos os ficheiros".

### `SyntaxError: invalid syntax` ao escrever `python ola.py`

Estás dentro da consola do Python, e a linha começa por `>>>`. A consola espera Python, e não comandos do terminal. Escreve `exit()`, carrega em Enter e escreve o comando outra vez.

### Não há triângulo no canto de cima do editor

O botão de correr vem com a extensão Python. Confirma, como no passo 7 da fase 3, se a extensão está instalada. Confirma também que o ficheiro aberto acaba em `.py`: o botão só aparece para os ficheiros de Python. Enquanto não houver botão, corre os scripts com o comando, no terminal.

### O botão de correr corre outro ficheiro

O botão corre o ficheiro do separador ativo. Carrega no separador do ficheiro que queres correr, para ele ficar à frente, e carrega outra vez no botão.

### `SyntaxError: invalid character '“' (U+201C)`

O código tem aspas curvas, que vêm de um documento de texto ou de uma apresentação. Apaga as aspas e escreve-as outra vez no VS Code, com a tecla das aspas.

### O resultado não muda depois de corrigires o código

O ficheiro não foi guardado. Guarda com Ctrl+S, ou Cmd+S no macOS, e corre outra vez.

## Desafios

1. O título numa caixa. Muda o `adivinha_abertura.py` para o título aparecer dentro de uma caixa desenhada com os sinais `+`, `-` e `|`, com três linhas, assim:

   ```text
   +---------------------+
   |  ADIVINHA O NÚMERO  |
   +---------------------+
   ```

   Pista: cada linha da caixa é um `print`. Conta os sinais e os espaços, para as três linhas ficarem com o mesmo comprimento.

2. As aspas dentro do texto. Acrescenta uma linha ao ecrã que escreva, com as aspas à vista, `O jogo responde "Mais alto" ou "Mais baixo".`. Pista: o Python aceita textos entre aspas simples, como `'Olá'`, e não só entre aspas duplas. Experimenta primeiro na consola.

3. Desligar e voltar a ligar. Põe as quatro linhas das regras, de uma vez, em comentário, e corre o programa para veres o ecrã sem elas. Depois volta a ligá-las. Pista: seleciona as quatro linhas e usa, no menu Edit, a opção Toggle Line Comment.

## Antes de terminares

- [ ] O `ola.py` corre e escreve as duas linhas.
- [ ] O `adivinha_abertura.py` escreve o ecrã de abertura, igual ao esperado, linha a linha.
- [ ] Corres os scripts no terminal com o comando que funciona no teu computador: `python`, `py` ou `python3`.
- [ ] Sabes onde está cada ferramenta das fases 3, 4 e 5 e para que serve.
- [ ] Sabes dizer de que tipo foi cada erro que provocaste: de sintaxe, de execução ou de lógica.
- [ ] Consegues explicar, por palavras tuas, o que é um IDE, para que serve, e quando te chegaria um editor simples ou a consola.

![Rodapé](../../imagens/rodape.png)
