![Cabeçalho](../../imagens/cabecalho.png)

# Laboratório: Dados e interação

Laboratório do tema Dados e interação, do módulo Criar aplicações em linguagem de programação Python. Vais construir um programa que lê os resultados de uma equipa no torneio de futebol da escola e mostra o resumo dela. Cada passo diz o que fazer, porquê e o que deves ver, e avanças ao teu ritmo. Tudo o que precisas está aqui; o [guia do tema](../02-dados-e-interacao.md) tem a teoria completa, para quem quiser saber mais.

## O que vais construir

No torneio de futebol entre as turmas da escola, cada vitória vale 3 pontos, cada empate vale 1 ponto e cada derrota não vale nada. O teu programa, `resumo_equipa.py`, pergunta o nome de uma equipa e quantas vitórias, empates e derrotas ela teve. Depois mostra quantos jogos a equipa fez, quantos pontos tem, quantos pontos fez em média por jogo e que percentagem dos jogos ganhou.

É um programa em sequência: lê, converte, calcula e escreve, sempre pela mesma ordem, de cima para baixo. No fim, ficas a saber guardar valores em variáveis e constantes e fazer contas com elas. Ficas também a saber ler valores do teclado, convertê-los e testar um programa com uma tabela de casos calculados à mão.

No fim, com a equipa 10.º DS, que teve 4 vitórias, 3 empates e 2 derrotas, o terminal fica assim:

```text
Nome da equipa? 10.º DS
Vitórias? 4
Empates? 3
Derrotas? 2

Equipa: 10.º DS
Jogos: 9
Vitórias: 4
Empates: 3
Derrotas: 2
Pontos: 15
Pontos por jogo: 1.67
Percentagem de vitórias: 44
```

As quatro respostas depois dos pontos de interrogação são as que tu escreves no teclado.

| Fase | O que muda | O que funciona no fim |
| --- | --- | --- |
| 1 | `resumo_equipa.py`, com os resultados escritos no programa | O programa mostra o nome e os resultados da equipa |
| 2 | `resumo_equipa.py`, com duas contas | O programa mostra também os jogos e os pontos |
| 3 | `resumo_equipa.py`, com duas constantes | O mesmo resumo, com as regras do torneio no início, com nome |
| 4 | Nada no disco; experimentas na consola do Python | Sabes como o Python divide e arredonda |
| 5 | `resumo_equipa.py`, com uma divisão e o `round` | O programa mostra os pontos por jogo e a percentagem de vitórias |
| 6 | `resumo_equipa.py`, com o `input` e o `int` | O programa pergunta os resultados de qualquer equipa |
| 7 | Nada no disco; corres o programa com cinco casos de teste | Confirmaste o programa com cinco casos calculados à mão |

No fim, a tua pasta tem mais um ficheiro, ao lado dos do tema anterior:

```text
fp-python/
├── ...
└── resumo_equipa.py
```

## Palavras que vais usar

- Variável: um espaço com um nome, onde se guarda um valor que pode mudar, como em `vitorias = 4`. A variável nasce na primeira linha que lhe dá um valor. Para saber mais, vê a secção "Guardar um valor numa variável" do [guia](../02-dados-e-interacao.md).
- Atribuição: a instrução com `=`, que calcula o lado direito e guarda o resultado na variável da esquerda. Lê-se "recebe".
- Constante: uma variável com o nome todo em maiúsculas, como `PONTOS_POR_VITORIA`, que guarda uma regra do problema e não muda.
- Tipo: o género de valor. `int` é um número inteiro, `float` um número com parte decimal, escrita com ponto, e `str` um texto, entre aspas.
- Operador: o sinal de uma conta, como `+`, `*` ou `/`.
- `//` e `%`: a divisão inteira e o resto, o `div` e o `resto` do pseudocódigo.
- Função predefinida: uma função que já vem com o Python, como o `round` ou o `type`. Chama-se escrevendo o nome e, entre parênteses, os valores que ela recebe, os argumentos. Devolve um resultado.
- `round`: a função predefinida que arredonda um número.
- `type`: a função predefinida que diz de que tipo é um valor.
- `input`: a função predefinida que escreve uma pergunta e espera que a pessoa escreva e carregue em Enter. Devolve o que ela escreveu, sempre como texto.
- Converter: transformar um valor de um tipo noutro, como o texto `"4"` no número 4, com a função `int`. Para saber mais, vê a secção "Converter o texto lido num número: `int` e `float`" do [guia](../02-dados-e-interacao.md).
- Caso de teste: uma entrada, com o resultado esperado calculado à mão a partir do enunciado, para comparar com o que o programa mostra.
- Traceback: a mensagem de um erro que para o programa a meio. Lê-se de baixo para cima: a última linha diz o que aconteceu, e as de cima dizem onde.

## O que precisas

- A pasta `fp-python`, do tema anterior, aberta no VS Code. Abre-a no menu File, com a opção Open Folder.... O que deves ver: à esquerda, no painel Explorer, o nome `FP-PYTHON` e os ficheiros do tema anterior. Se não a tens, faz primeiro a secção "Preparar o projeto" do [laboratório do tema 01](01-do-pseudocodigo-ao-python-laboratorio.md).
- O Python 3. Para confirmares que o tens, abre o terminal, no menu Terminal, com a opção New Terminal, e escreve `python --version`. Deve aparecer uma linha como `Python 3.13.2`, que quer dizer que o Python 3 está instalado. O primeiro número tem de ser 3. No macOS, o comando é `python3 --version`. Se o Windows não conhecer o `python`, experimenta `py --version`.

