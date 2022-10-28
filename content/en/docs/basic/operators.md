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
____

{{< alert icon="💡" text="Por favor, Recarregue a página para ver os novos conteúdos." />}}

Basicamente podemos dizer que um operador opera os operandos. Por exemplo, ‘+’ é um operador usado para adição, conforme mostrado abaixo:

```html
c = a + b;
```
Aqui, ‘+’ é o operador conhecido como operador de adição e ‘a’ e ‘b’ são operandos. O operador de adição diz ao compilador para adicionar ambos os operandos ‘a’ e ‘b’.

A funcionalidade da linguagem de programação C/C++ é incompleta sem o uso de operadores.

Podemos classificar os operadores build-in no C/C++ como:

1. __Operadores Aritméticos__ (+, -, *, /, %)
   
2. __Operadores Relacionais__ (==, !=, >, <, >=, <=)
   
3. __Operadores Lógicos__ (&&, ||, !)
   
4. __Operadores Bit a Bit__ (&, |, ^, ~, >>, <<)
   
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

Os operadores Bitwise são usados para realizar operações em nível de bit nos operandos. Os operadores são primeiro convertidos em nível de bits e, em seguida, o cálculo é realizado nos operandos. Operações matemáticas como adição, subtração, multiplicação, etc. podem ser executadas no nível de bits para um processamento mais rápido. Por exemplo, o operador AND bit a bit representado como ‘&’ em C recebe dois números como operandos e faz AND em cada bit de dois números. O resultado de AND é 1 somente se ambos os bits forem 1(True).

```html
int a = 5, b = 9; // a = 5(00000101), b = 9(00001001)
cout << (a ^ b); // 00001100
cout << (~a); // 11111010
```
1. O & (AND(E) bitwise) em C ou C++ recebe dois números como operandos e faz AND em cada bit de dois números. O resultado de AND é 1 somente se ambos os bits forem 1.

2. O | (OR(OU) bitwise) em C ou C++ recebe dois números como operandos e faz OR em cada bit de dois números. O resultado de OR é 1 se qualquer um dos dois bits for 1.

3. O ^ (XOR bitwise) em C ou C++ recebe dois números como operandos e faz XOR em cada bit de dois números. O resultado de XOR é 1 se os dois bits forem diferentes.

4. O << (Left Shift (deslocamento para a esquerda)) em C ou C++ leva dois números, desloca para a esquerda os bits do primeiro operando, o segundo operando decide o número de casas a serem deslocadas.

5. O >> (Right Shift (deslocamento para a direita)) em C ou C++ leva dois números, desloca para a direita os bits do primeiro operando, o segundo operando decide o número de casas a serem deslocadas.

6. O ~ (NOT(NÃO) bitwise) em C ou C++ pega um número e inverte todos os bits dele.

