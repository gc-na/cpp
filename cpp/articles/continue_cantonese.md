<!--
Meta Description: # C++ 中的 "continue" 指令：用法與示例 ## 概述 C++ 中的 "continue" 指令是一個控制流語句，用於跳過當前迭代的剩餘部分，直接進入下一次迭代。這個指令通常在循環結構中使用，如 `for`、`while` 或 `do-while` 循環。 ## 文檔 ### 目的 "...
Meta Keywords: continue, while, int, cpp, 直接進入下一次迭代
-->

# C++ 中的 "continue" 指令：用法與示例

## 概述
C++ 中的 "continue" 指令是一個控制流語句，用於跳過當前迭代的剩餘部分，直接進入下一次迭代。這個指令通常在循環結構中使用，如 `for`、`while` 或 `do-while` 循環。

## 文檔
### 目的
"continue" 指令的主要目的是控制循環的執行流程，當遇到特定條件時，跳過當前迭代的剩餘語句，並開始下一次迭代，這在需要忽略某些條件下的操作時非常有用。

### 用法
"continue" 指令的基本語法如下：

```cpp
continue;
```

在循環中使用 "continue" 時，當執行到這條語句時，控制權會立即轉移到循環的條件判斷部分。如果條件滿足，則開始下一次迭代。

### 詳細說明
- 在 `for` 循環中，"continue" 會跳過當前迭代的後續語句，並執行增量表達式。
- 在 `while` 和 `do-while` 循環中，"continue" 會直接跳到條件檢查部分。
- 注意，"continue" 只能在循環結構中使用，若在非循環結構中使用會導致編譯錯誤。

## 示例
以下是 "continue" 指令的幾個基本使用範例：

### 示例 1：在 `for` 循環中使用
```cpp
#include <iostream>
using namespace std;

int main() {
    for (int i = 1; i <= 10; i++) {
        if (i % 2 == 0) {
            continue; // 如果是偶數，則跳過當前迭代
        }
        cout << i << " "; // 只會輸出奇數
    }
    return 0;
}
```

### 示例 2：在 `while` 循環中使用
```cpp
#include <iostream>
using namespace std;

int main() {
    int i = 1;
    while (i <= 10) {
        i++;
        if (i % 2 == 0) {
            continue; // 如果是偶數，則跳過當前迭代
        }
        cout << i << " "; // 只會輸出奇數
    }
    return 0;
}
```

## 解釋
使用 "continue" 指令時需要注意幾個常見的陷阱：
- 若不小心放置在不正確的位置，可能會導致循環無法正常終止，從而造成無限循環。
- 在嵌套循環中使用 "continue" 時，會影響最近的外層循環，因此需要特別小心，以免混淆邏輯。
- 使用 "continue" 雖然能使代碼更簡潔，但過度使用可能會降低代碼的可讀性，建議在必要時使用。

## 單行總結
C++ 中的 "continue" 指令可用來跳過當前迭代的剩餘部分，直接進入下一次迭代，從而有效控制循環流程。