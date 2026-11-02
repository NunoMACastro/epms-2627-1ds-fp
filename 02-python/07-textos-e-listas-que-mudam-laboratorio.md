![Cabeçalho](../imagens/cabecalho.png)

# Laboratório: Textos e listas que mudam

Laboratório do tema Textos e listas que mudam, do módulo Criar aplicações em linguagem de programação Python. Vais construir dois programas para o clube de videojogos da escola. Um arruma e confirma o código de um jogo, e o outro gere a fila para a consola do clube. Cada passo diz o que fazer, porquê e o que deves ver, e avanças ao teu ritmo. Tudo o que precisas está aqui; o [guia do tema](07-textos-e-listas-que-mudam.md) tem a teoria completa, para quem quiser saber mais.

## O que vais construir

O clube de videojogos de uma escola foi inventado para as aulas. Identifica cada jogo por um código como `PLA-01`: três letras do género, um hífen e dois algarismos. No fim deste laboratório, tens dois programas em Python:

- `codigo.py` lê um código escrito de qualquer maneira, como ` pla_01 `, arruma-o, confirma que tem a forma certa e mostra as suas partes numa frase;
- `fila.py` gere a fila para a consola do clube. Cada nome escrito entra no fim da fila, a palavra `próximo` chama o primeiro a jogar, e ninguém entra duas vezes.

Pelo caminho, ficas a saber ler um texto por posições, tirar-lhe fatias e usar os métodos dos textos. Ficas também a saber percorrer um texto carácter a carácter, escrever mensagens com f-strings e fazer crescer e encolher uma lista. Fazes ainda, no caderno, a tua **tabela das operações**. É uma tabela com cada operação que usaste, o que ela faz e se muda o valor original.

| Fase | O que muda | O que funciona no fim |
| --- | --- | --- |
| 1 | Nada no disco; experimentas na consola do Python | Sabes ler um carácter de um texto pela posição |
| 2 | Nada no disco; continuas na consola | Sabes tirar uma fatia de um texto |
| 3 | `codigo.py`, a primeira versão | O programa arruma o código escrito e separa o género e o número |
| 4 | `codigo.py`, com o hífen no sítio | O programa aceita um código escrito com outro separador |
| 5 | `codigo.py`, com a confirmação das letras | O programa recusa um código com o tamanho errado ou sem três letras no género |
| 6 | `codigo.py`, com a confirmação dos algarismos | O programa recusa também um código sem dois algarismos no número |
| 7 | `codigo.py`, com uma f-string | O programa mostra o código numa só frase |
| 8 | `fila.py`, a primeira versão | Os nomes entram um a um no fim da fila |
| 9 | `fila.py`, com o `próximo` | O primeiro da fila é chamado e sai dela, e o programa não para com a fila vazia |
| 10 | `fila.py`, completo | Ninguém entra duas vezes, e no fim aparece quem ficou |

No fim, a tua pasta fica assim, com os ficheiros dos laboratórios anteriores e mais estes dois:

```text
fp-python/
├── ...
├── codigo.py
└── fila.py
```

## Palavras que vais usar

- Carácter: uma letra, um algarismo, um sinal ou um espaço. Um texto é uma sequência de caracteres. Para saber mais, vê a secção "Um texto é uma sequência de caracteres" do [guia](07-textos-e-listas-que-mudam.md).
- Índice: a posição de um carácter num texto, ou de um elemento numa lista, a contar do 0.
- Índice negativo: um índice que conta a partir do fim; `-1` é o último.
- Fatia: um pedaço de um texto tirado por posições, como `codigo[0:3]`. O segundo índice não entra.
- Método: uma função que pertence a um valor e se chama com um ponto, como `codigo.upper()`.
- Imutável: que não se pode alterar depois de criado, como um texto.
- Mutável: que se pode alterar depois de criado, como uma lista.
- `isdigit`: o método que diz se um texto tem só algarismos.
- `lower`: o método que devolve um texto novo, em minúsculas, o contrário do `upper`.
- f-string: um texto com um `f` antes das aspas, em que cada par de chavetas recebe um valor.
- `append`: o método que acrescenta um elemento no fim de uma lista.
- `pop`: o método que tira um elemento de uma lista, pela posição, e o devolve.
- Tabela das operações: a tabela do teu caderno com cada operação, o que ela faz e se muda o valor original.

## O que precisas

- O Python 3 e o VS Code, os dos laboratórios anteriores. Para confirmares o Python, abre o terminal do VS Code, no menu Terminal, com a opção New Terminal. Escreve `python --version`, com o teu comando: `python`, `py` no Windows ou `python3` no macOS. Deve aparecer uma linha como `Python 3.14.0`, com o 3 no início.
- A pasta `fp-python`, a dos laboratórios anteriores. Se não a tiveres, cria-a como diz "Preparar o projeto".
- O caderno, para a tabela das operações e para as previsões.

Os resultados e as mensagens de erro deste laboratório são os do Python 3.14. Num Python mais antigo, uma mensagem pode ter outras palavras, ou apontar outra coluna da linha. O tipo de erro, a palavra antes dos dois pontos, é o mesmo. O caminho do ficheiro que aparece nas mensagens, a seguir a `File`, muda de computador para computador.

## Se alguma coisa falhar

1. Guardaste o ficheiro? O Python corre o que está guardado no disco. Guarda com Ctrl+S, ou Cmd+S no macOS. Uma bola cheia no separador do ficheiro, no lugar do X, quer dizer que há alterações por guardar.
2. Estás na pasta certa? No terminal, o texto antes do cursor tem de ter `fp-python` no fim. Se não tiver, abre um terminal novo, no menu Terminal, com a opção New Terminal.
3. Estás na consola do Python sem quereres? Se a linha começa por `>>>`, escreve `exit()` e carrega em Enter, para voltares ao terminal.
4. O programa não volta ao terminal? Pode estar à espera que escrevas alguma coisa. Lê a última linha do terminal, escreve e carrega em Enter. Na fila, carrega em Enter sem escrever nada para acabar.
5. Copiaste o código à mão? Confirma as aspas que abrem e fecham cada texto, e os parênteses. Confirma os dois pontos no fim das linhas do `for`, do `while`, do `if`, do `elif` e do `else`. Confirma também a indentação, quatro espaços por nível.

## Preparar o projeto

1. Abre a pasta `fp-python` no VS Code. No menu File, escolhe Open Folder..., isto é, "abrir pasta", e escolhe `fp-python`. Se ainda não tens a pasta, cria-a primeiro no sítio onde guardas os trabalhos, por exemplo em Documentos. O que deves ver: à esquerda, no painel Explorer, o nome `FP-PYTHON`, com os ficheiros que já lá estiverem.

