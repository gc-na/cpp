<!--
Meta Description: # C++ 中的 dynamic_cast：動態類型轉換的詳細指南 ## 概要 `dynamic_cast` 是 C++ 中用於安全地進行類型轉換的運算符，特別是在多態性（Polymorphism）中，能夠將基類指標或引用轉換為派生類型。 ## 文件說明 `dynamic_cast` 是 C++ 的...
Meta Keywords: dynamic_cast, std, derived, base, class
-->

# C++ 中的 dynamic_cast：動態類型轉換的詳細指南

## 概要
`dynamic_cast` 是 C++ 中用於安全地進行類型轉換的運算符，特別是在多態性（Polymorphism）中，能夠將基類指標或引用轉換為派生類型。

## 文件說明
`dynamic_cast` 是 C++ 的一個運算符，主要用於執行運行時類型檢查，確保在進行類型轉換時的安全性。它通常與類型繼承有關，特別是當使用虛擬函數時，可以安全地將基類指標或引用轉換為派生類型。

### 目的
`dynamic_cast` 的主要目的是在多態性上下文中安全地轉換指標或引用。這意味著它能夠在運行時檢查目標類型是否是指定類型的有效子類型。

### 使用方法
`dynamic_cast` 的語法如下：

```cpp
dynamic_cast<type>(expression)
```

- `type` 是要轉換到的目標類型。
- `expression` 是要進行類型轉換的基類指標或引用。

若轉換成功，`dynamic_cast` 返回轉換後的類型指標或引用；如果轉換失敗，則對於指標返回 `nullptr`，對於引用則會拋出 `std::bad_cast` 異常。

### 注意事項
- `dynamic_cast` 只能用於具有虛擬函數的類。
- 在轉換過程中，必須確保基類和派生類之間存在正確的繼承關係。

## 範例
以下是 `dynamic_cast` 的基本使用範例：

```cpp
#include <iostream>
#include <typeinfo>

class Base {
public:
    virtual ~Base() {}  // 必須有虛擬析構函數
};

class Derived : public Base {
public:
    void show() { std::cout << "Derived class" << std::endl; }
};

int main() {
    Base* basePtr = new Derived();  // 基類指標指向派生類物件
    Derived* derivedPtr = dynamic_cast<Derived*>(basePtr);

    if (derivedPtr) {
        derivedPtr->show();  // 轉換成功
    } else {
        std::cout << "Conversion failed" << std::endl;
    }

    delete basePtr;
    return 0;
}
```

## 解釋
### 常見的陷阱
- **未使用虛擬函數**：如果基類中沒有虛擬函數，則 `dynamic_cast` 將無法正常工作，因為運行時類型信息(RTTI)無法被正確獲取。
- **不正確的繼承關係**：確保正確的類型繼承結構，否則轉換將失敗。
- **引用類型轉換失敗**：如果將 `dynamic_cast` 用於引用類型，轉換失敗時會拋出異常，因此需要用 `try-catch` 块來捕獲可能的異常。

## 總結
`dynamic_cast` 是 C++ 中進行安全類型轉換的重要工具，特別是在面對多態性時，能有效避免類型轉換錯誤。