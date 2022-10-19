---
title: "Operadores no C++"
description: "Os operadores assim como os data types são os fundamentos de qualquer linguagem de programação. Podemos definir operadores como símbolos que nos ajudam a realizar cálculos matemáticos e lógicos específicos em operandos."
lead: "Os operadores assim como os data types são os fundamentos de qualquer linguagem de programação. Podemos definir operadores como símbolos que nos ajudam a realizar cálculos matemáticos e lógicos específicos em operandos."
date: 2022-09-27T15:37:30-03:00
lastmod: 2022-09-27T15:37:30-03:00
draft: false
images: []
menu:
  docs:
    parent: ""
    identifier: "operators-99903efcb7f599852f69684c414ecf67"
weight: 9
toc: true
--- 
Basicamente podemos dizer que um operador opera os operandos. Por exemplo, ‘+’ é um operador usado para adição, conforme mostrado abaixo:

```html
c = a + b;
```
Aqui, ‘+’ é o operador conhecido como operador de adição e ‘a’ e ‘b’ são operandos. O operador de adição diz ao compilador para adicionar ambos os operandos ‘a’ e ‘b’.

A funcionalidade da linguagem de programação C/C++ é incompleta sem o uso de operadores.

Podemos classificar os operadores build-in no C/C++ como:

1. __Operadores aritméticos__ (+, -, *, /, %)
   
2. __Operadores Relacionais__ (==, !=, >, <, >=, <=)
   
3. __Operadores lógicos__ (&&, ||, !)
   
4. __Operadores bit a bit__ (&, |, ^, ~, >>, <<)
   
5. __Operadores de Atribuição__ (=, +=, -=, *=)
   
6. __Outros Operadores__

_____

## 1. Operadores Aritméticos
   
Esses operadores são usados para realizar operações aritméticas/matemáticas em operandos. Exemplos: (+, -, *, /, %,++,–). Os operadores aritméticos são de dois tipos:

### 1.1 Operadores Unários:

Os operadores que operam ou trabalham com um único operando são operadores unários. Por exemplo: Operadores de Incremento(++) e Decremento(--)

```html
int x = 5;
x++; // 6 
```
- __Incremento__: O operador ‘++’ é usado para incrementar o valor de um inteiro. Quando colocado antes do nome da variável (também chamado de operador de pré-incremento), seu valor é incrementado instantaneamente. Por exemplo, __++x__. E quando o colocamos após o nome da variável (também chamado de operador pós-incremento), seu valor é preservado temporariamente até a execução desta instrução e é atualizado antes da execução da próxima instrução. Por exemplo, __x++__.

- __Decremento__: O operador ‘ – – ‘ é usado para decrementar o valor de um inteiro. Quando colocado antes do nome da variável (também chamado de operador de pré-decremento), seu valor é decrementado instantaneamente. Por exemplo, – – x. E quando o colocamos após o nome da variável (também chamado de operador pós-decremento), seu valor é preservado temporariamente até a execução desta instrução e é atualizado antes da execução da próxima instrução. Por exemplo, x – –.

Exemplo:

```c++
// Programa em C++ para demonstrar o funcionamento dos operadores unários
#include<iostream>
using namespace std;

int main(){
  int x = 10, uni;

  cout << "Valor inicial de x: " << x << endl;
  
  // Exemplo de pós-incremento
  uni = x++;
  cout << "\nValor de x++: " << x << endl; // x se torna 11
  cout << "Valor de uni: " << uni << endl; // uni é atribuido 10 
 
  // Exemplo de pós-decremento
  uni = x--;
  cout << "\nValor x--: " << x << endl; // x se torna 10
  cout << "Valor de uni: " << uni << endl; // uni é atribuido 11

  // Exemplo pré-incremento
  uni = ++x;
  cout << "\nValor de ++x: " << x << endl; // x se trona 11 
  cout << "Valor de uni: " << uni << endl; // uni é atribuido 11

  //Exemplo pré-decremento
  uni = --x;
  cout << "\nValor de --x: " << x << endl; // x se torna 10
  cout << "Valor de uni: " << uni << endl; // uni é atribuido 10
}
```
### 1.2 Operadores Binários:

