![Cabeçalho](../imagens/cabecalho.png)

# Ficha de exercícios: Listas

Ficha do tema Listas, do módulo Criar aplicações em linguagem de programação Python. Praticas a leitura dos índices e os percursos de listas para contar, somar, mudar, procurar e saltar valores, sempre com os três casos de teste. Fazes sozinho, ao teu ritmo: o que não acabares na aula, acabas em casa ou na aula seguinte.

## O que precisas de saber

O [guia do tema](05-listas.md) e o [laboratório](05-listas-laboratorio.md).

## Como trabalhar

Os exercícios 1 a 7 são obrigatórios e fazem-se por esta ordem, porque cada um usa o que os anteriores treinaram. Cada um precisa das secções do guia que estão entre parênteses:

1. Exercício 1 ("O índice: a posição de cada elemento" e "O `len`: quantos elementos tem a lista").
2. Exercício 2 ("Percorrer a lista pelo valor, com `for`").
3. Exercício 3 ("Percorrer a lista pelo índice, com `range` e `len`").
4. Exercício 4 ("Mudar um elemento pelo índice").
5. Exercício 5 ("Procurar um valor: a pesquisa com bandeira" e "Parar a pesquisa com `break`").
6. Exercício 6 ("Saltar uma volta com `continue`").
7. Exercício 7 (todo o guia, e "Erros frequentes").

O desafio opcional e a secção "Para ires mais longe" são para quem acabar os obrigatórios.

Guarda os teus scripts na pasta `fp-python`, com os nomes que cada exercício indica. As tabelas e as respostas escritas ficam no caderno. Antes de correres um script, escreve sempre o resultado que esperas, tirado do enunciado. Para testar uma lista diferente, muda a linha da lista, guarda e corre outra vez. As linhas de exemplo dos enunciados mostram só a forma do que o script escreve, com outros números. Não são a resposta.

## Exercício 1: Os índices de uma lista

Num jogo de corridas, fizeste quatro tentativas numa pista. O tempo de cada tentativa, em segundos, ficou nesta lista:

```python
tempos = [42, 38, 45, 40]
```

a) Antes de experimentares, escreve no caderno o que esperas de cada linha da tabela. Se esperas um erro, escreve "erro".

| Linha | O que esperas |
| --- | --- |
| `tempos[0]` | |
| `tempos[3]` | |
| `len(tempos)` | |
| `tempos[len(tempos) - 1]` | |
| `tempos[1] + tempos[2]` | |
| `tempos[4]` | |

Depois abre a consola do Python, no terminal, com `python`, ou `py` no Windows, ou `python3` no macOS. Escreve a linha da lista a seguir ao `>>>` e carrega em Enter. Depois escreve cada linha da tabela, uma de cada vez, e confirma. Na linha que der erro, copia a última linha da mensagem e diz que tipo de erro é.

b) Em que tentativa fizeste o melhor tempo, o mais baixo, contando a primeira como tentativa 1? Qual é o índice desse elemento na lista?

c) Prevê como fica a lista depois de `tempos[2] = 39`. Escreve essa linha na consola e, a seguir, escreve só `tempos`, para confirmares.

## Exercício 2: As estrelas dos níveis

Num jogo de plataformas, cada nível dá de 0 a 3 estrelas. As estrelas que a Inês ganhou nos níveis que já jogou estão nesta lista:

```python
estrelas = [3, 2, 3, 0, 1, 3, 2, 3]
```

a) Escreve o script `estrelas_niveis.py`, que mostra três coisas. A primeira é quantos níveis têm 3 estrelas. A segunda é o total de estrelas. A terceira é quantas estrelas faltam para ter 3 em todos os níveis jogados. O script tem de funcionar para uma lista com qualquer número de níveis, por isso não escrevas o 8 em lado nenhum.

b) Antes de correres, calcula à mão o que o script deve mostrar com a lista da Inês. Depois corre e confirma.

c) Muda a lista para `[]`, e depois para `[3]`. Antes de correres cada uma, escreve o que esperas que apareça. Depois confirma.

## Exercício 3: Os dias em que chegaste à meta

O telemóvel do Duarte conta os passos de cada dia. Os passos da última semana, de segunda a domingo, estão nesta lista:

```python
passos = [6200, 8000, 10450, 3900, 7999, 12100, 7500]
```

