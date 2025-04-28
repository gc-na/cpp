<!--
Meta Description: # C++中的struct：结构体的使用与特性 ## 概述 在C++编程语言中，`struct`（结构体）是一种用户自定义的数据类型，可以将不同类型的数据组合在一起。结构体使程序员能够创建复杂数据类型，以更好地组织和管理数据。 ## 文档 ### 目的 `struct`用于定义一个新的数据类型，它可...
Meta Keywords: std, book1, struct, cpp, person
-->

# C++中的struct：结构体的使用与特性

## 概述
在C++编程语言中，`struct`（结构体）是一种用户自定义的数据类型，可以将不同类型的数据组合在一起。结构体使程序员能够创建复杂数据类型，以更好地组织和管理数据。

## 文档
### 目的
`struct`用于定义一个新的数据类型，它可以包含多个变量（成员），这些变量可以是不同类型。结构体为数据的逻辑分组提供了便利，常用于表示对象或记录。

### 用法
在C++中，可以通过以下方式定义一个结构体：

```cpp
struct StructName {
    DataType member1;
    DataType member2;
    // 其他成员
};
```

定义结构体后，可以使用点运算符（`.`）来访问其成员。以下是结构体的基本用法示例：

1. 定义结构体：
   ```cpp
   struct Person {
       std::string name;
       int age;
   };
   ```

2. 创建结构体变量：
   ```cpp
   Person person;
   ```

3. 访问和修改结构体成员：
   ```cpp
   person.name = "张三";
   person.age = 30;
   ```

### 详细说明
结构体在C++中具有以下特性：
- **默认访问权限**：结构体的成员默认是公共的（public），可以从外部直接访问。
- **可以包含函数**：结构体不仅可以包含数据成员，还可以包含成员函数。
- **继承**：结构体可以作为基类，支持继承。
- **内存布局**：结构体的内存布局是顺序排列的，即按成员声明的顺序分配内存。

## 示例
以下是一个简单的结构体示例，演示如何定义和使用结构体：

```cpp
#include <iostream>
#include <string>

struct Book {
    std::string title;
    std::string author;
    int year;
};

int main() {
    Book book1;
    book1.title = "C++ Primer";
    book1.author = "Stanley B. Lippman";
    book1.year = 2012;

    std::cout << "书名: " << book1.title << std::endl;
    std::cout << "作者: " << book1.author << std::endl;
    std::cout << "出版年份: " << book1.year << std::endl;

    return 0;
}
```

## 解释
- **常见陷阱**：尽管结构体的成员默认是公共的，但为了封装和数据保护，建议在结构体中使用私有成员，并提供公共的访问方法。
- **内存对齐**：在某些情况下，结构体的成员可能会因为内存对齐的原因而造成额外的内存占用，因此设计结构体时要注意成员的顺序。
- **与类的区别**：结构体与类的主要区别在于默认访问权限（结构体为public，类为private），其他特性基本相同。

## 一句话总结
C++中的`struct`用于定义用户自定义的数据类型，以便有效地组织和管理不同类型的数据。