Os operadores que operam ou trabalham com dois operandos são operadores binários. Por exemplo: Adição(+), Subtração(-), Multiplicação(*), Divisão(/).

```html
int a = 7;
int b = 10;
cout << a + b; // 17
```
1. __Adição__: O operador ‘+’ adiciona dois operandos. Por exemplo, x+y.
  
2. __Subtração__: O operador ‘-‘ subtrai dois operandos. Por exemplo, x-y.
   
3. __Multiplicação__: O operador de ' * ' multiplica dois operandos. Por exemplo, x*y.
   
4. __Divisão__: O operador '/' divide dois operandos. Por exemplo, x/y.
   
5. __Módulo__: O operador ‘%’ retorna o resto quando o primeiro operando é dividido pelo segundo. Por exemplo, x%y.

Exemplo

```c++
#include<iostream>
using namespace std;

int main(){
   int a = 10, b = 5, bin;

   cout << "\nValor de a: " << a << "\nValor de b: " << b << endl;
  
   // Adição
   cout << "\nSoma de a + b: " << a + b << endl;
   // ou
   bin = a + b;
   cout << "Soma de a + b: " << bin << endl;

   // Subtração
   cout << "\nSubtração de a - b: " << a - b << endl;
   // ou
   bin = a - b;
   cout << "Subtração de a - b: " << bin << endl;

   // Multiplicação
   cout << "\nMultplicação de a * b: " << a * b << endl;
   //ou 
   bin = a * b;
   cout << "Multiplicação de a * b: " << bin << endl;

   // Divisão
   cout << "\nDivisão de a / b: " << a / b << endl;
   // ou
   bin = a / b;
   cout << "Divisão de a / b: " << bin << endl;

   // Módulos
   cout << "\nMódulo a % b: " << a % b << endl;
   // ou
   bin = a % b;
   cout << "Módulo a % b: " << bin << endl;
}
```
____

## 2. Operadores Relacionais

Estes operadores são usados para a comparação dos valores de dois operandos. Por exemplo, verificar se um operando é igual ao outro ou não, se um operando é maior que o outro ou não, etc. Alguns dos operadores relacionais são (==, >= , <= ).

### 2.1 Operador 'igual a'
 
Representado como ‘==’, o operador igual a verifica se os dois operandos fornecidos são iguais ou não. Se sim, ele retorna verdadeiro.Caso contrário, retorna falso. Por exemplo, 5==5 retornará verdadeiro.

### 2.2 Operador 'diferente de'

Representado como '!=', o operador diferente de verifica se os dois operandos fornecidos são iguais ou não. Se não, ele retorna verdadeiro. Caso contrário, retorna falso. É o complemento booleano exato do operador '=='. Por exemplo, 5!=5 retornará falso.

### 2.3 Operador 'maior que'

Representado como ‘>’, o operador maior que verifica se o primeiro operando é maior que o segundo operando ou não. Se sim, ele retorna verdadeiro. Caso contrário, retorna falso. Por exemplo, 6>5 retornará true.

### 2.4 Operador 'menor que'

Representado como '<', o operador menor que verifica se o primeiro operando é menor que o segundo operando. Se sim, ele retorna verdadeiro. Caso contrário, retorna falso. Por exemplo, 6<5 retornará false.

### 2.5 Operador 'maior ou que ou igual'

Representado como ‘>=’, o operador maior ou igual a verifica se o primeiro operando é maior ou igual ao segundo operando. Se sim, ele retorna verdadeiro, senão retorna falso. Por exemplo, 5>=5 retornará verdadeiro.

### 2.6 Operador 'menor que ou igual'

Representado como ‘<=’, o operador menor ou igual a verifica se o primeiro operando é menor ou igual ao segundo operando. Se sim, retorna true senão false. Por exemplo, 5<=5 também retornará true.

Exemplo