O Duarte tem uma meta de 8000 passos por dia. Chega à meta num dia em que dá 8000 passos ou mais.

a) Antes de escreveres código, escreve no caderno em que dias o Duarte chegou à meta, contando a segunda-feira como dia 1, e quantos foram.

b) Escreve o script `passos_meta.py`. Para cada dia em que o Duarte chegou à meta, mostra uma linha como, por exemplo, `Dia 4 com 9150 passos`. No fim, mostra quantos dias foram, numa linha como, por exemplo, `Dias com a meta cumprida: 2`. Corre-o e confirma a alínea a).

c) Testa o script com as listas `[]`, `[8000]` e `[7999]`. Antes de correres cada uma, escreve o que esperas.

## Exercício 4: Os saldos da loja

Na loja de um jogo, as skins custam moedas do jogo. Os preços estão nesta lista:

```python
precos = [1500, 800, 1000, 2400, 600]
```

Começaram os saldos: as skins que custam mais de 1000 moedas passam a custar metade. As outras ficam com o preço que tinham. Os preços são sempre números inteiros de moedas.

a) Antes de escreveres código, escreve no caderno como deve ficar a lista depois dos saldos.

b) Escreve o script `saldos.py`, que muda os preços da lista e, no fim, mostra a lista com uma linha como `Preços com os saldos: [...]`. Corre-o e compara a lista que aparece com a tua, número a número.

c) Testa o script com as listas `[]`, `[1000]` e `[1200]`. Antes de correres cada uma, escreve o que esperas.

## Exercício 5: O primeiro jogo que a equipa não ganhou

Uma equipa de um jogo online registou o resultado de cada jogo, pela ordem em que os jogou. Cada resultado é um texto de uma letra: `"V"` para vitória, `"E"` para empate e `"D"` para derrota.

```python
resultados = ["V", "V", "E", "D", "V", "D"]
```

Escreve o script `sem_vitoria.py`, que diz qual foi o primeiro jogo que a equipa não ganhou, numa linha como, por exemplo, `Primeiro jogo sem vitória: jogo 5`. Se a equipa ganhou todos os jogos, mostra `Nenhum jogo sem vitória.`. Com a lista vazia, mostra a mesma frase, porque não há nenhum jogo que a equipa não tenha ganho. O programa para de procurar logo que encontra o primeiro jogo que a equipa não ganhou.

Antes de correres, escreve no caderno o resultado esperado de cada lista, e, para a lista do enunciado, quantas voltas esperas que o ciclo dê. Depois testa as cinco listas:

| Lista | O que esperas |
| --- | --- |
| `["V", "V", "E", "D", "V", "D"]` | |
| `["D"]` | |
| `["V", "V", "E"]` | |
| `["V", "V"]` | |
| `[]` | |

## Exercício 6: A média sem as faltas

As notas dos testes de um aluno estão nesta lista, pela ordem dos testes. Num teste a que o aluno faltou, a nota ficou registada como -1:

```python
notas = [14, -1, 12, 16, -1]
```

Escreve o script `media_testes.py`, que mostra quantos testes o aluno fez e a média das notas desses testes, numa linha como, por exemplo, `Média dos testes feitos: 13.5`. Os testes a que faltou não contam para nada. Usa o `continue` para os saltar.

Antes de correres, escreve no caderno o que esperas de cada lista da tabela. Em nenhum dos casos o programa pode parar com um erro. Quando não há média para mostrar, mostra uma frase que o explique.

| Lista | Testes feitos | O que mostra a segunda linha |
| --- | ---: | --- |
| `[14, -1, 12, 16, -1]` | | |
| `[15]` | | |
| `[-1, -1]` | | |
| `[]` | | |

## Exercício 7: Encontrar o erro

O script `inventario.py` devia dizer se algum item do inventário de um jogo acabou, isto é, se algum tem 0 unidades. Cada elemento da lista é o número de unidades de um item. O script tem dois erros, de propósito. Um deles aparece de duas maneiras, conforme a lista. Com umas listas, o resultado sai errado sem mensagem. Com outra, o programa para com uma mensagem.

```python
# inventario.py: diz se algum item do inventário de um jogo acabou, isto é, tem 0 unidades.
# Este script tem dois erros, de propósito.
unidades = [3, 0, 5, 2]
for i in range(0, len(unidades) - 1):
    acabou = False
    if unidades[i] == 0:
        acabou = True
if acabou:
    print("Há itens que acabaram.")
else:
    print("Nenhum item acabou.")
```

