<!--
Meta Description: # C++ 命名空間 (Namespace) 詳細介紹 ## 概述 命名空間（Namespace）是 C++ 中的一種封裝機制，用來組織代碼和避免命名衝突。它允許開發者在同一個作用域中使用相同名稱的變量、函數或類，但在不同的命名空間中。 ## 文檔 ### 目的 命名空間的主要目的是解決代碼中可能出...
Meta Keywords: namespace, int, add, std, cpp
-->

# C++ 命名空間 (Namespace) 詳細介紹

## 概述
命名空間（Namespace）是 C++ 中的一種封裝機制，用來組織代碼和避免命名衝突。它允許開發者在同一個作用域中使用相同名稱的變量、函數或類，但在不同的命名空間中。

## 文檔
### 目的
命名空間的主要目的是解決代碼中可能出現的命名衝突問題。隨著大型項目的擴展，可能會導致多個庫或模塊中出現相同名稱的標識符，這時命名空間提供了一種有效的解決方案。

### 使用方式
在 C++ 中，定義命名空間的語法如下：
```cpp
namespace NamespaceName {
    // 代碼，例如變量、函數或類的定義
}
```

使用命名空間中的標識符時，可以透過以下兩種方式訪問：
1. 使用範圍解析運算符 (`::`)：
   ```cpp
   NamespaceName::functionName();
   ```
2. 使用 `using` 聲明：
   ```cpp
   using namespace NamespaceName;
   functionName();
   ```

### 詳細信息
- 命名空間可以嵌套，也就是說，命名空間可以在其他命名空間中定義。
- C++ 標準庫中有許多預定義的命名空間，例如 `std`，用於標準函數和類。
- 可以在同一個文件中多次定義同一命名空間，這樣可以將代碼結構化。

## 範例
以下是一個簡單的命名空間使用範例：

```cpp
#include <iostream>

namespace Math {
    int add(int a, int b) {
        return a + b;
    }
}

namespace Science {
    int add(int a, int b) {
        return a + b + 1; // 假設這是科學計算
    }
}

int main() {
    std::cout << "Math add: " << Math::add(3, 4) << std::endl; // 輸出 7
    std::cout << "Science add: " << Science::add(3, 4) << std::endl; // 輸出 8
    return 0;
}
```

## 解釋
- **常見陷阱**：使用 `using namespace` 可能會導致命名衝突，特別是在大型項目中。建議在大的代碼庫中謹慎使用。
- **不完全限定名稱**：如果您使用 `using` 聲明，則不再需要使用範圍解析運算符，但這可能會導致不可預期的命名衝突。
- **命名空間與類**：命名空間和類都是用來封裝代碼的結構，但命名空間不支持繼承，而類則支持。

## 一句話總結
命名空間是 C++ 中用來組織代碼和避免命名衝突的有效工具。