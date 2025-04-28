<!--
Meta Description: # C++ 中的 switch 语句详解 ## 概述 `switch` 语句是 C++ 编程语言中的一种控制流语句，用于根据变量的值选择执行不同的代码块。它通常用于替代多个 `if-else` 语句，使代码更加简洁和易读。 ## 文档 ### 目的 `switch` 语句允许根据一个表达式的值来执行...
Meta Keywords: case, switch, break, cout, endl
-->

# C++ 中的 switch 语句详解

## 概述
`switch` 语句是 C++ 编程语言中的一种控制流语句，用于根据变量的值选择执行不同的代码块。它通常用于替代多个 `if-else` 语句，使代码更加简洁和易读。

## 文档
### 目的
`switch` 语句允许根据一个表达式的值来执行不同的代码块。它通常用于处理多个可能的值，尤其是当这些值是整数、字符或枚举类型时。

### 使用方法
`switch` 语句的基本语法如下：

```cpp
switch (expression) {
    case constant1:
        // 当 expression 的值等于 constant1 时执行的代码
        break;
    case constant2:
        // 当 expression 的值等于 constant2 时执行的代码
        break;
    // 可以有任意数量的 case
    default:
        // 如果没有 case 匹配，则执行的代码
}
```

- `expression` 是要评估的表达式，通常是一个整数或字符。
- `case` 标签后面跟着常量值，用于匹配 `expression` 的值。
- `break` 语句用于终止 `switch` 语句，防止程序继续执行后续的 `case`。
- `default` 标签是可选的，用于处理没有匹配的情况。

## 示例
### 示例 1：基本用法
```cpp
#include <iostream>
using namespace std;

int main() {
    int day = 3;

    switch (day) {
        case 1:
            cout << "今天是星期一" << endl;
            break;
        case 2:
            cout << "今天是星期二" << endl;
            break;
        case 3:
            cout << "今天是星期三" << endl;
            break;
        default:
            cout << "无效的日期" << endl;
    }
    return 0;
}
```

### 示例 2：不使用 break
```cpp
#include <iostream>
using namespace std;

int main() {
    char grade = 'B';

    switch (grade) {
        case 'A':
            cout << "优秀" << endl;
        case 'B':
            cout << "良好" << endl;
        case 'C':
            cout << "及格" << endl;
        default:
            cout << "无效的成绩" << endl;
    }
    return 0;
}
```
在这个例子中，如果 `grade` 为 `B`，将输出 "良好"、"及格" 和 "无效的成绩"，因为缺少 `break` 语句。

## 说明
- **常见陷阱**：在 `switch` 语句中，如果忘记添加 `break` 语句，程序会继续执行下一个 `case` 的代码，这可能不是所期望的行为。
- **类型限制**：`switch` 语句要求 `expression` 必须是整数类型、字符类型或枚举类型，不能使用浮点数或字符串。
- **重复的 case 标签**：在同一个 `switch` 语句中，不能有重复的 `case` 标签，否则编译器将报错。

## 一句总结
C++ 中的 `switch` 语句是用于根据变量值执行不同代码块的有效控制流工具。