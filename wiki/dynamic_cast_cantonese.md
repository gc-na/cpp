<!--
Meta Description: # C++ 中的 dynamic_cast：用於安全的類型轉換 ## 概述 `dynamic_cast` 是 C++ 中的一個運算符，用於在多態性類型間進行安全的類型轉換，特別是在類層級結構中。它主要用於將基類指針或引用轉換為派生類類型，並能在運行時檢查類型的正確性。 ## 文檔 ### 目的 `d...
Meta Keywords: dynamic_cast, std, derived, base, class
-->

# C++ 中的 dynamic_cast：用於安全的類型轉換

## 概述
`dynamic_cast` 是 C++ 中的一個運算符，用於在多態性類型間進行安全的類型轉換，特別是在類層級結構中。它主要用於將基類指針或引用轉換為派生類類型，並能在運行時檢查類型的正確性。

## 文檔
### 目的
`dynamic_cast` 主要用於處理多態性，幫助程序員在運行時確認對象的實際類型，避免不安全的轉換。它適用於有虛擬函數的類別，並且能夠在轉換失敗時返回空指針或拋出異常。

### 使用方法
`dynamic_cast` 的語法如下：
```cpp
dynamic_cast<目標類型>(表達式)
```
- **目標類型**：要轉換到的類型，必須是指針或引用類型。
- **表達式**：要轉換的基類指針或引用。

### 詳細說明
- `dynamic_cast` 只能用於具有虛擬函數的類。
- 如果轉換成功，返回的指針或引用將指向目標類型的對象；如果失敗，對於指針返回 `nullptr`，對於引用則會拋出 `std::bad_cast` 異常。
- 使用 `dynamic_cast` 進行類型檢查時，建議搭配 `typeid` 來進一步確認類型。

## 範例
以下是 `dynamic_cast` 的基本使用範例：

```cpp
#include <iostream>
#include <typeinfo>

class Base {
public:
    virtual ~Base() {}
};

class Derived : public Base {
public:
    void show() {
        std::cout << "Derived class method called." << std::endl;
    }
};

int main() {
    Base* b = new Derived();
    
    // 使用 dynamic_cast 進行類型轉換
    Derived* d = dynamic_cast<Derived*>(b);
    if (d) {
        d->show(); // 成功轉換，調用 Derived 的方法
    } else {
        std::cout << "轉換失敗。" << std::endl;
    }
    
    delete b;
    return 0;
}
```

## 解釋
### 常見問題
1. **不支持非多態類型**：`dynamic_cast` 不能用於沒有虛擬函數的類型，因此若類型不是多態的，轉換將無法進行。
2. **性能開銷**：由於 `dynamic_cast` 需要運行時檢查類型，可能會引入額外的性能開銷，特別是在頻繁調用的情況下。
3. **引用轉換的異常**：如果轉換失敗，對於引用類型，將拋出 `std::bad_cast` 異常，這需要在程式中進行異常處理。

## 一句總結
`dynamic_cast` 是 C++ 中用於安全類型轉換的運算符，能在多態性環境中有效地檢查和轉換類型。