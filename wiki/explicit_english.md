<!--
Meta Description: # Understanding `explicit` in C++: Preventing Unintended Conversions ## Synopsis The `explicit` keyword in C++ is used to prevent implicit type conver...
Meta Keywords: explicit, int, myclass, conversions, value
-->

# Understanding `explicit` in C++: Preventing Unintended Conversions

## Synopsis
The `explicit` keyword in C++ is used to prevent implicit type conversions for constructors and conversion operators, ensuring that object creation and type conversions are intentional and clear.

## Documentation
In C++, constructors and conversion operators can allow implicit conversions between types. This can sometimes lead to unexpected behavior or bugs if conversions happen without the programmer's explicit intent. The `explicit` keyword is introduced to manage this behavior by disallowing implicit conversions.

### Purpose
The primary purpose of `explicit` is to enhance code clarity and safety by ensuring that conversions are made only when explicitly requested by the programmer. This is particularly useful for constructors that take a single argument.

### Usage
To declare a constructor or conversion operator as explicit, simply prefix it with the `explicit` keyword. Here’s the syntax:

```cpp
class ClassName {
public:
    explicit ClassName(int value); // Constructor
    explicit operator int(); // Conversion operator
};
```

When attempting to create an object using an implicit conversion, the compiler will generate an error.

### Details
- **Constructors**: When a constructor is defined as `explicit`, it cannot be used for implicit conversions. For example:

```cpp
class MyClass {
public:
    explicit MyClass(int value) { /*...*/ }
};
```

If you try to initialize `MyClass` with an integer directly:

```cpp
MyClass obj = 10; // Error: cannot convert 'int' to 'MyClass' implicitly
```

You must use explicit syntax:

```cpp
MyClass obj(10); // Correct usage
```

- **Conversion Operators**: The same rule applies to conversion operators. Declaring a conversion operator as `explicit` prevents implicit conversions:

```cpp
class MyClass {
public:
    explicit operator int() { return 42; }
};

MyClass obj;
int value = obj; // Error: cannot convert 'MyClass' to 'int' implicitly
```
To convert explicitly, you would use:

```cpp
int value = static_cast<int>(obj); // Correct usage
```

## Examples

### Example 1: Explicit Constructor
```cpp
#include <iostream>

class MyClass {
public:
    explicit MyClass(int value) : value(value) {}
    int getValue() const { return value; }
private:
    int value;
};

int main() {
    MyClass obj(10); // Correct
    // MyClass obj2 = 10; // Error: cannot convert 'int' to 'MyClass' implicitly
    return 0;
}
```

### Example 2: Explicit Conversion Operator
```cpp
#include <iostream>

class MyClass {
public:
    explicit operator int() const { return 42; }
};

int main() {
    MyClass obj;
    // int value = obj; // Error: cannot convert 'MyClass' to 'int' implicitly
    int value = static_cast<int>(obj); // Correct
    std::cout << value << std::endl; // Outputs: 42
    return 0;
}
```

## Explanation
### Common Pitfalls
- **Overusing `explicit`**: While using `explicit` can prevent unintended conversions, overuse can lead to verbose code and unnecessary complications in scenarios where implicit conversions are actually desired.
- **Misunderstanding the Scope**: Developers might mistakenly believe that `explicit` applies to all constructors. It only affects single-argument constructors and conversion operators.

### Gotchas
- **Default Constructors**: If a constructor has multiple parameters, it is implicitly non-convertible regardless of the `explicit` keyword, so you need to use `explicit` for single-argument constructors only.
- **Inheritance**: If a base class constructor is declared as `explicit`, derived classes must explicitly call it in their constructors.

## One Line Summary
The `explicit` keyword in C++ prevents implicit conversions for constructors and conversion operators, promoting clearer and safer code.