2. No caderno, faz uma tabela com três colunas, com estes títulos: "Operação", "O que faz" e "Muda o original?". É a tua tabela das operações. Em cada paragem, acrescentas-lhe as linhas que a paragem indica.

## Fase 1: Um texto lê-se por posições

O código de um jogo, como `"DES-02"`, é um texto. Um texto guarda uma sequência de caracteres, por ordem. Cada carácter tem uma posição, o índice, que começa em 0, como nas listas. Lê-se um carácter com o índice entre parênteses retos, como se lia um elemento de uma lista. O código tem seis caracteres, com os índices de 0 a 5:

| Carácter | `D` | `E` | `S` | `-` | `0` | `2` |
| --- | --- | --- | --- | --- | --- | --- |
| Índice | 0 | 1 | 2 | 3 | 4 | 5 |

Nesta fase experimentas na consola do Python, onde cada linha mostra logo o resultado. Para saber mais, lê a secção "Um texto é uma sequência de caracteres" do [guia](07-textos-e-listas-que-mudam.md).

1. Abre a consola: no terminal, escreve o teu comando do Python, `python`, `py` ou `python3`, sem mais nada, e carrega em Enter. O que deves ver: umas linhas com a versão do Python e, por baixo, `>>>`, à espera de uma linha.

2. Escreve estas linhas, uma de cada vez, e carrega em Enter depois de cada uma. Antes de cada Enter, olha para a tabela e prevê o que aparece.

   ```text
   >>> codigo = "DES-02"
   >>> codigo[0]
   'D'
   >>> codigo[3]
   '-'
   >>> len(codigo)
   6
   ```

   O que deves ver: os resultados acima. O `codigo[0]` é o primeiro carácter, e a consola mostra-o entre plicas, as aspas simples, para se ver que é um texto. O `codigo[3]` é o hífen, o quarto carácter. O `len` conta os seis caracteres, e por isso o último índice é 5.

3. Agora lê o último carácter de outra forma. Um índice negativo conta a partir do fim: `-1` é o último carácter, `-2` o penúltimo. Prevê e escreve:

   ```text
   >>> codigo[-1]
   '2'
   ```

   O que deves ver: `'2'`, o mesmo que `codigo[5]`. O `-1` é sempre o último, seja o texto curto ou comprido.

4. Provoca um erro de propósito: lê uma posição que não existe.

   ```text
   >>> codigo[6]
   ```

   O que deves ver: uma mensagem de erro, que acaba nesta linha:

   ```text
   IndexError: string index out of range
   ```

   Quer dizer "erro de índice: índice do texto fora dos limites". É o erro das listas, agora num texto: num texto de 6 caracteres, o último índice é 5. É um erro de execução, porque a linha está bem escrita, mas não se consegue executar com este valor.

### Paragem 1

Sabes ler um carácter de um texto pelo índice, a contar do início e a contar do fim.

Pensa antes de continuares: no título `"Celeste"`, qual é o índice do último `e`, a contar do início? E a contar do fim? A resposta: 6 e -1. O título tem 7 caracteres, por isso o último índice a contar do início é 6.

Acrescenta à tua tabela das operações:

| Operação | O que faz | Muda o original? |
| --- | --- | --- |
| `texto[i]` | dá o carácter do índice `i`; com `-1`, o último | não |
| `len(texto)` | conta os caracteres | não |

## Fase 2: Tirar fatias de um texto

Muitas vezes não queres um carácter, mas um pedaço do texto. Do código `"DES-02"`, queres o género, `"DES"`, ou o número, `"02"`. Um pedaço de um texto, tirado por posições, chama-se fatia. Escreve-se com dois índices separados por dois pontos: `codigo[0:3]`. O primeiro índice entra na fatia, e o segundo não entra, como no `range`. Para saber mais, lê a secção "Fatias de um texto" do [guia](07-textos-e-listas-que-mudam.md).

1. Continua na consola, com o mesmo `codigo`. Prevê e escreve:

   ```text
   >>> codigo[0:3]
   'DES'
   >>> codigo[:3]
   'DES'
   >>> codigo[4:]
   '02'
   ```

   O que deves ver: os resultados acima. O `codigo[0:3]` dá os índices 0, 1 e 2, e para antes do hífen. Sem o primeiro índice, a fatia começa no início. Sem o segundo, vai até ao fim. São estas duas fatias, `[:3]` e `[4:]`, que separam o género e o número de qualquer código do clube.

2. Agora experimenta a fatia que engana. Antes de carregares em Enter, prevê quantos caracteres tem.

   ```text
   >>> codigo[0:2]
   'DE'
   ```

   O que deves ver: `'DE'`, só com dois caracteres. O índice 2 não entra. Uma fatia tem sempre o segundo índice menos o primeiro caracteres: 2 - 0, isto é, 2. Para ter os três do género, o fim tem de ser 3.

3. Sai da consola com `exit()` e Enter. O que deves ver: o terminal normal, sem o `>>>`.

### Paragem 2

Sabes tirar uma fatia de um texto e contar quantos caracteres ela tem antes de a tirar.

Pensa antes de continuares: o que dá `"DES-02"[4:20]`? Dá erro? A resposta: dá `'02'`, sem erro. Uma fatia que passa do fim do texto fica com os caracteres que existem. Só o índice de um carácter, sozinho, dá erro fora dos limites.

Acrescenta à tua tabela das operações:

| Operação | O que faz | Muda o original? |
| --- | --- | --- |
| `texto[a:b]` | dá um texto novo, do índice `a` até antes do `b` | não |

## Fase 3: Arrumar o código com os métodos

Quem escreve um código no teclado pode escrever ` pla-01 `, com espaços à volta e em minúsculas. Para o Python, isso é outro texto, diferente de `"PLA-01"`. Antes de usar um texto que vem do teclado, é preciso arrumá-lo.

Para isso, cada texto traz consigo funções próprias, os métodos. Chamam-se com um ponto depois do valor e os parênteses no fim. O `strip()` devolve o texto sem os espaços do início e do fim, e o `upper()` devolve o texto em maiúsculas. Nenhum dos dois muda o texto original: devolvem um texto novo. Para saber mais, lê a secção "Os métodos dos textos" do [guia](07-textos-e-listas-que-mudam.md).

