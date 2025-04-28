<!--
Meta Description: # Operadores en C++: Una Guía Completa ## Sinopsis Los operadores en C++ son símbolos que permiten realizar operaciones sobre variables y valores. Son...
Meta Keywords: operadores, los, bit, que, asignación
-->

# Operadores en C++: Una Guía Completa

## Sinopsis
Los operadores en C++ son símbolos que permiten realizar operaciones sobre variables y valores. Son fundamentales para la manipulación de datos y la construcción de expresiones.

## Documentación
En C++, los operadores se clasifican en varias categorías según su función. A continuación se detallan las principales categorías de operadores:

1. **Operadores Aritméticos**: Realizan cálculos matemáticos.
   - `+` (suma)
   - `-` (resta)
   - `*` (multiplicación)
   - `/` (división)
   - `%` (módulo)

2. **Operadores de Comparación**: Comparan dos valores y devuelven un resultado booleano.
   - `==` (igual a)
   - `!=` (diferente de)
   - `<` (menor que)
   - `>` (mayor que)
   - `<=` (menor o igual que)
   - `>=` (mayor o igual que)

3. **Operadores Lógicos**: Operan sobre valores booleanos.
   - `&&` (y lógico)
   - `||` (o lógico)
   - `!` (no lógico)

4. **Operadores de Asignación**: Asignan valores a variables.
   - `=` (asignación simple)
   - `+=` (suma y asignación)
   - `-=` (resta y asignación)
   - `*=` (multiplicación y asignación)
   - `/=` (división y asignación)
   - `%=` (módulo y asignación)

5. **Operadores Unarios**: Operan sobre un solo operando.
   - `++` (incremento)
   - `--` (decremento)
   - `-` (negación)

6. **Operadores Bit a Bit**: Manipulan los bits de los operandos.
   - `&` (AND bit a bit)
   - `|` (OR bit a bit)
   - `^` (XOR bit a bit)
   - `~` (complemento a uno)
   - `<<` (desplazamiento a la izquierda)
   - `>>` (desplazamiento a la derecha)

## Ejemplos
A continuación se presentan algunos ejemplos de cómo utilizar los operadores en C++:

```cpp
#include <iostream>
using namespace std;

int main() {
    int a = 10, b = 5;

    // Operadores Aritméticos
    cout << "Suma: " << (a + b) << endl; // 15
    cout << "Resta: " << (a - b) << endl; // 5
    cout << "Multiplicación: " << (a * b) << endl; // 50
    cout << "División: " << (a / b) << endl; // 2
    cout << "Módulo: " << (a % b) << endl; // 0

    // Operadores de Comparación
    cout << "a es igual a b? " << (a == b) << endl; // 0 (false)
    
    // Operadores Lógicos
    cout << "a > b y a < 20? " << ((a > b) && (a < 20)) << endl; // 1 (true)

    return 0;
}
```

## Explicación
Es importante tener en cuenta algunos aspectos al trabajar con operadores en C++:

- **Prioridad de Operadores**: La evaluación de expresiones se basa en la precedencia de los operadores. Por ejemplo, en una expresión como `a + b * c`, la multiplicación se calcula antes de la suma.
- **Conversión de Tipos**: Al utilizar operadores, puede haber conversiones implícitas de tipos. Esto puede llevar a resultados inesperados, especialmente en operaciones aritméticas entre tipos enteros y de punto flotante.
- **Operadores Lógicos**: Los operadores lógicos (`&&`, `||`, `!`) pueden utilizar la evaluación corta (short-circuit evaluation), lo que significa que no siempre se evalúan todos los operandos.

## Resumen en una línea
Los operadores en C++ son herramientas esenciales para realizar operaciones matemáticas, lógicas y de comparación en programas.