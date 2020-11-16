+++
title = "Set (conjunto)"
author = ["Vicente Villarroel"]
draft = false
weight = 3002
+++

<div class="ox-hugo-toc toc">
<div></div>

<div class="heading">Table of Contents</div>

- [Inicialización](#inicialización)
- [insert (Insertar)](#insert--insertar)
- [find (Encontrar)](#find--encontrar)
- [erase (borrar)](#erase--borrar)
- [Iterar a través de un conjunto](#iterar-a-través-de-un-conjunto)

</div>
<!--endtoc-->

No permite que hayan elementos repetidos.


## Inicialización {#inicialización}

Incluimos la librería:

{{< highlight cpp "linenos=table, linenostart=1" >}}
#include <set>
{{< /highlight >}}

Inicializamos nuestro conjunto:

{{< highlight cpp "linenos=table, linenostart=2" >}}
set < int > conjunto; // int puede ser reemplazado con cualquier otro tipo de dato
{{< /highlight >}}


## insert (Insertar) {#insert--insertar}

Inserta un dato. Retorna un par de elementos, el primero siendo el iterador del valor insertado y el segundo siendo un bool que marca si es que ya existía o no. En el ejemplo de abajo, usamos .second para comprobar si se insertó correctamente o no.

{{< highlight cpp "linenos=table, linenostart=3" >}}
if (conjunto.insert(10).second) // Retorna TRUE ya que no estaba anteriormente
    cout << "ganai\n"; if (conjunto.insert(10).second); // Retorna FALSE ya que ya había un 10.
cout << "no ganai\n";
conjunto.insert(20);
conjunto.insert(40);
conjunto.insert(30);
conjunto.insert(11);
{{< /highlight >}}


## find (Encontrar) {#find--encontrar}

Busca un elemento en el set y si lo encuentra retorna un iterador al valor. De lo contrario, retorna conjunto.end();

{{< highlight cpp "linenos=table, linenostart=10" >}}
if (conjunto.find(10) != conjunto.end())
    cout << "ganai\n";
{{< /highlight >}}


## erase (borrar) {#erase--borrar}

Puedes borrar un valor si le entregas el iterador al valor.

{{< highlight cpp "linenos=table, linenostart=12" >}}
set < int >::iterator it = conjunto.find(11);
if (it != conjunto.end())
    conjunto.erase(it);
{{< /highlight >}}


## Iterar a través de un conjunto {#iterar-a-través-de-un-conjunto}

Puedes iterar a través de un conjunto con los valores ya ordenados con un iterador:

{{< highlight cpp "linenos=table, linenostart=15" >}}
// Imprime 10 11 20 30 40
for (it = conjunto.begin(); it != conjunto.end(); ++it)
    cout << *it << " ";
cout << '\n';
{{< /highlight >}}