1. Cria o ficheiro `codigo.py`. No painel Explorer, passa o rato por cima de `FP-PYTHON` e carrega no ícone New File..., o primeiro dos quatro que aparecem. Escreve o nome e carrega em Enter. Cria-o com este conteúdo:

   ```python
   # codigo.py: lê o código de um jogo do clube e separa as suas duas partes.
   escrito = input("Código do jogo? ")
   codigo = escrito.strip().upper()
   prefixo = codigo[:3]
   numero = codigo[4:]
   print("Código arrumado:", codigo)
   print("Género:", prefixo)
   print("Número:", numero)
   ```

   Leitura guiada: o texto escrito fica em `escrito`, tal e qual. A terceira linha lê-se da esquerda para a direita. O `strip` devolve o texto sem os espaços das pontas, e o `upper` passa esse resultado a maiúsculas. Chamar um método sobre o resultado de outro chama-se encadear. Só o texto arrumado fica em `codigo`. As duas linhas seguintes são as fatias da fase 2. Os três `print` mostram as partes, uma por linha.

2. Guarda. Antes de correres, prevê o que aparece se escreveres ` pla-01 `, com um espaço antes e outro depois. Depois corre o programa, com o teu comando, como `python codigo.py`, e escreve o código. O que deves ver:

   ```text
   Código do jogo?  pla-01 
   Código arrumado: PLA-01
   Género: PLA
   Número: 01
   ```

   Isto quer dizer que os métodos arrumaram o código antes das fatias. Experimenta também `des-02`, que deve dar o género `DES` e o número `02`.

3. Provoca um erro de propósito: na terceira linha, apaga o `.strip()`, para ficar `codigo = escrito.upper()`. Guarda e corre outra vez, com ` pla-01 `. O que deves ver:

   ```text
   Código do jogo?  pla-01 
   Código arrumado:  PLA-01 
   Género:  PL
   Número: -01 
   ```

   Não aparece nenhuma mensagem de erro, e o resultado está errado. O espaço do início ficou no texto e ocupou o índice 0. Por isso, a fatia `[:3]` apanhou o espaço, o `P` e o `L`. É um erro de lógica, que só se vê comparando com o esperado. Volta a pôr o `.strip()`, guarda e corre outra vez.

### Paragem 3

O `codigo.py` arruma o código escrito e separa o género e o número, mesmo com espaços e minúsculas.

Pensa antes de continuares: depois de escreveres ` pla-01 `, quanto vale `escrito`, no fim do programa? A resposta: continua `" pla-01 "`, com os espaços e as minúsculas. O `strip` e o `upper` devolveram textos novos, e só o último ficou em `codigo`. O texto escrito ficou como estava.

Acrescenta à tua tabela das operações:

| Operação | O que faz | Muda o original? |
| --- | --- | --- |
| `texto.strip()` | devolve um texto novo, sem os espaços das pontas | não |
| `texto.upper()` | devolve um texto novo, em maiúsculas | não |

## Fase 4: Um texto não se altera

Há quem escreva o código com outro separador: `pla_01`, com um traço baixo, ou `pla 01`, com um espaço. O programa tem de pôr um hífen no índice 3. A ideia natural é mudar esse carácter, como se muda um elemento de uma lista. Nesta fase vais ver porque é que isso não funciona, e o que se faz em vez disso. Para saber mais, lê a secção "Um texto não se altera" do [guia](07-textos-e-listas-que-mudam.md).

1. Corre o `codigo.py` com `pla_01`. Antes de correres, prevê o código arrumado. O que deves ver:

   ```text
   Código do jogo? pla_01
   Código arrumado: PLA_01
   Género: PLA
   Número: 01
   ```

   O género e o número estão certos, porque as fatias saltam o índice 3. Mas o código arrumado tem o traço baixo, e não é um código do clube.

2. Provoca um erro de propósito: tenta mudar o carácter do índice 3. Em `codigo.py`, acrescenta esta linha logo a seguir à linha `codigo = escrito.strip().upper()`:

   ```python
   codigo[3] = "-"
   ```

   Guarda e corre com `pla_01`. O que deves ver:

   ```text
   Código do jogo? pla_01
   Traceback (most recent call last):
     File "C:\Users\aluno\Documents\fp-python\codigo.py", line 4, in <module>
       codigo[3] = "-"
       ~~~~~~^^^
   TypeError: 'str' object does not support item assignment
   ```

   Lê a mensagem de baixo para cima. Quer dizer "erro de tipo: um objeto `str` não aceita que se dê um valor a um elemento". Para o Python, um objeto é um valor. O Python não deixa mudar um carácter de um texto: depois de criado, um texto nunca muda. Um valor assim diz-se imutável. As listas, pelo contrário, são mutáveis.

3. Então, constrói-se um texto novo: as três letras, um hífen e o que vem depois do índice 3. Substitui a linha `codigo[3] = "-"` por estas duas:

   ```python
   # Um texto não se altera: para pôr o hífen, constrói-se um texto novo com duas fatias.
   codigo = codigo[:3] + "-" + codigo[4:]
   ```

   Leitura guiada: o lado direito faz-se primeiro, como em qualquer atribuição. O `+` junta três textos: a fatia das três primeiras letras, o hífen e a fatia do índice 4 até ao fim. O resultado é um texto novo, que passa a ficar em `codigo`. O texto antigo, com o traço baixo, não mudou: a variável é que passou a guardar outro texto.

4. Guarda. Antes de correres, prevê o código arrumado com `pla_01`, com ` des 02 ` e com `PLA-01`, que já vem certo. Corre três vezes. O que deves ver: `PLA-01`, `DES-02` e `PLA-01`. Com um código que já tem o hífen, a linha nova não estraga nada: troca o hífen por outro hífen.

### Paragem 4

O `codigo.py` aceita um código com qualquer separador no índice 3, e mostra-o sempre com o hífen.

Pensa antes de continuares: o método `replace("_", "-")` troca cada traço baixo por um hífen. Porque é que, aqui, as duas fatias servem melhor? A resposta: o `replace("_", "-")` só trata o traço baixo, e falhava com `pla 01` ou `pla.01`. As fatias põem o hífen no índice 3, seja qual for o carácter que lá estava.

Acrescenta à tua tabela das operações:

| Operação | O que faz | Muda o original? |
| --- | --- | --- |
| `texto[i] = x` | não é permitido: para com `TypeError` | não se aplica |
| `texto1 + texto2` | constrói um texto novo, com os dois juntos | não |

## Fase 5: Confirmar as letras, carácter a carácter

E se a pessoa escrever `pla01`, sem separador, ou `pl4-01`, com um algarismo no lugar de uma letra? O programa mostra um código que não existe. Um código do clube tem uma forma certa: seis caracteres, três letras, um separador e dois algarismos. O separador já ficou tratado na fase 4, com o hífen que o programa põe no índice 3. Nesta fase, o programa confirma o tamanho e as três letras. Na fase seguinte, confirma os dois algarismos.

