---
title: "Data Types no C++"
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
____
## C++ Data Types

Todas as variáveis usam data type durante sua declaração para restringir o tipo de dados que serão armazenados. Portanto, podemos dizer que os data type são usados para informar às variáveis o que elas podem armazenar ou o tipo de dados que elas podem armazenar. Sempre que uma variável é definida em C++ o compilador aloca alguma memória para essa variável com base no data type com o qual ela é declarada, cada data type requer uma quantidade diferente de memória.

O C++ suporta uma ampla variedade de data types e o programador pode selecionar as que sejam mais apropriadas as necessidades do seu programa. Os data types especificam o tamanho e os tipos de valor a serem armazenados. No entanto, a representação de armazenamento e as instruções de máquina para manipular cada tipo de dados diferem de equipamento para equipamento, embora as instruções do C++ sejam idênticas em todas as máquinas.

Os data types que o C++ suporta:

- Primary or Built in or Fundamental data type - Data type primário, integrado ou fundamental.

- Derived data type - data type derivados dos primary ou fundamental.

- User defined data types - data types definidos pelo usuário.

|                       | Data Type No C++ |                     |
|:---------------------:|:----------------:|:-------------------:|
|   **1. Fundamental**  |  **2. Derived**  | **3. User-Defined** |
|        Integer        |     Function     |        Class        |
|       Character       |       Array      |      Structure      |
|        Boolean        |      Pointer     |        Union        |
|     Floating Point    |     Reference    |         Enum        |
| Double Floating Point |                  |       Typedef       |
|          Void         |                  |                     |
|     Wide Character    |                  |                     |

## Fundamental DataTypes 

Vamos analisar em detalhes cada um deles:

1. __Primary__ ou __Primitive__ data types: Esses data types são internos (built-in) ou predefinidos e podem ser usados diretamente pelo usuário para declarar variáveis. Por exemplo: *int*, *char*, *float*, *bool*, etc. Data types primitivos no C++ são:

- __Integer__: A key-word usada para tipos de dados integer (*inteiros*) é __int__. Os inteiros normalmente exigem 4 bytes de espaço de memória e variam de -2,147,483,648 a 2,147,483,647.

- __Character__: O data type character é usado para armazenar caracteres. A key-word usada para o tipo de dados de caractere é __char__. Character normalmente requerem 1 byte de espaço de memória e variam de -128 a 127 ou 0 a 255.

- __Boolean__: O data type boolean é usado para armazenar valores booleanos ou lógicos. Uma variável booleana pode armazenar *true* ou *false*. A key-word usada para o tipo de dados Boolean é __bool__.

- __Floating Point__: O data type floating-point é usado para armazenar valores de precisão simples ou valores decimais. A key-word usada para o tipo de dados floating point é __float__. Variáveis float normalmente requerem 4 bytes de espaço de memória.

- __Double Floating Point__: Como o nome sugere, o data type bouble floating point é usado para armazenar valores de precião duplos ou valores decimais. A key-word para o double floating point é __double__. Este data type normalmente requer 8 bytes de memória.

- __Valueless or Void__: Void significa sem valor. O tipo de dados void representa uma entidade sem valor e portanto, é usado para aquelas funções que não retornam um valor.

- __Wide Character__: O data type wide character também é um tipo de dados de caracteres, mas ele tem um tamanho maior que o tipo de dados normal de 8 bits. Representado por __wchar_t__. Geralmente tem 2 ou 4 bytes de memória.

O tamanho das variáveis pode ser diferente dos mostrados acima, dependendo do compilador e do computador que você está usando.

Para saber o número de bytes ocupado por uma variável ou data type na memória do computador usamos o operador __sizeof__. Por exemplo:

```c++
int m, x[50];
cout << sizeof(m);
```
Retorna 4 que é o número de bytes ocupado pelo data type __integer__ da variável m.

```c++
int m, x[50];
cout << sizeof(x);
```
Retorna 200 que é número de bytes ocupado pelo array integer da variável x.

O exemplo a seguir mostrará o correto número de bytes que os data types ocupam na mémoria do seu computador.

```c++
#include<iostream>
using namespace std;

int main()
{
    cout << "O tamanho de Int: " << sizeof(int) << endl;
    cout << "O tamanho de Char: " << sizeof(char) << endl;
    cout << "O tamanho de Bool: " << sizeof(bool) << endl;
    cout << "O tamanho de Float: " << sizeof(float) << endl;
    cout << "O tamanho de Double: " << sizeof(double) << endl;
    cout << "O tamanho de Wchar_t: " << sizeof(wchar_t) << endl;

    return 0;
}
```
____

