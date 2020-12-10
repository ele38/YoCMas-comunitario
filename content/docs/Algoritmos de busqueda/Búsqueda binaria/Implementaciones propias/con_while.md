+++
title = "Implementación con while"
author = ["Comunidad YoC+"]
draft = false
weight = 4001
+++

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
