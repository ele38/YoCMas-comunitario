+++
title = "Uso mediante la librería STL"
author = ["Comunidad YoC+"]
draft = false
weight = 3002
+++

<div class="ox-hugo-toc toc">
<div></div>

<div class="heading">Table of Contents</div>

- [Importar](#importar)
- [binary\_search()](#binary-search)
- [lower\_bound() (límite inferior)](#lower-bound--límite-inferior)
- [upper\_bound() (límite superior)](#upper-bound--límite-superior)

</div>
<!--endtoc-->


## Importar {#importar}

Podemos directamente importar toda la stl o podemos importar la librería <algorithm> de la
siguiente forma:

{{< highlight cpp "linenos=table, linenostart=1" >}}
#include <algorithm>
{{< /highlight >}}


## binary\_search() {#binary-search}

La librería STL ya incluye binary search, si queremos saber si el valor
3 está en un vector, podemos ejecutar:

{{< highlight cpp "linenos=table, linenostart=2" >}}
vector<int> v{1,2,5,7};
if (binary_search (v.begin(), v.end(), 3)) {
    cout << "Se encuentra el valor 3 en nuestro vector\n";
}
else {
    cout << "No hay ningún 3 en nuestro vector\n";
}
{{< /highlight >}}

Retorna un _bool_.


## lower\_bound() (límite inferior) {#lower-bound--límite-inferior}

La función lower\_bound() de la librería STL retorna un puntero a un
valor **superior** o, si es posible, **igual** al entregado dentro de una
estructura ordenada.

Si todos los elementos en el arreglo son inferiores al valor pedido, se
entrega el último elemento del arreglo. Si los elementos del arreglo son
superiores al valor pedido, se entrega el primer elemento del arreglo.

Por ejemplo:

{{< highlight cpp "linenos=table, linenostart=1" >}}
  vector<int> v{ 10, 20, 30, 30, 30, 40, 50 };
  *lower_bound(v.begin(), v.end(), 30);
{{< /highlight >}}

Valor de retorno: un iterador que apunta hacia **30** (el primero en el arreglo, en la posición [2])


## upper\_bound() (límite superior) {#upper-bound--límite-superior}

La función upper\_bound() de la librería STL nos entrega un puntero a un valor
**superior** al pedido en un arreglo ordenado.

En el caso de que no haya un valor superior al pedido, nos entrega el
último valor del arreglo.

Por ejemplo:

{{< highlight cpp "linenos=table, linenostart=3" >}}
  *upper_bound(v.begin(), v.end(), 30);
{{< /highlight >}}

Valor de retorno: iterador al **40** (posición [4])
