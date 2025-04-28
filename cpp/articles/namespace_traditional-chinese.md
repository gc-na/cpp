<!--
Meta Description: # C++ 命名空間 (Namespace) 詳解 ## 概述 命名空間 (namespace) 是 C++ 中用來組織代碼和避免命名衝突的工具。它允許開發者將全局範圍的標識符（如變數、函數和類）分組，從而提高代碼的可維護性和可讀性。 ## 文檔 命名空間的主要目的是避免不同庫或模塊之間的命名衝突。...
Meta Keywords: namespace, myfunction, cpp, namespacename, double
-->

# C++ 命名空間 (Namespace) 詳解

## 概述
命名空間 (namespace) 是 C++ 中用來組織代碼和避免命名衝突的工具。它允許開發者將全局範圍的標識符（如變數、函數和類）分組，從而提高代碼的可維護性和可讀性。

## 文檔
命名空間的主要目的是避免不同庫或模塊之間的命名衝突。當多個庫使用相同的標識符時，命名空間可以有效地區分這些標識符。命名空間的定義使用 `namespace` 關鍵字，並可以包含多個成員，包括變數、函數和類。

### 用法
命名空間的基本語法如下：

```cpp
namespace NamespaceName {
    // 成員定義
    int myVariable;
    void myFunction() {
        // 函數實現
    }
}
```

要訪問命名空間中的成員，可以使用範圍解析運算符 `::`：

```cpp
NamespaceName::myVariable = 10;
NamespaceName::myFunction();
```

此外，C++ 允許使用 `using` 關鍵字來簡化訪問：

```cpp
using NamespaceName::myFunction;
// 現在可以直接調用 myFunction()
myFunction();
```

## 範例
以下是一個簡單的命名空間示例：

```cpp
#include <iostream>

namespace Math {
    const double PI = 3.141592653589793;
    double add(double a, double b) {
        return a + b;
    }
}

int main() {
    std::cout << "PI: " << Math::PI << std::endl;
    std::cout << "3 + 4 = " << Math::add(3, 4) << std::endl;
    return 0;
}
```

### 輸出
```
PI: 3.141592653589793
3 + 4 = 7
```

## 解釋
使用命名空間時，有幾個常見的陷阱和注意事項：

1. **命名衝突**：如果不小心在不同的命名空間中使用相同的標識符，仍然可能會導致衝突。這是因為 `using` 語句會將命名空間的所有成員引入到當前作用域。

2. **嵌套命名空間**：C++11 引入了嵌套命名空間的功能，可以在一個命名空間內再定義另一個命名空間。使用時需要注意正確的範圍解析。

3. **全局命名空間**：所有不在命名空間內的標識符默認屬於全局命名空間。這可能導致全局變數與命名空間內的變數發生衝突。

## 總結
命名空間是 C++ 中組織代碼和避免命名衝突的有效工具，能提高代碼的可讀性和可維護性。