---
title: "Tokens no C/C++"
description: "C++ Tokens são as menores unidades individuais de um programa."
lead: "C++ Tokens são as menores unidades individuais de um programa."
date: 2022-10-24T00:01:36-03:00
lastmod: 2022-10-24T00:01:36-03:00
draft: false
images: []
menu:
  docs:
    parent: ""
    identifier: "tokens-98c1d5af386781a5e3299146622e3925"
weight: 1004
toc: true
---
____

Um token é o menor elemento de um programa que é significativo para o compilador. Os tokens podem ser classificados da seguinte forma:

- Key-Words (Palavras-Chave)

- Identificadores

- Constantes

- Strings

- Símbolos Especiais

- Operadores

### KeyWords

1. __KeyWords__: Palavras-chave são palavras pré-definidas ou reservadas em uma linguagem de programação. Cada palavra-chave destina-se a executar uma função específica em um programa. Como as palavras-chave são nomes referenciados para um compilador, elas não podem ser usadas como nomes de variáveis porque, ao fazer isso, estamos tentando atribuir um novo significado à palavra-chave que não é permitido. Você não pode redefinir palavras-chave. No entanto, você pode especificar o texto a ser substituído por palavras-chave antes da compilação usando diretivas de pré-processador C/C++.

As palavras reservadas de C++ podem ser convenientemente colocadas em vários grupos. No primeiro grupo colocamos aqueles que também estavam presentes na linguagem de programação C e foram transportados para C++. Existem 32 delas, e aqui estão elas:

|          |        |          |          |
|:--------:|:------:|:--------:|:--------:|
|   auto   | double |    int   |  struct  |
|   break  |  else  |   long   |  switch  |
|   case   |  enum  | register |  typedef |
|   char   | extern |  return  |   union  |
|   const  |  float |   short  | unsigned |
| continue |   for  |  signed  |   void   |
|  default |  goto  |  sizeof  | volatile |
|    do    |   if   |  static  |   while  |

Enquanto em C++ existem 31 palavras-chave adicionais além das palavras-chave em C, elas são:

|              |           |                  |          |
|:------------:|:---------:|:----------------:|:--------:|
|      asm     |   export  |      private     |   true   |
|     bool     |   false   |     protected    |    try   |
|     catch    |   friend  |      public      |  typeid  |
|     class    |   inline  | reinterpret_cast | typename |
|  const_cast  |  mutable  |    static_cast   |   using  |
|    delete    | namespace |     template     |  virtual |
| dynamic_cast |    new    |       this       |  wchar_t |
|   explicit   |  operator |       throw      |          |

As 11 palavras reservadas no C++ a seguir não são essenciais quando o conjunto de caracteres ASCII padrão está sendo usado, mas foram adicionadas para fornecer alternativas mais legíveis para alguns dos operadores C++ e também para facilitar a programação com conjuntos de caracteres que não possuem caracteres necessários para C++ .

|        |        |       |        |       |        |
|:------:|:------:|:-----:|:------:|:-----:|:------:|
|   and  | bitand | compl | not_eq | or_eq | xor_eq |
| and_eq |  bitor |  not  |   or   |  xor  |        |

### Identificadores

2. __Identificadores__: são usados como terminologia geral para a nomeação de variáveis, funções e arrays. Esses são nomes definidos pelo usuário que consistem em uma sequência arbitrariamente longa de letras e dígitos com uma letra ou sublinhado(_) como primeiro caractere. Os nomes dos identificadores devem diferir em ortografia e maiúsculas e minúsculas de qualquer palavra-chave. Você não pode usar palavras-chave como identificadores; eles são reservados para uso especial. Uma vez declarado, você pode usar o identificador em instruções de programa posteriores para se referir ao valor associado. Um tipo especial de identificador, chamado rótulo de instrução, pode ser usado em instruções goto.

*Existem algunhas regras que devem ser seguidas quando nomeamos variáveis*:

- Eles devem começar com uma letra ou sublinhado(_).
- Eles devem consistir apenas em letras, dígitos ou sublinhado. Nenhum outro caractere especial é permitido.
- Não deve conter espaço em branco.
- Deve ter até 31 caracteres, pois apenas os primeiros 31 caracteres são significativos.

### Constantes

3. __Constantes__: são como variáveis normais. Mas, a única diferença é que seus valores não podem ser modificados pelo programa uma vez definidos. Constantes referem-se a valores fixos. Eles também são chamados de literais.

Sintaxe:

