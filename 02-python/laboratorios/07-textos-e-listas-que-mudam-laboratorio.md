![Cabeçalho](../../imagens/cabecalho.png)

# Laboratório: Textos e listas que mudam

## O que vais construir

Vais construir dois programas para o clube de videojogos. O `codigo.py` arruma e confirma o código de um jogo, como `PLA-01`, e o `fila.py` gere a fila para a consola do clube.

No fim, o ecrã do `codigo.py` fica assim, com o que a pessoa escreveu a seguir à pergunta:

```text
Código do jogo?  pla_01 
O código PLA-01 é do género PLA e tem o número 1.
```

E o do `fila.py` fica assim:

```text
Nome, próximo, ou Enter para acabar: Rui
Rui entrou na fila, em 1.º lugar.
Nome, próximo, ou Enter para acabar: Ana
Ana entrou na fila, em 2.º lugar.
Nome, próximo, ou Enter para acabar: próximo
É a vez de Rui. Na fila: 1.
Nome, próximo, ou Enter para acabar: 

Ficaram na fila: 1
1. Ana
```

1. [Fase 1: Um texto é uma sequência de caracteres](#fase-1-um-texto-é-uma-sequência-de-caracteres)
2. [Fase 2: Uma fatia é um pedaço do texto](#fase-2-uma-fatia-é-um-pedaço-do-texto)
3. [Fase 3: Os métodos arrumam um texto](#fase-3-os-métodos-arrumam-um-texto)
4. [Fase 4: Um texto não se altera](#fase-4-um-texto-não-se-altera)
5. [Fase 5: O `in` pergunta se um texto contém outro](#fase-5-o-in-pergunta-se-um-texto-contém-outro)
6. [Fase 6: O `isdigit` confirma que um texto só tem algarismos](#fase-6-o-isdigit-confirma-que-um-texto-só-tem-algarismos)
7. [Fase 7: As f-strings juntam textos e valores](#fase-7-as-f-strings-juntam-textos-e-valores)
8. [Fase 8: O `append` faz uma lista crescer](#fase-8-o-append-faz-uma-lista-crescer)
9. [Fase 9: O `pop` tira um elemento pela posição](#fase-9-o-pop-tira-um-elemento-pela-posição)
10. [Fase 10: O `in` procura um elemento numa lista](#fase-10-o-in-procura-um-elemento-numa-lista)

## O que precisas

- A pasta `fp-python`, aberta no VS Code, e um terminal, que se abre no menu Terminal, com a opção New Terminal. Se não a tiveres, faz primeiro [Preparar o projeto](01-do-pseudocodigo-ao-python-laboratorio.md#preparar-o-projeto), no laboratório do tema 01.
- O comando que corre o Python no teu computador, `python`, `py` ou `python3`. Onde o texto diz `python`, usa o teu.

## Fase 1: Um texto é uma sequência de caracteres

Experimentas na consola do Python, onde cada linha mostra logo o resultado. O código `"DES-02"` tem seis caracteres, com os índices de 0 a 5. Rever: [Um texto é uma sequência de caracteres](../07-textos-e-listas-que-mudam.md#um-texto-é-uma-sequência-de-caracteres).

1. No terminal, escreve o teu comando do Python, sem mais nada, e carrega em Enter. O que deves ver: `>>>`, à espera de uma linha.

2. Escreve estas linhas, uma de cada vez, e carrega em Enter depois de cada uma. O que deves ver são os resultados que aqui estão.

   ```text
   >>> codigo = "DES-02"
   >>> codigo[0]
   'D'
   >>> codigo[3]
   '-'
   >>> len(codigo)
   6
   >>> codigo[-1]
   '2'
   ```

3. Provoca um erro: escreve `codigo[6]`. O que deves ver no fim da mensagem: `IndexError: string index out of range`. Num texto de 6 caracteres, o último índice é 5.

### Paragem 1

Sabes ler um carácter de um texto pelo índice, a contar do início e a contar do fim.

Pensa antes de continuares: no título `"Celeste"`, qual é o índice do último `e`, a contar do início? E a contar do fim? A resposta: 6 e -1.

## Fase 2: Uma fatia é um pedaço do texto

Continuas na consola e tiras as duas partes do código. O segundo índice de uma fatia não entra. Rever: [Uma fatia é um pedaço do texto](../07-textos-e-listas-que-mudam.md#uma-fatia-é-um-pedaço-do-texto).

1. Com o mesmo `codigo`, escreve estas linhas e confirma os resultados:

   ```text
   >>> codigo[0:3]
   'DES'
   >>> codigo[:3]
   'DES'
   >>> codigo[4:]
   '02'
   ```

   As fatias `[:3]` e `[4:]` separam o género e o número de qualquer código do clube.

2. Agora experimenta a fatia que engana. Escreve `codigo[0:2]`. O que deves ver: `'DE'`, só com dois caracteres, porque o índice 2 não entra.

3. Sai da consola com `exit()` e Enter.

### Paragem 2

Sabes tirar uma fatia de um texto.

Pensa antes de continuares: que fatia de `"DES-02"` dá só o hífen? A resposta: `codigo[3:4]`.

## Fase 3: Os métodos arrumam um texto

Crias o programa, que arruma o que a pessoa escreveu antes de o usar. O `strip` tira os espaços das pontas, e o `upper` passa a maiúsculas. Rever: [Os métodos arrumam um texto](../07-textos-e-listas-que-mudam.md#os-métodos-arrumam-um-texto).

1. No painel Explorer, cria um ficheiro novo, com o nome `codigo.py`, e escreve nele:

   ```python
   # codigo.py: lê o código de um jogo do clube, arruma-o, confirma a forma e separa as partes.
   escrito = input("Código do jogo? ")
   # Cada método devolve um texto novo: primeiro sem os espaços, depois em maiúsculas.
   codigo = escrito.strip().upper()
   prefixo = codigo[:3]
   numero = codigo[4:]
   print("Código arrumado:", codigo)
   print("Género:", prefixo)
   print("Número:", numero)
   ```

2. Guarda e corre o programa, e escreve ` pla-01 `, com um espaço antes e outro depois:

   ```bash
   python codigo.py
   ```

   O que deves ver:

   ```text
   Código do jogo?  pla-01 
   Código arrumado: PLA-01
   Género: PLA
   Número: 01
   ```

   Se aparecer outra coisa, vê [Se alguma coisa falhar](#se-alguma-coisa-falhar).

3. Provoca um erro: apaga o `.strip()`, para ficar `codigo = escrito.upper()`. Guarda e corre outra vez, com ` pla-01 `. O que deves ver:

   ```text
   Código do jogo?  pla-01 
   Código arrumado:  PLA-01 
   Género:  PL
   Número: -01 
   ```

   O espaço do início ficou no índice 0, e a fatia `[:3]` apanhou-o. Não há mensagem nenhuma: é um erro de lógica. Volta a pôr o `.strip()` e guarda.

### Paragem 3

O `codigo.py` arruma o código escrito e separa o género e o número.

Pensa antes de continuares: depois de escreveres ` pla-01 `, quanto vale `escrito`, no fim do programa? A resposta: continua `" pla-01 "`, porque os métodos devolveram textos novos.

## Fase 4: Um texto não se altera

Há quem escreva o código com outro separador, como `pla_01`, e o programa tem de pôr um hífen no índice 3. Mudar esse carácter não se pode, e por isso constrói-se um texto novo. Rever: [Um texto não se altera](../07-textos-e-listas-que-mudam.md#um-texto-não-se-altera).

1. Corre o programa com `pla_01`. O que deves ver na segunda linha: `Código arrumado: PLA_01`, com o traço baixo.

2. Provoca um erro. Põe o cursor no fim da linha `codigo = escrito.strip().upper()` e carrega em Enter. Na linha nova, escreve:

   ```python
   codigo[3] = "-"
   ```

   Guarda e corre com `pla_01`. O que deves ver:

   ```text
   Código do jogo? pla_01
   Traceback (most recent call last):
     File "C:\Users\aluno\Documents\fp-python\codigo.py", line 5, in <module>
       codigo[3] = "-"
       ~~~~~~^^^
   TypeError: 'str' object does not support item assignment
   ```

3. Substitui a linha `codigo[3] = "-"` por estas duas:

   ```python
   # Um texto não se altera: para pôr o hífen, constrói-se um texto novo com duas fatias.
   codigo = codigo[:3] + "-" + codigo[4:]
   ```

4. Guarda e corre três vezes, com `pla_01`, com ` des 02 ` e com `PLA-01`. O que deves ver no código arrumado: `PLA-01`, `DES-02` e `PLA-01`.

### Paragem 4

O `codigo.py` aceita um código com qualquer separador no índice 3.

Pensa antes de continuares: porque é que não serve o `replace("_", "-")`? A resposta: só trata o traço baixo, e falhava com `pla 01`.

## Fase 5: O `in` pergunta se um texto contém outro

Com `pl4-01`, o programa mostra um código que não existe. Percorres o género carácter a carácter e perguntas se cada um está no texto das 26 letras. Rever: [O `in` pergunta se um texto contém outro](../07-textos-e-listas-que-mudam.md#o-in-pergunta-se-um-texto-contém-outro).

1. Põe o cursor no fim da linha 1 e carrega em Enter. Na linha nova, escreve:

   ```python
   LETRAS = "ABCDEFGHIJKLMNOPQRSTUVWXYZ"
   ```

2. Substitui as três linhas do `print` por estas:

   ```python
   # Percorre o género carácter a carácter: basta um que não seja letra para falhar.
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

3. Guarda e corre três vezes, com ` pla_01 `, `pla01` e `pl4-01`. O que deves ver: as três linhas de sempre com ` pla_01 `, e nos outros dois casos:

   ```text
   Código do jogo? pla01
   O código pla01 não tem a forma certa, como PLA-01.
   ```

   ```text
   Código do jogo? pl4-01
   O código pl4-01 não tem a forma certa, como PLA-01.
   ```

   O `pla01` passa a `PLA-1`, com 5 caracteres, e falha no tamanho. O `pl4-01` falha nas letras, por causa do 4.

4. Corre outra vez, com `pla-0a`. O que deves ver: o programa aceita-o, com `Número: 0A`. Nada confirma ainda os algarismos.

### Paragem 5

O `codigo.py` recusa um código com o tamanho errado ou sem três letras no género.

Pensa antes de continuares: se a bandeira `so_letras` começasse em `False`, o que mostrava o programa com ` pla_01 `? A resposta: dizia que o código não tem a forma certa, porque nenhuma linha a põe a `True`.

## Fase 6: O `isdigit` confirma que um texto só tem algarismos

Falta confirmar que o número tem só algarismos. Os textos têm um método que faz essa procura. Rever: [O `isdigit` confirma que um texto só tem algarismos](../07-textos-e-listas-que-mudam.md#o-isdigit-confirma-que-um-texto-só-tem-algarismos).

1. Muda a linha do `if len(codigo)` para ficar assim:

   ```python
   if len(codigo) == 6 and so_letras and numero.isdigit():
   ```

2. Guarda e corre três vezes, com ` pla_01 `, `pla-0a` e `des-002`. O que deves ver: as três linhas de sempre com ` pla_01 `, e a mensagem de recusa nos outros dois casos. O `des-002` tem 7 caracteres, e falha no tamanho.

### Paragem 6

O `codigo.py` confirma o tamanho, as letras e os algarismos.

Pensa antes de continuares: o programa aceita `plax01`, com um x no lugar do separador? Corre-o e explica. A resposta: aceita, porque as fatias saltam o índice 3. Um dos desafios trata disso.

## Fase 7: As f-strings juntam textos e valores

O clube quer uma só frase. Com o `print` e as vírgulas, aparecia um espaço antes do ponto final. Rever: [As f-strings juntam textos e valores](../07-textos-e-listas-que-mudam.md#as-f-strings-juntam-textos-e-valores).

1. Substitui o bloco do `if len(codigo)` e do `else`, até ao fim do ficheiro, por este:

   ```python
   if len(codigo) == 6 and so_letras and numero.isdigit():
       # O int() tira o zero à esquerda: o texto "01" passa ao número 1.
       print(f"O código {codigo} é do género {prefixo} e tem o número {int(numero)}.")
   else:
       print(f"O código {escrito.strip()} não tem a forma certa, como PLA-01.")
   ```

2. Guarda e corre com ` pla_01 ` e com `des 02`. O que deves ver: `O código PLA-01 é do género PLA e tem o número 1.` e `O código DES-02 é do género DES e tem o número 2.`.

3. Provoca um erro: apaga o `f` da primeira f-string. Guarda e corre com `pla-01`. O que deves ver: `O código {codigo} é do género {prefixo} e tem o número {int(numero)}.`. Volta a pôr o `f` e guarda.

4. Provoca outro erro: na linha do `if len(codigo)`, apaga o ` and numero.isdigit()`. Guarda e corre com `pla-0a`. O que deves ver:

   ```text
   Código do jogo? pla-0a
   Traceback (most recent call last):
     File "C:\Users\aluno\Documents\fp-python\codigo.py", line 18, in <module>
       print(f"O código {codigo} é do género {prefixo} e tem o número {int(numero)}.")
                                                                       ~~~^^^^^^^^
   ValueError: invalid literal for int() with base 10: '0A'
   ```

   A mensagem aponta o `print`, mas a causa está no `if`, a que falta uma condição. Volta a pôr o ` and numero.isdigit()` e guarda.

### Paragem 7

O `codigo.py` está completo.

O ficheiro `codigo.py` completo, como deve estar no fim:

```python
# codigo.py: lê o código de um jogo do clube, arruma-o, confirma a forma e separa as partes.
LETRAS = "ABCDEFGHIJKLMNOPQRSTUVWXYZ"
escrito = input("Código do jogo? ")
# Cada método devolve um texto novo: primeiro sem os espaços, depois em maiúsculas.
codigo = escrito.strip().upper()
# Um texto não se altera: para pôr o hífen, constrói-se um texto novo com duas fatias.
codigo = codigo[:3] + "-" + codigo[4:]
prefixo = codigo[:3]
numero = codigo[4:]
# Percorre o género carácter a carácter: basta um que não seja letra para falhar.
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

Pensa antes de continuares: o que escrevia `print(f"{prefixo}{numero}")`, com o código `PLA-01`? A resposta: `PLA01`, sem espaço nem hífen.

## Fase 8: O `append` faz uma lista crescer

Começas o segundo programa, com uma fila que nasce vazia. O `append` muda a própria lista. Rever: [O `append` faz uma lista crescer](../07-textos-e-listas-que-mudam.md#o-append-faz-uma-lista-crescer).

1. Cria o ficheiro `fila.py` e escreve nele:

   ```python
   # fila.py: a fila para a consola do clube.
   fila = []
   entrada = input("Nome (Enter para acabar): ").strip()
   # O texto vazio, de quem carrega em Enter sem escrever nada, faz de sentinela.
   while entrada != "":
       fila.append(entrada)
       print(f"{entrada} entrou na fila, em {len(fila)}.º lugar.")
       entrada = input("Nome (Enter para acabar): ").strip()
   print(f"Ficaram na fila: {len(fila)}")
   print(fila)
   ```

2. Guarda e corre, com `Rui`, `Ana`, `Bia` e Enter sem nada. O que deves ver:

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

3. Provoca um erro: muda a linha do `append` para `fila = fila.append(entrada)`. Guarda e corre com `Rui`. O que deves ver:

   ```text
   Nome (Enter para acabar): Rui
   Traceback (most recent call last):
     File "C:\Users\aluno\Documents\fp-python\fila.py", line 7, in <module>
       print(f"{entrada} entrou na fila, em {len(fila)}.º lugar.")
                                             ~~~^^^^^^
   TypeError: object of type 'NoneType' has no len()
   ```

   O `append` devolveu `None`, e a atribuição deitou a lista fora. A mensagem aponta a linha 7, mas a causa está na linha 6. Volta a pôr `fila.append(entrada)`, guarda e corre outra vez.

### Paragem 8

O `fila.py` junta os nomes numa lista que cresce.

Pensa antes de continuares: o que mostrava `print(fila)` logo a seguir a `fila = fila.append(entrada)`? A resposta: `None`.

## Fase 9: O `pop` tira um elemento pela posição

Quem escreve `próximo` chama o primeiro a jogar. O `pop` tira-o da fila e devolve o nome. Rever: [O `pop` tira um elemento pela posição](../07-textos-e-listas-que-mudam.md#o-pop-tira-um-elemento-pela-posição).

1. Substitui as linhas da leitura e do ciclo, de `entrada = input(...)` até à última leitura, por estas:

   ```python
   entrada = input("Nome, próximo, ou Enter para acabar: ").strip()
   # O texto vazio, de quem carrega em Enter sem escrever nada, faz de sentinela.
   while entrada != "":
       # O lower aceita também Próximo ou PRÓXIMO.
       if entrada.lower() == "próximo":
           a_jogar = fila.pop(0)
           print(f"É a vez de {a_jogar}. Na fila: {len(fila)}.")
       else:
           fila.append(entrada)
           print(f"{entrada} entrou na fila, em {len(fila)}.º lugar.")
       entrada = input("Nome, próximo, ou Enter para acabar: ").strip()
   ```

2. Guarda e corre, com `Rui`, `Ana`, `próximo`, `Bia`, `PRÓXIMO` e Enter sem nada. O que deves ver no fim:

   ```text
   Nome, próximo, ou Enter para acabar: PRÓXIMO
   É a vez de Ana. Na fila: 1.
   Nome, próximo, ou Enter para acabar: 
   Ficaram na fila: 1
   ['Bia']
   ```

3. Testa o caso que engana: corre outra vez e escreve logo `próximo`. O que deves ver:

   ```text
   Nome, próximo, ou Enter para acabar: próximo
   Traceback (most recent call last):
     File "C:\Users\aluno\Documents\fp-python\fila.py", line 8, in <module>
       a_jogar = fila.pop(0)
   IndexError: pop from empty list
   ```

4. Substitui as duas linhas do `pop` e do `print` a seguir, dentro do `if`, por estas:

   ```python
           # Com a fila vazia, o pop(0) parava o programa: não há ninguém para chamar.
           if len(fila) == 0:
               print("A fila está vazia.")
           else:
               a_jogar = fila.pop(0)
               print(f"É a vez de {a_jogar}. Na fila: {len(fila)}.")
   ```

5. Guarda e corre, com `próximo`, `Eva`, `próximo` e Enter sem nada. O que deves ver: `A fila está vazia.`, `Eva entrou na fila, em 1.º lugar.`, `É a vez de Eva. Na fila: 0.`, e no fim `Ficaram na fila: 0` e `[]`.

### Paragem 9

O `fila.py` chama o primeiro da fila e não para com a fila vazia.

Pensa antes de continuares: com `fila.pop()` em vez de `fila.pop(0)`, quem jogava primeiro? A resposta: o último a chegar.

## Fase 10: O `in` procura um elemento numa lista

Ninguém pode estar duas vezes na fila, e no fim o programa mostra quem ficou. Antes de acrescentar um nome, o programa pergunta se ele já lá está. Rever: [O `in` procura um elemento numa lista](../07-textos-e-listas-que-mudam.md#o-in-procura-um-elemento-numa-lista).

1. Há dois `else` no ficheiro, e o que interessa é o de fora, com quatro espaços antes. Clica no início dessa linha e carrega em Enter. Na linha em branco que ficou por cima, escreve estas duas linhas, com o `elif` alinhado com esse `else`:

   ```python
       elif entrada in fila:
           print(f"{entrada} já está na fila.")
   ```

2. Substitui os dois `print` depois do ciclo por estas linhas, e deixa uma linha vazia no ficheiro antes delas:

   ```python
   print()
   if len(fila) == 0:
       print("A fila ficou vazia.")
   else:
       print(f"Ficaram na fila: {len(fila)}")
       for i in range(0, len(fila)):
           # O i + 1 dá o lugar de cada um, a contar do 1.
           print(f"{i + 1}. {fila[i]}")
   ```

3. Guarda e corre, com `Rui`, `Ana`, `Rui`, `próximo`, `Bia`, `Rui` e Enter sem nada. O que deves ver:

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

   O último Rui entrou, porque já tinha saído da fila para jogar.

### Paragem 10

O `fila.py` está completo.

O ficheiro `fila.py` completo, como deve estar no fim:

```python
# fila.py: a fila para a consola do clube.
fila = []
entrada = input("Nome, próximo, ou Enter para acabar: ").strip()
# O texto vazio, de quem carrega em Enter sem escrever nada, faz de sentinela.
while entrada != "":
    # O lower aceita também Próximo ou PRÓXIMO.
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
        # O i + 1 dá o lugar de cada um, a contar do 1.
        print(f"{i + 1}. {fila[i]}")
```

Pensa antes de continuares: corre o programa com `Rui` e depois `rui`. O que acontece? A resposta: os dois entram, porque são textos diferentes.

## Se alguma coisa falhar

1. Guardaste o ficheiro? O Python corre o que está no disco, e não o que vês no ecrã.
2. Estás na pasta certa? No terminal, o texto antes do cursor tem de ter `fp-python` no fim, antes do `>` ou do `%`.
3. Estás na consola do Python sem quereres? Se a linha começa por `>>>`, escreve `exit()` e carrega em Enter.
4. Desfizeste o que mudaste para experimentar? Antes de passares à fase seguinte, o programa tem de voltar a dar o resultado certo.

### A fatia tem um carácter a menos

O segundo índice da fatia não entra. Para os três primeiros caracteres, a fatia é `[:3]`, e não `[:2]`.

### O género aparece com um espaço, como ` PL`

Falta o `.strip()` na linha que arruma o código. O espaço do início ocupa o índice 0.

### `TypeError: 'str' object does not support item assignment`

Estás a tentar mudar um carácter de um texto. Constrói um texto novo e guarda-o na variável.

### Um código certo é recusado

Confirma que o `LETRAS` tem as 26 letras, em maiúsculas, e que a linha que arruma o código tem os dois métodos.

### Aparecem as chavetas no ecrã, como `{codigo}`

Falta o `f` antes das aspas da f-string.

### `TypeError: object of type 'NoneType' has no len()`

Guardaste o resultado do `append`. Escreve só `fila.append(...)`.

### `IndexError: pop from empty list`

Fizeste um `pop` com a fila vazia. Antes do `pop`, pergunta se a fila tem alguém.

### Quem escreve `proximo`, sem acento, entra na fila

O programa compara com `"próximo"`, com acento, e para o Python são textos diferentes. Escreve a palavra com o acento.

## Desafios

Faz cada desafio num ficheiro novo, como `desafio_1.py`, com o código do programa copiado para lá.

1. O `codigo.py` deixa de acabar quando o código não tem a forma certa, e pede o código outra vez, até receber um certo. Testa com `pla01`, depois `pl4-01` e por fim `pla-01`. Pista: pensa em todas as linhas que têm de se repetir, incluindo a bandeira.
2. O `codigo.py` passa a recusar um separador errado. Os separadores certos são o hífen, o traço baixo, o espaço e o ponto. Testa com `plax01`, `pla101`, `pla_01`, `pla.01`, ` pla 01 `, `pla-01` e `pla`. Pista: o separador tem de se confirmar antes de o programa lá pôr o hífen.
3. No `fila.py`, quem escrever `sai` seguido de um nome, como `sai Ana`, tira essa pessoa da fila. Se a pessoa não estiver na fila, o programa diz-o e não para. Testa com `Rui`, `Ana`, `Bia`, `sai Ana`, `sai Eva` e Enter: no fim, a fila deve ser Rui e Bia. Pista: uma fatia dá o nome que vem depois de `sai `. Rever: [O `remove` e o `insert` também mudam a lista](../07-textos-e-listas-que-mudam.md#o-remove-e-o-insert-também-mudam-a-lista).
4. No `fila.py`, quem escrever `frente` seguido de um nome, como `frente Bia`, passa essa pessoa para o primeiro lugar. Se a pessoa ainda não estiver na fila, entra logo em primeiro. Testa com `Rui`, `Ana`, `Bia`, `frente Bia`, `frente Eva` e Enter: no fim, a fila deve ser Eva, Bia, Rui e Ana. Pista: há um método das listas que põe um valor numa posição.

## Antes de terminares

- [ ] O `codigo.py` mostra a frase certa com ` pla_01 ` e com `des 02`, e recusa `pla01`, `pl4-01`, `pla-0a` e `des-002`.
- [ ] O `fila.py` dá o ecrã do passo 3 da fase 10, e não para com `próximo` e a fila vazia.

![Rodapé](../../imagens/rodape.png)
