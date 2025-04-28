<!--
Meta Description: # C++ 中的 bool 類型：布林值的使用與應用 ## 簡介 在 C++ 程式設計語言中，`bool` 是一種基本數據類型，用於表示布林值，只有兩個可能的取值：`true`（真）和 `false`（假）。這種數據類型常用於控制流程、條件判斷以及邏輯運算。 ## 文檔 ### 目的 `bool` ...
Meta Keywords: bool, true, false, result, cout
-->

# C++ 中的 bool 類型：布林值的使用與應用

## 簡介
在 C++ 程式設計語言中，`bool` 是一種基本數據類型，用於表示布林值，只有兩個可能的取值：`true`（真）和 `false`（假）。這種數據類型常用於控制流程、條件判斷以及邏輯運算。

## 文檔
### 目的
`bool` 類型主要用於表示邏輯值，通常用於條件語句（如 `if` 和 `while`）以及表達式的結果。這使得程式能夠根據條件執行不同的操作。

### 使用方法
在 C++ 中，`bool` 類型的定義和使用相當簡單。可以通過以下方式聲明和初始化一個布林變量：

```cpp
bool isTrue = true;  // 定義並初始化為 true
bool isFalse = false; // 定義並初始化為 false
```

### 詳細資訊
- `bool` 類型的大小通常為 1 個字節（8 位元），但具體大小可能依賴於實作。
- 布林值可以用於邏輯運算，如 AND (`&&`)、OR (`||`) 和 NOT (`!`)。
- 在條件語句中，任何非零值被視為 `true`，而零值則視為 `false`。

## 範例
以下是一些 `bool` 類型的基本使用範例：

### 範例 1：基本使用
```cpp
#include <iostream>
using namespace std;

int main() {
    bool isEven = true;
    if (isEven) {
        cout << "數字是偶數。" << endl;
    } else {
        cout << "數字是奇數。" << endl;
    }
    return 0;
}
```

### 範例 2：邏輯運算
```cpp
#include <iostream>
using namespace std;

int main() {
    bool a = true;
    bool b = false;

    bool result = a && b; // 並且運算，結果為 false
    cout << "a AND b: " << result << endl;

    result = a || b; // 或者運算，結果為 true
    cout << "a OR b: " << result << endl;

    result = !a; // 非運算，結果為 false
    cout << "NOT a: " << result << endl;

    return 0;
}
```

## 解釋
在使用 `bool` 時，有些常見的陷阱和注意事項：
- 確保使用 `true` 和 `false` 來初始化 `bool` 變量，避免使用整數（如 0 和 1），雖然會被隱式轉換，但不具可讀性。
- 在條件判斷中，請注意布林值的優先級，避免邏輯錯誤。
- 在 C++ 中，`bool` 類型不能與整數類型混合使用，這會導致編譯錯誤。

## 一句總結
`bool` 是 C++ 中用於表示邏輯真偽的基本數據類型，主要用於控制程序流程和進行邏輯運算。