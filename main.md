Estructuras lineales
====================

Vectores
--------

------------------------------------------------------------------------

Los vectores son como arreglos, excepto de que el tamaño es dinámico, es
decir, se puede cambiar. Incluimos la librería:

    #include <vector>

Inicializamos nuestro vector "vec":

    int n = 3;
    vector < int > vec(n, 0); // Inicializa un vector de tamaño 3 con todos sus valores = 0. Tanto el tamaño como valor son opcionales.

### Asignar un valor

    vec[2] = 1; // Asigna el valor "1" al índice 2 (es decir, al 3er valor del vector)

### push back (empujar atrás)

Si no sabemos el tamaño de nuestro vector, podemos simplemente usar
push<sub>back</sub>(valor); para enviar es valor al final del vector.

    vec.push_back(1); // Inserta un 1 al final del vector

Por ejemplo, se podría usar en un for, sin necesidad de inicializar el
vector con una cantidad de valores.

    vector <int> vec2;
    int n;
    cin >> n;
    for (int i = 0; i < n; ++i){
        int valor;
        cin >> valor;
        vec2.push_back();
    }

### pop back (quitar atrás)

Elimina el último valor del vector.

    vec.pop_back(); // En este caso, elimina el 1

### insert (insertar)

Podemos insertar un valor entre dos indices de un vector. El problema de
esto es que mueve todos los valores que estén más adelante, lo que es
lento.

    vec.insert(vec.begin() + 2, 4); // Inserta el valor 4 al índice 2

### erase (borrar)

Borra un dato del vector. Al igual que el insert, tiene que mover todos
los datos siguientes (esta vez a la derecha).

    vec.erase(vec.begin() + 2); // Elimina el valor con índice 2, en nuestro caso, el 4 que insertamos antes.

Stacks (pilas)
--------------

------------------------------------------------------------------------

La pila es una estructura de datos lineal al que sólo puedes acceder al
último elemento que fue insertado. Imagina una pila de platos, por
ejemplo.

    stack < int > pilita;

### push (empujar)

Empuja un dato a la cima de la pila.

    pilita.push(8); // Empuja un 8 a la cima de la pila.

### top (cima)

Lee lo que hay en la cima de la pila.

    pilita.top(); // Retorna el 8.

### pop (quitar)

Remueve el dato de la cima de la pila.

    pilita.pop(); // Remueve el 8.

### empty (vacío)

Retorna 1 si la pila está vacía, de lo contrario retorna 0.

    pilita.empty(); // Retorna 1 ya que nuestra pila está vacía.

### size (tamaño)

Retorna el tamaño de nuestra pila.

    pilita.size(); // Retorna 0 ya que nuestra pila no tiene datos.

Queues (colas)
--------------

------------------------------------------------------------------------

La cola es una estructura de datos lineal al que sólo puedes acceder al
primer elemento que fue insertado. Imagina una fila de una caja de un
supermercado, por ejemplo.

    queue < int > colita;

### push (empujar)

Añade un dato al final de la cola.

    colita.push(5);
    colita.push(4);
    colita.push(3);
    colita.push(2);
    colita.push(1);

### front (frente)

Lee el dato que está al frente de la cola.

    colita.front(); // Retorna 5, ya que fue lo primero que empujamos a la cola.

### pop (quitar)

Remueve el dato que está al frente de la cola

    colita.pop();   // Remueve el 5
    colita.front(); // Retorna 4, ya que fue lo segundo que empujamos a la cola (y que ahora está primero).

### empty (vacío)

Retorna 1 si la cola está vacía, de lo contrario retorna 0.

    colita.empty(); // Retorna 1 ya que nuestra cola está vacía.

### size (tamaño)

Retorna el tamaño de nuestra cola.

    colita.size(); // Retorna 0 ya que nuestra cola no tiene datos.

Estructuras en forma de árbol
=============================

Véase: arbol binario

Set (conjunto)
--------------

------------------------------------------------------------------------

No permite que hayan elementos repetidos.

### Inicialización

Incluimos la librería:

    #include <set>

