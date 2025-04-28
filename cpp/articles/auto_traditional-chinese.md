<!--
Meta Description: # C++ 中的 auto 關鍵字：自動類型推斷 ## 簡介 `auto` 是 C++11 標準引入的一個關鍵字，允許編譯器根據初始化表達式自動推斷變量的類型，從而使程式碼更加簡潔和易於維護。 ## 文檔 ### 目的 `auto` 的主要目的是簡化變量類型的聲明，特別是在處理複雜類型（如迭代器、L...
Meta Keywords: auto, variablename, expression, int, vec
-->

# C++ 中的 auto 關鍵字：自動類型推斷

## 簡介
`auto` 是 C++11 標準引入的一個關鍵字，允許編譯器根據初始化表達式自動推斷變量的類型，從而使程式碼更加簡潔和易於維護。

## 文檔
### 目的
`auto` 的主要目的是簡化變量類型的聲明，特別是在處理複雜類型（如迭代器、Lambda 表達式等）時，開發者不再需要手動指定類型。

### 使用方式
`auto` 關鍵字可以用於變量的聲明，其基本語法如下：
```cpp
auto variableName = expression;
```
在這裡，`variableName` 是變量的名稱，而 `expression` 是用來初始化變量的表達式。編譯器會根據 `expression` 自動推斷出 `variableName` 的類型。

### 詳細說明
- `auto` 只能在變量聲明和初始化的上下文中使用。
- `auto` 不能用於函數的返回類型聲明，除非與 `decltype` 一起使用。
- C++14 進一步增強了 `auto` 的功能，允許用於函數參數的類型推斷。

## 範例
以下是 `auto` 關鍵字的基本使用範例：

```cpp
#include <iostream>
#include <vector>

int main() {
    // 使用 auto 自動推斷整數類型
    auto a = 10; // a 的類型為 int

    // 使用 auto 推斷浮點數類型
    auto b = 3.14; // b 的類型為 double

    // 使用 auto 推斷容器迭代器類型
    std::vector<int> vec = {1, 2, 3, 4, 5};
    for (auto it = vec.begin(); it != vec.end(); ++it) {
        std::cout << *it << " ";
    }

    return 0;
}
```

## 解釋
### 常見問題
- **類型不明確**：`auto` 的類型是根據初始化表達式的類型推斷的，若表達式類型不清晰，可能導致錯誤。例如，對於 `auto x = {1, 2, 3};`，這將產生編譯錯誤，因為編譯器無法推斷出 `x` 的類型。
- **引用和指針問題**：如果希望 `auto` 推斷為引用類型，可以使用 `auto&`。例如：`auto& x = someVariable;` 這樣 `x` 將是 `someVariable` 的引用。

## 一句總結
`auto` 是 C++ 的一個關鍵字，通過自動類型推斷來簡化變量的聲明和初始化過程。