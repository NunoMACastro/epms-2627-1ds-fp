![Cabeçalho](../../imagens/cabecalho.png)

# Laboratório: Funções

Laboratório do tema Funções, do módulo Criar aplicações em linguagem de programação Python. Vais construir, uma função de cada vez, um programa que faz o resumo das partidas de uma semana num jogo online. Cada passo diz o que fazer, porquê e o que deves ver, e avanças ao teu ritmo. Tudo o que precisas está aqui; o [guia do tema](../06-funcoes.md) tem a teoria completa, para quem quiser saber mais.

## O que vais construir

Num jogo online, no fim de cada partida aparecem os pontos que fizeste. Guardaste numa lista os pontos das seis partidas que jogaste esta semana: 1200, 850, 2000, 400, 1750 e 1000. O teu programa, `partidas.py`, vai fazer o resumo da semana. Diz o total de pontos e a média por partida. Classifica cada partida como excelente, boa ou fraca, e conta quantas partidas ficaram acima da média.

No fim, o programa escreve isto:

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

Cada parte do resumo é calculada por uma função, e cada função é testada sozinha antes de a parte principal a usar. Pelo caminho, ficas a saber escrever funções com `def` e `return`, documentá-las, chamá-las com argumentos e escrever uma função que chama outra. Ficas também a saber reconhecer os erros mais frequentes com funções, porque vais provocar alguns de propósito.

| Fase | O que muda | O que funciona no fim |
| --- | --- | --- |
| 1 | `partidas.py`, com a função `total_de_pontos` e a parte principal | O programa mostra o total da semana |
| 2 | As linhas de teste da função `total_de_pontos` | A função está testada sozinha, com a lista vazia, uma partida e várias |
| 3 | A função `media_de_pontos`, que chama a `total_de_pontos` | O programa mostra também a média por partida |
| 4 | As constantes e a função `classificar_partida`, com três `return` | Cada partida aparece com a sua classificação |
| 5 | A função `contar_acima`, com dois parâmetros | O programa diz quantas partidas ficaram acima da média |
| 6 | A arrumação final do ficheiro | O programa completo, pela ordem constantes, funções e parte principal |

No fim, a tua pasta tem um ficheiro novo:

```text
fp-python/
└── partidas.py
```

## Palavras que vais usar

- Função: um bloco de código com nome, que recebe valores, faz um trabalho e devolve um resultado. Para saber mais, vê a secção "Porque é que se escrevem funções" do [guia](../06-funcoes.md).
- `def`: a palavra que começa uma função em Python; é a `Função` do pseudocódigo.
- `return`: entrega um valor a quem chamou a função e termina a função; é o `devolver` do pseudocódigo.
- Parâmetro: o nome que a função dá, no cabeçalho, a um valor que vai receber.
- Argumento: o valor que se dá à função quando se chama, entre os parênteses.
- Chamar uma função: escrever o nome dela com os argumentos entre parênteses, para ela se executar.
- Valor devolvido: o valor que a função entrega, e que fica no sítio da chamada.
- Documentação de uma função, ou docstring: o texto entre aspas triplas, `"""`, por baixo do cabeçalho. Diz o que a função faz, recebe e devolve. Para saber mais, vê a secção "A documentação de uma função" do [guia](../06-funcoes.md).
- Parte principal: as linhas encostadas à margem, depois das funções, que usam as funções e escrevem no ecrã.
- Variável local: um parâmetro, ou uma variável que nasce dentro de uma função; só existe enquanto ela se executa.
- `None`: o valor que quer dizer "nenhum valor"; é o que devolve uma função que acaba sem passar por um `return`.
- Linha de teste: um `print` com uma chamada a uma função e o valor que se espera que ela devolva.
- Testar uma função sozinha: chamá-la com valores escolhidos e comparar o que devolve com o que calculaste à mão, antes de a usar. Para saber mais, vê a secção "Testar cada função sozinha" do [guia](../06-funcoes.md).

## O que precisas

- O Python 3, o interpretador. Para confirmares que o tens, abre o terminal do VS Code e escreve `python --version`, ou `python3 --version` no macOS. Deve aparecer uma linha como `Python 3.14.0`, com o primeiro número 3.
- O VS Code, com a pasta `fp-python` aberta, a mesma dos laboratórios anteriores. Se não a tiveres, cria-a, como no laboratório do tema 01, e abre-a no menu File, com a opção Open Folder.

Os resultados e as mensagens de erro deste laboratório são os do Python 3.14. Num Python mais antigo, uma mensagem pode ter outras palavras, ou não ter os sinais `^` e `~` por baixo da linha. O tipo de erro, a palavra antes dos dois pontos na última linha, é o mesmo. O caminho do ficheiro nas mensagens, como `C:\Users\aluno\Documents\fp-python\partidas.py`, é o do computador onde o programa correu, e no teu é outro.

## Se alguma coisa falhar

