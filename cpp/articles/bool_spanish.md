<!--
Meta Description: # El tipo de dato bool en C++ ## Sinopsis El tipo de dato `bool` en C++ es fundamental para la programación lógica, permitiendo almacenar valores bool...
Meta Keywords: bool, que, tipo, valores, dato
-->

# El tipo de dato bool en C++

## Sinopsis
El tipo de dato `bool` en C++ es fundamental para la programación lógica, permitiendo almacenar valores booleanos que representan verdadero (true) o falso (false). Este tipo de dato es esencial en la toma de decisiones y en el control del flujo de un programa.

## Documentación
El tipo `bool` es un tipo de dato incorporado en C++, que se utiliza para representar valores booleanos. Los dos posibles valores que puede almacenar son:
- `true`: Indica que una condición es verdadera.
- `false`: Indica que una condición es falsa.

### Propósito
El tipo `bool` se utiliza principalmente en expresiones condicionales, bucles y en cualquier situación donde se requiera una evaluación lógica. Su uso es crucial en estructuras de control como `if`, `while` y `for`, así como en operaciones booleanas.

### Uso
Para declarar una variable de tipo `bool`, se utiliza la siguiente sintaxis:

```cpp
bool nombre_variable;
```

Los valores booleanos pueden ser asignados directamente, o bien a partir de expresiones que resultan en un valor lógico. Además, cualquier valor distinto de cero se considera `true`, mientras que el valor cero se considera `false`.

## Ejemplos
### Ejemplo 1: Declaración y asignación
```cpp
#include <iostream>
using namespace std;

int main() {
    bool esVerdadero = true;
    bool esFalso = false;

    cout << "Es verdadero: " << esVerdadero << endl; // Salida: Es verdadero: 1
    cout << "Es falso: " << esFalso << endl;         // Salida: Es falso: 0

    return 0;
}
```

### Ejemplo 2: Uso en condiciones
```cpp
#include <iostream>
using namespace std;

int main() {
    int numero = 10;
    bool esPar = (numero % 2 == 0);

    if (esPar) {
        cout << "El número es par." << endl; // Salida: El número es par.
    } else {
        cout << "El número es impar." << endl;
    }

    return 0;
}
```

## Explicación
Al trabajar con el tipo `bool`, es importante tener en cuenta que:
- La comparación `==` devuelve un valor booleano, que puede ser utilizado directamente en condiciones.
- Cualquier expresión que evalúe a cero se considerará `false`, mientras que cualquier otro valor se considerará `true`. Esto puede llevar a confusiones si no se tiene cuidado al trabajar con valores enteros y booleanos.
- En C++, el tipo `bool` ocupa un byte en memoria, aunque en algunas arquitecturas puede ser optimizado a menos espacio.

## Resumen en una línea
El tipo de dato `bool` en C++ permite representar valores de verdad, siendo esencial para la lógica y control de flujo en la programación.