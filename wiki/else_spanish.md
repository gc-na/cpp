<!--
Meta Description: # Else en C++: Controlando el Flujo de Ejecución ## Sinopsis La instrucción `else` en C++ permite la ejecución condicional de bloques de código, propo...
Meta Keywords: else, condición, código, una, para
-->

# Else en C++: Controlando el Flujo de Ejecución

## Sinopsis
La instrucción `else` en C++ permite la ejecución condicional de bloques de código, proporcionando una alternativa a las declaraciones `if` cuando la condición evaluada resulta ser falsa.

## Documentación
La declaración `else` se utiliza para extender la funcionalidad de las instrucciones condicionales `if`. Su propósito es ejecutar un bloque de código diferente si la condición especificada en la instrucción `if` no se cumple. La sintaxis básica es la siguiente:

```cpp
if (condición) {
    // Código a ejecutar si la condición es verdadera
} else {
    // Código a ejecutar si la condición es falsa
}
```

### Uso
- **Condiciones múltiples**: `else` puede ser combinado con `if` para manejar múltiples condiciones usando `else if`.
- **Bloques anidados**: Se pueden anidar múltiples instrucciones `if-else` para crear estructuras de decisión más complejas.

### Detalles
- La declaración `else` no toma condiciones; simplemente se ejecuta si la condición del `if` correspondiente es falsa.
- Se puede omitir el bloque `else`, pero no se puede usar sin un bloque `if` asociado.

## Ejemplos
### Ejemplo 1: Uso básico de `else`
```cpp
#include <iostream>
using namespace std;

int main() {
    int numero = 10;

    if (numero > 0) {
        cout << "El número es positivo." << endl;
    } else {
        cout << "El número es negativo o cero." << endl;
    }

    return 0;
}
```

### Ejemplo 2: Uso de `if-else if-else`
```cpp
#include <iostream>
using namespace std;

int main() {
    int numero = 0;

    if (numero > 0) {
        cout << "El número es positivo." << endl;
    } else if (numero < 0) {
        cout << "El número es negativo." << endl;
    } else {
        cout << "El número es cero." << endl;
    }

    return 0;
}
```

## Explicación
Al utilizar `else`, es importante considerar:

- **Orden de evaluación**: Asegúrate de que las condiciones están en el orden correcto. Si una condición anterior es verdadera, el bloque `else` no se ejecutará.
- **Uso de llaves**: Aunque en C++ no es obligatorio usar llaves para bloques de código de una sola línea, es una buena práctica hacerlo para evitar errores en la ejecución.
- **Combinación con `switch`**: `else` no se puede usar con la instrucción `switch`, ya que esta última tiene un flujo de control diferente.

## Resumen en una línea
La instrucción `else` en C++ permite la ejecución de un bloque de código alternativo si la condición de una declaración `if` resulta ser falsa.