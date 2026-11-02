![Cabeçalho](../imagens/cabecalho.png)

# Ficha de exercícios: Seleção

Ficha do tema Seleção, do módulo Criar aplicações em linguagem de programação Python. Praticas as comparações, as decisões com `if`, `elif` e `else`, o `and` e o `or`, o `match`, e a escolha dos casos de fronteira. Fazes sozinho, ao teu ritmo: o que não acabares na aula, acabas em casa ou na aula seguinte.

## O que precisas de saber

O [guia do tema](03-selecao.md) e o [laboratório](03-selecao-laboratorio.md).

## Como trabalhar

Os exercícios 1 a 6 são obrigatórios e fazem-se por esta ordem, porque cada um usa o que os anteriores treinaram. Cada um precisa das secções do guia que estão entre parênteses:

1. Exercício 1 ("As comparações dão `True` ou `False`" e "Juntar condições com `and`, `or` e `not`").
2. Exercício 2 ("Dois caminhos: `if` e `else`").
3. Exercício 3 ("Mais de dois caminhos: a cadeia com `elif`" e "Validar um valor: dentro e fora de um intervalo").
4. Exercício 4 ("As comparações dão `True` ou `False`" e "Juntar condições com `and`, `or` e `not`").
5. Exercício 5 ("Escolher entre valores certos com `match`").
6. Exercício 6 ("Erros frequentes" e a rotina da depuração, do guia 01).

O desafio opcional e a secção "Para ires mais longe" são para quem acabar os obrigatórios.

Guarda os teus scripts na pasta `fp-python`, com os nomes que cada exercício indica. As tabelas e as respostas escritas ficam no caderno. Antes de correres um script, escreve sempre o resultado que esperas, tirado do enunciado. Depois corres cada caso e escreves o que apareceu ao lado.

## Exercício 1: Prever na consola

Abre a consola do Python, no terminal, com o teu comando. Escreve estas três linhas, que guardam três valores:

```text
>>> vidas = 2
>>> moedas = 150
>>> nome = "Rita"
```

Para cada linha da tabela, escreve no caderno o resultado que esperas, `True` ou `False`, antes de a experimentares. Depois escreve a linha a seguir ao `>>>` e confirma.

| Linha | O que esperas |
| --- | --- |
| `vidas > 0` | |
| `vidas == 3` | |
| `vidas != 3` | |
| `moedas >= 150` | |
| `moedas > 150` | |
| `vidas > 0 and moedas >= 200` | |
| `vidas == 0 or moedas >= 100` | |
| `not (moedas >= 150)` | |
| `nome == "rita"` | |

Para cada linha em que te enganaste, escreve uma frase a explicar o que o Python fez.

## Exercício 2: O tempo de ecrã

O telemóvel deixa marcar um limite diário para uma aplicação. O limite desta é de 120 minutos. Escreve o script `tempo_ecra.py`, que pergunta quantos minutos passaste hoje na aplicação, um número inteiro. Se chegaste ao limite, ou já o passaste, escreve "Chegaste ao limite de hoje. Faz uma pausa.". Se não, escreve quantos minutos ainda podes usar, numa linha como "Minutos que ainda podes usar hoje: 45".

a) Antes de escreveres código, copia a tabela para o caderno e completa o resultado esperado de cada caso. A tabela ainda não tem todos os casos de fronteira. Cada fronteira testa-se com o valor de baixo, o da fronteira e o de cima. Acrescenta, no fim da tabela, os casos que faltam, e escreve o resultado esperado de cada um.

| Minutos | Resultado esperado |
| ---: | --- |
| 0 | |
| 119 | |
| 120 | |
| 150 | |

b) Escreve o script `tempo_ecra.py`. Começa com um comentário que diga o que o script faz, e guarda o limite numa constante.

c) Corre o script com todos os casos da tua tabela e confirma-a.

## Exercício 3: O escalão do jogador

Num jogo online, o escalão de um jogador depende dos pontos de experiência que tem, um número inteiro. Com menos de 1000 pontos, o escalão é Bronze. De 1000 a 2499 pontos, é Prata. Com 2500 pontos ou mais, é Ouro. Um número negativo de pontos é inválido, e o programa escreve "Pontos inválidos" em vez de um escalão.

