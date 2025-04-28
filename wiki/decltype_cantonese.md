<!--
Meta Description: # C++ 中的 decltype：用於自動推斷類型的關鍵字 ## 概述 `decltype` 是 C++ 中的一個關鍵字，用於在編譯時自動推斷表達式的類型。它使得程序員能夠輕鬆獲取變量的類型，特別是在模板編程和泛型編程中非常有用。 ## 文檔 `decltype` 的主要目的是獲取一個表達式的類型...
Meta Keywords: decltype, int, cpp, 的類型為, vec
-->

# C++ 中的 decltype：用於自動推斷類型的關鍵字

## 概述
`decltype` 是 C++ 中的一個關鍵字，用於在編譯時自動推斷表達式的類型。它使得程序員能夠輕鬆獲取變量的類型，特別是在模板編程和泛型編程中非常有用。

## 文檔
`decltype` 的主要目的是獲取一個表達式的類型，而無需顯式地聲明該類型。這對於需要根據其他變量或表達式進行動態類型推斷的情況尤為重要。

### 用法
`decltype` 的基本語法如下：
```cpp
decltype(expression)
```
這裡，`expression` 可以是任何合法的 C++ 表達式。`decltype` 將返回該表達式的類型。

### 詳細說明
- **類型推斷**：`decltype` 有助於根據變量或函數的返回類型進行類型推斷。
- **與 auto 結合使用**：在 C++11 中引入的 `auto` 和 `decltype` 可以一起使用，讓類型推斷更加靈活。
- **常量引用**：使用 `decltype` 時，若表達式是某個變量，`decltype` 會保留其常量性質。例如，對於 `const int x = 10;`，`decltype(x)` 將返回 `const int`。

## 範例
以下是幾個使用 `decltype` 的基本範例：

### 範例 1：基本用法
```cpp
int a = 5;
decltype(a) b = 10; // b 的類型為 int
```

### 範例 2：推斷函數返回類型
```cpp
int add(int x, int y) {
    return x + y;
}

decltype(add(1, 2)) result; // result 的類型為 int
```

### 範例 3：推斷複雜類型
```cpp
std::vector<int> vec;
decltype(vec.begin()) it = vec.begin(); // it 的類型為 std::vector<int>::iterator
```

## 解釋
使用 `decltype` 時需要注意以下幾點：
- **完整性**：`decltype` 在推斷類型時會保留表達式的常量性質，這可能導致意外的類型結果。
- **不計算表達式**：`decltype` 不會計算其參數，只是用來獲取類型，這使得其非常高效。
- **不支持某些情況**：對於某些不完整或無法推斷的表達式，`decltype` 可能會導致編譯錯誤。

## 總結
`decltype` 是 C++ 中一個強大的工具，能夠自動推斷表達式的類型，為程序員提供靈活性和便利性。