Para mais informações dos operadores [bitwise](https://en.wikipedia.org/wiki/Bitwise_operation).

Exemplo:

```c++
#include<iostream>
using namespace std;

int main()
{
  // a = 5(00000101), b = 9(00001001)
  int a = 5, b = 9;

  cout << "a = " << a << " , " << "b = " << b << endl;

  // AND // 00000001
  cout << "\na & b = " << (a & b) << endl;
  // OR // 00001101
  cout << "\na | b = " << (a | b) << endl;
  // XOR // 00001100
  cout << "\na ^ b = " << (a ^ b) << endl;
  // NOt // 11111010
  cout << "\n~a = " << (~a) << endl;
  // Left Shift // 00010010
  cout << "\nb << 1 = " << (b << 1) << endl;
  // Right Shift // 00000100
  cout << "\nb >> 1 = " << (b >> 1) << endl;

  return 0; 
}
```
- O operador bitwise XOR é o operador mais útil do ponto de vista técnico. É usado em muitos problemas. Um exemplo simples poderia ser “Dado um conjunto de números onde todos os elementos ocorrem um número par de vezes, exceto um número, encontre o número ímpar”.

```c++
#include<iostream>
using namespace std;

// Função que retorna o único valor ímpar em ocorrência
int findOdd(int arr[], int n)
{
  int res = 0 , i;
  for (i = 0; i < n; i++)
      res ^= arr[i];
  return res;
} 

// Teste
int main()
{
  int arr[] = {2,2,4,4,5,2,2,4,4,};
  int n = sizeof(arr) / sizeof(arr[0]);
  cout << "O elemento impar de ocorrencia: " << findOdd(arr, n);
  return 0;
}
```
- Os operadores bit a bit não devem ser usados no lugar de operadores lógicos. O resultado dos operadores lógicos (&&, || e !) é 0 ou 1, mas os operadores bit a bit retornam um valor inteiro. Além disso, os operadores lógicos consideram qualquer operando diferente de zero como 1. Por exemplo, considere o programa a seguir, os resultados de & e && são diferentes para os mesmos operandos.

```c++
#include<iostream>
using namespace std;

int main()
{
  int x = 1, y = 2;
  (x & y) ? cout << "Verdadeiro" : cout << "Falso";
  (x && y) ? cout << "\nVerdadeiro" : cout << "Falso";
  return 0;
}
```
- Os operadores de deslocamento à esquerda e deslocamento à direita são equivalentes à multiplicação e divisão por 2, respectivamente. Como mencionado antes, funciona apenas se os números forem positivos.

```c++
#include<iostream>
using namespace std;

int main()
{
  int x = 20;
  // Multiplicação por 2
  cout << "x << 1: " << ( x << 1) << endl;
  // Divisão por 2
  cout << "x >> 1: " << (x >> 1) << endl;
  return 0;
}
```
- O operador & pode ser usado para verificar rapidamente se um número é par ou ímpar. O valor da expressão (x & 1) seria diferente de zero somente se x for ímpar, caso contrário o valor seria zero.

```c++
#include<iostream>
using namespace std;

int main()
{
  int x = 20;
  (x & 1) ? cout << "Impar" : cout << "Par";
  return 0;
}
``` 
____

## 5. Operadores de Atribuição

Os operadores de atribuição são usados para atribuir valor a uma variável. O lado esquerdo do operador de atribuição é uma variável e o do lado direito do operador de atribuição é um valor. O valor do lado direito deve ser do mesmo tipo de dados que a variável do lado esquerdo, caso contrário o compilador irá gerar um erro.

### 5.1 '='

Este é o operador de atribuição mais simples. Este operador é usado para atribuir o valor da variável à direita para a variável à esquerda.

```html
a = 10;
b = 5;
```
### 5.2 '+='

Este operador é a combinação dos operadores ‘+’ e ‘=’. Esse operador primeiro adiciona o valor atual da variável à esquerda ao valor à direita e, em seguida, atribui o resultado à variável à esquerda.

```html
(a += b) é o mesmo que (a = a + b)
(x += 3) é o mesmo que (x = x + 3)
Se 5 = x, então, x += 3 = 8;
```
### 5.3 '-='

Este operador é uma combinação dos operadores '-' e '='. Este operador primeiro subtrai o valor à direita do valor atual da variável à esquerda e, em seguida, atribui o resultado à variável à esquerda.

```html
(a -= b) é o mesmo que (a = a -b)
(x -= 3) é o mesmo que (x = x -3)
Se 5 = x, então, x -= 3 = 2;
```
### 5.4 '*='

Este operador é uma combinação dos operadores '*' e '='. Esse operador primeiro multiplica o valor atual da variável à esquerda pelo valor à direita e, em seguida, atribui o resultado à variável à esquerda.

```html
(a *= b) é o mesmo que (a = a * b)
(x *= 3) é o mesmo que (x = x * 3)
Se 5 = x, então, x *= 3 = 15;
```
### 5.5 '/='

Este operador é uma combinação dos operadores '/' e '='. Esse operador primeiro divide o valor atual da variável à esquerda pelo valor à direita e, em seguida, atribui o resultado à variável à esquerda.

```html
(a /= b) é o mesmo que (a = a / b)
(x /= 3) é o mesmo que (x = x / 3)
Se 5 = x, então, x /= 3 = 1.66667;
```
____

## 6. Outros Operadores

Além dos operadores acima, existem alguns outros operadores disponíveis em C/C++ usados para realizar algumas tarefas específicas.

### 6.1 Operador Sizeof

- sizeof é muito usado na linguagem de programação C/C++.
- É um operador unário de tempo de compilação que pode ser usado para calcular o tamanho de seu operando.
- O resultado de sizeof é do tipo integral que geralmente é denotado por size_t.
- Basicamente, o operador sizeof é usado para calcular o tamanho da variável.
  
### 6.2 Operador Vírgula

- O operador vírgula é um operador binário que avalia seu primeiro operando e descarta o resultado, então avalia o segundo operando e retorna este valor e tipo.
- O operador vírgula tem a menor precedência de qualquer operador C.
- A vírgula atua como operador e separador.

### 6.3 Operador Condicional

- O operador condicional tem a forma Expressão1? Expressão2 : Expressão3.
- Aqui, Expressão1 é a condição a ser avaliada. Se a condição (Expressão1) for Verdadeira, executaremos e retornaremos o resultado da Expressão2, caso contrário, se a condição (Expressão1) for falsa, executaremos e retornaremos o resultado da Expressão3.
- Podemos substituir o uso de instruções if..else por operadores condicionais.
  
### 6.4 Operadors ponto(.) e seta(->)

- Os operadores de membro são usados para fazer referência a membros individuais de classes, estruturas e uniões.
- O operador ponto é aplicado ao objeto real.
- O operador de seta é usado com um ponteiro para um objeto.

### 6.5 Operador de Conversão

- Os operadores de conversão convertem um tipo de dados em outro. Por exemplo, int(2.2000) retornaria 2.
- Um cast é um operador especial que força um tipo de dado a ser convertido em outro.
- A conversão mais geral suportada pela maioria dos compiladores C é a seguinte − [ (tipo) expressão ].

### 6.6 Operador Pointer *,&

- Operador de ponteiro & retorna o endereço de uma variável. Por exemplo &a; fornecerá o endereço real da variável.
- Operador de ponteiro * é um ponteiro para uma variável. Por exemplo *var; apontará para uma variável var.
_____

Por favor, escreva para o email: (siteaprendacpp@gmail.com) se você encontrar algo incorreto ou se quiser compartilhar mais informações sobre o tópico discutido acima.





































































