1. Guardaste o ficheiro? O Python corre o que está guardado no disco, e não o que vês no ecrã. Guarda com Ctrl+S, ou Cmd+S no macOS. Uma bola cheia no separador do ficheiro, no lugar do X, quer dizer que há alterações por guardar.
2. Estás na pasta certa? No terminal, o texto antes do cursor tem de acabar em `fp-python`. Se não acabar, fecha o terminal e abre outro no menu Terminal, com a opção New Terminal.
3. Estás na consola do Python sem quereres? Se a linha começa por `>>>`, escreve `exit()` e carrega em Enter, para voltares ao terminal.
4. Copiaste o código à mão? Confirma os dois pontos no fim das linhas do `def`, do `for`, do `if`, do `elif` e do `else`. Confirma também os espaços da indentação. São quatro dentro de uma função, e oito dentro de um `for` ou de um `if` que está dentro de uma função.
5. Perdeste-te nas alterações? No fim de cada fase, na paragem, está o ficheiro completo, ou o que mudou. Compara o teu, linha a linha.

## Preparar o projeto

1. Abre a pasta `fp-python` no VS Code, se ainda não estiver aberta. O que deves ver: à esquerda, no painel Explorer, o nome `FP-PYTHON`, com os ficheiros dos temas anteriores.

2. Cria um ficheiro novo, `partidas.py`. No painel Explorer, passa o rato por cima do nome da pasta e carrega no ícone New File, a folha com um sinal de mais. Escreve o nome `partidas.py` e carrega em Enter. O ficheiro abre-se vazio, à direita.

## Fase 1: Escrever e chamar uma função

A primeira parte do resumo é o total de pontos da semana. Com o que já sabes, fazia-se com um acumulador e um `for`, na parte principal. Agora, essa conta vai para uma função, com um nome que diz o que ela faz. Na algoritmia escrevias `Função totalDePontos(pontuacoes)` e `devolver total`. Em Python, a `Função` passa a `def` e o `devolver` passa a `return`. O cabeçalho acaba com dois pontos, e o corpo da função vai indentado, como num `if`.

Uma função escrita ainda não faz nada. Só se executa quando alguém a chama, com o nome e os valores entre parênteses. Para saber mais, lê a secção "Escrever uma função com `def` e `return`" do [guia](../06-funcoes.md).

1. Escreve em `partidas.py` este conteúdo e guarda:

   ```python
   # partidas.py: o resumo das partidas de uma semana num jogo online.
   # Nesta fase, soma os pontos de todas as partidas.


   def total_de_pontos(pontuacoes):
       """Devolve a soma dos pontos de uma lista de partidas.

       Recebe a lista com os pontos de cada partida, ints maiores ou iguais
       a zero. Devolve o total, um int. Com a lista vazia, devolve 0.
       """
       total = 0
       for pontos in pontuacoes:
           total = total + pontos
       return total


   pontuacoes = [1200, 850, 2000, 400, 1750, 1000]
   print("Pontos das partidas:", pontuacoes)
   print("Total da semana:", total_de_pontos(pontuacoes))
   ```

   Leitura guiada: começa pela linha do `def`. É o cabeçalho: a função chama-se `total_de_pontos` e recebe um valor, a que dá o nome `pontuacoes`. A esse nome chama-se **parâmetro**. Logo por baixo, entre aspas triplas, `"""`, está a documentação da função. Diz o que ela devolve, o que recebe e o que faz com a lista vazia. O Python guarda este texto, mas não o executa. A seguir vem o corpo, com o acumulador e o `for` que já conheces, e no fim o `return total`, que entrega o total. As duas linhas em branco antes e depois da função são uma convenção do Python, para se ver bem onde ela começa e acaba. As três linhas encostadas à margem, no fim, são a **parte principal**: é aí que o programa começa a fazer coisas.

2. Antes de correres, prevê o total das seis partidas. Depois, no terminal, corre:

   ```bash
   python partidas.py
   ```

   No Windows, se o `python` não funcionar, o comando é `py partidas.py`. No macOS, é `python3 partidas.py`. Também podes usar o botão de correr do VS Code, no canto de cima à direita.

   O que deves ver:

   ```text
   Pontos das partidas: [1200, 850, 2000, 400, 1750, 1000]
   Total da semana: 7200
   ```

   Isto quer dizer que a chamada funcionou. Na última linha, `total_de_pontos(pontuacoes)` é a chamada. A lista passa para o parâmetro, a função soma-a e devolve 7200, e o 7200 fica no sítio da chamada, dentro do `print`.

3. Confirma que o `def` sozinho não faz nada. Seleciona as três linhas da parte principal. Depois, no menu Edit, escolhe a opção Toggle Line Comment, isto é, "ligar ou desligar o comentário da linha". O nome foi confirmado a 2 de novembro de 2026, no VS Code 1.144, em inglês. O VS Code põe um `#` no início de cada linha selecionada, e as três passam a ser comentários. O atalho de teclado para fazer o mesmo aparece ao lado da opção, no menu. Guarda e corre outra vez. O que deves ver: nada, e nenhum erro. O Python passou pelo `def`, criou a função, e ninguém a chamou. Seleciona outra vez as três linhas e escolhe de novo Toggle Line Comment, para tirar os `#`. Guarda.

### Paragem 1

O `partidas.py` tem uma função documentada, e a parte principal chama-a e mostra `Total da semana: 7200`.

