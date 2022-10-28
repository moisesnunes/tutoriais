---
title: "Qual intervalo válido de Data Types?"
description: "O que pode acontecer se excedermos o intervalo dos build-in data-types?"
lead: "O que pode acontecer se exedermos o intervalo dos build-in data-types?"
date: 2022-09-27T15:35:35-03:00
lastmod: 2022-09-27T15:35:35-03:00
draft: false
images: []
menu:
  docs:
    parent: ""
    identifier: "valid-data-types-96a10482c80da4e8f3b09189860856f8"
weight: 7
toc: true
---
____

{{< alert icon="💡" text="Por favor, Recarregue a página para ver os novos conteúdos." />}}

Neste artigo, veremos o que pode acontecer quando excedemos o intervalo válido de tipos de dados internos em C++ com alguns exemplos.

__char__

__Exemplo com char__: Vamos ver um programa que mostra o que acontece quando excedemos o intervalo de *char*.

Neste exemplo temos que *a* é declarado como char, o loop deve funcionar de 0 a 225. Então, ele deve fazer print de 0 a 225 e parar; mas ao invéz disso, ele vai gerar um loop infinito. A razão para isso é que o intervalo válido de dados de caracteres é de -128 a 127. Quando '*a*' se tornar 128 pelo a++, o intervalo é excedido e, como resultado, o primeiro número do lado negativo do intervalo (ou seja, -128) é atribuído a. Como resultado disso, '*a*' nunca chegará ao ponto 225. Portanto o programa printa a série infinita de caracteres.

```c++
// Programa para demonstar problema com char
#include<iostream>
using namespace std;

int main()
{
  for (char a = 0; a <= 225; a++)
    cout << a;
  return 0;
}
```
____

__bool__

Neste próximo veremos que o programa vai fazer o print de '1' infinitas vezes, porque aqui 'a' é declarado como 'bool' e seu intervalo válido é de 0 a 1. E para uma variável booleana, qualquer coisa diferente de 0 é 1 (ou true). Quando 'a' tenta se tornar 2 (através de a++), 1 é atribuído a 'a'. A condição a<=5 é satisfeita e o controle permanece dentro do loop.

__Exemplo com bool__: Vamos ver um programa que mostra o que acontece quando excedemos o intervalo de '*bool*'

```c++
// Programa para demonstar problema com bool
#include<iostream>
using namespace std;

int main()
{
  // declarando a variável bool com um valor de true
  bool a = true;

  for (a = 1; a <= 5; a++)
    cout << a;
  return 0;
}
```
____

__short__

*Este programa vai fazer o print de 'a' até que ele se torne 32770?. A responda é um loop infinito porque 'a' é declarado como um short e seu intervalo válido e de -32768 até +32767. Quando 'a' tente se tornar 32768 pelo a++, o intervalo é excedido e como resultado, o primeiro número do lado negativo do intervalo (-32768) é atribuida em 'a'. Portanto, a condição "a < 32770" é satisfeita e o controle permanece no loop.

__Exemplo com short__: Vamos ver outro programa que mostra o que acontece quando execedemos o intervalo de 'short'.

*Observe que short é abreviação de short int. Eles são sinônimos, short, short int, signed short e signed short int são todos do mesmo tipo de dados. Também note que a ordem não importa, int short signed é a mesma coisa que signed short int.*

```c++
// Programa para demonstar problema com short
#include <iostream>

using namespace std;

int main()
{
	// declarando a variável short 
	short a;

	for (a = 32767; a < 32770; a++)
		cout << a << "\n";

	return 0;
}
```
____

Por favor, escreva para o email: (__siteaprendacpp@gmail.com__) se você encontrar algo incorreto ou se quiser compartilhar mais informações sobre o tópico discutido acima.