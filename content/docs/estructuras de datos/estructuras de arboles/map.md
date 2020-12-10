+++
title = "Map (mapa, tabla de hashing)"
author = ["Vicente Villarroel"]
draft = false
weight = 3003
+++

<div class="ox-hugo-toc toc">
<div></div>

<div class="heading">Table of Contents</div>

- [Ejemplo cotidiano](#ejemplo-cotidiano)
- [Inicializar](#inicializar)
- [Insert (insertar)](#insert--insertar)
- [Operar con los valores](#operar-con-los-valores)
- [Find (encontrar)](#find--encontrar)
- [Erase (borrar)](#erase--borrar)
- [Recorrer los valores de un mapa](#recorrer-los-valores-de-un-mapa)
- [Dudas que no dejan dormir](#dudas-que-no-dejan-dormir)

</div>
<!--endtoc-->

Toma dos datos, una llave y un valor. Puedes buscar una llave en tiempo logarítmico con la implementación de la STL. Pero con otras implementaciones se puede hacer en tiempo constante. Las llaves no se pueden repetir.


## Ejemplo cotidiano {#ejemplo-cotidiano}

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


## Inicializar {#inicializar}

Incluimos la librería de map:

{{< highlight cpp "linenos=table, linenostart=1" >}}
#include <map>
{{< /highlight >}}

Inicializamos el mapa curso:

{{< highlight cpp "linenos=table, linenostart=2" >}}
map<string, int> curso;
{{< /highlight >}}


## Insert (insertar) {#insert--insertar}

Forma 1:

{{< highlight cpp "linenos=table, linenostart=3" >}}
curso["perez"] = 1;
{{< /highlight >}}

Forma 2:

{{< highlight cpp "linenos=table, linenostart=4" >}}
curso.insert(pair<string, int>("gonzalez, 3"));
{{< /highlight >}}


## Operar con los valores {#operar-con-los-valores}

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


## Find (encontrar) {#find--encontrar}

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


## Erase (borrar) {#erase--borrar}

Forma 1:

{{< highlight cpp "linenos=table, linenostart=15" >}}
it = curso.find("perez");
curso.erase(it);
{{< /highlight >}}

Forma 2:

{{< highlight cpp "linenos=table, linenostart=17" >}}
curso.erase("gonzalez");
{{< /highlight >}}


## Recorrer los valores de un mapa {#recorrer-los-valores-de-un-mapa}

Es exactamente igual que en un conjunto:

{{< highlight cpp "linenos=table, linenostart=18" >}}
for (it = curso.begin(); it != curso.end(); ++it){
    cout << "Llave: " << it->first << " Valor: " << it->second << '\n';
}
{{< /highlight >}}


## Dudas que no dejan dormir {#dudas-que-no-dejan-dormir}


### ¿Qué pasa si modifico una llave? {#qué-pasa-si-modifico-una-llave}

No se puede, tu código no compilará pues es ilegal hacerlo 👮🚓🚨


### ¿Puedo buscar con el second? {#puedo-buscar-con-el-second}

No, en ese caso recomendamos otra estructura, o tener dos maps 👀


### ¿Puedo tener un map dentro de un map? {#puedo-tener-un-map-dentro-de-un-map}

Si, pero es de psicópata buscar dentro de ese map.
