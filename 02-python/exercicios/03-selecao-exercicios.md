![Cabeçalho](../../imagens/cabecalho.png)

# Ficha de exercícios: Seleção

Ficha do tema Seleção, do módulo Criar aplicações em linguagem de programação Python. Praticas as comparações, as decisões com `if`, `elif` e `else`, o `and` e o `or`, o `match`, e a escolha dos casos de fronteira. Fazes sozinho, ao teu ritmo: o que não acabares na aula, acabas em casa ou na aula seguinte.

## O que precisas de saber

O [guia do tema](../03-selecao.md) e o [laboratório](../laboratorios/03-selecao-laboratorio.md).

## Como trabalhar

Os exercícios 1 a 6 são obrigatórios e fazem-se por esta ordem, porque cada um usa o que os anteriores treinaram. Cada um precisa das secções do guia que estão entre parênteses:

1. Exercício 1 ("As comparações dão `True` ou `False`" e "Juntar condições com `and`, `or` e `not`").
2. Exercício 2 ("Dois caminhos: `if` e `else`").
3. Exercício 3 ("Mais de dois caminhos: a cadeia com `elif`" e "Validar um valor: dentro e fora de um intervalo").
4. Exercício 4 ("As comparações dão `True` ou `False`" e "Juntar condições com `and`, `or` e `not`").
5. Exercício 5 ("Escolher entre valores certos com `match`").
6. Exercício 6 ("Erros frequentes" e a rotina da depuração, do guia 01).

O desafio opcional e a secção "Para ires mais longe" são para quem acabar os obrigatórios.

Guarda os teus scripts na pasta `fp-python`, com os nomes que cada exercício indica. Quando um exercício pede uma resposta escrita, como os casos de teste que acrescentaste, escreve-a num comentário no script, com `#`. Antes de correres cada caso, pensa no resultado que esperas, tirado do enunciado, e compara-o com o que aparece.

## Exercício 1: Prever na consola

Abre a consola do Python, no terminal, com o teu comando. Escreve estas três linhas, que guardam três valores:

```text
>>> vidas = 2
>>> moedas = 150
>>> nome = "Rita"
```

Para cada linha da tabela, prevê o resultado, `True` ou `False`. Depois escreve a linha a seguir ao `>>>` e confirma.

| Linha |
| --- |
| `vidas > 0` |
| `vidas == 3` |
| `vidas != 3` |
| `moedas >= 150` |
| `moedas > 150` |
| `vidas > 0 and moedas >= 200` |
| `vidas == 0 or moedas >= 100` |
| `not (moedas >= 150)` |
| `nome == "rita"` |

Em cada linha em que te enganaste, descobre o que o Python fez e porquê.

## Exercício 2: O tempo de ecrã

O telemóvel deixa marcar um limite diário para uma aplicação. O limite desta é de 120 minutos. Escreve o script `tempo_ecra.py`, que pergunta quantos minutos passaste hoje na aplicação, um número inteiro. Se chegaste ao limite, ou já o passaste, escreve "Chegaste ao limite de hoje. Faz uma pausa.". Se não, escreve quantos minutos ainda podes usar, numa linha como "Minutos que ainda podes usar hoje: 45". O script começa com um comentário que diz o que faz, e guarda o limite numa constante.

Experimenta-o com 0, 119, 120 e 150 minutos. Estes casos ainda não chegam para a fronteira, que se testa com o valor de baixo, o da fronteira e o de cima. Acrescenta os que faltam, experimenta-os também e escreve-os num comentário no início do script.

## Exercício 3: O escalão do jogador

Num jogo online, o escalão de um jogador depende dos pontos de experiência que tem, um número inteiro. Com menos de 1000 pontos, o escalão é Bronze. De 1000 a 2499 pontos, é Prata. Com 2500 pontos ou mais, é Ouro. Um número negativo de pontos é inválido, e o programa escreve "Pontos inválidos" em vez de um escalão. Escreve o script `escalao.py`, que lê os pontos e escreve o escalão.

Experimenta-o com -1, 0, 999, 1000, 2499 e 2500 pontos. Estes casos ainda não chegam para as fronteiras: cada fronteira testa-se com o valor de baixo, o da fronteira e o de cima. Acrescenta os que faltam e experimenta-os também. Junto de cada ramo da cadeia, escreve num comentário que casos de teste passam por ele.

## Exercício 4: O modo difícil

Num jogo, o modo difícil fica desbloqueado quando já acabaste a história, ou quando tens 30 estrelas ou mais. Escreve o script `modo_dificil.py`. Primeiro, pergunta se já acabaste a história, e a pessoa responde `s` ou `n`, em minúsculas. Depois, pergunta quantas estrelas tens, um número inteiro. No fim, escreve "Modo difícil desbloqueado!" ou "O modo difícil ainda está bloqueado.".

Experimenta-o com estes casos:

| Acabaste a história? | Estrelas |
| --- | ---: |
| s | 0 |
| n | 30 |
| n | 29 |
| s | 40 |

A fronteira das estrelas ainda não tem todos os casos: testa-se com o valor de baixo, o da fronteira e o de cima. Acrescenta o caso que falta, experimenta-o também e escreve-o num comentário no início do script.

