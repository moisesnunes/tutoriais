---
title: "Lista de Problemas relacionada aos Números Primos"
description: "Prátique o que você aprendeu sobre números e tente resolver os desafios."
lead: "Prátique o que você aprendeu sobre números e tente resolver os desafios."
date: 2022-10-12T22:21:28-03:00
lastmod: 2022-10-12T22:21:28-03:00
draft: true
images: []
menu:
  docs:
    parent: ""
    identifier: "chapter-4-7aa44b79bf1d3e0de5f046cd5e4ef70b"
weight: 2004
toc: true
---
____

## Encontre dois números primos distintos cujo produto seja igual ao número dado

*Dado um número N (maior que 2). Sua tarefa é encontrar dois números primos distintos cujo produto seja igual ao número fornecido. Pode haver várias combinações possíveis. Print apenas o primeiro par desse tipo.*

Se não for possível expressar N como produto de dois primos distintos, printe “Sem Produto”.

__Exemplo__

Input: N = 15

Outptu: 3, 5

Explicação: 3 e 5 são primos e 3*5 = 15

Input: N = 34

Output: 2, 17 

Explicação: 2 e 17 são primos e 2*17 = 34

_____

Você pode tentar resolver o problema no seu IDE local ou tente no [IDE](https://ide.geeksforgeeks.org/) online.
_____

### Resolução

{{< details "Resposta:" >}}

A idéia é encontrar todos os primos menores ou iguais ao número dado N usando o crivo de Eratóstenes. Assim que tivermos uma matriz que informe todos os primos, podemos percorrer essa matriz para encontrar um par com um determinado produto.

Abaixo temos a implementação da abordagem acima:

```c++
// Programa em C++ para achar um par de números primos cujo produto
// É igual ao número dado
#include<bits/stdc++.h>
using namespace std;

//Função para gerar todos os números primos menores que n
bool CrivodeEratostenes(int n, bool prime[])
{
  // Inicialize todas as entradas do array booleano como true.
  // Um valor em prime[i] será falso se i Não for primo
  // else true
  prime[0] = prime[1] = false;
  for (int i = 2; i <= n; i++)
    prime[i] = true;

  for (int p = 2; p * p <= n; p++)
  {
    // Se prime[p] não mudar então, prime[p] é primo
    if (prime[p] == true)
    {
      // atualize todos os múltiplos de p
      for (int i = p * 2; i <= n; i += p)
        prime[i] = false;
    }
  }
}

// Função para fazer o print de uma dupla de primos com um produto
void AcheParPrimo(int n)
{
  int flag = 0;
  
  // Gerando primos com a função o crivo de Eratóstenes
  bool prime[n + 1];
  CrivodeEratostenes(n, prime);

  // Percorra todos os números para encontrar o primeiro par
  for (int i = 2; i < n; i++)
  {
    int x = n / i;

    if (prime[i] && prime[x] and x != i and x * i == n)
    {
      cout << i << " " << x;
      flag = 1;
      return;
    }
  }

  if (!flag)
    cout << " Sem Produto ";
}
int main()
{
  int n = 29;

  AcheParPrimo(n);

  return 0;
}
```
{{< /details>}}

____