<!--
Meta Description: # Understanding the `new` Operator in C++ ## Synopsis The `new` operator in C++ is used for dynamic memory allocation, allowing developers to allocate...
Meta Keywords: memory, new, delete, myclass, std
-->

# Understanding the `new` Operator in C++

## Synopsis
The `new` operator in C++ is used for dynamic memory allocation, allowing developers to allocate memory for objects and data structures at runtime.

## Documentation
The `new` operator is a fundamental feature in C++ that enables dynamic memory management. When you use `new`, it allocates memory on the heap for a specified type and returns a pointer to that memory. This is particularly useful when the size of the data structure is not known at compile time or when you need the memory to persist beyond the scope of a function.

### Purpose
The primary purpose of `new` is to create a dynamic object or array and to allocate the required memory at runtime. Unlike stack allocation, the memory allocated using `new` remains until it is explicitly deallocated using `delete`.

### Usage
The syntax for using `new` is as follows:

- For a single object:
  ```cpp
  Type* pointer = new Type;
  ```

- For an array of objects:
  ```cpp
  Type* pointer = new Type[size];
  ```

After using `new`, it is crucial to manage memory properly to prevent memory leaks.

### Details
- **Constructor Calls**: When `new` allocates memory for an object, it also calls the constructor for that object.
- **Array Allocation**: When allocating an array, `new` will allocate enough memory for all elements and call the constructor for each element.
- **Deallocation**: To free the allocated memory, use `delete` for single objects and `delete[]` for arrays.

## Examples

### Example 1: Allocating a Single Object
```cpp
#include <iostream>

class MyClass {
public:
    MyClass() { std::cout << "Constructor called!" << std::endl; }
    ~MyClass() { std::cout << "Destructor called!" << std::endl; }
};

int main() {
    MyClass* obj = new MyClass(); // Allocate memory and call constructor
    delete obj; // Free memory and call destructor
    return 0;
}
```

### Example 2: Allocating an Array of Objects
```cpp
#include <iostream>

class MyClass {
public:
    MyClass() { std::cout << "Constructor called!" << std::endl; }
    ~MyClass() { std::cout << "Destructor called!" << std::endl; }
};

int main() {
    int size = 3;
    MyClass* arr = new MyClass[size]; // Allocate memory for an array of MyClass
    delete[] arr; // Free memory for the array and call destructors
    return 0;
}
```

## Explanation
### Common Pitfalls
- **Memory Leaks**: If you forget to call `delete` or `delete[]`, the allocated memory will not be released, leading to memory leaks.
- **Dangling Pointers**: After calling `delete`, the pointer still holds the address of the deallocated memory. Using this pointer can lead to undefined behavior.
- **Misusing `delete` and `delete[]`**: Always match `new` with `delete` and `new[]` with `delete[]`. Using the wrong form can cause runtime errors or crashes.

### Additional Notes
- In modern C++, consider using smart pointers (`std::unique_ptr` or `std::shared_ptr`) for automatic memory management, reducing the risk of memory leaks and dangling pointers.

## One Line Summary
The `new` operator in C++ is essential for dynamic memory allocation, allowing developers to manage memory efficiently at runtime.