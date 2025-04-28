<!--
Meta Description: # La declaración "throw" en C++: Manejo de Excepciones ## Sinopsis La declaración `throw` en C++ se utiliza para lanzar excepciones, permitiendo manej...
Meta Keywords: std, throw, una, excepción, catch
-->

# La declaración "throw" en C++: Manejo de Excepciones

## Sinopsis
La declaración `throw` en C++ se utiliza para lanzar excepciones, permitiendo manejar errores y condiciones excepcionales de manera controlada. Este mecanismo es fundamental para la programación robusta y la gestión de errores en aplicaciones complejas.

## Documentación
La declaración `throw` se emplea dentro de un bloque de código para indicar que se ha producido un error o una condición excepcional. Al lanzar una excepción, el flujo normal del programa se interrumpe, y el control se transfiere a un bloque de manejo de excepciones correspondiente.

### Propósito
El propósito principal de `throw` es notificar a los bloques de manejo de excepciones (definidos por `try` y `catch`) sobre la ocurrencia de una condición anómala. Esto permite que el programa responda adecuadamente, como liberando recursos o informando al usuario sobre el problema.

### Uso
El uso básico de `throw` es el siguiente:

```cpp
throw expresión;
```

Donde `expresión` puede ser un objeto de un tipo de excepción, que generalmente es una clase derivada de `std::exception` en C++. 

### Detalles
Cuando se lanza una excepción:
- Se busca el bloque `catch` más cercano que coincida con el tipo de la excepción lanzada.
- Si no se encuentra un bloque `catch` adecuado, el programa puede terminar, a menos que se maneje de forma global.

Ejemplo de declaración `throw` en un contexto de función:

```cpp
#include <iostream>
#include <stdexcept>

void verificarEdad(int edad) {
    if (edad < 18) {
        throw std::invalid_argument("La edad debe ser al menos 18 años.");
    }
}

int main() {
    try {
        verificarEdad(15);
    } catch (const std::invalid_argument &e) {
        std::cerr << "Error: " << e.what() << std::endl;
    }
    return 0;
}
```

## Ejemplos
### Ejemplo 1: Lanzar una excepción simple

```cpp
#include <iostream>

void division(int a, int b) {
    if (b == 0) {
        throw "División por cero"; // Lanzando una cadena como excepción
    }
    std::cout << "Resultado: " << a / b << std::endl;
}

int main() {
    try {
        division(10, 0);
    } catch (const char* e) {
        std::cout << "Error capturado: " << e << std::endl;
    }
    return 0;
}
```

### Ejemplo 2: Lanzar una excepción personalizada

```cpp
#include <iostream>
#include <exception>

class MiExcepcion : public std::exception {
public:
    const char* what() const noexcept override {
        return "Ocurrió un error en la aplicación";
    }
};

void funcion() {
    throw MiExcepcion(); // Lanzando una excepción personalizada
}

int main() {
    try {
        funcion();
    } catch (const MiExcepcion &e) {
        std::cout << "Error capturado: " << e.what() << std::endl;
    }
    return 0;
}
```

## Explicación
Al usar `throw`, es importante tener en cuenta varios aspectos:
- **Tipos de Excepción**: Se recomienda usar tipos de excepción derivados de `std::exception` para aprovechar las funcionalidades de la biblioteca estándar.
- **Bloques Try-Catch**: Siempre que se lance una excepción, debe estar acompañada de un bloque `try` y al menos un bloque `catch` para manejarla adecuadamente.
- **No Capturar Todo**: Capturar excepciones sin especificar el tipo (usando `catch (...)`) puede ocultar errores y dificultar el diagnóstico.

### Errores Comunes
- **No Manejar Excepciones**: Si olvidas un bloque `catch`, el programa podría finalizar abruptamente.
- **Lanzar Tipos Incorrectos**: Lanzar tipos no derivados de `std::exception` puede complicar la depuración.

## Resumen en Una Línea
La declaración `throw` en C++ permite lanzar excepciones para manejar errores y condiciones excepcionales de manera controlada.