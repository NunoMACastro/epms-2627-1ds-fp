![Cabeçalho](../../imagens/cabecalho.png)

# Ficha de exercícios: Do pseudocódigo ao Python

Ficha do tema Do pseudocódigo ao Python, do módulo Criar aplicações em linguagem de programação Python. Praticas a escolha da ferramenta certa, a escrita no ecrã com `print` e a leitura dos erros. Fazes sozinho, ao teu ritmo: o que não acabares na aula, acabas em casa ou na aula seguinte.

## O que precisas de saber

O [guia do tema](../01-do-pseudocodigo-ao-python.md) e o [laboratório](../laboratorios/01-do-pseudocodigo-ao-python-laboratorio.md).

## Como trabalhar

Os exercícios 1 a 5 são obrigatórios e fazem-se por esta ordem. Cada um precisa das secções do guia que estão entre parênteses:

1. Exercício 1 ("Escrever no ecrã com `print`" e "Comentários: notas para quem lê o código").
2. Exercício 2 (de "Onde se escreve um programa" a "Quando é preciso um IDE, e quando não").
3. Exercício 3 (o exemplo guiado).
4. Exercício 4 ("Os três tipos de erro").
5. Exercício 5 ("Escrever no ecrã com `print`", "Os três tipos de erro" e "Erros frequentes").

O desafio opcional e a secção "Para ires mais longe" são para quem acabar os obrigatórios.

Guarda os teus scripts na pasta `fp-python`, a do laboratório, com os nomes que cada exercício indica. As respostas escritas ficam no caderno. Antes de correres um script, escreve sempre o resultado que esperas. É aí que percebes se a ideia ficou entendida.

## Exercício 1: Prever o ecrã

Este script escreve o ecrã de um nível de um jogo:

```python
# previsao.py: o ecrã de um nível de um jogo.
print("Nível", 1)
print("Pontos: ", 250)
print()
print("Vidas:", 3, "de", 5)
# print("Fim do nível")
print("Bom jogo!")  # A última linha do ecrã.
```

1. Antes de correres, escreve no caderno o ecrã que esperas, linha a linha, com as linhas em branco e com os espaços exatos. Diz quantas linhas tem o ecrã.
2. Cria `previsao.py` com este conteúdo, corre-o e compara o ecrã com o que escreveste. Para cada linha em que te enganaste, explica numa frase porque é que o ecrã é assim.

## Exercício 2: A ferramenta certa

Para cada uma destas tarefas, diz se usas a consola do Python, o terminal, um editor de texto simples ou o IDE. Justifica numa frase. Há tarefas em que mais do que uma ferramenta serve: nesse caso, diz qual escolhes e porquê.

1. Descobrir se um `print()` sem nada lá dentro escreve alguma coisa.
2. Mostrar a um colega, num computador da biblioteca que tem o Python mas não tem o VS Code, que o teu `ola.py` corre.
3. No mesmo computador, mudar uma letra no `ola.py` antes de o mostrar.
4. Começar um jogo novo, com vários ficheiros, que vais corrigir muitas vezes ao longo das próximas semanas.

## Exercício 3: O menu do quiz

O quiz do 10.º ano começa com um menu. O algoritmo, em pseudocódigo, é este:

```text
Escreve: "QUIZ DO 10.º ANO"
Escreve: "Perguntas: ", 10
Escreve: "Pontos por resposta certa: ", 5
Escreve: "1. Jogar"
Escreve: "2. Ver as regras"
Escreve: "3. Sair"
```

O ecrã que o programa tem de escrever, exatamente, é este:

```text
QUIZ DO 10.º ANO

Perguntas: 10
Pontos por resposta certa: 5

  1. Jogar
  2. Ver as regras
  3. Sair
```

Traduz o algoritmo para Python, num script `quiz_menu.py`. A primeira linha é um comentário com o nome do ficheiro e o que ele faz. Corre-o e compara o ecrã com o esperado, linha a linha.

## Exercício 4: Que tipo de erro é?