a) Copia a tabela dos casos de teste para o caderno e completa o resultado esperado de cada um. A tabela ainda não tem todos os casos de fronteira. Cada fronteira testa-se com o valor de baixo, o da fronteira e o de cima. Acrescenta, no fim da tabela, os casos que faltam, e escreve o resultado esperado de cada um.

| Pontos | Resultado esperado |
| ---: | --- |
| -1 | |
| 0 | |
| 999 | |
| 1000 | |
| 2499 | |
| 2500 | |

b) Escreve o script `escalao.py`, que lê os pontos e escreve o escalão. Se te ajudar, escreve primeiro o algoritmo em pseudocódigo, e depois traduz.

c) Corre o script com todos os casos da tua tabela e confirma-a. Para cada caso, diz também por que ramo da cadeia a execução seguiu.

## Exercício 4: O modo difícil

Num jogo, o modo difícil fica desbloqueado quando já acabaste a história, ou quando tens 30 estrelas ou mais. Escreve o script `modo_dificil.py`. Primeiro, pergunta se já acabaste a história, e a pessoa responde `s` ou `n`, em minúsculas. Depois, pergunta quantas estrelas tens, um número inteiro. No fim, escreve "Modo difícil desbloqueado!" ou "O modo difícil ainda está bloqueado.".

a) Copia a tabela para o caderno e completa o resultado esperado de cada caso. A fronteira das estrelas ainda não tem todos os casos. Testa-se com o valor de baixo, o da fronteira e o de cima. Acrescenta, no fim da tabela, o caso que falta, e escreve o resultado esperado.

| Acabaste a história? | Estrelas | Resultado esperado |
| --- | ---: | --- |
| s | 0 | |
| n | 30 | |
| n | 29 | |
| s | 40 | |

b) Escreve o script `modo_dificil.py`.

c) Corre o script com todos os casos da tua tabela e confirma-a.

d) Opcional: corre o script com `S`, em maiúscula, e 10 estrelas. Antes de correres, escreve o que esperas. Depois explica, numa frase, o que aconteceu e porquê.

## Exercício 5: O robô aspirador

Um robô aspirador recebe um comando de uma letra. O `f` manda andar para a frente, e o `t` para trás. O `e` manda virar à esquerda, e o `d` à direita. Escreve o script `robo.py`, que lê o comando e escreve o que o robô vai fazer, como "A andar para a frente.". Para qualquer outra letra, escreve "Comando desconhecido.". Usa o `match`.

a) Escolhe tu os casos de teste. Precisas de casos para cada ramo do `match` se executar pelo menos uma vez, também o do `case _`. Escreve no caderno cada comando que vais testar e a mensagem que esperas.

b) Escreve o script `robo.py`.

c) Corre o script com os teus casos e confirma.

d) Opcional: corre o script com `F`, em maiúscula. Antes de correres, escreve o que esperas, e depois explica o que aconteceu.

Este exercício precisa do Python 3.10 ou mais recente, por causa do `match`. Confirma a tua versão com `python --version`, ou com o teu comando.

## Exercício 6: Encontrar o erro

O script `pocao.py` devia dizer se o jogador pode comprar uma poção na loja de um jogo. A loja só vende a quem está no nível 5 ou acima, e a poção custa 50 moedas. Se o jogador comprar, o script diz com quantas moedas fica. O script tem três erros, de propósito.

```python
# pocao.py: diz se o jogador pode comprar uma poção na loja do jogo e com quantas moedas fica.
# A loja só vende a quem está no nível 5 ou acima.
# Este script tem três erros, de propósito.
PRECO_POCAO = 50
NIVEL_MINIMO = 5

nivel = int(input("Em que nível estás? "))
moedas = input("Quantas moedas tens? ")
if nivel < NIVEL_MINIMO:
    print("A loja só abre no nível 5.")
else if PRECO_POCAO >= moedas:
    print("Compraste a poção. Ficas com", moedas - PRECO_POCAO, "moedas.")
else:
    print("Não tens moedas que cheguem.")
```

Com estes quatro casos, o script certo mostra isto:

| Nível | Moedas | O que deve aparecer |
| ---: | ---: | --- |
| 3 | 100 | A loja só abre no nível 5. |
| 5 | 80 | Compraste a poção. Ficas com 30 moedas. |
| 7 | 50 | Compraste a poção. Ficas com 0 moedas. |
| 6 | 20 | Não tens moedas que cheguem. |

Copia o script para o ficheiro `pocao.py` e corre-o com os quatro casos. O Python mostra os erros um de cada vez. Para cada erro que encontrares, segue a rotina e escreve no caderno:

