+++
title = "Stacks (pilas)"
author = ["Comunidad YoC+"]
draft = false
weight = 3005
+++

<div class="ox-hugo-toc toc">
<div></div>

<div class="heading">Table of Contents</div>

- [push (empujar)](#push--empujar)
- [top (cima)](#top--cima)
- [pop (quitar)](#pop--quitar)
- [empty (vacío)](#empty--vacío)
- [size (tamaño)](#size--tamaño)

</div>
<!--endtoc-->

La pila es una estructura de datos lineal al que sólo puedes acceder al último elemento que fue insertado. Imagina una pila de platos, por ejemplo.

{{< highlight cpp "linenos=table, linenostart=1" >}}
stack < int > pilita;
{{< /highlight >}}


## push (empujar) {#push--empujar}

Empuja un dato a la cima de la pila.

{{< highlight cpp "linenos=table, linenostart=2" >}}
pilita.push(8); // Empuja un 8 a la cima de la pila.
{{< /highlight >}}


## top (cima) {#top--cima}

Lee lo que hay en la cima de la pila.

{{< highlight cpp "linenos=table, linenostart=3" >}}
pilita.top(); // Retorna el 8.
{{< /highlight >}}


## pop (quitar) {#pop--quitar}

Remueve el dato de la cima de la pila.

{{< highlight cpp "linenos=table, linenostart=4" >}}
pilita.pop(); // Remueve el 8.
{{< /highlight >}}


## empty (vacío) {#empty--vacío}

Retorna 1 si la pila está vacía, de lo contrario retorna 0.

{{< highlight cpp "linenos=table, linenostart=5" >}}
pilita.empty(); // Retorna 1 ya que nuestra pila está vacía.
{{< /highlight >}}


## size (tamaño) {#size--tamaño}

Retorna el tamaño de nuestra pila.

{{< highlight cpp "linenos=table, linenostart=6" >}}
pilita.size(); // Retorna 0 ya que nuestra pila no tiene datos.
{{< /highlight >}}
