![Cabeçalho](../../imagens/cabecalho.png)

# Ficha de exercícios: Textos e listas que mudam

Ficha do tema Textos e listas que mudam, do módulo Criar aplicações em linguagem de programação Python. Praticas os textos, com os índices, as fatias e os métodos, e as listas que crescem e encolhem. Praticas também a leitura de um script com erros. Fazes sozinho, ao teu ritmo: o que não acabares na aula, acabas em casa ou na aula seguinte.

## O que precisas de saber

O [guia do tema](../07-textos-e-listas-que-mudam.md) e o [laboratório](../laboratorios/07-textos-e-listas-que-mudam-laboratorio.md).

## Como trabalhar

Os exercícios 1 a 7 são obrigatórios e fazem-se por esta ordem, porque cada um usa o que os anteriores treinaram. Cada um precisa das secções do guia que estão entre parênteses:

1. Exercício 1 (do início até "Os textos não mudam, as listas mudam").
2. Exercício 2 ("Fatias de um texto" e "Juntar textos e valores com f-strings").
3. Exercício 3 ("Os métodos dos textos" e "Fatias de um texto").
4. Exercício 4 ("Um texto é uma sequência de caracteres" e "Os métodos dos textos").
5. Exercício 5 ("Listas que crescem e encolhem" e "Funções predefinidas para listas").
6. Exercício 6 ("Listas que crescem e encolhem").
7. Exercício 7 (o guia todo, e a rotina de cinco passos para procurar um erro).

O desafio opcional e a secção "Para ires mais longe" são para quem acabar os obrigatórios.

Guarda os teus scripts na pasta `fp-python`, com os nomes que cada exercício indica. Quando um exercício pede uma resposta escrita, escreve-a no script, num comentário com `#`, no sítio que o exercício indica. Antes de correres um script, decide que resultado esperas, a partir do enunciado: é com ele que vês se o script está certo. Nas mensagens, usa f-strings ou o `print` com vírgulas, como preferires, desde que o ecrã fique como o enunciado mostra.

## Exercício 1: Prever na consola

Abre a consola do Python, com o teu comando, `python`, `py` ou `python3`. Vais escrever as linhas abaixo, por esta ordem. Antes de cada linha marcada com uma letra, prevê o que a consola vai mostrar. Só depois a escreves e confirmas. As linhas sem letra não mostram nada, mas criam ou mudam os valores.

```text
nome = "Ana Sofia"
a) nome[0]
b) nome[-1]
c) nome[4:]
d) nome[:3].upper()
e) nome
f) nome.split()
g) "sofia" in nome
mochila = ["corda", "lanterna"]
mochila.append("mapa")
h) mochila
mochila.insert(1, "bússola")
i) mochila
j) mochila.pop()
k) mochila
mochila.remove("corda")
l) len(mochila)
```

Na consola, não escrevas a letra nem o parêntese: escreve só o que vem a seguir, como `nome[0]`.

Quando uma previsão falhar, procura no guia a razão do que o Python fez.

## Exercício 2: O despertador

Um despertador mostra as horas num texto com cinco caracteres, como `"07:45"`: dois algarismos das horas, os dois pontos e dois algarismos dos minutos. Escreve o script `despertador.py`, que lê uma hora nesta forma e diz quantos minutos passaram desde a meia-noite. O script começa com um comentário que diz o que ele faz. O ecrã fica assim:

```text
Hora do despertador (hh:mm)? 07:45
07:45 são 465 minutos depois da meia-noite.
```

Experimenta-o com `00:00`, `07:45`, `12:00` e `23:59`.

## Exercício 3: O nome de utilizador

O clube cria um nome de utilizador para cada sócio entrar no computador da sala. O nome junta três partes, por esta ordem:

- as três primeiras letras do primeiro nome;
- as três primeiras letras do último nome;
- o ano de nascimento.

As letras ficam todas em minúsculas, e os acentos ficam como estão. Com um só nome, o primeiro e o último nome são o mesmo. Escreve o script `utilizador.py`, que lê o nome completo e o ano, e mostra o nome de utilizador. O ecrã fica assim:

```text
Nome completo? Ana Sofia Martins
Ano de nascimento? 2011
O teu nome de utilizador é anamar2011.
```

Experimenta-o com estes casos:

| Nome completo | Ano |
| --- | --- |
| `Ana Sofia Martins` | `2011` |
| `rui costa` | `2010` |
| `Eva Sá` | `2012` |
| `Tomás` | `2010` |

