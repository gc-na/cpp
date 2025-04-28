<!--
Meta Description: # C++ 中的 switch 語句：用法與範例 ## 概述 在 C++ 中，`switch` 語句是一種多分支選擇結構，允許根據變量的值執行不同的代碼區塊。它提供了一種簡單的方式來替代多個 `if-else` 條件判斷，特別是在處理多個常數值時。 ## 文件說明 ### 目的 `switch` 語...
Meta Keywords: case, switch, break, default, cout
-->

# C++ 中的 switch 語句：用法與範例

## 概述
在 C++ 中，`switch` 語句是一種多分支選擇結構，允許根據變量的值執行不同的代碼區塊。它提供了一種簡單的方式來替代多個 `if-else` 條件判斷，特別是在處理多個常數值時。

## 文件說明
### 目的
`switch` 語句用於根據指定表達式的值來選擇執行的代碼段。它通常用於處理整數或字符類型的變量。

### 使用方法
`switch` 語句的語法結構如下：

```cpp
switch (expression) {
    case constant1:
        // 執行代碼區塊1
        break;
    case constant2:
        // 執行代碼區塊2
        break;
    // 可選的其他 case
    default:
        // 執行默認代碼區塊
}
```

- **expression**：一個整數或字符類型的表達式。
- **case constant**：與表達式比較的常數值。
- **break**：用於終止 `switch` 語句，防止執行後續的 `case` 或 `default` 代碼。
- **default**：可選的，當所有 `case` 都不匹配時執行的代碼區塊。

## 範例
以下是使用 `switch` 語句的簡單範例：

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
            cout << "未知的星期" << endl;
    }

    return 0;
}
```

在這個例子中，根據變量 `day` 的值，程序將輸出相應的星期幾。

## 解釋
在使用 `switch` 語句時，開發者需注意以下幾點：

1. **缺少 break 語句**：如果省略 `break`，程序將繼續執行下個 `case` 的代碼，這可能不是預期的行為。
2. **常量要求**：`case` 中的常量必須是常數表達式，不能是變量或運算結果。
3. **重複的 case**：同一個 `case` 標籤不能重複，否則會導致編譯錯誤。

此外，`switch` 語句不支持浮點數類型或字符串類型的表達式。

## 總結
C++ 中的 `switch` 語句是一種高效的多分支選擇結構，適合用於處理多個常數條件的情況。