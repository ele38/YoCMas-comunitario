+++
title = "Implementaciones propias"
author = ["Vicente Villarroel"]
draft = false
weight = 3003
+++

<div class="ox-hugo-toc toc">
<div></div>

<div class="heading">Table of Contents</div>

- [Implementación con while](#implementación-con-while)
- [Implementación recursiva](#implementación-recursiva)

</div>
<!--endtoc-->


## Implementación con while {#implementación-con-while}

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


## Implementación recursiva {#implementación-recursiva}

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
