---
title: "Pré-processadores no C++"
description: "Como o nome sugere, os pré-processadores são programas que processam nosso código-fonte antes da compilação. Existem várias etapas envolvidas entre escrever um programa e executar um programa em C/C++. Vamos dar uma olhada nessas etapas antes de começarmos a aprender sobre pré-processadores."
lead: "Como o nome sugere, os pré-processadores são programas que processam nosso código-fonte antes da compilação. Existem várias etapas envolvidas entre escrever um programa e executar um programa em C/C++. Vamos dar uma olhada nessas etapas antes de começarmos a aprender sobre pré-processadores."
date: 2022-09-27T15:36:44-03:00
lastmod: 2022-09-27T15:36:44-03:00
draft: false
images: []
menu:
  docs:
    parent: ""
    identifier: "preprocessors-5f45eb3ecc590a3f15960739b9b3ee1d"
weight: 8
toc: true
---
____

## Conceitos Básicos dos Pré-Processadores

![img](./preprocessor-compiler.jpg)

Você pode ver as etapas intermediárias no diagrama acima: o código fonte escrito pelo programador é armazenado primeiro em um arquivo, podemos chama-lá de “programa.c”, este arquivo é então processado por pré-processadores e um arquivo de código fonte expandido é gerado chamado “programa.i”. Depois, este arquivo expandido é compilado pelo compilador e um arquivo de código objeto é gerado chamado “programa.obj”. Por fim, o vinculador vincula esse arquivo de código objeto ao código objeto das funções da biblioteca para gerar o arquivo executável “programa.exe”.

Os programas feitos para os pré-processadores fornecem diretivas de que dizem ao compilador para pré-processar o código-fonte antes de ele ser compilado. Todas essas diretivas de pré-processador começam com um símbolo '#' (hash). O símbolo '#' indica que qualquer instrução que comece com um '#' irá para o programa do pré-processador para ser executada. Exemplos de algumas diretivas de pré-processador são: *#include*, *#define*, *#ifndef*, etc. Lembre-se de que o símbolo '#' fornece apenas um caminho para o pré-processador, e um comando como include é processado pelo programa do pré-processador. Por exemplo, #include incluirá código extra em seu programa. Podemos colocar essas diretivas de pré-processador em qualquer lugar do nosso programa.

### Os quatro tipos principais de diretivas dos pré-processadores

1. Macros

2. Inclusão de arquivo

3. Compilação Condicional

4. Outras diretivas

Vamos aprender cada uma delas em detalhes.

### 1. Macros

Macros são partes de um código em um programa que recebe algum nome. Sempre que esse nome é encontrado pelo compilador, o compilador substitui o nome pela parte real do código. A diretiva ‘*#define*’ é usada para definir uma macro. Vamos agora entender a definição de macro com a ajuda de um programa:

```c++
#include<iostream>

// definição da macro
#define LIMITE 5
int main()
{
  // Criando um loop com limite 5
  for (int i = 0; i < LIMITE; i++){
    std:: cout << i << "\n";
  }
  return 0;
}
```
Output:
```bash
0
1
2
3
4
```
No programa acima, quando o compilador executa a palavra *LIMITE*, ele a substitui com o número 5. Dessa forma, A palavra 'LIMITE' na definição das macros é chamada de *macro template* e o número '5' é a *macro expansion*.

{{< alert icon="💡" text="Não precisamos colocar ponto e vírgula (;) no final da definição da macro." />}}

### 1.2 Macros com Argumentos

Também podemos passar argumentos ou parâmetros para as macros, elas funcionam de forma similar as funções no C++. Vamos entender com um programa:

```c++
#include<iostream>

// macros com parâmetros
#define AREA(l, b) (l * b)
int main()
{
  int l1 = 10, l2 = 5, area;

  area = AREA(l1, l2);

  std::cout << "Area do retangulo: " << area;

  return 0;
}
```
Output:

```c--
Area do retangulo: 50
```
Podemos ver no programa acima que sempre que o compilador encontra AREA(l, b) ele a substitui pela instrução (l * b). Não apenas isso, mas os valores passados para o modelo de macro AREA(l, b) também serão substituídos na instrução (l * b). Portanto, AREA(10, 5) será igual a 10 * 5.

### 2. Inclusão de arquivo

Esse tipo de diretiva de pré-processador informa ao compilador para incluir um arquivo no código-fonte. Existem dois tipos de arquivos que podem ser incluídos pelo usuário no programa:

### 2.1 Header Files or Arquivos de Cabeçalho:

Esses arquivos contêm definições de funções pré-definidas como *printf()*, *scanf()*, etc. Diferentes funções podems ser declaradas em diferentes header files. Por exemplo, as funções padrão de input e output estão no 'iostream', enquanto as funções que executam operações de string estão no arquivo 'string'.

Sintaxe:

```c--
#include< nome_do_arquivo >
```
Os colchetes '<' e '>' dizem ao compilador para procurar o arquivo no diretório do padrão.

### 2.2 Arquivos Definidos Pelo Usuário

Quando um programa se torna muito grande, é uma boa prática dividi-lo em arquivos menores e incluí-los sempre que necessário. Esses tipos de arquivos são arquivos definidos pelo usuário. Assim, esses arquivos podem ser incluídos como:

```c--
#include"nomedoarquivo"
```
As aspas "" dizem ao compilador para procurar o arquivo no diretório atual do programa.

### 3. Compilação Condicional

As diretivas de compilação condicional são um tipo de diretiva que ajuda a compilar uma parte específica do programa ou pular a compilação de alguma parte específica do programa com base em algumas condições. Isso pode ser feito com a ajuda dos dois comandos de pré-processamento '***ifdef***' e '***endif***'.

Sintaxe

```c--
#ifdef nome_da_macro
  declaração1;
  declaração2;
  declaração3;
  .
  .
  .
  declaraçãoN;
#endif
```