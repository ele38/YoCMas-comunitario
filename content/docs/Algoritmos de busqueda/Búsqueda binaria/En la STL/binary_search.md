+++
title = "binary_search()"
author = ["Comunidad YoC+"]
draft = false
weight = 4002
+++

La librería STL ya incluye binary search, si queremos saber si el valor
3 está en un vector, podemos ejecutar:

{{< highlight cpp "linenos=table, linenostart=1" >}}
vector<int> v{1,2,5,7};
if (binary_search (v.begin(), v.end(), 3)) {
    cout << "Se encuentra el valor 3 en nuestro vector\n";
}
else {
    cout << "No hay ningún 3 en nuestro vector\n";
}
{{< /highlight >}}

Retorna un _bool_.
