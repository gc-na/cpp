<!--
Meta Description: # Operador "or" en C++ ## Sinopsis El operador lógico "or" en C++ es un operador utilizado para realizar operaciones lógicas entre dos expresiones boo...
Meta Keywords: operador, condiciones, una, que, expresiones
-->

# Operador "or" en C++

## Sinopsis
El operador lógico "or" en C++ es un operador utilizado para realizar operaciones lógicas entre dos expresiones booleanas, devolviendo verdadero si al menos una de las expresiones es verdadera.

## Documentación
El operador "or" forma parte de los operadores lógicos en C++. Su propósito principal es evaluar dos condiciones y retornar un valor booleano. Este operador es equivalente al operador `||`, pero ofrece una alternativa más legible, especialmente para quienes vienen de otros lenguajes de programación.

### Uso
El operador "or" se utiliza en las expresiones condicionales, permitiendo combinar múltiples condiciones. La sintaxis es la siguiente:

```cpp
resultado = expresion1 or expresion2;
```

Donde `resultado` será `true` si `expresion1` o `expresion2` (o ambas) son verdaderas.

### Detalles
- **Tipo de retorno**: El operador "or" devuelve un valor de tipo booleano (`true` o `false`).
- **Prioridad**: Tiene una prioridad baja en comparación con los operadores aritméticos, pero mayor que el operador de asignación.
- **Short-circuit Evaluation**: Si la primera expresión evalúa como `true`, la segunda expresión no se evalúa, lo que puede ser útil para evitar errores en condiciones complejas.

## Ejemplos

### Ejemplo 1: Uso básico de "or"
```cpp
#include <iostream>
using namespace std;

int main() {
    bool a = true;
    bool b = false;

    if (a or b) {
        cout << "Al menos una de las condiciones es verdadera." << endl;
    }

    return 0;
}
```

### Ejemplo 2: Evaluación de múltiples condiciones
```cpp
#include <iostream>
using namespace std;

int main() {
    int x = 10;
    int y = 5;

    if (x > 15 or y < 10) {
        cout << "Al menos una de las condiciones es verdadera." << endl;
    } else {
        cout << "Ambas condiciones son falsas." << endl;
    }

    return 0;
}
```

## Explicación
Al utilizar el operador "or", es fundamental entender que puede haber confusiones con el operador `&&` (y). Un error común es suponer que "or" evaluará ambas condiciones en todos los casos; sin embargo, debido a la evaluación corta, si la primera condición es verdadera, la segunda no se ejecuta.

Además, es importante recordar que el operador "or" es un operador lógico que se utiliza exclusivamente con expresiones booleanas. Intentar usarlo con tipos de datos no booleanos puede resultar en errores de compilación.

## Resumen en una línea
El operador "or" en C++ permite realizar operaciones lógicas, devolviendo verdadero si al menos una de las expresiones evaluadas es verdadera.