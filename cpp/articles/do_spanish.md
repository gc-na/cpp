<!--
Meta Description: # Uso del comando "do" en C++ ## Sinopsis El comando `do` en C++ es parte de la estructura de control de bucles que permite ejecutar un bloque de códi...
Meta Keywords: que, condición, bucle, código, bloque
-->

# Uso del comando "do" en C++

## Sinopsis
El comando `do` en C++ es parte de la estructura de control de bucles que permite ejecutar un bloque de código repetidamente mientras se cumpla una condición. Específicamente, se utiliza en la construcción del bucle `do-while`, que garantiza que el bloque de código se ejecute al menos una vez.

## Documentación
El bucle `do-while` en C++ se utiliza para ejecutar un conjunto de instrucciones repetidamente, pero a diferencia del bucle `while`, el bloque de código dentro de `do` se ejecuta primero antes de evaluar la condición. Esto es útil cuando se necesita que el código se ejecute al menos una vez, independientemente de si la condición es verdadera o falsa al inicio.

### Sintaxis
```cpp
do {
    // Bloque de código a ejecutar
} while (condición);
```

- **Bloque de código**: Contiene las instrucciones que se ejecutarán.
- **condición**: Una expresión booleana que se evalúa después de ejecutar el bloque de código. Si es verdadera, el bucle se repetirá; si es falsa, el bucle terminará.

### Ejemplo de uso
```cpp
#include <iostream>

int main() {
    int contador = 0;

    do {
        std::cout << "El contador es: " << contador << std::endl;
        contador++;
    } while (contador < 5);

    return 0;
}
```
En este ejemplo, el programa imprimirá los valores del contador del 0 al 4. La condición `contador < 5` se evalúa después de que el bloque de código se haya ejecutado.

## Explicación
Un aspecto importante del bucle `do-while` es que siempre ejecuta el bloque de código al menos una vez. Esto puede ser ventajoso en situaciones donde es necesario que cierta lógica se ejecute antes de validar la condición. Sin embargo, se debe tener cuidado con la condición de salida, ya que si esta nunca se cumple, se puede crear un bucle infinito.

### Errores comunes
- **Bucle infinito**: Si la condición nunca se convierte en falsa, el bucle se ejecutará indefinidamente. Asegúrate de que la lógica dentro del bucle modifique la variable de control de manera que eventualmente la condición se evalúe como falsa.
- **Olvidar el punto y coma**: Es común olvidar el punto y coma al final de la condición del bucle `do-while`, lo que provocará errores de compilación.

## Resumen en una línea
El comando `do` en C++ se utiliza para crear bucles que ejecutan un bloque de código al menos una vez, evaluando la condición después de cada ejecución.