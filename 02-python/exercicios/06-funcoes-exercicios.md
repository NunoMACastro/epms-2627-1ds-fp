![Cabeçalho](../../imagens/cabecalho.png)

# Ficha de exercícios: Funções

Ficha do tema Funções, do módulo Criar aplicações em linguagem de programação Python. Praticas a previsão do que uma chamada devolve e a escrita de funções documentadas e testadas sozinhas. Praticas também a procura de erros em funções e a leitura de uma função que não escreveste. Fazes sozinho, ao teu ritmo: o que não acabares na aula, acabas em casa ou na aula seguinte.

## O que precisas de saber

O [guia do tema](../06-funcoes.md) e o [laboratório](../laboratorios/06-funcoes-laboratorio.md).

## Como trabalhar

Os exercícios 1 a 5 são obrigatórios e fazem-se por esta ordem, porque cada um usa o que os anteriores treinaram. Cada um precisa das secções do guia que estão entre parênteses:

1. Exercício 1 ("Chamar uma função: parâmetros e argumentos", "O `return` entrega o valor e termina a função" e "Uma chamada dentro de outra").
2. Exercício 2 (até "A documentação de uma função", e "Testar cada função sozinha").
3. Exercício 3 ("As funções que calculam devolvem, e a parte principal escreve").
4. Exercício 4 ("Erros frequentes" e as secções com os erros de cada ideia).
5. Exercício 5 (o guia todo).

O desafio opcional e a secção "Para ires mais longe" são para quem acabar os obrigatórios. O exercício de "Para ires mais longe" precisa também do laboratório até à fase 5.

Guarda os teus scripts na pasta `fp-python`, com os nomes que cada exercício indica. Uma resposta escrita fica num comentário no script, com `#`, no início ou junto da linha a que diz respeito. Cada função que escreves leva documentação, e testa-se sozinha, com linhas de teste, antes de a parte principal a usar. O valor esperado de cada linha de teste tira-se do enunciado, antes de correres, e não do ecrã. Num script com parte principal, os testes que já batem certo ficam no ficheiro, desligados com `#`.

## Exercício 1: Prever o que as chamadas devolvem

Num jogo de combate por turnos, o dano de um ataque é o ataque de quem ataca menos a defesa de quem é atacado. Se a defesa for igual ou maior do que o ataque, o dano é 0. Estas duas funções fazem as contas do combate:

```python
def dano(ataque, defesa):
    """Devolve o dano de um ataque.

    Recebe o ataque de quem ataca e a defesa de quem é atacado, dois ints.
    Devolve o ataque menos a defesa, ou 0 se a defesa for igual ou maior.
    """
    if ataque > defesa:
        return ataque - defesa
    return 0


def vida_restante(vida, dano_sofrido):
    """Devolve a vida que fica depois de um ataque.

    Recebe a vida antes do ataque e o dano sofrido, dois ints.
    Devolve a vida que fica, um int. Se o dano for maior do que a vida,
    o resultado é negativo.
    """
    return vida - dano_sofrido
```

Sem correres, prevê o que devolve cada uma destas chamadas:

- `dano(30, 10)`
- `dano(10, 30)`
- `dano(25, 25)`
- `vida_restante(100, dano(30, 10))`
- `vida_restante(vida_restante(100, 20), 35)`
- `vida_restante(100, dano(20, 35))`

Confirma as tuas previsões no script `combate.py`, com as duas funções, um comentário no topo e um `print` para cada chamada. Em cada chamada em que te enganaste, explica num comentário, junto da linha dela, o que a função fez.

## Exercício 2: A barra de vida

Num jogo, a vida de uma personagem vai de 0 a 100. A barra de vida pisca a vermelho quando a personagem tem, no máximo, 25 pontos de vida.

No script `vida.py`, escreve a função `vida_critica(vida)`, com um comentário no topo e a documentação. A função recebe a vida e devolve `True` quando a barra deve piscar, e `False` quando não deve. Usa uma constante para o 25. Testa a função sozinha com valores à volta da fronteira, escolhidos por ti.

A parte principal pergunta a vida da personagem e escreve "A barra de vida pisca a vermelho" ou "A barra de vida está normal". Experimenta o programa com dois valores à tua escolha, um de cada lado da fronteira.

