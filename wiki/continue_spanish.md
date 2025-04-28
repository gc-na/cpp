<!--
Meta Description: # La instrucción "continue" en C++: Uso y Ejemplos ## Sinopsis La instrucción `continue` en C++ se utiliza dentro de estructuras de control de bucles ...
Meta Keywords: continue, del, iteración, bucle, instrucción
-->

# La instrucción "continue" en C++: Uso y Ejemplos

## Sinopsis
La instrucción `continue` en C++ se utiliza dentro de estructuras de control de bucles para omitir la iteración actual y continuar con la siguiente iteración del bucle.

## Documentación
La instrucción `continue` es una parte fundamental de los bucles en C++, como `for`, `while` y `do-while`. Su propósito principal es permitir que el flujo de ejecución salte el resto del código dentro del bucle para la iteración actual y pase inmediatamente a la siguiente iteración.

### Uso
La sintaxis básica de la instrucción `continue` es la siguiente:

```cpp
continue;
```

Cuando se encuentra una instrucción `continue`, el control del programa salta al final del bloque del bucle, y se evalúa la condición del bucle para determinar si se debe continuar con la siguiente iteración.

#### Ejemplo en un bucle `for`:
```cpp
for (int i = 0; i < 10; i++) {
    if (i % 2 == 0) {
        continue; // Salta a la siguiente iteración si 'i' es par
    }
    std::cout << i << std::endl; // Solo imprime números impares
}
```

## Ejemplos
### Ejemplo 1: Bucle `for`
```cpp
#include <iostream>

int main() {
    for (int i = 0; i < 10; i++) {
        if (i == 5) {
            continue; // Salta la iteración cuando 'i' es 5
        }
        std::cout << i << " ";
    }
    return 0;
}
```
**Salida:** `0 1 2 3 4 6 7 8 9`

### Ejemplo 2: Bucle `while`
```cpp
#include <iostream>

int main() {
    int i = 0;
    while (i < 10) {
        i++;
        if (i % 3 == 0) {
            continue; // Salta la iteración cuando 'i' es múltiplo de 3
        }
        std::cout << i << " ";
    }
    return 0;
}
```
**Salida:** `1 2 4 5 7 8 10`

## Explicación
Al utilizar `continue`, es importante tener en cuenta algunas consideraciones:
- **Ubicación de `continue`**: Debe estar dentro de un bucle. De lo contrario, generará un error de compilación.
- **Condiciones de salida**: Si no se manejan adecuadamente las condiciones del bucle, se pueden crear bucles infinitos.
- **Claridad del código**: El uso excesivo de `continue` puede dificultar la lectura del código. Es recomendable usarlo con moderación y asegurarse de que el flujo del programa sea claro para otros desarrolladores.

## Resumen en una línea
La instrucción `continue` en C++ permite omitir la iteración actual de un bucle y continuar con la siguiente iteración, mejorando el control del flujo de ejecución.