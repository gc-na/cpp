<!--
Meta Description: # C++ 中的 typeid：類型識別的關鍵命令 ## 概要 `typeid` 是 C++ 中用於獲取變量或表達式的數據類型信息的運算符。它可以用於靜態類型檢查，並在運行時提供有關對象類型的詳細信息。 ## 文檔 `typeid` 運算符的主要目的是在編譯時和運行時獲取類型信息。當使用 `type...
Meta Keywords: typeid, std, base, derived, name
-->

# C++ 中的 typeid：類型識別的關鍵命令

## 概要
`typeid` 是 C++ 中用於獲取變量或表達式的數據類型信息的運算符。它可以用於靜態類型檢查，並在運行時提供有關對象類型的詳細信息。

## 文檔
`typeid` 運算符的主要目的是在編譯時和運行時獲取類型信息。當使用 `typeid` 時，會返回一個 `std::type_info` 對象，該對象包含有關指定類型的詳細信息，例如類型名稱和其他屬性。

### 用法
基本語法如下：
```cpp
#include <typeinfo>

typeid(expression)
```
- `expression` 可以是任何變量、類型或類型運算符。

對於多態類型，`typeid` 可以用於獲取動態類型信息，這在使用基類指針或引用時特別有用。

### 例子
以下是 `typeid` 的一些基本用法示例：

```cpp
#include <iostream>
#include <typeinfo>

class Base {};
class Derived : public Base {};

int main() {
    int a = 5;
    double b = 3.14;
    Base base;
    Derived derived;

    std::cout << "Type of a: " << typeid(a).name() << std::endl;        // 輸出 int
    std::cout << "Type of b: " << typeid(b).name() << std::endl;        // 輸出 double
    std::cout << "Type of base: " << typeid(base).name() << std::endl;  // 輸出 Base
    std::cout << "Type of derived: " << typeid(derived).name() << std::endl; // 輸出 Derived

    Base* ptr = new Derived();
    std::cout << "Dynamic type of ptr: " << typeid(*ptr).name() << std::endl; // 輸出 Derived
    delete ptr;

    return 0;
}
```

## 解釋
在使用 `typeid` 時，有幾個常見的注意事項：
1. **多態性**：對於使用了虛擬函數的類型，`typeid` 會返回動態類型，而非靜態類型。
2. **未定義行為**：對於未初始化的指針或引用使用 `typeid` 可能會導致未定義的行為。
3. **類型名稱格式**：使用 `typeid(...).name()` 取得的類型名稱在不同的編譯器中可能會有所不同。

## 總結
`typeid` 是 C++ 中一個強大的運算符，用於獲取變量或表達式的類型信息，尤其在處理多態性時非常有用。