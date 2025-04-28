<!--
Meta Description: # Understanding "virtual" in C++: A Guide to Polymorphism and Dynamic Binding ## Synopsis In C++, the `virtual` keyword is essential for implementing ...
Meta Keywords: virtual, class, derived, base, show
-->

# Understanding "virtual" in C++: A Guide to Polymorphism and Dynamic Binding

## Synopsis
In C++, the `virtual` keyword is essential for implementing polymorphism in class hierarchies, allowing derived classes to override base class methods and enabling dynamic binding during runtime.

## Documentation
The `virtual` keyword in C++ is used in the context of class inheritance to indicate that a method can be overridden in derived classes. When a method is declared as `virtual`, C++ utilizes a mechanism called "dynamic dispatch," which means that the method being called is determined at runtime based on the type of the object being referenced, rather than the type of the pointer/reference.

### Purpose
- To enable polymorphism: The `virtual` keyword allows for a common interface in base classes while permitting specialized implementations in derived classes.
- To support dynamic binding: It allows the program to decide which method to invoke based on the actual object type at runtime.

### Usage
To declare a method as virtual, you simply prefix the method declaration in the base class with the `virtual` keyword. Derived classes can override this method, and the base class pointer/reference will call the correct version based on the object type.

### Details
- **Virtual Destructor**: If a class has virtual functions, it should also have a virtual destructor to ensure proper cleanup of derived class resources.
- **Pure Virtual Functions**: You can declare a function as a pure virtual function by using the syntax `virtual void functionName() = 0;`. This makes the class abstract and prevents instantiation.
- **Overriding**: When a derived class overrides a base class method, the `virtual` keyword is optional but recommended for clarity.

## Examples

### Basic Example of Virtual Functions
```cpp
#include <iostream>

class Base {
public:
    virtual void show() { // Virtual function
        std::cout << "Base class show function called." << std::endl;
    }
};

class Derived : public Base {
public:
    void show() override { // Override the base class method
        std::cout << "Derived class show function called." << std::endl;
    }
};

int main() {
    Base* basePtr;
    Derived derivedObj;
    
    basePtr = &derivedObj; // Pointing to Derived object
    basePtr->show(); // Calls Derived's show function
    return 0;
}
```

### Example of Pure Virtual Functions
```cpp
#include <iostream>

class AbstractBase {
public:
    virtual void show() = 0; // Pure virtual function
};

class ConcreteDerived : public AbstractBase {
public:
    void show() override { // Implementing the pure virtual function
        std::cout << "ConcreteDerived show function called." << std::endl;
    }
};

int main() {
    ConcreteDerived derivedObj;
    derivedObj.show(); // Calls ConcreteDerived's show function
    return 0;
}
```

## Explanation
While using virtual functions, it is crucial to understand a few common pitfalls:
- **Slicing**: If a derived class object is assigned to a base class object (not a pointer/reference), the derived part is sliced off. Always use pointers or references to avoid this.
- **Performance Overhead**: Virtual functions introduce a slight overhead due to dynamic dispatch. However, this is often negligible compared to the benefits of polymorphism.
- **Destructor Consideration**: If a class has virtual functions, it should have a virtual destructor to ensure that derived class destructors are invoked when an object is deleted through a base class pointer.

## One Line Summary
The `virtual` keyword in C++ enables polymorphism by allowing base class methods to be overridden in derived classes, facilitating dynamic binding at runtime.