+++
title = "Algoritmos de fuerza bruta"
author = ["Comunidad YoC+"]
draft = false
weight = 2002
+++

<div class="ox-hugo-toc toc">
<div></div>

<div class="heading">Table of Contents</div>

- [Acerca de](#acerca-de)
- [Bubble sort](#bubble-sort)
- [Insertion sort](#insertion-sort)

</div>
<!--endtoc-->


## Acerca de {#acerca-de}

Rellenar


## Bubble sort {#bubble-sort}

-   Se van comparando los elementos, haciendo que los más grandes suban en el arreglo, como una burbuja.
-   Da lo mismo cómo estén ordenadas las cosas, porque puedes modificar la función de comparación.
-   Funciona invirtiendo el orden de cada par de elementos, si es que el primero es mayor que el segundo.
-   Por ejemplo, se podría usar para contar el número de inversiones que hay que hacer.


### Ejemplo {#ejemplo}

| <span class="underline">5</span> | <span class="underline">3</span> | 4                                | 1                                |
|----------------------------------|----------------------------------|----------------------------------|----------------------------------|
| 3                                | <span class="underline">5</span> | <span class="underline">4</span> | 1                                |
| 3                                | 4                                | <span class="underline">5</span> | <span class="underline">1</span> |
| 3                                | 4                                | 1                                | **5**                            |
| <span class="underline">3</span> | <span class="underline">4</span> | 1                                | **5**                            |
| 3                                | <span class="underline">1</span> | <span class="underline">4</span> | **5**                            |
| 3                                | 1                                | **4**                            | **5**                            |
| <span class="underline">3</span> | <span class="underline">1</span> | **4**                            | **5**                            |
| 1                                | **3**                            | **4**                            | **5**                            |
| **1**                            | **3**                            | **4**                            | **5**                            |


### Código de ejemplo: {#código-de-ejemplo}

```cpp
void bubblesort (vector<int> &vec) {
    int size = vec.size();
    for (int i = size-1; i > 0; --i) {
        for (int j = 0; j < i; ++j) {
            if (vec[j] > vec[j+1]) {
                int aux = vec[j];
                vec[j] = vec[j+1];
                vec[j+1] = aux;
            }
        }
    }
    return;
}
```


## Insertion sort {#insertion-sort}

-   Se va de izquierda a derecha, se compara el segundo con el primero, se intercambian si el segundo es menor, si este es el caso, se vuelve a preguntar si el de la izquierda es menor al de mas a la izquierda y así hasta que se encuentre un caso en el que no o se llegue al principio del arreglo.


### Rellenar ejemplo {#rellenar-ejemplo}


### Rellenar codigo de ejemplo {#rellenar-codigo-de-ejemplo}
