---
title: "<bits/stdc++.h> No C++"
description: ""
lead: ""
date: 2022-10-23T22:55:45-03:00
lastmod: 2022-10-23T22:55:45-03:00
draft: false
images: []
menu:
  docs:
    parent: ""
    identifier: "bits-stdc-e4d5c32579dafb5001e30a7dbbe9161d"
weight: 1003
toc: true
---
____

É basicamente um arquivo de cabeçalho que inclui todas as bibliotecas padrão. Em concursos de programação, usar este arquivo é uma boa ideia, quando você quer reduzir o tempo gasto em tarefas; especialmente quando sua classificação é sensível ao tempo.

Em concursos, as pessoas se concentram mais em encontrar o algoritmo certo para resolver um problema do que em engenharia de software. Do ponto de vista da engenharia de software, é uma boa ideia minimizar o *include*. Se você usá-lo, na verdade, será incluido muitos arquivos, dos quais seu programa pode não precisar, aumentando assim o tempo de compilação e o tamanho do programa desnecessariamente.

__Desvantagens do bits/stdc++.h__

- bits/stdc++.h é um arquivo de cabeçalho não padrão da biblioteca GNU C++. Portanto, se você tentar compilar seu código com algum compilador diferente do GCC, ele poderá falhar.

- Usá-lo incluiria muitos arquivos desnecessários e aumentaria o tempo de compilação.

- Além disso, mesmo se houvesse algum cabeçalho abrangente no padrão, você gostaria de evitá-lo em vez de cabeçalhos específicos, já que o compilador precisa ler e analisar todos os cabeçalhos incluídos (incluindo cabeçalhos incluídos recursivamente) toda vez que unidade é compilada.

__Vantagens do bits/stdc++.h__

- Em concursos, usar este arquivo é uma boa ideia, quando você quer reduzir o tempo gasto em tarefas; especialmente quando sua classificação é sensível ao tempo.

- Isso também reduz todas as tarefas de escrever todos os arquivos de cabeçalho necessários.

- Você não precisa se lembrar de todo o STL do GNU C++ para cada função que você usa.

Exemplo:

Por exemplo, para usar a função sqrt( ), com o arquivo de cabeçalho __bits/stdc++.h__ não precisamos escrever o arquivo de cabeçalho __cmath__ no código.

```c++
#include <bits/stdc++.h>
using namespace std;

int main() {

	cout << sqrt(100);
	return 0;
}
```
Output:

```html
10
```
Mas se usarmos o arquivo de cabeçalho  __iostream__ , temos que escrever o arquivo de cabeçalho __cmath__ para executar a função sqrt(), caso contrário, o compilador mostra que 'sqrt' não foi declarado neste escopo.

```c++
#include <iostream>
#include <cmath>
using namespace std;

int main() {

	cout << sqrt(100);
	return 0;
}
```
Assim, fica a critério do usúario usá-lo e economizar tempo para escrever os include necessários ou, economizar tempo de compilação em não usá-lo e ter que escrever os arquivos de cabeçalho necessários. 
____

Por favor, escreva para o email: (__siteaprendacpp@gmail.com__) se você encontrar algo incorreto ou se quiser compartilhar mais informações sobre o tópico discutido acima.