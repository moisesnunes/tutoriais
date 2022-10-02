---
title: "Introdução ao C++"
description: ""
lead: ""
date: 2022-10-01T00:08:18-03:00
lastmod: 2022-10-01T00:08:18-03:00
draft: false
images: []
menu:
  docs:
    parent: "tutorial"
    identifier: "introduction-cf3b201e1a480492dbec4a35439be848"
weight: 1001
toc: true
---
## Introdução ao C++

C++ é uma das linguagens de programação de propósito geral mais flexíveis e eficientes, que é um superconjunto da linguagem de programação C onde a maioria das ferramentas e bibliotecas suportadas em C também podem ser usadas em C++. Esta introdução ao artigo c++ está dividida em várias seções, começando por uma visão geral da linguagem até suas vantagens e desvantagens.

____

## Overviem do C++

O advento do C++ aconteceu em 1983 quando Bjarne Stroustrup começou a trabalhar com ‘C com classes, que mais tarde foi renomeado para C++ que tinha poucos recursos adicionais como sobrecarga de operadores, comentários no estilo BCPL, etc.

A ideia por trás do C++ é que ele é uma linguagem compilada, o que significa que o programa fonte é compilado para produzir arquivos de objeto que produzem um programa executável depois de serem combinados por um vinculador. A imagem abaixo dá uma ideia de uma compilação de programa em C++.

Um dos outros aspectos do C++ é seu recurso estatisticamente tipado, ou seja, qualquer objeto, valor ou nome deve ser pré-informado ao compilador, o que pode ajudar a determinar o conjunto de operações que precisam ser executadas. C++ é adequado para aplicativos que têm restrições de recursos e beneficia aqueles que preferem escrever código de qualidade. Apesar da introdução de várias novas linguagens de programação, C++ ainda está evoluindo e é usado por pessoas de várias backgrounds.

___

## Componentes do C++

### 1. Primeiro componente

```c++
#include<iostream>

int main()
{
  std::cout << "Hello World\n";
}
```
O primeiro componente neste programa é o arquivo de cabeçalho denotado pelo comando #include<iostream>, que contém o comando cout que está sendo usado para imprimir ‘Hello World’ neste caso. 

### 2. Segundo componente

```c++
void print_square(double x)
{
  cout << "A raiz de" << x << " é " << square(x) << "\n";
}
int main()
{
  print_square(1.234);
}
```

### 3. Terceiro componente