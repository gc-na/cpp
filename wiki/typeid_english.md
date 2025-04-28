<!--
Meta Description: # Understanding `typeid` in C++: Key Features and Usage ## Synopsis The `typeid` operator in C++ is a powerful tool used to determine the type of an e...
Meta Keywords: type, typeid, std, polymorphic, derived
-->

# Understanding `typeid` in C++: Key Features and Usage

## Synopsis
The `typeid` operator in C++ is a powerful tool used to determine the type of an expression at runtime. It provides a way to access type information, facilitating dynamic type identification and supporting polymorphism in object-oriented programming.

## Documentation
### Purpose
The `typeid` operator is part of the C++ RTTI (Run-Time Type Information) mechanism. It is primarily used to retrieve the type information of an object or a type. This can be particularly useful in scenarios involving inheritance, where you might need to determine the exact type of an object at runtime.

### Usage
The syntax for using `typeid` is straightforward:

```cpp
typeid(expression)
```

Here, `expression` can be any valid C++ expression, including objects, pointers, or references. When using `typeid` with polymorphic types (classes with virtual functions), it returns the most derived type of the object.

#### Example of Basic Usage
```cpp
#include <iostream>
#include <typeinfo>

class Base {
    virtual void foo() {}
};

class Derived : public Base {};

int main() {
    Base* b = new Derived();
    std::cout << "Type of b: " << typeid(*b).name() << std::endl; // Output will be derived type
    delete b;
    return 0;
}
```

### Details
- **Return Value**: `typeid` returns a reference to a `std::type_info` object, which contains information about the type.
- **Using `name()`**: To obtain a human-readable string representation of the type, you can call the `name()` method on the returned `std::type_info` object.
- **Static vs. Dynamic Types**: If you use `typeid` on a polymorphic base class pointer or reference, it will return the dynamic type. If used on a non-polymorphic type, it will return the static type.

## Examples
### Example 1: Basic Type Identification
```cpp
#include <iostream>
#include <typeinfo>

int main() {
    int a = 5;
    std::cout << "Type of a: " << typeid(a).name() << std::endl; // Output: int
    return 0;
}
```

### Example 2: Polymorphic Types
```cpp
#include <iostream>
#include <typeinfo>

class Base {
    virtual void foo() {}
};

class Derived : public Base {};

int main() {
    Base* basePtr = new Derived();
    std::cout << "Type of basePtr: " << typeid(*basePtr).name() << std::endl; // Output: Derived
    delete basePtr;
    return 0;
}
```

### Example 3: Non-Polymorphic Types
```cpp
#include <iostream>
#include <typeinfo>

class NonPolymorphic {};

int main() {
    NonPolymorphic np;
    std::cout << "Type of np: " << typeid(np).name() << std::endl; // Output: NonPolymorphic
    return 0;
}
```

## Explanation
### Common Pitfalls
1. **Using `typeid` on Null Pointers**: If you use `typeid` on a null pointer of a polymorphic type, it will throw a `std::bad_typeid` exception. Always check for null pointers before dereferencing.
  
2. **Non-Polymorphic Types**: For non-polymorphic types, `typeid` will always return the type of the expression as defined at compile-time, not considering any potential derived classes.

3. **Compiler Variability**: The output of `typeid(...).name()` may vary between different compilers. For consistent type names, consider using additional libraries like `boost`.

## One Line Summary
`typeid` in C++ provides runtime type identification, enabling the determination of an object's type during execution, essential for polymorphism and RTTI.