Para confirmar que o género tem só letras, percorre-se o prefixo carácter a carácter, com `for`, como se percorre uma lista. Em cada volta, pergunta-se se o carácter está num texto com as 26 letras. Para isso serve o `in`: entre dois textos, pergunta se o primeiro aparece dentro do segundo, e dá `True` ou `False`. O `not in` faz o contrário. Para saber mais, lê a secção "Perguntar se um texto contém outro, com `in`" do [guia](07-textos-e-listas-que-mudam.md).

1. Experimenta primeiro o `in` na consola. No terminal, escreve o teu comando do Python, sem mais nada, e carrega em Enter. Escreve estas linhas, uma de cada vez, e prevê o que aparece antes de cada Enter.

   ```text
   >>> LETRAS = "ABCDEFGHIJKLMNOPQRSTUVWXYZ"
   >>> "P" in LETRAS
   True
   >>> "4" in LETRAS
   False
   >>> "4" not in LETRAS
   True
   >>> "p" in LETRAS
   False
   ```

   O que deves ver: os resultados acima. O `P` está entre as 26 letras, e o `4` não está. O `not in` dá a resposta ao contrário. O `p` minúsculo dá `False`, porque o texto `LETRAS` só tem maiúsculas. É por isso que o código se arruma com o `upper` antes de ser confirmado. Sai da consola com `exit()` e Enter.

2. Em `codigo.py`, substitui tudo por este conteúdo, que acrescenta a confirmação das letras ao que já tinhas:

   ```python
   # codigo.py: lê o código de um jogo do clube, arruma-o, confirma a forma
   # e separa as suas duas partes.
   LETRAS = "ABCDEFGHIJKLMNOPQRSTUVWXYZ"

   escrito = input("Código do jogo? ")
   codigo = escrito.strip().upper()
   # Um texto não se altera: para pôr o hífen, constrói-se um texto novo com duas fatias.
   codigo = codigo[:3] + "-" + codigo[4:]
   prefixo = codigo[:3]
   numero = codigo[4:]

   # Percorre o prefixo carácter a carácter: basta um que não seja letra para falhar.
   so_letras = True
   for caracter in prefixo:
       if caracter not in LETRAS:
           so_letras = False

   if len(codigo) == 6 and so_letras:
       print("Código arrumado:", codigo)
       print("Género:", prefixo)
       print("Número:", numero)
   else:
       print("O código", escrito.strip(), "não tem a forma certa, como PLA-01.")
   ```

   Leitura guiada: começa pela constante `LETRAS`, a da consola. O início do programa é o da fase 4. Depois vem a bandeira `so_letras`, que começa em `True`, ao contrário das bandeiras da pesquisa do tema 05, e como a `todas_validas` do tema 06. Parte-se do princípio de que são todas letras, e basta uma que não seja para a bandeira passar a `False`. O `for` dá à variável `caracter` cada um dos três caracteres do prefixo. O `if` final junta duas condições com `and`: o tamanho e as letras. Quando o código falha, a mensagem mostra o que a pessoa escreveu, sem os espaços, e não o código já mexido.

3. Guarda. Antes de correres, prevê a resposta a cada um destes códigos: ` pla_01 `, `pla01` e `pl4-01`. Corre três vezes. O que deves ver, em cada vez:

   ```text
   Código do jogo?  pla_01 
   Código arrumado: PLA-01
   Género: PLA
   Número: 01
   ```

   ```text
   Código do jogo? pla01
   O código pla01 não tem a forma certa, como PLA-01.
   ```

   ```text
   Código do jogo? pl4-01
   O código pl4-01 não tem a forma certa, como PLA-01.
   ```

   O `pla01` passa a `PLA-1` depois das fatias, com 5 caracteres, e falha no tamanho. O `pl4-01` falha nas letras, por causa do 4.

4. Segue o ciclo com o `pl4-01`, no caderno, antes de continuares. O prefixo é `"PL4"`:

   | Volta | `caracter` | `caracter not in LETRAS` | `so_letras` depois da volta |
   | ---: | --- | --- | --- |
   | antes | | | `True` |
   | 1 | `"P"` | `False` | `True` |
   | 2 | `"L"` | `False` | `True` |
   | 3 | `"4"` | `True` | `False` |

   Depois de passar a `False`, a bandeira nunca volta a `True`, porque nenhuma linha do ciclo a põe a `True`. Basta um carácter errado.

5. Corre outra vez, agora com `pla-0a`. O que deves ver:

   ```text
   Código do jogo? pla-0a
   Código arrumado: PLA-0A
   Género: PLA
   Número: 0A
   ```

   O programa aceita-o, com um número que não é um número. O tamanho e as letras estão certos, e nada confirma os algarismos. É o que a fase 6 resolve.

### Paragem 5

O `codigo.py` recusa um código com o tamanho errado ou com um carácter que não é uma letra no género.

Pensa antes de continuares: se a bandeira `so_letras` começasse em `False`, o que mostrava o programa com ` pla_01 `? A resposta: dizia que o código não tem a forma certa. Nenhuma linha do ciclo põe a bandeira a `True`, e ela ficava em `False` mesmo com três letras. Esta bandeira procura um carácter errado, e por isso começa em `True`.

Acrescenta à tua tabela das operações:

| Operação | O que faz | Muda o original? |
| --- | --- | --- |
| `for caracter in texto:` | percorre o texto, um carácter por volta | não |
| `x in texto` | dá `True` se `x` aparecer dentro do texto | não |

## Fase 6: Confirmar os algarismos com um método

Falta confirmar que o número tem só algarismos. Podias escrever outro ciclo, igual ao das letras, com um texto dos dez algarismos. Mas os textos têm um método que já faz essa procura: o `isdigit()`, de *is digit*, "é algarismo". Dá `True` quando o texto tem só algarismos, e `False` quando tem outra coisa, ou quando está vazio. Para saber mais, lê a secção "Os métodos dos textos" do [guia](07-textos-e-listas-que-mudam.md).

1. Experimenta-o na consola. Prevê e escreve:

   ```text
   >>> "01".isdigit()
   True
   >>> "0A".isdigit()
   False
   >>> "".isdigit()
   False
   ```

   O que deves ver: os resultados acima. O `"0A"` tem uma letra, e o texto vazio não tem nenhum algarismo. Sai da consola com `exit()` e Enter.

2. Em `codigo.py`, na linha do `if` final, acrescenta ` and numero.isdigit()` antes dos dois pontos, para a linha ficar assim:

   ```python
   if len(codigo) == 6 and so_letras and numero.isdigit():
   ```

   Leitura guiada: o `if` passa a juntar três condições com `and`: o tamanho, as letras e os algarismos. O código só é aceite se as três forem verdadeiras. O `isdigit` faz pelo número o que o ciclo faz pelas letras: percorre o texto e diz se todos os caracteres são algarismos.