Pensa antes de continuares: dentro da função há uma variável `total`. Se escreveres `print(total)` no fim do ficheiro, na parte principal, o que acontece? A resposta: o programa escreve as duas linhas e para com `NameError: name 'total' is not defined`, isto é, "o nome `total` não está definido". O `total` é uma **variável local** da função: nasce quando a função é chamada e desaparece quando ela devolve o valor. Fora da função, o nome não existe. O que sai da função é só o valor do `return`. Se fizeste a experiência, apaga a linha `print(total)`.

## Fase 2: Testar a função sozinha

O total deu 7200, que é a soma das seis partidas. Mas um caso só não chega para confiar numa função. Uma função que recebe uma lista testa-se com três tipos de lista. São a lista vazia, se a função a aceitar, uma lista com um elemento e uma lista com vários. A documentação diz que a função aceita a lista vazia e que devolve 0.

Testar a função sozinha quer dizer chamá-la com estas listas, antes de a parte principal a usar. Depois compara-se o que ela devolve com o que calculaste à mão. Cada teste é uma linha com um `print`: primeiro a chamada, depois o texto com o valor esperado. Assim, cada linha do ecrã mostra as duas coisas lado a lado. As linhas de teste ficam depois das funções e antes da parte principal. Para saber mais, lê a secção "Testar cada função sozinha" do [guia](../06-funcoes.md).

1. Antes de escreveres os testes, calcula de cabeça o que a função deve devolver com cada uma destas listas: `[]`, `[500]` e `[1200, 850, 2000]`.

2. Em `partidas.py`, a seguir ao `return total` e às duas linhas em branco, antes da linha `pontuacoes = [...]`, acrescenta estas linhas, encostadas à margem:

   ```python
   # Testes das funções sozinhas: o valor devolvido e o que se esperava.
   print(total_de_pontos([]), "esperado: 0")
   print(total_de_pontos([500]), "esperado: 500")
   print(total_de_pontos([1200, 850, 2000]), "esperado: 4050")


   ```

   As duas linhas em branco do fim separam os testes da parte principal.

   Leitura guiada: cada linha chama a função com uma lista escrita ali mesmo, entre parênteses retos. A chamada não precisa de uma variável: o argumento pode ser a própria lista. O `print` escreve o valor devolvido e, a seguir, o texto com o esperado.

3. Guarda e corre. O que deves ver:

   ```text
   0 esperado: 0
   500 esperado: 500
   4050 esperado: 4050
   Pontos das partidas: [1200, 850, 2000, 400, 1750, 1000]
   Total da semana: 7200
   ```

   As três primeiras linhas são os testes, e em todas o devolvido bate com o esperado. Com a lista vazia, o `for` não dá nenhuma volta, e o `total` fica com o 0 do início.

4. Provoca um erro de propósito, para veres os testes a trabalhar. Na função, acrescenta quatro espaços ao início da linha `return total`, para ela ficar com oito, dentro do `for`. Guarda e corre. O que deves ver:

   ```text
   None esperado: 0
   500 esperado: 500
   1200 esperado: 4050
   Pontos das partidas: [1200, 850, 2000, 400, 1750, 1000]
   Total da semana: 1200
   ```

   Não há nenhuma mensagem de erro, e dois testes falham. O `return` termina a função. Dentro do ciclo, termina-a logo na primeira volta, e a função devolve só o primeiro elemento: 1200, em vez de 4050. Com a lista vazia, o ciclo não dá nenhuma volta, e a função nunca chega ao `return`. Devolve `None`, o valor que quer dizer "nenhum valor", o mesmo que o `print` devolve. O teste com uma só partida passou, por acaso, porque com um elemento a primeira volta é a única. É por isso que se testa com os três tipos de lista. Tira os quatro espaços, para o `return total` voltar a ficar com quatro, encostado ao `for`. Guarda e corre outra vez, e confirma que os três testes batem certo.

5. A função está testada. As linhas de teste já não fazem falta no ecrã, mas é bom guardá-las, para as voltares a ligar se um dia mudares a função. Seleciona as três linhas com `print` dos testes e escolhe Toggle Line Comment, no menu Edit, para as desligar com um `#`. A linha do comentário de cima já tem `#`, e fica como está. Guarda e corre. O que deves ver: só as duas linhas da parte principal.

### Paragem 2

A função `total_de_pontos` está testada sozinha, e os testes estão guardados no ficheiro, desligados. O `partidas.py` completo, como deve estar agora:

```python
# partidas.py: o resumo das partidas de uma semana num jogo online.
# Nesta fase, soma os pontos de todas as partidas.


def total_de_pontos(pontuacoes):
    """Devolve a soma dos pontos de uma lista de partidas.

    Recebe a lista com os pontos de cada partida, ints maiores ou iguais
    a zero. Devolve o total, um int. Com a lista vazia, devolve 0.
    """
    total = 0
    for pontos in pontuacoes:
        total = total + pontos
    return total


# Testes das funções sozinhas: o valor devolvido e o que se esperava.
# print(total_de_pontos([]), "esperado: 0")
# print(total_de_pontos([500]), "esperado: 500")
# print(total_de_pontos([1200, 850, 2000]), "esperado: 4050")


pontuacoes = [1200, 850, 2000, 400, 1750, 1000]
print("Pontos das partidas:", pontuacoes)
print("Total da semana:", total_de_pontos(pontuacoes))
```

