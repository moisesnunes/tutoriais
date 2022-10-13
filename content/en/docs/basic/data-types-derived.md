---
title: "Derived Data Typed no C++"
description: ""
lead: ""
date: 2022-10-12T19:21:02-03:00
lastmod: 2022-10-12T19:21:02-03:00
draft: 
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

```
#include <iostream>
tipoRetorno nomeFuncao (arg1, arg2,...) {
...; // corpo da função
}
int main()
{...; // corpo da funcao principal main() }
```
onde:
-  tipoRetorno é o tipo de dado retornado pela função;

-  nomeFuncao é o nome atribuído à função;

-  arg1, arg2,... são os argumentos (ou parâmetros) passados à função quando ela é chamada; cada argumento deve ser precedido pelo seu respectivo tipo;

- corpo da funcao compreende às instruções da função.


__Exemplo__:

```c++
// Programa em C++ que mostra o funcionamento básico de uma Função
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
 Pressione qualquer tecla para continuar. . .
```
____
__Exemplo__:

```c++
// Programa em C++ que ilustra o uso básico das funções
#include<iostream>
using namespace std;

int soma(int x, int y)
{
  cout << "\n Funcao soma que rece os valores: " << x << " e " << y << endl;
  return (x + y);
}
int main()
{
  int a, b, c;
  cout << " Digite um valor inteiro: ";
  cin >> a;
  cout << " Digite outro valor inteiro: ";
  cin >> b;
  c = soma(a, b);
  cout << "\n Valor retornado pela funcao soma de: " << a <<  " + "  << b <<  " = "  << c << endl;
  return 0;
}
```
__OutPut__

```bash
 Digite um valor inteiro: 10
 Digite outro valor inteiro: 25

 Funcao soma que rece os valores: 10 e 25

 Valor retornado pela funcao soma de: 10 + 25 = 35

 Pressione qualquer tecla para continuar. . .

```

Observe que o programa consiste em duas funções: main() e soma(). Outros programas usam apenas a função main(). Da mesma forma que não podemos usar uma variável sem a declarar, também não podemos usar uma função sem declará-la antes. Portanto, você deve declarar a função no início do programa, como fizemos com o programa acima. 



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
### Passagem de Parâmetros para Funções

Os parâmetros passados para a função são chamados de **parâmetros reais**. Por exemplo, no programa abaixo, 5 e 10 são parâmetros reais.

Os parâmetros recebidos pela função são chamados de **parâmetros formais**. Por exemplo, no programa abaixo x e y são parâmetros formais.

```
class Multiplica {
  int multiplicador (int x, int y) { // Parâmetro formal 
    return (x * y);
  }
  public:
    static void main() {
      Multiplica M = new Multiplica();
      int a = 5, b = 10;
      int c = multiplicador (a, b); // Parâmetro real
      cout << " Soma é " << c;
    }
}
```
*Existem duas maneiras passar parâmetros*:

1. ***Passagem por valor***: neste método de passagem de parâmetros, os valores dos parâmetros reais são copiados para os parâmetros formais da função e os dois tipos de parâmetros são armazenados em diferentes locais de memória. Portanto, quaisquer alterações feitas dentro das funções não são refletidas nos parâmetros reais do chamador.

2. ***Passar por referência***: tanto os parâmetros reais quanto os formais referem-se aos mesmos locais, portanto, quaisquer alterações feitas dentro da função são refletidas nos parâmetros reais do chamador.