```c++
const data_type nome_da_variável; ou const data_type*nome_da_variável;
```
```c++
const [data_type] [nome_da_variável] = [valor];
```
Tipos de Constantes:

1. Constantes inteiras – Exemplo: 0, 1, 1218, 12482
2. Constantes Reais ou de Floating-point - Exemplo: 0,0, 1203,03, 30486,184
3. Constantes octais e hexadecimais – Exemplo: octal:$ (013)_8 = (11)_10 $, hexadecimais: $ (013)_16 = (19)_10 $
4. Constantes de caractere -Exemplo: 'a', 'A', 'z'
5. Constantes de string -Exemplo: "Aprendacpp"

Exemplo:

```c++
#include <iostream>
using namespace std;

int main()
{
    const int tamanho_maximo=100; // constante integer
    const char letras='A';       // constante de caractere
    const char titulo[]="aprendacpp.com"; // constante string
    const float temp=12.34; // constante float

    cout << "tamanho_maximo: " << tamanho_maximo << endl;
    cout << "letras: " << letras << endl;
    cout << "titulo: " << titulo << endl;
    cout << "temp: " << temp << endl;
    return 0;
}
```
Output:

```html
tamanho_maximo: 100
letras: A
titulo: aprendacpp.com
temp: 12.34
```
### Strings

4. __Strings__: nada mais são do que uma matriz de caracteres terminada com um caractere nulo (‘\0’). Este caractere nulo indica o final da string. Strings são sempre colocadas entre aspas duplas. Considerando que, um caractere é colocado entre aspas simples em C e C++.

Declaração de Strings:

- char caractere[20] = {'a','p','r','e','n','d','a','c','p','p','\0'};
- char string[20] = "aprendacpp";
- char string[] = "aprendacpp.com";

Quando declaramos char como "string[20]", 20 bytes de spaço na memória é alocado para armazenar os valores da string.

Quando declaramos char como "string[]", o espaço na memória será alocado conforme o requisito durante a execução do programa.

### Símbolos Especiais

5. __Símbolos Especiais__: Os seguintes símbolos especiais são usados em C/C++ tendo algum significado especial e, portanto, não podem ser usados para outros propósitos.[] () {}, ; * = #

- Colchetes [ ]: Os colchetes de abertura e fechamento são usados como referência de elemento de matriz. Estes indicam subscritos unidimensionais e multidimensionais.
- Parênteses ( ): Esses símbolos especiais são usados para indicar chamadas de função e parâmetros.
- Chaves { }: essas chaves de abertura e final marcam o início e o fim de um bloco de código contendo mais de uma instrução executável.
- Vírgula ( , ): É usada para separar mais de uma instrução como para separar parâmetros em chamadas de funções.
- Dois pontos( : ): É um operador que essencialmente invoca algo chamado lista de inicialização.
- Ponto e vírgula( ; ): É conhecido como terminador de instrução. Indica o fim de uma entidade lógica. É por isso que cada instrução individual deve ser terminada com um ponto e vírgula.
- Asterisco ( * ): É usado para criar uma variável ponteiro e para a multiplicação de variáveis.
- Operador de atribuição( = ): É utilizado para atribuir valores e para a validação da operação lógica.
- Pré-processador ( # ): é um processador de macro que é usado automaticamente pelo compilador para transformar seu programa antes da compilação real.

### Operadores

6. __Operadores__: Operadores são símbolos que acionam uma ação quando aplicados a variáveis e outros objetos. Os itens de dados sobre os quais os operadores atuam são chamados de operandos.
Dependendo do número de operandos sobre os quais um operador pode atuar, os operadores podem ser classificados da seguinte forma:

- Operadores Unários: Aqueles operadores que requerem apenas um único operando para atuar são conhecidos como operadores unários. Por exemplo, operadores de incremento e decremento.

- Operadores Binários: Aqueles operadores que requerem dois operandos para atuar são chamados de operadores binários. Eles podem ser classificados em :

1. Operadores aritméticos
2. Operadores Relacionais
3. Operadores lógicos
4. Operadores de Atribuição
5. Operador bitwise

- Operador Ternário: O operador que requer três operandos para atuar é chamado de operador ternário. Operador Condicional (?) também é chamado de operador ternário.
Sintaxe: (Expressão1)? expressão2: expressão3;

___

Por favor, escreva para o email: (__siteaprendacpp@gmail.com__) se você encontrar algo incorreto ou se quiser compartilhar mais informações sobre o tópico discutido acima.