Pensa antes de continuares: no passo 4, o teste com `[1200, 850, 2000]` apanhou o `return` dentro do ciclo. Que lista com vários elementos não o apanharia? A resposta: uma em que o primeiro elemento já é o total, porque os outros são todos 0, como `[500, 0, 0]`. Com ela, a função devolve 500 na primeira volta, e o esperado também é 500. Uma lista de teste com vários elementos serve melhor quando os elementos são diferentes e nenhum é 0.

## Fase 3: Uma função que chama outra

A segunda parte do resumo é a média por partida: o total dividido pelo número de partidas. O total já tem uma função, testada. O número de partidas dá-o o `len`. A média pode então ser uma função de uma linha, que chama a `total_de_pontos` lá dentro.

Quando uma chamada está dentro de outra, ou dentro de uma conta, o Python faz primeiro a chamada de dentro. Pensa na chamada como um buraco na linha: o Python vai à função buscar o valor e tapa o buraco com ele. Só depois continua a conta. Para saber mais, lê a secção "Uma chamada dentro de outra" do [guia](../06-funcoes.md).

A média tem um cuidado. Com a lista vazia, a conta seria 0 / 0, que não tem resultado. Esta função não aceita a lista vazia, e a documentação di-lo, para quem a chamar saber.

1. Em `partidas.py`, a seguir ao `return total` da primeira função, deixa duas linhas em branco e escreve a segunda função, encostada à margem:

   ```python
   def media_de_pontos(pontuacoes):
       """Devolve a média dos pontos por partida.

       Recebe a lista com os pontos de cada partida, com pelo menos uma
       partida: com a lista vazia, a conta seria 0 / 0, e o programa parava.
       Devolve a média, um float.
       """
       return total_de_pontos(pontuacoes) / len(pontuacoes)
   ```

   Deixa também duas linhas em branco entre esta função e o comentário dos testes.

   Leitura guiada: o corpo é só o `return`, com uma conta. A conta tem duas chamadas: `total_de_pontos(pontuacoes)`, a tua função, e `len(pontuacoes)`, a função predefinida. O parâmetro desta função também se chama `pontuacoes`, e passa a sua lista à função de cima. Os dois parâmetros têm o mesmo nome, mas cada um é uma variável local da sua função. A divisão com `/` dá sempre um `float`.

2. Escolhe os testes. A lista vazia não entra, porque a documentação diz que a função não a aceita. Ficam uma lista com uma partida e listas com várias. Calcula de cabeça o que a função deve devolver com `[500]`, com `[1000, 2000]` e com a lista das seis partidas.

3. Por baixo das três linhas de teste desligadas, acrescenta estas três, ligadas:

   ```python
   print(media_de_pontos([500]), "esperado: 500.0")
   print(media_de_pontos([1000, 2000]), "esperado: 1500.0")
   print(media_de_pontos([1200, 850, 2000, 400, 1750, 1000]), "esperado: 1200.0")
   ```

   Guarda e corre. O que deves ver:

   ```text
   500.0 esperado: 500.0
   1500.0 esperado: 1500.0
   1200.0 esperado: 1200.0
   Pontos das partidas: [1200, 850, 2000, 400, 1750, 1000]
   Total da semana: 7200
   ```

   Os três testes batem certo. Os valores vêm com o `.0` porque a divisão com `/` dá sempre um `float`. Foi por isso que o esperado já se escreveu assim. Na segunda chamada, o Python calculou primeiro `total_de_pontos([1000, 2000])`, que deu 3000, e `len([1000, 2000])`, que deu 2. Só depois fez 3000 / 2.

4. Vê o que acontece quando alguém não cumpre a documentação. Acrescenta, por baixo dos três testes da média, esta linha:

   ```python
   print(media_de_pontos([]), "esperado: erro")
   ```

   Guarda e corre. O que deves ver, depois dos três testes:

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

   Quer dizer "erro de divisão por zero". Este traceback tem duas linhas `File`, porque o erro aconteceu dentro de uma função. Lê-se de baixo para cima. A última linha diz o erro. A linha `File` de baixo, com `in media_de_pontos`, diz onde o Python parou: na linha 24, dentro da função. A linha `File` de cima, com `in <module>`, diz quem chamou a função: a linha 34, uma linha de teste, fora de qualquer função. O erro vê-se na função, mas a causa está na chamada, que lhe deu uma lista que ela não aceita. Apaga esta linha de teste, que era só para veres a mensagem.

5. Desliga os três testes da média, com Toggle Line Comment. Depois, no fim do ficheiro, a seguir à linha do total, acrescenta estas duas linhas:

   ```python
   media_da_semana = media_de_pontos(pontuacoes)
   print("Média por partida:", media_da_semana)
   ```

   Leitura guiada: a primeira linha chama a função e guarda o valor devolvido em `media_da_semana`. A segunda escreve-o. A média vai fazer falta outra vez na fase 5. Um valor que não muda calcula-se uma vez e guarda-se, em vez de se chamar a função outra vez.

   Muda também a segunda linha do comentário do topo para `# Mostra o total e a média dos pontos das partidas.`, porque o programa passou a fazer isso. Guarda e corre. O que deves ver:

   ```text
   Pontos das partidas: [1200, 850, 2000, 400, 1750, 1000]
   Total da semana: 7200
   Média por partida: 1200.0
   ```

