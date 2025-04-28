<!--
Meta Description: # C++ 中的 "case" 关键字详解 ## 概述 在 C++ 中，`case` 关键字用于 `switch` 语句中，以定义不同的执行路径。这种结构使得根据变量的值执行不同代码块变得更加简洁和易读。 ## 文档 ### 目的 `case` 关键字用来表示 `switch` 语句中的一个分支。每...
Meta Keywords: case, switch, break, cout, endl
-->

# C++ 中的 "case" 关键字详解

## 概述
在 C++ 中，`case` 关键字用于 `switch` 语句中，以定义不同的执行路径。这种结构使得根据变量的值执行不同代码块变得更加简洁和易读。

## 文档
### 目的
`case` 关键字用来表示 `switch` 语句中的一个分支。每个 `case` 后面跟随一个常量表达式，当 `switch` 表达式的值与某个 `case` 表达式匹配时，程序将执行该 `case` 下的代码。

### 使用方法
`case` 通常与 `switch` 语句配合使用，语法如下：

```cpp
switch (expression) {
    case constant1:
        // 执行代码块1
        break;
    case constant2:
        // 执行代码块2
        break;
    default:
        // 执行默认代码块
}
```

- `expression` 是要评估的变量或表达式。
- `constant` 是与 `expression` 进行比较的常量值。
- `break` 语句用于退出 `switch` 语句，防止执行下一个 `case`。

### 详细信息
- `case` 后面的常量可以是整数常量、枚举常量或字符常量，但必须是常量表达式。
- 如果没有 `break` 语句，程序将继续执行下一个 `case`，这被称为“fall-through”。
- `default` 是可选的，代表当没有 `case` 匹配时执行的代码。

## 示例
### 示例 1：基本用法
```cpp
#include <iostream>
using namespace std;

int main() {
    int day = 3;

    switch (day) {
        case 1:
            cout << "星期一" << endl;
            break;
        case 2:
            cout << "星期二" << endl;
            break;
        case 3:
            cout << "星期三" << endl;
            break;
        default:
            cout << "无效的日期" << endl;
    }

    return 0;
}
```

### 示例 2：fall-through 示例
```cpp
#include <iostream>
using namespace std;

int main() {
    int grade = 85;

    switch (grade / 10) {
        case 10:
        case 9:
            cout << "优秀" << endl;
            break;
        case 8:
            cout << "良好" << endl;
            break;
        case 7:
            cout << "中等" << endl;
            break;
        default:
            cout << "及格或不及格" << endl;
    }

    return 0;
}
```

## 说明
- **常见陷阱**：忘记在 `case` 语句中使用 `break`，导致代码意外地执行多个分支。
- **类型匹配**：`switch` 表达式的类型与 `case` 常量的类型必须一致，否则会产生编译错误。
- **只支持整型**：`switch` 只支持整数类型（如 `int`, `char`），不能直接使用浮点数或字符串。

## 一句话总结
`case` 关键字在 C++ 中用于 `switch` 语句，提供了基于常量值执行不同代码块的功能。