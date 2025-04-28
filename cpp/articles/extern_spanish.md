<!--
Meta Description: # Uso de "extern" en C++ ## Sinopsis La palabra clave `extern` en C++ se utiliza para declarar variables y funciones que se definen en otros archivos ...
Meta Keywords: extern, variable, una, cpp, que
-->

# Uso de "extern" en C++

## Sinopsis
La palabra clave `extern` en C++ se utiliza para declarar variables y funciones que se definen en otros archivos o en un ámbito diferente, permitiendo así la vinculación externa entre varios archivos de código.

## Documentación
La palabra clave `extern` se utiliza principalmente para indicar que una variable o función tiene una definición en otro archivo o módulo. Esto es esencial en proyectos grandes donde el código se divide en múltiples archivos para una mejor organización.

### Propósito
El propósito de `extern` es permitir que diferentes archivos fuente compartan variables y funciones, facilitando la modularidad y la reutilización del código.

### Uso
Para declarar una variable como `extern`, se utiliza la siguiente sintaxis:

```cpp
extern tipo nombre_variable;
```

Donde `tipo` es el tipo de dato de la variable y `nombre_variable` es su nombre. La definición real de la variable debe estar presente en otro archivo, o en una sección del mismo archivo, sin la palabra clave `extern`.

Para funciones, `extern` se utiliza de manera similar, aunque no es estrictamente necesario, ya que las funciones son `extern` por defecto.

```cpp
extern tipo nombre_funcion(parametros);
```

### Detalles
- La declaración `extern` solo informa al compilador sobre la existencia de la variable o función, sin asignarle memoria.
- Si se utilizan variables globales en múltiples archivos, `extern` ayuda a evitar conflictos de nombres y problemas de vinculación.

## Ejemplos

### Ejemplo de variable externa

**Archivo1.cpp**
```cpp
#include <iostream>

int variableGlobal = 10; // Definición de la variable

void mostrarVariable() {
    std::cout << "Valor de la variableGlobal: " << variableGlobal << std::endl;
}
```

**Archivo2.cpp**
```cpp
#include <iostream>

// Declaración de la variable externa
extern int variableGlobal;

void modificarVariable() {
    variableGlobal += 5;
}
```

### Ejemplo de función externa

**Archivo1.cpp**
```cpp
#include <iostream>

void funcionExterna(); // Declaración de la función

int main() {
    funcionExterna();
    return 0;
}
```

**Archivo2.cpp**
```cpp
#include <iostream>

void funcionExterna() {
    std::cout << "Esta es una función externa." << std::endl;
}
```

## Explicación
Al usar `extern`, es importante recordar que solo se debe declarar la variable o función, no definirla. Un error común es intentar definir una variable como `extern` en el mismo archivo donde se declara, lo que llevará a errores de compilación. Además, si se intenta acceder a una variable `extern` no definida, también se generará un error.

Otra consideración es que usar `extern` en el ámbito de una función no tiene sentido, ya que se espera que las variables sean locales. En cambio, se usa principalmente para variables y funciones globales.

## Resumen en una línea
La palabra clave `extern` en C++ permite la declaración de variables y funciones definidas en otros archivos, facilitando la vinculación externa y la modularidad del código.