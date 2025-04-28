<!--
Meta Description: # El Modificador "friend" en C++ ## Sinopsis El modificador `friend` en C++ permite que una función o clase acceda a los miembros privados y protegido...
Meta Keywords: clase, friend, que, clasea, int
-->

# El Modificador "friend" en C++

## Sinopsis
El modificador `friend` en C++ permite que una función o clase acceda a los miembros privados y protegidos de otra clase, facilitando la interacción entre diferentes componentes del código.

## Documentación
El modificador `friend` se utiliza para declarar que una función o una clase es amiga de otra clase. Esto significa que la función o clase amiga tiene acceso a los miembros privados y protegidos de la clase que la declara como amiga. Esta característica es útil en situaciones donde se necesita una interacción cercana entre clases que no deberían ser completamente públicas.

### Propósito
El propósito principal del modificador `friend` es permitir que ciertas funciones o clases accedan a la información encapsulada de otras clases, promoviendo así la colaboración entre componentes del sistema sin romper la encapsulación.

### Uso
Para declarar una función o clase como amiga, se utiliza la palabra clave `friend` dentro de la definición de la clase que otorga el acceso. La declaración de amistad no es recíproca; si la Clase A declara a la Clase B como amiga, no significa que la Clase B tenga acceso a los miembros de la Clase A.

#### Ejemplo de declaración:
```cpp
class ClaseA;

class ClaseB {
public:
    void mostrarClaseA(ClaseA &obj);
};

class ClaseA {
private:
    int dato;

public:
    ClaseA(int d) : dato(d) {}

    friend void ClaseB::mostrarClaseA(ClaseA &obj);
};
```

## Ejemplos
A continuación se presentan ejemplos básicos de cómo utilizar el modificador `friend`.

### Ejemplo 1: Función amiga
```cpp
#include <iostream>
using namespace std;

class Caja {
private:
    int ancho;
    int alto;

public:
    Caja(int a, int h) : ancho(a), alto(h) {}

    friend void mostrarCaja(Caja &c);
};

void mostrarCaja(Caja &c) {
    cout << "Ancho: " << c.ancho << ", Alto: " << c.alto << endl;
}

int main() {
    Caja c(5, 10);
    mostrarCaja(c);
    return 0;
}
```

### Ejemplo 2: Clase amiga
```cpp
#include <iostream>
using namespace std;

class ClaseB; // Declaración anticipada

class ClaseA {
private:
    int dato;

public:
    ClaseA(int d) : dato(d) {}

    friend class ClaseB; // ClaseB es amiga de ClaseA
};

class ClaseB {
public:
    void mostrarDato(ClaseA &a) {
        cout << "El dato es: " << a.dato << endl;
    }
};

int main() {
    ClaseA a(42);
    ClaseB b;
    b.mostrarDato(a);
    return 0;
}
```

## Explicación
Un error común al usar `friend` es asumir que la amistad es bidireccional. Si una clase A declara a B como amiga, B no tiene acceso a los miembros privados de A a menos que se declare explícitamente. Además, el uso excesivo de `friend` puede llevar a un diseño menos limpio y más difícil de mantener, ya que puede romper la encapsulación.

### Notas adicionales
- La declaración de amistad se aplica a la clase completa, no a instancias individuales.
- Las funciones globales pueden ser declaradas como amigas de clases, permitiendo así el acceso a sus miembros.
- La amistad no se hereda; si una clase C hereda de B, C no tendrá acceso a los miembros privados de A a menos que A lo declare explícitamente.

## Resumen en una línea
El modificador `friend` en C++ permite a funciones y clases acceder a los miembros privados de otras clases, facilitando la colaboración en el código.