<!--
Meta Description: # C++中的typeid：类型识别符 ## 概述 `typeid` 是C++中的一个运算符，用于在运行时获取对象的类型信息。它是RTTI（运行时类型识别）的一部分，能够帮助程序员在多态环境中判断对象的实际类型。 ## 文档 `typeid`运算符的主要用途是返回一个`std::type_info`...
Meta Keywords: typeid, std, name, type_info, include
-->

# C++中的typeid：类型识别符

## 概述
`typeid` 是C++中的一个运算符，用于在运行时获取对象的类型信息。它是RTTI（运行时类型识别）的一部分，能够帮助程序员在多态环境中判断对象的实际类型。

## 文档
`typeid`运算符的主要用途是返回一个`std::type_info`对象，该对象包含了关于给定类型的信息。它可以与任何表达式一起使用，包括基础类型、类类型和指针类型。

### 用法
使用`typeid`的基本语法如下：
```cpp
typeid(expression)
```
其中，`expression`可以是一个对象、引用或类型名。

`typeid`的返回值是一个常量引用，指向`std::type_info`对象。可以通过调用`name()`方法获取类型的名称。

### 注意事项
- `typeid`仅适用于具有虚函数的类的实例（即多态类型）。对于非多态类型，`typeid`将返回该对象的静态类型。
- 如果使用`typeid`来获取一个空指针的类型信息，结果将是指向其类型的`std::type_info`对象。
- 在使用`typeid`时，确保你包含了 `<typeinfo>` 头文件。

## 示例
### 基本使用示例
```cpp
#include <iostream>
#include <typeinfo>

class Base {
    virtual void func() {}
};

class Derived : public Base {};

int main() {
    Base* b = new Derived();
    
    // 使用typeid获取实际类型
    std::cout << "b的类型: " << typeid(*b).name() << std::endl; // 输出实际类型: Derived

    delete b;
    return 0;
}
```

### 使用typeid与类型名
```cpp
#include <iostream>
#include <typeinfo>

int main() {
    int a = 5;
    double b = 3.14;

    std::cout << "a的类型: " << typeid(a).name() << std::endl; // 输出: int
    std::cout << "b的类型: " << typeid(b).name() << std::endl; // 输出: double

    return 0;
}
```

## 解释
在使用`typeid`时，程序员需要注意以下几点：
- **多态性**：`typeid`的行为依赖于对象的多态性。如果你对一个基类指针使用`typeid`，结果将是指向该指针实际指向的派生类的类型信息。
- **空指针**：对于空指针，`typeid`将返回指向该指针所指向类型的`std::type_info`对象，避免了可能的错误。
- **编译器特性**：不同的编译器对`typeid`的实现细节可能有所不同，涉及到名称修饰（name mangling）和输出格式。

## 一句话总结
`typeid`运算符在C++中用于获取对象的运行时类型信息，是多态编程的重要工具。