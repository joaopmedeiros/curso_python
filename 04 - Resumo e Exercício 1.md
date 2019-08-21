# 4 Python: Conceitos Básicos (resumo)
Adaptado de Prof. Felipe Meneguzzi e Henry Cagnini / Prof. Douglas Souza


## Variáveis, tipos de dados

Python manipula objetos
Cada objeto possui um tipo

Tipos definem que operações podem ser realizadas em cada objeto

Tipos podem ser escalares o ou não-escalares

Objetos escalares são indivisíveis

Objetos não-escalares possuem estrutura interna (e.g. strings)

Python possui quatro tipos de objetos escalares:
* **int** representam inteiros
* **float** representam números reais em ponto flutuante
* **bool** representam valores lógicos booleanos True e False
* **NoneType** é um tipo com valor único, denotando None representando a ausência de quaisquer outros valores

Variáveis associam nomes a objetos

**O operador = associa o valor de uma expressão a uma variável**

Expressões sempre resultam em um objeto de algum tipo
* inteiro = 10
* decimal = 1.3
* booleano = True
* nulo = None

## Conversões de tipos

Tipos básicos de python possuem uma variedade de operações de conversão de tipo:

* int(p) converterá p para inteiro
    * Possível converter strings str e números em ponto flutuante float
* float(p) converterá p para ponto flutuante
    * Possível converter strings str e números inteiros int
* str(p) converterá p para uma representação em string
    * Possível converter int, float, list, tuple, dict
* list(p) converterá p para uma lista
    * Possível converter str, tuple, dict
* tuple(p) converterá p para uma tupla
    * Possível converter str, list

```python
inteiro = int('10') + 1
string = str(10)
print(inteiro, string)
>>> 11 10
```

## Operadores matemáticos e comparativos
Escalares em Python possuem um conjunto básico de operadores.

Os tipos int e float possuem os seguintes operadores matemáticos:
* i+j representa a adição de i e j
* i-j representa a subtração de i e j
* i*j representa a multiplicação de i e j,
* i**j representa i elevado a potência j, para estas quatro operações:
    * se ambos i e j forem do tipo int o resultado será do tipo int;
    * se qualquer um deles for do tipo float, o resultado também será do tipo float
* i//j representa a divisão inteira de i e j (então o resultado será sempre int)
* i/j representa a divisão em ponto flutuante de i e j (isto, em Python 3, * então o resultado será sempre float)
* i%j representa o resto da divisão inteira de i e j (então o resultado será sempre int)

De forma similar, estes tipos possuem os operadores comparativos:
* == (igual);
* != (diferente)
* > (maior que)
* >= (maior ou igual a)
* < (menor que); e
* <= (menor ou igual a).

Objetos bool possuem os seguintes operadores lógicos
* a and b conjunção;
* a or b disjunção;
* **not** a negação.




## Exercícios

1. Faça um Programa que mostre a mensagem "Alo mundo" na tela.
2. Faça um Programa que peça um número e então mostre a mensagem O número informado foi [número].
3. Faça um Programa que peça dois números e imprima a soma.
4. Faça um Programa que peça as 4 notas bimestrais e mostre a média.
5. Faça um Programa que pergunte quanto você ganha por hora e o número de horas trabalhadas no mês. Calcule e mostre o total do seu salário no referido mês.
6. Faça um Programa que converta metros para centímetros.
7. João Papo-de-Pescador, homem de bem, comprou um microcomputador para controlar o rendimento diário de seu trabalho. Toda vez que ele traz um peso de peixes maior que o estabelecido pelo regulamento de pesca do estado de São Paulo (50 quilos) deve pagar uma multa de R$ 4,00 por quilo excedente. João precisa que você faça um programa que leia a variável peso (peso de peixes) e calcule o excesso. Gravar na variável excesso a quantidade de quilos além do limite e na variável multa o valor da multa que João deverá pagar. Imprima os dados do programa com as mensagens adequadas.

8. Faça um Programa que pergunte quanto você ganha por hora e o número de horas trabalhadas no mês. Calcule e mostre o total do seu salário no referido mês, sabendo-se que são descontados 11% para o Imposto de Renda, 8% para o INSS e 5% para o sindicato, faça um programa que nos dê:
salário bruto.
quanto pagou ao INSS.
quanto pagou ao sindicato.
o salário líquido.
calcule os descontos e o salário líquido, conforme a tabela abaixo:
    - Salário Bruto : R$
    - IR (11%) : R$
    - INSS (8%) : R$
    - Sindicato ( 5%) : R$
    - = Salário Liquido : R$

    Obs.: Salário Bruto - Descontos = Salário Líquido.

#### Dica
A função *input* interage com o usuário e pode ser usada para armazenar o valor de uma variável, exemplo:
```python
numero = input("Digite um número:")
```
Quando o interpretador passar por essa linha será lançada essa mensagem na tela do console e qualquer valor digitado será atribuído à variável *numero*.