### Paragem 3

O programa mostra o total e a média, calculados por duas funções testadas. A segunda usa a primeira. Além da segunda linha do comentário do topo, mudou a parte do ficheiro que vai da função nova ao fim. Essa parte deve estar assim:

```python
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


pontuacoes = [1200, 850, 2000, 400, 1750, 1000]
print("Pontos das partidas:", pontuacoes)
print("Total da semana:", total_de_pontos(pontuacoes))
media_da_semana = media_de_pontos(pontuacoes)
print("Média por partida:", media_da_semana)
```

Pensa antes de continuares: porque é que valeu a pena testar a `total_de_pontos` sozinha antes de escrever a `media_de_pontos`? A resposta: a média usa o total. Se a média desse errado, já sabias que o total estava certo, e só tinhas de procurar o erro na linha da média. Cada função testada é uma peça em que podes confiar quando constróis a seguinte.

## Fase 4: Decidir dentro de uma função, com vários `return`

A terceira parte do resumo é a classificação de cada partida. As regras são estas: uma partida com 2000 pontos ou mais é excelente; de 1000 a 1999, é boa; abaixo de 1000, é fraca. Os números 2000 e 1000 são regras do jogo, que não mudam enquanto o programa corre. Por isso, vão ser constantes, no início do ficheiro.

A função recebe os pontos de uma partida e devolve um texto. Tem um `if`, um `elif` e um `else`, com um `return` em cada caminho. O `return` termina a função. Em cada chamada, executa-se só um dos três, o do primeiro caminho cuja condição é verdadeira. Para saber mais, lê a secção "O `return` entrega o valor e termina a função" do [guia](../06-funcoes.md).

1. Em `partidas.py`, a seguir às duas linhas do comentário do topo, deixa uma linha em branco e escreve as duas constantes:

   ```python
   PONTOS_EXCELENTE = 2000
   PONTOS_BOA = 1000
   ```

   As duas linhas em branco que já lá estavam ficam entre as constantes e a primeira função. As constantes ficam no início do ficheiro para quem o lê ver logo as regras do jogo.

2. A seguir à função `media_de_pontos`, com duas linhas em branco antes e depois, escreve a terceira função:

   ```python
   def classificar_partida(pontos):
       """Classifica uma partida pelos pontos que fez.

       Recebe os pontos da partida, um int. Devolve um texto: "excelente"
       com 2000 pontos ou mais, "boa" de 1000 a 1999 e "fraca" abaixo de 1000.
       """
       if pontos >= PONTOS_EXCELENTE:
           return "excelente"
       elif pontos >= PONTOS_BOA:
           return "boa"
       else:
           return "fraca"
   ```

   Leitura guiada: a função recebe um número, os pontos de uma só partida, e não a lista. A cadeia testa primeiro a fronteira de cima. Se a partida tiver 2000 ou mais, devolve "excelente" e termina ali, sem olhar para o resto. Só chega ao `elif` uma partida com menos de 2000, e só chega ao `else` uma com menos de 1000. A função devolve o texto, e não o escreve: quem escreve é a parte principal.

3. Escolhe os testes. Há duas fronteiras, a do 1000 e a do 2000. Para cada uma, testa-se o valor de baixo, o da fronteira e o de cima: 999, 1000 e 1001, e 1999, 2000 e 2001. Prevê a classificação de cada um. Depois, por baixo dos testes desligados, acrescenta:

   ```python
   print(classificar_partida(999), "esperado: fraca")
   print(classificar_partida(1000), "esperado: boa")
   print(classificar_partida(1001), "esperado: boa")
   print(classificar_partida(1999), "esperado: boa")
   print(classificar_partida(2000), "esperado: excelente")
   print(classificar_partida(2001), "esperado: excelente")
   ```

   Guarda e corre. O que deves ver:

   ```text
   fraca esperado: fraca
   boa esperado: boa
   boa esperado: boa
   boa esperado: boa
   excelente esperado: excelente
   excelente esperado: excelente
   Pontos das partidas: [1200, 850, 2000, 400, 1750, 1000]
   Total da semana: 7200
   Média por partida: 1200.0
   ```

   Os seis testes batem certo. Os dois casos que mais interessam são o 1000 e o 2000, as fronteiras: são eles que apanham um `>` escrito no lugar do `>=`.

