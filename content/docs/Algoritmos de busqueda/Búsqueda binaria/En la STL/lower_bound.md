+++
title = "upper_bound() (límite superior)"
author = ["Comunidad YoC+"]
draft = false
weight = 5004
+++

La función upper\_bound() de la librería STL nos entrega un puntero a un valor
**superior** al pedido en un arreglo ordenado.

En el caso de que no haya un valor superior al pedido, nos entrega el
último valor del arreglo.

Por ejemplo:

{{< highlight cpp "linenos=table, linenostart=1" >}}
  *upper_bound(v.begin(), v.end(), 30);
{{< /highlight >}}

Valor de retorno: iterador al **40** (posición [4])