## Exercício 3: O preço do bilhete de cinema

O cinema da tua cidade tem quatro preços, conforme a idade. Até aos 11 anos, o bilhete custa 4 euros. Dos 12 aos 17 anos, custa 6 euros. Dos 18 aos 64 anos, custa 8 euros. A partir dos 65 anos, custa 5 euros.

No script `cinema.py`, escreve a função `preco_do_bilhete(idade)`, com a documentação. Recebe a idade e devolve o preço, em euros. Testa-a sozinha com estas nove idades, três à volta de cada fronteira: 10, 11, 12, 16, 17, 18, 63, 64 e 65.

A parte principal pergunta a idade e escreve uma linha como "O bilhete custa 6 euros.". A função não pergunta nada nem escreve nada: só recebe a idade e devolve o preço.

## Exercício 4: Encontrar o erro

O script `moedas_erros.py` trabalha com as moedas que um jogador apanhou em cada nível de um jogo de plataformas. Num nível com 50 moedas ou mais, o jogador ganha uma estrela. O script devia mostrar o total de moedas e em quantos níveis se ganhou a estrela. Tem três erros, de propósito.

```python
# moedas_erros.py: as moedas apanhadas em cada nível de um jogo de plataformas.
# Este script tem três erros, de propósito.

MOEDAS_PARA_ESTRELA = 50


def total_de_moedas(moedas_por_nivel):
    """Devolve a soma das moedas de todos os níveis.

    Recebe a lista com as moedas de cada nível, ints. Com a lista vazia,
    devolve 0.
    """
    total = 0
    for moedas in moedas_por_nivel:
        total = total + moedas
    return moedas


def ganhou_estrela(moedas):
    """Diz se as moedas de um nível chegam para ganhar a estrela.

    Recebe as moedas de um nível, um int. Devolve True com 50 moedas
    ou mais, e False com menos.
    """
    return moedas >= MOEDAS_PARA_ESTRELA


def niveis_com_estrela(moedas_por_nivel):
    """Conta os níveis em que se ganhou a estrela.

    Recebe a lista com as moedas de cada nível, ints. Devolve quantos
    níveis deram estrela, um int. Com a lista vazia, devolve 0.
    """
    quantos = 0
    for moedas in moedas_por_nivel:
        if ganhou_estrela(moedas_por_nivel):
            quantos = quantos + 1
return quantos


moedas_por_nivel = [35, 50, 80, 12, 64]
print("Total de moedas:", total_de_moedas(moedas_por_nivel))
print("Níveis com estrela:", niveis_com_estrela(moedas_por_nivel))
```

Com a lista `[35, 50, 80, 12, 64]`, o script devia mostrar `Total de moedas: 241` e `Níveis com estrela: 3`.

Copia o script para o ficheiro `moedas_erros.py` e corre-o. O Python mostra os erros um de cada vez. Para cada erro que encontrares, segue a rotina e escreve-a num comentário no fim do script, com `#`:

1. O que aconteceu, e que tipo de erro é: de sintaxe, de execução ou de lógica. Se houver uma mensagem, copia a última linha e a linha que ela aponta.
2. Numa frase, o que achas que causa o erro.
3. Como confirmaste essa frase.
4. A linha que mudaste, e como ficou. Muda o mínimo possível.
5. O que aconteceu quando voltaste a correr.

Quando o script mostrar o resultado certo, testa-o também com a lista `[50]` e com a lista vazia, mudando a linha da lista.

## Exercício 5: A função mistério

Esta função foi escrita por outra pessoa. Falta-lhe a documentação, e o nome não diz o que ela faz:

```python
def misterio(pontos, limite):
    quantos = 0
    for valor in pontos:
        if valor > limite:
            quantos = quantos + 1
        else:
            break
    return quantos
```

a) Sem a correres, que valor devolve cada uma destas chamadas?

- `misterio([15, 12, 8, 20], 10)`
- `misterio([5, 30], 10)`
- `misterio([], 10)`

b) No início do script `misterio.py`, escreve num comentário a função em pseudocódigo, na forma das aulas.

c) No mesmo script, copia a função com a documentação que lhe falta e com um nome que diga o que ela faz. Junta uma linha de teste para cada chamada da alínea a), com o valor que previste.

## Apoio

