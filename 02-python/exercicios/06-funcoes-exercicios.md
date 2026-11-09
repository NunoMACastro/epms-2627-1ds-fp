![Cabeçalho](../../imagens/cabecalho.png)

# Ficha de exercícios: Funções

Praticas a previsão do que uma chamada devolve e a escrita de funções documentadas e testadas sozinhas. Os exercícios 1 a 5 são obrigatórios. Os scripts ficam na pasta `fp-python`, e cada função que escreves leva documentação e linhas de teste, com o esperado calculado antes de correres. Quando os testes baterem certo, desliga-os com `#`. Para rever: o [guia do tema](../06-funcoes.md) e o [laboratório](../laboratorios/06-funcoes-laboratorio.md).

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

Sem correres, prevê o que devolve cada uma destas chamadas e escreve as previsões num comentário no início do script `combate.py`:

- `dano(30, 10)`
- `dano(10, 30)`
- `dano(25, 25)`
- `vida_restante(100, dano(30, 10))`
- `vida_restante(vida_restante(100, 20), 35)`
- `vida_restante(100, dano(20, 35))`

Confirma as tuas previsões nesse script, com as duas funções e um `print` para cada chamada. Em cada chamada em que te enganaste, explica num comentário, junto da linha dela, o que a função fez.

Rever: [Uma função pode chamar outra](../06-funcoes.md#uma-função-pode-chamar-outra) e [O `return` entrega o valor e termina a função](../06-funcoes.md#o-return-entrega-o-valor-e-termina-a-função).

<details>
<summary>Pista</summary>

Numa chamada dentro de outra, calcula primeiro a de dentro e reescreve a linha com o valor dela.

</details>

## Exercício 2: A barra de vida

Num jogo, a vida de uma personagem vai de 0 a 100. A barra de vida pisca a vermelho quando a personagem tem, no máximo, 25 pontos de vida.

No script `vida.py`, escreve a função `vida_critica(vida)`. Recebe a vida e devolve `True` quando a barra deve piscar, e `False` quando não deve. Usa uma constante para o 25. Testa a função sozinha com valores à volta da fronteira, escolhidos por ti.

A parte principal pergunta a vida da personagem e escreve "A barra de vida pisca a vermelho" ou "A barra de vida está normal". Experimenta o programa com dois valores à tua escolha, um de cada lado da fronteira.

Rever: [A documentação diz o que a função recebe e devolve](../06-funcoes.md#a-documentação-diz-o-que-a-função-recebe-e-devolve) e [Testar cada função sozinha](../06-funcoes.md#testar-cada-função-sozinha).

## Exercício 3: O preço do bilhete de cinema

O cinema da tua cidade tem quatro preços, conforme a idade. Até aos 11 anos, o bilhete custa 4 euros. Dos 12 aos 17 anos, custa 6 euros. Dos 18 aos 64 anos, custa 8 euros. A partir dos 65 anos, custa 5 euros.

No script `cinema.py`, escreve a função `preco_do_bilhete(idade)`, que recebe a idade e devolve o preço, em euros. Usa constantes para as idades que separam os preços. Testa-a sozinha com três idades à volta de cada fronteira.

A parte principal pergunta a idade e escreve uma linha como "O bilhete custa 6 euros.". A função não pergunta nada nem escreve nada.

Rever: [O `return` entrega o valor e termina a função](../06-funcoes.md#o-return-entrega-o-valor-e-termina-a-função) e [As funções que calculam devolvem, e a parte principal escreve](../06-funcoes.md#as-funções-que-calculam-devolvem-e-a-parte-principal-escreve).

<details>
<summary>Pista</summary>

Desenha primeiro a reta das idades, com as regiões e as fronteiras.

</details>

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

Com a lista `[35, 50, 80, 12, 64]`, o script devia mostrar `Total de moedas: 241` e `Níveis com estrela: 3`. Copia-o para o ficheiro `moedas_erros.py`, corre-o e corrige-o, mudando o mínimo possível.

Para cada erro, escreve num comentário no fim do script o que aconteceu e o tipo de erro. Escreve também o que achas que o causa, como o confirmaste, a linha que mudaste e o que viste ao correr de novo. No fim, muda a linha da lista e testa também com `[50]` e com a lista vazia.

Rever: [Os três tipos de erro](../01-do-pseudocodigo-ao-python.md#os-três-tipos-de-erro) e [Testar cada função sozinha](../06-funcoes.md#testar-cada-função-sozinha).

<details>
<summary>Pista</summary>

Depois de cada correção, corre outra vez e compara o resultado com o esperado.

</details>

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

Rever: [Parar a pesquisa com `break`](../05-listas.md#parar-a-pesquisa-com-break) e [A documentação diz o que a função recebe e devolve](../06-funcoes.md#a-documentação-diz-o-que-a-função-recebe-e-devolve).

<details>
<summary>Pista</summary>

Faz a tabela de iterações da primeira chamada.

</details>

## Desafios

### Desafio 1: O apuramento do corta-mato

No corta-mato da escola, fica apurado para a final quem fizer o percurso em 300 segundos ou menos. Estes são os tempos, em segundos, dos atletas de uma turma:

```python
tempos = [312, 298, 300, 345, 301, 287]
```

No script `corta_mato.py`, escreve a função `contar_apurados(tempos, limite)`, que devolve quantos atletas ficaram apurados. O limite é um parâmetro, para a mesma função servir noutra prova. Testa-a sozinha com estas chamadas:

- `contar_apurados([], 300)`
- `contar_apurados([301], 300)`
- `contar_apurados([300], 300)`
- `contar_apurados([250, 280, 310], 270)`

A parte principal tem a lista dos tempos e uma constante para o limite de 300 segundos. Escreve uma linha como "Ficaram apurados X dos Y atletas", com os dois números calculados pelo programa.

### Desafio 2: O duelo de dados em Python

Traduz para Python o teu algoritmo do [projeto 1, Duelo de dados](../../01-algoritmos/projetos-guiados/05-projeto-1-duelo-de-dados.md), que está no teu portefólio, no script `duelo.py`. Escreve uma função que recebe os números escolhidos pelos dois jogadores numa ronda e devolve quem ganhou essa ronda. Escreve outra que recebe as rondas ganhas de cada jogador e devolve quem ganhou o duelo. Testa as duas sozinhas antes de escreveres a parte principal.

A parte principal lê os números e escreve as mensagens das rondas e do fim. Para o caso em que ninguém ganha o duelo, usa a decisão que a turma tomou. Confirma, com os casos da tua tabela do projeto, que o programa dá o mesmo que o algoritmo.

## Critérios de conclusão

- O `combate.py` tem um `print` para cada uma das seis chamadas.
- Os scripts `vida.py` e `cinema.py` correm, e as funções deles têm documentação e linhas de teste desligadas com `#`.
- Nenhuma das tuas funções tem um `print` nem um `input`.
- O `moedas_erros.py` dá os resultados certos com as três listas, e o comentário do fim explica cada erro.
- O `misterio.py` tem o pseudocódigo, a função com um nome novo e a documentação, e uma linha de teste para cada chamada.

![Rodapé](../../imagens/rodape.png)
