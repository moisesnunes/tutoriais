---
title: "Números Primos - Algoritmos para números primos menores que N"
description: "Aprenda várias algoritmos para achar todos os números primos menores que n."
lead: "Aprenda várias algoritmos para achar todos os números primos menores que n."
date: 2022-10-11T00:20:22-03:00
lastmod: 2022-10-11T00:20:22-03:00
draft: false
images: []
menu:
  docs:
    parent: ""
    identifier: "chapter-3-e53f494a3ba810b638b64673048af200"
weight: 2003
toc: true
---
____

{{< alert icon="💡" text="Por favor, Recarregue a página para ver os novos conteúdos." />}}

## Crivo de Eratóstenes

Dado um número n, faça o print de todos os primos menores ou iguais a $n$. Considere também que $n$ é um número pequeno.

__Exemplo__:

__Input__: $n$ = 10

__Output__: 2 3 5 7

__Input__: $n$ = 20

__Output__: 2 3 5 7 11 13 17 19

O crivo de Eratóstenes é uma das maneiras mais eficientes de encontrar todos os primos menores que $n$ quando $n$ é menor que 10 milhões,[Wikipedia](https://en.wikipedia.org/wiki/Sieve_of_Eratosthenes).

A seguir explicamos o algoritmo para encontrar todos os números primos menores ou iguais a um dado inteiro $n$ pelo método de Eratóstenes:

Quando o algoritmo terminar, todos os números da lista que não estão marcados são primos.

Vamos dar um exemplo quando $n$ = 20. Assim, precisamos exibir todos os números primos menores ou iguais a 20.

 |    |    |    |    |
 |----|----|----|----|
 |    | 2  | 3  | 4  |
 | 5  | 6  | 7  | 8  |
 | 9  | 10 | 11 | 12 |
 | 13 | 14 | 15 | 16 |
 | 17 | 18 | 19 | 20 |

De acordo com o algoritmo, marcaremos todos os números que são divisíveis por __2__ e são maiores ou iguais ao seu quadrado.

|    |          |    |          |
|----|----------|----|----------|
|    | 2        | 3  | **_4_**  |
| 5  | **_6_**  | 7  | **_8_**  |
| 9  | **_10_** | 11 | **_12_** |
| 13 | **_14_** | 15 | **_16_** |
| 17 | **_18_** | 19 | **_20_** |

Agora vamos para o nosso próximo número não marcado __3__ e marcamos todos os números que são múltiplos de 3 e são maiores ou iguais ao seu quadrado.

|         |          |          |          |
|---------|----------|----------|----------|
|         | 2        | 3        | **_4_**  |
| 5       | **_6_**  | 7        | **_8_**  |
| **_9_** | **_10_** | 11       | **_12_** |
| 13      | **_14_** | **_15_** | **_16_** |
| 17      | **_18_** | 19       | **_20_** |

Passamos para o nosso próximo número não marcado __5__ e marcamos todos os múltiplos de 5 e são maiores ou iguais ao seu quadrado.

|         |          |          |          |
|---------|----------|----------|----------|
|         | 2        | 3        | **_4_**  |
| 5       | **_6_**  | 7        | **_8_**  |
| **_9_** | **_10_** | 11       | **_12_** |
| 13      | **_14_** | **_15_** | **_16_** |
| 17      | **_18_** | 19       | **_20_** |

Continuamos esse processo até o último número não marcado em nosso tabela.

Portanto os números __NÃO__ __MARCADOS__ são os números __PRIMOS__: 

 2, 3, 5, 7, 11, 13, 17, 19, ... 

 ### Implementação

 Agora vamos tentar implementar o algoritmo acima com C++ e Python3. Na implementação a seguir, uma matriz booleana arr[] de tamanho n é usada para marcar múltiplos de números primos.

__C++__

 ```c++
// Programa em C++ que printa todos os números primos menores ao iguais a n com o método de Crivo de Eratóstenes.
#include<bits/stdc++.h>
using namespace std;

void CrivodeErastotenes(int n)
{
    // Crie uma matriz booleana "prime[0..n]" e inicialize todas as entradas como verdadeiras.
    // Um valor em prime[i] será false se i não for primo, else true.
    bool prime[n + 1];
    memset(prime, true, sizeof(prime));

    for (int p = 2; p * p <= n; p++) {
        // Se prime[p] não for alterado, então é um primo
        if (prime[p] == true) {
            // Atualize todos os múltiplos de p maiores ou iguais ao quadrado de seus números
            // que são multiplos de p e são menores que p^2 que já estão marcados
            for (int i = p * p; i <= n; i += p)
                prime[i] = false;
        } 
    }
    // Print todos os números primos
    for (int p = 2; p <= n; p++)
        if (prime[p])
            cout << p << " ";
}

// Teste
int main()
{
    int n = 30;
    cout << "Todos os números primos a seguir são menores a iguais: " << n <<  endl;
    CrivodeErastotenes(n);
    return 0;
}
```
____

__Pyhton__

```python
# Programa em Python que printa todos os números primos menores ao iguais a n com o método de Crivo de Eratóstenes.
def CrivodeErastotenes(n):

  # Crie uma matriz booleana "prime[0..n]" e inicialize todas as entradas como verdadeiras.
  # Um valor em prime[i] será false se i não for primo, else true.
  prime = [True for i in range(n+1)]
  p = 2
  while (p * p <= n):

    # Se prime[p] não for alterado, então é um primo
    if (prime[p] == True):

        # Atualize todos os multiplos de p
        for i in range(p * p, n+1 , p):
          prime[i] = False
    p += 1

  # Faça o print de todos os números primos
  for p in range(2, n+1):
    if prime[p]:
      print(p)

# Teste
if __name__ == '__main__':
  n = 150
  print("Todos os números primos a seguir são menores a iguais: ", n)
  CrivodeErastotenes(n)
```
____

## Prática

*Dado um número __N__, calcule os números primos até N usando o crivo de Eratóstenes.*

Sua tarefa é completar a função __sieveOfEratosthenes()__ que recebe um inteiro N como parâmetro de entrada e retorna a lista de números primos menores ao igual a N.

__Exemplo__:

Input: n = 10

Output: 2 3 5 7 

Explicação: Números primos menores ao igual a N são, 2, 3, 5, 7

Input: n = 35

Output: 2 3 5 7 11 13 17 19 23 29 31

Explicação: Números primos menores ao igual a N são, 2, 3, 5, 7, 11, 13, 17, 19, 23, 29, 31

__Restrições:__

$1 ≤ N ≤ 10^4$
___

Resolva o problema e envie sua resposta no [GeeksforGeeks](https://practice.geeksforgeeks.org/problems/sieve-of-eratosthenes5242/1).

___
