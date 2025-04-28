<!--
Meta Description: # C++ 中的 static_cast：靜態轉換的全面指南 ## 概述 `static_cast` 是 C++ 語言中的一種類型轉換運算子，用於在不同類型之間進行靜態轉換。這個運算子提供一種安全的方式來轉換指標或引用類型，並且能夠進行基本數據類型之間的轉換。 ## 文檔 `static_cast`...
Meta Keywords: static_cast, int, derived, class, base
-->

# C++ 中的 static_cast：靜態轉換的全面指南

## 概述
`static_cast` 是 C++ 語言中的一種類型轉換運算子，用於在不同類型之間進行靜態轉換。這個運算子提供一種安全的方式來轉換指標或引用類型，並且能夠進行基本數據類型之間的轉換。

## 文檔
`static_cast` 的主要目的是進行類型轉換，並且在編譯時檢查轉換的合法性。與傳統的 C 語言風格的轉換不同，使用 `static_cast` 可以提高代碼的可讀性和安全性。

### 用法
`static_cast` 的語法如下：
```cpp
static_cast<目標類型>(表達式)
```
- **目標類型**：要轉換為的類型。
- **表達式**：被轉換的值或對象。

### 詳細說明
`static_cast` 可以用於：
- 基本數據類型之間的轉換（例如：`int` 轉換為 `float`）。
- 對象類型之間的安全轉換，當涉及到繼承時，它可以用於轉換基類和派生類之間的指標或引用。
- 隱式轉換不能滿足的情況，例如當從 `void*` 指標轉換為具體類型的指標。

使用 `static_cast` 而不是 C 語言的強制轉換可以幫助編譯器檢查轉換的合理性，減少潛在的錯誤。

## 示例
### 基本使用示例
```cpp
#include <iostream>
using namespace std;

class Base {
public:
    virtual void show() { cout << "Base class\n"; }
};

class Derived : public Base {
public:
    void show() override { cout << "Derived class\n"; }
};

int main() {
    Base* b = new Derived();
    Derived* d = static_cast<Derived*>(b); // 基類指標轉換為派生類指標
    d->show(); // 輸出: Derived class
    delete b;
    return 0;
}
```

### 數據類型轉換示例
```cpp
#include <iostream>
using namespace std;

int main() {
    double pi = 3.14;
    int intPi = static_cast<int>(pi); // double 轉換為 int
    cout << "轉換前: " << pi << ", 轉換後: " << intPi << endl; // 輸出: 轉換前: 3.14, 轉換後: 3
    return 0;
}
```

## 解釋
使用 `static_cast` 時需要注意以下幾點：
- **安全性**：`static_cast` 會檢查轉換的合法性，但不會進行運行時檢查。如果轉換不正確，可能會導致未定義的行為。
- **多重繼承**：在多重繼承的情況下，`static_cast` 可能不會如預期般工作，因為派生類的指標可能需要指定具體的基類。
- **指標轉換**：當進行指標轉換時，確保原指標實際上是指向所需的派生類，而不是其他類型，否則會出現錯誤。

## 總結
`static_cast` 是 C++ 中一種安全且有效的靜態類型轉換工具，適用於多種類型之間的轉換。