- Exercício 1: uma chamada que está dentro de outra calcula-se primeiro, e a linha reescreve-se com o valor dela. Lê o corpo de `dano` linha a linha, e lembra-te do que o `return` faz quando se executa.
- Exercício 2: antes de escreveres a condição, pensa no que quer dizer "no máximo 25", com um exemplo de cada lado. Para os testes, a secção "Testar cada função sozinha" diz quantos valores se escolhem à volta de uma fronteira.
- Exercício 3: uma cadeia de `if`, `elif` e `else`, com um `return` em cada caminho. Pensa primeiro na reta das idades, com as regiões e as fronteiras.
- Exercício 4: o Python só mostra o erro seguinte depois de corrigires o anterior. Num traceback com várias linhas `File`, a de baixo diz onde o Python parou, e as de cima dizem quem chamou quem. Um dos erros não dá mensagem nenhuma: só o encontras se comparares o resultado com o esperado, ou se testares a função sozinha.
- Exercício 5: faz a tabela de iterações da primeira chamada. Repara no que o `break` faz na volta em que a condição é falsa.

## Desafio opcional

Traduz para Python o teu algoritmo do [projeto 1, Duelo de dados](../../01-algoritmos/projetos-guiados/05-projeto-1-duelo-de-dados.md), que está no teu portefólio, no script `duelo.py`. Escreve uma função que recebe os números escolhidos pelos dois jogadores numa ronda e devolve quem ganhou essa ronda. Escreve outra que recebe as rondas ganhas de cada jogador e devolve quem ganhou o duelo. Testa as duas sozinhas antes de escreveres a parte principal. A parte principal lê os números e escreve as mensagens das rondas e do fim. Para o caso em que ninguém ganha, usa a decisão que a turma tomou. Usa os casos da tua tabela de casos esperados do projeto, e confirma que o programa dá o mesmo que o algoritmo.

## Para ires mais longe

### Mais longe: O apuramento do corta-mato

No corta-mato da escola, há uma prova de apuramento. Fica apurado para a final quem fizer o percurso em 300 segundos ou menos. Estes são os tempos, em segundos, dos atletas de uma turma:

```python
tempos = [312, 298, 300, 345, 301, 287]
```

No script `corta_mato.py`, escreve a função `contar_apurados(tempos, limite)`, com a documentação. Recebe a lista dos tempos e o limite, e devolve quantos atletas ficaram apurados. O limite é um parâmetro, e não uma conta fixa, para a mesma função servir noutra prova. Testa-a sozinha com estas chamadas:

- `contar_apurados([], 300)`
- `contar_apurados([301], 300)`
- `contar_apurados([300], 300)`
- `contar_apurados([250, 280, 310], 270)`

A parte principal tem a lista dos tempos e uma constante para o limite de 300 segundos. Escreve uma linha como "Ficaram apurados X dos Y atletas", com os dois números calculados pelo programa. O número de atletas não se escreve à mão: o programa tem de funcionar para uma lista de qualquer tamanho.

Pista: a função é um contador, como o `contar_acima` da fase 5 do laboratório. Aqui, quem ganha é quem faz menos tempo.

## Critérios de conclusão

- O `combate.py` tem um `print` para cada uma das seis chamadas. Junto de cada chamada em que te enganaste, tem um comentário que explica o que a função fez.
- Os scripts `vida.py` e `cinema.py` correm, e as funções deles têm documentação e linhas de teste desligadas com `#`.
- As linhas de teste dos exercícios 2 e 3 testam as fronteiras, e o esperado de cada uma vem do enunciado.
- Nenhuma das tuas funções tem um `print` nem um `input`.
- O `moedas_erros.py` dá os resultados certos nos três casos. O comentário do fim tem a rotina de cada um dos três erros, com o tipo de cada um.
- O `misterio.py` tem a função em pseudocódigo, num comentário, e a função com um nome novo e a documentação. Tem também uma linha de teste para cada uma das três chamadas.

## Autoavaliação

1. O que te custou mais: prever as chamadas, escrever a documentação ou escolher os casos de teste?
2. No exercício 4, qual dos três erros foi o mais difícil de encontrar, e porquê?
3. Quando vês um traceback com várias linhas `File`, já consegues dizer onde o programa parou e quem chamou a função?

![Rodapé](../../imagens/rodape.png)
