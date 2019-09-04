## 7.1 - Instrução while
Adaptado de: https://github.com/PenseAllen/PensePython2e

Os computadores muitas vezes são usados para automatizar tarefas repetitivas. A repetição de tarefas idênticas ou semelhantes sem fazer erros é algo que os computadores fazem bem e as pessoas não. Em um programa de computador, a repetição também é chamada de iteração.

Já vimos duas funções, `countdown` e `print_n`, que se repetem usando recursividade. Como a iteração é bem comum, o Python fornece recursos de linguagem para facilitá-la. Um deles é a instrução `while`. Aqui está uma versão de countdown que usa a instrução `while`:

```python
def countdown(n):
    while n > 0:
        print(n)
        n = n - 1
    print('Blastoff!')
```

Você até pode ler a instrução `while` como se fosse uma tradução do inglês. Significa "Enquanto" `n` for maior que 0, mostre o valor de `n` e então decremente `n`. Quando chegar a 0, mostre a palavra Blastoff!

Mais formalmente, aqui está o fluxo de execução para uma instrução while:

1. Determine se a condição é verdadeira ou falsa.

2. Se for falsa, saia da instrução while e continue a execução da próxima instrução.

3. Se a condição for verdadeira, execute o corpo e então volte ao passo 1.

Este tipo de fluxo chama-se loop (laço), porque o terceiro passo faz um loop de volta ao topo.

O corpo do loop deve mudar o valor de uma ou mais variáveis para que, a certa altura, a condição fique falsa e o loop termine. Senão o loop vai se repetir para sempre, o que é chamado de loop infinito. Uma fonte infindável de divertimento para cientistas da computação é a observação das instruções no xampu, Faça espuma, enxague, repita, que são parte de um loop infinito.


## 7.2 - break

As vezes você não sabe que está na hora de terminar um loop até que já esteja na metade do corpo. Neste caso pode usar a instrução break para sair do loop.

Por exemplo, suponha que você quer receber uma entrada do usuário até que este digite done. Você pode escrever:

```python
while True:
    line = input('> ')
    if line == 'done':
        break
    print(line)
print('Done!')
```

A condição do loop é True, que sempre é verdade, então o loop roda até que chegue a instrução de interrupção.

Cada vez que passa pelo loop, o programa apresenta ao usuário um colchete angular. Se o usuário digitar done, a instrução break sai do loop. Senão, o programa ecoa o que quer que o usuário digite e volta ao topo do loop. Aqui está uma amostra de execução:

```python
> not done
not done
> done
Done!
```

Esta forma de escrever loops while é comum porque podemos verificar a condição em qualquer lugar do loop (não somente no topo) e podemos exprimir a condição de parada afirmativamente (pare quando isto acontecer) em vez de negativamente (continue a seguir até que isto aconteça).