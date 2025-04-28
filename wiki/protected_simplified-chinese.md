<!--
Meta Description: # C++中的“protected”访问修饰符详解 ## 概述 在C++中，“protected”是一个访问修饰符，用于控制类成员（属性和方法）的访问权限。它主要用于继承关系中，以便在基类和派生类之间共享数据。 ## 文档说明 “protected”关键字用于定义类的成员，使得这些成员可以被该类的派...
Meta Keywords: protected, species, dog, public, animal
-->

# C++中的“protected”访问修饰符详解

## 概述
在C++中，“protected”是一个访问修饰符，用于控制类成员（属性和方法）的访问权限。它主要用于继承关系中，以便在基类和派生类之间共享数据。

## 文档说明
“protected”关键字用于定义类的成员，使得这些成员可以被该类的派生类访问，但不能被类外的其他代码直接访问。这种访问控制机制有助于封装和数据隐藏，同时允许派生类访问基类的内部实现。

### 用法
在C++中，使用“protected”关键字定义成员变量或成员函数时，语法如下：

```cpp
class Base {
protected:
    int protectedValue;
    
    void protectedMethod() {
        // 方法实现
    }
};

class Derived : public Base {
public:
    void accessProtectedMembers() {
        protectedValue = 10; // 允许访问
        protectedMethod();    // 允许访问
    }
};
```

在上述代码中，`protectedValue`和`protectedMethod`可以在派生类`Derived`中访问，但在类`Base`的外部则无法直接访问。

## 示例
以下是一个简单的示例，展示“protected”修饰符的使用：

```cpp
#include <iostream>
using namespace std;

class Animal {
protected:
    string species;

public:
    Animal(string name) : species(name) {}
};

class Dog : public Animal {
public:
    Dog(string name) : Animal(name) {}

    void displaySpecies() {
        cout << "Species: " << species << endl; // 访问基类的protected成员
    }
};

int main() {
    Dog dog("Canine");
    dog.displaySpecies(); // 输出: Species: Canine
    return 0;
}
```

在这个例子中，`Dog`类能够访问`Animal`类中的`species`成员，因为它是`protected`的。

## 说明
使用“protected”访问修饰符时需要注意以下几点：
1. **只能通过继承访问**：只有派生类可以访问基类中的`protected`成员，其他类无法直接访问。
2. **访问权限的继承**：如果派生类进一步被继承，其`protected`成员将仍然是`protected`，并且可以被其子类访问。
3. **与“private”的区别**：`private`成员只能在定义它的类内部访问，而`protected`成员可以在派生类中访问。

## 一句总结
“protected”是C++中的一种访问修饰符，允许派生类访问基类的成员，同时保护这些成员不被外部代码直接访问。