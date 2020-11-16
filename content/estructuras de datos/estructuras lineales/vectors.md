+++
title = "Vectores"
author = ["Vicente Villarroel"]
draft = false
weight = 3002
+++

<div class="ox-hugo-toc toc">
<div></div>

<div class="heading">Table of Contents</div>

- [Asignar un valor](#asignar-un-valor)
- [push back (empujar atrás)](#push-back--empujar-atrás)
- [pop back (quitar atrás)](#pop-back--quitar-atrás)
- [insert (insertar)](#insert--insertar)
- [erase (borrar)](#erase--borrar)

</div>
<!--endtoc-->

Los vectores son como arreglos, excepto de que el tamaño es dinámico, es decir, se puede cambiar.
Incluimos la librería:

{{< highlight cpp "linenos=table, linenostart=1" >}}
#include <vector>
{{< /highlight >}}

Inicializamos nuestro vector "vec":

{{< highlight cpp "linenos=table, linenostart=2" >}}
int n = 3;
vector < int > vec(n, 0); // Inicializa un vector de tamaño 3 con todos sus valores = 0. Tanto el tamaño como valor son opcionales.
{{< /highlight >}}


## Asignar un valor {#asignar-un-valor}

{{< highlight cpp "linenos=table, linenostart=4" >}}
vec[2] = 1; // Asigna el valor "1" al índice 2 (es decir, al 3er valor del vector)
{{< /highlight >}}


## push back (empujar atrás) {#push-back--empujar-atrás}

Si no sabemos el tamaño de nuestro vector, podemos simplemente usar push\_back(valor); para enviar es valor al final del vector.

{{< highlight cpp "linenos=table, linenostart=5" >}}
vec.push_back(1); // Inserta un 1 al final del vector
{{< /highlight >}}

Por ejemplo, se podría usar en un for, sin necesidad de inicializar el vector con una cantidad de valores.

{{< highlight cpp "linenos=table, linenostart=6" >}}
vector <int> vec2;
int n;
cin >> n;
for (int i = 0; i < n; ++i){
    int valor;
    cin >> valor;
    vec2.push_back();
}
{{< /highlight >}}


## pop back (quitar atrás) {#pop-back--quitar-atrás}

Elimina el último valor del vector.

{{< highlight cpp "linenos=table, linenostart=14" >}}
vec.pop_back(); // En este caso, elimina el 1
{{< /highlight >}}


## insert (insertar) {#insert--insertar}

Podemos insertar un valor entre dos indices de un vector. El problema de esto es que mueve todos los valores que estén más adelante, lo que es lento.

{{< highlight cpp "linenos=table, linenostart=15" >}}
vec.insert(vec.begin() + 2, 4); // Inserta el valor 4 al índice 2
{{< /highlight >}}


## erase (borrar) {#erase--borrar}

Borra un dato del vector. Al igual que el insert, tiene que mover todos los datos siguientes (esta vez a la derecha).

{{< highlight cpp "linenos=table, linenostart=16" >}}
vec.erase(vec.begin() + 2); // Elimina el valor con índice 2, en nuestro caso, el 4 que insertamos antes.
{{< /highlight >}}
