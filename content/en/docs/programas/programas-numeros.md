---
title: "Números com C++"
description: "Neste artigo vamos aprender programas com operações númericas com o C++."
lead: "Neste artigo vamos aprender programas com operações númericas com o C++."
date: 2022-10-27T23:23:16-03:00
lastmod: 2022-10-27T23:23:16-03:00
draft: false
images: []
menu:
  docs:
    parent: ""
    identifier: "programas-numeros-662daaef437c20c7517342a020ee36a5"
weight: 6002
toc: true
---
_____

{{< alert icon="💡" text="Por favor, Recarregue a página para ver os novos conteúdos." />}}

## Soma de N números 

```c++
#include<iostream>
using namespace std;

int main()
{
    int a, soma = 0;
    cout << "Digite um numero: ";
    cin >> a;
    for (int i = 0; i <= a; i++)
    {
        soma+=i; // soma = soma + i
    }
    cout << "Soma de todos os numeros ate "<< a << ": " << soma;
    return 0;
}
```
Resultado:

```html
Digite um numero: 100
Soma de todos os numeros ate 100: 5050
```
____

## Soma de todos os digítos de um número 

```c++
#include<iostream>
using namespace std;

int main()
{
    int depois, x, n, soma=0; // depois é a variável que será chamada quando o loop acabar, n>0.
                              // x para armazenar n%10
    cout << "Digite um numero: ";
    cin >> n;
    depois = n; // n se torna 0 no final do programa, assim precisamos de outra variável para restaurá-lo.
    while (n > 0)
    {
        x = n % 10; 
        soma+=x;
        n = n / 10;
    }
    cout << "A soma de todos os digitos de: " << depois << " e " << soma;
    return 0;
}
```
Resultado:

```html
Digite um numero: 1234
A soma de todos os digitos de: 1234 e 10
```
____

## Print o reverso de qualquer número 

```c++
#include<iostream>
using namespace std;

int main()
{
    int depois, x, n, rev=0;
    cout << "Digite um numero: ";
    cin >> n;
    depois = n;
    while (n > 0)
    {
        x = n % 10;
        rev = rev * 10 + x;
        n = n / 10;
    }
    cout << "O numero reverso de: " << depois << " e " << rev;
    return 0;
}
```
Resultado:

```html
Digite um numero: 1234
O numero reverso de: 1234 e 4321
``` 
____

## Soma de todos os inteiros divisíveis por 2

```c++
#include<iostream>
using namespace std;

int main()
{
    int num1, num2, soma=0;
    cout << "Digite o primeiro numero: ";
    cin >> num1;
    cout << "Digite o segundo numero: ";
    cin >> num2;
    for (int i = num1; i <= num2; i++)
    {
        if (i % 2 == 0)
        { 
            soma+=i;
        }
    }
    cout << "O soma de todos os inteiros divisiveis por 2 entre " << num1 << ", " << num2 << " e: " << soma << endl;
    return 0;
}
```
resultado:

```html
Digite o primeiro numero: 1
Digite o segundo numero: 5
O soma de todos os inteiros divisiveis por 2 entre 1, 5 e: 6
```
____


## O fatorial de qualquer número

```c++
#include<iostream>
using namespace std;

int main()
{
    int numero, fatorial = 1;
    cout << "Digite um numero para saber seu fatorial: ";
    cin >> numero;
    for (int i = 1; i <= numero; i++)
    {
    	fatorial = fatorial * i;
	}
	cout << "O fatorial de " << numero << "! = " << fatorial << endl;
}
```
Resultado:

```html
Digite um numero para saber seu fatorial: 5
O fatorial de 5! = 120
```
_____

## Serie de Fibonacci

```c++
#iclude<iostream>
int main()
```




























