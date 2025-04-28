<!--
Meta Description: # Modificador "protected" en C++: Uso y Ejemplos ## Sinopsis El modificador de acceso "protected" en C++ es una característica fundamental de la progr...
Meta Keywords: protected, clase, que, los, miembros
-->

# Modificador "protected" en C++: Uso y Ejemplos

## Sinopsis
El modificador de acceso "protected" en C++ es una característica fundamental de la programación orientada a objetos que permite controlar la visibilidad de los miembros de una clase, facilitando la herencia y la encapsulación.

## Documentación
El modificador "protected" se utiliza para especificar que los miembros (atributos y métodos) de una clase son accesibles solo dentro de la clase misma y por las clases derivadas. Esto significa que, a diferencia de los miembros "private", que son accesibles solo dentro de la clase que los declara, los miembros "protected" pueden ser utilizados por cualquier clase que herede de la clase base.

### Propósito
El propósito del modificador "protected" es permitir que las clases derivadas accedan a ciertos miembros de la clase base, fomentando la reutilización del código y la extensión funcional de las clases.

### Uso
Para declarar un miembro "protected", simplemente se antepone la palabra clave `protected` antes de la declaración del miembro en la clase. Aquí hay un ejemplo básico:

```cpp
class Base {
protected:
    int valor;
    
public:
    Base(int v) : valor(v) {}
};

class Derivada : public Base {
public:
    Derivada(int v) : Base(v) {}
    
    void mostrarValor() {
        std::cout << "El valor es: " << valor << std::endl; // Accediendo a un miembro protected
    }
};
```

En este ejemplo, `valor` es un miembro "protected" de la clase `Base`, lo que permite a la clase `Derivada` acceder a él.

## Ejemplos

### Ejemplo Básico

```cpp
#include <iostream>
using namespace std;

class Animal {
protected:
    string nombre;

public:
    Animal(string n) : nombre(n) {}
};

class Perro : public Animal {
public:
    Perro(string n) : Animal(n) {}

    void ladrar() {
        cout << nombre << " dice: ¡Guau!" << endl; // Acceso al miembro protected
    }
};

int main() {
    Perro miPerro("Rex");
    miPerro.ladrar(); // Salida: Rex dice: ¡Guau!
    return 0;
}
```

### Ejemplo con Métodos

```cpp
#include <iostream>
using namespace std;

class Vehiculo {
protected:
    int velocidad;

public:
    Vehiculo(int v) : velocidad(v) {}
};

class Coche : public Vehiculo {
public:
    Coche(int v) : Vehiculo(v) {}

    void mostrarVelocidad() {
        cout << "La velocidad es: " << velocidad << " km/h" << endl; // Acceso al miembro protected
    }
};

int main() {
    Coche miCoche(120);
    miCoche.mostrarVelocidad(); // Salida: La velocidad es: 120 km/h
    return 0;
}
```

## Explicación
Al utilizar el modificador "protected", es importante tener en cuenta:

- **Acceso Limitado**: Los miembros "protected" no son accesibles desde fuera de la clase base y las derivadas. Esto significa que no se pueden acceder directamente desde instancias de la clase base o de otras clases no relacionadas.
  
- **Herencia**: Si una clase derivada no hereda públicamente de la clase base, el acceso a los miembros "protected" puede ser restringido. Por ejemplo, si se utiliza herencia privada o protegida, el acceso a los miembros "protected" también se verá afectado.

- **Encapsulación**: Aunque "protected" permite el acceso a las clases derivadas, es recomendable mantener un equilibrio y no exponer más información de la necesaria. Considera si es más apropiado usar métodos públicos para interactuar con los miembros "protected".

## Resumen en Una Línea
El modificador "protected" en C++ permite que los miembros de una clase sean accesibles desde clases derivadas, facilitando la herencia y la reutilización de código.