Para cada script, diz que tipo de erro tem: de sintaxe, de execução ou de lógica. Diz também que linhas aparecem no ecrã antes da mensagem de erro, se aparecer alguma. Responde primeiro no caderno, só a ler o código. Depois corre cada script, para confirmares.

1. Este script devia escrever duas linhas:

   ```python
   # erro_a.py
   print("Ronda", 1))
   print("Ronda", 2)
   ```

2. Este script devia escrever três linhas:

   ```python
   # erro_b.py
   print("Jogador 1 pronto")
   Print("Jogador 2 pronto")
   print("Começar!")
   ```

3. Este script devia escrever `Ronda 1` e, por baixo, `Ronda 2`:

   ```python
   # erro_c.py
   print("Ronda", 2)
   print("Ronda", 1)
   ```

## Exercício 5: Encontrar os erros da corrida

Este script devia escrever o ecrã de partida de uma corrida de karts, num jogo:

```text
CORRIDA DE KARTS
Voltas: 5
Pilotos: 8

Preparar...
Partida!
```

Mas tem três erros, um de cada tipo:

```python
# corrida.py: o ecrã de partida de uma corrida de karts num jogo.
print("CORRIDA DE KARTS")
print("Voltas:", 3)
print("Pilotos:" 8)
print()
print("Preparar...")
print(Partida)
```

Cria `corrida.py` com este conteúdo e corrige-o até escrever o ecrã esperado. Para cada erro, escreve no caderno a rotina da depuração. Escreve o que esperavas e o que obtiveste, o tipo de erro, a tua hipótese, a correção e o resultado de voltares a testar. Corrige um erro de cada vez, e corre o programa depois de cada correção.

## Apoio

- Exercício 1: cada vírgula entre valores dá um espaço, e um espaço dentro das aspas fica lá. Uma linha que começa por `#` não se executa.
- Exercício 2: pergunta-te se a tarefa precisa de um ficheiro, de várias tentativas e de procurar erros, ou só de uma resposta rápida.
- Exercício 3: compara o ecrã esperado com o pseudocódigo, linha a linha, e olha também para o início de cada linha.
- Exercício 4: lembra-te de quando o Python dá por cada tipo de erro: antes de executar, a meio, ou nunca.
- Exercício 5: o Python mostra um erro de cada vez, e os de sintaxe aparecem primeiro. O erro de lógica só se vê comparando o ecrã com o esperado.

## Desafio opcional

Escreve um script `trofeu.py` que desenhe no ecrã este troféu, feito só com sinais do teclado, e por baixo a frase `Parabéns, campeão!`:

```text
  ___
 |   |
 | 1 |
 |___|
   |
  _|_
```

Antes de correres, conta os espaços do início de cada linha.

## Para ires mais longe

### Mais longe 1: Um script do Python 2

Encontraste numa página da internet este script, escrito para o Python 2:

```python
print "TABELA DE PONTOS"
print "Primeiro lugar:", 100
print
print "Boa sorte!"
```

Prevê o que acontece se o correres no Python 3, e qual é a primeira linha de que o Python se queixa. Depois passa-o para o Python 3, num script `pontos.py`, e corre-o. Pista para a terceira linha: no Python 2, um `print` sozinho escrevia uma linha em branco.

## Critérios de conclusão

- O ecrã que previste no exercício 1 está escrito, com as diferenças explicadas.
- As quatro tarefas do exercício 2 têm a ferramenta e a justificação.
- O `quiz_menu.py` escreve o ecrã do exercício 3, igual ao esperado.
- Os três scripts do exercício 4 têm o tipo de erro e as linhas que aparecem.
- O `corrida.py` escreve o ecrã esperado, e a rotina dos três erros está no caderno.

## Autoavaliação

1. Que tipo de erro te custou mais a encontrar, e porquê?
2. Numa frase tua, o que é um IDE e quando é que não precisas dele?
3. Que ferramenta do VS Code usaste mais nesta ficha?

![Rodapé](../../imagens/rodape.png)
