<!--
Meta Description: # C++ 模板详解：提升代码复用性与灵活性的强大工具 ## 概述 C++ 模板是C++编程语言中的一种强大机制，允许程序员编写与类型无关的代码，从而实现代码的复用性和灵活性。模板可以用于函数和类，使得同一段代码可以处理不同的数据类型。 ## 文档 ### 目的 C++ 模板的主要目的在于允许开发人...
Meta Keywords: item, return, typename, cpp, template
-->

# C++ 模板详解：提升代码复用性与灵活性的强大工具

## 概述
C++ 模板是C++编程语言中的一种强大机制，允许程序员编写与类型无关的代码，从而实现代码的复用性和灵活性。模板可以用于函数和类，使得同一段代码可以处理不同的数据类型。

## 文档
### 目的
C++ 模板的主要目的在于允许开发人员定义通用的算法和数据结构，这些算法和数据结构可以与任何数据类型一起使用。

### 用法
C++ 模板分为函数模板和类模板两种类型：

1. **函数模板**：可以定义一个通用的函数，接收不同类型的参数。
   ```cpp
   template <typename T>
   T add(T a, T b) {
       return a + b;
   }
   ```

2. **类模板**：可以定义一个通用的类，能够处理不同类型的对象。
   ```cpp
   template <typename T>
   class Box {
   public:
       void setItem(T item) {
           this->item = item;
       }
       T getItem() {
           return item;
       }
   private:
       T item;
   };
   ```

### 细节
- **模板参数**：可以使用`typename`或`class`关键字来声明模板参数。
- **默认模板参数**：可以为模板参数提供默认值。
- **模板特化**：允许对特定类型的模板进行特化，从而实现不同的实现方式。
- **编译期多态**：模板在编译期进行类型检查，提供了更高的性能。

## 示例
### 函数模板示例
```cpp
#include <iostream>
using namespace std;

template <typename T>
T add(T a, T b) {
    return a + b;
}

int main() {
    cout << add(5, 10) << endl;         // 输出 15
    cout << add(5.5, 10.5) << endl;     // 输出 16
    return 0;
}
```

### 类模板示例
```cpp
#include <iostream>
using namespace std;

template <typename T>
class Box {
public:
    void setItem(T item) {
        this->item = item;
    }
    T getItem() {
        return item;
    }
private:
    T item;
};

int main() {
    Box<int> intBox;
    intBox.setItem(123);
    cout << intBox.getItem() << endl; // 输出 123

    Box<string> strBox;
    strBox.setItem("Hello, Templates!");
    cout << strBox.getItem() << endl; // 输出 Hello, Templates!
    
    return 0;
}
```

## 说明
- **常见陷阱**：使用模板时，确保类型兼容性。如果模板类型不支持某些操作，将导致编译错误。
- **模板实例化**：模板在使用时会被实例化，可能导致代码膨胀。
- **调试困难**：模板的错误信息在编译时可能较为复杂，调试时需要耐心。

## 一句话总结
C++ 模板是实现代码复用与灵活性的强大机制，允许编写与类型无关的函数和类。