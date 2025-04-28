<!--
Meta Description: # Clase en C++: Definición, Uso y Ejemplos ## Sinopsis La clase en C++ es un concepto fundamental de la programación orientada a objetos que permite l...
Meta Keywords: clase, que, una, atributos, clases
-->

# Clase en C++: Definición, Uso y Ejemplos

## Sinopsis
La clase en C++ es un concepto fundamental de la programación orientada a objetos que permite la creación de tipos de datos complejos, encapsulando datos y funciones en una única entidad.

## Documentación
En C++, una clase es una plantilla o modelo que define un tipo de objeto. Una clase puede contener atributos (variables) y métodos (funciones) que operan sobre esos atributos. La definición de una clase se realiza utilizando la palabra clave `class`, seguida del nombre de la clase y un bloque de código entre llaves que contiene sus miembros.

### Propósito
El propósito principal de una clase es proporcionar un marco para crear objetos que representan entidades del mundo real, facilitando la reutilización de código y la organización de programas complejos.

### Uso
Para definir una clase en C++, se utiliza la siguiente sintaxis básica:

```cpp
class NombreClase {
public:
    // Atributos
    Tipo atributo;

    // Métodos
    void metodo();
};
```

### Detalles
- **Atributos**: Son las variables que pertenecen a la clase. Pueden ser de cualquier tipo de datos, incluidos tipos primitivos, otras clases, o punteros.
- **Métodos**: Son funciones definidas dentro de la clase que pueden manipular los atributos de la clase o ejecutar acciones específicas.
- **Especificadores de acceso**: Las clases pueden tener miembros `public`, `protected` y `private`, que controlan la visibilidad y el acceso a los miembros de la clase.

## Ejemplos
### Ejemplo Básico de Clase

```cpp
#include <iostream>
using namespace std;

class Persona {
public:
    string nombre;
    int edad;

    void mostrarInformacion() {
        cout << "Nombre: " << nombre << ", Edad: " << edad << endl;
    }
};

int main() {
    Persona persona1;
    persona1.nombre = "Juan";
    persona1.edad = 30;
    persona1.mostrarInformacion();

    return 0;
}
```

### Ejemplo con Constructor

```cpp
#include <iostream>
using namespace std;

class Coche {
public:
    string marca;
    string modelo;

    // Constructor
    Coche(string m, string mo) {
        marca = m;
        modelo = mo;
    }

    void mostrarDetalles() {
        cout << "Marca: " << marca << ", Modelo: " << modelo << endl;
    }
};

int main() {
    Coche coche1("Toyota", "Corolla");
    coche1.mostrarDetalles();

    return 0;
}
```

## Explicación
Al utilizar clases, es importante tener en cuenta lo siguiente:

- **Inicialización**: Si no se inicializan los atributos de una clase, pueden contener valores indeterminados.
- **Encapsulamiento**: Es recomendable utilizar modificadores de acceso para proteger los atributos y proporcionar métodos públicos para acceder a ellos.
- **Herencia**: C++ permite la herencia entre clases, lo que facilita la creación de jerarquías de clases y la reutilización de código.

## Resumen en una línea
Las clases en C++ son estructuras que permiten encapsular datos y funciones, facilitando la programación orientada a objetos.