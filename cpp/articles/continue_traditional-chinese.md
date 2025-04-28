<!--
Meta Description: # C++ 中的 continue 關鍵字 ## 摘要 `continue` 是 C++ 中的一個控制語句，用於在迴圈內部跳過當前迭代的剩餘代碼，並立即開始下一次迭代。這個關鍵字常用於 `for`、`while` 和 `do-while` 迴圈，使程式碼更具可讀性和簡潔性。 ## 文檔 ### 目的...
Meta Keywords: continue, while, int, cpp, include
-->

# C++ 中的 continue 關鍵字

## 摘要
`continue` 是 C++ 中的一個控制語句，用於在迴圈內部跳過當前迭代的剩餘代碼，並立即開始下一次迭代。這個關鍵字常用於 `for`、`while` 和 `do-while` 迴圈，使程式碼更具可讀性和簡潔性。

## 文檔
### 目的
`continue` 關鍵字的主要目的是控制迴圈的執行流程，使其能夠在特定條件滿足時，跳過當前迭代的剩餘部分，直接進入下一次迭代的檢查。

### 使用方式
在 C++ 中，`continue` 可用於任何迴圈結構中。當 `continue` 被執行時，迴圈將立即停止當前迭代，並根據迴圈類型（例如 `for`、`while` 或 `do-while`）的結束條件轉向下一次迭代。

#### 語法範例
```cpp
for (初始化; 條件; 更新) {
    if (某個條件) {
        continue; // 跳過當前迭代
    }
    // 其他代碼
}
```

## 範例
以下是使用 `continue` 的基本示例：

### 使用 `for` 迴圈
```cpp
#include <iostream>
using namespace std;

int main() {
    for (int i = 1; i <= 10; i++) {
        if (i % 2 == 0) {
            continue; // 跳過偶數
        }
        cout << i << " "; // 只輸出奇數
    }
    return 0;
}
```

### 使用 `while` 迴圈
```cpp
#include <iostream>
using namespace std;

int main() {
    int i = 0;
    while (i < 10) {
        i++;
        if (i % 2 == 0) {
            continue; // 跳過偶數
        }
        cout << i << " "; // 只輸出奇數
    }
    return 0;
}
```

## 解釋
使用 `continue` 時需要注意以下幾點：
- `continue` 只影響它所在的迴圈，若有巢狀迴圈，則僅跳過內部迴圈的當前迭代。
- 在使用 `continue` 時，務必確保迴圈條件最終能夠達成，以避免產生無限迴圈。
- 不當使用 `continue` 可能導致程式邏輯不清晰，建議在必要時使用，並保持代碼的可讀性。

## 總結
`continue` 是 C++ 中用於控制迴圈流的關鍵字，能有效地跳過當前迭代的剩餘代碼，並開始下一次迭代。