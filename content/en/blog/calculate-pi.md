---
title: "Formas de calcular Pi"
description: ""
excerpt: ""
date: 2022-10-09T14:03:27-03:00
lastmod: 2022-10-09T14:03:27-03:00
draft: false
weight: 50
images: []
categories: ["math", "python", "c++"]
tags: ["matemática"]
contributors: ["Moises Nunes"]
pinned: false
homepage: false
---
## Métodos de como calcular Pi usando diferentes algoritimos

Antes de calcularmos $\pi$ precisamos provar que ele é irracional, o que significa que ele não é um número inteiro dividido por outro número inteiro. Na verdade, os dígitos de $\pi$ são extremamente aleatórios - se você não soubesse que eles eram os dígitos de $\pi$, eles seriam perfeitamente aleatórios.

Supunha que $\pi=a/b$, o quociente de inteiros positivos. Definimos os polinômios:
$$
\begin{equation*}
    f(x) = \frac{x^n(a-bx)^n}{n!},
\end{equation*}
$$

$$
\begin{equation*}
    F(x) = f(x) - f{^2}(x) + f{^4}(x) - ... + (-1)^n f^{2n}(x),
\end{equation*}
$$