Ao longo do laboratório, o comando para correr o programa é `python resumo_equipa.py`. Usa o que funcionou no teu computador no tema anterior: `py resumo_equipa.py` no Windows, se o `python` não funcionar, ou `python3 resumo_equipa.py` no macOS. Também podes usar o botão de correr, o triângulo no canto de cima, à direita do editor, se a extensão Python estiver instalada.

Os resultados e as mensagens de erro deste laboratório são os do Python 3.14. Num Python mais antigo, uma mensagem pode ter outras palavras, ou não ter os sinais que apontam o sítio do erro. O tipo de erro, a palavra antes dos dois pontos na última linha, é o mesmo.

Os nomes dos menus e dos botões são os do VS Code em inglês. São os mesmos do laboratório do tema 01, confirmados a 27 de outubro de 2026. Se o teu VS Code estiver em português, estão no mesmo sítio, com o nome traduzido.

## Se alguma coisa falhar

1. Guardaste o ficheiro? O Python corre o que está guardado no disco, e não o que vês no ecrã. Guarda com Ctrl+S, ou Cmd+S no macOS. No VS Code, uma bola cheia no separador do ficheiro, no lugar do X, quer dizer que há alterações por guardar.
2. Estás na pasta certa? No terminal, o texto antes do cursor tem de acabar em `fp-python`. Se não acabar, fecha o terminal e abre outro, no menu Terminal, com a opção New Terminal. O terminal novo abre na pasta que tens aberta no VS Code.
3. Estás na consola do Python sem quereres? Se a linha começa por `>>>`, escreve `exit()` e carrega em Enter, para voltares ao terminal.
4. O programa ficou parado? A partir da fase 6, o programa espera que escrevas cada resposta. Escreve-a e carrega em Enter. Se quiseres parar o programa a meio, carrega em Ctrl+C no terminal. Aparece uma mensagem que acaba em `KeyboardInterrupt`, isto é, "interrupção pelo teclado": quer só dizer que o paraste tu.
5. Copiaste o código à mão? Confirma as aspas, que abrem e fecham, e os parênteses. Numa linha como `vitorias = int(input("Vitórias? "))`, há dois parênteses a fechar no fim, um do `input` e outro do `int`.

## Fase 1: Guardar os resultados em variáveis

Um programa que mostra o resumo de uma equipa precisa de se lembrar dos resultados dela. Na algoritmia, um valor que o algoritmo guarda tinha um nome e ficava numa variável, como `int vitorias = 4`. Em Python, a variável escreve-se sem o tipo à frente: `vitorias = 4`. O Python descobre o tipo pelo próprio valor. Os nomes escrevem-se em minúsculas, sem acentos, com um traço baixo entre as palavras: `nome_equipa`, e não `nomeEquipa`.

Nesta fase, os resultados ficam escritos no próprio programa. Na fase 6, passam a ser perguntados a quem usa o programa. Para saber mais, lê a secção "Guardar um valor numa variável" do [guia](../02-dados-e-interacao.md).

1. No painel Explorer, passa o rato por cima de `FP-PYTHON` e carrega no primeiro ícone, New File.... Escreve o nome `resumo_equipa.py` e carrega em Enter. Cria `resumo_equipa.py` com este conteúdo:

   ```python
   # resumo_equipa.py: o resumo de uma equipa no torneio de futebol da escola.
   # Nesta fase, os resultados da equipa estão escritos no próprio programa.

   nome_equipa = "10.º DS"
   vitorias = 4
   empates = 3
   derrotas = 2

   print("Equipa:", nome_equipa)
   print("Vitórias:", vitorias)
   print("Empates:", empates)
   print("Derrotas:", derrotas)
   ```

   Leitura guiada: as linhas 4 a 7 criam quatro variáveis. Cada uma nasce na sua linha, com o primeiro valor. `nome_equipa` guarda um texto, entre aspas, e as outras três guardam números inteiros. As linhas 9 a 12 escrevem cada uma um texto e um valor. Em cada `print`, o que está entre aspas aparece tal e qual. O que está sem aspas é o nome de uma variável, e aparece o valor dela. Os acentos ficam só dentro das aspas, como em `"Vitórias:"`, e nunca nos nomes.

