---
title: "Programas Básicos com C++"
description: ""
lead: ""
date: 2022-10-25T01:14:20-03:00
lastmod: 2022-10-25T01:14:20-03:00
draft: false
images: []
menu:
  docs:
    parent: ""
    identifier: "programas-basicos-ee3193228fdfdb46b21fc4078a947668"
weight: 6001
toc: true
---
____

Neste artigo vamos aprender alguns programas básicos com C++.
____

## Hello World

```c++
#include<iostream>

int main()
{
  std::cout << "Hello World!";
  return 0;
}
```
Resultado:

```html
Hello World!
```
____

## Print de 1 até 100

```c++
#include<iostream>

int main()
{
  int i;
  for (i = 1; i <= 100; i++)
  {
    std::cout << "\n" << i;
  }
  return 0;
}
```
Resultado:

```html
1
2
3
4
5
.
.
.
100
```
____

## Print o alfabeto de A-Z

```c++
#include<iostream>

int main()
{
    std::cout << "Alfabeto de A-Z:\n";
    for (char c{'A'}; c <= 'Z'; c++){
        std::cout << c << '\n';
    }
    return 0;
}
```
Resultado:

```html
Alfabeto de A-Z:
A
B
C
D
E
F
G
H
I
J
K
L
M
N
O
P
Q
R
S
T
U
V
W
X
Y
Z
```
____

## Print se um número é par ou ímpar

```c++
#include<iostream>
using namespace std;

int main()
{
    int i;
    cout << "Digite um Numero: ";
    cin >> i;
    if (i % 2 == 0) // módulo com 2, o retorno 0 é par e o retorno 1 é ímpar
    {
        cout << "O numero " << i << " e par" << endl;
    }
    else
    {
        cout << "O numero " << i << " e primo " << endl;
    }
    return 0;
}
```
Resultado:

```html
Digite um Numero: 2
O numero 2 e par
```
____

## Print todos os números ímpares até N

```c++
#include<iostream>
using namespace std;

int main()
{
    int i, n;
    cout << "Digite um numero: ";
    cin >> n;
    for (int i = 0; i <= n; i++)
    {
        if ( i % 2 == 1) // para os número pares i % 2 == 0
            cout << "\n" << i;
        else
            continue;
    }
    return 0;
}
```
Resultado:

```html
Digite um numero: 10

1
3
5
7
9
```
____

## Inverta dois números com uma terceira variável

```c++
#include<iostream>
using namespace std;

int main()
{
    int a, b, c;
    cout << "Digite o primeiro numero: ";
    cin >> a;
    cout << "Digite o segundo numero: ";
    cin >> b;
    cout << "Os valores de " << a << " e " << b << " antes de trocarmos.\n";
    c=a; // c = 10
    a=b; // b = 20 -> a = 20
    b=c; // c = 10 -> b = 10
    cout << "Os valores de " << a << " e " << b << " depois de trocarmos." ;
    return 0;
}
```
Resultado:

```html
Digite o primeiro numero: 10
Digite o segundo numero: 20
Os valores de 10 e 20 antes de trocarmos.
Os valores de 20 e 10 depois de trocarmos.
```
____

## Mostre que o ano é bissexto ou não 

```c++
#include<iostream>
using namespace std;

int main()
{
    int ano;
    cout << "Digite o ano que para saber se ele e bissexto: ";
    cin >> ano;
    if (ano % 400 == 0){ // todos os anos múltiplos de 400
        cout << "O ano " << ano << " e bissexto." << endl;
    }
    else if (ano % 100 == 0){// De 100 em 100 anos não é ano bissexto. 
        cout << "O ano " << ano << " nao e bissexto." << endl;
    }
    else if (ano % 4 == 0){ // De 4 em 4 anos é ano bissexto. 
        cout << "O ano " << ano << " e bissexto." << endl;
    }
    else
    cout << "O ano " << ano << " nao e bissexto." << endl; // Não são bissextos todos os demais anos.
    return 0;
}
```
Resultado:

```html
Digite o ano que para saber se ele e bissexto: 2022
O ano 2022 nao e bissexto.
``` 
____

## Transforme N número de dias em ano, semanas, dias

```c++
#include<iostream>
using namespace std;

int main()
{
    int ndias, anos, semanas, dias;
    cout << "Digite o total de dias: ";
    cin >> ndias;
    anos = ndias / 365;
    semanas = (ndias % 365) / 7;
    dias = (ndias % 365) % 7;
    cout << ndias << " = " << anos << " ano " << semanas << " semanas " << dias << " dias" << endl;
}
```
Resultado:

```html
Digite o total de dias: 500
500 = 1 ano 19 semanas 2 dias
```