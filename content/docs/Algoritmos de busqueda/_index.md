+++
title = "Algoritmos de búsqueda"
author = ["Comunidad YoC+"]
draft = false
weight = 1003
collapsible = true
+++

<div class="ox-hugo-toc toc">
<div></div>

<div class="heading">Table of Contents</div>

- [Búsqueda binaria](#búsqueda-binaria)

</div>
<!--endtoc-->


## Búsqueda binaria {#búsqueda-binaria}


### Acerca de {#acerca-de}

La búsqueda binaria es un algoritmo de _divide and conquer_ (dividir y conquistar), que nos
permite encontrar un elemento dentro de una estructura **ordenada**
rápidamente. Al ejecutarse, toma el centro de un arreglo y comprueba si
el valor que se busca es igual al del centro. De no serlo, verifica si
el valor es menor o mayor al del centro.

Si el valor es mayor al del centro, se ignoran todos los valores
anteriores al centro, dividiendo la cantidad de números a la mitad.

Si el valor es menor al del centro, se ignoran todos los valores de
después del centro, dividiendo la cantidad de números a la mitad.

La complejidad de este algoritmo es **Olog(N)**, comparada con un
algoritmo lineal, que en el peor de los casos tiene complejidad **O(N)**.


#### Ejemplos {#ejemplos}

<!--list-separator-->

-  en la vida real

    Ir al medio de un diccionario, y buscar alfabéticamente, tomando una palabra central
    (más o menos), viendo si la palabra que queremos está antes o después y repetir el
    proceso de buscar una palabra central.

<!--list-separator-->

-  Ejemplo computacional

    En esta imágen, se usa la búsqueda binaria para encontrar el 19.
    ![](https://uniwebsidad.com/static/libros/imagenes/algoritmos-python/f0801.png)


### Uso mediante la librería STL {#uso-mediante-la-librería-stl}

<!--list-separator-->

-  Importar

    Podemos directamente importar toda la stl o podemos importar la librería <algorithm> de la
    siguiente forma:

    {{< highlight cpp "linenos=table, linenostart=1" >}}
    #include <algorithm>
    {{< /highlight >}}

<!--list-separator-->

-  binary\_search()

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

<!--list-separator-->

-  lower\_bound() (límite inferior)

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

<!--list-separator-->

-  upper\_bound() (límite superior)

    La función upper\_bound() de la librería STL nos entrega un puntero a un valor
    **superior** al pedido en un arreglo ordenado.

    En el caso de que no haya un valor superior al pedido, nos entrega el
    último valor del arreglo.

    Por ejemplo:

    {{< highlight cpp "linenos=table, linenostart=3" >}}
      *upper_bound(v.begin(), v.end(), 30);
    {{< /highlight >}}

    Valor de retorno: iterador al **40** (posición [4])


### Implementaciones propias {#implementaciones-propias}


#### Implementación con while {#implementación-con-while}

Esta implementación nos retorna el índice del número a buscar dentro de un arreglo.

{{< highlight cpp "linenos=table, linenostart=1" >}}
  int binarySearch(int arr[], int l, int r, int x)
  {

      while (l <= r) {
          int m = l + (r - l) / 2;

          // Revisa si x esta al medio
          if (arr[m] == x)
          return m;

          // Si x es mayor, ignorar la izquierda
          if (arr[m] < x)
          l = m + 1;

          // Si x es menor, ignorar la derecha
          else
          r = m - 1;

      }
      return -1;

  }
{{< /highlight >}}


#### Implementación recursiva {#implementación-recursiva}

Esta implementación nos retorna el índice del número a buscar dentro de un arreglo.

{{< highlight cpp "linenos=table, linenostart=1" >}}
  int binarySearch(int arr[], int l, int r, int x)
  {

      if (r >= l) {

          int mid = l + (r - l) / 2;

          // Revisa si x esta al medio

          if (arr[mid] == x)
          return mid;

          // Si x es mayor, ignorar la izquierda
          if (arr[mid] > x)
          return binarySearch(arr, l, mid - 1, x);
          // Si x es mayor, ignorar la derecha
          return binarySearch(arr, mid + 1, r, x);
      }
      return -1;
  }
{{< /highlight >}}
