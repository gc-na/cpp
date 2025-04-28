<!--
Meta Description: # C++ 中的虚函数（virtual） ## 概述 在 C++ 中，虚函数是实现多态性的关键特性。通过使用虚函数，程序员可以在基类中定义接口，并在派生类中提供具体实现，使得在运行时可以根据对象的实际类型调用相应的函数。 ## 文档 ### 目的 虚函数允许基类指针或引用指向派生类对象时，能够调用派...
Meta Keywords: show, virtual, base, class, public
-->

# C++ 中的虚函数（virtual）

## 概述
在 C++ 中，虚函数是实现多态性的关键特性。通过使用虚函数，程序员可以在基类中定义接口，并在派生类中提供具体实现，使得在运行时可以根据对象的实际类型调用相应的函数。

## 文档
### 目的
虚函数允许基类指针或引用指向派生类对象时，能够调用派生类中重写的函数。它是实现运行时多态的基础。

### 用法
在 C++ 中，可以通过在函数声明前加上关键字`virtual`来定义虚函数。虚函数通常在基类中声明，派生类可以重写这些函数。

### 细节
1. **声明**：在基类中使用`virtual`关键字声明函数。
2. **重写**：在派生类中可以重写基类中的虚函数。
3. **虚析构函数**：为了避免内存泄漏，基类的析构函数应声明为虚函数。
4. **性能开销**：使用虚函数会增加一定的性能开销，因为需要通过虚函数表（vtable）进行动态绑定。

## 示例
以下是一个简单的虚函数示例：

```cpp
#include <iostream>
using namespace std;

class Base {
public:
    virtual void show() {
        cout << "Base class show function called." << endl;
    }
    virtual ~Base() {}  // 虚析构函数
};

class Derived : public Base {
public:
    void show() override {  // 重写基类的虚函数
        cout << "Derived class show function called." << endl;
    }
};

int main() {
    Base* b = new Derived();  // 基类指针指向派生类对象
    b->show();                // 调用派生类的 show 函数
    delete b;                // 释放内存
    return 0;
}
```

## 说明
- **常见陷阱**：如果基类的析构函数不是虚的，删除基类指针时可能导致未定义行为。
- **纯虚函数**：在基类中可以将虚函数声明为纯虚函数（`virtual void show() = 0;`），这使得该类成为抽象类，无法实例化。
- **override 关键字**：在 C++11 及以后的版本中，可以使用`override`关键字来明确指示该函数是重写基类的虚函数。

## 一句话总结
虚函数是 C++ 中实现多态性的关键特性，允许通过基类指针或引用调用派生类中的重写函数。