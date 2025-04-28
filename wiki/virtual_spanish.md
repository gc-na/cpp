<!--
Meta Description: # Uso de "virtual" en C++: Conceptos y Ejemplos ## Sinopsis La palabra clave `virtual` en C++ es fundamental para la programación orientada a objetos,...
Meta Keywords: virtual, que, base, public, std
-->

# Uso de "virtual" en C++: Conceptos y Ejemplos

## Sinopsis
La palabra clave `virtual` en C++ es fundamental para la programación orientada a objetos, ya que permite la creación de métodos virtuales que facilitan la implementación de polimorfismo, permitiendo que las funciones se comporten de manera diferente según el objeto que las invoque.

## Documentación
En C++, la palabra clave `virtual` se utiliza para declarar métodos en clases base que se pueden sobrescribir en clases derivadas. Esto es esencial para lograr el polimorfismo, una de las características clave de la programación orientada a objetos.

### Propósito
El propósito de los métodos virtuales es permitir que las clases derivadas proporcionen implementaciones específicas de funciones definidas en clases base. Cuando se llama a un método virtual desde un puntero o referencia a una clase base, la implementación de la clase derivada se ejecuta, lo que permite un comportamiento dinámico.

### Uso
Para declarar un método como virtual, simplemente se antepone la palabra clave `virtual` a la declaración del método en la clase base. Aquí hay un ejemplo básico:

```cpp
class Base {
public:
    virtual void mostrar() {
        std::cout << "Mostrar desde Base" << std::endl;
    }
};

class Derivada : public Base {
public:
    void mostrar() override { // 'override' es opcional, pero recomendado
        std::cout << "Mostrar desde Derivada" << std::endl;
    }
};
```

### Detalles
- **Destructores virtuales**: Es importante declarar destructores como virtual en clases base para asegurar que se llame al destructor correcto de las clases derivadas.
- **Métodos virtuales puros**: Se pueden declarar métodos virtuales como puros utilizando el operador `= 0`. Esta técnica se utiliza para crear clases abstractas que no se pueden instanciar directamente.

```cpp
class Abstracto {
public:
    virtual void metodoVirtual() = 0; // Método virtual puro
};
```

## Ejemplos
A continuación, se presentan algunos ejemplos prácticos del uso de `virtual` en C++:

### Ejemplo 1: Polimorfismo básico

```cpp
#include <iostream>

class Animal {
public:
    virtual void hacerSonido() {
        std::cout << "Sonido de animal" << std::endl;
    }
};

class Perro : public Animal {
public:
    void hacerSonido() override {
        std::cout << "Guau" << std::endl;
    }
};

void hacerSonidoAnimal(Animal* animal) {
    animal->hacerSonido();
}

int main() {
    Animal* miAnimal = new Perro();
    hacerSonidoAnimal(miAnimal); // Salida: Guau
    delete miAnimal;
    return 0;
}
```

### Ejemplo 2: Clases abstractas

```cpp
#include <iostream>

class Forma {
public:
    virtual void dibujar() = 0; // Método virtual puro
};

class Circulo : public Forma {
public:
    void dibujar() override {
        std::cout << "Dibujando un círculo" << std::endl;
    }
};

int main() {
    Forma* miForma = new Circulo();
    miForma->dibujar(); // Salida: Dibujando un círculo
    delete miForma;
    return 0;
}
```

## Explicación
Al usar métodos virtuales, es crucial entender que:

- **Sobreescritura**: Si una clase derivada no sobrescribe un método virtual de la clase base, la implementación de la clase base será utilizada.
- **Destructores**: No tener un destructor virtual en la clase base puede resultar en fugas de memoria, ya que el destructor de la clase derivada no se llamará.
- **Rendimiento**: El uso de métodos virtuales puede tener un pequeño costo de rendimiento debido a la tabla de métodos virtuales (vtable) que se genera para manejar el despacho dinámico.

## Resumen en una línea
La palabra clave `virtual` en C++ permite el polimorfismo mediante la sobrescritura de métodos en clases derivadas, facilitando un comportamiento dinámico y flexible en la programación orientada a objetos.