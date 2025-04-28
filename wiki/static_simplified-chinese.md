<!--
Meta Description: # C++中的静态（static）关键字详解 ## 概述 在C++中，`static`关键字用于定义静态变量和静态方法。它可以用于函数内部、类内部以及全局作用域中，具有不同的用途和特性。 ## 文档 ### 目的 `static`关键字的主要作用是控制变量和方法的生命周期和可见性。它可以使变量在函数...
Meta Keywords: static, int, std, count, counter
-->

# C++中的静态（static）关键字详解

## 概述
在C++中，`static`关键字用于定义静态变量和静态方法。它可以用于函数内部、类内部以及全局作用域中，具有不同的用途和特性。

## 文档
### 目的
`static`关键字的主要作用是控制变量和方法的生命周期和可见性。它可以使变量在函数调用之间保持其值，并限制变量或方法的作用域。

### 使用方法
1. **静态局部变量**：
   - 在函数内部定义，存储在静态存储区，生命周期与程序相同。
   - 只会在第一次调用时初始化，之后的调用将保留上次的值。

   ```cpp
   void countCalls() {
       static int callCount = 0; // 只初始化一次
       callCount++;
       std::cout << "Function called " << callCount << " times." << std::endl;
   }
   ```

2. **静态成员变量**：
   - 属于类而不是类的对象。所有对象共享同一份数据。
   - 在类外部定义并初始化。

   ```cpp
   class MyClass {
   public:
       static int objectCount; // 声明静态成员变量
       MyClass() { objectCount++; }
   };

   int MyClass::objectCount = 0; // 定义并初始化
   ```

3. **静态成员函数**：
   - 不依赖于类的对象，可以通过类名直接调用。
   - 只能访问静态成员变量。

   ```cpp
   class MyClass {
   public:
       static void displayCount() {
           std::cout << "Object count is: " << objectCount << std::endl;
       }
   };
   ```

4. **静态全局变量**：
   - 限制变量的作用域，仅在定义它的文件内可见。

   ```cpp
   static int globalVar = 10; // 仅在当前源文件可见
   ```

## 示例
以下是使用`static`关键字的基本示例：

```cpp
#include <iostream>

class Counter {
public:
    static int count; // 静态成员变量声明

    Counter() {
        count++;
    }

    static void showCount() { // 静态成员函数
        std::cout << "Count: " << count << std::endl;
    }
};

int Counter::count = 0; // 静态成员变量定义

int main() {
    Counter c1;
    Counter c2;
    Counter::showCount(); // 输出Count: 2
    return 0;
}
```

## 说明
- **常见陷阱**：
  - 静态成员变量在类外定义时，必须与类中的声明一致，确保类型和名字相同。
  - 静态局部变量在多线程环境中可能导致数据竞争，需要谨慎使用。
  
- **注意事项**：
  - 静态函数无法访问非静态成员变量和方法。
  - 静态全局变量的作用域仅限于定义它的文件，避免命名冲突。

## 一句话总结
C++中的`static`关键字用于控制变量和方法的生命周期与可见性，使其适用于多种上下文。