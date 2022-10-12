---
title: "Pratica"
description: ""
lead: ""
date: 2022-10-12T19:19:55-03:00
lastmod: 2022-10-12T19:19:55-03:00
draft: true
images: []
menu:
  docs:
    parent: ""
    identifier: "pratica-eabb386a900155049f94a5c8267ec644"
weight: 999
toc: true
---

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

____

Diferentes respostas seguem abaixo:
____

```c++
#include <bits/stdc++.h>
using namespace std;

class Solution {
  public:
    int BasicDataType(string s) {
       
        int size = s.size();
        // Se existe apenas 1 character ele será
        if(size==1) 
        {
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

```c++
#include <bits/stdc++.h>
using namespace std;

class Solution {
  public:
    int BasicDataType(string s) {
        // Digite aqui...
        int i;
        int n=s.size();
        int char_size=1;
        int float_size=4;
        int double_size=8;
        int integer_size=4;
        // Se existe apenas um caractere significa int ou char
        if(n==1)
        {
            if(isdigit(s[0]))
            {
                return integer_size;
            }
            else
            {
                return char_size;
            }
        }
        // Ou float e double
        for(i=0;i<s.size();i++)
        {
          if(s[i]=='.')
          {
              if(n-1-i>=6)
              {
                  return double_size;
              }
              else
              {
                  return float_size;
              }
          }
        }
        // Se não for float ou double será int;
        return integer_size;
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

```c++
#include <bits/stdc++.h>
using namespace std;

class Solution {
  public:
     int BasicDataType(string s) {
     int returnFloat = 0, returnDouble = 0, returnChar = 0, floatingPointIndex;
       // digite aqui...
       
       // se o comprimento da string for 1 e não for um dígito, o data type será um char
       if (s.length() == 1 && !isdigit(s[0]))
       {
           returnChar++;
       }
       
       // passe por todos os itens na string e veja se algum deles é um ponto
       for ( int i = 0; i < s.length(); i++)
       {
           if (s[i] == '.')
           {
               floatingPointIndex = i; // defina o index do ponto para a variável floatingPointIndex
               
               // verifique se o comprimento do subarray formado pelos itens após o ponto é menor que 6, 
               // mas maior que 0, o data type é float
               if (s.length() - 1 - floatingPointIndex > 0 && s.length() - 1 - floatingPointIndex < 6) 
               {
                   returnFloat++; 
                   break;
               }
               else 
               {
                   // se o comprimento do subarray formado pelos itens após o ponto for maior que 6, 
                   // o data type será double
                   returnDouble++;
               }
           }
       }
       
      if (returnChar != 0)
      {
          return sizeof(char);
      }
      else if (returnFloat != 0)
      {
          return sizeof(float);
      }
      else if (returnDouble != 0)
      {
          return sizeof(double);
      }
      else
      {
          // se nenhum data type definido corresponder ao input, o data type será int
          return sizeof(int);
      }
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

{{< /details >}}