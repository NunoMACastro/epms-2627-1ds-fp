![Cabeçalho](../../imagens/cabecalho.png)

# Laboratório: Dados e interação

## O que vais construir

Vais construir `resumo_equipa.py`, um programa que lê os resultados de uma equipa no torneio de futebol da escola e mostra o resumo dela. Uma vitória vale 3 pontos, um empate vale 1, e uma derrota não vale nada.

No fim, com a equipa 10.º DS, o terminal fica assim:

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

1. [Fase 1: Uma variável guarda um valor com um nome](#fase-1-uma-variável-guarda-um-valor-com-um-nome)
2. [Fase 2: A ordem das contas é a da matemática](#fase-2-a-ordem-das-contas-é-a-da-matemática)
3. [Fase 3: As constantes têm o nome em maiúsculas](#fase-3-as-constantes-têm-o-nome-em-maiúsculas)
4. [Fase 4: A divisão com `/` dá sempre um `float`](#fase-4-a-divisão-com--dá-sempre-um-float)
5. [Fase 5: O `round` arredonda um número](#fase-5-o-round-arredonda-um-número)
6. [Fase 6: O `input` lê sempre um texto](#fase-6-o-input-lê-sempre-um-texto)
7. [Fase 7: Converter o texto lido num número](#fase-7-converter-o-texto-lido-num-número)
8. [Fase 8: Os casos de teste, calculados à mão](#fase-8-os-casos-de-teste-calculados-à-mão)

## O que precisas

- A pasta `fp-python`, aberta no VS Code, com o menu File e a opção `Open Folder...`. Deves ver `FP-PYTHON` no painel Explorer. Se não a tiveres, faz primeiro [Preparar o projeto](01-do-pseudocodigo-ao-python-laboratorio.md#preparar-o-projeto), no laboratório do tema 01.
- O Python 3. No terminal, que se abre no menu Terminal, com a opção New Terminal, escreve `python --version`. Deve aparecer uma linha como `Python 3.13.2`, com o 3 em primeiro. No macOS, o comando é `python3 --version`. No Windows, se o `python` não funcionar, é `py --version`.

## Fase 1: Uma variável guarda um valor com um nome

O programa guarda os resultados da equipa em variáveis e mostra-os. Em Python, uma variável escreve-se sem o tipo à frente. Rever: [Uma variável guarda um valor com um nome](../02-dados-e-interacao.md#uma-variável-guarda-um-valor-com-um-nome).

1. O resumo tem de se lembrar dos resultados da equipa, e começa pelo nome e pelas vitórias. No painel Explorer, passa o rato por cima de `FP-PYTHON` e carrega no ícone `New File...`. Escreve `resumo_equipa.py`, carrega em Enter e escreve no ficheiro esta primeira versão:

   ```python
   # resumo_equipa.py: o resumo de uma equipa no torneio de futebol da escola.

   nome_equipa = "10.º DS"
   vitorias = 4

   print("Equipa:", nome_equipa)
   print("Vitórias:", vitorias)
   ```

2. Guarda com Ctrl+S, ou Cmd+S no macOS. Depois, no terminal, corre o programa:

   ```bash
   python resumo_equipa.py
   ```

   No macOS, o comando é `python3 resumo_equipa.py`. No Windows, se o `python` não funcionar, é `py resumo_equipa.py`. Ao longo do laboratório, usa sempre o comando que funcionou.

   O que deves ver:

   ```text
   Equipa: 10.º DS
   Vitórias: 4
   ```

   Isto quer dizer que as duas variáveis guardaram os valores. Se aparecer outra coisa, vê [Se alguma coisa falhar](#se-alguma-coisa-falhar).

3. Faltam os empates e as derrotas. Em `resumo_equipa.py`, a seguir à linha `vitorias = 4`, acrescenta:

   ```python
   empates = 3
   derrotas = 2
   ```

   No fim do ficheiro, acrescenta:

   ```python
   print("Empates:", empates)
   print("Derrotas:", derrotas)
   ```

   Guarda e corre outra vez. O que deves ver: as quatro linhas, com `Empates: 3` e `Derrotas: 2` no fim.

4. Experimenta a diferença entre um texto e uma variável. Na linha 9, põe aspas à volta do nome da variável, para ficar `print("Vitórias:", "vitorias")`. Antes de correres, prevê o que aparece na segunda linha. Guarda e corre.

   O que deves ver na segunda linha: `Vitórias: vitorias`. Com aspas, é um texto, e o `print` escreve as letras. Tira as aspas e guarda.

5. Provoca um erro, para o reconheceres quando te acontecer. Na linha 9, apaga o `s` do fim do nome, para ficar `print("Vitórias:", vitoria)`. Guarda e corre. O que deves ver:

   ```text
   Equipa: 10.º DS
   Traceback (most recent call last):
     File "C:\Users\aluno\Documents\fp-python\resumo_equipa.py", line 9, in <module>
       print("Vitórias:", vitoria)
                          ^^^^^^^
   NameError: name 'vitoria' is not defined. Did you mean: 'vitorias'?
   ```

   Para o Python, `vitoria` é outra variável, que nunca nasceu. A linha 8 correu, e o programa parou na 9. Volta a pôr o `s`, guarda e corre outra vez.

### Paragem 1

O programa mostra o nome e os resultados da equipa, em quatro linhas.

Pensa antes de continuares: em pseudocódigo, como se escrevia a linha 4? A resposta: `int vitorias = 4`, com o tipo à frente. Em Python, o tipo não se escreve, porque o Python o vê no valor.

## Fase 2: A ordem das contas é a da matemática

O programa passa a calcular quantos jogos a equipa fez e quantos pontos tem. As multiplicações fazem-se antes da soma, como na matemática. Rever: [A ordem das contas é a da matemática](../02-dados-e-interacao.md#a-ordem-das-contas-é-a-da-matemática).

1. Os jogos são as vitórias, mais os empates, mais as derrotas. Em `resumo_equipa.py`, a seguir à linha `derrotas = 2`, acrescenta uma linha em branco e esta conta:

   ```python
   jogos = vitorias + empates + derrotas
   ```

   A seguir ao `print` da equipa, acrescenta:

   ```python
   print("Jogos:", jogos)
   ```

   Guarda e corre. O que deves ver: uma linha nova, `Jogos: 9`, a seguir à da equipa. A conta tem de vir depois das linhas onde nascem os valores que usa.

2. Os pontos são as vitórias vezes 3, mais os empates vezes 1. A seguir à linha `jogos = vitorias + empates + derrotas`, acrescenta:

   ```python
   # As multiplicações fazem-se antes da soma, por isso não são precisos parênteses.
   pontos = vitorias * 3 + empates * 1
   ```

   No fim do ficheiro, acrescenta:

   ```python
   print("Pontos:", pontos)
   ```

   Guarda e corre. O que deves ver no fim: `Pontos: 15`. Isto quer dizer que a conta está certa: 4 vezes 3, mais 3 vezes 1, dá 12 mais 3. A derrota não entra na conta, porque vale zero.

3. Provoca um erro de lógica. Na linha 10, acrescenta parênteses, para ficar `pontos = (vitorias + empates) * 3`. Antes de correres, prevê quantos pontos aparecem. Guarda e corre.

   O que deves ver na última linha: `Pontos: 21`. Não há mensagem nenhuma, mas o resultado está errado. Os parênteses fizeram a soma primeiro, e é como se os empates valessem tanto como as vitórias. Só o apanhas porque sabes que deviam ser 15. Volta a pôr a linha como estava, guarda e confirma que aparece `Pontos: 15`.

### Paragem 2

O programa mostra `Jogos: 9` e `Pontos: 15`.

Pensa antes de continuares: se escrevesses `pontos = empates * 1 + vitorias * 3`, o resultado mudava? A resposta: não. As multiplicações fazem-se primeiro, seja qual for a ordem em que estão escritas, e 3 mais 12 dá os mesmos 15.

## Fase 3: As constantes têm o nome em maiúsculas

As regras do torneio passam a ter um nome. Uma constante é uma variável com o nome todo em maiúsculas, que se combina não mudar. Rever: [As constantes têm o nome em maiúsculas](../02-dados-e-interacao.md#as-constantes-têm-o-nome-em-maiúsculas).

1. O 3 e o 1 da conta dos pontos são regras do torneio, e quem lê tem de adivinhar o que querem dizer. Em `resumo_equipa.py`, a seguir à linha 2, que está em branco, acrescenta estas três linhas e mais uma linha em branco:

   ```python
   # As regras do torneio: uma vitória vale 3 pontos, um empate vale 1.
   PONTOS_POR_VITORIA = 3
   PONTOS_POR_EMPATE = 1
   ```

2. A conta dos pontos desceu para a linha 14. Substitui-a por esta, com os nomes no lugar dos números:

   ```python
   pontos = vitorias * PONTOS_POR_VITORIA + empates * PONTOS_POR_EMPATE
   ```

   Guarda e corre. O que deves ver: o mesmo resumo, com `Jogos: 9` e `Pontos: 15`. Isto quer dizer que trocar os números pelos nomes não muda nenhuma conta, e muda só a forma como o programa se lê.

### Paragem 3

O programa mostra o mesmo resumo, e as regras do torneio estão no início, com nome.

O ficheiro `resumo_equipa.py` completo, como deve estar agora:

```python
# resumo_equipa.py: o resumo de uma equipa no torneio de futebol da escola.

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

As constantes vêm primeiro, para quem lê conhecer as regras. Depois vêm os dados, as contas que os usam e, no fim, o que aparece no ecrã.

Pensa antes de continuares: se o torneio passasse a dar 2 pontos por empate, que linha mudavas? A resposta: só a linha 5, para `PONTOS_POR_EMPATE = 2`, e a conta ficava igual.

## Fase 4: A divisão com `/` dá sempre um `float`

Vês na consola como o Python divide e pões os pontos por jogo no programa. Uma média faz-se com `/`, porque tem parte decimal. Rever: [A divisão com `/` dá sempre um `float`](../02-dados-e-interacao.md#a-divisão-com--dá-sempre-um-float).

1. Experimenta a conta na consola, onde cada linha mostra logo o resultado. No terminal, escreve o comando que tens usado, sem o nome do ficheiro, e carrega em Enter. O que deves ver: umas linhas com a versão do Python e, na última, `>>>`.

2. Escreve só o que está a seguir a cada `>>>`. Antes de carregares em Enter em `18 / 9`, prevê o resultado.

   ```text
   >>> 15 / 9
   1.6666666666666667
   >>> 18 / 9
   2.0
   >>> 15 // 9
   1
   >>> type(18 / 9)
   <class 'float'>
   ```

   O `/` dá um `float`, até em `18 / 9`, que é uma conta exata. O `//` é o `div` do pseudocódigo: diz quantas vezes o 9 cabe inteiro no 15. O `type` diz o tipo de um valor, o nome entre aspas.

3. Sai da consola: escreve `exit()` e carrega em Enter. O que deves ver: a linha do terminal outra vez, com `fp-python` no fim, antes do `>` ou do `%`.

4. Em `resumo_equipa.py`, a seguir à linha `pontos = vitorias * PONTOS_POR_VITORIA + empates * PONTOS_POR_EMPATE`, acrescenta a conta:

   ```python
   # O / dá sempre um float.
   pontos_por_jogo = pontos / jogos
   ```

   No fim do ficheiro, acrescenta:

   ```python
   print("Pontos por jogo:", pontos_por_jogo)
   ```

   Guarda e corre. O que deves ver no fim: `Pontos por jogo: 1.6666666666666667`. O valor está certo, mas tem casas decimais a mais para um resumo.

### Paragem 4

O programa mostra os pontos por jogo, com todas as casas decimais.

Pensa antes de continuares: uma equipa com 12 pontos em 4 jogos mostra `3` ou `3.0`? A resposta: `3.0`, porque a conta se faz com `/`, mesmo sendo exata.

## Fase 5: O `round` arredonda um número

Arredondas os pontos por jogo e acrescentas a percentagem de vitórias. O `round` recebe um número e devolve-o arredondado. Rever: [O `round` arredonda um número](../02-dados-e-interacao.md#o-round-arredonda-um-número).

1. Experimenta primeiro na consola, que abres como na fase 4. Escreve só o que está a seguir a cada `>>>`:

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

   Com dois argumentos, o segundo diz quantas casas decimais ficam. Com um só, arredonda às unidades. As duas últimas contas são a percentagem de vitórias, com 4 vitórias em 9 jogos. Sai da consola com `exit()`.

2. Em `resumo_equipa.py`, substitui o comentário `# O / dá sempre um float.` e a linha `pontos_por_jogo = pontos / jogos` por estas quatro, que juntam a percentagem:

   ```python
   # O / dá sempre um float; o round deixa-o com duas casas decimais.
   pontos_por_jogo = round(pontos / jogos, 2)
   # Da esquerda para a direita: primeiro a divisão, depois a multiplicação por 100.
   percentagem_vitorias = round(vitorias / jogos * 100)
   ```

3. No fim do ficheiro, acrescenta:

   ```python
   print("Percentagem de vitórias:", percentagem_vitorias)
   ```

   Guarda e corre. O que deves ver no fim:

   ```text
   Pontos: 15
   Pontos por jogo: 1.67
   Percentagem de vitórias: 44
   ```

   Isto quer dizer que o `round` deixou os dois valores prontos a ler.

### Paragem 5

O programa mostra o resumo completo da equipa 10.º DS.

O ficheiro `resumo_equipa.py` completo, como deve estar agora:

```python
# resumo_equipa.py: o resumo de uma equipa no torneio de futebol da escola.

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

As contas que usam `jogos` e `pontos` vêm depois das linhas onde esses valores nascem. Os `print` ficam todos no fim, depois de tudo calculado.

Pensa antes de continuares: porque é que os pontos por jogo não se calculam com `//`? A resposta: com `//`, 15 a dividir por 9 dava 1, e escondia que a equipa fez quase 1.7 pontos por jogo.

## Fase 6: O `input` lê sempre um texto

O programa passa a perguntar o nome da equipa. O `input` escreve a pergunta, espera pela resposta e devolve-a como texto. Rever: [O `input` lê sempre um texto](../02-dados-e-interacao.md#o-input-lê-sempre-um-texto).

1. Vê primeiro na consola o que o `input` devolve. Abre a consola e escreve só o que está a seguir a cada `>>>`. Quando aparecer a pergunta, escreve 4 e carrega em Enter. Antes de carregares em Enter na linha `resposta`, prevê se o valor aparece com aspas ou sem elas.

   ```text
   >>> resposta = input("Vitórias? ")
   Vitórias? 4
   >>> resposta
   '4'
   >>> type(resposta)
   <class 'str'>
   ```

   Aparece com aspas porque é um texto, com um algarismo lá dentro, e não o número quatro. O `str` é o `string` do pseudocódigo. Sai da consola com `exit()`.

2. Em `resumo_equipa.py`, substitui a linha `nome_equipa = "10.º DS"` por esta, para o programa servir para qualquer equipa:

   ```python
   nome_equipa = input("Nome da equipa? ")
   ```

   O espaço depois do ponto de interrogação, dentro das aspas, separa a pergunta da resposta.

3. Antes da linha `print("Equipa:", nome_equipa)`, acrescenta:

   ```python
   # Uma linha em branco separa a pergunta do resumo.
   print()
   ```

   Guarda e corre. O programa escreve a pergunta e fica à espera. Clica no terminal, escreve `10.º DS` e carrega em Enter. O que deves ver no início:

   ```text
   Nome da equipa? 10.º DS

   Equipa: 10.º DS
   Jogos: 9
   ```

   Isto quer dizer que o nome veio do teclado.

### Paragem 6

O programa pergunta o nome da equipa e mostra o resumo.

Pensa antes de continuares: o que muda no resumo se escreveres outro nome? A resposta: só a linha da equipa, porque as contas usam as vitórias, os empates e as derrotas, que ainda estão escritos no programa.

## Fase 7: Converter o texto lido num número

O programa passa a perguntar os resultados e converte cada resposta num número. A função `int` converte um texto num inteiro. Rever: [Converter o texto lido num número](../02-dados-e-interacao.md#converter-o-texto-lido-num-número) e [Quando o texto não é um número](../02-dados-e-interacao.md#quando-o-texto-não-é-um-número).

1. Vê primeiro na consola porque é preciso converter. Abre a consola e escreve só o que está a seguir a cada `>>>`:

   ```text
   >>> "4" + "3"
   '43'
   >>> int("4") + 3
   7
   ```

   Entre dois textos, o `+` não soma: junta-os. Depois de o `int` converter o texto, o `+` já soma. Sai da consola com `exit()`.

2. Em `resumo_equipa.py`, substitui as três linhas `vitorias = 4`, `empates = 3` e `derrotas = 2` por estas quatro:

   ```python
   # Os resultados convertem-se em int, para as contas.
   vitorias = int(input("Vitórias? "))
   empates = int(input("Empates? "))
   derrotas = int(input("Derrotas? "))
   ```

3. Guarda e corre. Escreve `10.º DS`, 4, 3 e 2, com Enter depois de cada resposta. O que deves ver:

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

   O resumo é igual ao da fase 5, e isso quer dizer que a leitura e a conversão funcionam. Se aparecer outra coisa, vê [Se alguma coisa falhar](#se-alguma-coisa-falhar).

4. Provoca um erro: tira a conversão das vitórias. Muda a linha 9 para `vitorias = input("Vitórias? ")`. Guarda, corre e escreve as mesmas respostas. O que deves ver no fim:

   ```text
   Traceback (most recent call last):
     File "C:\Users\aluno\Documents\fp-python\resumo_equipa.py", line 13, in <module>
       jogos = vitorias + empates + derrotas
               ~~~~~~~~~^~~~~~~~~
   TypeError: can only concatenate str (not "int") to str
   ```

   A mensagem aponta a linha 13, mas a causa está na linha 9, na leitura sem `int`. Volta a pôr a linha como estava, `vitorias = int(input("Vitórias? "))`, e guarda.

5. Provoca outro erro, agora com o programa certo. Corre-o e, à pergunta das vitórias, escreve `quatro`. O que deves ver no fim:

   ```text
   Traceback (most recent call last):
     File "C:\Users\aluno\Documents\fp-python\resumo_equipa.py", line 9, in <module>
       vitorias = int(input("Vitórias? "))
                  ~~~^^^^^^^^^^^^^^^^^^^^^
   ValueError: invalid literal for int() with base 10: 'quatro'
   ```

   A conversão está lá, mas o texto escrito não é um número. Este programa confia que a pessoa escreve números, e ainda não consegue evitar este erro.

### Paragem 7

O programa pergunta os resultados de qualquer equipa e mostra o resumo dela.

O ficheiro `resumo_equipa.py` completo, como deve estar agora:

```python
# resumo_equipa.py: o resumo de uma equipa no torneio de futebol da escola.

# As regras do torneio: uma vitória vale 3 pontos, um empate vale 1.
PONTOS_POR_VITORIA = 3
PONTOS_POR_EMPATE = 1

nome_equipa = input("Nome da equipa? ")
# Os resultados convertem-se em int, para as contas.
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

# Uma linha em branco separa a pergunta do resumo.
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

O programa lê, calcula e escreve, sempre por esta ordem. Desde a fase 5, mudaram as leituras e entrou a linha em branco, e as contas são as mesmas.

Pensa antes de continuares: porque é que o nome da equipa não leva `int`? A resposta: o nome é um texto, e o `input` já devolve um texto. Com o `int`, o programa parava com um `ValueError` logo na primeira pergunta.

## Fase 8: Os casos de teste, calculados à mão

Confirmas o programa com cinco casos, calculados antes de o correres. Se copiasses o resultado do ecrã, o caso concordava sempre com o programa. Rever: [Os casos de teste, calculados à mão](../02-dados-e-interacao.md#os-casos-de-teste-calculados-à-mão).

1. Antes de correres, calcula o que o programa deve mostrar em cada caso: os jogos, os pontos, os pontos por jogo e a percentagem. No último caso, pensa bem no que acontece à divisão.

   | Caso | Vitórias, empates, derrotas |
   | --- | --- |
   | Um caso normal | 4, 3, 2 |
   | Só vitórias | 5, 0, 0 |
   | Só derrotas | 0, 0, 3 |
   | Um só jogo, empatado | 0, 1, 0 |
   | Nenhum jogo | 0, 0, 0 |

2. Corre o programa uma vez por caso, e escreve o nome que quiseres. Compara o que aparece com o que calculaste. Os quatro primeiros casos devem dar:

   | Caso | Jogos | Pontos | Pontos por jogo | Percentagem |
   | --- | ---: | ---: | ---: | ---: |
   | 4, 3, 2 | 9 | 15 | `1.67` | 44 |
   | 5, 0, 0 | 5 | 15 | `3.0` | 100 |
   | 0, 0, 3 | 3 | 0 | `0.0` | 0 |
   | 0, 1, 0 | 1 | 1 | `1.0` | 0 |

   Se algum caso não coincidir, confirma primeiro a tua conta à mão e depois se o programa está igual ao da paragem 7.

3. O último caso, a equipa sem nenhum jogo, dá isto no fim:

   ```text
   Traceback (most recent call last):
     File "C:\Users\aluno\Documents\fp-python\resumo_equipa.py", line 17, in <module>
       pontos_por_jogo = round(pontos / jogos, 2)
                               ~~~~~~~^~~~~~~
   ZeroDivisionError: division by zero
   ```

   Com 0 jogos, a conta é 0 a dividir por 0, que não tem resultado. Este programa faz sempre todas as linhas, de cima para baixo, e por isso só serve para equipas com pelo menos um jogo.

### Paragem 8

Comparaste os cinco casos com o que calculaste antes. Os quatro primeiros coincidem, e o quinto mostra o limite do programa.

Pensa antes de continuares: que caso mostrou um problema que o 4, 3, 2 nunca mostraria? A resposta: o 0, 0, 0, porque só aí há uma divisão por zero.

## Se alguma coisa falhar

1. Guardaste o ficheiro? O Python corre o que está no disco, e não o que vês no ecrã. No VS Code, uma bola cheia no separador do ficheiro quer dizer que há alterações por guardar.
2. Estás na pasta certa? No terminal, o texto antes do cursor tem de ter `fp-python` no fim, antes do `>` ou do `%`. Se não acabar, fecha o terminal e abre outro, no menu Terminal, com a opção New Terminal.
3. Estás na consola do Python sem quereres? Se a linha começa por `>>>`, escreve `exit()` e carrega em Enter.
4. O programa ficou parado? A partir da fase 6, ele espera pelas tuas respostas. Para o parares a meio, carrega em Ctrl+C no terminal, também no macOS. Aparece uma mensagem que acaba em `KeyboardInterrupt`, que só quer dizer que o paraste tu.

### `NameError: name '...' is not defined`

Um nome está escrito de maneira diferente da linha onde a variável nasceu, ou a variável é usada antes dessa linha. A sugestão "Did you mean", no fim da mensagem, costuma dar o nome certo.

### `TypeError` numa linha de contas, depois de um `input`

Falta o `int` à volta de um `input`. A linha da mensagem é a da conta, mas a causa está na linha da leitura.

### `ValueError: invalid literal for int() with base 10`

Escreveste uma resposta que não é um número inteiro, como `quatro`, `4.5` ou nada. Corre o programa outra vez e escreve um número inteiro.

### `SyntaxError: '(' was never closed`

Falta fechar um parêntese, quase sempre numa linha com `int(input(...))`, que precisa de dois no fim. Os sinais `^` apontam para o parêntese que ficou aberto.

### Os pontos estão errados, e não aparece nenhuma mensagem

É um erro de lógica, quase sempre na conta dos pontos. Compara essa linha com a do ficheiro completo da paragem 7 e confirma os valores das duas constantes.

### A mensagem de erro não é igual à do laboratório

Num Python anterior ao 3.14, uma mensagem pode ter outras palavras ou não ter os sinais que apontam o sítio do erro. A palavra antes dos dois pontos, na última linha, é a mesma. O caminho do ficheiro, a seguir a `File`, é o do teu computador.

## Desafios

Faz cada desafio num ficheiro novo, como `desafio_1.py`, com o código do programa copiado para lá. Calcula os casos à mão antes de correres.

1. O quadro do torneio mostra a percentagem com o sinal colado ao número, como `Percentagem de vitórias: 44%`. Muda a última linha do resumo para aparecer exatamente assim. Pista: o `str` converte um número em texto, e `str(44)` dá `'44'`. Rever: [Juntar textos com `+` e `str`](../02-dados-e-interacao.md#juntar-textos-com--e-str).
2. Acrescenta ao programa duas perguntas, os golos marcados e os golos sofridos. No resumo, mostra a diferença de golos e a média de golos marcados por jogo, arredondada a uma casa decimal. Com os resultados 4, 3, 2, e com 14 golos marcados e 9 sofridos, a diferença é 5. Pensa no que a diferença deve mostrar numa equipa que sofreu mais golos do que marcou.
3. Acrescenta ao resumo os pontos que ficaram por ganhar: quantos pontos faltam à equipa para ter o máximo possível nos jogos que fez. Com 4, 3, 2, são 12. Pista: calcula primeiro quantos pontos teria a equipa se ganhasse todos os jogos.

## Antes de terminares

- [ ] O `resumo_equipa.py` está guardado na pasta `fp-python`, igual ao da paragem 7, e corre sem erros com números inteiros e pelo menos um jogo.
- [ ] Correste os cinco casos da fase 8 e comparaste cada um com o que calculaste antes.
- [ ] Provocaste os quatro erros do laboratório e voltaste a pôr o programa certo.

![Rodapé](../../imagens/rodape.png)
