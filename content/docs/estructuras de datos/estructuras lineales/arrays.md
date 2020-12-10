+++
title = "Arrays (arreglos)"
author = ["Comunidad YoC+"]
draft = false
weight = 3002
+++

<div class="ox-hugo-toc toc">
<div></div>

<div class="heading">Table of Contents</div>

- [Inicialización](#inicialización)
- [Leer el valor de un arreglo](#leer-el-valor-de-un-arreglo)
- [Asignar valores a un arreglo](#asignar-valores-a-un-arreglo)

</div>
<!--endtoc-->

Los arrays son conjuntos de datos que se almacenan en memoria de manera contigua usando el mismo nombre. Se usan índices para diferenciar los distintos valores del arreglo.
Para crear una arreglo es necesario saber la cantidad de elementos que van a componer nuestro arreglo, pues la cantidad de elementos no se puede cambiar.
Una cosa muy importante que al principio uno suele olvidar es que los índices de los arreglos parten en 0. Es decir, un arreglo de tamaño n puede tomar índices desde el 0 hasta el n-1.


## Inicialización {#inicialización}

Hay dos formas de inicializar un array, especificando su tamaño o llenandolo con valores por defecto.


### Inicializar un array por su tamaño {#inicializar-un-array-por-su-tamaño}

Para inicializar un array por su tamaño, lo único que hay que especificar es el nombre de la variable y colocar entre "[]" el tamaño de nuestro arreglo. Recordar que como los arrays parten en 0, el valor máximo que podremos acceder será el tamaño del array menos 1.

{{< highlight cpp "linenos=table, linenostart=1" >}}
int arreglo[38]; // Inicializar un arreglo de ints de tamaño 38.
{{< /highlight >}}


### Inicializar un array con valores por defecto {#inicializar-un-array-con-valores-por-defecto}

Para inicializar un array con valores por defecto, no es necesario especificar el tamaño de nuestro array, pues este está implícito en la cantidad de valores que introducimos.

{{< highlight cpp "linenos=table, linenostart=2" >}}
int arreglo2[] = {3, 6, 2, 1};
{{< /highlight >}}


## Leer el valor de un arreglo {#leer-el-valor-de-un-arreglo}

Para leer un valor de nuestro arreglo, solo hay que especificar el nombre del arreglo y su índice. Notar que sólo se puede acceder a un valor de un arreglo a la vez.

```cpp
arreglo2[3]; // Retorna 1
```


## Asignar valores a un arreglo {#asignar-valores-a-un-arreglo}

Para esto, hay que especificar la variable, el índice al cuál acceder y especificar su nuevo valor. Recordar que el valor del índice puede ser una variable, pero que no puede estar fuera del rango del tamaño de nuestro arreglo.

{{< highlight cpp "linenos=table, linenostart=3" >}}
arreglo2[3] = 5; // El indice 3 de nuestro arreglo, ahora tiene el valor 3
{{< /highlight >}}
