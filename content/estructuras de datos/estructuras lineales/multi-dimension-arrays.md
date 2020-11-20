+++
title = "Arrays multidimensionales"
author = ["Vicente Villarroel"]
draft = false
weight = 3003
+++

<div class="ox-hugo-toc toc">
<div></div>

<div class="heading">Table of Contents</div>

- [Inicializar un arreglo multidimensional](#inicializar-un-arreglo-multidimensional)
- [Asignar valores en un arreglo multidimensional](#asignar-valores-en-un-arreglo-multidimensional)

</div>
<!--endtoc-->

Un array multidimensional es aquel que requiuere de más de un índice para ser llamado, como su nombre lo indica, es útil para cuando necesitamos acceder a datos que requieren más de una dimensión, como por ejemplo valores dentro de una malla. Otra forma de enternder los arrays multidimensionales es como un arreglo de arreglos (de arreglos de arreglos.. n veces, siendo n la cantidad de dimensiones). Los arreglos de 2 dimensiones también son conocidos como matrices.


## Inicializar un arreglo multidimensional {#inicializar-un-arreglo-multidimensional}

Para esto, hay que especificar el tamaño de cada dimensión del array. Notar que la regla de que empiezan en 0 y terminan en n-1 se sigue cumpliendo. Es posible asignarles valores predeterminados, pero creo que eso se va poniendo exponencialmente más psicópata a medida de que vas incrementando las dimensiones del array a crear, por lo que no lo voy a demostrar.

{{< highlight cpp "linenos=table, linenostart=1" >}}
int matriz[3][4];
int tridimensional[100][100][100];
{{< /highlight >}}


## Asignar valores en un arreglo multidimensional {#asignar-valores-en-un-arreglo-multidimensional}

Es muy similar a cómo se hace en un arreglo unidimensional, solo que se especifica cada índice.

{{< highlight cpp "linenos=table, linenostart=3" >}}
int n = 3, m = 5;
matriz[2][1] = 10;
tridimensional[n][m] = 4;
{{< /highlight >}}