```c++
#include<iostream>
using namespace std;

int main()
{
  int a = 10, b = 5;

  // Exemplo igual a ==
  if (a == b)
      cout << "a é igual a b\n"; // falso
  else 
      cout << "a e b não são iguais\n"; // verdadeiro
  
  // Exemplo diferente de !=
  if (a != b)
      cout << "a não é igual a b\n"; // verdadeiro
  else
      cout << "a é igual a b\n"; //   falso
  
  // Exemplo maior que >
  if ( a > b)
      cout << "a é maior que b\n"; // verdadeiro
  else
      cout << "a é menor ou igual a b\n"; // falso

  // Exemplo menor que <
  if (a < b)
      cout << "a é menor que b\n"; // falso
  else
      cout << "a é maior ou igual a b\n"; // verdadeiro

  // Exemplo maior que ou igual
  if ( a >= b)
      cout << "a é maior ou igual a b\n"; // verdadeiro
  else
      cout << "a é menor do que b\n"; // falso

  // Exemplo menor que ou igual
  if ( a <= b)
      cout << "a é menor ou igual a b\n"; // falso
  else
      cout << "a é maior do que b\n"; // verdadeiro

  return 0;
}
```
____

## 3. Operadores Lógicos

Operadores lógicos são usados para combinar duas ou mais condições/restrições ou para complementar a avaliação da condição original em consideração. O resultado da operação de um operador lógico é um valor booleano verdadeiro ou falso.

```html
(4 != 5) && (4 < 5); // verdadeiro
```
### 3.1 Operador Lógico AND '&&'

O AND(e) lógico representado como o operador ‘&&’ retorna-se verdadeiro quando ambas as condições em consideração são satisfeitas. Caso contrário, retorna falso. Portanto, a && b retorna true quando a e b são true (ou seja, diferente de zero).

### 3.2 Operaodor Lógico OR '||'

O operador ‘||’(ou) retorna true mesmo se uma (ou ambas) das condições em consideração for satisfeita. Caso contrário, retorna falso. Por exemplo, um || b retorna verdadeiro se um de a ou b, ou ambos forem verdadeiros (ou seja, diferente de zero). Claro, ele retorna verdadeiro quando a e b são verdadeiros.

### 3.3 Operador Lógico NOT '!'

O operador '!'(não) retorna true se a condição em consideração não for satisfeita. Caso contrário, retorna falso. Por exemplo, !a retorna true se a for false, ou seja, quando a=0.

Exemplo

```c++
#include<iostream>
using namespace std;

int main()
{
  int a = 10, b = 5, c =  10, d = 4;

  // Exemplo com o operador lógico AND '&&'
  if (a > b && c == d)
      cout << "a é maior do que b 'E' c é igual a d.\n";
  else
      cout << "condição 'AND' não satisfeita.\n";

  // Exemplo com o operador lógico OR '||'
  if (a > b || c == d)
      cout << "a é maior do que b 'OU' c é igual a b\n";
  else
      cout << "condição 'OU' não satisfeita\n";

  // Exemplo com o operador lógico NOT '!'
  if (!a)
      cout << "a é zero\n";
  else
      cout << "a nao é zero\n";    
  return 0;
}
```
____

Mais considerações nos operadores lógicos:

- No caso de AND lógico, o segundo operando não é avaliado se o primeiro operando for falso. Por exemplo, o programa 1 abaixo não faz o print de “AprendaCpp” pois o primeiro operando do AND lógico é falso.

```c++
#include<iostream>
using namespace std;

int main()
{
  int a = 10, b = 5;
  bool log = ((a == b) && cout << "AprendaCpp");
  return 0; 
}
```
- Para fazer o print de "AprendaCPP" o primeiro operando do operador lógico AND '&&' deve ser verdadeiro.

```c++
#include<iostream>
using namespace std;

int main()
{
  int a = 10, b = 5;
  bool log = ((a >= b || a != b) && cout << "AprendaCpp");
  return 0;
}
```
- De forma semelhante, no caso de OR lógico, o segundo operando não é avaliado se o primeiro operando for verdadeiro. Por exemplo, o programa abaixo faz o print de “AprendaCpp” pois o primeiro operando do OR lógico é verdadeiro.

```c++
#include<iostream>
using namespace std;

int main()
{
  int a = 10, b = 6;
  bool log = ((a >= b) || cout << "AprendaCpp");
  return 0;
}
```
- Para fazer o print de "AprendaCpp" o primeiro operador lógico OR '||' deve ser falso.
____

## 4. Operadores BitWise (bit a bit)























































