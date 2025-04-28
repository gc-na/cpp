<!--
Meta Description: # C++ 中的 "default" 关键字详解 ## 摘要 在 C++ 中，"default" 关键字主要用于提供默认构造函数、默认拷贝构造函数和默认析构函数的定义。它使得用户可以显式地声明这些函数的默认行为，从而提高代码的可读性和维护性。 ## 文档 ### 目的 "Default" 关键字的主...
Meta Keywords: default, myclass, example, 默认构造函数, 默认拷贝构造函数
-->

# C++ 中的 "default" 关键字详解

## 摘要
在 C++ 中，"default" 关键字主要用于提供默认构造函数、默认拷贝构造函数和默认析构函数的定义。它使得用户可以显式地声明这些函数的默认行为，从而提高代码的可读性和维护性。

## 文档
### 目的
"Default" 关键字的主要目的是为类提供默认的构造、拷贝和析构函数的定义。C++ 语言允许程序员通过 `= default` 语法来指示编译器生成这些函数的默认实现。

### 用法
- 默认构造函数：如果类没有定义任何构造函数，编译器会自动生成一个默认构造函数。使用 `= default` 可以显式地请求编译器生成该构造函数。
- 默认拷贝构造函数：如未定义，编译器也会自动提供一个拷贝构造函数。`= default` 可用于显式声明。
- 默认析构函数：同样，若未定义，编译器会生成一个析构函数，使用 `= default` 可以进行显式声明。

### 详细信息
在 C++11 及以后的版本中，`= default` 语法被引入，允许开发者更清晰地表明其意图，使得代码的可读性更高。例如：

```cpp
class Example {
public:
    Example() = default;              // 默认构造函数
    Example(const Example&) = default; // 默认拷贝构造函数
    ~Example() = default;             // 默认析构函数
};
```

这段代码告诉编译器为 `Example` 类生成默认的构造函数、拷贝构造函数和析构函数。

## 示例
以下是如何在 C++ 中使用 `default` 关键字的示例：

```cpp
#include <iostream>

class MyClass {
public:
    MyClass() = default;                // 默认构造函数
    MyClass(const MyClass&) = default;  // 默认拷贝构造函数
    ~MyClass() = default;               // 默认析构函数

    void display() {
        std::cout << "MyClass object" << std::endl;
    }
};

int main() {
    MyClass obj1;                      // 使用默认构造函数
    MyClass obj2 = obj1;               // 使用默认拷贝构造函数
    obj1.display();
    return 0;
}
```

## 解释
使用 `default` 关键字时需要注意以下几点：
- 如果类中定义了任何构造函数、拷贝构造函数或析构函数，编译器将不会自动生成默认版本，除非显式声明。
- 不能同时声明某个函数为 `= default` 和提供自定义实现，这将导致编译错误。
- `= default` 只能在类的定义中使用，不能在类外部使用。

## 一句话总结
在 C++ 中，"default" 关键字用于显式请求编译器生成默认的构造函数、拷贝构造函数和析构函数。