3. Guarda. Antes de correres, prevê a resposta a ` pla_01 `, `pla-0a` e `des-002`. Corre três vezes. O que deves ver: ` pla_01 ` dá as três linhas da fase 5, e os outros dois são recusados:

   ```text
   Código do jogo? pla-0a
   O código pla-0a não tem a forma certa, como PLA-01.
   ```

   ```text
   Código do jogo? des-002
   O código des-002 não tem a forma certa, como PLA-01.
   ```

   O `pla-0a` falha nos algarismos, por causa do `A`. O `des-002` tem 7 caracteres, e falha no tamanho.

### Paragem 6

O `codigo.py` confirma o tamanho, as letras e os algarismos de um código, e diz qual foi o código recusado.

Pensa antes de continuares: o programa aceita `plax01`, com um x no lugar do separador? E `pla101`? Corre os dois e explica porquê. A resposta: aceita os dois, e mostra o código `PLA-01`. As fatias da fase 4 saltam o índice 3, e o programa põe lá o hífen, seja qual for o carácter que lá estava. O programa não confirma o carácter do meio. Um dos desafios do fim trata disso.

Acrescenta à tua tabela das operações:

| Operação | O que faz | Muda o original? |
| --- | --- | --- |
| `texto.isdigit()` | dá `True` se o texto tiver só algarismos | não |

## Fase 7: A frase com uma f-string

O programa escreve três linhas, mas o clube quer uma só frase: `O código PLA-01 é do género PLA e tem o número 1.`. Com o `print` e as vírgulas, aparece um espaço antes do ponto final. Com o `+`, era preciso converter o número com `str` e cuidar de cada espaço.

Para isto há as f-strings. Uma f-string é um texto com um `f` antes das aspas. Dentro dele, cada par de chavetas, `{` e `}`, marca o sítio onde entra um valor. O Python calcula o que está entre as chavetas e põe o resultado no lugar delas, já como texto. Para saber mais, lê a secção "Juntar textos e valores com f-strings" do [guia](07-textos-e-listas-que-mudam.md).

1. Em `codigo.py`, substitui os três `print` dentro do `if` e o `print` dentro do `else`. O fim do ficheiro fica assim:

   ```python
   if len(codigo) == 6 and so_letras and numero.isdigit():
       # O int() tira o zero à esquerda: o texto "01" passa ao número 1.
       print(f"O código {codigo} é do género {prefixo} e tem o número {int(numero)}.")
   else:
       print(f"O código {escrito.strip()} não tem a forma certa, como PLA-01.")
   ```

   Leitura guiada: o `f` antes das aspas faz do texto uma f-string. Na primeira, há três pares de chavetas. Os dois primeiros recebem as variáveis `codigo` e `prefixo`. O terceiro recebe uma chamada, `int(numero)`, que converte o texto `"01"` no número 1. O ponto final fica colado ao número, porque está escrito colado a ele. Na segunda f-string, as chavetas têm um método, `escrito.strip()`, e o Python escreve o que ele devolve.

2. Guarda. Antes de correres, prevê a frase que aparece com ` pla_01 ` e com `des 02`. Depois corre duas vezes. O que deves ver:

   ```text
   Código do jogo?  pla_01 
   O código PLA-01 é do género PLA e tem o número 1.
   ```

   ```text
   Código do jogo? des 02
   O código DES-02 é do género DES e tem o número 2.
   ```

3. Provoca um erro de propósito: apaga o `f` antes das aspas da primeira f-string. Guarda e corre com `pla-01`. O que deves ver:

   ```text
   Código do jogo? pla-01
   O código {codigo} é do género {prefixo} e tem o número {int(numero)}.
   ```

   Sem o `f`, as chavetas são caracteres como os outros, e o Python escreve-as tal e qual. Não há mensagem de erro: é um erro de lógica, que se vê no ecrã. Volta a pôr o `f`, guarda e corre outra vez.

4. Provoca outro erro: na linha do `if`, apaga o ` and numero.isdigit()`, para ficar `if len(codigo) == 6 and so_letras:`. Guarda e corre com `pla-0a`. O que deves ver:

   ```text
   Código do jogo? pla-0a
   Traceback (most recent call last):
     File "C:\Users\aluno\Documents\fp-python\codigo.py", line 20, in <module>
       print(f"O código {codigo} é do género {prefixo} e tem o número {int(numero)}.")
                                                                       ~~~^^^^^^^^
   ValueError: invalid literal for int() with base 10: '0A'
   ```

   Quer dizer "erro de valor: escrita inválida para um `int` na base 10". O `int` não consegue converter `"0A"` num número. A mensagem aponta a linha 20, mas a causa está na linha 18, no `if` a que falta uma condição. É o `isdigit` que garante que o `int` só recebe algarismos. Volta a pôr o ` and numero.isdigit()`, guarda e corre outra vez com `pla-0a`, para confirmares a mensagem do código recusado.

### Paragem 7

O `codigo.py` está completo. Muda a segunda linha do comentário do início, porque o programa já não escreve as partes em linhas separadas. Depois confere o teu com este:

```python
# codigo.py: lê o código de um jogo do clube, arruma-o, confirma a forma
# e mostra as suas duas partes numa frase.
LETRAS = "ABCDEFGHIJKLMNOPQRSTUVWXYZ"

escrito = input("Código do jogo? ")
codigo = escrito.strip().upper()
# Um texto não se altera: para pôr o hífen, constrói-se um texto novo com duas fatias.
codigo = codigo[:3] + "-" + codigo[4:]
prefixo = codigo[:3]
numero = codigo[4:]

# Percorre o prefixo carácter a carácter: basta um que não seja letra para falhar.
so_letras = True
for caracter in prefixo:
    if caracter not in LETRAS:
        so_letras = False

if len(codigo) == 6 and so_letras and numero.isdigit():
    # O int() tira o zero à esquerda: o texto "01" passa ao número 1.
    print(f"O código {codigo} é do género {prefixo} e tem o número {int(numero)}.")
else:
    print(f"O código {escrito.strip()} não tem a forma certa, como PLA-01.")
```

Pensa antes de continuares: o que escrevia `print(f"{prefixo}{numero}")`, com o código `PLA-01`? A resposta: `PLA01`. Entre os dois pares de chavetas não há nada, e por isso os dois valores ficam colados, sem espaço nem hífen.

Acrescenta à tua tabela das operações:

| Operação | O que faz | Muda o original? |
| --- | --- | --- |
| `f"... {valor} ..."` | constrói um texto novo, com o valor no lugar das chavetas | não |

## Fase 8: Uma lista que cresce: a fila