4. Provoca o erro mais frequente com funções, o `return` esquecido. Na linha `return "boa"`, apaga a palavra `return` e o espaço, para ficar só `"boa"`, com os oito espaços. Guarda e corre. O que deves ver nos testes:

   ```text
   fraca esperado: fraca
   None esperado: boa
   None esperado: boa
   None esperado: boa
   excelente esperado: excelente
   excelente esperado: excelente
   ```

   Não há mensagem de erro. O Python aceita uma linha só com um texto, que não faz nada. Nos casos de 1000 a 1999, a função entra no `elif` e passa pelo `"boa"` sem o entregar. Depois chega ao fim do corpo sem nenhum `return`. Por isso devolve `None`, "nenhum valor". Quando vires `None` onde esperavas um valor, procura um `return` em falta no caminho desse caso. Apanharam-no os três testes que passam pelo `elif`, de 1000 a 1999. Volta a pôr `return "boa"`, guarda e corre, e confirma os seis testes.

5. Desliga os seis testes da classificação. Depois, no fim do ficheiro, acrescenta um ciclo que escreve cada partida com a sua classificação:

   ```python
   for i in range(0, len(pontuacoes)):
       pontos = pontuacoes[i]
       print("Partida", i + 1, "teve", pontos, "pontos:", classificar_partida(pontos))
   ```

   Muda a segunda linha do comentário do topo para `# Mostra o total e a média dos pontos, e classifica cada partida.` Guarda e corre. O que deves ver:

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
   ```

   Leitura guiada do ciclo: o `for` percorre a lista pelo índice, porque a mensagem precisa do número da partida, `i + 1`. Em cada volta, `pontos` recebe os pontos dessa partida, e a chamada `classificar_partida(pontos)` dá o texto que o `print` escreve no fim da linha. A partida 3, com 2000, e a partida 6, com 1000, estão nas fronteiras, e ficam do lado certo.

### Paragem 4

Cada partida aparece com a sua classificação, dada por uma função testada nas duas fronteiras. Esta fase mudou o ficheiro em vários sítios. O `partidas.py` completo, como deve estar agora:

```python
# partidas.py: o resumo das partidas de uma semana num jogo online.
# Mostra o total e a média dos pontos, e classifica cada partida.

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


pontuacoes = [1200, 850, 2000, 400, 1750, 1000]
print("Pontos das partidas:", pontuacoes)
print("Total da semana:", total_de_pontos(pontuacoes))
media_da_semana = media_de_pontos(pontuacoes)
print("Média por partida:", media_da_semana)
for i in range(0, len(pontuacoes)):
    pontos = pontuacoes[i]
    print("Partida", i + 1, "teve", pontos, "pontos:", classificar_partida(pontos))
```

Pensa antes de continuares: a função podia ter um `print("excelente")` em vez de `return "excelente"`, e o ecrã parecia quase igual. Porque é que se usa o `return`? A resposta: com o `print`, a função só servia para escrever, sempre daquela maneira. Devolvia `None`, e o texto não se podia guardar, comparar nem pôr no meio de outra frase. Com o `return`, a parte principal recebe o texto e decide o que fazer com ele. Aqui, põe-no no fim da linha de cada partida. As funções que calculam devolvem, e quem escreve no ecrã é a parte principal.

## Fase 5: Uma função com dois parâmetros

A última parte do resumo é contar as partidas que ficaram acima da média. Podia ser uma função só para a média, mas é mais útil uma que conte as partidas acima de um limite qualquer. Assim, a mesma função conta as partidas acima da média, acima de 1000 ou acima de 1500. Para isso, recebe dois valores: a lista e o limite.

Com dois parâmetros, a ordem conta. Os argumentos passam para os parâmetros pela ordem em que estão escritos, e não pelo nome. O primeiro argumento vai para o primeiro parâmetro, e o segundo para o segundo. Para saber mais, lê a secção "Chamar uma função: parâmetros e argumentos" do [guia](../06-funcoes.md).

1. A seguir à função `classificar_partida`, com duas linhas em branco antes e depois, escreve a quarta função:

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

   Leitura guiada: o cabeçalho tem dois parâmetros, separados por uma vírgula: primeiro a lista, depois o limite. O corpo é um contador, como os que já fizeste, com a condição `pontos > limite`. A documentação diz o que acontece na fronteira: uma partida igual ao limite não conta, porque "acima" quer dizer "mais do que".

2. Escolhe os testes e calcula de cabeça o esperado de cada um. São quatro: a lista vazia, uma partida igual ao limite, uma partida logo acima e uma lista com várias. Depois, por baixo dos testes desligados, acrescenta:

   ```python
   print(contar_acima([], 1000), "esperado: 0")
   print(contar_acima([1000], 1000), "esperado: 0")
   print(contar_acima([1001], 1000), "esperado: 1")
   print(contar_acima([1200, 850, 2000], 1000), "esperado: 2")
   ```

   Guarda e corre. O que deves ver, antes das linhas do resumo:

   ```text
   0 esperado: 0
   0 esperado: 0
   1 esperado: 1
   2 esperado: 2
   ```

   Os quatro testes batem certo. O segundo confirma a decisão da documentação: com 1000 e o limite 1000, a partida não conta.

3. Desliga os quatro testes. Depois, no fim do ficheiro, encostada à margem, acrescenta esta linha:

   ```python
   print("Partidas acima da média:", contar_acima(pontuacoes, media_da_semana))
   ```

   Muda a segunda linha do comentário do topo para `# Mostra o total, a média, a classificação e as partidas acima da média.` Guarda. Antes de correres, prevê o número que aparece: qual é a média, e que partidas têm mais do que ela? Depois corre. O que deves ver, no fim:

   ```text
   Partidas acima da média: 2
   ```

   Leitura guiada: a chamada tem dois argumentos, pela ordem do cabeçalho. A lista `pontuacoes` vai para o parâmetro `pontuacoes`, e a média guardada na fase 3, `media_da_semana`, vai para o parâmetro `limite`. A chamada passa a ser `contar_acima(pontuacoes, 1200.0)`, que conta as partidas com mais de 1200 pontos: a de 2000 e a de 1750. Devolve 2, e o `print` escreve-o. A partida 1, com 1200, é igual à média e não conta.

