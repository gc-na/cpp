<!--
Meta Description: # La instrucción "case" en C++ ## Sinopsis La instrucción `case` en C++ es utilizada dentro de una estructura de control `switch` para manejar diferen...
Meta Keywords: case, break, switch, cout, endl
-->

# La instrucción "case" en C++

## Sinopsis
La instrucción `case` en C++ es utilizada dentro de una estructura de control `switch` para manejar diferentes condiciones de manera eficiente y legible, permitiendo la ejecución de diferentes bloques de código según el valor de una expresión.

## Documentación
La instrucción `case` se utiliza en conjunción con la instrucción `switch`. Permite evaluar una expresión y ejecutar diferentes bloques de código dependiendo del valor de esa expresión. Cada caso se define con la palabra clave `case`, seguido de un valor constante y un dos puntos (`:`). La instrucción `break` se utiliza para salir del bloque `switch` después de que se ha ejecutado un caso específico.

### Sintaxis
```cpp
switch (expresión) {
    case valor1:
        // Código a ejecutar si expresión == valor1
        break;
    case valor2:
        // Código a ejecutar si expresión == valor2
        break;
    // Se pueden agregar más casos
    default:
        // Código a ejecutar si no coincide con ningún caso
}
```

### Propósito
El objetivo principal de `case` es proporcionar una forma clara y estructurada de manejar múltiples posibilidades en función de un valor variable, evitando el uso de múltiples sentencias `if` anidadas.

## Ejemplos
### Ejemplo básico de uso
```cpp
#include <iostream>
using namespace std;

int main() {
    int dia = 3;

    switch (dia) {
        case 1:
            cout << "Lunes" << endl;
            break;
        case 2:
            cout << "Martes" << endl;
            break;
        case 3:
            cout << "Miércoles" << endl;
            break;
        case 4:
            cout << "Jueves" << endl;
            break;
        case 5:
            cout << "Viernes" << endl;
            break;
        default:
            cout << "Fin de semana" << endl;
    }

    return 0;
}
```

### Ejemplo con múltiples casos
```cpp
#include <iostream>
using namespace std;

int main() {
    char letra = 'B';

    switch (letra) {
        case 'A':
        case 'E':
        case 'I':
        case 'O':
        case 'U':
            cout << "La letra es una vocal." << endl;
            break;
        default:
            cout << "La letra es una consonante." << endl;
    }

    return 0;
}
```

## Explicación
Al utilizar la instrucción `case`, es importante recordar que cada caso debe ser único. Si se omite el `break`, el programa continuará ejecutando los siguientes casos, lo que puede llevar a resultados inesperados (esto se denomina "fall-through"). Además, los valores después de `case` deben ser constantes y de un tipo que coincida con el tipo de la expresión en el `switch`. 

Es también recomendable incluir un caso `default` para manejar situaciones no previstas, mejorando así la robustez del código.

## Resumen en una línea
La instrucción `case` en C++ permite manejar múltiples condiciones de forma clara y eficiente dentro de un bloque `switch`.