Agora o segundo programa. O clube tem uma consola, e quem quer jogar põe-se na fila. Não se sabe quantas pessoas vão chegar. A fila começa vazia e cresce à medida que chegam nomes.

Uma lista vazia escreve-se `[]`. Para lhe acrescentar um elemento no fim, usa-se o método `append`, que quer dizer "acrescentar". As listas são mutáveis: o `append` muda a própria lista e não devolve nada. É ao contrário dos métodos dos textos, que nunca mudam o texto e devolvem um texto novo. Para saber mais, lê a secção "Listas que crescem e encolhem" do [guia](07-textos-e-listas-que-mudam.md).

1. Cria o ficheiro `fila.py` com este conteúdo:

   ```python
   # fila.py: a fila para a consola do clube.
   # Cada nome escrito entra no fim da fila. Enter sem nada acaba o programa.
   fila = []
   entrada = input("Nome (Enter para acabar): ").strip()
   while entrada != "":
       fila.append(entrada)
       print(f"{entrada} entrou na fila, em {len(fila)}.º lugar.")
       entrada = input("Nome (Enter para acabar): ").strip()
   print(f"Ficaram na fila: {len(fila)}")
   print(fila)
   ```

   Leitura guiada: a lista nasce vazia, antes do ciclo, como um contador nasce a 0. É o ciclo da sentinela, com uma leitura antes do ciclo e outra no fim do corpo. O texto vazio, de quem carrega em Enter sem escrever nada, faz de sentinela. Em cada volta, o `append` acrescenta o nome lido ao fim da lista. Logo a seguir, o `len` diz quantos elementos a lista tem, que é o lugar de quem acabou de entrar. O último `print` mostra a lista inteira, entre parênteses retos.

2. Guarda. Antes de correres, prevê o que aparece se escreveres `Rui`, `Ana` e `Bia`, e depois carregares em Enter sem escrever nada. Corre o programa. O que deves ver:

   ```text
   Nome (Enter para acabar): Rui
   Rui entrou na fila, em 1.º lugar.
   Nome (Enter para acabar): Ana
   Ana entrou na fila, em 2.º lugar.
   Nome (Enter para acabar): Bia
   Bia entrou na fila, em 3.º lugar.
   Nome (Enter para acabar): 
   Ficaram na fila: 3
   ['Rui', 'Ana', 'Bia']
   ```

   Corre outra vez, e carrega logo em Enter. O que deves ver: `Ficaram na fila: 0` e `[]`. O ciclo deu zero voltas, e a lista ficou vazia.

3. Provoca um erro de propósito: aplica às listas a regra dos textos, e guarda o resultado do `append`. Muda a linha do `append` para `fila = fila.append(entrada)`. Guarda e corre com `Rui`. O que deves ver:

   ```text
   Nome (Enter para acabar): Rui
   Traceback (most recent call last):
     File "C:\Users\aluno\Documents\fp-python\fila.py", line 7, in <module>
       print(f"{entrada} entrou na fila, em {len(fila)}.º lugar.")
                                             ~~~^^^^^^
   TypeError: object of type 'NoneType' has no len()
   ```

   Quer dizer "erro de tipo: um objeto do tipo `NoneType` não tem `len`". O `NoneType` é o tipo do `None`, o valor que quer dizer "nenhum valor". O `append` mudou a lista e devolveu `None`, e a atribuição guardou esse `None` em `fila`, deitando a lista fora. A mensagem aponta a linha 7, mas a causa está na linha 6: a mensagem é uma pista, e não a resposta. Volta a pôr `fila.append(entrada)`, sem atribuição, guarda e corre outra vez.

### Paragem 8

O `fila.py` junta os nomes numa lista que começa vazia e cresce um a um.

Pensa antes de continuares: porque é que se escreve `codigo = codigo.upper()`, com atribuição, e `fila.append(entrada)`, sem atribuição? A resposta: o `upper` não muda o texto e devolve um texto novo, que tem de se guardar. O `append` muda a própria lista e devolve `None`, que não se deve guardar.

Acrescenta à tua tabela das operações:

| Operação | O que faz | Muda o original? |
| --- | --- | --- |
| `lista.append(x)` | acrescenta `x` no fim da lista; não devolve nada | sim |

## Fase 9: Chamar o primeiro com `pop`

Quando a consola fica livre, joga o primeiro da fila, e ele sai da fila. Para tirar um elemento de uma lista pela posição, usa-se o método `pop`. Com `fila.pop(0)`, a lista perde o elemento do índice 0, e os outros passam uma posição para a frente. O `pop` devolve o elemento que tirou, para o programa o poder usar: aqui, para dizer de quem é a vez. Sem nada entre os parênteses, `fila.pop()` tira o último. Para saber mais, lê a secção "Listas que crescem e encolhem" do [guia](07-textos-e-listas-que-mudam.md).

O programa passa a aceitar uma palavra especial: quem escreve `próximo` não entra na fila, chama o primeiro a jogar. Para aceitar também `Próximo` ou `PRÓXIMO`, o programa usa o método `lower()`, o contrário do `upper()`: devolve um texto novo, em minúsculas.

1. Em `fila.py`, substitui tudo por este conteúdo:

   ```python
   # fila.py: a fila para a consola do clube.
   # Cada nome escrito entra no fim da fila; a palavra próximo chama o primeiro a jogar.
   # Enter sem nada acaba o programa.
   fila = []
   entrada = input("Nome, próximo, ou Enter para acabar: ").strip()
   while entrada != "":
       if entrada.lower() == "próximo":
           a_jogar = fila.pop(0)
           print(f"É a vez de {a_jogar}. Na fila: {len(fila)}.")
       else:
           fila.append(entrada)
           print(f"{entrada} entrou na fila, em {len(fila)}.º lugar.")
       entrada = input("Nome, próximo, ou Enter para acabar: ").strip()
   print(f"Ficaram na fila: {len(fila)}")
   print(fila)
   ```

   Leitura guiada: o ciclo é o mesmo, com um `if` dentro. A condição compara a entrada, em minúsculas, com `"próximo"`, para aceitar também `Próximo` ou `PRÓXIMO`. Nesse caso, o `pop(0)` tira o primeiro nome da fila, e o nome fica em `a_jogar`. Em qualquer outro caso, a entrada é um nome, e entra no fim da fila, como na fase 8.

