![Cabeçalho](../../imagens/cabecalho.png)

# Ficha de exercícios: Textos e listas que mudam

Praticas os textos, com os índices, as fatias e os métodos, e as listas que crescem e encolhem. Os exercícios 1 a 7 são obrigatórios. Os scripts ficam na pasta `fp-python` e abrem com um comentário a dizer o que fazem. Antes de correres, decide o resultado que esperas. Para rever: o [guia do tema](../07-textos-e-listas-que-mudam.md) e o [laboratório](../laboratorios/07-textos-e-listas-que-mudam-laboratorio.md).

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

Rever: [Uma fatia é um pedaço do texto](../07-textos-e-listas-que-mudam.md#uma-fatia-é-um-pedaço-do-texto), [Os métodos arrumam um texto](../07-textos-e-listas-que-mudam.md#os-métodos-arrumam-um-texto) e [Os textos não mudam, as listas mudam](../07-textos-e-listas-que-mudam.md#os-textos-não-mudam-as-listas-mudam).

## Exercício 2: O despertador

Um despertador mostra as horas num texto com cinco caracteres, como `"07:45"`: dois algarismos das horas, os dois pontos e dois algarismos dos minutos. Escreve o script `despertador.py`, que lê uma hora nesta forma e diz quantos minutos passaram desde a meia-noite. O ecrã fica assim:

```text
Hora do despertador (hh:mm)? 07:45
07:45 são 465 minutos depois da meia-noite.
```

Experimenta-o com `00:00`, `07:45`, `12:00` e `23:59`.

Rever: [Uma fatia é um pedaço do texto](../07-textos-e-listas-que-mudam.md#uma-fatia-é-um-pedaço-do-texto).

<details>
<summary>Pista</summary>

Conta os índices de `"07:45"`, carácter a carácter, antes de escolheres as fatias.

</details>

## Exercício 3: O nome de utilizador

O clube cria um nome de utilizador para cada sócio entrar no computador da sala. O nome junta três partes, por esta ordem:

- as três primeiras letras do primeiro nome;
- as três primeiras letras do último nome;
- o ano de nascimento.

As letras ficam todas em minúsculas, e os acentos ficam como estão. Um nome com menos de três letras entra inteiro. Com um só nome, o primeiro e o último nome são o mesmo. Escreve o script `utilizador.py`, que lê o nome completo e o ano, e mostra o nome de utilizador. O ecrã fica assim:

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

Rever: [Os métodos arrumam um texto](../07-textos-e-listas-que-mudam.md#os-métodos-arrumam-um-texto) e [Uma fatia é um pedaço do texto](../07-textos-e-listas-que-mudam.md#uma-fatia-é-um-pedaço-do-texto).

<details>
<summary>Pista</summary>

Experimenta na consola o método que parte um texto, com os nomes da tabela, para veres a lista que ele dá.

</details>

## Exercício 4: O PIN do cacifo

Os cacifos do clube abrem com um PIN de quatro algarismos. Um PIN só é aceite se tiver exatamente quatro caracteres, todos algarismos. Os quatro também não podem ser iguais, como em `1111`, que é fácil de adivinhar. Escreve o script `pin.py`, que lê um PIN e mostra uma destas três mensagens:

```text
PIN aceite.
O PIN tem de ter 4 algarismos.
O PIN não pode ter os quatro algarismos iguais.
```

Experimenta-o com os PIN `2580`, `1111`, `12a4`, `123`, `0000` e `1121`.

Rever: [O `isdigit` confirma que um texto só tem algarismos](../07-textos-e-listas-que-mudam.md#o-isdigit-confirma-que-um-texto-só-tem-algarismos) e [Um texto é uma sequência de caracteres](../07-textos-e-listas-que-mudam.md#um-texto-é-uma-sequência-de-caracteres).

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

Rever: [O `append` faz uma lista crescer](../07-textos-e-listas-que-mudam.md#o-append-faz-uma-lista-crescer).

<details>
<summary>Pista</summary>

Faz primeiro a versão que funciona com pontuações, e só depois trata o caso sem nenhuma.

</details>

## Exercício 6: A lista de tarefas

A lista de tarefas do teu telemóvel começa assim:

```python
tarefas = ["estudar Python", "arrumar o quarto", "treino"]
```

Escreve o script `tarefas.py`, com esta lista, que faz, por esta ordem, o que cada pedido diz. Cada pedido de a) a d) é uma linha, ou duas. Usa um método diferente das listas em cada um.

a) Chegou uma tarefa urgente, `"entregar a ficha"`, que passa para o primeiro lugar da lista.

b) O treino foi cancelado, e sai da lista.

c) Lembraste-te de `"ligar à avó"`, que fica para o fim.