2. Guarda o ficheiro. Antes de correres, prevê as quatro linhas que aparecem. Depois, no terminal, corre:

   ```bash
   python resumo_equipa.py
   ```

   No macOS, o comando é `python3 resumo_equipa.py`.

   O que deves ver:

   ```text
   Equipa: 10.º DS
   Vitórias: 4
   Empates: 3
   Derrotas: 2
   ```

   Isto quer dizer que as quatro variáveis guardaram os valores e que cada `print` foi buscar o valor da sua. Se aparecer outra coisa, vê os [problemas frequentes](#problemas-frequentes).

3. Experimenta a diferença entre um texto e uma variável. Na linha 10, põe aspas à volta do nome da variável, para ficar `print("Vitórias:", "vitorias")`. Antes de correres, prevê o que aparece na segunda linha. Guarda e corre.

   O que deves ver na segunda linha: `Vitórias: vitorias`. Com aspas, `"vitorias"` é só um texto, e o `print` escreve as letras. Sem aspas, o Python procura uma variável com esse nome e escreve o valor dela. Tira as aspas, para a linha voltar a ser `print("Vitórias:", vitorias)`, e guarda.

4. Provoca um erro de propósito. Na linha 10, apaga o `s` do fim do nome, para ficar `print("Vitórias:", vitoria)`. Guarda e corre. O que deves ver:

   ```text
   Equipa: 10.º DS
   Traceback (most recent call last):
     File "C:\Users\aluno\Documents\fp-python\resumo_equipa.py", line 10, in <module>
       print("Vitórias:", vitoria)
                          ^^^^^^^
   NameError: name 'vitoria' is not defined. Did you mean: 'vitorias'?
   ```

   Lê a mensagem de baixo para cima. A última linha quer dizer "erro de nome: o nome 'vitoria' não está definido. Querias dizer 'vitorias'?". As de cima dizem onde: na linha 10, e os sinais `^` estão debaixo do nome errado. O caminho do ficheiro, a seguir a `File`, muda de computador para computador. Para o Python, `vitoria` e `vitorias` são duas variáveis diferentes, e a primeira nunca nasceu. É um erro de execução: a linha 9 correu, e o programa parou na 10. Para corrigir, volta a pôr o `s`, guarda e corre outra vez, até veres as quatro linhas.

### Paragem 1

O `resumo_equipa.py` mostra o nome e os resultados da equipa, em quatro linhas. Sabes criar variáveis em Python e escrever o valor delas com o `print`.

Pensa antes de continuares: em pseudocódigo, como se escrevia a linha 5? E porque é que, em Python, não se escreve o `int`? A resposta: em pseudocódigo era `int vitorias = 4`, com o tipo na linha onde a variável nasce. Em Python o tipo não se escreve, porque está no valor: o Python vê que 4 é um inteiro e guarda-o como tal.

## Fase 2: Calcular os jogos e os pontos, pela ordem das contas

O resumo precisa de duas contas: quantos jogos a equipa fez e quantos pontos tem. Os jogos são as vitórias, mais os empates, mais as derrotas. Os pontos são as vitórias vezes 3, mais os empates vezes 1, porque uma vitória vale 3 pontos e um empate vale 1.

Na conta dos pontos há multiplicações e uma soma. A ordem é a da matemática: primeiro as multiplicações e as divisões, depois as somas e as subtrações. Os parênteses mudam a ordem. Para saber mais, lê a secção "A ordem das contas" do [guia](../02-dados-e-interacao.md).

1. Substitui todo o conteúdo de `resumo_equipa.py` por este:

   ```python
   # resumo_equipa.py: o resumo de uma equipa no torneio de futebol da escola.
   # Nesta fase, o programa calcula os jogos e os pontos da equipa.

   nome_equipa = "10.º DS"
   vitorias = 4
   empates = 3
   derrotas = 2

   jogos = vitorias + empates + derrotas
   # As multiplicações fazem-se antes da soma, por isso não são precisos parênteses.
   pontos = vitorias * 3 + empates * 1

   print("Equipa:", nome_equipa)
   print("Jogos:", jogos)
   print("Vitórias:", vitorias)
   print("Empates:", empates)
   print("Derrotas:", derrotas)
   print("Pontos:", pontos)
   ```

   Leitura guiada: as linhas 9 e 11 são duas atribuições com contas. Em cada uma, o Python calcula primeiro o lado direito, com os valores que as variáveis têm nesse momento. Depois guarda o resultado na variável da esquerda, que nasce aí. Por isso as contas vêm depois das linhas onde nascem as vitórias, os empates e as derrotas. Na linha 11, o 3 e o 1 são os pontos de uma vitória e de um empate. A derrota não aparece na conta, porque vale zero.

2. Guarda. Antes de correres, calcula à mão os jogos e os pontos desta equipa. Depois corre o programa, com o mesmo comando da fase 1.

   O que deves ver:

   ```text
   Equipa: 10.º DS
   Jogos: 9
   Vitórias: 4
   Empates: 3
   Derrotas: 2
   Pontos: 15
   ```

   Isto quer dizer que as duas contas estão certas. 4 mais 3 mais 2 dá 9 jogos. 4 vezes 3, mais 3 vezes 1, dá 12 mais 3, ou seja, 15 pontos.

3. Provoca um erro de lógica de propósito. Na linha 11, escreve a conta com outros parênteses: `pontos = (vitorias + empates) * 3`. Antes de correres, prevê quantos pontos aparecem. Guarda e corre.

   O que deves ver na última linha: `Pontos: 21`. Não há mensagem nenhuma, e o programa acaba normalmente, mas o resultado está errado. Os parênteses fizeram a soma primeiro, 4 mais 3 dá 7, e depois multiplicaram esses 7 por 3. É como se os empates valessem tanto como as vitórias. É um erro de lógica: só o apanhas porque calculaste à mão que deviam ser 15. Volta a pôr a linha 11 como estava, guarda e confirma que aparece outra vez `Pontos: 15`.

### Paragem 2

O programa mostra os jogos e os pontos da equipa: `Jogos: 9` e `Pontos: 15`.

Pensa antes de continuares: se escrevesses `pontos = empates * 1 + vitorias * 3`, com as duas partes trocadas, o resultado mudava? A resposta: não. As multiplicações fazem-se primeiro, seja qual for a ordem em que estão escritas, e 3 mais 12 dá os mesmos 15.

## Fase 3: Dar nome às regras, com constantes

Na linha 11, o 3 e o 1 são regras do torneio, e não resultados de uma equipa. Quem lê a conta tem de adivinhar o que querem dizer. E se o torneio mudar uma regra, tens de procurar o número no meio das contas.

Na algoritmia, uma regra destas era uma constante, com `const`. O Python não tem `const`: uma constante é uma variável com o nome todo em maiúsculas, que se combina não mudar. Escreve-se no início do programa, para quem lê conhecer as regras antes das contas. Para saber mais, lê a secção "As constantes" do [guia](../02-dados-e-interacao.md).

1. Em `resumo_equipa.py`, logo a seguir à linha em branco da linha 3, acrescenta estas três linhas, e mais uma linha em branco depois delas:

   ```python
   # As regras do torneio: uma vitória vale 3 pontos, um empate vale 1.
   PONTOS_POR_VITORIA = 3
   PONTOS_POR_EMPATE = 1
   ```

   Leitura guiada: o comentário diz que regras são, e as duas constantes guardam-nas. Os nomes em maiúsculas avisam quem lê de que estes valores não mudam enquanto o programa corre.

2. Com as quatro linhas novas, a conta dos pontos desceu para a linha 15. Substitui-a por esta, com os nomes das constantes no lugar dos números:

   ```python
   pontos = vitorias * PONTOS_POR_VITORIA + empates * PONTOS_POR_EMPATE
   ```

   Leitura guiada: a conta é a mesma da fase 2, e lê-se agora como uma frase. São as vitórias vezes os pontos de uma vitória, mais os empates vezes os pontos de um empate.

3. Guarda. Antes de correres, prevê se os pontos mudam. Depois corre.

   O que deves ver: o mesmo resumo da fase 2, com `Jogos: 9` e `Pontos: 15`. Trocar os números pelas constantes não muda nenhuma conta. Muda só a forma como o programa se lê.

### Paragem 3

O programa mostra o mesmo resumo, e as regras do torneio estão no início, com nome.

O ficheiro `resumo_equipa.py` completo, como deve estar agora:

```python
# resumo_equipa.py: o resumo de uma equipa no torneio de futebol da escola.
# Nesta fase, o programa calcula os jogos e os pontos da equipa.

# As regras do torneio: uma vitória vale 3 pontos, um empate vale 1.
PONTOS_POR_VITORIA = 3
PONTOS_POR_EMPATE = 1

nome_equipa = "10.º DS"
vitorias = 4
empates = 3
derrotas = 2

jogos = vitorias + empates + derrotas
# As multiplicações fazem-se antes da soma, por isso não são precisos parênteses.
pontos = vitorias * PONTOS_POR_VITORIA + empates * PONTOS_POR_EMPATE

print("Equipa:", nome_equipa)
print("Jogos:", jogos)
print("Vitórias:", vitorias)
print("Empates:", empates)
print("Derrotas:", derrotas)
print("Pontos:", pontos)
```

Pensa antes de continuares: se o torneio passasse a dar 2 pontos por empate, que linha mudavas? E se o 1 estivesse escrito na conta, em vez de `PONTOS_POR_EMPATE`? A resposta: mudavas só a linha 6, para `PONTOS_POR_EMPATE = 2`, e a conta ficava igual. Com o número escrito na conta, tinhas de o procurar no meio das contas, e o leitor não sabia o que queria dizer aquele 1.

## Fase 4: Experimentar as divisões na consola

Os pontos por jogo são os pontos a dividir pelos jogos: 15 a dividir por 9. Antes de pores essa conta no programa, vale a pena ver na consola do Python como ele divide, porque há surpresas. Na consola, o Python executa uma linha de cada vez e mostra logo o resultado, sem precisares de `print`. O que lá escreves não fica guardado em nenhum ficheiro.

Vais usar duas funções predefinidas, que já vêm com o Python. O `type` recebe um valor e diz de que tipo ele é. O `round` recebe um número e devolve-o arredondado. Escreve-se o nome da função e, entre parênteses, o valor. Para saber mais, lê as secções "A divisão com `/` dá sempre um `float`" e "Funções predefinidas" do [guia](../02-dados-e-interacao.md).

1. No terminal, escreve só `python`, sem nome de ficheiro, e carrega em Enter. No macOS, é `python3`. O que deves ver: umas linhas com a versão do Python e, na última, `>>>`. Isto quer dizer que estás na consola do Python, à espera de uma linha.

2. Antes de escreveres cada linha, prevê o resultado. Depois escreve-a a seguir ao `>>>` e carrega em Enter:

   ```text
   >>> 15 / 9
   1.6666666666666667
   >>> 18 / 9
   2.0
   >>> 15 // 9
   1
   >>> 15 % 9
   6
   >>> type(15 / 9)
   <class 'float'>
   >>> type(15 // 9)
   <class 'int'>
   ```

   A divisão com `/` dá sempre um número com parte decimal, um `float`. Até `18 / 9`, que é uma conta exata, dá `2.0`, e não `2`. O `//` é o `div` do pseudocódigo: diz quantas vezes o 9 cabe inteiro no 15, uma vez, e dá um `int`. O `%` é o `resto`: o que sobra, 6. O `type` responde com `<class '...'>`, e o nome entre as aspas é o tipo. Para os pontos por jogo, a conta certa é o `/`, porque uma média tem parte decimal.

3. A média `1.6666666666666667` tem casas decimais a mais para um resumo. Arredonda-a, com o `round`. Prevê e confirma:

   ```text
   >>> round(15 / 9, 2)
   1.67
   >>> round(15 / 9)
   2
   >>> 4 / 9 * 100
   44.44444444444444
   >>> round(4 / 9 * 100)
   44
   ```

   Com dois argumentos, separados por uma vírgula, o segundo diz quantas casas decimais ficam: `round(15 / 9, 2)` dá `1.67`. Com um só argumento, arredonda às unidades e dá um inteiro. As duas últimas linhas são a percentagem de vitórias: 4 vitórias em 9 jogos, vezes 100. A divisão e a multiplicação estão no mesmo nível, e fazem-se da esquerda para a direita: primeiro 4 a dividir por 9, depois vezes 100.

4. Sai da consola: escreve `exit()` e carrega em Enter. O que deves ver: a linha do terminal outra vez, a acabar em `fp-python`.

### Paragem 4

Sabes como o Python divide e arredonda. Não ficou nenhum ficheiro novo na pasta, porque o que se escreve na consola não se guarda.

Pensa antes de continuares: uma equipa com 12 pontos em 4 jogos, que pontos por jogo vai mostrar o programa, `3` ou `3.0`? A resposta: `3.0`, porque a conta se faz com `/`, e o `/` dá sempre um `float`, mesmo numa conta exata. O `round(..., 2)` não muda isso, porque também devolve um `float`.

## Fase 5: Os pontos por jogo e a percentagem, com `/` e `round`

Com o que viste na consola, já podes pôr as duas contas no programa. Os pontos por jogo são os pontos a dividir pelos jogos, arredondados a duas casas decimais. A percentagem de vitórias é a parte dos jogos que a equipa ganhou, vezes 100, arredondada às unidades.

O resultado do `round` pode ficar numa variável, como qualquer outro valor. O `round` recebe o resultado da divisão e devolve-o arredondado, e é esse valor arredondado que fica guardado. Para saber mais, lê a secção "`round`, o arredondamento" do [guia](../02-dados-e-interacao.md).

1. Em `resumo_equipa.py`, a seguir à linha 15, a dos pontos, acrescenta estas quatro linhas:

   ```python
   # O / dá sempre um float; o round deixa-o com duas casas decimais.
   pontos_por_jogo = round(pontos / jogos, 2)
   # Da esquerda para a direita: primeiro a divisão, depois a multiplicação por 100.
   percentagem_vitorias = round(vitorias / jogos * 100)
   ```

   Leitura guiada: cada linha tem uma conta dentro de uma chamada ao `round`. O Python faz primeiro a conta dos parênteses, depois chama o `round` com o resultado e guarda na variável o valor que ele devolve. As duas linhas usam `jogos` e `pontos`, e por isso ficam depois das linhas onde essas variáveis nascem.

2. No fim do ficheiro, depois do `print` dos pontos, acrescenta estes dois `print`:

   ```python
   print("Pontos por jogo:", pontos_por_jogo)
   print("Percentagem de vitórias:", percentagem_vitorias)
   ```

   Muda também o comentário da linha 2, para dizer o que o programa faz agora: `# Nesta fase, o programa calcula também os pontos por jogo e a percentagem de vitórias.`

3. Guarda. Antes de correres, prevê as duas linhas novas, com o que viste na fase 4. Depois corre. O que deves ver no fim:

   ```text
   Pontos: 15
   Pontos por jogo: 1.67
   Percentagem de vitórias: 44
   ```

   Isto quer dizer que a divisão e o arredondamento correram como na consola. 15 a dividir por 9 dá 1.666..., que arredondado a duas casas decimais fica 1.67. E 4 a dividir por 9, vezes 100, dá 44.44..., que arredondado fica 44.

4. Experimenta o programa sem os arredondamentos. Na linha dos pontos por jogo, apaga o `round(` e o `, 2)`, para ficar `pontos_por_jogo = pontos / jogos`. Guarda, corre e repara na linha dos pontos por jogo: `Pontos por jogo: 1.6666666666666667`. O valor está certo, mas tem dezasseis casas decimais, que não ajudam ninguém a ler o resumo. Volta a pôr a linha como estava, com o `round(` e o `, 2)`, guarda e confirma que aparece outra vez `1.67`.

### Paragem 5

O programa mostra o resumo completo da equipa 10.º DS, com os pontos por jogo e a percentagem de vitórias.

O ficheiro `resumo_equipa.py` completo, como deve estar agora:

```python
# resumo_equipa.py: o resumo de uma equipa no torneio de futebol da escola.
# Nesta fase, o programa calcula também os pontos por jogo e a percentagem de vitórias.

# As regras do torneio: uma vitória vale 3 pontos, um empate vale 1.
PONTOS_POR_VITORIA = 3
PONTOS_POR_EMPATE = 1

nome_equipa = "10.º DS"
vitorias = 4
empates = 3
derrotas = 2

jogos = vitorias + empates + derrotas
# As multiplicações fazem-se antes da soma, por isso não são precisos parênteses.
pontos = vitorias * PONTOS_POR_VITORIA + empates * PONTOS_POR_EMPATE
# O / dá sempre um float; o round deixa-o com duas casas decimais.
pontos_por_jogo = round(pontos / jogos, 2)
# Da esquerda para a direita: primeiro a divisão, depois a multiplicação por 100.
percentagem_vitorias = round(vitorias / jogos * 100)

print("Equipa:", nome_equipa)
print("Jogos:", jogos)
print("Vitórias:", vitorias)
print("Empates:", empates)
print("Derrotas:", derrotas)
print("Pontos:", pontos)
print("Pontos por jogo:", pontos_por_jogo)
print("Percentagem de vitórias:", percentagem_vitorias)
```

Pensa antes de continuares: porque é que os pontos por jogo se calculam com `/`, e não com `//`? A resposta: com `//`, 15 a dividir por 9 dava 1, só as vezes que o 9 cabe inteiro no 15. Uma média tem parte decimal, e o 1 escondia que a equipa fez quase 1.7 pontos por jogo.

## Fase 6: Ler os resultados do teclado e convertê-los

O programa ainda só serve para a equipa 10.º DS. Para mostrar o resumo de outra equipa, era preciso mudar as linhas 8 a 11 e correr outra vez. Um programa útil pergunta os resultados a quem o usa.

No pseudocódigo, uma leitura levava duas linhas, a pergunta e o `ler valor`:

```text
Escreve: "Vitórias?"
int vitorias = ler valor
```

No Python, as duas juntam-se numa só, com a função `input`. O `input` escreve a pergunta, espera que a pessoa escreva e carregue em Enter, e devolve o que ela escreveu. Mas devolve sempre um texto. Mesmo que a pessoa escreva 4, chega ao programa o texto `"4"`, com um algarismo lá dentro, e não o número quatro. O passo 1 mostra na consola porque é que isso importa. Para fazer contas, converte-se o texto num número com o `int`, logo na leitura. Para saber mais, lê as secções "Ler do teclado com `input`" e "Converter o texto lido num número: `int` e `float`" do [guia](../02-dados-e-interacao.md).

1. Vê primeiro, na consola, o que acontece quando um número está escrito como texto, entre aspas. Abre a consola, como na fase 4, com `python`, ou `python3` no macOS. Prevê cada resultado antes de carregares em Enter:

   ```text
   >>> "4" + "3"
   '43'
   >>> int("4") + 3
   7
   >>> type("4")
   <class 'str'>
   >>> type(int("4"))
   <class 'int'>
   ```

   Entre dois textos, o `+` não soma: junta-os, um a seguir ao outro, e dá o texto `'43'`. A consola mostra os textos entre aspas simples, para se ver que são textos. A função `int` converte o texto `"4"` no número 4, e aí o `+` já soma. Na última linha há uma chamada dentro de outra, que se lê de dentro para fora. Primeiro faz-se o `int`, e depois o `type` do que ele devolveu. É isto que vais fazer no programa, a seguir.

   Sai da consola com `exit()`, para voltares ao terminal.

2. Em `resumo_equipa.py`, substitui as quatro linhas dos resultados escritos no programa, de `nome_equipa = "10.º DS"` a `derrotas = 2`, por estas cinco:

   ```python
   # O nome fica como texto; os resultados convertem-se em int, para as contas.
   nome_equipa = input("Nome da equipa? ")
   vitorias = int(input("Vitórias? "))
   empates = int(input("Empates? "))
   derrotas = int(input("Derrotas? "))
   ```

   Leitura guiada: o nome da equipa é um texto, e por isso o que o `input` devolve fica como está. As outras três linhas leem-se de dentro para fora. Primeiro, o `input` faz a pergunta e devolve o texto escrito. Depois, o `int` converte esse texto num número inteiro. Só então o número fica guardado na variável. O espaço depois do ponto de interrogação, dentro das aspas, separa a pergunta da resposta.

3. Antes da linha `print("Equipa:", nome_equipa)`, acrescenta um `print()` vazio, com um comentário por cima:

   ```python
   # Uma linha em branco separa as perguntas do resumo.
   print()
   ```

   Substitui também as duas linhas de comentário do início do ficheiro por estas três, que dizem o que o programa faz agora:

   ```python
   # resumo_equipa.py: o resumo de uma equipa no torneio de futebol da escola.
   # Lê o nome da equipa e os resultados, e mostra os jogos, os pontos,
   # os pontos por jogo e a percentagem de vitórias.
   ```

   Com estas mudanças, os números das linhas passam a ser os do ficheiro completo da paragem 6. As mensagens de erro dos passos seguintes usam esses números.

4. Guarda. Antes de correres, prevê o que aparece se escreveres 10.º DS, 4, 3 e 2. Depois corre. O programa escreve a primeira pergunta e fica à espera. Escreve `10.º DS` e carrega em Enter, e faz o mesmo com as outras três respostas. O que deves ver:

   ```text
   Nome da equipa? 10.º DS
   Vitórias? 4
   Empates? 3
   Derrotas? 2

   Equipa: 10.º DS
   Jogos: 9
   Vitórias: 4
   Empates: 3
   Derrotas: 2
   Pontos: 15
   Pontos por jogo: 1.67
   Percentagem de vitórias: 44
   ```

   O que está a seguir a cada pergunta é o que tu escreveste. O resumo é igual ao da fase 5, e isso quer dizer que a leitura e a conversão funcionam. Se o programa ficar parado depois de uma pergunta, está à espera da tua resposta.

5. Provoca um erro de propósito: tira a conversão das vitórias. Muda a linha das vitórias para `vitorias = input("Vitórias? ")`, sem o `int(` e sem o último parêntese. Guarda, corre e escreve as mesmas quatro respostas. O que deves ver:

   ```text
   Nome da equipa? 10.º DS
   Vitórias? 4
   Empates? 3
   Derrotas? 2
   Traceback (most recent call last):
     File "C:\Users\aluno\Documents\fp-python\resumo_equipa.py", line 15, in <module>
       jogos = vitorias + empates + derrotas
               ~~~~~~~~~^~~~~~~~~
   TypeError: can only concatenate str (not "int") to str
   ```

   A última linha quer dizer "erro de tipo: só se consegue juntar um texto a outro texto, e não um `int`". As de cima dizem que foi na linha 15, na soma dos jogos. Por baixo da linha, os `~` sublinham as partes da conta, e o `^` aponta o `+` que falhou. Isto acontece porque, sem a conversão, `vitorias` guarda o texto `"4"`, e o `+` entre um texto e um número não funciona. Repara que a mensagem aponta a linha 15, mas a causa está na linha 11, na leitura sem `int`. A linha apontada é onde o Python deu pelo problema, e não onde ele nasceu. Para corrigir, volta a pôr a linha como estava, `vitorias = int(input("Vitórias? "))`, guarda e corre outra vez.

6. Provoca outro erro, agora com o programa certo. Corre-o e, à pergunta das vitórias, escreve `quatro` em vez de 4. O que deves ver:

   ```text
   Nome da equipa? 10.º DS
   Vitórias? quatro
   Traceback (most recent call last):
     File "C:\Users\aluno\Documents\fp-python\resumo_equipa.py", line 11, in <module>
       vitorias = int(input("Vitórias? "))
                  ~~~^^^^^^^^^^^^^^^^^^^^^
   ValueError: invalid literal for int() with base 10: 'quatro'
   ```

   A última linha quer dizer "erro de valor: escrita inválida para um `int` na base 10". No fim, mostra o texto que o `int` não conseguiu converter. A base 10 é a numeração de todos os dias, com os algarismos de 0 a 9. A conversão está no sítio, mas o texto escrito não é um número. Este programa confia que a pessoa escreve números, e ainda não consegue evitar este erro. Corre o programa outra vez, com números.

### Paragem 6

O programa pergunta os resultados de qualquer equipa e mostra o resumo dela.

O ficheiro `resumo_equipa.py` completo, como deve estar agora:

```python
# resumo_equipa.py: o resumo de uma equipa no torneio de futebol da escola.
# Lê o nome da equipa e os resultados, e mostra os jogos, os pontos,
# os pontos por jogo e a percentagem de vitórias.

# As regras do torneio: uma vitória vale 3 pontos, um empate vale 1.
PONTOS_POR_VITORIA = 3
PONTOS_POR_EMPATE = 1

# O nome fica como texto; os resultados convertem-se em int, para as contas.
nome_equipa = input("Nome da equipa? ")
vitorias = int(input("Vitórias? "))
empates = int(input("Empates? "))
derrotas = int(input("Derrotas? "))

jogos = vitorias + empates + derrotas
# As multiplicações fazem-se antes da soma, por isso não são precisos parênteses.
pontos = vitorias * PONTOS_POR_VITORIA + empates * PONTOS_POR_EMPATE
# O / dá sempre um float; o round deixa-o com duas casas decimais.
pontos_por_jogo = round(pontos / jogos, 2)
# Da esquerda para a direita: primeiro a divisão, depois a multiplicação por 100.
percentagem_vitorias = round(vitorias / jogos * 100)

# Uma linha em branco separa as perguntas do resumo.
print()
print("Equipa:", nome_equipa)
print("Jogos:", jogos)
print("Vitórias:", vitorias)
print("Empates:", empates)
print("Derrotas:", derrotas)
print("Pontos:", pontos)
print("Pontos por jogo:", pontos_por_jogo)
print("Percentagem de vitórias:", percentagem_vitorias)
```

Pensa antes de continuares: porque é que o nome da equipa não leva `int`? A resposta: o nome é um texto, e o `input` já devolve um texto. Com `int(input("Nome da equipa? "))`, o programa tentava converter `10.º DS` num número, e parava com um `ValueError` logo na primeira pergunta.

## Fase 7: Testar com uma tabela de casos

O programa funcionou com a equipa 10.º DS, mas um caso só não chega para confiar nele. Na algoritmia, um algoritmo testava-se com casos de teste: entradas escolhidas de propósito, com o resultado esperado calculado à mão, a partir do enunciado. Em Python é igual, com uma vantagem: o computador faz a parte do trace, e tu comparas.

O resultado esperado calcula-se antes de correr o programa, e nunca a partir do que ele mostra. Se o copiasses do ecrã, a tabela concordava sempre com o programa, mesmo que ele estivesse errado.

1. Lê os cinco casos de teste. Cada caso foi escolhido por uma razão, que está na primeira coluna.

   | Caso | Vitórias, empates, derrotas |
   | --- | --- |
   | Um caso normal | 4, 3, 2 |
   | Só vitórias | 5, 0, 0 |
   | Só derrotas | 0, 0, 3 |
   | Um só jogo, empatado | 0, 1, 0 |
   | Nenhum jogo | 0, 0, 0 |

   Antes de correres, calcula o que o programa deve mostrar em cada caso: os jogos, os pontos, os pontos por jogo e a percentagem. Nos pontos por jogo, lembra-te de que o `/` dá sempre um `float`, e pensa no resultado como o Python o mostra. No último caso, pensa bem no que acontece à divisão.

2. Corre o programa cinco vezes, uma por caso. O nome da equipa não muda as contas: escreve o que quiseres. Em cada caso, compara o que o programa mostra com o que calculaste.

   Os quatro primeiros casos devem dar estes resultados:

   | Caso | Jogos | Pontos | Pontos por jogo | Percentagem |
   | --- | ---: | ---: | ---: | ---: |
   | 4, 3, 2 | 9 | 15 | `1.67` | 44 |
   | 5, 0, 0 | 5 | 15 | `3.0` | 100 |
   | 0, 0, 3 | 3 | 0 | `0.0` | 0 |
   | 0, 1, 0 | 1 | 1 | `1.0` | 0 |

   Se algum caso teu não coincidir, segue a rotina de cinco passos. Primeiro, confirma a conta à mão. Depois, confirma se o programa está igual ao da paragem 6.

3. O último caso, a equipa sem nenhum jogo, dá isto:

   ```text
   Nome da equipa? Teste
   Vitórias? 0
   Empates? 0
   Derrotas? 0
   Traceback (most recent call last):
     File "C:\Users\aluno\Documents\fp-python\resumo_equipa.py", line 19, in <module>
       pontos_por_jogo = round(pontos / jogos, 2)
                               ~~~~~~~^~~~~~~
   ZeroDivisionError: division by zero
   ```

   A última linha quer dizer "erro de divisão por zero". Com 0 jogos, a conta dos pontos por jogo é 0 a dividir por 0, que não tem resultado, nem na matemática nem no Python. É um erro de execução, na linha 19. Uma equipa sem jogos não tem pontos por jogo nem percentagem de vitórias, e era essa a resposta certa à mão. Este programa ainda não sabe decidir não fazer uma conta: faz sempre todas as linhas, de cima para baixo. Por isso, só serve para equipas com pelo menos um jogo.

### Paragem 7

Correste os cinco casos de teste e comparaste cada um com o que calculaste antes. Os quatro primeiros coincidem. O quinto mostra o limite do programa: uma equipa tem de ter pelo menos um jogo.

Pensa antes de continuares: no caso 5, 0, 0, porque é que o programa mostra `3.0`, e não `3`? E porque é que vale a pena testar o caso 0, 0, 3? A resposta: `3.0` porque 15 a dividir por 5 se faz com `/`, que dá sempre um `float`. O caso 0, 0, 3 confirma que o programa se porta bem quando a equipa não tem nenhum ponto. A divisão de 0 por 3 é possível, e dá `0.0`.

## Problemas frequentes

### `TypeError` numa linha de contas, depois de um `input`

Falta o `int` à volta de um `input`. O texto lido ficou como texto, e o `+` não soma um texto com um número. A linha da mensagem é a da conta, mas a causa está na linha da leitura. Confirma que cada resultado lido tem `int(input(...))`, com os dois parênteses no fim.

### `ValueError: invalid literal for int() with base 10`

Escreveste uma resposta que não é um número inteiro, como `quatro`, `4.5` ou nada. O texto que falhou aparece entre aspas no fim da mensagem. Corre o programa outra vez e escreve um número inteiro, sem espaços nem letras.

### `NameError: name '...' is not defined`

Um nome está escrito de outra maneira da linha onde a variável nasceu: uma letra a menos, uma maiúscula, um acento. A sugestão "Did you mean", no fim da mensagem, costuma dar o nome certo. Também acontece se uma linha usar uma variável antes da linha onde ela nasce: as contas têm de vir depois das leituras.

### `SyntaxError: '(' was never closed`

Falta fechar um parêntese, quase sempre numa linha com `int(input(...))`, que precisa de dois no fim. Quer dizer "o parêntese nunca foi fechado". Os sinais `^` apontam para o parêntese que ficou aberto. Conta os parênteses que abrem e os que fecham.

### `ZeroDivisionError: division by zero`

A equipa tem 0 jogos, e o programa tentou dividir por zero. Este programa só serve para equipas com pelo menos um jogo. Corre-o outra vez com outros resultados.

### Os pontos estão errados, e não aparece nenhuma mensagem

É um erro de lógica, quase sempre na conta dos pontos. Confirma a linha `pontos = vitorias * PONTOS_POR_VITORIA + empates * PONTOS_POR_EMPATE`, sem parênteses, e confirma os valores das duas constantes.

### Os pontos por jogo aparecem com muitas casas decimais

Falta o `round(..., 2)` à volta da divisão. A conta está certa, mas fica com dezasseis casas decimais. Confirma a linha `pontos_por_jogo = round(pontos / jogos, 2)`.

### O resultado não muda depois de corrigires o código

O ficheiro não foi guardado. O Python corre o que está no disco. Guarda com Ctrl+S, ou Cmd+S no macOS, e corre outra vez.

## Desafios

Estes desafios são para quem acabou as sete fases. Faz cada um numa cópia do teu programa, ou no mesmo ficheiro, e testa-o com casos calculados à mão antes de correres.

1. O quadro do torneio mostra a percentagem com o sinal colado ao número, como `Percentagem de vitórias: 44%`. Muda a última linha do resumo para aparecer exatamente assim, sem espaço antes do `%`. Pista: com as vírgulas, o `print` põe sempre um espaço entre os valores. A secção "Juntar textos com `+` e `str`" do [guia](../02-dados-e-interacao.md) mostra como colar um número a um texto.
2. Acrescenta ao programa duas perguntas, os golos marcados e os golos sofridos. No resumo, mostra a diferença de golos e a média de golos marcados por jogo, arredondada a uma casa decimal. Com 4, 3, 2, 14 golos marcados e 9 sofridos, a diferença é 5. Pensa no que a diferença deve mostrar numa equipa que sofreu mais golos do que marcou.
3. Acrescenta ao resumo os pontos que ficaram por ganhar: quantos pontos faltam à equipa para ter o máximo possível nos jogos que fez. Com 4, 3, 2, são 12. Pista: calcula primeiro quantos pontos teria a equipa se ganhasse todos os jogos.

## Antes de terminares

- [ ] O `resumo_equipa.py` está guardado na pasta `fp-python`, igual ao da paragem 6, e corre sem erros com números inteiros e pelo menos um jogo.
- [ ] Correste os cinco casos de teste da fase 7 e comparaste cada um com o que calculaste antes de correr.
- [ ] Provocaste e corrigiste os quatro erros do laboratório. São o nome mal escrito, a conta com os parênteses trocados, a conversão esquecida e o texto que não é um número.
- [ ] Sabes dizer de que tipo é cada erro: de sintaxe, de execução ou de lógica.
- [ ] Consegues explicar, por palavras tuas, porque é que os pontos por jogo aparecem com parte decimal.
- [ ] Consegues explicar, por palavras tuas, porque é que o valor lido com o `input` se converte com o `int` antes de entrar numa conta.

![Rodapé](../../imagens/rodape.png)
