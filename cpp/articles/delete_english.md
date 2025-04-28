<!--
Meta Description: # Understanding the `delete` Operator in C++ ## Synopsis The `delete` operator in C++ is used to deallocate memory previously allocated with `new`. It...
Meta Keywords: memory, delete, pointer, myclass, new
-->

# Understanding the `delete` Operator in C++

## Synopsis
The `delete` operator in C++ is used to deallocate memory previously allocated with `new`. It plays a crucial role in memory management, preventing memory leaks and ensuring efficient utilization of system resources.

## Documentation
The `delete` operator is essential when working with dynamic memory allocation in C++. When you allocate memory for an object or an array using `new`, it is important to release that memory using `delete` to free up system resources. 

### Purpose
- To free memory allocated on the heap that is no longer needed.
- To prevent memory leaks which can lead to increased memory consumption and performance degradation.

### Usage
The syntax for using the `delete` operator varies slightly depending on whether you are deallocating a single object or an array of objects.

1. **Deleting a Single Object:**
   ```cpp
   delete pointer;
   ```
   Here, `pointer` is a pointer to the object that was created using `new`.

2. **Deleting an Array of Objects:**
   ```cpp
   delete[] pointerArray;
   ```
   In this case, `pointerArray` is a pointer to an array created with `new[]`.

### Details
- Using `delete` on a pointer that has not been allocated with `new` results in undefined behavior.
- After using `delete`, the pointer itself should be set to `nullptr` to avoid dangling pointers.
- It is crucial to use `delete` or `delete[]` corresponding to how memory was allocated (`new` or `new[]`), respectively.

## Examples

### Example 1: Deleting a Single Object
```cpp
#include <iostream>

class MyClass {
public:
    MyClass() {
        std::cout << "Constructor called." << std::endl;
    }
    ~MyClass() {
        std::cout << "Destructor called." << std::endl;
    }
};

int main() {
    MyClass* obj = new MyClass(); // Allocate memory
    delete obj;                   // Deallocate memory
    return 0;
}
```

### Example 2: Deleting an Array of Objects
```cpp
#include <iostream>

class MyClass {
public:
    MyClass() {
        std::cout << "Constructor called." << std::endl;
    }
    ~MyClass() {
        std::cout << "Destructor called." << std::endl;
    }
};

int main() {
    MyClass* objArray = new MyClass[3]; // Allocate memory for an array
    delete[] objArray;                  // Deallocate memory
    return 0;
}
```

## Explanation
Using `delete` improperly can lead to serious issues in a C++ program:

- **Double Deletion:** Deleting the same pointer multiple times can cause undefined behavior. Always ensure that a pointer is deleted only once.
- **Memory Leaks:** Failing to call `delete` on allocated memory leads to memory leaks. Tools like Valgrind can help identify such leaks.
- **Dangling Pointers:** After deletion, set the pointer to `nullptr` to avoid dereferencing a dangling pointer, which can lead to crashes.

Properly managing memory with `delete` is vital for resource management and overall application performance in C++.

## One Line Summary
The `delete` operator in C++ is used to free dynamically allocated memory, ensuring efficient resource management and preventing memory leaks.