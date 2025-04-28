<!--
Meta Description: # C++中的delete关键字详解 ## 摘要 `delete`是C++中的一个关键字，用于动态内存管理。它用于释放由`new`关键字分配的内存，防止内存泄漏。 ## 文档 `delete`操作符的主要目的是释放动态分配的内存。C++提供了两种形式的`delete`操作符： 1. **单个对象的删...
Meta Keywords: delete, int, new, arr, std
-->

# C++中的delete关键字详解

## 摘要
`delete`是C++中的一个关键字，用于动态内存管理。它用于释放由`new`关键字分配的内存，防止内存泄漏。

## 文档
`delete`操作符的主要目的是释放动态分配的内存。C++提供了两种形式的`delete`操作符：

1. **单个对象的删除**：使用`delete`释放通过`new`分配的单个对象的内存。
2. **数组的删除**：使用`delete[]`释放通过`new[]`分配的数组的内存。

### 用法
- **删除单个对象**：
  ```cpp
  int* ptr = new int; // 动态分配内存
  delete ptr;        // 释放内存
  ```

- **删除数组**：
  ```cpp
  int* arr = new int[10]; // 动态分配数组
  delete[] arr;           // 释放内存
  ```

## 示例
以下是使用`delete`的基本示例：

### 示例1：释放单个对象
```cpp
#include <iostream>

int main() {
    int* num = new int(42); // 动态分配内存
    std::cout << *num << std::endl; // 输出42
    delete num; // 释放内存
    return 0;
}
```

### 示例2：释放数组
```cpp
#include <iostream>

int main() {
    int* arr = new int[5]; // 动态分配数组
    for (int i = 0; i < 5; ++i) {
        arr[i] = i + 1;
    }
    for (int i = 0; i < 5; ++i) {
        std::cout << arr[i] << " "; // 输出1 2 3 4 5
    }
    std::cout << std::endl;
    delete[] arr; // 释放内存
    return 0;
}
```

## 说明
### 常见问题
- **双重删除**：调用`delete`或`delete[]`两次会导致未定义行为，可能会导致程序崩溃。
- **未释放内存**：如果忘记使用`delete`，会导致内存泄漏，尤其是在循环或长时间运行的程序中。
- **使用不匹配**：使用`delete`删除由`new[]`分配的内存或使用`delete[]`删除由`new`分配的内存也会导致未定义行为。

### 附加注意事项
- 在使用`delete`后，通常建议将指针设置为`nullptr`，以避免悬挂指针的问题。

## 一句话总结
`delete`关键字用于释放动态分配的内存，是C++内存管理的重要组成部分。