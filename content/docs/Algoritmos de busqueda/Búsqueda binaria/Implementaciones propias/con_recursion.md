+++
title = "Implementación recursiva"
author = ["Vicente Villarroel"]
draft = false
weight = 4002
+++

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
