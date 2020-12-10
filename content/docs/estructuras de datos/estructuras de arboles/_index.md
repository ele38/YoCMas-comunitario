+++
title = "Estructuras en forma de árbol"
author = ["Comunidad YoC+"]
draft = false
weight = 2002
+++

<div class="ox-hugo-toc toc">
<div></div>

<div class="heading">Table of Contents</div>

- [Acerca de](#acerca-de)
- [Set (conjunto)](#set--conjunto)
- [Map (mapa, tabla de hashing)](#map--mapa-tabla-de-hashing)

</div>
<!--endtoc-->


## Acerca de {#acerca-de}

Véase: arbol binario


## Set (conjunto) {#set--conjunto}

Es una lista que no permite que hayan elementos repetidos.


### Inicialización {#inicialización}

Incluimos la librería:

{{< highlight cpp "linenos=table, linenostart=1" >}}
#include <set>
{{< /highlight >}}

Inicializamos nuestro conjunto:

{{< highlight cpp "linenos=table, linenostart=2" >}}
set < int > conjunto; // int puede ser reemplazado con cualquier otro tipo de dato
{{< /highlight >}}


### insert (Insertar) {#insert--insertar}

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


### find (Encontrar) {#find--encontrar}

Busca un elemento en el set y si lo encuentra retorna un iterador al valor. De lo contrario, retorna conjunto.end();

{{< highlight cpp "linenos=table, linenostart=10" >}}
if (conjunto.find(10) != conjunto.end())
    cout << "ganai\n";
{{< /highlight >}}


### erase (borrar) {#erase--borrar}

Puedes borrar un valor si le entregas el iterador al valor.

{{< highlight cpp "linenos=table, linenostart=12" >}}
set < int >::iterator it = conjunto.find(11);
if (it != conjunto.end())
    conjunto.erase(it);
{{< /highlight >}}


### Iterar a través de un conjunto {#iterar-a-través-de-un-conjunto}

Puedes iterar a través de un conjunto con los valores ya ordenados con un iterador:

{{< highlight cpp "linenos=table, linenostart=15" >}}
// Imprime 10 11 20 30 40
for (it = conjunto.begin(); it != conjunto.end(); ++it)
    cout << *it << " ";
cout << '\n';
{{< /highlight >}}


## Map (mapa, tabla de hashing) {#map--mapa-tabla-de-hashing}

Toma dos datos, una llave y un valor. Puedes buscar una llave en tiempo logarítmico con la implementación de la STL. Pero con otras implementaciones se puede hacer en tiempo constante. Las llaves no se pueden repetir.


### Ejemplo cotidiano {#ejemplo-cotidiano}

Libros:

| Título (Llave)               | Autor (Valor)   |
|------------------------------|-----------------|
| The C Programming Language   | Brian Keringhan |
| The AWK Programming Language | Brian Keringhan |
| 1984                         | George Orwell   |

Curso:

| Apellido | Cantidad de alumnos con el apellido |
|----------|-------------------------------------|
| Gonzalez | 3                                   |
| Perez    | 2                                   |


### Inicializar {#inicializar}

Incluimos la librería de map:

{{< highlight cpp "linenos=table, linenostart=1" >}}
#include <map>
{{< /highlight >}}

Inicializamos el mapa curso:

{{< highlight cpp "linenos=table, linenostart=2" >}}
map<string, int> curso;
{{< /highlight >}}


### Insert (insertar) {#insert--insertar}

Forma 1:

{{< highlight cpp "linenos=table, linenostart=3" >}}
curso["perez"] = 1;
{{< /highlight >}}

Forma 2:

{{< highlight cpp "linenos=table, linenostart=4" >}}
curso.insert(pair<string, int>("gonzalez, 3"));
{{< /highlight >}}


### Operar con los valores {#operar-con-los-valores}

Se puede operar con el valor tomando la llave.
Ejemplo 1:

{{< highlight cpp "linenos=table, linenostart=5" >}}
++curso.["perez"]; // Incrementar el valor de la llave perez, por ejemplo.
{{< /highlight >}}

Ejemplo 2:

{{< highlight cpp "linenos=table, linenostart=6" >}}
cout << curso.["perez"] << endl; // El output será 2.
{{< /highlight >}}

Cuidado con operar con valores no existentes, pues los inicializará de una forma inesperada.


### Find (encontrar) {#find--encontrar}

Retorna un iterador, si no lo encuentra, apunta a map.end()
Asignamos el iterador it a gonzalez, y luego lo usamos:

{{< highlight cpp "linenos=table, linenostart=7" >}}
map<string, int>::iterator it;
it = curso.find("gonzalez");

if (it != curso.end()){
cout << "Hay " << it->second << " " << it->first << " en el curso:\n";
cout << "Llave: " << it->first << " Valor: " << it->second << '\n';
}
{{< /highlight >}}

Podemos incluso operar usando los iteradores:

{{< highlight cpp "linenos=table, linenostart=14" >}}
it->++second;
{{< /highlight >}}


### Erase (borrar) {#erase--borrar}

Forma 1:

{{< highlight cpp "linenos=table, linenostart=15" >}}
it = curso.find("perez");
curso.erase(it);
{{< /highlight >}}

Forma 2:

{{< highlight cpp "linenos=table, linenostart=17" >}}
curso.erase("gonzalez");
{{< /highlight >}}


### Recorrer los valores de un mapa {#recorrer-los-valores-de-un-mapa}

Es exactamente igual que en un conjunto:

{{< highlight cpp "linenos=table, linenostart=18" >}}
for (it = curso.begin(); it != curso.end(); ++it){
    cout << "Llave: " << it->first << " Valor: " << it->second << '\n';
}
{{< /highlight >}}


### Dudas que no dejan dormir {#dudas-que-no-dejan-dormir}


#### ¿Qué pasa si modifico una llave? {#qué-pasa-si-modifico-una-llave}

No se puede, tu código no compilará pues es ilegal hacerlo 👮🚓🚨


#### ¿Puedo buscar con el second? {#puedo-buscar-con-el-second}

No, en ese caso recomendamos otra estructura, o tener dos maps 👀


#### ¿Puedo tener un map dentro de un map? {#puedo-tener-un-map-dentro-de-un-map}

Si, pero es de psicópata buscar dentro de ese map.