Inicializamos nuestro conjunto:

    set < int > conjunto; // int puede ser reemplazado con cualquier otro tipo de dato

### insert (Insertar)

Inserta un dato. Retorna un par de elementos, el primero siendo el
iterador del valor insertado y el segundo siendo un bool que marca si es
que ya existía o no. En el ejemplo de abajo, usamos .second para
comprobar si se insertó correctamente o no.

    if (conjunto.insert(10).second) // Retorna TRUE ya que no estaba anteriormente
        cout << "ganai\n"; if (conjunto.insert(10).second); // Retorna FALSE ya que ya había un 10.
    cout << "no ganai\n";
    conjunto.insert(20);
    conjunto.insert(40);
    conjunto.insert(30);
    conjunto.insert(11);

### find (Encontrar)

Busca un elemento en el set y si lo encuentra retorna un iterador al
valor. De lo contrario, retorna conjunto.end();

    if (conjunto.find(10) != conjunto.end())
        cout << "ganai\n";

### erase (borrar)

Puedes borrar un valor si le entregas el iterador al valor.

    set < int >::iterator it = conjunto.find(11);
    if (it != conjunto.end())
        conjunto.erase(it);

### Iterar a través de un conjunto

Puedes iterar a través de un conjunto con los valores ya ordenados con
un iterador:

    // Imprime 10 11 20 30 40
    for (it = conjunto.begin(); it != conjunto.end(); ++it)
        cout << *it << " ";
    cout << '\n';

Map (mapa, tabla de hashing)
----------------------------

------------------------------------------------------------------------

Toma dos datos, una llave y un valor. Puedes buscar una llave en tiempo
logarítmico con la implementación de la STL. Pero con otras
implementaciones se puede hacer en tiempo constante. Las llaves no se
pueden repetir.

### Ejemplo cotidiano

Libros:

| Título (Llave)               | Autor (Valor)   |
|------------------------------|-----------------|
| The C Programming Language   | Brian Keringhan |
| The AWK Programming Language | Brian Keringhan |
| 1984                         | George Orwell   |

Curso:

| Apellido | Cantidad de alumnos con el apellido |
|----------|-------------------------------------|
| Gonzalez | 3                                   |
| Perez    | 2                                   |

### Inicializar

Incluimos la librería de map:

    #include <map>

Inicializamos el mapa curso:

    map<string, int> curso;

### Insert (insertar)

Forma 1:

    curso["perez"] = 1;

Forma 2:

    curso.insert(pair<string, int>("gonzalez, 3"));

### Operar con los valores

Se puede operar con el valor tomando la llave. Ejemplo 1:

    ++curso.["perez"]; // Incrementar el valor de la llave perez, por ejemplo.

Ejemplo 2:

    cout << curso.["perez"] << endl; // El output será 2.

Cuidado con operar con valores no existentes, pues los inicializará de
una forma inesperada.

### Find (encontrar)

Retorna un iterador, si no lo encuentra, apunta a map.end() Asignamos el
iterador it a gonzalez, y luego lo usamos:

    map<string, int>::iterator it;
    it = curso.find("gonzalez");

    if (it != curso.end()){
    cout << "Hay " << it->second << " " << it->first << " en el curso:\n";
    cout << "Llave: " << it->first << " Valor: " << it->second << '\n';
    }

Podemos incluso operar usando los iteradores:

    it->++second;

### Erase (borrar)

Forma 1:

    it = curso.find("perez");
    curso.erase(it);

Forma 2:

    curso.erase("gonzalez");

### Recorrer los valores de un vector

Es exactamente igual que en un conjunto:

    for (it = curso.begin(); it != curso.end(); ++it){
        cout << "Llave: " << it->first << " Valor: " << it->second << '\n';
    }

### Dudas que no dejan dormir

1.  ¿Qué pasa si modifico una llave?

    No se puede, tu código no compilará pues es ilegal hacerlo 👮🚓🚨

2.  ¿Puedo buscar con el second?

    No, en ese caso recomendamos otra estructura, o tener dos maps 👀

3.  ¿Puedo tener un map dentro de un map?

    Si, pero es de psicópata buscar dentro de ese map.
