
# Table of Contents

1.  [Estructuras lineales](#orge4e11cc)
    1.  [Vectores](#orgb9fc00e)
        1.  [Asignar un valor](#org17293f5)
        2.  [push back (empujar atrás)](#orgf165640)
        3.  [pop back (quitar atrás)](#orgf0f8989)
        4.  [insert (insertar)](#orga50ee3a)
        5.  [erase (borrar)](#org89e6680)
    2.  [Stacks (pilas)](#org19877f1)
        1.  [push (empujar)](#orga0a8436)
        2.  [top (cima)](#org8b376db)
        3.  [pop (quitar)](#orgd8bf83f)
        4.  [empty (vacío)](#org8fcb229)
        5.  [size (tamaño)](#org80b8a01)
    3.  [Queues (colas)](#org3843023)
        1.  [push (empujar)](#orgea3b30a)
        2.  [front (frente)](#org08c4831)
        3.  [pop (quitar)](#orgd88b51b)
        4.  [empty (vacío)](#org28a8d2f)
        5.  [size (tamaño)](#org1f4588a)
2.  [Estructuras en forma de árbol](#orgce87665)
    1.  [Set (conjunto)](#org7f814d3)
        1.  [Inicialización](#orgad40f85)
        2.  [insert (Insertar)](#orgb22aec0)
        3.  [find (Encontrar)](#orge830d58)
        4.  [erase (borrar)](#org1c7fcfd)
        5.  [Iterar a través de un conjunto](#org5eb58ee)
    2.  [Map (mapa, tabla de hashing)](#org89a7f8c)
        1.  [Ejemplo cotidiano](#orga96d1d2)
        2.  [Inicializar](#org4c31b7d)
        3.  [Insert (insertar)](#org3e3e2ff)
        4.  [Operar con los valores](#org2e6c6a5)
        5.  [Find (encontrar)](#org0a63e70)
        6.  [Erase (borrar)](#org1a7c601)
        7.  [Recorrer los valores de un vector](#org9a00ce0)
        8.  [Dudas que no dejan dormir](#org487022e)



<a id="orge4e11cc"></a>

# Estructuras lineales


<a id="orgb9fc00e"></a>

## Vectores

---

Los vectores son como arreglos, excepto de que el tamaño es dinámico, es decir, se puede cambiar.
Incluimos la librería:

    1  #include <vector>

Inicializamos nuestro vector &ldquo;vec&rdquo;:

    2  int n = 3;
    3  vector < int > vec(n, 0); // Inicializa un vector de tamaño 3 con todos sus valores = 0. Tanto el tamaño como valor son opcionales.


<a id="org17293f5"></a>

### Asignar un valor

    4  vec[2] = 1; // Asigna el valor "1" al índice 2 (es decir, al 3er valor del vector)


<a id="orgf165640"></a>

### push back (empujar atrás)

Si no sabemos el tamaño de nuestro vector, podemos simplemente usar push<sub>back</sub>(valor); para enviar es valor al final del vector.

    5  vec.push_back(1); // Inserta un 1 al final del vector

Por ejemplo, se podría usar en un for, sin necesidad de inicializar el vector con una cantidad de valores.

     6  vector <int> vec2;
     7  int n;
     8  cin >> n;
     9  for (int i = 0; i < n; ++i){
    10      int valor;
    11      cin >> valor;
    12      vec2.push_back();
    13  }


<a id="orgf0f8989"></a>

### pop back (quitar atrás)

Elimina el último valor del vector.

    14  vec.pop_back(); // En este caso, elimina el 1


<a id="orga50ee3a"></a>

### insert (insertar)

Podemos insertar un valor entre dos indices de un vector. El problema de esto es que mueve todos los valores que estén más adelante, lo que es lento.

    15  vec.insert(vec.begin() + 2, 4); // Inserta el valor 4 al índice 2


<a id="org89e6680"></a>

### erase (borrar)

Borra un dato del vector. Al igual que el insert, tiene que mover todos los datos siguientes (esta vez a la derecha).

    16  vec.erase(vec.begin() + 2); // Elimina el valor con índice 2, en nuestro caso, el 4 que insertamos antes.


<a id="org19877f1"></a>

## Stacks (pilas)

---

La pila es una estructura de datos lineal al que sólo puedes acceder al último elemento que fue insertado. Imagina una pila de platos, por ejemplo.

    1  stack < int > pilita;


<a id="orga0a8436"></a>

### push (empujar)

Empuja un dato a la cima de la pila.

    2  pilita.push(8); // Empuja un 8 a la cima de la pila.


<a id="org8b376db"></a>

### top (cima)

Lee lo que hay en la cima de la pila.

    3  pilita.top(); // Retorna el 8.


<a id="orgd8bf83f"></a>

### pop (quitar)

Remueve el dato de la cima de la pila.

    4  pilita.pop(); // Remueve el 8.


<a id="org8fcb229"></a>

### empty (vacío)

Retorna 1 si la pila está vacía, de lo contrario retorna 0.

    5  pilita.empty(); // Retorna 1 ya que nuestra pila está vacía.


<a id="org80b8a01"></a>

### size (tamaño)

Retorna el tamaño de nuestra pila.

    6  pilita.size(); // Retorna 0 ya que nuestra pila no tiene datos.


<a id="org3843023"></a>

## Queues (colas)

---

La cola es una estructura de datos lineal al que sólo puedes acceder al primer elemento que fue insertado. Imagina una fila de una caja de un supermercado, por ejemplo.

    1  queue < int > colita;


<a id="orgea3b30a"></a>

### push (empujar)

Añade un dato al final de la cola.

    2  colita.push(5);
    3  colita.push(4);
    4  colita.push(3);
    5  colita.push(2);
    6  colita.push(1);


<a id="org08c4831"></a>

### front (frente)

Lee el dato que está al frente de la cola.

    7  colita.front(); // Retorna 5, ya que fue lo primero que empujamos a la cola.


<a id="orgd88b51b"></a>

### pop (quitar)

Remueve el dato que está al frente de la cola

    8  colita.pop();   // Remueve el 5
    9  colita.front(); // Retorna 4, ya que fue lo segundo que empujamos a la cola (y que ahora está primero).


<a id="org28a8d2f"></a>

### empty (vacío)

Retorna 1 si la cola está vacía, de lo contrario retorna 0.

    10  colita.empty(); // Retorna 1 ya que nuestra cola está vacía.


<a id="org1f4588a"></a>

### size (tamaño)

Retorna el tamaño de nuestra cola.

    11  colita.size(); // Retorna 0 ya que nuestra cola no tiene datos.


<a id="orgce87665"></a>

# Estructuras en forma de árbol

Véase: arbol binario


<a id="org7f814d3"></a>

## Set (conjunto)

---

No permite que hayan elementos repetidos.


<a id="orgad40f85"></a>

### Inicialización

Incluimos la librería:

    1  #include <set>

Inicializamos nuestro conjunto:

    2  set < int > conjunto; // int puede ser reemplazado con cualquier otro tipo de dato


<a id="orgb22aec0"></a>

### insert (Insertar)

Inserta un dato. Retorna un par de elementos, el primero siendo el iterador del valor insertado y el segundo siendo un bool que marca si es que ya existía o no. En el ejemplo de abajo, usamos .second para comprobar si se insertó correctamente o no.

    3  if (conjunto.insert(10).second) // Retorna TRUE ya que no estaba anteriormente
    4      cout << "ganai\n"; if (conjunto.insert(10).second); // Retorna FALSE ya que ya había un 10.
    5  cout << "no ganai\n";
    6  conjunto.insert(20);
    7  conjunto.insert(40);
    8  conjunto.insert(30);
    9  conjunto.insert(11);


<a id="orge830d58"></a>

### find (Encontrar)

Busca un elemento en el set y si lo encuentra retorna un iterador al valor. De lo contrario, retorna conjunto.end();

    10  if (conjunto.find(10) != conjunto.end())
    11      cout << "ganai\n";


<a id="org1c7fcfd"></a>

### erase (borrar)

Puedes borrar un valor si le entregas el iterador al valor.

    12  set < int >::iterator it = conjunto.find(11);
    13  if (it != conjunto.end())
    14      conjunto.erase(it);


<a id="org5eb58ee"></a>

### Iterar a través de un conjunto

Puedes iterar a través de un conjunto con los valores ya ordenados con un iterador:

    15  // Imprime 10 11 20 30 40
    16  for (it = conjunto.begin(); it != conjunto.end(); ++it)
    17      cout << *it << " ";
    18  cout << '\n';


<a id="org89a7f8c"></a>

## Map (mapa, tabla de hashing)

---

Toma dos datos, una llave y un valor. Puedes buscar una llave en tiempo logarítmico con la implementación de la STL. Pero con otras implementaciones se puede hacer en tiempo constante. Las llaves no se pueden repetir.


<a id="orga96d1d2"></a>

### Ejemplo cotidiano

Libros:

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">Título (Llave)</th>
<th scope="col" class="org-left">Autor (Valor)</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">The C Programming Language</td>
<td class="org-left">Brian Keringhan</td>
</tr>


<tr>
<td class="org-left">The AWK Programming Language</td>
<td class="org-left">Brian Keringhan</td>
</tr>


<tr>
<td class="org-left">1984</td>
<td class="org-left">George Orwell</td>
</tr>
</tbody>
</table>

Curso:

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-right" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">Apellido</th>
<th scope="col" class="org-right">Cantidad de alumnos con el apellido</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">Gonzalez</td>
<td class="org-right">3</td>
</tr>


<tr>
<td class="org-left">Perez</td>
<td class="org-right">2</td>
</tr>
</tbody>
</table>


<a id="org4c31b7d"></a>

### Inicializar

Incluimos la librería de map:

    1  #include <map>

Inicializamos el mapa curso:

    2  map<string, int> curso;


<a id="org3e3e2ff"></a>

### Insert (insertar)

Forma 1:

    3  curso["perez"] = 1;

Forma 2:

    4  curso.insert(pair<string, int>("gonzalez, 3"));


<a id="org2e6c6a5"></a>

### Operar con los valores

Se puede operar con el valor tomando la llave.
Ejemplo 1:

    5  ++curso.["perez"]; // Incrementar el valor de la llave perez, por ejemplo.

Ejemplo 2:

    6  cout << curso.["perez"] << endl; // El output será 2.

Cuidado con operar con valores no existentes, pues los inicializará de una forma inesperada.


<a id="org0a63e70"></a>

### Find (encontrar)

Retorna un iterador, si no lo encuentra, apunta a map.end()
Asignamos el iterador it a gonzalez, y luego lo usamos:

     7  map<string, int>::iterator it;
     8  it = curso.find("gonzalez");
     9  
    10  if (it != curso.end()){
    11  cout << "Hay " << it->second << " " << it->first << " en el curso:\n";
    12  cout << "Llave: " << it->first << " Valor: " << it->second << '\n';
    13  }

Podemos incluso operar usando los iteradores:

    14  it->++second;


<a id="org1a7c601"></a>

### Erase (borrar)

Forma 1:

    15  it = curso.find("perez");
    16  curso.erase(it);

Forma 2:

    17  curso.erase("gonzalez");


<a id="org9a00ce0"></a>

### Recorrer los valores de un vector

Es exactamente igual que en un conjunto:

    18  for (it = curso.begin(); it != curso.end(); ++it){
    19      cout << "Llave: " << it->first << " Valor: " << it->second << '\n';
    20  }


<a id="org487022e"></a>

### Dudas que no dejan dormir

1.  ¿Qué pasa si modifico una llave?

    No se puede, tu código no compilará pues es ilegal hacerlo 👮🚓🚨

2.  ¿Puedo buscar con el second?

    No, en ese caso recomendamos otra estructura, o tener dos maps 👀

3.  ¿Puedo tener un map dentro de un map?

    Si, pero es de psicópata buscar dentro de ese map.

