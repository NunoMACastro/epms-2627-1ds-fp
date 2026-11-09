![Cabeçalho](../../imagens/cabecalho.png)

# Ficha de exercícios: Do pseudocódigo ao Python

Praticas a escolha da ferramenta certa, a escrita no ecrã com `print` e a leitura dos erros. Os exercícios 1 a 5 são obrigatórios. Os scripts ficam na pasta `fp-python`, com a primeira linha a dizer o nome do ficheiro e o que ele faz. Para rever: o [guia do tema](../01-do-pseudocodigo-ao-python.md) e o [laboratório](../laboratorios/01-do-pseudocodigo-ao-python-laboratorio.md).

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

Sem o correres, prevê o ecrã, linha a linha, com as linhas em branco e com os espaços exatos, e quantas linhas tem. Depois cria `previsao.py` com este conteúdo e confirma. Para cada linha do ecrã em que te enganaste, explica numa frase porque é que o ecrã é assim. Escreve a frase num comentário, no fim da linha do script a que diz respeito.

Rever: [Escrever no ecrã com `print`](../01-do-pseudocodigo-ao-python.md#escrever-no-ecrã-com-print) e [Os comentários são notas para quem lê o código](../01-do-pseudocodigo-ao-python.md#os-comentários-são-notas-para-quem-lê-o-código).

## Exercício 2: A ferramenta certa

Para cada uma destas tarefas, diz se usas a consola do Python, o terminal, um editor de texto simples ou o IDE. Justifica numa frase. Há tarefas em que mais do que uma ferramenta serve: nesse caso, diz qual escolhes e porquê. Escreve as respostas num ficheiro `ferramenta_certa.py`, só com comentários, um por tarefa.

1. Descobrir se um `print()` sem nada lá dentro escreve alguma coisa.
2. Mostrar a um colega, num computador da biblioteca que tem o Python mas não tem o VS Code, que o teu `ola.py` corre.
3. No mesmo computador, mudar uma letra no `ola.py` antes de o mostrar.
4. Começar um jogo novo, com vários ficheiros, que vais corrigir muitas vezes ao longo das próximas semanas.

Rever: [Quando é preciso um IDE, e quando não](../01-do-pseudocodigo-ao-python.md#quando-é-preciso-um-ide-e-quando-não).

<details>
<summary>Pista</summary>

Pergunta-te se a tarefa precisa de um ficheiro, de várias tentativas e de procurar erros, ou só de uma resposta rápida.

</details>

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

Traduz o algoritmo para Python, num script `quiz_menu.py` que escreva este ecrã exatamente.

Rever: [Escrever no ecrã com `print`](../01-do-pseudocodigo-ao-python.md#escrever-no-ecrã-com-print) e [Exemplo guiado: o ecrã das regras do duelo de dados](../01-do-pseudocodigo-ao-python.md#exemplo-guiado-o-ecrã-das-regras-do-duelo-de-dados).

<details>
<summary>Pista</summary>

Compara o ecrã esperado com o pseudocódigo, linha a linha.

</details>

## Exercício 4: Que tipo de erro é?

Para cada script, diz, só a ler o código, que tipo de erro tem: de sintaxe, de execução ou de lógica. Diz também que linhas aparecem no ecrã, antes da mensagem de erro ou sem nenhuma mensagem. Escreve a resposta no comentário da primeira linha de cada script, a seguir ao nome, e corre-o para a confirmares.

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

Rever: [Os três tipos de erro](../01-do-pseudocodigo-ao-python.md#os-três-tipos-de-erro).

## Exercício 5: Encontrar os erros da corrida

Este script devia escrever o ecrã de partida de uma corrida de karts, num jogo:

```text
CORRIDA DE KARTS
Voltas: 5
Pilotos: 8

Preparar...
Partida!
```

Mas tem três erros:

```python
# corrida.py: o ecrã de partida de uma corrida de karts num jogo.
print("CORRIDA DE KARTS")
print("Voltas:", 3)
print("Pilotos:" 8)
print()
print("Preparar...")
print(Partida)
```

Cria `corrida.py` com este conteúdo e corrige-o até escrever o ecrã esperado, um erro de cada vez. Para cada erro, escreve em comentários no fim do script o que esperavas, o que obtiveste e o tipo de erro. Escreve também a tua hipótese, a correção e o resultado de voltares a testar.

Rever: [Os três tipos de erro](../01-do-pseudocodigo-ao-python.md#os-três-tipos-de-erro).

<details>
<summary>Pista</summary>

O Python mostra um erro de cada vez. Depois de o corrigires, corre outra vez.

</details>

## Desafios

### Desafio 1: O troféu

Escreve um script `trofeu.py` que desenhe no ecrã este troféu, feito só com sinais do teclado, e por baixo a frase `Parabéns, campeão!`. Os espaços do início de cada linha também contam.

```text
  ___
 |   |
 | 1 |
 |___|
   |
  _|_
```

### Desafio 2: Um script do Python 2

Encontraste numa página da internet este script, escrito para o Python 2. No Python 2, um `print` sozinho escrevia uma linha em branco. Prevê o que acontece se o correres no Python 3, e qual é a primeira linha de que o Python se queixa. Depois passa-o para o Python 3, num script `pontos.py`.

```python
print "TABELA DE PONTOS"
print "Primeiro lugar:", 100
print
print "Boa sorte!"
```

Rever: [O Python 3 e o código antigo](../01-do-pseudocodigo-ao-python.md#o-python-3-e-o-código-antigo).

## Critérios de conclusão

- O `previsao.py` tem um comentário com a explicação de cada linha do ecrã em que te enganaste.
- O `ferramenta_certa.py` tem, para cada uma das quatro tarefas do exercício 2, a ferramenta e a justificação.
- O `quiz_menu.py` escreve o ecrã do exercício 3, igual ao esperado.
- Os três scripts do exercício 4 têm, no comentário da primeira linha, o tipo de erro e as linhas que aparecem.
- O `corrida.py` escreve o ecrã esperado, e o comentário do fim explica os três erros.

![Rodapé](../../imagens/rodape.png)