O script tem de servir para nomes com qualquer número de palavras.

## Exercício 4: O PIN do cacifo

Os cacifos do clube abrem com um PIN de quatro algarismos. Um PIN só é aceite se tiver exatamente quatro caracteres, todos algarismos. Os quatro também não podem ser iguais, como em `1111`, que é fácil de adivinhar. Escreve o script `pin.py`, que lê um PIN e mostra uma destas três mensagens:

```text
PIN aceite.
O PIN tem de ter 4 algarismos.
O PIN não pode ter os quatro algarismos iguais.
```

Experimenta-o com os PIN `2580`, `1111`, `12a4`, `123`, `0000` e `1121`.

## Exercício 5: Os lançamentos de dardos

Num jogo de dardos, cada lançamento vale de 0 a 60 pontos. Escreve o script `dardos.py`, que lê as pontuações dos lançamentos, uma de cada vez, até a pessoa carregar em Enter sem escrever nada. No fim, mostra quantos lançamentos houve, o total de pontos, o melhor lançamento e o pior. Se não houver nenhum lançamento, escreve só `Não houve lançamentos.`. Não precisas de validar as pontuações: quem usa o programa escreve sempre um número de 0 a 60. Com 20 e 5, o ecrã fica assim:

```text
Pontuação do lançamento (Enter para acabar): 20
Pontuação do lançamento (Enter para acabar): 5
Pontuação do lançamento (Enter para acabar): 
Lançamentos: 2
Total: 25
Melhor: 20
Pior: 5
```

Experimenta-o com as pontuações 20, 5, 60 e 0, por esta ordem, e com uma só pontuação, 25. Experimenta-o também sem nenhuma pontuação, carregando logo em Enter.

## Exercício 6: A lista de tarefas

A lista de tarefas do teu telemóvel começa assim:

```python
tarefas = ["estudar Python", "arrumar o quarto", "treino"]
```

Escreve o script `tarefas.py`, que começa com esta linha e faz, por esta ordem, o que cada pedido diz. Cada pedido de a) a d) é uma linha, ou duas. Usa um método diferente das listas em cada um.

a) Chegou uma tarefa urgente, `"entregar a ficha"`, que passa para o primeiro lugar da lista.

b) O treino foi cancelado, e sai da lista.

c) Lembraste-te de `"ligar à avó"`, que fica para o fim.

d) Fizeste a primeira tarefa da lista: sai da lista, e o programa escreve `Feita:` e o nome dela.

e) O programa mostra quantas tarefas faltam e a lista, numerada a partir do 1, uma por linha. A primeira linha diz `Faltam` e o número de tarefas, como `Faltam 5 tarefas:`. Cada tarefa vem numa linha, como `1. fazer a mochila`.

## Exercício 7: Encontrar o erro

O script `palavra_do_dia.py` devia ler uma frase e contar quantas vezes aparece a palavra do dia, sem ligar às maiúsculas. Tem três erros, de propósito.

```python
# palavra_do_dia.py: lê uma frase e conta quantas vezes aparece a palavra do dia,
# sem ligar às maiúsculas. Este script tem três erros, de propósito.
PALAVRA_DO_DIA = "jogo"

frase = input("Escreve uma frase: ").strip()
palavras = frase.split().lower()
vezes = 0
for palavra in palavras:
    if palavra == PALAVRA_DO_DIA:
        vezes = vezes + 1
print(f"A frase tem {len(palavras)} palavras.")
print(f"A palavra {PALAVRA_DO_DIA.upper} aparece {vezes} vezes.")
print(f"Última palavra: {palavras[-1]")
```

Com a frase `O jogo de hoje é um bom jogo`, o script devia mostrar:

```text
A frase tem 8 palavras.
A palavra JOGO aparece 2 vezes.
Última palavra: jogo
```

Copia o script para o ficheiro `palavra_do_dia.py` e corre-o. O Python mostra os erros um de cada vez. Para cada erro que encontrares, segue a rotina. Escreve o que ela pede num comentário no fim do script, com `#`, para os números das linhas não mudarem:

1. O que aconteceu, e que tipo de erro é: de sintaxe, de execução ou de lógica. Se houver uma mensagem, copia a última linha e a linha que ela aponta.
2. Numa frase, o que achas que causa o erro.
3. Como confirmaste essa frase.
4. A linha que mudaste, e como ficou. Muda o mínimo possível.
5. O que aconteceu quando voltaste a correr.

