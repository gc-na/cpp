<!--
Meta Description: # Uso de "catch" en C++: Manejo de Excepciones ## Sinopsis El comando "catch" en C++ es utilizado para manejar excepciones, permitiendo a los desarrol...
Meta Keywords: catch, excepción, excepciones, std, que
-->

# Uso de "catch" en C++: Manejo de Excepciones

## Sinopsis
El comando "catch" en C++ es utilizado para manejar excepciones, permitiendo a los desarrolladores capturar errores y excepciones lanzadas durante la ejecución del programa, asegurando así un manejo adecuado de situaciones inesperadas.

## Documentación
En C++, el manejo de excepciones se realiza a través de un conjunto de palabras clave: `try`, `catch` y `throw`. La palabra clave `catch` se utiliza para definir un bloque de código que se ejecutará en caso de que una excepción sea lanzada en un bloque `try`.

### Propósito
El propósito de `catch` es gestionar errores o situaciones excepcionales que pueden ocurrir durante la ejecución del programa, evitando que el programa se detenga abruptamente y permitiendo al desarrollador implementar una lógica de recuperación.

### Uso
La estructura básica para utilizar `catch` es la siguiente:

```cpp
try {
    // Código que puede lanzar una excepción
} catch (tipo_excepcion &e) {
    // Código para manejar la excepción
}
```

- **try**: En este bloque se coloca el código que puede generar una excepción.
- **catch**: Se define el tipo de excepción a capturar y el código que se ejecutará para manejarla.

### Detalles
- Se pueden definir múltiples bloques `catch` para diferentes tipos de excepciones.
- También es posible utilizar un bloque `catch` genérico que capture todas las excepciones si se usa `catch (...)`.
- Las excepciones en C++ son objetos, y se pueden lanzar usando la palabra clave `throw`.

## Ejemplos

### Ejemplo Básico
```cpp
#include <iostream>
#include <stdexcept>

int main() {
    try {
        throw std::runtime_error("Se produjo un error");
    } catch (const std::runtime_error& e) {
        std::cout << "Excepción capturada: " << e.what() << std::endl;
    }
    return 0;
}
```

### Múltiples Capturas
```cpp
#include <iostream>
#include <stdexcept>

int main() {
    try {
        throw 10; // Lanzamos un entero
    } catch (int e) {
        std::cout << "Excepción capturada: " << e << std::endl;
    } catch (const std::runtime_error& e) {
        std::cout << "Excepción de tipo runtime_error: " << e.what() << std::endl;
    }
    return 0;
}
```

## Explicación
Al trabajar con `catch`, es importante tener en cuenta:

- **Orden de los bloques**: Los bloques `catch` deben estar en orden desde el más específico al más genérico. Si se coloca primero un bloque genérico, se ignorarán los bloques más específicos.
- **No capturar excepciones**: Si no se maneja una excepción, el programa terminará su ejecución abruptamente.
- **Excepción no lanzada**: Si no se lanza ninguna excepción en el bloque `try`, el bloque `catch` será ignorado.

## Resumen en una línea
La palabra clave "catch" en C++ se utiliza para manejar excepciones, permitiendo a los desarrolladores capturar y gestionar errores durante la ejecución del programa.