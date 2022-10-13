---
title: "Input/Output Báscio no C++"
description: ""
lead: ""
date: 2022-09-27T15:34:09-03:00
lastmod: 2022-09-27T15:34:09-03:00
draft: false
images: []
menu:
  docs:
    parent: ""
    identifier: "input-output-3059b16cf739ec6a788a8a7cf627ab32"
weight: 6
toc: true
---
____

O C++ vem com bibliotecas que nos fornecem muitas maneiras de realizar *Inputs* e *Outputs*, a entrada (input) e a saída (output) são executadas na forma de uma sequência de bytes ou mais comumente conhecida como **streams**.

- **Input Stream**: Se a direção do fluxo de bytes for do dispositivo (por exemplo, teclado) para a memória principal, esse processo é chamado de entrada (input).

- **Output Stream**: Se a direção do fluxo de bytes for oposta, ou seja, da memória principal para o dispositivo (tela de exibição), esse processo é chamado de saída (output).

Os arquivos de cabeçalho disponíveis em C++ para operações de entrada/saída são:

1. ***iostream***: Significa (standard input-output stream) fluxo de entrada-saída padrão. Este arquivo de cabeçalho contém definições de objetos como cin, cout, cerr, etc.

2. ***iomanip***: Significa (input-output manipulators) manipuladores de entrada-saída. Os métodos declarados nesses arquivos são usados para manipular fluxos. Este arquivo contém definições de setw, setprecision, etc.

3. ***fstream***: Este arquivo de cabeçalho descreve principalmente o fluxo de arquivos. É usado para lidar com os dados que estão sendo lidos de um arquivo como input ou dados e estão sendo gravados em outro arquivo como o de saída.

As duas instâncias em C++ **cout** e **cin** são usadas com muita frequência para fazer outputs e receber inputs, respectivamente. Esses dois são os métodos mais básicos de entrada e saída em C++. Para usar cin e cout em C++ deve-se incluir o arquivo de cabeçalho iostream no programa.
____

Neste artigo vamos focar nossa atenção aos objetos definidos no arquivo de cabeçalho iostream, como cin e cout.

### cout

- ***Standard output stream (cout)***: Normalmente o dispositivo de saída padrão é a tela de exibição. A instrução **cout** no C++ é a instância da classe **ostream**. Ele é usado para produzir uma saída no dispositivo padrão que geralmente é a tela do computador. Os dados necessários para serem exibidos na tela são inseridos no cout usando o operador de inserção (<<).

__Exemplo__:

```c++
#include<iostream>
using namespace std;

int main()
{
  // usamos char para declarar a variável string
  char exemplo[] = " Aprenda C++: ";

  // o operador de inserção << insere o valor da variável string exemplo no cout 
  cout << exemplo << " O grande website para aprender c++. ";

  return 0; 

}
```
__Output__:

```bash
 Aprenda C++:  O grande website para aprender c++.
```
No programa acima, o operador de inserção (<<) insere o valor da variável string **exemplo** seguido pela string “O grande website para aprender c++.s” no fluxo de saída padrão **cout** que então exibe a sáida output na tela.
____

### cin

- ***standard input stream (cin)***: Normalmente o dispositivo de entrada em um computador é o teclado. A instrução **cin** no C++ é a instância da classe **istream** e é usada para ler a entrada do dispositivo de entrada padrão que geralmente é um teclado. O operador de extração (>>) é usado junto com o objeto cin para leitura de entradas. O operador de extração extrai os dados do objeto cin que é inserido usando o teclado.

__Exemplo__:

```c++
#include<iostream>
using namespace std;

int main ()
{
  string nome;

  cout << " Digite o seu nome: ";
  cin >> nome;
  cout << " Seu nome: " << nome;

  return 0;
}
```
__Output__: 

```bash
Digite o seu nome: Cpp
Seu nome: Cpp
```
O programa acima pede ao usuário para inserir seu nome. O objeto cin está conectado ao dispositivo de entrada. A idade inserida pelo usuário é extraída do cin usando o operador de extração(>>) e os dados extraídos são então armazenados na variável *nome* presente no lado direito do operador de extração.
____

### cerr

- ***Un-buffered standard error stream (cerr)***: O fluxo de erro padrão sem buffer (cerr): No C++ é o fluxo de erro padrão usado para gerar os erros, esta também é uma instância da classe iostream. Como cerr em C++ não é armazenado em buffer, é usado quando é necessário exibir a mensagem de erro imediatamente. Não possui buffer para armazenar a mensagem de erro e exibi-la posteriormente. A principal diferença entre cerr e cout vem quando você deseja redirecionar a saída usando “cout” que é redirecionado para o arquivo, se você usar “cerr” o erro não é armazenado no arquivo. (Isso é o que significa sem buffer .. Ele não pode armazenar a mensagem).

__Exemplo__:

```c++
#include<iostream>
using namespace std;

int main()
{
  cerr << " Tivemos um erro. ";
  return 0;
}
```
__Output__:

```bash
Tivemos um erro.
```
____

### clog

- ***buffered standard error stream (clog)***: fluxo de erro padrão em buffer (clog), este também é uma instância da classe ostream e é usada para exibir erros, mas ao contrário de cerr, o erro é inserido primeiro em um buffer e é armazenado neste buffer até que não seja totalmente preenchido, ou o buffer não seja liberado explicitamente (usando *flush()*). A mensagem de erro também será exibida na tela.

__Exemplo__:

```c++
#include<iostream>
using namespace std;

int main()
{
  cerr << " Tivemos um erro. ";
  return 0;
}
```
__Output__:

```bash
Tivemos um erro.
```
____

Por favor, escreva para o email: (**siteaprendacpp@gmail.com**) se você encontrar algo incorreto ou se quiser compartilhar mais informações sobre o tópico discutido acima.