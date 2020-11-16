+++
title = "Estructuras lineales"
author = ["Vicente Villarroel"]
draft = false
weight = 2001
+++

<div class="ox-hugo-toc toc">
<div></div>

<div class="heading">Table of Contents</div>

- [Acerca de](#acerca-de)
- [Vectores](#vectores)
- [Stacks (pilas)](#stacks--pilas)
- [Queues (colas)](#queues--colas)

</div>
<!--endtoc-->


## Acerca de {#acerca-de}

Rellenar página


## Vectores {#vectores}

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


### Asignar un valor {#asignar-un-valor}

{{< highlight cpp "linenos=table, linenostart=4" >}}
vec[2] = 1; // Asigna el valor "1" al índice 2 (es decir, al 3er valor del vector)
{{< /highlight >}}


### push back (empujar atrás) {#push-back--empujar-atrás}

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


### pop back (quitar atrás) {#pop-back--quitar-atrás}

Elimina el último valor del vector.

{{< highlight cpp "linenos=table, linenostart=14" >}}
vec.pop_back(); // En este caso, elimina el 1
{{< /highlight >}}


### insert (insertar) {#insert--insertar}

Podemos insertar un valor entre dos indices de un vector. El problema de esto es que mueve todos los valores que estén más adelante, lo que es lento.

{{< highlight cpp "linenos=table, linenostart=15" >}}
vec.insert(vec.begin() + 2, 4); // Inserta el valor 4 al índice 2
{{< /highlight >}}


### erase (borrar) {#erase--borrar}

Borra un dato del vector. Al igual que el insert, tiene que mover todos los datos siguientes (esta vez a la derecha).

{{< highlight cpp "linenos=table, linenostart=16" >}}
vec.erase(vec.begin() + 2); // Elimina el valor con índice 2, en nuestro caso, el 4 que insertamos antes.
{{< /highlight >}}


## Stacks (pilas) {#stacks--pilas}

La pila es una estructura de datos lineal al que sólo puedes acceder al último elemento que fue insertado. Imagina una pila de platos, por ejemplo.

{{< highlight cpp "linenos=table, linenostart=1" >}}
stack < int > pilita;
{{< /highlight >}}


### push (empujar) {#push--empujar}

Empuja un dato a la cima de la pila.

{{< highlight cpp "linenos=table, linenostart=2" >}}
pilita.push(8); // Empuja un 8 a la cima de la pila.
{{< /highlight >}}


### top (cima) {#top--cima}

Lee lo que hay en la cima de la pila.

{{< highlight cpp "linenos=table, linenostart=3" >}}
pilita.top(); // Retorna el 8.
{{< /highlight >}}


### pop (quitar) {#pop--quitar}

Remueve el dato de la cima de la pila.

{{< highlight cpp "linenos=table, linenostart=4" >}}
pilita.pop(); // Remueve el 8.
{{< /highlight >}}


### empty (vacío) {#empty--vacío}

Retorna 1 si la pila está vacía, de lo contrario retorna 0.

{{< highlight cpp "linenos=table, linenostart=5" >}}
pilita.empty(); // Retorna 1 ya que nuestra pila está vacía.
{{< /highlight >}}


### size (tamaño) {#size--tamaño}

Retorna el tamaño de nuestra pila.

{{< highlight cpp "linenos=table, linenostart=6" >}}
pilita.size(); // Retorna 0 ya que nuestra pila no tiene datos.
{{< /highlight >}}


## Queues (colas) {#queues--colas}

La cola es una estructura de datos lineal al que sólo puedes acceder al primer elemento que fue insertado. Imagina una fila de una caja de un supermercado, por ejemplo.

{{< highlight cpp "linenos=table, linenostart=1" >}}
queue < int > colita;
{{< /highlight >}}


### push (empujar) {#push--empujar}

Añade un dato al final de la cola.

{{< highlight cpp "linenos=table, linenostart=2" >}}
colita.push(5);
colita.push(4);
colita.push(3);
colita.push(2);
colita.push(1);
{{< /highlight >}}


### front (frente) {#front--frente}

Lee el dato que está al frente de la cola.

{{< highlight cpp "linenos=table, linenostart=7" >}}
colita.front(); // Retorna 5, ya que fue lo primero que empujamos a la cola.
{{< /highlight >}}


### pop (quitar) {#pop--quitar}

Remueve el dato que está al frente de la cola

{{< highlight cpp "linenos=table, linenostart=8" >}}
colita.pop();   // Remueve el 5
colita.front(); // Retorna 4, ya que fue lo segundo que empujamos a la cola (y que ahora está primero).
{{< /highlight >}}


### empty (vacío) {#empty--vacío}

Retorna 1 si la cola está vacía, de lo contrario retorna 0.

{{< highlight cpp "linenos=table, linenostart=10" >}}
colita.empty(); // Retorna 1 ya que nuestra cola está vacía.
{{< /highlight >}}


### size (tamaño) {#size--tamaño}

Retorna el tamaño de nuestra cola.

{{< highlight cpp "linenos=table, linenostart=11" >}}
colita.size(); // Retorna 0 ya que nuestra cola no tiene datos.
{{< /highlight >}}
