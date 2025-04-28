<!--
Meta Description: # Estructura en C++: Uso y Características de `struct` ## Sinopsis La palabra clave `struct` en C++ se utiliza para definir estructuras, que son tipos...
Meta Keywords: que, miembros, struct, datos, para
-->

# Estructura en C++: Uso y Características de `struct`

## Sinopsis
La palabra clave `struct` en C++ se utiliza para definir estructuras, que son tipos de datos compuestos que permiten agrupar diferentes tipos de datos bajo un mismo nombre. Esto es fundamental para la organización y manejo de datos complejos en programación.

## Documentación
En C++, la palabra clave `struct` se utiliza para crear un nuevo tipo de dato que puede contener variables de diferentes tipos. Las estructuras son similares a las clases en C++, pero por defecto, sus miembros son públicos. Las estructuras son útiles para agrupar datos relacionados y, a menudo, se utilizan para representar entidades en el mundo real.

### Sintaxis
```cpp
struct NombreDeLaEstructura {
    tipoDeDato miembro1;
    tipoDeDato miembro2;
    // ...
};
```

### Propósito
El propósito principal de `struct` es organizar datos de manera coherente, permitiendo así crear tipos de datos que modelen de manera efectiva objetos y entidades.

### Uso
Una vez que se ha definido una estructura, se pueden crear variables de ese tipo, inicializar sus miembros y acceder a ellos mediante el operador de acceso a miembros (`.`).

## Ejemplos
### Ejemplo Básico
```cpp
#include <iostream>
using namespace std;

// Definición de la estructura
struct Persona {
    string nombre;
    int edad;
};

int main() {
    // Creación de una variable de tipo Persona
    Persona persona1;
    
    // Inicialización de miembros
    persona1.nombre = "Juan";
    persona1.edad = 30;
    
    // Acceso a miembros
    cout << "Nombre: " << persona1.nombre << ", Edad: " << persona1.edad << endl;
    
    return 0;
}
```

### Ejemplo con Funciones
```cpp
#include <iostream>
using namespace std;

struct Punto {
    int x;
    int y;
};

// Función para mostrar las coordenadas
void mostrarPunto(Punto p) {
    cout << "Coordenadas: (" << p.x << ", " << p.y << ")" << endl;
}

int main() {
    Punto punto1 = {10, 20};
    mostrarPunto(punto1);
    
    return 0;
}
```

## Explicación
Al usar `struct`, es importante recordar que, a diferencia de las clases, los miembros de una estructura son públicos por defecto. Esto significa que se puede acceder directamente a ellos sin necesidad de métodos de acceso (getters/setters). Sin embargo, si se necesita encapsulación, se puede utilizar la palabra clave `private`.

### Errores Comunes
1. **Olvidar Inicializar Miembros**: Si no se inicializan los miembros de una estructura, pueden contener valores basura.
2. **Confusión con Clases**: Recordar que las estructuras tienen miembros públicos por defecto y las clases tienen miembros privados por defecto.
3. **Pasaje por Valor**: Al pasar estructuras a funciones, se pasan por valor de forma predeterminada, lo que puede ser ineficiente para estructuras grandes. Usar referencias cuando sea necesario.

## Resumen en Una Línea
La palabra clave `struct` en C++ permite definir tipos de datos compuestos que agrupan múltiples variables bajo un solo nombre, facilitando la organización y manipulación de datos relacionados.