d) Fizeste a primeira tarefa da lista: sai da lista, e o programa escreve `Feita:` e o nome dela.

e) O programa mostra quantas tarefas faltam e a lista, numerada a partir do 1, uma por linha. A primeira linha diz `Faltam` e o número de tarefas, como, por exemplo, `Faltam 5 tarefas:`. Cada tarefa vem numa linha, como, por exemplo, `1. fazer a mochila`.

Rever: [Os textos não mudam, as listas mudam](../07-textos-e-listas-que-mudam.md#os-textos-não-mudam-as-listas-mudam).

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

Copia o script para o ficheiro `palavra_do_dia.py`, corre-o e corrige-o, mudando o mínimo possível. Para cada erro, diz num comentário no fim do script o que aconteceu e o tipo de erro. Diz também o que achas que o causa, como o confirmaste, a linha que mudaste e o que viste ao correr de novo. Depois, experimenta-o também com `Hoje há JOGO e amanhã há jogo` e com `Não há aulas amanhã`.

Rever: [Os três tipos de erro](../01-do-pseudocodigo-ao-python.md#os-três-tipos-de-erro).

<details>
<summary>Pista</summary>

Depois de corrigires um erro, volta a correr e compara o ecrã com o esperado.

</details>

## Desafios

### Desafio 1: O palíndromo

Uma palavra é um palíndromo quando se lê da mesma maneira nos dois sentidos, como "radar" e "ana". Escreve o script `palindromo.py`, que lê uma palavra e diz se é um palíndromo, sem ligar às maiúsculas. Testa com `Radar`, `ana`, `Tetris`, `abba` e `a`.

Rever: [Um texto é uma sequência de caracteres](../07-textos-e-listas-que-mudam.md#um-texto-é-uma-sequência-de-caracteres).

### Desafio 2: As iniciais

Escreve o script `iniciais.py`, que lê um nome completo e mostra as iniciais, em maiúsculas, como `Iniciais: ASM` para `ana sofia martins`. Testa também com um nome de uma só palavra.

### Desafio 3: A palavra mais comprida

Escreve o script `palavra_comprida.py`, que lê uma frase e diz qual é a palavra mais comprida e quantas letras tem. Se houver duas com o mesmo tamanho, mostra a primeira. Se a frase não tiver palavras, diz-o. Testa com `O clube de videojogos abre amanhã`, com `Ana viu Rui` e com uma frase só de espaços.

<details>
<summary>Pista</summary>

Guarda numa variável a palavra mais comprida vista até agora.

</details>

### Desafio 4: A frase vazia

Corre o teu `palavra_do_dia.py` corrigido e carrega logo em Enter, sem escrever nenhuma frase. O que acontece, e porquê? Muda o script para que, com uma frase vazia, escreva só `Não escreveste nenhuma frase.`, e confirma que os três casos do exercício 7 continuam certos.

## Critérios de conclusão

- Previste e confirmaste na consola as linhas do exercício 1.
- Os scripts `despertador.py`, `utilizador.py`, `pin.py` e `dardos.py` dão o resultado certo em todos os casos do seu exercício.
- O `tarefas.py` usa um método diferente em cada pedido e mostra as tarefas que faltam, numeradas.
- O `palavra_do_dia.py` dá os resultados certos com as três frases, e o comentário do fim explica cada erro.

![Rodapé](../../imagens/rodape.png)