2. Guarda. Antes de correres, prevê o que aparece com esta sequência: `Rui`, `Ana`, `próximo`, `Bia`, `PRÓXIMO` e Enter sem nada. Corre o programa. O que deves ver:

   ```text
   Nome, próximo, ou Enter para acabar: Rui
   Rui entrou na fila, em 1.º lugar.
   Nome, próximo, ou Enter para acabar: Ana
   Ana entrou na fila, em 2.º lugar.
   Nome, próximo, ou Enter para acabar: próximo
   É a vez de Rui. Na fila: 1.
   Nome, próximo, ou Enter para acabar: Bia
   Bia entrou na fila, em 2.º lugar.
   Nome, próximo, ou Enter para acabar: PRÓXIMO
   É a vez de Ana. Na fila: 1.
   Nome, próximo, ou Enter para acabar: 
   Ficaram na fila: 1
   ['Bia']
   ```

   Segue a fila no caderno, linha a linha: `['Rui']`, `['Rui', 'Ana']`, `['Ana']`, `['Ana', 'Bia']` e `['Bia']`. A Bia entrou em 2.º lugar, e não em 3.º, porque o Rui já tinha saído.

3. Agora testa o caso que engana: a fila vazia. Antes de correres, prevê o que acontece se a primeira coisa que escreves for `próximo`. Corre e escreve `próximo`. O que deves ver:

   ```text
   Nome, próximo, ou Enter para acabar: próximo
   Traceback (most recent call last):
     File "C:\Users\aluno\Documents\fp-python\fila.py", line 8, in <module>
       a_jogar = fila.pop(0)
   IndexError: pop from empty list
   ```

   Quer dizer "erro de índice: `pop` de uma lista vazia". Não há ninguém para chamar, e o `pop` não tem nada para tirar. Este caso não apareceu no teste anterior, porque a fila nunca ficou vazia antes de um `próximo`. É por isso que a lista vazia é sempre um dos casos de teste.

4. Corrige: antes do `pop`, pergunta se a fila tem alguém. Substitui as duas linhas do `pop` e do `print` que vem a seguir, dentro do `if`, por estas seis:

   ```python
           # Com a fila vazia, o pop(0) parava o programa: não há ninguém para chamar.
           if len(fila) == 0:
               print("A fila está vazia.")
           else:
               a_jogar = fila.pop(0)
               print(f"É a vez de {a_jogar}. Na fila: {len(fila)}.")
   ```

   Leitura guiada: são seis linhas, contando com o comentário, indentadas com oito espaços, porque estão dentro do `if` do `próximo`. O `if` novo trata a fila vazia à parte. O `pop` só se faz no `else`, quando há pelo menos um nome.

5. Guarda. Corre outra vez e escreve `próximo`, depois `Eva`, depois `próximo`, e por fim Enter sem nada. O que deves ver: `A fila está vazia.`, `Eva entrou na fila, em 1.º lugar.`, `É a vez de Eva. Na fila: 0.`, e no fim `Ficaram na fila: 0` e `[]`. Volta a correr a sequência do passo 2, para confirmares que o caso normal continua certo.

### Paragem 9

O `fila.py` chama o primeiro da fila, que sai dela, e não para com a fila vazia.

Pensa antes de continuares: se escrevesses `fila.pop()` em vez de `fila.pop(0)`, quem jogava primeiro? A resposta: o último a chegar, porque o `pop()` sem posição tira o último elemento. Uma fila justa tira do princípio, com o `pop(0)`, e acrescenta no fim, com o `append`.

Acrescenta à tua tabela das operações:

| Operação | O que faz | Muda o original? |
| --- | --- | --- |
| `lista.pop(0)` | tira o primeiro elemento e devolve-o | sim |
| `lista.pop()` | tira o último elemento e devolve-o | sim |
| `texto.lower()` | devolve um texto novo, em minúsculas | não |

## Fase 10: Ninguém entra duas vezes, e quem ficou

Falta uma regra: a mesma pessoa não pode estar duas vezes na fila. Antes de acrescentar um nome, o programa pergunta se ele já lá está. O `in` que usaste com os textos também funciona com as listas: `"Rui" in fila` dá `True` se o Rui for um dos elementos da fila. No fim, o programa mostra quem ficou, numerado. Para saber mais, lê a secção "Listas que crescem e encolhem" do [guia](07-textos-e-listas-que-mudam.md).

1. Em `fila.py`, acrescenta um `elif` entre o bloco do `próximo` e o `else` que acrescenta o nome. Há dois `else` no ficheiro. O que interessa é o de fora, com quatro espaços antes, alinhado com o `if entrada.lower() == "próximo":`. Logo antes dele, escreve estas duas linhas, a primeira também com quatro espaços:

   ```python
       elif entrada in fila:
           print(f"{entrada} já está na fila.")
   ```

   Leitura guiada: o `elif` só se testa quando a entrada não é `próximo`. Se o nome já for um elemento da fila, o programa diz-o, e o `else` não chega a acrescentá-lo. A lista não muda nessa volta.

2. Substitui as duas últimas linhas do ficheiro, os dois `print` depois do ciclo, por estas. Deixa uma linha em branco entre o ciclo e elas, para separar as duas partes:

   ```python
   print()
   if len(fila) == 0:
       print("A fila ficou vazia.")
   else:
       print(f"Ficaram na fila: {len(fila)}")
       for i in range(0, len(fila)):
           print(f"{i + 1}. {fila[i]}")
   ```

   Leitura guiada: o `print()` vazio deixa uma linha em branco. A fila vazia tem uma mensagem própria. Se houver alguém, o `for` percorre a fila pelo índice, como as listas do tema 05. O `i + 1` dá o lugar de cada um, a contar do 1.

3. Guarda. Antes de correres, prevê o que aparece com esta sequência: `Rui`, `Ana`, `Rui`, `próximo`, `Bia`, `Rui` e Enter sem nada. Corre o programa. O que deves ver:

   ```text
   Nome, próximo, ou Enter para acabar: Rui
   Rui entrou na fila, em 1.º lugar.
   Nome, próximo, ou Enter para acabar: Ana
   Ana entrou na fila, em 2.º lugar.
   Nome, próximo, ou Enter para acabar: Rui
   Rui já está na fila.
   Nome, próximo, ou Enter para acabar: próximo
   É a vez de Rui. Na fila: 1.
   Nome, próximo, ou Enter para acabar: Bia
   Bia entrou na fila, em 2.º lugar.
   Nome, próximo, ou Enter para acabar: Rui
   Rui entrou na fila, em 3.º lugar.
   Nome, próximo, ou Enter para acabar: 

   Ficaram na fila: 3
   1. Ana
   2. Bia
   3. Rui
   ```

   Repara no último Rui. Da primeira vez que tentou entrar outra vez, estava na fila, e foi recusado. Depois de jogar, saiu da fila, e por isso pôde voltar a entrar, no fim.

### Paragem 10

O `fila.py` está completo. Confere o teu com este:

