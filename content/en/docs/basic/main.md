---
title: "void main ou main()"
description: ""
lead: ""
date: 2022-09-27T15:25:43-03:00
lastmod: 2022-09-27T15:25:43-03:00
draft: false
images: []
menu:
  docs:
    parent: ""
    identifier: "main-65f3fd6f5de9cda024de65b87a1c64fc"
weight: 4
toc: true
---
___

{{< alert icon="💡" text="Por favor, Recarregue a página para ver os novos conteúdos." />}}

## É correto escrever void main() ou main() em C/C++?

Em C++ o tipo de retorno padrão de main é void, ou seja, *main()* não retornará nada. Mas, em C, o tipo de retorno padrão de main é int, ou seja, *main()* retornará um valor inteiro por padrão.

Em C *void main()* não tem uso definido e às vezes pode gerar resultados inúteis ou um erro. No entanto, *main()* é usado para denotar a função principal que não recebe argumentos e retorna um data type integer.

```c++
void main(){
  //
}
```
Uma implementação em conformidade aceita os formatos fornecidos abaixo:

```c++
int main(){
  //
}
```
e 

```c++
int main(int argc, char* argv[]){
  //
}
```

Um uso em conformidade pode fornecer mais versões de main(), mas todas elas devem ter o tipo de retorno *int*. O int retornado por main() é uma maneira de um programa retornar um valor para “o sistema” que o invoca. Em sistemas que não fornecem esse recurso, o valor de retorno é ignorado, mas isso não torna “void main()” legal no C++ ou C.

{{< alert icon="💡" text="Mesmo que seu compilador aceite void main(), evite-o, ou corra o risco de ser considerado ignorante por programadores C e C++. Em C++, main() não precisa conter uma instrução de retorno explícita. Nesse caso, o valor retornado é 0, o que signifca que a excução foi bem sucedida."/>}}

Exemplo:

```c++
#include<iostream>
using namespace std;

int main()
{
  cout << "Este programa retorna o valor integer 0\n";
}
```
Consequentemente:

```c++
#include<iostream>
using namespace std;

main() // o tipo de retorno padrão do main em c++ é int
{
  cout << "Um valor do tipo integer será retornado"; 

  return 0;
}
```
O código acima não tem erro. Se você escrever toda a função main() livre de erros sem um statement de retorno no final, o compilador adicionará automaticamente um statement de retorno com o tipo de dados apropriado no final do programa.

Resumindo o que foi dito acima, nunca é uma boa ideia usar ***void main()*** ou simplesmente ***main()***, pois não está de acordo com os padrões. Embora pode ser permitido por alguns compiladores.
___

Se existe alguma inconsistência ao foi descrito algo incorreto acima, por favor vá até __Help__ e nos envie seu comentário para que tudo que foi dito esteja claro e bem definido.