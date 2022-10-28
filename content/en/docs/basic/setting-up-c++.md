---
title: "Configurando o ambiente de desenvolvimento C++"
description: "Antes de começarmos a programar com C++ precisaremos de um ambiente a ser configurado em nosso computador local para compilar e executar nossos programas com sucesso. Se você não deseja configurar um ambiente local, você também pode usar IDEs online para compilar seu programa."
lead: "Antes de começarmos a programar com C++ precisaremos de um ambiente a ser configurado em nosso computador local para compilar e executar nossos programas com sucesso. Se você não deseja configurar um ambiente local, você também pode usar IDEs online para compilar seu programa."
date: 2022-09-27T15:01:50-03:00
lastmod: 2022-09-27T15:01:50-03:00
draft: false
images: []
menu:
  docs:
    parent: ""
    identifier: "setting-up-c++-cf3fdbe7ccc66d43468a3d83aac3f8cc"
weight: 2
toc: true
---
____

{{< alert icon="💡" text="Por favor, Recarregue a página para ver os novos conteúdos." />}}

__Usando IDE online__: IDE significa ambiente de desenvolvimento integrado. Existem muitos IDEs online disponíveis que você pode usar para compilar e executar seus programas facilmente sem configurar um ambiente de desenvolvimento local.

Recomendamos que você use o [GeeksforGeek IDE](https://ide.geeksforgeeks.org/).

### Configurando um ambiente local

 Para configurar seu próprio ambiente de desenvolvimento pessoal em sua máquina local, você precisa instalar dois softwares importantes:

 1. **Editor de texto**: Usaremos editores de texto para digitar nossos programas C++. A extensão normal de um arquivo de texto é (.txt), mas um arquivo de texto contendo um programa C++ deve ser salvo com a extensão '.CPP' ou '.C'. Arquivos que terminam com a extensão '.CPP' e '.C' são chamados de arquivos de código-fonte e devem conter código-fonte escrito em linguagem de programação C++. Essas extensões ajudam o compilador a identificar que o arquivo contém um programa C++. Antes de começar a programar com C++, deve-se ter um editor de texto instalado para escrever programas.

2. **Compilador C++:** Depois de instalar o editor de texto e digitar e salvar seu programa em um arquivo com extensão ‘.CPP’, você precisará de um compilador C++ para compilar este arquivo. Um compilador é um programa de computador que converte linguagem de alto nível em linguagem de baixo nível compreensível por máquina. Em outras palavras, podemos dizer que ele converte o código-fonte escrito em uma linguagem de programação em outra linguagem de computador que o computador entende. Para compilar um programa C++, precisaremos de um compilador C++ que converterá o código-fonte escrito em C++ em códigos de máquina. Abaixo estão os detalhes sobre como configurar o compilador em diferentes plataformas.

### Linux

Vamos instalar o compilador GNU GCC no Linux. Para instalar e trabalhar com o compilador GCC em sua máquina Linux, siga os passos abaixo:

- Você deve primeiro executar os comandos abaixo na janela do terminal Linux:

```bash
sudo apt-get update
sudo apt-get install gcc
sudo apt-get install g++
```
- Este comando instalará o compilador GCC em seu sistema. Você também pode executar o comando abaixo:

```bash
sudo apt-get install build-essential
```
- Este comando instalará todas as bibliotecas necessárias para compilar e executar um programa C++.

- Após concluir os passos acima, você deve verificar se o compilador GCC está instalado corretamente em seu sistema ou não. Para fazer isso, você deve executar o comando abaixo fornecido no terminal Linux:

```bash
g++ --version
```
- Se você concluiu as duas etapas acima sem erros, seu ambiente Linux está configurado e pronto para ser usado para compilar programas C++.

- Escreva seu programa em um arquivo de texto e salve-o com qualquer nome de arquivo e extensão .CPP. Você pode escrever um programa para exibir “Hello World” e salvar em um arquivo com o nome de arquivo “helloworld.cpp” na área de trabalho.

- Agora você precisa abrir o terminal Linux e ir para o diretório onde salvou seu arquivo (desktop). Então você tem que executar o comando abaixo para compilar seu arquivo:

```bash
g++ nomedoarquivo.cpp -o outro nome
```
- nomedoarquivo.cpp é o nome do arquivo de código-fonte. No nosso caso, o nome é “helloworld.cpp” e *outro nome* pode ser qualquer nome de sua escolha. Este nome será atribuído ao arquivo executável que é criado pelo compilador após a compilação. No nosso caso, escolhemos qualquer nome para ser “hello”.

```bash
g++ helloworld.cpp -o hello
```
- Depois de executar o comando acima, você verá que um novo arquivo é criado automaticamente no mesmo diretório onde você salvou o arquivo de origem e o nome desse arquivo é o nome que você escolheu como *outro nome*.

Agora, para executar seu programa, você deve executar o comando abaixo:

```bash
./hello
```
- Este comando executará seu programa na janela do terminal.

### Windows

Existem muitos IDEs disponíveis para o sistema operacional Windows que você pode usar para trabalhar facilmente com a linguagem de programação C++.

Um dos mais populares hoje em dia é o [Visual Studio Code](https://code.visualstudio.com/) e recomendamos que você use ele. Faça o download e prosiga com a instalação no seu computador.

Você também vai precisar de um compilador, recomendamos que você uso o [MinGW](https://sourceforge.net/projects/mingw/). Faça o download e prosiga com a instalação normalmente.

Depois de instalar ambos, você vai precisar idicionar o MinGW no seu *PATH*, seguia os passos abaixo para fazê-lo:

- Vá até este > Este Computador > Disco Local (C:) > MinGW > bin - (***Copie este caminho***).

- Agora vá até a barra de pesquisa e digite ***variáveis de ambiente***, na janela que abrir, logo abaixo click em *Variáveis de Ambiente*.

- Click em **Path** -> **Editar** -> **Novo** -> Cole o *caminho* que você copiou anteriormente -> e **OK**.

- Vá até seu Visual Studio Code -> Extensões (**Ctrl+Shift+X**) -> e instale a extensão (**C/C++ Compile Run**). 

- Crie um arquivo.**cpp** e digite um programa básico em C++. Após fazer isso, você pode pressionar a tecla ***F6***. Se seu programa tiver um erro, será exibo no *terminal* integrado do Visual Studio, se estiver correto, uma janela do *Prompt de comando* será aberta com o *Output* do seu programa. Assim, você já pode começar a programar em C++.
____