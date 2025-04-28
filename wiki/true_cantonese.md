<!--
Meta Description: # C++ 中的 "true"：布爾值的基礎 ## 概述 在 C++ 程式語言中，`true` 是一個布爾常數，代表邏輯真值。它與 `false` 相對，後者表示邏輯假值。`true` 和 `false` 在控制程式流程時極為關鍵，例如在條件語句和循環中。 ## 文檔 ### 目的 `true` 用...
Meta Keywords: true, false, bool, cpp, flag
-->

# C++ 中的 "true"：布爾值的基礎

## 概述
在 C++ 程式語言中，`true` 是一個布爾常數，代表邏輯真值。它與 `false` 相對，後者表示邏輯假值。`true` 和 `false` 在控制程式流程時極為關鍵，例如在條件語句和循環中。

## 文檔
### 目的
`true` 用於表示布爾型別的真值，該型別通常用於條件表達式和邏輯運算。

### 使用方法
在 C++ 中，`true` 是一個內建的關鍵字，無需額外的聲明或引入。可以直接在程式中使用，例如：

```cpp
bool flag = true;
```

這行程式碼將變數 `flag` 初始化為真。

### 詳情
- **布爾型別**：C++ 中的布爾型別 (`bool`) 只能取 `true` 或 `false` 兩個值。這使得在邏輯運算中非常清晰和簡潔。
- **條件語句**：`true` 常用於 `if` 語句、`while` 循環等，例如：

```cpp
if (flag) {
    // 當 flag 為 true 時執行的程式碼
}
```

- **邏輯運算**：`true` 還可以與其他布爾運算符（如 `&&`、`||`）結合使用，形成複雜的邏輯表達式。

## 示例
以下是使用 `true` 的一些基本示例：

### 示例 1：使用 `true` 的條件語句
```cpp
#include <iostream>
using namespace std;

int main() {
    bool isRaining = true;

    if (isRaining) {
        cout << "請帶上雨具。" << endl;
    } else {
        cout << "今天天氣晴朗！" << endl;
    }
    return 0;
}
```

### 示例 2：使用 `true` 的循環
```cpp
#include <iostream>
using namespace std;

int main() {
    bool keepGoing = true;

    while (keepGoing) {
        cout << "這個循環會持續運行。" << endl;
        // 這裡可以加入一個條件來改變 keepGoing 的值
        // keepGoing = false; // 取消循環的條件
    }
    return 0;
}
```

## 解釋
- **常見陷阱**：在使用 `true` 時，確保變數的類型為 `bool`。將 `true` 和其他數字類型相混淆（例如整數）可能會導致邏輯錯誤。
- **隱式轉換**：在 C++ 中，任何非零的整數都被視為 `true`，而零則被視為 `false`。這一點在進行邏輯運算時需要特別注意。
- **可讀性**：儘管可以使用整數代替 `true`（如 1），但為了程式碼的可讀性，建議始終使用 `true` 和 `false`。

## 一句總結
在 C++ 中，`true` 是用來表示邏輯真值的布爾常數，對於控制程式流程至關重要。