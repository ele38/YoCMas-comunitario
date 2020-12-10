+++
title = "Acerca de"
author = ["Comunidad YoC+"]
draft = false
weight = 3001
+++

<div class="ox-hugo-toc toc">
<div></div>

<div class="heading">Table of Contents</div>

- [Ejemplos](#ejemplos)

</div>
<!--endtoc-->

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


## Ejemplos {#ejemplos}


### en la vida real {#en-la-vida-real}

Ir al medio de un diccionario, y buscar alfabéticamente, tomando una palabra central
(más o menos), viendo si la palabra que queremos está antes o después y repetir el
proceso de buscar una palabra central.


### Ejemplo computacional {#ejemplo-computacional}

En esta imágen, se usa la búsqueda binaria para encontrar el 19.
![](https://uniwebsidad.com/static/libros/imagenes/algoritmos-python/f0801.png)