Quando o script mostrar o resultado certo, experimenta-o também com `Hoje há JOGO e amanhã há jogo` e com `Não há aulas amanhã`.

## Apoio

- Exercício 1: na linha `e)`, lembra-te do que um método de um texto faz ao texto. Nas linhas `h)`, `i)` e `k)`, a consola mostra a lista inteira; pensa em como ela fica depois de cada linha que a muda. A linha `j)` mostra um valor: qual?
- Exercício 2: conta os índices de `"07:45"`, carácter a carácter, como na tabela da fase 1 do laboratório, antes de escolheres as fatias. Cada fatia é um texto: pensa no que é preciso antes de fazer contas com ela.
- Exercício 3: há um método que parte o nome numa lista de palavras. Experimenta-o na consola com os nomes da tabela, para veres a lista que ele dá, antes de escolheres o que tiras dela.
- Exercício 4: o guia tem um método que diz se um texto tem só algarismos. Para os quatro iguais, servem o `for` que percorre um texto carácter a carácter e uma bandeira, como as do tema 05.
- Exercício 5: é o ciclo da sentinela, com o texto vazio no papel do -1 do laboratório do tema 04. Faz primeiro a versão que funciona com os dois primeiros casos, e só depois trata o caso sem nenhuma pontuação.
- Exercício 6: para cada pedido, pergunta-te o que sabes: o valor que entra ou sai, ou a posição. A tabela das operações das listas, no fim de "Seguir o estado da lista", no guia, ajuda a escolher o método.
- Exercício 7: o Python só mostra o erro seguinte depois de corrigires o anterior. A linha que a mensagem aponta pode ter a causa ou não. Um dos erros não dá mensagem nenhuma: só o encontras comparando o ecrã com o esperado.

## Desafio opcional

Uma palavra é um palíndromo quando se lê da mesma maneira nos dois sentidos, do princípio para o fim e do fim para o princípio. São exemplos "radar" e "ana". Escreve o script `palindromo.py`, que lê uma palavra e diz se é um palíndromo, sem ligar às maiúsculas. Testa com `Radar`, `ana`, `Tetris`, `abba` e `a`.

Há uma forma de o fazer com os índices negativos. Compara o primeiro carácter com o último, o segundo com o penúltimo, e assim por diante.

## Para ires mais longe

### Mais longe 1: As iniciais

Escreve o script `iniciais.py`, que lê um nome completo e mostra as iniciais, em maiúsculas, como `Iniciais: ASM` para `ana sofia martins`. Testa também com um nome de uma só palavra.

### Mais longe 2: A palavra mais comprida

Escreve o script `palavra_comprida.py`, que lê uma frase e diz qual é a palavra mais comprida e quantas letras tem. Se houver duas com o mesmo tamanho, mostra a primeira. Se a frase não tiver palavras, por exemplo só com espaços, diz-o. Testa com `O clube de videojogos abre amanhã`, com `Ana viu Rui`, onde as três palavras têm o mesmo tamanho, e com uma frase só de espaços.

### Mais longe 3: A frase vazia

Corre o teu `palavra_do_dia.py` corrigido e carrega logo em Enter, sem escrever nenhuma frase. O que acontece, e porquê? Muda o script para que, com uma frase vazia, escreva só `Não escreveste nenhuma frase.`, e confirma que os três casos do exercício 7 continuam certos.

## Critérios de conclusão

- Correste as linhas do exercício 1 na consola, e percebes cada resultado, também os que não previste.
- Os scripts `despertador.py`, `utilizador.py`, `pin.py` e `dardos.py` correm e dão o resultado certo em todos os casos do seu exercício.
- O `tarefas.py` usa um método diferente em cada pedido e mostra as tarefas que faltam, numeradas.
- O `palavra_do_dia.py` dá os resultados certos nos três casos. O comentário do fim tem a rotina de cada um dos três erros, com o tipo de cada um.

## Autoavaliação

1. Que operação dos textos ou das listas ainda te faz hesitar na hora de prever o resultado? Porquê?
2. No exercício 7, qual dos três erros foi o mais difícil de encontrar, e porquê?
3. Já consegues dizer, antes de correr, se um método muda o valor ou devolve um valor novo?

![Rodapé](../../imagens/rodape.png)