### Datatype Modifiers (Modificadores de data types)

Como o nome sugere, os modificadores de tipo de dados são usados com os **tipos de dados Primarios** para modificar o *comprimento* dos dados que um determinado data type pode conter.

|                |  Modificadores No C++ |      |             |
|:--------------:|:---------------:|:----------:|-------------|
|  **_Signed_**  |  **_Unsigned_** | **_Long_** | **_Short_** |
|     Integer    |     Integer     |   Integer  |   Integer   |
|      Char      |       Char      |   Double   |             |
| Long - prefixo | Short - prefixo |            |             |

Resumindo os datatype modifiers no C++ são:

__Signed__

__Unsigned__

__Long__

__Short__

_____

A tabela abaixo resume o tamanho modificado dos datatypes e o intervalo de tipos de dados primitivo quando combinados com os modificadores de type:

|     **_Data Type_**    | **_Tamanho (em bytes)_** |         **_Intervalo_**         |
|:----------------------:|:------------------------:|:-------------------------------:|
|        short int       |             2            |         -32,768 - 32,767        |
|   unsigned short int   |             2            |            0 - 65,535           |
|      unsigned int      |             4            |        0 - 4,294,967,295        |
|           int          |             4            |  -2,147,483,648 - 2,147,483,648 |
|        long int        |             4            |  -2,147,483,648 - 2,147,483,648 |
|    unsigned long int   |             4            |        0 - 4,294,967,295        |
|      long long int     |             8            |       -(2^63) to (2^63)-1       |
| unsigned long long int |             8            | 0 to 18,446,744,073,709,551,615 |
|       signed char      |             1            |             0 to 255            |
|          float         |             4            |                                 |
|         double         |             8            |                                 |
|       long double      |            12            |                                 |
|         wchar_t        |          2 ou 4          |         1 wide character        |

{{<  alert icon="⚠️" text="Os valores acima podem variar de compilador para compilador. No exemplo acima, consideramos o GCC de 32 bits." />}}
____

{{< alert icon="💡" text="Se você estiver confuso com o que estes data types significam, não se preocupe! Estamos apenas criando os fundamentos necessários sobre o C++. Precisaremos saber os data types corretamente para podermos depois declarar as variáveis sem erros. Sendo assim, a medida que você avançar com o C++, você pode voltar e rever com mais calma todos os data types e o seu correto uso." />}}

____

### Resumo 

C++ fornece um conjunto de data types. Cada variável deve ter um type. O tipo determina a quantidade de memória alocada para a variável, o intervalo de valores que podem ser atribuídos a ela e o tipo de operações que podem ser aplicadas a ela. O tamanho dos tipos depende da implementação, ou seja, pode variar entre os diferentes sistemas.

Os tipos __char__, __short__, __int__ e __long__ são usados para armazenar valores integer, que podem ser signed or unsigned. Se adicionarmos a palavra __unsigned__ a variável não possui sign bit e pode armazenar apenas valores positivos ou zero. A palavra __int__ pode ser omitida, por exemplo, __long__ em vez de __long int__. Além disso, as palavras podem ser misturadas em qualquer ordem, por exemplo, a declaração __unsigned long int a;__ é o mesmo que __int long unsigned a;__.

Com exceção do tipo __char__, todos os outros tipos são signed por padrão.

Os caracteres são representados por códigos numéricos específicos. O tipo __char__ é normalmente usado para armazenar os códigos numéricos dos caracteres do conjunto básico, como o conjunto ASCII (por exemplo, ele inclui caracteres que aparecem no teclado, como dígitos, letras, sinais de pontuação, …). O tipo __wchar_t__ é usado para armazenar os códigos numéricos dos caracteres de um conjunto maior, como o Unicode.

O tipo __bool__ tem dois valores possíveis, __true__ e __false__. Normalmente, uma variável __bool__ é usada para armazenar o resultado de uma ação, como se um valor é encontrado em uma array ou não.

Os tipos __float__, __double__ e __long double__ são usados para armazenar valores com uma parte fracionária, ou seja, números __floating-point__. Ao contrário dos integer types, os floating-point são sempre signed. Embora o tipo __long double__ normalmente forneça a mais alta precisão, raramente é usado porque a precisão dos tipos __float__ e __double__ geralmente é suficiente.
_____

A seguir vamos estudar os __Tipos de Dados Derivados__.

____