4. Provoca um erro de propósito: troca a ordem dos argumentos na linha nova, para ficar `contar_acima(media_da_semana, pontuacoes)`. Guarda e corre. O que deves ver, depois das linhas das partidas:

   ```text
   Traceback (most recent call last):
     File "C:\Users\aluno\Documents\fp-python\partidas.py", line 85, in <module>
       print("Partidas acima da média:", contar_acima(media_da_semana, pontuacoes))
                                         ~~~~~~~~~~~~^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
     File "C:\Users\aluno\Documents\fp-python\partidas.py", line 52, in contar_acima
       for pontos in pontuacoes:
                     ^^^^^^^^^^
   TypeError: 'float' object is not iterable
   ```

   Quer dizer "erro de tipo: um objeto `float` não se pode percorrer". Lê de baixo para cima. O Python parou na linha 52, dentro da `contar_acima`, no `for`. Com a ordem trocada, o parâmetro `pontuacoes` recebeu a média, 1200.0, e o `for` não consegue percorrer um número. A linha `File` de cima diz de onde veio a chamada: a linha 85, na parte principal. É lá que está a causa, na ordem dos argumentos, e não no `for`, que está certo. Volta a pôr a ordem do cabeçalho, `contar_acima(pontuacoes, media_da_semana)`, guarda e corre.

### Paragem 5

O programa faz o resumo completo, com quatro funções testadas sozinhas. Confirma que o ecrã é o de "O que vais construir", com as dez linhas. O ficheiro completo está na paragem 6, que só lhe acrescenta dois comentários.

Pensa antes de continuares: a parte principal tem uma variável `pontos`, no ciclo das partidas. Três das funções também têm uma variável `pontos`. Isto dá algum problema? A resposta: não. As variáveis de cada função são locais, e só existem enquanto essa função se executa. O `pontos` da parte principal e o `pontos` de cada função são caixas diferentes, que só têm o mesmo nome. O mesmo vale para o parâmetro `pontuacoes` e a lista `pontuacoes` da parte principal.

## Fase 6: A arrumação final do ficheiro

O programa está completo e funciona. Falta confirmar que o ficheiro está arrumado pela ordem certa, e perceber porque é que essa ordem não é só uma questão de gosto. Um script com funções arruma-se sempre assim, de cima para baixo: o comentário do topo, as constantes, as funções e a parte principal. Neste laboratório, as linhas de teste, desligadas, ficam entre as funções e a parte principal.

O Python executa o ficheiro de cima para baixo. A linha do `def` é a que cria a função, e antes de o Python passar por ela, a função ainda não existe. Por isso, uma função tem de estar criada antes de a linha que a chama ser executada. Para saber mais, lê a secção "A ordem no ficheiro: constantes, funções e parte principal" do [guia](../06-funcoes.md).

1. Acrescenta dois comentários que mostram as partes do ficheiro. Por cima da linha `PONTOS_EXCELENTE = 2000`, escreve `# As constantes: os pontos que separam as classificações das partidas.` Por cima da linha `pontuacoes = [...]`, escreve `# A parte principal: usa as funções e escreve o resumo da semana.` Guarda e corre. O resultado não muda, porque os comentários não se executam.

2. Provoca um erro de propósito, para veres porque é que a ordem conta. Seleciona as linhas da parte principal, do comentário `# A parte principal` até à última linha do ficheiro. Corta-as com Ctrl+X, ou Cmd+X no macOS. Cola-as com Ctrl+V, ou Cmd+V, logo a seguir à linha `PONTOS_BOA = 1000`, antes das funções, com uma linha em branco antes. Guarda e corre. O que deves ver:

   ```text
   Pontos das partidas: [1200, 850, 2000, 400, 1750, 1000]
   Traceback (most recent call last):
     File "C:\Users\aluno\Documents\fp-python\partidas.py", line 11, in <module>
       print("Total da semana:", total_de_pontos(pontuacoes))
                                 ^^^^^^^^^^^^^^^
   NameError: name 'total_de_pontos' is not defined
   ```

   Quer dizer "erro de nome: o nome `total_de_pontos` não está definido". As duas primeiras linhas da parte principal executaram-se, porque não usam nenhuma função tua: a lista nasceu, e o `print` escreveu-a. Na linha 11, o Python ainda não tinha chegado ao `def` da `total_de_pontos`, e não conhecia esse nome. A função está escrita no ficheiro, mas mais abaixo, e ainda não tinha sido criada. Desfaz a alteração com Ctrl+Z, ou Cmd+Z, até a parte principal voltar ao fim do ficheiro. Guarda e corre, e confirma que o resumo completo volta a aparecer.

