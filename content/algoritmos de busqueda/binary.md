---
title: "Binary Search"
date: 2020-11-23T06:08:41+00:00
author: "Mateo León"
draft: false
---

<div class="ox-hugo-toc toc">
<div></div>

<div class="heading">Contenido</div>

- [¿Qué es la búsqueda binaria?](#que-es)
- [Ejemplo de búsqueda binaria](#ejemplo)
- [Uso mediante STL](#uso-stl)
- [Implementación con while](#imp-while)
- [Implementación recursiva](#imp-recursiva)
- [lower_bound() en STL](#lower-bound)
- [upper_bound() en STL](#upper-bound)
</div>
<!--endtoc-->

## ¿Qué es la búsqueda binaria? {#que-es}
La búsqueda binaria es un algoritmo de *divide and conquer*, que nos permite encontrar un elemento dentro de una estructura **ordenada** rápidamente.
Al ejecutarse, toma el centro de un arreglo y comprueba si el valor que se busca es igual al del centro. De no serlo, verifica si el valor es menor o mayor al del centro.

Si el valor es mayor al del centro, se ignoran todos los valores anteriores al centro, dividiendo la cantidad de números a la mitad.

Si el valor es menor al del centro, se ignoran todos los valores de después del centro, dividiendo la cantidad de números a la mitad.

La dificultad de este algoritmo es **O log(N)**, comparada con un algoritmo lineal, que en el peor de los casos tiene dificultad **O (N)**.
## Ejemplo de búsqueda binaria {#ejemplo}
### Ejemplo en la vida real: 
Ir al medio de un diccionario, y buscar alfabéticamente.

### Ejemplo buscando el 19:

![ejemplo](https://uniwebsidad.com/static/libros/imagenes/algoritmos-python/f0801.png)


## Uso mediante STL {#uso-stl}
La librería STL ya incluye binary search, si queremos saber si el valor 3 está en un vector, podemos ejecutar:
```cpp 
binary_search (v.begin(), v.end(), 3)
```
Retorna un *bool*.

## Implementación con while {#imp-while}
Esta implementación nos retorna el número a buscar dentro de un arreglo. 
```cpp
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
```
## Implementación recursiva {#imp-recursiva}
Esta implementación nos retorna el número a buscar dentro de un arreglo. 
```cpp
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
```

## lower_bound() en STL {#lower-bound}
La función lower_bound() de la librería STL retorna un puntero a un valor **superior** o, si es posible, **igual** al entregado dentro de una estructura ordenada.

Si todos los elementos en el arreglo son inferiores al valor pedido, se entrega el último elemento del arreglo.
Si los elementos del arreglo son superiores al valor pedido, se entrega el primer elemento del arreglo.
### Ejemplo
```cpp
vector<int> v{ 10, 20, 30, 30, 30, 40, 50 };
*lower_bound(v.begin(), v.end(), 35);
```
Valor de retorno: **30** (el primero en el arreglo, en la posición [2])
## upper_bound() en STL {#upper-bound}
La función upper_bound() de la librería STL nos entrega un puntero a un valor **superior** al pedido en un arreglo ordenado.

En el caso de que no haya un valor superior al pedido, nos entrega el último valor del arreglo.

### Ejemplo
```cpp
vector<int> v{ 10, 20, 30, 30, 40, 50 };
*upper_bound(v.begin(), v.end(), 30);
```

Valor de retorno: **40** (posición [4])