Opcional: experimenta o script com `S`, em maiúscula, e 10 estrelas. Num comentário, explica numa frase o que aconteceu e porquê.

## Exercício 5: O robô aspirador

Um robô aspirador recebe um comando de uma letra. O `f` manda andar para a frente, e o `t` para trás. O `e` manda virar à esquerda, e o `d` à direita. Escreve o script `robo.py`, que lê o comando e escreve o que o robô vai fazer, como "A andar para a frente.". Para qualquer outra letra, escreve "Comando desconhecido.". Usa o `match`.

Os casos de teste escolhes tu: cada ramo do `match` tem de se executar pelo menos uma vez, também o do `case _`. Experimenta o script com eles e escreve-os num comentário no início do script.

Opcional: experimenta o script com `F`, em maiúscula. Num comentário, explica o que aconteceu.

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

Copia o script para o ficheiro `pocao.py` e corre-o com os quatro casos. O Python mostra os erros um de cada vez. Para cada erro que encontrares, segue a rotina e escreve, num comentário no fim do script:

1. O caso que falhou, o que devia aparecer e o que apareceu, e que tipo de erro é: de sintaxe, de execução ou de lógica. Se houver uma mensagem, copia a última linha e a linha que ela aponta.
2. Numa frase, o que achas que causa o erro.
3. Como confirmaste essa frase.
4. A linha que mudaste, e como estava antes. Muda o mínimo possível.
5. O que aconteceu quando voltaste a correr os quatro casos, também os que já passavam.

## Apoio

- Exercício 1: com 150 moedas, pensa em qual dos dois sinais, o `>=` ou o `>`, inclui o próprio 150. No `and`, basta uma parte falsa para o resultado ser `False`; no `or`, basta uma verdadeira para ser `True`.
- Exercício 2: antes do código, decide o que deve aparecer em cada caso de teste. O 120 é o caso que mais te obriga a pensar.
- Exercício 3: desenha primeiro a reta dos pontos, com as regiões e as fronteiras, como no guia 03 da algoritmia. Se te ajudar, escreve também o algoritmo em pseudocódigo, e depois traduz. A ordem das condições na cadeia conta.
- Exercício 4: a resposta à primeira pergunta é um texto, e as estrelas são um número. Pensa em qual das duas leituras precisa de conversão. Depois, lê outra vez a frase do enunciado que diz quando o modo fica desbloqueado.
- Exercício 5: o comando é uma letra, e não um número, como a resposta do `outra_vez.py` do guia.
- Exercício 6: o Python só mostra o erro seguinte depois de corrigires o anterior. A mensagem de um erro aponta para onde o Python deu pelo problema, e a causa pode estar noutra linha. Uma mensagem pode pedir os dois pontos numa linha que já os tem: nesse caso, vale a pena olhar para onde aponta o `^`. Um dos erros não dá mensagem nenhuma: só o encontras se comparares o resultado com a tabela.
- Desafio opcional: "divisível por 4" quer dizer que o resto da divisão por 4 é 0. Vê no guia 02 como se calcula o resto.

## Desafio opcional

O calendário tem um dia 29 de fevereiro nos anos bissextos. Um ano é bissexto quando é divisível por 4 e não é divisível por 100. Há uma exceção: os anos divisíveis por 400 também são bissextos. Por isso, o ano 2000 foi bissexto, e o 1900 não foi.

Escreve o script `bissexto.py`, que lê um ano e diz se é bissexto. Escreve uma linha como "2024 é bissexto: fevereiro tem 29 dias." ou "2023 não é bissexto: fevereiro tem 28 dias.". Experimenta-o com os anos 2024, 2023, 1900 e 2000.

## Para ires mais longe

### Mais longe 1: Pedra, papel, tesoura

Dois jogadores escrevem, um de cada vez, `pedra`, `papel` ou `tesoura`, em minúsculas. A pedra ganha à tesoura, a tesoura ganha ao papel, e o papel ganha à pedra. Duas jogadas iguais dão empate. Escreve o script `pedra_papel_tesoura.py`, que lê as duas jogadas e escreve "Empate", "Ganha o jogador 1" ou "Ganha o jogador 2".

Experimenta-o com as nove combinações possíveis de jogadas. Podes supor que os jogadores escrevem sempre uma das três palavras, sem erros.

## Critérios de conclusão

- No exercício 1, experimentaste as nove linhas na consola e sabes explicar o resultado de cada uma, também das que previste mal.
- Os scripts `tempo_ecra.py`, `escalao.py`, `modo_dificil.py` e `robo.py` correm e dão o resultado certo em todos os casos de teste. Os casos que acrescentaste ou escolheste estão num comentário em cada script.
- O `pocao.py` dá os resultados certos nos quatro casos. O comentário do fim tem a rotina de cada erro, com o tipo.

## Autoavaliação

1. Que parte da seleção ainda te faz hesitar? Pode ser a escolha do sinal nas fronteiras, a ordem das condições numa cadeia, o `and` e o `or`, ou outra.
2. No exercício 6, qual dos três erros foi o mais difícil de encontrar, e porquê?
3. Antes de correres um script, já consegues dizer que casos de teste vais usar e porquê?

![Rodapé](../../imagens/rodape.png)