1. O caso que falhou, o que devia aparecer e o que apareceu, e que tipo de erro é: de sintaxe, de execução ou de lógica. Se houver uma mensagem, copia a última linha e a linha que ela aponta.
2. Numa frase, o que achas que causa o erro.
3. Como confirmaste essa frase.
4. A linha que mudaste, e como ficou. Muda o mínimo possível.
5. O que aconteceu quando voltaste a correr os quatro casos, também os que já passavam.

## Apoio

- Exercício 1: com 150 moedas, pensa em qual dos dois sinais, o `>=` ou o `>`, inclui o próprio 150. No `and`, basta uma parte falsa para o resultado ser `False`; no `or`, basta uma verdadeira para ser `True`.
- Exercício 2: preenche a tabela da alínea a) antes de pensares no código. O 120 é o caso que mais te obriga a pensar.
- Exercício 3: desenha primeiro a reta dos pontos, com as regiões e as fronteiras, como no guia 03 da algoritmia. A ordem das condições na cadeia conta.
- Exercício 4: a resposta à primeira pergunta é um texto, e as estrelas são um número. Pensa em qual das duas leituras precisa de conversão. Depois, lê outra vez a frase do enunciado que diz quando o modo fica desbloqueado.
- Exercício 5: o comando é uma letra, e não um número, como a resposta do `outra_vez.py` do guia.
- Exercício 6: o Python só mostra o erro seguinte depois de corrigires o anterior. A mensagem de um erro aponta para onde o Python deu pelo problema, e a causa pode estar noutra linha. Uma mensagem pode pedir os dois pontos numa linha que já os tem: nesse caso, vale a pena olhar para onde aponta o `^`. Um dos erros não dá mensagem nenhuma: só o encontras se comparares o resultado com a tabela.
- Desafio opcional: "divisível por 4" quer dizer que o resto da divisão por 4 é 0. Vê no guia 02 como se calcula o resto.

## Desafio opcional

O calendário tem um dia 29 de fevereiro nos anos bissextos. Um ano é bissexto quando é divisível por 4 e não é divisível por 100. Há uma exceção: os anos divisíveis por 400 também são bissextos. Por isso, o ano 2000 foi bissexto, e o 1900 não foi.

Escreve o script `bissexto.py`, que lê um ano e diz se é bissexto. Escreve uma linha como "2024 é bissexto: fevereiro tem 29 dias." ou "2023 não é bissexto: fevereiro tem 28 dias.". Antes de escreveres código, faz no caderno a tabela dos casos 2024, 2023, 1900 e 2000, com o resultado esperado de cada um. Depois corre o script com os quatro e confirma.

## Para ires mais longe

### Mais longe 1: Pedra, papel, tesoura

Dois jogadores escrevem, um de cada vez, `pedra`, `papel` ou `tesoura`, em minúsculas. A pedra ganha à tesoura, a tesoura ganha ao papel, e o papel ganha à pedra. Duas jogadas iguais dão empate. Escreve o script `pedra_papel_tesoura.py`, que lê as duas jogadas e escreve "Empate", "Ganha o jogador 1" ou "Ganha o jogador 2".

Antes de escreveres código, faz no caderno uma tabela com as nove combinações possíveis de jogadas e o resultado esperado de cada uma. Depois corre o script com as nove e confirma. Podes supor que os jogadores escrevem sempre uma das três palavras, sem erros.

## Critérios de conclusão

- O exercício 1 tem a previsão e a confirmação de cada linha, e uma frase para cada previsão errada.
- Os scripts `tempo_ecra.py`, `escalao.py`, `modo_dificil.py` e `robo.py` correm e dão os resultados das tabelas. Preencheste-as antes de correr, com os casos de fronteira que faltavam.
- O `pocao.py` dá os resultados certos nos quatro casos. Tens no caderno a rotina de cada um dos três erros, com o tipo de cada um.

## Autoavaliação

1. Que parte da seleção ainda te faz hesitar? Pode ser a escolha do sinal nas fronteiras, a ordem das condições numa cadeia, o `and` e o `or`, ou outra.
2. No exercício 6, qual dos três erros foi o mais difícil de encontrar, e porquê?
3. Antes de correres um script, já consegues dizer que casos de teste vais usar e porquê?

![Rodapé](../imagens/rodape.png)
