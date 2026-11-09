![Cabeçalho](../imagens/cabecalho.png)

# Listas

Neste guia, os teus programas passam a guardar muitos valores com um só nome, numa lista. Depois percorrem a lista para contar, somar, procurar e saltar valores. O que é novo é a forma de escrever os ciclos, o `break`, o `continue` e o `len`.

Usa os arrays da algoritmia e o `for` do tema 04. Rever: [Criar um array](../01-algoritmos/04-repeticao-e-arrays.md#criar-um-array), [Percorrer um array com `Para cada`](../01-algoritmos/04-repeticao-e-arrays.md#percorrer-um-array-com-para-cada), [Parar e Continuar](../01-algoritmos/04-repeticao-e-arrays.md#parar-e-continuar) e [Contar voltas com `for` e `range`](04-ciclos-while-e-for.md#contar-voltas-com-for-e-range). Para praticar: [laboratório](laboratorios/05-listas-laboratorio.md) e [ficha de exercícios](exercicios/05-listas-exercicios.md).

## Neste guia

1. [Uma lista guarda vários valores com um só nome](#uma-lista-guarda-vários-valores-com-um-só-nome)
2. [O índice é a posição de cada elemento](#o-índice-é-a-posição-de-cada-elemento)
3. [O `len` diz quantos elementos tem a lista](#o-len-diz-quantos-elementos-tem-a-lista)
4. [Percorrer a lista pelo valor, com `for`](#percorrer-a-lista-pelo-valor-com-for)
5. [Percorrer a lista pelo índice, com `range` e `len`](#percorrer-a-lista-pelo-índice-com-range-e-len)
6. [Escolher entre o valor e o índice](#escolher-entre-o-valor-e-o-índice)
7. [Mudar um elemento pelo índice](#mudar-um-elemento-pelo-índice)
8. [Procurar um valor com uma bandeira](#procurar-um-valor-com-uma-bandeira)
9. [Parar a pesquisa com `break`](#parar-a-pesquisa-com-break)
10. [Saltar uma volta com `continue`](#saltar-uma-volta-com-continue)
11. [A lista vazia e os três casos de teste](#a-lista-vazia-e-os-três-casos-de-teste)
12. [Exemplo guiado: os jogos da equipa](#exemplo-guiado-os-jogos-da-equipa)

## Uma lista guarda vários valores com um só nome

Num jogo de plataformas, apanhaste 15 moedas no primeiro nível, 8 no segundo, 22 no terceiro, nenhuma no quarto e 25 no quinto. Com variáveis, precisavas de cinco nomes, e de uma conta com os cinco. Com 50 níveis, de 50 nomes.

Em Python, o array do pseudocódigo chama-se lista. Escreve-se como na algoritmia: os valores entre parênteses retos, separados por vírgulas. Cada valor é um elemento, e a ordem conta.

```python
# moedas_niveis.py: as moedas que apanhaste em cada nível de um jogo de plataformas.
moedas = [15, 8, 22, 0, 25]
print("Moedas por nível:", moedas)
```

O resultado é `Moedas por nível: [15, 8, 22, 0, 25]`. O nome da lista vai no plural, porque guarda vários valores.

Uma lista também pode guardar textos, como `["Floresta", "Deserto", "Gelo"]`. Quando o `print` escreve a lista, mostra cada texto entre aspas simples, para se ver onde começa e acaba.

## O índice é a posição de cada elemento

Para usar só as moedas do terceiro nível, é preciso dizer qual. Cada elemento tem uma posição, o índice, e os índices começam em 0, como nos arrays.

| Índice | 0 | 1 | 2 | 3 | 4 |
| --- | ---: | ---: | ---: | ---: | ---: |
| Elemento | 15 | 8 | 22 | 0 | 25 |

Escreve-se o nome da lista e o índice entre parênteses retos, e o elemento usa-se como qualquer variável. O nível 3, para as pessoas, tem o índice 2.

```python
# moedas_indice.py: usa os elementos da lista das moedas pelo índice.
moedas = [15, 8, 22, 0, 25]
print("Primeiro nível:", moedas[0])
print("Terceiro nível:", moedas[2])
print("Os dois primeiros juntos:", moedas[0] + moedas[1])
```

Aparecem 15, 22 e 23. Numa lista com 5 elementos, os índices vão de 0 a 4, e o 4 é o último índice válido.

O erro típico é pedir um índice que não existe. Em Python, o programa para.

```text
Traceback (most recent call last):
  File "C:\Users\aluno\Documents\fp-python\moedas_fora.py", line 3, in <module>
    print("Sexto nível:", moedas[5])
                          ~~~~~~^^^
IndexError: list index out of range
```

A última linha quer dizer "erro de índice: índice da lista fora dos limites". É um erro de execução: a linha está bem escrita, mas a lista só tem cinco níveis.

## O `len` diz quantos elementos tem a lista

Na algoritmia, o número de elementos vinha numa constante. Se a lista passar a ter 6 níveis e a constante ficar em 5, o sexto fica de fora, e o programa não avisa.

O **`len`**, do inglês *length*, comprimento, é uma função predefinida que recebe uma lista e devolve quantos elementos ela tem. O último índice válido é `len(moedas) - 1`.

```python
# moedas_len.py: quantos níveis tem a lista, e qual é o último.
moedas = [15, 8, 22, 0, 25]
numero_de_niveis = len(moedas)
print("Níveis jogados:", numero_de_niveis)
print("Moedas do último nível:", moedas[numero_de_niveis - 1])
```

Aparecem 5 e 25. Com mais um nível na lista, os dois resultados mudam sozinhos. Numa lista de 5 elementos, o `len` dá 5, mas o último índice é o 4. Por isso, `moedas[len(moedas)]` dá sempre `IndexError`.

## Percorrer a lista pelo valor, com `for`

Para somar as moedas todas, escrever `moedas[0] + moedas[1] + ...` não serve com 50 níveis. Percorre-se a lista com um ciclo. O `Para cada quantidade em moedas` passa a `for quantidade in moedas:`, sem `range`.

Em cada volta, a variável recebe o elemento seguinte, e o ciclo acaba sozinho quando eles se esgotam. O nome da variável diz o que é cada elemento.

```python
# moedas_total.py: soma as moedas de todos os níveis e calcula a média por nível.
moedas = [15, 8, 22, 0, 25]
total = 0
for quantidade in moedas:
    total = total + quantidade
print("Total de moedas:", total)
print("Média por nível:", total / len(moedas))
```

| Volta | `quantidade` | `total` no fim da volta |
| --- | ---: | ---: |
| antes do ciclo | sem valor | 0 |
| 1.ª | 15 | 15 |
| 2.ª | 8 | 23 |
| 3.ª | 22 | 45 |
| 4.ª | 0 | 45 |
| 5.ª | 25 | 70 |

O programa escreve `Total de moedas: 70` e `Média por nível: 14.0`. Neste `for` não há índice nenhum, e por isso não há maneira de sair da lista.

## Percorrer a lista pelo índice, com `range` e `len`

Para escrever "Nível 1 teve 15 moedas", cada volta precisa da posição do elemento. O `Para i = 0, i < n, i++` passa a `for i in range(0, len(moedas)):`. O `range` dá os números de 0 a 4, os índices válidos da lista.

```python
# moedas_por_nivel.py: escreve as moedas de cada nível, com o número do nível.
moedas = [15, 8, 22, 0, 25]
for i in range(0, len(moedas)):
    # O i + 1 faz com que o nível de índice 0 seja, para as pessoas, o nível 1.
    print("Nível", i + 1, "teve", moedas[i], "moedas")
```

Aparecem cinco linhas, de `Nível 1 teve 15 moedas` a `Nível 5 teve 25 moedas`. Em cada volta, `i` recebe um índice, e `moedas[i]` é o elemento nessa posição.

Com `range(0, len(moedas) + 1)`, o programa escreve as cinco linhas e, na sexta volta, para com `IndexError`. É o mesmo erro de escrever `<=` em vez de `<` na algoritmia, e por isso testa-se sempre a última volta.

## Escolher entre o valor e o índice

As duas formas passam por todos os elementos. A pergunta é esta: preciso de saber em que posição está cada elemento?

| | Pelo valor | Pelo índice |
| --- | --- | --- |
| A linha do ciclo | `for quantidade in moedas:` | `for i in range(0, len(moedas)):` |
| A variável recebe | o elemento | a posição |
| Para usar o elemento | `quantidade` | `moedas[i]` |
| Pode sair da lista | não | sim, se o `range` estiver errado |
| Serve para | somar, contar, comparar com um limite, mostrar | dizer a posição, mudar um elemento |

Se precisas da posição, percorre pelo índice. Se não, pelo valor.

<details>
<summary>Para ires mais longe: comparar um elemento com o anterior</summary>

Pelo índice também se compara um elemento com o anterior, `moedas[i - 1]`. O percurso começa no índice 1, com `range(1, len(moedas))`, porque o primeiro não tem anterior. Se começasse no 0, `moedas[-1]` não dava erro. Um índice negativo conta a partir do fim, e o programa comparava o primeiro nível com o último, sem avisar.

</details>

## Mudar um elemento pelo índice

O quarto nível ficou registado com 0 moedas, mas afinal apanhaste 5. Para corrigir, dás um valor novo ao elemento, como a uma variável: `moedas[3] = 5`. O 0 perde-se, e os outros ficam como estavam.

Volta à lista original. Num fim de semana de evento, o jogo dá o dobro das moedas de cada nível. A lista tem de ficar `[30, 16, 44, 0, 50]`. Antes de leres a resposta, prevê o que este programa escreve.

```python
# moedas_evento_tentativa.py: tenta dar o dobro das moedas de cada nível.
moedas = [15, 8, 22, 0, 25]
for quantidade in moedas:
    quantidade = quantidade * 2
print("Com o evento:", moedas)
```

Escreve `Com o evento: [15, 8, 22, 0, 25]`, e a lista não mudou. Em cada volta, a variável recebe o valor do elemento, e a linha do corpo dá um valor novo só à variável. É o que acontecia com o `Para cada`. Para mudar um elemento, é preciso a sua posição.

```python
# moedas_evento.py: num fim de semana de evento, o jogo dá o dobro das moedas de cada nível.
moedas = [15, 8, 22, 0, 25]
for i in range(0, len(moedas)):
    moedas[i] = moedas[i] * 2
print("Com o evento:", moedas)
```

Escreve `Com o evento: [30, 16, 44, 0, 50]`. Em cada volta, a linha do corpo lê o elemento da posição `i`, multiplica-o por 2 e escreve o resultado na mesma posição.

Só mudas elementos que já existem. `moedas[5] = 12`, numa lista de cinco elementos, para o programa com `IndexError`.

## Procurar um valor com uma bandeira

Houve algum nível com mais de 20 moedas? O programa olha para os elementos um a um. Se encontrar um, já sabe que sim, mas só pode responder que não depois de ver a lista toda. A resposta fica numa bandeira, como na algoritmia: uma variável `bool` que começa em `False` e passa a `True` quando acontece o que se procura.

```python
# nivel_rico.py: diz se houve algum nível com mais de 20 moedas.
LIMITE = 20

moedas = [15, 8, 22, 0, 25]
encontrado = False
for quantidade in moedas:
    if quantidade > LIMITE:
        encontrado = True
if encontrado:
    print("Houve pelo menos um nível com mais de", LIMITE, "moedas.")
else:
    print("Nenhum nível passou das", LIMITE, "moedas.")
```

Aparece `Houve pelo menos um nível com mais de 20 moedas.`. Dentro do ciclo, a bandeira só pode passar a `True`. Na 4.ª volta, o 0 não é maior do que 20, e ela continua `True`, porque nada a volta a pôr em `False`. O `if encontrado:` é o mesmo que `if encontrado == True:`.

Com a mensagem de "não encontrado" num `else` dentro do ciclo, a frase `Nenhum nível passou das 20 moedas.` aparece três vezes, apesar de dois níveis terem passado.

## Parar a pesquisa com `break`

Qual foi o primeiro nível com mais de 20 moedas? Depois de encontrar o primeiro, o resto da lista não interessa. O `Parar` do pseudocódigo escreve-se `break`, e termina o ciclo imediatamente.

```python
# primeiro_nivel_rico.py: diz qual foi o primeiro nível com mais de 20 moedas.
LIMITE = 20

moedas = [15, 8, 22, 0, 25]
encontrado = False
for i in range(0, len(moedas)):
    if moedas[i] > LIMITE:
        print("Primeiro nível com mais de", LIMITE, "moedas: nível", i + 1)
        encontrado = True
        break
if not encontrado:
    print("Nenhum nível passou das", LIMITE, "moedas.")
```

| Volta | `i` | `moedas[i]` | `moedas[i] > LIMITE` | O que acontece |
| --- | ---: | ---: | --- | --- |
| 1.ª | 0 | 15 | `False` | nada |
| 2.ª | 1 | 8 | `False` | nada |
| 3.ª | 2 | 22 | `True` | escreve a resposta, a bandeira passa a `True`, `break` |

Aparece `Primeiro nível com mais de 20 moedas: nível 3`. A bandeira continua a fazer falta. O ciclo pode ter acabado pelo `break` ou por não haver mais elementos, e é ela que diz qual das duas aconteceu. O `if not encontrado:` é o mesmo que `if encontrado == False:`. Sem o `break`, o nível 5 também passava no `if`, e apareciam duas linhas.

Se escreveres o `break` com quatro espaços, alinhado com o `if`, em vez de oito, fica fora do `if`. Executa-se logo na primeira volta, e o programa diz que nenhum nível passou das 20 moedas. Por isso, numa pesquisa, testa-se o valor procurado no início, no meio e no fim da lista.

## Saltar uma volta com `continue`

Os níveis que ainda não jogaste estão registados com -1, e não podem entrar na soma. O `Continuar` escreve-se `continue`. Termina só a volta atual: as linhas abaixo dele não se executam, e o ciclo passa ao elemento seguinte.

```python
# moedas_jogadas.py: soma só as moedas dos níveis já jogados.
# Um nível que ainda não foi jogado tem -1 na lista.
NAO_JOGADO = -1

moedas = [15, -1, 22, 0, -1]
total = 0
for quantidade in moedas:
    if quantidade == NAO_JOGADO:
        # O -1 não entra na soma.
        continue
    total = total + quantidade
print("Moedas dos níveis jogados:", total)
```

Aparece `Moedas dos níveis jogados: 37`. O 0 do quarto nível entra na soma, porque é um nível jogado em que não apanhaste moedas. O -1 não é um número de moedas: é um sinal combinado, e por isso tem um nome.

<details>
<summary>Para ires mais longe: o <code>continue</code> num <code>while</code></summary>

Num `while`, se a atualização estiver abaixo do `continue`, também é saltada, e o ciclo pode nunca acabar. Num `for`, este perigo não existe, porque é o próprio `for` que passa ao elemento seguinte.

</details>

## A lista vazia e os três casos de teste

Uma lista pode não ter nenhum elemento: `[]`, a lista vazia, com o `len` igual a 0. É a lista dos níveis de quem ainda não jogou, e um `for` sobre ela não dá nenhuma volta.

Com `moedas = []`, o `moedas_total.py` escreve o total e para na média com `ZeroDivisionError`, porque a conta é 0 a dividir por 0. Antes de dividir pelo número de elementos, confirma que ele não é zero.

```python
# moedas_total.py: soma as moedas de todos os níveis e calcula a média por nível.
moedas = [15, 8, 22, 0, 25]
total = 0
for quantidade in moedas:
    total = total + quantidade
print("Total de moedas:", total)
# Sem este if, com a lista vazia, a conta seria 0 / 0 e o programa parava.
if len(moedas) > 0:
    print("Média por nível:", total / len(moedas))
else:
    print("Sem níveis, não há média.")
```

| Lista | Total de moedas | A segunda linha |
| --- | ---: | --- |
| `[]` | 0 | `Sem níveis, não há média.` |
| `[12]` | 12 | `Média por nível: 12.0` |
| `[15, 8, 22, 0, 25]` | 70 | `Média por nível: 14.0` |

Cada programa com listas testa-se pelo menos com estes três casos. A lista vazia mostra as divisões por zero e os índices que não existem: nela, nem o 0 existe. Uma lista com um só elemento mostra o que corre mal quando a primeira volta é também a última. Uma lista com vários elementos mostra o que precisa de mais de uma volta.

## Exemplo guiado: os jogos da equipa

### O problema

Uma equipa guarda os pontos que fez em cada jogo, e quer saber em quantos jogos fez 10 ou mais pontos. Com `[12, 7, 20, 5]`, a resposta é 2. No [guia 04 da algoritmia](../01-algoritmos/04-repeticao-e-arrays.md#o-contador), este problema resolveu-se com um contador.

### O programa, parte a parte

Começa-se por percorrer a lista e mostrar cada valor, para confirmar o ciclo:

```python
# jogos_bons.py: conta os jogos da equipa com 10 ou mais pontos.
pontuacoes = [12, 7, 20, 5]
for pontuacao in pontuacoes:
    print(pontuacao)
```

Aparecem os quatro valores. O `print` dá lugar ao contador, que só aumenta dentro de um `if`. O programa completo fica assim:

```python
# jogos_bons.py: conta os jogos da equipa com 10 ou mais pontos.
MINIMO = 10

pontuacoes = [12, 7, 20, 5]
jogos_bons = 0
for pontuacao in pontuacoes:
    if pontuacao >= MINIMO:
        jogos_bons = jogos_bons + 1
print("Jogos com", MINIMO, "ou mais pontos:", jogos_bons)
```

Só precisa de olhar para cada valor e decidir se conta, e por isso percorre pelo valor.

### Os casos de teste

| Lista | Porquê este caso | Esperado |
| --- | --- | ---: |
| `[]` | a lista vazia, sem jogos | 0 |
| `[10]` | um só jogo, no valor da fronteira | 1 |
| `[9]` | um só jogo, logo abaixo da fronteira | 0 |
| `[12, 7, 20, 5]` | vários jogos, com os dois lados da fronteira | 2 |

Os quatro casos dão o esperado. O `[10]` confirma que o `>=` está certo: com `>`, o 10 não contava, e os outros casos não davam por isso.

## Erros frequentes

### Usar o valor como se fosse o índice

Com `for quantidade in moedas:` e, no corpo, `moedas[quantidade]`, o programa para logo na primeira volta com `IndexError`. A variável vale 15, e o 15 não é uma posição da lista. Pelo valor, usa-se diretamente a variável. Se precisas da posição, percorre pelo índice.

### Dar à variável do `for` o nome da lista

Com `for moedas in moedas:`, o total sai certo, mas a média para com `TypeError: object of type 'int' has no len()`. Em cada volta, o `for` dá um valor novo à variável `moedas`, e no fim ela guarda o último elemento, um inteiro. A variável leva um nome diferente, no singular, como em `for nota in notas:`.

## Palavras novas deste guia

- `len`: a função predefinida que diz quantos elementos tem uma lista.
- `IndexError`: o erro de execução que aparece quando se usa um índice que não existe.

## O que vem a seguir

No tema seguinte, [Funções](06-funcoes.md), dás um nome às partes que se repetem, como somar uma lista ou procurar um valor, e testas cada uma sozinha.

![Rodapé](../imagens/rodape.png)
