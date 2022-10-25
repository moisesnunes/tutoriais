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