```python
# fila.py: a fila para a consola do clube.
# Cada nome escrito entra no fim da fila, se ainda lá não estiver; a palavra próximo
# chama o primeiro a jogar. Enter sem nada acaba o programa e mostra quem ficou.
fila = []
entrada = input("Nome, próximo, ou Enter para acabar: ").strip()
while entrada != "":
    if entrada.lower() == "próximo":
        # Com a fila vazia, o pop(0) parava o programa: não há ninguém para chamar.
        if len(fila) == 0:
            print("A fila está vazia.")
        else:
            a_jogar = fila.pop(0)
            print(f"É a vez de {a_jogar}. Na fila: {len(fila)}.")
    elif entrada in fila:
        print(f"{entrada} já está na fila.")
    else:
        fila.append(entrada)
        print(f"{entrada} entrou na fila, em {len(fila)}.º lugar.")
    entrada = input("Nome, próximo, ou Enter para acabar: ").strip()

print()
if len(fila) == 0:
    print("A fila ficou vazia.")
else:
    print(f"Ficaram na fila: {len(fila)}")
    for i in range(0, len(fila)):
        print(f"{i + 1}. {fila[i]}")
```

Atualiza também o comentário do início do teu ficheiro, se ainda não tiver as três linhas acima: o programa passou a fazer mais coisas.

Pensa antes de continuares: corre o programa com `Rui` e depois `rui`. O que acontece, e porquê? A resposta: os dois entram na fila, como se fossem pessoas diferentes. Para o Python, `"Rui"` e `"rui"` são textos diferentes, e o `in` compara os elementos exatamente.

Acrescenta à tua tabela das operações:

| Operação | O que faz | Muda o original? |
| --- | --- | --- |
| `x in lista` | dá `True` se `x` for um dos elementos da lista | não |

Olha agora para a última coluna da tabela inteira. As operações dos textos dizem todas "não", ou "não se aplica", e as das listas que acrescentam ou tiram dizem "sim". É a diferença entre um valor imutável e um mutável.

## Problemas frequentes

### `IndexError: string index out of range` na consola

O índice é maior do que o último. Num texto de 6 caracteres, o último índice é 5, ou -1. Conta os caracteres com o `len` e tira 1.

### A fatia tem um carácter a menos

O segundo índice da fatia não entra. Para os três primeiros caracteres, a fatia é `[0:3]` ou `[:3]`, e não `[0:2]`. Confirma com a conta: o segundo índice menos o primeiro dá o número de caracteres.

### O género aparece com um espaço, como ` PL`

Falta o `.strip()` na linha que arruma o código. O espaço do início ocupa o índice 0 e estraga as fatias.

### `TypeError: 'str' object does not support item assignment`

Estás a tentar mudar um carácter de um texto, como `codigo[3] = "-"`. Um texto não se altera. Constrói um texto novo e guarda-o na variável, como na fase 4.

### Um código certo é recusado

Confirma que o `LETRAS` tem as 26 letras, em maiúsculas, sem espaços, e que a linha `codigo = escrito.strip().upper()` tem os dois métodos. Com uma letra em falta no `LETRAS`, um código com essa letra é recusado.

### Aparecem as chavetas no ecrã, como `{codigo}`

Falta o `f` antes das aspas da f-string. Acrescenta-o, colado às aspas: `f"..."`.

### `TypeError: object of type 'NoneType' has no len()` ou `AttributeError: 'NoneType' object has no attribute 'append'`

Guardaste o resultado do `append`, com `fila = fila.append(...)`. O `append` muda a lista e devolve `None`. Escreve só `fila.append(...)`.

### `IndexError: pop from empty list`

Fizeste um `pop` com a fila vazia. Antes do `pop`, pergunta se a fila tem alguém, com `len(fila) == 0`, como na fase 9.

### Quem escreve `proximo`, sem acento, entra na fila

O programa compara com `"próximo"`, com acento, e para o Python são textos diferentes. Escreve a palavra com o acento.

## Desafios

1. Pedir o código outra vez. Em `codigo.py`, o programa deixa de acabar quando o código não tem a forma certa. Em vez disso, pede o código outra vez, até receber um código certo. Testa com `pla01`, depois `pl4-01` e por fim `pla-01`. Pista: pensa em todas as linhas que têm de se repetir para cada código novo, incluindo a bandeira.

2. Confirmar o separador. Em `codigo.py`, o programa passa a recusar um código com um carácter do meio errado. Os separadores certos são o hífen, o traço baixo, o espaço e o ponto. O carácter do meio é o do índice 3 do que a pessoa escreveu, depois do `strip`. Testa com `plax01`, `pla101`, `pla_01`, ` pla 01 ` e `pla-01`. Antes de cada caso, escreve o que esperas. Pista: o carácter do meio tem de se confirmar antes de o programa lá pôr o hífen.

3. Desistir da fila. Em `fila.py`, quem escrever `sai` seguido de um nome, como `sai Ana`, tira essa pessoa da fila, esteja onde estiver. Se a pessoa não estiver na fila, o programa diz-o e não para. Testa com `Rui`, `Ana`, `Bia`, `sai Ana`, `sai Eva` e Enter. Pista: as primeiras letras da entrada dizem se é um pedido para sair, e uma fatia dá o nome que vem depois. Há um método das listas que tira um valor sem saber a posição; o guia explica-o na secção "Listas que crescem e encolhem".

4. Passar à frente. Em `fila.py`, quem escrever `frente` seguido de um nome, como `frente Bia`, passa essa pessoa para o primeiro lugar da fila. Se a pessoa ainda não estiver na fila, entra logo em primeiro. Testa com `Rui`, `Ana`, `Bia`, `frente Bia`, `frente Eva` e Enter: no fim, a fila deve ser Eva, Bia, Rui e Ana. Pista: há um método das listas que põe um valor numa posição à escolha; o guia explica-o na secção "Listas que crescem e encolhem".

## Antes de terminares

- [ ] O `codigo.py` mostra a frase certa com ` pla_01 ` e com `des 02`.
- [ ] O `codigo.py` recusa `pla01`, `pl4-01`, `pla-0a` e `des-002`.
- [ ] O `fila.py` dá o ecrã do passo 3 da fase 10, e não para com `próximo` e a fila vazia.
- [ ] A tua tabela das operações tem as linhas das dez paragens, com a coluna "Muda o original?" preenchida.
- [ ] Sabes dizer de que tipo foi cada erro que provocaste: de sintaxe, de execução ou de lógica.
- [ ] Consegues explicar, por palavras tuas, porque é que o `upper` se guarda com uma atribuição e o `append` não. E o que isso diz sobre os textos e as listas.

![Rodapé](../imagens/rodape.png)
