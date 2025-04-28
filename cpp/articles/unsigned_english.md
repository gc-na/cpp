<!--
Meta Description: # Understanding Unsigned Types in C++ ## Synopsis In C++, the `unsigned` keyword is used to define integer types that can only represent non-negative ...
Meta Keywords: unsigned, integer, can, types, negative
-->

# Understanding Unsigned Types in C++

## Synopsis
In C++, the `unsigned` keyword is used to define integer types that can only represent non-negative values, effectively doubling the upper limit of the range compared to their signed counterparts.

## Documentation
### Purpose
The `unsigned` keyword modifies integer data types (such as `int`, `short`, `long`, etc.) to signify that the variable will only store non-negative values (0 and positive integers). By using `unsigned` types, developers can take advantage of the extended range of positive values, which can be particularly beneficial in applications like graphics programming, network protocols, and other scenarios where negative values are not needed.

### Usage
To declare an unsigned integer in C++, you can simply prefix the standard integer types with the `unsigned` keyword. For instance:

```cpp
unsigned int myUnsignedInt;
```

This declaration creates an unsigned integer variable named `myUnsignedInt`. The following types can also be modified with `unsigned`:

- `unsigned short`
- `unsigned long`
- `unsigned long long`

### Details
The range of an `unsigned` integer type is from 0 to the maximum value that can be represented by the corresponding signed type. For example, while a signed `int` typically ranges from -2,147,483,648 to 2,147,483,647, an `unsigned int` ranges from 0 to 4,294,967,295.

The C++ standard defines the sizes of these types, but they may vary depending on the system and compiler. Generally, the following sizes are commonly observed:

- `unsigned short`: 0 to 65,535 (16 bits)
- `unsigned int`: 0 to 4,294,967,295 (32 bits)
- `unsigned long`: 0 to 4,294,967,295 (32 bits on many systems)
- `unsigned long long`: 0 to 18,446,744,073,709,551,615 (64 bits)

### Examples
Here are some basic examples of using unsigned integers in C++:

```cpp
#include <iostream>

int main() {
    unsigned int positiveNumber = 100; // Valid
    unsigned int negativeNumber = -10; // Compiler warning/error

    std::cout << "Positive number: " << positiveNumber << std::endl;

    // Using unsigned long
    unsigned long bigNumber = 3000000000; // Valid
    std::cout << "Big number: " << bigNumber << std::endl;

    return 0;
}
```

In this example, `positiveNumber` is a valid unsigned integer, while attempting to assign a negative value to `negativeNumber` will typically result in a compiler warning or error.

## Explanation
### Common Pitfalls
1. **Negative Assignment**: Assigning a negative value to an unsigned variable can lead to unexpected behavior, typically resulting in a very large positive number due to underflow.
   
2. **Comparison Issues**: When comparing signed and unsigned integers, if a signed integer is negative and compared to an unsigned integer, the signed integer is converted to an unsigned type, which can lead to misleading results.

3. **Overflow**: Performing arithmetic operations that exceed the maximum value of an unsigned integer will result in wraparound behavior, which can also cause bugs if not properly handled.

### Additional Notes
- Unsigned integers are often used in contexts where negative values are illogical or to ensure that values remain within a specified range.
- Use caution when mixing signed and unsigned types in expressions to avoid unintended consequences.

## One Line Summary
The `unsigned` keyword in C++ allows the declaration of integer types that can only represent non-negative values, effectively increasing the range of positive integers.