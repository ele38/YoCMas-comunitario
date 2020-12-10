+++
title = "Algoritmos de ordenamiento"
author = ["Vicente Villarroel"]
draft = false
weight = 1001
+++

<div class="ox-hugo-toc toc">
<div></div>

<div class="heading">Table of Contents</div>

- [Acerca de](#acerca-de)
- [Algoritmos de fuerza bruta](#algoritmos-de-fuerza-bruta)
- [Algoritmos de "decrecer y conquistar"](#algoritmos-de-decrecer-y-conquistar)

</div>
<!--endtoc-->


## Acerca de {#acerca-de}

Un algoritmo de ordenamiento es aquel que toma los elementos de una estructura y les asigna un orden. Cada algoritmo de ordenamiento tiene su forma de operar, y podría ayudar a conseguir la respuesta a un problema, no necesariamente por el resultado del ordenamiento.


## Algoritmos de fuerza bruta {#algoritmos-de-fuerza-bruta}


### Acerca de {#acerca-de}

Rellenar


### Bubble sort {#bubble-sort}

-   Se van comparando los elementos, haciendo que los más grandes suban en el arreglo, como una burbuja.
-   Da lo mismo cómo estén ordenadas las cosas, porque puedes modificar la función de comparación.
-   Funciona invirtiendo el orden de cada par de elementos, si es que el primero es mayor que el segundo.
-   Por ejemplo, se podría usar para contar el número de inversiones que hay que hacer.


#### Ejemplo {#ejemplo}

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


#### Código de ejemplo: {#código-de-ejemplo}

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


### Insertion sort {#insertion-sort}

-   Se va de izquierda a derecha, se compara el segundo con el primero, se intercambian si el segundo es menor, si este es el caso, se vuelve a preguntar si el de la izquierda es menor al de mas a la izquierda y así hasta que se encuentre un caso en el que no o se llegue al principio del arreglo.


#### Rellenar ejemplo {#rellenar-ejemplo}


#### Rellenar codigo de ejemplo {#rellenar-codigo-de-ejemplo}


## Algoritmos de "decrecer y conquistar" {#algoritmos-de-decrecer-y-conquistar}


### Acerca de {#acerca-de}

Rellenar


### Selection sort {#selection-sort}

-   Tiene dos sub-arreglos, uno de elementos ya ordenados y uno de los elementos resantes.
-   El arreglo ya ordenado parte vacío.
-   Busca el valor mínimo entre los elementos no ordenados y lo añade al final de los ordenados.


#### Rellenar ejemplo {#rellenar-ejemplo}


#### Rellenar codigo de ejemplo {#rellenar-codigo-de-ejemplo}
