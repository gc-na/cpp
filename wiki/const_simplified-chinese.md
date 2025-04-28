<!--
Meta Description: # C++中的const关键字详解 ## 概述 在C++中，`const`关键字用于声明常量或不可修改的变量，确保程序中的数据不被意外改变。它是实现数据保护和提高代码可读性的有效工具。 ## 文档 ### 目的 `const`关键字的主要目的是为了定义常量，防止数据在程序执行过程中被意外修改。它可以...
Meta Keywords: const, int, cpp, void, std
-->

# C++中的const关键字详解

## 概述
在C++中，`const`关键字用于声明常量或不可修改的变量，确保程序中的数据不被意外改变。它是实现数据保护和提高代码可读性的有效工具。

## 文档
### 目的
`const`关键字的主要目的是为了定义常量，防止数据在程序执行过程中被意外修改。它可以用于变量、指针、成员函数等多种场景中。

### 用法
1. **常量变量**：
   使用`const`声明的变量在初始化后不能被修改。
   ```cpp
   const int maxAttempts = 5;
   ```

2. **常量指针**：
   `const`可以用于指针，指定指针本身或所指向的数据不可被修改。
   ```cpp
   const int* ptrToConst = &maxAttempts; // 指向常量的指针
   int* const constPtr = &someVariable; // 常量指针
   ```

3. **常量成员函数**：
   在类中，使用`const`修饰成员函数，表示该函数不会修改类的任何成员变量。
   ```cpp
   class MyClass {
   public:
       void display() const {
           // 只能读取成员变量
       }
   };
   ```

4. **常量引用**：
   `const`也可以用于引用，防止通过引用修改数据。
   ```cpp
   void process(const int& value) {
       // value不能被修改
   }
   ```

## 示例
以下是几个使用`const`的基本示例：

```cpp
#include <iostream>

const int MAX_SIZE = 100;

void printArray(const int* arr, const int size) {
    for (int i = 0; i < size; i++) {
        std::cout << arr[i] << " ";
    }
    std::cout << std::endl;
}

int main() {
    int numbers[MAX_SIZE] = {1, 2, 3, 4, 5};
    printArray(numbers, 5);
    return 0;
}
```

## 说明
- **常见错误**：
  - 尝试修改`const`变量会导致编译错误。
  - 需要注意`const`的作用范围，局部常量与全局常量不相同。
  
- **指针的复杂性**：
  - 理解`const`指针与常量指针的区别非常重要。`const int*`表示指向常量的指针，而`int* const`表示常量指针。

- **常量表达式**：
  - 使用`const`可以提高性能，尤其在传递大型对象时，使用常量引用可以避免不必要的复制。

## 一句话总结
`const`关键字在C++中用于声明不可修改的变量，保证数据安全并提高代码可读性。