3. Confirma a regra das funções que calculam. Percorre as quatro funções e confirma que nenhuma tem um `print` nem um `input`. Todos os `print` do programa estão na parte principal, e as funções só recebem valores e devolvem resultados.

### Paragem 6

O `partidas.py` está completo, arrumado e com as funções testadas. Confere o teu com este:

```python
# partidas.py: o resumo das partidas de uma semana num jogo online.
# Mostra o total, a média, a classificação e as partidas acima da média.

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
media_da_semana = media_de_pontos(pontuacoes)
print("Média por partida:", media_da_semana)
for i in range(0, len(pontuacoes)):
    pontos = pontuacoes[i]
    print("Partida", i + 1, "teve", pontos, "pontos:", classificar_partida(pontos))
print("Partidas acima da média:", contar_acima(pontuacoes, media_da_semana))
```

Pensa antes de continuares: se mudares a lista da parte principal para `[2500, 900]`, o que esperas que o programa escreva? Calcula de cabeça e depois experimenta. A resposta: o total é 3400 e a média é 1700.0. A partida 1 é excelente e a partida 2 é fraca. Acima da média fica uma partida, a de 2500. Quando acabares, volta a pôr a lista das seis partidas.

## Problemas frequentes

### `NameError: name '...' is not defined`, com o nome de uma função

A função foi chamada antes de o Python passar pelo `def` dela, ou o nome está escrito de outra maneira na chamada. Confirma que todas as funções estão antes da parte principal e que o nome na chamada é igual, letra a letra, ao do `def`.

### Aparece `<function ... at 0x...>` no ecrã

Falta pôr os parênteses na chamada. O nome sozinho é a função, e não o valor que ela devolve. Escreve a chamada com os parênteses e os argumentos, como `total_de_pontos(pontuacoes)`.

### Aparece `None` onde devia aparecer um valor

A função chegou ao fim do corpo sem passar por nenhum `return`. Procura, no caminho do caso que falhou, um `return` esquecido, ou um `print` no lugar do `return`. Confirma também que o `return` não ficou dentro do ciclo.

### `TypeError: ... missing 1 required positional argument`

A chamada tem menos argumentos do que a função tem parâmetros. A mensagem diz o nome do parâmetro que ficou sem valor. Confirma no cabeçalho quantos parâmetros a função tem e por que ordem.

### `TypeError: 'float' object is not iterable`

Uma função que percorre uma lista recebeu um número no lugar dela. Quase sempre, os argumentos da chamada estão pela ordem errada. A linha `File` de cima do traceback diz que chamada foi.

### `IndentationError: expected an indented block after function definition`

A linha a seguir ao cabeçalho do `def` ficou encostada à margem. A documentação e o corpo da função têm de estar indentados quatro espaços.

### As linhas de teste continuam a aparecer no ecrã

Falta o `#` no início de alguma linha de teste. Seleciona as linhas com `print` dos testes e escolhe Toggle Line Comment, no menu Edit. Também podes escrever o `#` à mão no início de cada uma.

### O resultado não muda depois de corrigires o código

O ficheiro não foi guardado. Guarda com Ctrl+S, ou Cmd+S no macOS, e corre outra vez.

## Desafios

1. A melhor partida. Escreve a função `melhor_partida(pontuacoes)`, que devolve a posição, o índice, da partida com mais pontos. Se houver várias com o máximo, devolve a primeira. Testa-a sozinha, com uma partida, com várias e com um empate no máximo. Depois, a parte principal escreve uma linha como `Melhor partida: a 3 com 2000 pontos`. Pista: guarda a posição do maior até agora, e compara cada partida com a que está nessa posição.

2. Quantas de cada. Escreve a função `contar_classificacao(pontuacoes, classificacao)`, que conta quantas partidas da lista têm a classificação dada, como `"boa"`. A parte principal escreve quantas partidas excelentes, boas e fracas houve na semana. Pista: uma função pode chamar outra dentro de um ciclo, e já tens uma que classifica uma partida.

3. A média sem a pior partida. Escreve a função `media_sem_a_pior(pontuacoes)`, que devolve a média dos pontos sem contar a partida com menos pontos. Pensa em quantas partidas a lista tem de ter, no mínimo, e escreve-o na documentação. Testa-a sozinha antes de a usares. Pista: as funções que já tens fazem parte da conta, e falta uma que diga quantos pontos teve a pior partida.

## Antes de terminares

- [ ] O `partidas.py` corre e mostra as dez linhas do resumo.
- [ ] As quatro funções têm documentação, com o que recebem e o que devolvem.
- [ ] As linhas de teste das quatro funções estão no ficheiro, desligadas com `#`.
- [ ] Nenhuma função tem um `print`.
- [ ] Sabes dizer, para cada erro que provocaste, que erro era e como o reconheceste.
- [ ] Consegues explicar, por palavras tuas, o que acontece numa chamada: dos argumentos que passam para os parâmetros ao valor devolvido que tapa o buraco.

![Rodapé](../../imagens/rodape.png)
