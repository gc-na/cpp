<!--
Meta Description: # C++ 中的 case：用於 switch 語句的關鍵字 ## 簡介 在 C++ 中，`case` 關鍵字用於 `switch` 語句，允許根據不同的值執行不同的程式碼區塊。這種結構使得多重條件判斷更為簡潔易讀，特別是當有多個可能的選擇時。 ## 文件說明 `case` 是 `switch` 語...
Meta Keywords: case, break, switch, expression, default
-->

# C++ 中的 case：用於 switch 語句的關鍵字

## 簡介
在 C++ 中，`case` 關鍵字用於 `switch` 語句，允許根據不同的值執行不同的程式碼區塊。這種結構使得多重條件判斷更為簡潔易讀，特別是當有多個可能的選擇時。

## 文件說明
`case` 是 `switch` 語句的一部分，用於定義每個可能的條件。當變數的值與某個 `case` 標籤匹配時，對應的程式碼將被執行。`case` 標籤必須是常量表達式，並且可以使用整數或字元類型。

### 用法
`case` 的基本語法如下：

```cpp
switch (expression) {
    case constant1:
        // 當 expression 等於 constant1 時執行的程式碼
        break;
    case constant2:
        // 當 expression 等於 constant2 時執行的程式碼
        break;
    default:
        // 當 expression 不匹配任何 case 時執行的程式碼
}
```

- `expression`：一個整數或字元類型的變數。
- `constant1`, `constant2`：對應的常量值。
- `break`：用於結束當前的 `case` 區塊，防止執行後續的 `case`。

## 範例
以下是使用 `case` 的基本範例：

```cpp
#include <iostream>
using namespace std;

int main() {
    int day = 3;

    switch (day) {
        case 1:
            cout << "星期一" << endl;
            break;
        case 2:
            cout << "星期二" << endl;
            break;
        case 3:
            cout << "星期三" << endl;
            break;
        default:
            cout << "無效的日子" << endl;
    }
    return 0;
}
```

在這個例子中，變數 `day` 的值為 3，因此將輸出 "星期三"。

## 解釋
使用 `case` 時需要注意以下幾點：
- **忘記 `break`**：如果沒有在每個 `case` 的結尾添加 `break`，程式將繼續執行後續的 `case`，這可能導致意外行為。
- **重複的 `case` 標籤**：每個 `case` 標籤必須是唯一的，否則將導致編譯錯誤。
- **使用 `default`**：雖然 `default` 是可選的，但它可以幫助處理不在任何 `case` 中的情況，提升程式的健壯性。

## 總結
在 C++ 中，`case` 關鍵字用於 `switch` 語句，幫助簡化多條件判斷的程式碼結構。