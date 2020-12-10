+++
title = "Bubble sort"
author = ["Vicente Villarroel"]
draft = false
weight = 3002
+++

<div class="ox-hugo-toc toc">
<div></div>

<div class="heading">Table of Contents</div>

- [Ejemplo](#ejemplo)
- [Código de ejemplo:](#código-de-ejemplo)

</div>
<!--endtoc-->

-   Se van comparando los elementos, haciendo que los más grandes suban en el arreglo, como una burbuja.
-   Da lo mismo cómo estén ordenadas las cosas, porque puedes modificar la función de comparación.
-   Funciona invirtiendo el orden de cada par de elementos, si es que el primero es mayor que el segundo.
-   Por ejemplo, se podría usar para contar el número de inversiones que hay que hacer.


## Ejemplo {#ejemplo}

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


## Código de ejemplo: {#código-de-ejemplo}

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
