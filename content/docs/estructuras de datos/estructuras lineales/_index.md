+++
title = "Estructuras lineales"
author = ["Comunidad YoC+"]
draft = false
weight = 2001
+++

<div class="ox-hugo-toc toc">
<div></div>

<div class="heading">Table of Contents</div>

- [Acerca de](#acerca-de)
- [Arrays (arreglos)](#arrays--arreglos)
- [Arrays multidimensionales](#arrays-multidimensionales)
- [Vectors (vectores)](#vectors--vectores)
- [Stacks (pilas)](#stacks--pilas)
- [Queues (colas)](#queues--colas)

</div>
<!--endtoc-->


## Acerca de {#acerca-de}

Rellenar página


## Arrays (arreglos) {#arrays--arreglos}

Los arrays son conjuntos de datos que se almacenan en memoria de manera contigua usando el mismo nombre. Se usan índices para diferenciar los distintos valores del arreglo.
Para crear una arreglo es necesario saber la cantidad de elementos que van a componer nuestro arreglo, pues la cantidad de elementos no se puede cambiar.
Una cosa muy importante que al principio uno suele olvidar es que los índices de los arreglos parten en 0. Es decir, un arreglo de tamaño n puede tomar índices desde el 0 hasta el n-1.


### Inicialización {#inicialización}

Hay dos formas de inicializar un array, especificando su tamaño o llenandolo con valores por defecto.


#### Inicializar un array por su tamaño {#inicializar-un-array-por-su-tamaño}

Para inicializar un array por su tamaño, lo único que hay que especificar es el nombre de la variable y colocar entre "[]" el tamaño de nuestro arreglo. Recordar que como los arrays parten en 0, el valor máximo que podremos acceder será el tamaño del array menos 1.

{{< highlight cpp "linenos=table, linenostart=1" >}}
int arreglo[38]; // Inicializar un arreglo de ints de tamaño 38.
{{< /highlight >}}


#### Inicializar un array con valores por defecto {#inicializar-un-array-con-valores-por-defecto}

Para inicializar un array con valores por defecto, no es necesario especificar el tamaño de nuestro array, pues este está implícito en la cantidad de valores que introducimos.

{{< highlight cpp "linenos=table, linenostart=2" >}}
int arreglo2[] = {3, 6, 2, 1};
{{< /highlight >}}


### Leer el valor de un arreglo {#leer-el-valor-de-un-arreglo}

Para leer un valor de nuestro arreglo, solo hay que especificar el nombre del arreglo y su índice. Notar que sólo se puede acceder a un valor de un arreglo a la vez.

```cpp
arreglo2[3]; // Retorna 1
```


### Asignar valores a un arreglo {#asignar-valores-a-un-arreglo}

Para esto, hay que especificar la variable, el índice al cuál acceder y especificar su nuevo valor. Recordar que el valor del índice puede ser una variable, pero que no puede estar fuera del rango del tamaño de nuestro arreglo.

{{< highlight cpp "linenos=table, linenostart=3" >}}
arreglo2[3] = 5; // El indice 3 de nuestro arreglo, ahora tiene el valor 3
{{< /highlight >}}


## Arrays multidimensionales {#arrays-multidimensionales}

Un array multidimensional es aquel que requiuere de más de un índice para ser llamado, como su nombre lo indica, es útil para cuando necesitamos acceder a datos que requieren más de una dimensión, como por ejemplo valores dentro de una malla. Otra forma de enternder los arrays multidimensionales es como un arreglo de arreglos (de arreglos de arreglos.. n veces, siendo n la cantidad de dimensiones). Los arreglos de 2 dimensiones también son conocidos como matrices.


### Inicializar un arreglo multidimensional {#inicializar-un-arreglo-multidimensional}

Para esto, hay que especificar el tamaño de cada dimensión del array. Notar que la regla de que empiezan en 0 y terminan en n-1 se sigue cumpliendo. Es posible asignarles valores predeterminados, pero creo que eso se va poniendo exponencialmente más psicópata a medida de que vas incrementando las dimensiones del array a crear, por lo que no lo voy a demostrar.

{{< highlight cpp "linenos=table, linenostart=1" >}}
int matriz[3][4];
int tridimensional[100][100][100];
{{< /highlight >}}


### Asignar valores en un arreglo multidimensional {#asignar-valores-en-un-arreglo-multidimensional}

Es muy similar a cómo se hace en un arreglo unidimensional, solo que se especifica cada índice.

{{< highlight cpp "linenos=table, linenostart=3" >}}
int n = 3, m = 5;
matriz[2][1] = 10;
tridimensional[n][m] = 4;
{{< /highlight >}}


## Vectors (vectores) {#vectors--vectores}

Los vectores son como arreglos, excepto de que el tamaño es dinámico, es decir, se puede cambiar.


### Inicializar un vector {#inicializar-un-vector}

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


### Iteradores de un arreglo {#iteradores-de-un-arreglo}

Hay ciertos iteradores que podemos usar en un arreglo que nos ayudarán en algunos casos, como por ejemplo si quieremos recorrer un arreglo. Estos son:

-   begin() -- Iterador que accede al primer valor del arreglo.
-   end() -- Accede al final del arreglo.
-   rbegin() -- Accede al ultimo elemento del arreglo
-   rend -- Accede al inicio del arreglo


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
