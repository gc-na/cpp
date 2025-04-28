<!--
Meta Description: # Uso de nullptr en C++: El Puntero Nulo Moderno ## Sinopsis `nullptr` es un literal de puntero nulo introducido en C++11, que proporciona una forma m...
Meta Keywords: nullptr, que, puntero, tipo, std
-->

# Uso de nullptr en C++: El Puntero Nulo Moderno

## Sinopsis
`nullptr` es un literal de puntero nulo introducido en C++11, que proporciona una forma más segura y eficiente de representar un puntero que no apunta a ningún objeto o función. A diferencia del antiguo `NULL`, `nullptr` tiene un tipo propio, lo que ayuda a evitar ambigüedades en las sobrecargas de funciones.

## Documentación
### Propósito
`nullptr` se utiliza para indicar que un puntero no está asociado con ningún objeto. Su uso es recomendable sobre `NULL` por su capacidad de ofrecer una mejor semántica y evitar errores de tipo.

### Uso
- **Declaración de punteros nulos**: Se puede asignar `nullptr` a punteros de cualquier tipo.
- **Sobrecargas de funciones**: Al utilizar `nullptr`, se evita la ambigüedad que puede surgir al usar `NULL`, especialmente en contextos de sobrecarga de funciones.

### Detalles
- **Tipo**: `nullptr` es de tipo `std::nullptr_t`, lo que permite que sea convertido a cualquier tipo de puntero.
- **Compatibilidad**: Aunque `nullptr` se introdujo en C++11, es recomendable utilizarlo en lugar de `NULL` en cualquier código moderno para mejorar la claridad.

## Ejemplos

### Ejemplo 1: Declaración de un puntero nulo
```cpp
#include <iostream>

int main() {
    int* ptr = nullptr; // Declaración de un puntero nulo
    if (ptr == nullptr) {
        std::cout << "El puntero es nulo." << std::endl;
    }
    return 0;
}
```

### Ejemplo 2: Sobrecarga de funciones
```cpp
#include <iostream>

void funcion(int* ptr) {
    std::cout << "Puntero a entero." << std::endl;
}

void funcion(char* ptr) {
    std::cout << "Puntero a carácter." << std::endl;
}

int main() {
    funcion(nullptr); // Llama a la función correcta
    return 0;
}
```

## Explicación
### Problemas comunes
- **Ambigüedad**: Usar `NULL` puede causar que el compilador no sepa qué función sobrecargar elegir, ya que `NULL` puede interpretarse como un entero cero.
- **Compatibilidad con tipos**: Al usar `nullptr`, se asegura que el tipo del puntero sea explícito y se evitan conversiones indeseadas.

### Notas adicionales
- `nullptr` no debe ser utilizado en contextos donde se espera un valor entero, ya que su conversión a entero puede no tener sentido.
- En proyectos que requieren compatibilidad con C++ anterior a C++11, se debe tener cuidado al utilizar `nullptr`, ya que no estará disponible.

## Resumen en una línea
`nullptr` es un literal de puntero nulo en C++ que mejora la claridad y seguridad al indicar punteros que no apuntan a ningún objeto.