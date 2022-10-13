---
title: "Derived Data Typed no C++"
description: ""
lead: ""
date: 2022-10-12T19:21:02-03:00
lastmod: 2022-10-12T19:21:02-03:00
draft: false
images: []
menu:
  docs:
    parent: ""
    identifier: "data-types-derived-94ce4dd293bd825b51216dfc2f7baf54"
weight: 6
toc: true
---
____

## Tipos de Dados Derivado no C++

Os tipos de dados que são derivados dos tipos de dados primitivos ou integrados são chamados de Tipos de Dados Derivados. Estes podem ser de quatro tipos, a saber:

__Function__ 

__Array__

__Pointers__

__References__

Vamos estudar cada um deles:

### Funções no C++

Uma função é um conjunto de instruções que recebem entradas (input), fazem algum cálculo específico e produzem saída (output). A ideia é juntar algumas tarefas comuns ou repetidas e criar uma função para que em vez de escrever o mesmo código várias vezes para entradas diferentes, possamos chamar a função.

*Em termos simples, uma função é um bloco de código que só é executado quando é chamado.*

__Sintaxe Básica__:

|                     |                    |                             |
|:-------------------:|:------------------:|:---------------------------:|
| **Tipo de Retorno** |                    | **Tipo do Parâmetro (int)** |
|         int         |        CPP         |      ( int x, int y );      |
|                     | **Nome da Função** |  **Nome do Parâmetro (x)**  |

__Exemplo__:

```c++
// Programa em C++ a funcionamento básico de uma Função
#include<iostream>
using namespace std;

// A seguir temos duas funções que tomam dois parâmetros como input x e y
// E retornam o máximo dos dois números como input 
int max(int x, int y)
{
  if (x > y)
      return x;
  else
      return y;
}
// A função main() que não recebe nenhum parâmetro e retorna um integer
int main()
{
  int a = 10, b = 20;

  // Chamando a função definda acima para achar o máximo dos dois números
  int maior = max(a, b);

  cout << " O Numero maior: " << maior;
  return 0;
}
```
__Output__

```bash
 O Numero maior: 20
```
### Por que precisamos de funções?

- As funções nos ajudam a *reduzir a **redundância*** do programa. Se a funcionalidade for executada em vários lugares no software, em vez de escrever o mesmo código, repetidamente, criamos uma função e a chamamos em qualquer lugar. Isso também ajuda na manutenção, pois precisamos alterar apenas um local se fizermos alterações futuras na funcionalidade.

- As funções tornam o código **modular**. Considere um arquivo grande com muitas linhas de código, torna-se muito simples ler e usar o programa se o código for dividido em funções.

- As funções fornecem **abstração**. Por exemplo, podemos usar funções de biblioteca sem nos preocupar com seu trabalho interno.

### Declarando Funções

Uma declaração de função informa ao compilador sobre o número de parâmetros que a função recebe, o tipos de dados de parâmetros, e retorna o tipo de função. Colocar nomes de parâmetros na declaração da função é opcional quando declaramos a função, mas é necessário colocá-los na definição. Abaixo está um exemplo de declarações de função.

__Exemplo__:

```c++
// Função que pega dois integers como parâmetros
// E retorna um integer
int max(int, int);

// Função que pega um pointer (ponteiro) int e uma variável int como parâmetros
// E retorna um pointer de tipo int
int* swap(int*, int);

// Função que pega um char como parâmetro
// E retorna um variável de referência
char* call(char b);

// Função que pega um char e int como parâmetros
// E retorna um integer
int fun(char, int);
```
### Tipos de funções
