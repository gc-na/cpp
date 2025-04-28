<!--
Meta Description: # C++ 中的 "default" 關鍵字 ## 摘要 在 C++ 中，"default" 關鍵字主要用於自動生成特殊成員函式，特別是在類別中定義預設構造函式、複製構造函式和移動構造函式時，讓開發者能夠簡化代碼。 ## 文檔 ### 目的 "Default" 關鍵字的主要目的是告訴編譯器生成默認版...
Meta Keywords: default, example, myclass, 預設構造函式, 複製構造函式
-->

# C++ 中的 "default" 關鍵字

## 摘要
在 C++ 中，"default" 關鍵字主要用於自動生成特殊成員函式，特別是在類別中定義預設構造函式、複製構造函式和移動構造函式時，讓開發者能夠簡化代碼。

## 文檔
### 目的
"Default" 關鍵字的主要目的是告訴編譯器生成默認版本的構造函式或運算符。這樣可以避免手動編寫這些函式，特別是在冗長或複雜的類別中。

### 使用方法
在 C++11 及以後的版本中，"default" 可以用於以下幾種情況：
1. **預設構造函式**：當需要自動生成一個沒有參數的構造函式時，可以使用 `= default`。
2. **複製構造函式**：如果您不想手動實現複製構造函式，可以將其設置為 `= default`。
3. **移動構造函式**：同樣，對於移動構造函式，您可以使用 `= default` 來自動生成。

### 詳細說明
使用 "default" 的一個基本範例如下：
```cpp
class MyClass {
public:
    MyClass() = default;               // 預設構造函式
    MyClass(const MyClass&) = default;  // 複製構造函式
    MyClass(MyClass&&) = default;       // 移動構造函式
};
```
這樣的寫法告訴編譯器自動生成這些函式，而不需要開發者自己編寫。

## 範例
以下是使用 "default" 的基本範例：

```cpp
#include <iostream>

class Example {
public:
    Example() = default;                // 預設構造函式
    Example(const Example&) = default;  // 複製構造函式
    Example(Example&&) = default;       // 移動構造函式

    void display() {
        std::cout << "Example object created!" << std::endl;
    }
};

int main() {
    Example e1;              // 使用預設構造函式
    Example e2 = e1;        // 使用複製構造函式
    Example e3 = std::move(e1); // 使用移動構造函式
    e2.display();
    e3.display();
    return 0;
}
```

## 解釋
雖然 "default" 提供了一個方便的機制來自動生成函式，但仍需注意以下幾點：
- 在某些情況下，類別的成員變量可能無法使用默認的構造函式，這會導致編譯錯誤。
- 當類別包含指針或資源管理的成員時，使用默認函式可能會導致潛在的資源洩漏或錯誤的行為，因此應謹慎使用。
- 確保在使用 "default" 時，類別的所有成員都可以被正確初始化。

## 一句總結
在 C++ 中，"default" 關鍵字用於自動生成類別的特殊成員函式，簡化代碼並提高可讀性。