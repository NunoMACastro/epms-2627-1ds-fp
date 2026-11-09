![Cabeçalho](../../imagens/cabecalho.png)

# Laboratório: Funções

## O que vais construir

Vais construir `partidas.py`, um programa que faz o resumo das partidas de uma semana num jogo online. Cada parte do resumo é uma função, testada sozinha antes de ser usada.

No fim, o ecrã fica assim:

```text
Pontos das partidas: [1200, 850, 2000, 400, 1750, 1000]
Total da semana: 7200
Média por partida: 1200.0
Partida 1 teve 1200 pontos: boa
Partida 2 teve 850 pontos: fraca
Partida 3 teve 2000 pontos: excelente
Partida 4 teve 400 pontos: fraca
Partida 5 teve 1750 pontos: boa
Partida 6 teve 1000 pontos: boa
Partidas acima da média: 2
```

1. [Fase 1: Escrever uma função com `def` e `return`](#fase-1-escrever-uma-função-com-def-e-return)
2. [Fase 2: Testar cada função sozinha](#fase-2-testar-cada-função-sozinha)
3. [Fase 3: Uma função pode chamar outra](#fase-3-uma-função-pode-chamar-outra)
4. [Fase 4: O `return` entrega o valor e termina a função](#fase-4-o-return-entrega-o-valor-e-termina-a-função)
5. [Fase 5: Uma função sem `return` devolve `None`](#fase-5-uma-função-sem-return-devolve-none)
6. [Fase 6: As funções que calculam devolvem, e a parte principal escreve](#fase-6-as-funções-que-calculam-devolvem-e-a-parte-principal-escreve)
7. [Fase 7: Os argumentos passam pela ordem dos parâmetros](#fase-7-os-argumentos-passam-pela-ordem-dos-parâmetros)
8. [Fase 8: A ordem no ficheiro: constantes, funções e parte principal](#fase-8-a-ordem-no-ficheiro-constantes-funções-e-parte-principal)

## O que precisas

- A pasta `fp-python`, aberta no VS Code, e um terminal, que se abre no menu Terminal, com a opção New Terminal. Se não a tiveres, faz primeiro [Preparar o projeto](01-do-pseudocodigo-ao-python-laboratorio.md#preparar-o-projeto), no laboratório do tema 01.
- O comando que corre o Python no teu computador, `python`, `py` ou `python3`. Onde o texto diz `python`, usa o teu.

## Fase 1: Escrever uma função com `def` e `return`

Crias o programa, com uma função que soma os pontos de todas as partidas. A `Função` do pseudocódigo passa a `def`, e o `devolver` passa a `return`. Rever: [Escrever uma função com `def` e `return`](../06-funcoes.md#escrever-uma-função-com-def-e-return) e [Chamar uma função: parâmetros e argumentos](../06-funcoes.md#chamar-uma-função-parâmetros-e-argumentos).

1. No painel Explorer, cria um ficheiro novo, com o nome `partidas.py`, e escreve nele:

   ```python
   # partidas.py: o resumo das partidas de uma semana num jogo online.


   def total_de_pontos(pontuacoes):
       """Devolve a soma dos pontos de uma lista de partidas.

       Recebe a lista com os pontos de cada partida, ints maiores ou iguais
       a zero. Devolve o total, um int. Com a lista vazia, devolve 0.
       """
       total = 0
       for pontos in pontuacoes:
           total = total + pontos
       # O return fica fora do ciclo: só se devolve depois de somar a lista toda.
       return total


   # A parte principal: usa as funções e escreve o resumo da semana.
   pontuacoes = [1200, 850, 2000, 400, 1750, 1000]
   print("Pontos das partidas:", pontuacoes)
   print("Total da semana:", total_de_pontos(pontuacoes))
   ```

2. Guarda e corre o programa:

   ```bash
   python partidas.py
   ```

   O que deves ver:

   ```text
   Pontos das partidas: [1200, 850, 2000, 400, 1750, 1000]
   Total da semana: 7200
   ```

   A lista passou para o parâmetro, a função devolveu 7200, e o 7200 ficou no sítio da chamada. Se aparecer outra coisa, vê [Se alguma coisa falhar](#se-alguma-coisa-falhar).

3. Confirma que o `def` sozinho não faz nada. Seleciona as três linhas abaixo do comentário `# A parte principal`. No menu Edit, escolhe a opção Toggle Line Comment, que põe um `#` no início de cada linha. Guarda e corre. O que deves ver: nada, e nenhum erro. Ninguém chamou a função. Com as três linhas ainda selecionadas, escolhe outra vez Toggle Line Comment, para tirar os `#`, e guarda.

### Paragem 1

O `partidas.py` tem uma função documentada, e a parte principal mostra o total.

Pensa antes de continuares: se escreveres `print(total)` no fim do ficheiro, o que acontece? A resposta: o programa para com `NameError`, porque o `total` só existe dentro da função. Rever: [As variáveis de uma função são locais](../06-funcoes.md#as-variáveis-de-uma-função-são-locais).

## Fase 2: Testar cada função sozinha

Confirmas que a função está certa antes de confiares nela. Cada teste é uma linha com um `print`: a chamada e o valor esperado. Rever: [Testar cada função sozinha](../06-funcoes.md#testar-cada-função-sozinha).

1. Calcula de cabeça o que a função deve devolver com `[]`, com `[500]` e com `[1200, 850, 2000]`.

2. Clica na linha em branco mesmo por cima do comentário `# A parte principal` e carrega em Enter. Na linha nova, escreve:

   ```python
   # Testes das funções sozinhas: o valor devolvido e o que se esperava.
   print(total_de_pontos([]), "esperado: 0")
   print(total_de_pontos([500]), "esperado: 500")
   print(total_de_pontos([1200, 850, 2000]), "esperado: 4050")
   ```

   Depois da última linha, carrega em Enter duas vezes, para ficarem duas linhas em branco antes da parte principal.

3. Guarda e corre. O que deves ver:

   ```text
   0 esperado: 0
   500 esperado: 500
   4050 esperado: 4050
   Pontos das partidas: [1200, 850, 2000, 400, 1750, 1000]
   Total da semana: 7200
   ```

   Nas três primeiras linhas, o devolvido bate com o esperado.

4. Provoca um erro: acrescenta quatro espaços ao início da linha `return total`, para ela ficar dentro do `for`. Guarda e corre. O que deves ver no início:

   ```text
   None esperado: 0
   500 esperado: 500
   1200 esperado: 4050
   ```

   Não há mensagem de erro, e dois testes falham. O `return` terminou a função na primeira volta. Com a lista vazia, o ciclo não deu voltas, e a função nunca chegou ao `return`. O teste com uma só partida passou por acaso, e é por isso que se testa com os três tipos de lista.

5. Tira os quatro espaços. Guarda e corre, e confirma que os três testes batem certo.

6. Seleciona as três linhas com `print` dos testes e escolhe Toggle Line Comment, no menu Edit, para as desligar. Guarda e corre. O que deves ver: só as duas linhas da parte principal.

### Paragem 2

A função `total_de_pontos` está testada, e os testes ficam no ficheiro, desligados.

Pensa antes de continuares: que lista com vários elementos não apanharia o `return` dentro do ciclo? A resposta: uma em que os outros elementos são todos 0, como `[500, 0, 0]`. A função devolvia 500 na primeira volta, que é também o total.

## Fase 3: Uma função pode chamar outra

Acrescentas a média por partida, que usa a função do total e o `len`. O Python faz primeiro as chamadas que estão dentro da conta. Rever: [Uma função pode chamar outra](../06-funcoes.md#uma-função-pode-chamar-outra).

1. Clica na linha em branco mesmo por cima do comentário `# Testes das funções sozinhas` e carrega em Enter. Na linha nova, escreve:

   ```python
   def media_de_pontos(pontuacoes):
       """Devolve a média dos pontos por partida.

       Recebe a lista com os pontos de cada partida, com pelo menos uma
       partida: com a lista vazia, a conta seria 0 / 0, e o programa parava.
       Devolve a média, um float.
       """
       return total_de_pontos(pontuacoes) / len(pontuacoes)
   ```

   Depois da última linha, carrega em Enter duas vezes, para ficarem duas linhas em branco antes dos testes.

2. Põe o cursor no fim da última linha de teste e carrega em Enter. Na linha nova, escreve:

   ```python
   print(media_de_pontos([500]), "esperado: 500.0")
   print(media_de_pontos([1000, 2000]), "esperado: 1500.0")
   print(media_de_pontos([1200, 850, 2000, 400, 1750, 1000]), "esperado: 1200.0")
   ```

   A lista vazia não entra, porque a documentação diz que a função não a aceita. Guarda e corre. O que deves ver no início:

   ```text
   500.0 esperado: 500.0
   1500.0 esperado: 1500.0
   1200.0 esperado: 1200.0
   ```

3. Vê o que acontece quando uma chamada não cumpre a documentação. Por baixo dos três testes da média, acrescenta esta linha:

   ```python
   print(media_de_pontos([]), "esperado: erro")
   ```

   Guarda e corre. O que deves ver no fim:

   ```text
   Traceback (most recent call last):
     File "C:\Users\aluno\Documents\fp-python\partidas.py", line 34, in <module>
       print(media_de_pontos([]), "esperado: erro")
             ~~~~~~~~~~~~~~~^^^^
     File "C:\Users\aluno\Documents\fp-python\partidas.py", line 24, in media_de_pontos
       return total_de_pontos(pontuacoes) / len(pontuacoes)
              ~~~~~~~~~~~~~~~~~~~~~~~~~~~~^~~~~~~~~~~~~~~~~
   ZeroDivisionError: division by zero
   ```

   A linha `File` de baixo diz onde o Python parou, dentro da função. A de cima diz quem a chamou. Quem lhe deu a lista vazia foi a chamada. Apaga esta linha de teste.

4. Desliga os três testes da média, com Toggle Line Comment. No fim do ficheiro, acrescenta:

   ```python
   # A média guarda-se numa variável, porque faz falta outra vez mais à frente.
   media_da_semana = media_de_pontos(pontuacoes)
   print("Média por partida:", media_da_semana)
   ```

   Guarda e corre. O que deves ver: `Pontos das partidas`, `Total da semana: 7200` e `Média por partida: 1200.0`.

### Paragem 3

O programa mostra o total e a média, calculados por duas funções testadas.

O ficheiro `partidas.py` completo, como deve estar agora:

```python
# partidas.py: o resumo das partidas de uma semana num jogo online.


def total_de_pontos(pontuacoes):
    """Devolve a soma dos pontos de uma lista de partidas.

    Recebe a lista com os pontos de cada partida, ints maiores ou iguais
    a zero. Devolve o total, um int. Com a lista vazia, devolve 0.
    """
    total = 0
    for pontos in pontuacoes:
        total = total + pontos
    # O return fica fora do ciclo: só se devolve depois de somar a lista toda.
    return total


def media_de_pontos(pontuacoes):
    """Devolve a média dos pontos por partida.

    Recebe a lista com os pontos de cada partida, com pelo menos uma
    partida: com a lista vazia, a conta seria 0 / 0, e o programa parava.
    Devolve a média, um float.
    """
    return total_de_pontos(pontuacoes) / len(pontuacoes)


# Testes das funções sozinhas: o valor devolvido e o que se esperava.
# print(total_de_pontos([]), "esperado: 0")
# print(total_de_pontos([500]), "esperado: 500")
# print(total_de_pontos([1200, 850, 2000]), "esperado: 4050")
# print(media_de_pontos([500]), "esperado: 500.0")
# print(media_de_pontos([1000, 2000]), "esperado: 1500.0")
# print(media_de_pontos([1200, 850, 2000, 400, 1750, 1000]), "esperado: 1200.0")


# A parte principal: usa as funções e escreve o resumo da semana.
pontuacoes = [1200, 850, 2000, 400, 1750, 1000]
print("Pontos das partidas:", pontuacoes)
print("Total da semana:", total_de_pontos(pontuacoes))
# A média guarda-se numa variável, porque faz falta outra vez mais à frente.
media_da_semana = media_de_pontos(pontuacoes)
print("Média por partida:", media_da_semana)
```

Pensa antes de continuares: porque é que valeu a pena testar o total antes da média? A resposta: se a média desse errado, o erro só podia estar na linha nova.

## Fase 4: O `return` entrega o valor e termina a função

Classificas cada partida: com 2000 pontos ou mais é excelente, de 1000 a 1999 é boa, e abaixo de 1000 é fraca. Há um `return` em cada caminho, e em cada chamada executa-se só um deles. Rever: [O `return` entrega o valor e termina a função](../06-funcoes.md#o-return-entrega-o-valor-e-termina-a-função).

1. Os 2000 e os 1000 são regras do jogo, e por isso ficam em constantes. Põe o cursor no fim da linha 1 e carrega em Enter. Na linha nova, escreve:

   ```python
   # As constantes: os pontos que separam as classificações das partidas.
   PONTOS_EXCELENTE = 2000
   PONTOS_BOA = 1000
   ```

2. Clica na linha em branco mesmo por cima dos testes e carrega em Enter. Na linha nova, escreve:

   ```python
   def classificar_partida(pontos):
       """Classifica uma partida pelos pontos que fez.

       Recebe os pontos da partida, um int. Devolve um texto: "excelente"
       com 2000 pontos ou mais, "boa" de 1000 a 1999 e "fraca" abaixo de 1000.
       """
       # A cadeia começa pela fronteira de cima: só chega ao elif quem tem menos de 2000.
       if pontos >= PONTOS_EXCELENTE:
           return "excelente"
       elif pontos >= PONTOS_BOA:
           return "boa"
       else:
           return "fraca"
   ```

   Depois da última linha, carrega em Enter duas vezes.

3. Há duas fronteiras, e cada uma testa-se com o valor de baixo, o da fronteira e o de cima. Põe o cursor no fim da última linha de teste, carrega em Enter e, na linha nova, escreve:

   ```python
   print(classificar_partida(999), "esperado: fraca")
   print(classificar_partida(1000), "esperado: boa")
   print(classificar_partida(1001), "esperado: boa")
   print(classificar_partida(1999), "esperado: boa")
   print(classificar_partida(2000), "esperado: excelente")
   print(classificar_partida(2001), "esperado: excelente")
   ```

   Guarda e corre. O que deves ver no início:

   ```text
   fraca esperado: fraca
   boa esperado: boa
   boa esperado: boa
   boa esperado: boa
   excelente esperado: excelente
   excelente esperado: excelente
   ```

   O 1000 e o 2000 são os casos que apanham um `>` escrito no lugar do `>=`.

### Paragem 4

A função `classificar_partida` dá o resultado certo nas duas fronteiras.

Pensa antes de continuares: o que acontecia se a condição do `PONTOS_BOA` viesse primeiro? A resposta: uma partida de 2000 pontos também tem 1000 ou mais, e ficava boa. O "excelente" nunca aparecia.

## Fase 5: Uma função sem `return` devolve `None`

Provocas o erro mais frequente com funções, o `return` esquecido. Os testes mostram-no, sem nenhuma mensagem de erro. Rever: [Uma função sem `return` devolve `None`](../06-funcoes.md#uma-função-sem-return-devolve-none).

1. Na linha `return "boa"`, apaga a palavra `return` e o espaço, para ficar só `"boa"`, com os oito espaços. Guarda e corre. O que deves ver no início:

   ```text
   fraca esperado: fraca
   None esperado: boa
   None esperado: boa
   None esperado: boa
   excelente esperado: excelente
   excelente esperado: excelente
   ```

   Nos casos de 1000 a 1999, a função passa pelo `"boa"` sem o entregar, e chega ao fim do corpo. Quando vires `None` onde esperavas um valor, procura um `return` em falta no caminho desse caso.

2. Volta a pôr `return "boa"`. Guarda e corre, e confirma os seis testes.

3. Desliga os seis testes da classificação, com Toggle Line Comment. Guarda.

### Paragem 5

A função voltou a devolver um texto em todos os caminhos, e os testes dela estão desligados.

Pensa antes de continuares: se só tivesses testado o 999 e o 2000, davas pelo erro? A resposta: não, porque nenhum dos dois entra no bloco do `elif`.

## Fase 6: As funções que calculam devolvem, e a parte principal escreve

Usas a classificação no resumo. A função devolve o texto, e é a parte principal que o escreve. Rever: [As funções que calculam devolvem, e a parte principal escreve](../06-funcoes.md#as-funções-que-calculam-devolvem-e-a-parte-principal-escreve).

1. No fim do ficheiro, acrescenta:

   ```python
   for i in range(0, len(pontuacoes)):
       pontos = pontuacoes[i]
       # O i + 1 faz com que a partida de índice 0 seja, para as pessoas, a partida 1.
       print("Partida", i + 1, "teve", pontos, "pontos:", classificar_partida(pontos))
   ```

   Guarda e corre. O que deves ver no fim:

   ```text
   Partida 1 teve 1200 pontos: boa
   Partida 2 teve 850 pontos: fraca
   Partida 3 teve 2000 pontos: excelente
   Partida 4 teve 400 pontos: fraca
   Partida 5 teve 1750 pontos: boa
   Partida 6 teve 1000 pontos: boa
   ```

2. Provoca um erro: na função, troca a linha `return "excelente"` por `print("excelente")`, com os mesmos oito espaços. Guarda e corre. O que deves ver na zona da partida 3:

   ```text
   Partida 2 teve 850 pontos: fraca
   excelente
   Partida 3 teve 2000 pontos: None
   Partida 4 teve 400 pontos: fraca
   ```

   O texto aparece no ecrã, mas não volta para a parte principal. Volta a pôr `return "excelente"`, guarda e corre.

### Paragem 6

Cada partida aparece com a sua classificação, dada por uma função testada.

O ficheiro `partidas.py` completo, como deve estar agora:

```python
# partidas.py: o resumo das partidas de uma semana num jogo online.
# As constantes: os pontos que separam as classificações das partidas.
PONTOS_EXCELENTE = 2000
PONTOS_BOA = 1000


def total_de_pontos(pontuacoes):
    """Devolve a soma dos pontos de uma lista de partidas.

    Recebe a lista com os pontos de cada partida, ints maiores ou iguais
    a zero. Devolve o total, um int. Com a lista vazia, devolve 0.
    """
    total = 0
    for pontos in pontuacoes:
        total = total + pontos
    # O return fica fora do ciclo: só se devolve depois de somar a lista toda.
    return total


def media_de_pontos(pontuacoes):
    """Devolve a média dos pontos por partida.

    Recebe a lista com os pontos de cada partida, com pelo menos uma
    partida: com a lista vazia, a conta seria 0 / 0, e o programa parava.
    Devolve a média, um float.
    """
    return total_de_pontos(pontuacoes) / len(pontuacoes)


def classificar_partida(pontos):
    """Classifica uma partida pelos pontos que fez.

    Recebe os pontos da partida, um int. Devolve um texto: "excelente"
    com 2000 pontos ou mais, "boa" de 1000 a 1999 e "fraca" abaixo de 1000.
    """
    # A cadeia começa pela fronteira de cima: só chega ao elif quem tem menos de 2000.
    if pontos >= PONTOS_EXCELENTE:
        return "excelente"
    elif pontos >= PONTOS_BOA:
        return "boa"
    else:
        return "fraca"


# Testes das funções sozinhas: o valor devolvido e o que se esperava.
# print(total_de_pontos([]), "esperado: 0")
# print(total_de_pontos([500]), "esperado: 500")
# print(total_de_pontos([1200, 850, 2000]), "esperado: 4050")
# print(media_de_pontos([500]), "esperado: 500.0")
# print(media_de_pontos([1000, 2000]), "esperado: 1500.0")
# print(media_de_pontos([1200, 850, 2000, 400, 1750, 1000]), "esperado: 1200.0")
# print(classificar_partida(999), "esperado: fraca")
# print(classificar_partida(1000), "esperado: boa")
# print(classificar_partida(1001), "esperado: boa")
# print(classificar_partida(1999), "esperado: boa")
# print(classificar_partida(2000), "esperado: excelente")
# print(classificar_partida(2001), "esperado: excelente")


# A parte principal: usa as funções e escreve o resumo da semana.
pontuacoes = [1200, 850, 2000, 400, 1750, 1000]
print("Pontos das partidas:", pontuacoes)
print("Total da semana:", total_de_pontos(pontuacoes))
# A média guarda-se numa variável, porque faz falta outra vez mais à frente.
media_da_semana = media_de_pontos(pontuacoes)
print("Média por partida:", media_da_semana)
for i in range(0, len(pontuacoes)):
    pontos = pontuacoes[i]
    # O i + 1 faz com que a partida de índice 0 seja, para as pessoas, a partida 1.
    print("Partida", i + 1, "teve", pontos, "pontos:", classificar_partida(pontos))
```

Pensa antes de continuares: a parte principal tem uma variável `pontos`, e duas funções também. Isto dá algum problema? A resposta: não, porque as variáveis de cada função são locais, e só têm o mesmo nome.

## Fase 7: Os argumentos passam pela ordem dos parâmetros

Contas as partidas acima da média, com uma função que recebe a lista e um limite. O primeiro argumento vai para o primeiro parâmetro, e o segundo para o segundo. Rever: [Os argumentos passam pela ordem dos parâmetros](../06-funcoes.md#os-argumentos-passam-pela-ordem-dos-parâmetros).

1. Como nas fases 3 e 4, a função nova fica por cima dos testes. Clica na linha em branco mesmo antes deles, carrega em Enter e escreve na linha nova:

   ```python
   def contar_acima(pontuacoes, limite):
       """Conta as partidas com mais pontos do que um limite.

       Recebe a lista com os pontos de cada partida e o limite, um número.
       Uma partida com os pontos iguais ao limite não conta. Devolve quantas
       partidas ficaram acima, um int. Com a lista vazia, devolve 0.
       """
       acima = 0
       for pontos in pontuacoes:
           if pontos > limite:
               acima = acima + 1
       return acima
   ```

   No fim, carrega em Enter duas vezes.

2. Põe o cursor no fim da última linha de teste, carrega em Enter e, na linha nova, escreve estes quatro testes:

   ```python
   print(contar_acima([], 1000), "esperado: 0")
   print(contar_acima([1000], 1000), "esperado: 0")
   print(contar_acima([1001], 1000), "esperado: 1")
   print(contar_acima([1200, 850, 2000], 1000), "esperado: 2")
   ```

   Guarda e corre. O que deves ver no início:

   ```text
   0 esperado: 0
   0 esperado: 0
   1 esperado: 1
   2 esperado: 2
   ```

   O segundo confirma a documentação: uma partida igual ao limite não conta.

3. Desliga os quatro testes. No fim do ficheiro, encostada à margem, acrescenta esta linha:

   ```python
   print("Partidas acima da média:", contar_acima(pontuacoes, media_da_semana))
   ```

   Guarda e corre. O que deves ver no fim: `Partidas acima da média: 2`. A partida 1, com 1200, é igual à média e não conta.

4. Provoca um erro: nessa linha, troca a ordem, para ficar `contar_acima(media_da_semana, pontuacoes)`. Guarda e corre. O que deves ver no fim:

   ```text
   Traceback (most recent call last):
     File "C:\Users\aluno\Documents\fp-python\partidas.py", line 89, in <module>
       print("Partidas acima da média:", contar_acima(media_da_semana, pontuacoes))
                                         ~~~~~~~~~~~~^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
     File "C:\Users\aluno\Documents\fp-python\partidas.py", line 53, in contar_acima
       for pontos in pontuacoes:
                     ^^^^^^^^^^
   TypeError: 'float' object is not iterable
   ```

   O parâmetro `pontuacoes` recebeu a média, e o `for` não consegue percorrer um número. A causa está na ordem dos argumentos, na linha `File` de cima. Volta a pôr `contar_acima(pontuacoes, media_da_semana)`, guarda e corre.

### Paragem 7

O programa mostra as dez linhas de "O que vais construir".

Pensa antes de continuares: e se os dois parâmetros fossem números, como no `preco_com_desconto` do guia? A resposta: o Python não dava erro nenhum, e só um teste mostrava o resultado errado.

## Fase 8: A ordem no ficheiro: constantes, funções e parte principal

Vês porque é que as funções ficam antes da parte principal. É a linha do `def` que cria a função, e o Python lê o ficheiro de cima para baixo. Rever: [A ordem no ficheiro: constantes, funções e parte principal](../06-funcoes.md#a-ordem-no-ficheiro-constantes-funções-e-parte-principal).

1. Provoca um erro: seleciona desde o comentário `# A parte principal` até à última linha do ficheiro, e corta com Ctrl+X, ou Cmd+X no macOS. Clica na primeira linha em branco a seguir a `PONTOS_BOA = 1000` e cola com Ctrl+V, ou Cmd+V. Guarda e corre. O que deves ver:

   ```text
   Pontos das partidas: [1200, 850, 2000, 400, 1750, 1000]
   Traceback (most recent call last):
     File "C:\Users\aluno\Documents\fp-python\partidas.py", line 8, in <module>
       print("Total da semana:", total_de_pontos(pontuacoes))
                                 ^^^^^^^^^^^^^^^
   NameError: name 'total_de_pontos' is not defined
   ```

   A função está escrita no ficheiro, mas o Python ainda não chegou ao `def` dela.

2. Desfaz a alteração com Ctrl+Z, ou Cmd+Z, até a parte principal voltar ao fim do ficheiro. Guarda e corre, e confirma que o resumo completo volta a aparecer.

### Paragem 8

O `partidas.py` está completo e arrumado, com as funções testadas.

O ficheiro `partidas.py` completo, como deve estar no fim:

```python
# partidas.py: o resumo das partidas de uma semana num jogo online.
# As constantes: os pontos que separam as classificações das partidas.
PONTOS_EXCELENTE = 2000
PONTOS_BOA = 1000


def total_de_pontos(pontuacoes):
    """Devolve a soma dos pontos de uma lista de partidas.

    Recebe a lista com os pontos de cada partida, ints maiores ou iguais
    a zero. Devolve o total, um int. Com a lista vazia, devolve 0.
    """
    total = 0
    for pontos in pontuacoes:
        total = total + pontos
    # O return fica fora do ciclo: só se devolve depois de somar a lista toda.
    return total


def media_de_pontos(pontuacoes):
    """Devolve a média dos pontos por partida.

    Recebe a lista com os pontos de cada partida, com pelo menos uma
    partida: com a lista vazia, a conta seria 0 / 0, e o programa parava.
    Devolve a média, um float.
    """
    return total_de_pontos(pontuacoes) / len(pontuacoes)


def classificar_partida(pontos):
    """Classifica uma partida pelos pontos que fez.

    Recebe os pontos da partida, um int. Devolve um texto: "excelente"
    com 2000 pontos ou mais, "boa" de 1000 a 1999 e "fraca" abaixo de 1000.
    """
    # A cadeia começa pela fronteira de cima: só chega ao elif quem tem menos de 2000.
    if pontos >= PONTOS_EXCELENTE:
        return "excelente"
    elif pontos >= PONTOS_BOA:
        return "boa"
    else:
        return "fraca"


def contar_acima(pontuacoes, limite):
    """Conta as partidas com mais pontos do que um limite.

    Recebe a lista com os pontos de cada partida e o limite, um número.
    Uma partida com os pontos iguais ao limite não conta. Devolve quantas
    partidas ficaram acima, um int. Com a lista vazia, devolve 0.
    """
    acima = 0
    for pontos in pontuacoes:
        if pontos > limite:
            acima = acima + 1
    return acima


# Testes das funções sozinhas: o valor devolvido e o que se esperava.
# print(total_de_pontos([]), "esperado: 0")
# print(total_de_pontos([500]), "esperado: 500")
# print(total_de_pontos([1200, 850, 2000]), "esperado: 4050")
# print(media_de_pontos([500]), "esperado: 500.0")
# print(media_de_pontos([1000, 2000]), "esperado: 1500.0")
# print(media_de_pontos([1200, 850, 2000, 400, 1750, 1000]), "esperado: 1200.0")
# print(classificar_partida(999), "esperado: fraca")
# print(classificar_partida(1000), "esperado: boa")
# print(classificar_partida(1001), "esperado: boa")
# print(classificar_partida(1999), "esperado: boa")
# print(classificar_partida(2000), "esperado: excelente")
# print(classificar_partida(2001), "esperado: excelente")
# print(contar_acima([], 1000), "esperado: 0")
# print(contar_acima([1000], 1000), "esperado: 0")
# print(contar_acima([1001], 1000), "esperado: 1")
# print(contar_acima([1200, 850, 2000], 1000), "esperado: 2")


# A parte principal: usa as funções e escreve o resumo da semana.
pontuacoes = [1200, 850, 2000, 400, 1750, 1000]
print("Pontos das partidas:", pontuacoes)
print("Total da semana:", total_de_pontos(pontuacoes))
# A média guarda-se numa variável, porque faz falta outra vez mais à frente.
media_da_semana = media_de_pontos(pontuacoes)
print("Média por partida:", media_da_semana)
for i in range(0, len(pontuacoes)):
    pontos = pontuacoes[i]
    # O i + 1 faz com que a partida de índice 0 seja, para as pessoas, a partida 1.
    print("Partida", i + 1, "teve", pontos, "pontos:", classificar_partida(pontos))
print("Partidas acima da média:", contar_acima(pontuacoes, media_da_semana))
```

Pensa antes de continuares: se mudares a lista para `[2500, 900]`, o que esperas que o programa escreva? Calcula de cabeça e experimenta. A resposta: o total é 3400 e a média é 1700.0. A partida 1 é excelente, a 2 é fraca, e só uma fica acima da média. Volta a pôr a lista das seis partidas.

## Se alguma coisa falhar

1. Guardaste o ficheiro? O Python corre o que está no disco, e não o que vês no ecrã.
2. Estás na pasta certa? No terminal, o texto antes do cursor tem de ter `fp-python` no fim, antes do `>` ou do `%`.
3. Desfizeste o que mudaste para experimentar? Antes de passares à fase seguinte, o programa tem de voltar a dar o resultado certo.

### `NameError: name '...' is not defined`, com o nome de uma função

A função foi chamada antes de o Python passar pelo `def` dela, ou o nome está escrito de outra maneira na chamada.

### Aparece `<function ... at 0x...>` no ecrã

Falta pôr os parênteses na chamada. O nome sozinho é a função, e não o valor que ela devolve.

### Aparece `None` onde devia aparecer um valor

A função chegou ao fim do corpo sem passar por nenhum `return`. Procura um `return` esquecido no caminho do caso que falhou, ou um `print` no lugar do `return`.

### `TypeError: ... missing 1 required positional argument`

A chamada tem menos argumentos do que a função tem parâmetros. A mensagem diz o nome do parâmetro que ficou sem valor.

### `TypeError: 'float' object is not iterable`

Uma função que percorre uma lista recebeu um número. Quase sempre, os argumentos da chamada estão pela ordem errada.

### `IndentationError: expected an indented block after function definition`

A linha a seguir ao cabeçalho do `def` ficou encostada à margem. A documentação e o corpo têm de estar indentados quatro espaços.

### As linhas de teste continuam a aparecer no ecrã

Falta o `#` no início de alguma linha de teste. Seleciona as linhas com `print` que ainda estão ligadas e escolhe Toggle Line Comment, no menu Edit.

## Desafios

Faz cada desafio num ficheiro novo, como `desafio_1.py`, com o código do programa copiado para lá. Cada função nova leva documentação e é testada sozinha antes de ser usada.

1. Escreve a função `melhor_partida(pontuacoes)`, que devolve a posição, o índice, da partida com mais pontos. Se houver várias com o máximo, devolve a primeira. Pensa no que acontece com a lista vazia e escreve-o na documentação. A parte principal escreve uma linha como `Melhor partida: a 3 com 2000 pontos`. Pista: guarda a posição do maior até agora e compara cada partida com a que está nessa posição.
2. Escreve a função `contar_classificacao(pontuacoes, classificacao)`, que conta quantas partidas têm a classificação dada, como `"boa"`. A parte principal escreve quantas partidas excelentes, boas e fracas houve. Pista: uma função pode chamar outra dentro de um ciclo.
3. Escreve a função `media_sem_a_pior(pontuacoes)`, que devolve a média dos pontos sem contar a partida com menos pontos. Pensa em quantas partidas a lista tem de ter, no mínimo, e escreve-o na documentação. Pista: falta uma função que diga quantos pontos teve a pior partida.

## Antes de terminares

- [ ] O `partidas.py` mostra o ecrã completo de "O que vais construir".
- [ ] As quatro funções têm documentação, com o que recebem e o que devolvem.
- [ ] As linhas de teste das quatro funções estão no ficheiro, desligadas com `#`.
- [ ] Nenhuma função tem um `print`.

![Rodapé](../../imagens/rodape.png)
