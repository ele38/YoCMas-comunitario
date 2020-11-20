+++
title = "Queues (colas)"
author = ["Vicente Villarroel"]
draft = false
weight = 3006
+++

<div class="ox-hugo-toc toc">
<div></div>

<div class="heading">Table of Contents</div>

- [push (empujar)](#push--empujar)
- [front (frente)](#front--frente)
- [pop (quitar)](#pop--quitar)
- [empty (vacío)](#empty--vacío)
- [size (tamaño)](#size--tamaño)

</div>
<!--endtoc-->

La cola es una estructura de datos lineal al que sólo puedes acceder al primer elemento que fue insertado. Imagina una fila de una caja de un supermercado, por ejemplo.

{{< highlight cpp "linenos=table, linenostart=1" >}}
queue < int > colita;
{{< /highlight >}}


## push (empujar) {#push--empujar}

Añade un dato al final de la cola.

{{< highlight cpp "linenos=table, linenostart=2" >}}
colita.push(5);
colita.push(4);
colita.push(3);
colita.push(2);
colita.push(1);
{{< /highlight >}}


## front (frente) {#front--frente}

Lee el dato que está al frente de la cola.

{{< highlight cpp "linenos=table, linenostart=7" >}}
colita.front(); // Retorna 5, ya que fue lo primero que empujamos a la cola.
{{< /highlight >}}


## pop (quitar) {#pop--quitar}

Remueve el dato que está al frente de la cola

{{< highlight cpp "linenos=table, linenostart=8" >}}
colita.pop();   // Remueve el 5
colita.front(); // Retorna 4, ya que fue lo segundo que empujamos a la cola (y que ahora está primero).
{{< /highlight >}}


## empty (vacío) {#empty--vacío}

Retorna 1 si la cola está vacía, de lo contrario retorna 0.

{{< highlight cpp "linenos=table, linenostart=10" >}}
colita.empty(); // Retorna 1 ya que nuestra cola está vacía.
{{< /highlight >}}


## size (tamaño) {#size--tamaño}

Retorna el tamaño de nuestra cola.

{{< highlight cpp "linenos=table, linenostart=11" >}}
colita.size(); // Retorna 0 ya que nuestra cola no tiene datos.
{{< /highlight >}}
