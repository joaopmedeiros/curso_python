# Capítulo 5: Condicionais e recursividade
Adaptado de: https://github.com/PenseAllen/PensePython2e

O tópico principal deste capítulo é a instrução if, que executa códigos diferentes dependendo do estado do programa. Mas primeiro quero reforçar dois operadores: divisão pelo piso e módulo.

## 5.1 - Divisão pelo piso e módulo

O operador de divisão pelo piso, //, divide dois números e arredonda o resultado para um número inteiro para baixo. Por exemplo, suponha que o tempo de execução de um filme seja de 105 minutos. Você pode querer saber a quanto isso corresponde em horas. A divisão convencional devolve um número de ponto flutuante:


```python
>>> minutes = 105
>>> minutes / 60
1.75
```

Mas não é comum escrever horas com pontos decimais. A divisão pelo piso devolve o número inteiro de horas, ignorando a parte fracionária:


```python
>>> minutes = 105
>>> hours = minutes // 60
>>> hours
1
```

Para obter o resto, você pode subtrair uma hora em minutos:


```python
>>> remainder = minutes - hours * 60
>>> remainder
45
```

Uma alternativa é usar o operador módulo, %, que divide dois números e devolve o resto:


```python
>>> remainder = minutes % 60
>>> remainder
45
```


## 5.2 - Expressões booleanas

Uma expressão booleana é uma expressão que pode ser verdadeira ou falsa. Os exemplos seguintes usam o operador ==, que compara dois operandos e produz True se forem iguais e False se não forem:

```python
>>> 5 == 5
True
>>> 5 == 6
False
```

True e False são valores especiais que pertencem ao tipo bool; não são strings:

```python
>>> type(True)
<class 'bool'>
>>> type(False)
<class 'bool'>
```

O operador == é um dos operadores relacionais; os outros são:

```python
x != y                # x não é igual a y
x > y                 # x é maior que y
x < y                 # x é menor que y
x >= y                # x é maior ou igual a y
x <= y                # x é menor ou igual a y
```

Embora essas operações provavelmente sejam familiares para você, os símbolos do Python são diferentes dos símbolos matemáticos. Um erro comum é usar apenas um sinal de igual (=) em vez de um sinal duplo (==). Lembre-se de que = é um operador de atribuição e == é um operador relacional. Não existe =&lt; ou =&gt;.


## 5.3 - Operadores lógicos

Há três operadores lógicos: and, or e not. A semântica (significado) destes operadores é semelhante ao seu significado em inglês. Por exemplo, x&gt; 0 and x &lt;10 só é verdade se x for maior que 0 e menor que 10.

n%2 == 0 or n%3 == 0 é verdadeiro se uma ou as duas condição(ões) for(em) verdadeira(s), isto é, se o número for divisível por 2 ou 3.

Finalmente, o operador not nega uma expressão booleana, então not (x &gt; y) é verdade se x &gt; y for falso, isto é, se x for menor que ou igual a y.

Falando estritamente, os operandos dos operadores lógicos devem ser expressões booleanas, mas o Python não é muito estrito. Qualquer número que não seja zero é interpretado como True:

```python
>>> 42 and True
True
```


## 5.4 - Execução condicional

Para escrever programas úteis, quase sempre precisamos da capacidade de verificar condições e mudar o comportamento do programa de acordo com elas. Instruções condicionais nos dão esta capacidade. A forma mais simples é a instrução if:

```python
if x > 0:
    print('x is positive')
```

A expressão booleana depois do if é chamada de condição. Se for verdadeira, a instrução endentada é executada. Se não, nada acontece.


## 5.5 - Execução alternativa

Uma segunda forma da instrução if é a “execução alternativa”, na qual há duas possibilidades e a condição determina qual será executada. A sintaxe pode ser algo assim:

```python
if x % 2 == 0:
    print('x is even')
else:
    print('x is odd')
```

Se o resto quando x for dividido por 2 for 0, então sabemos que x é par e o programa exibe uma mensagem adequada. Se a condição for falsa, o segundo conjunto de instruções é executado. Como a condição deve ser verdadeira ou falsa, exatamente uma das alternativas será executada. As alternativas são chamadas de ramos (branches), porque são ramos no fluxo da execução.


## 5.6 - Condicionais encadeadas

Às vezes, há mais de duas possibilidades e precisamos de mais que dois ramos. Esta forma de expressar uma operação de computação é uma condicional encadeada:

```python
if x < y:
    print('x is less than y')
elif x > y:
    print('x is greater than y')
else:
    print('x and y are equal')
```

elif é uma abreviatura de “else if”. Novamente, exatamente um ramo será executado. Não há nenhum limite para o número de instruções elif. Se houver uma cláusula else, ela deve estar no fim, mas não é preciso haver uma.


## 5.7 - Condicionais aninhadas

Uma condicional também pode ser aninhada dentro de outra. Poderíamos ter escrito o exemplo na seção anterior desta forma:

```python
if x == y:
    print('x and y are equal')
else:
    if x < y:
        print('x is less than y')
    else:
        print('x is greater than y')
```

A condicional exterior contém dois ramos. O primeiro ramo contém uma instrução simples. O segundo ramo contém outra instrução if, que tem outros dois ramos próprios. Esses dois ramos são instruções simples, embora pudessem ser instruções condicionais também.

Embora a endentação das instruções evidencie a estrutura das condicionais, condicionais aninhadas são difíceis de ler rapidamente. É uma boa ideia evitá-las quando for possível.

Operadores lógicos muitas vezes oferecem uma forma de simplificar instruções condicionais aninhadas. Por exemplo, podemos reescrever o seguinte código usando uma única condicional:

```python
if 0 < x:
    if x < 10:
        print('x is a positive single-digit number.')
```

A instrução print só é executada se a colocarmos depois de ambas as condicionais, então podemos obter o mesmo efeito com o operador and:

```python
if 0 < x and x < 10:
    print('x is a positive single-digit number.')
```

Para este tipo de condição, o Python oferece uma opção mais concisa:

```python
if 0 < x < 10:
    print('x is a positive single-digit number.')
```