<!--
Meta Description: # El Tipo de Dato "int" en C++ ## Sinopsis El tipo de dato `int` en C++ es una de las construcciones más fundamentales para representar números entero...
Meta Keywords: int, tipo, enteros, que, dato
-->

# El Tipo de Dato "int" en C++

## Sinopsis
El tipo de dato `int` en C++ es una de las construcciones más fundamentales para representar números enteros en programación. Es ampliamente utilizado por su eficiencia y facilidad de uso.

## Documentación
El `int` (abreviatura de "integer", que significa "entero" en inglés) es un tipo de dato primitivo en C++ que se utiliza para almacenar números enteros, es decir, números sin parte decimal. Este tipo de dato puede ser positivo, negativo o cero. La representación de `int` en C++ generalmente utiliza 4 bytes (32 bits), aunque esto puede variar según la plataforma y el compilador.

### Propósito
El propósito del tipo `int` es proporcionar una manera eficiente de manejar operaciones aritméticas y lógicas con números enteros en programas de C++. Gracias a su naturaleza binaria, los cálculos con `int` son rápidos y requieren menos recursos computacionales en comparación con tipos de datos más complejos.

### Uso
Para declarar una variable de tipo `int`, se utiliza la siguiente sintaxis:

```cpp
int nombreVariable;
```

Los valores enteros pueden ser asignados a la variable de la siguiente manera:

```cpp
int edad = 25;
int temperatura = -5;
int contador = 0;
```

## Ejemplos
Aquí hay algunos ejemplos básicos de cómo utilizar el tipo `int` en C++:

```cpp
#include <iostream>

int main() {
    int a = 10;
    int b = 20;
    int suma = a + b;

    std::cout << "La suma de " << a << " y " << b << " es " << suma << std::endl;

    return 0;
}
```

### Ejemplo de uso en un bucle
```cpp
#include <iostream>

int main() {
    for (int i = 0; i < 5; i++) {
        std::cout << "Número: " << i << std::endl;
    }

    return 0;
}
```

## Explicación
Aunque el tipo `int` es bastante robusto, hay algunos aspectos que los programadores deben tener en cuenta:

1. **Rango de Valores**: El rango de un `int` típicamente va de -2,147,483,648 a 2,147,483,647 en sistemas de 32 bits. Superar este rango puede causar un desbordamiento, lo que resulta en comportamientos inesperados.

2. **Tipos de Enteros**: C++ también ofrece otros tipos de enteros como `short`, `long` y `long long`, que pueden ser utilizados para almacenar valores enteros en rangos diferentes. Es importante elegir el tipo adecuado según las necesidades del programa.

3. **Valor por Defecto**: Las variables de tipo `int` no inicializadas tienen un valor indeterminado, lo que puede llevar a errores si se intentan utilizar antes de asignarles un valor.

4. **Operaciones**: Las operaciones aritméticas sobre `int` son simples, pero se debe tener cuidado con la división, ya que dividir dos enteros siempre resulta en un entero, truncando cualquier parte decimal.

## Resumen en una línea
El tipo de dato `int` en C++ es fundamental para almacenar y manipular números enteros de manera eficiente en programación.