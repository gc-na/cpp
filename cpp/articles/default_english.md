<!--
Meta Description: # Default in C++: Understanding the Default Keyword and Its Usage ## Synopsis In C++, the keyword `default` is used primarily in the context of defini...
Meta Keywords: default, case, constructor, myclass, example
-->

# Default in C++: Understanding the Default Keyword and Its Usage

## Synopsis
In C++, the keyword `default` is used primarily in the context of defining default constructors, defaulted functions, and in `switch` statements to specify a fallback case. This article explores the various applications of the `default` keyword, its syntax, and best practices.

## Documentation
### Purpose
The `default` keyword serves multiple purposes in C++:
1. **Default Constructors**: It allows the compiler to generate a default constructor for a class.
2. **Defaulted Functions**: It can explicitly instruct the compiler to generate default implementations for special member functions such as copy constructors, move constructors, copy assignment operators, and move assignment operators.
3. **Switch Statements**: It defines a default case within a switch statement, providing a fallback option when none of the specified cases match.

### Usage
1. **Default Constructors**:
   ```cpp
   class MyClass {
   public:
       MyClass() = default; // Using default to define a default constructor
   };
   ```

2. **Defaulted Functions**:
   ```cpp
   class MyClass {
   public:
       MyClass(const MyClass&) = default; // Default copy constructor
       MyClass(MyClass&&) = default;      // Default move constructor
       MyClass& operator=(const MyClass&) = default; // Default copy assignment
       MyClass& operator=(MyClass&&) = default;      // Default move assignment
   };
   ```

3. **Switch Statements**:
   ```cpp
   int value = 3;
   switch(value) {
       case 1:
           // Do something
           break;
       case 2:
           // Do something else
           break;
       default:
           // Fallback action
           break;
   }
   ```

## Examples
### Example 1: Default Constructor
```cpp
class Example {
public:
    Example() = default; // Default constructor
};

int main() {
    Example ex; // Calls the default constructor
    return 0;
}
```

### Example 2: Defaulted Function
```cpp
class Example {
public:
    Example(const Example&) = default; // Default copy constructor
};

int main() {
    Example ex1;
    Example ex2 = ex1; // Uses the default copy constructor
    return 0;
}
```

### Example 3: Switch Statement Default Case
```cpp
#include <iostream>

int main() {
    int num = 5;
    switch(num) {
        case 1:
            std::cout << "One\n";
            break;
        case 2:
            std::cout << "Two\n";
            break;
        default:
            std::cout << "Default case: Not One or Two\n"; // Default case
            break;
    }
    return 0;
}
```

## Explanation
While using `default`, there are several important considerations:
- **Automatic Generation**: When you default a constructor or function, it allows the compiler to automatically generate the most efficient version based on the class's members. However, if there are members that do not have default constructors, the defaulted constructor will fail.
- **Copy and Move Semantics**: Defaulting copy and move constructors and assignment operators can be particularly useful for classes that manage resources. Defaulted functions will perform member-wise copy or move, which is often the intended behavior.
- **Switch Default Case**: The `default` case in a switch statement is optional but ensures that there is a defined behavior when no case matches. Always remember to include a `break` statement in the `default` case unless you want to allow fall-through.

## One Line Summary
The `default` keyword in C++ is used to specify default constructors, defaulted functions, and fallback cases in switch statements, facilitating efficient and clear code management.