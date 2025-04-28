<!--
Meta Description: # C++ 中的 decltype：用於推斷類型的強大工具 ## 概要 `decltype` 是 C++ 中一個強大的關鍵字，用於推斷表達式的類型，並在編譯時期決定變數的類型。這使得開發者在撰寫模板或需要靈活類型的程式碼時，可以更方便地處理複雜的類型。 ## 文檔 `decltype` 的主要用途是...
Meta Keywords: decltype, std, int, auto, sum
-->

# C++ 中的 decltype：用於推斷類型的強大工具

## 概要
`decltype` 是 C++ 中一個強大的關鍵字，用於推斷表達式的類型，並在編譯時期決定變數的類型。這使得開發者在撰寫模板或需要靈活類型的程式碼時，可以更方便地處理複雜的類型。

## 文檔
`decltype` 的主要用途是根據給定的表達式來推斷其類型。這對於模板編程特別有用，因為它可以根據傳遞的參數自動確定返回類型。

### 語法
```cpp
decltype(expression)
```

### 參數
- `expression`：可以是任何有效的 C++ 表達式。`decltype` 將根據該表達式的類型進行推斷。

### 返回值
`decltype` 返回的類型是表達式的類型。如果表達式是一個變數，則返回該變數的類型；如果表達式是一個函數調用，則返回該函數的返回類型。

### 例子
以下是 `decltype` 的一些基本用法示例：

```cpp
#include <iostream>

int main() {
    int a = 5;
    decltype(a) b = 10; // b 的類型為 int
    std::cout << "b: " << b << std::endl; // 輸出: b: 10

    double c = 3.14;
    decltype(c) d; // d 的類型為 double
    d = 2.71;
    std::cout << "d: " << d << std::endl; // 輸出: d: 2.71

    // 使用在函數返回類型上
    auto sum = [](int x, int y) -> decltype(x + y) {
        return x + y;
    };
    std::cout << "sum: " << sum(2, 3) << std::endl; // 輸出: sum: 5

    return 0;
}
```

## 解釋
使用 `decltype` 時需要注意以下幾點：

1. **表達式的值**：`decltype` 根據表達式的值來推斷類型，這意味著如果表達式的值是引用類型，則返回的類型也是引用類型。
   
2. **常量與非常量**：如果表達式是一個變數，並且該變數是常量，則 `decltype` 將返回該變數的常量類型。

3. **複雜表達式**：對於複雜的表達式，`decltype` 會根據其最終的計算結果來判斷類型，這可能會導致意外的類型推斷。

4. **與 auto 的關係**：`decltype` 和 `auto` 之間的區別在於，`decltype` 在編譯時期決定類型，而 `auto` 是在變數初始化時決定類型。

## 一行總結
`decltype` 是 C++ 中用於推斷表達式類型的關鍵字，能在編譯時期靈活處理複雜類型問題。