Estes são os resultados que o enunciado pede:

| Lista | Resultado esperado |
| --- | --- |
| `[3, 0, 5, 2]` | Há itens que acabaram. |
| `[3, 5, 0]` | Há itens que acabaram. |
| `[4, 1]` | Nenhum item acabou. |
| `[]` | Nenhum item acabou. |

Copia o script para o ficheiro `inventario.py` e corre-o com as quatro listas. Para cada erro que encontrares, segue a rotina e escreve no caderno:

1. O caso que falhou, o resultado esperado e o resultado obtido. Diz também que tipo de erro se vê nesse caso: de sintaxe, de execução ou de lógica.
2. Numa frase, o que achas que causa o erro.
3. Como confirmaste essa frase, com a tabela de iterações ou com a mensagem.
4. A linha que mudaste, e como ficou. Muda o mínimo possível.
5. O que aconteceu quando voltaste a correr as quatro listas.

## Apoio

- Exercício 1: o último índice válido é o número de elementos menos 1. As pessoas contam as tentativas a partir do 1, e os índices começam no 0.
- Exercício 2: há uma função predefinida que diz quantos elementos tem uma lista. O contador e o acumulador podem estar no mesmo ciclo.
- Exercício 3: cada linha que o script mostra precisa do número do dia. Lê com atenção a frase do enunciado que diz quando o Duarte chega à meta.
- Exercício 4: para mudar um elemento, é preciso saber a posição dele. Compara a lista que aparece com a que calculaste à mão, número a número, também na forma como cada número está escrito.
- Exercício 5: os elementos são textos, e comparam-se com outro texto, entre aspas. Antes de escreveres o `if`, escreve no caderno, por palavras, que resultados fazem o programa parar.
- Exercício 6: um teste a que o aluno faltou não é um teste feito. Antes de dividires, pergunta-te se o número por que divides pode ser zero.
- Exercício 7: em dois dos casos, o Python não dá mensagem nenhuma, e só comparando com o resultado esperado se vê o erro. Faz a tabela de iterações da lista `[3, 0, 5, 2]`, com uma coluna para `i` e outra para `acabou`.

## Desafio opcional

O Duarte quer saber em que dias da semana deu mais passos do que no dia anterior. Escreve o script `melhorias.py`, que usa a lista de passos do exercício 3. Para cada um desses dias, mostra uma linha como, por exemplo, `Dia 4 com 9150 passos, mais do que no dia anterior`. No fim, mostra quantos dias foram. Testa também com `[]`, `[5000]`, `[3000, 3000]` e `[5000, 3000]`, e escreve antes o que esperas de cada uma.

## Para ires mais longe

### Mais longe 1: O último jogo com golos

Os golos que uma equipa marcou em cada jogo estão na lista `golos = [2, 0, 1, 0, 0]`. Escreve o script `ultimo_golo.py`, que diz em que jogo a equipa marcou pela última vez, numa linha como, por exemplo, `Último jogo com golos: jogo 4`. Se a equipa nunca marcou, mostra `A equipa ainda não marcou.`. Testa com `[2, 0, 1, 0, 0]`, `[0, 0, 4]`, `[0, 0]` e `[]`. Explica numa frase se o teu programa usa o `break`, e porquê.

## Critérios de conclusão

- O exercício 1 tem a previsão e a confirmação de cada linha, com o tipo do erro da linha que falhou.
- Os scripts `estrelas_niveis.py`, `passos_meta.py`, `saldos.py`, `sem_vitoria.py` e `media_testes.py` correm e dão os resultados que escreveste antes de correr, em todas as listas de teste.
- Nenhum script para com um erro com a lista vazia.
- O `inventario.py` dá os quatro resultados esperados. Tens no caderno a rotina de cada um dos dois erros, com o tipo de erro que se viu em cada caso que falhou.

## Autoavaliação

1. Em que exercício hesitaste mais entre percorrer a lista pelo valor e pelo índice? O que te fez decidir?
2. Que caso de teste te mostrou um erro que não esperavas: a lista vazia, a lista com um elemento ou a fronteira?
3. No exercício 7, qual dos dois erros foi o mais difícil de encontrar, e porquê?

![Rodapé](../imagens/rodape.png)
