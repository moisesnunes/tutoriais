---
title: "C++ Data Types"
description: ""
lead: ""
date: 2022-09-27T15:07:22-03:00
lastmod: 2022-09-27T15:07:22-03:00
draft: false
images: []
menu:
  docs:
    parent: ""
    identifier: "data-types-5fd683a1f8a832dcd54b0605cf03bf54"
weight: 5
toc: true
---

## Data Types no C++

All variables use data-type during declaration to restrict the type of data to be stored. Therefore, we can say that data types are used to tell the variables the type of data it can store. Whenever a variable is defined in C++, the compiler allocates some memory for that variable based on the data type with which it is declared. Every data type requires a different amount of memory.

C++ supports a wide variety of data types and the programmer can select the data type appropriate to the needs of the application. Data types specify the size and types of value to be stored. However, storage representation and machine instructions to manipulate each data type differ from machine to machine, although C++ instructions are identical on all machines.

C++ supports the following data types:

## Prática

Dada uma String S, descubra qual dos seguintes data types básicos ela representa e seu tamanho (em bytes).
Os data types possíveis são:
1. Integer
2. Float
3. Double
4. Character

Exemplo 1.
```bash
Input:
S=a
Output:
1
Explicação:
A string claramente representa o tipo char e assim o tamanho de char é exibido
```
Exemplo 2.
```bash
Input
S=98.45685456
Output: 
8
Explanation:
A string representa um Double.
```
### Sua Tarefa

Sua tarefa é completar a função __BasicDataType__() que recebe a String S como parâmetro de entrada e exibe o tamanho (em bytes) do tipo de dados que ela representa.
Copie o código abaixo e faça a tarefa:

```c++
#include <bits/stdc++.h>
using namespace std;

class Solution {
  public:
    int BasicDataType(string s) {
        // digite aqui
    }
};

int main() {
    int t;
    cin >> t;
    while (t--) {
        string S;
        cin >> S;

        Solution ob;
        cout << ob.BasicDataType(S) << endl;
    }
}
```
{{< details "Respostas:" >}}

Diferentes respostas seguem abaixo:
____

```c++
#include <bits/stdc++.h>
using namespace std;

class Solution {
  public:
    int BasicDataType(string s) {
       
        int size = s.size()
        // Se existe apenas 1 character ele será
        if(size==1) {
          // Ou int ou char
            if(isdigit(s[0])) return sizeof(int);
            else return sizeof(char);
        }
        for(int i=0; i<size; i++)
        {
          // Ou float e double
            if(s[i]=='.')
            {
                if(size-1-i>=6) return sizeof(double);
                return sizeof(float);
            }
        }
        return sizeof(int);
    }      
};

int main() {
    int t;
    cin >> t;
    while (t--) {
        string S;
        cin >> S;

        Solution ob;
        cout << ob.BasicDataType(S) << endl;
    }
}
```
____


{{< /details >}}