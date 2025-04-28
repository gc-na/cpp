<!--
Meta Description: # Estructura de control "while" en C++ ## Sinopsis El comando "while" es una estructura de control en C++ que permite ejecutar un bloque de código rep...
Meta Keywords: bucle, condición, while, contador, que
-->

# Estructura de control "while" en C++

## Sinopsis
El comando "while" es una estructura de control en C++ que permite ejecutar un bloque de código repetidamente mientras una condición específica sea verdadera. Es fundamental en la programación para manejar bucles y realizar iteraciones.

## Documentación
La estructura de control "while" en C++ se utiliza para ejecutar un bloque de código de manera repetitiva hasta que la condición especificada se evalúe como falsa. La sintaxis básica es la siguiente:

```cpp
while (condición) {
    // Bloque de código a ejecutar
}
```

### Propósito
El propósito del bucle "while" es permitir que el programa realice tareas repetitivas sin la necesidad de escribir el mismo código varias veces, facilitando así la eficiencia y la legibilidad del código.

### Uso
1. **Inicialización**: Antes de entrar en el bucle, es común inicializar variables que se utilizarán en la condición.
2. **Condición**: El bucle se ejecuta mientras la condición sea verdadera. Si la condición es falsa desde el principio, el bloque de código dentro del bucle no se ejecuta.
3. **Modificación**: Es esencial modificar alguna variable dentro del bloque del bucle, de lo contrario, se puede crear un bucle infinito.

### Detalles
- El bucle "while" es útil cuando no se conoce de antemano cuántas veces debe ejecutarse el bucle.
- La condición se evalúa antes de cada iteración del bucle.
- Si la condición es falsa en la primera evaluación, el bloque de código no se ejecutará ni una sola vez.

## Ejemplos
### Ejemplo 1: Bucle simple
```cpp
#include <iostream>
using namespace std;

int main() {
    int contador = 0;

    while (contador < 5) {
        cout << "Contador: " << contador << endl;
        contador++;
    }

    return 0;
}
```
**Salida:**
```
Contador: 0
Contador: 1
Contador: 2
Contador: 3
Contador: 4
```

### Ejemplo 2: Bucle hasta una condición
```cpp
#include <iostream>
using namespace std;

int main() {
    int numero;

    cout << "Introduce un número positivo (0 para salir): ";
    cin >> numero;

    while (numero != 0) {
        cout << "Número: " << numero << endl;
        cout << "Introduce otro número positivo (0 para salir): ";
        cin >> numero;
    }

    return 0;
}
```

## Explicación
Al usar el bucle "while", es crucial tener en cuenta ciertas consideraciones:
- **Bucle infinito**: Si la condición nunca se vuelve falsa, el bucle continuará indefinidamente y puede provocar que el programa se bloquee. Asegúrate de que la lógica dentro del bucle cambie el estado de las variables involucradas en la condición.
- **Evaluación de la condición**: La condición se evalúa antes de cada iteración. Esto significa que si se requiere que el bucle se ejecute al menos una vez, es más apropiado usar "do while", que evalúa la condición después de ejecutar el bloque de código.

## Resumen en una línea
El bucle "while" en C++ permite ejecutar repetidamente un bloque de código mientras una condición específica sea verdadera, siendo esencial para la creación de estructuras de control eficientes.