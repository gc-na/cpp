<!--
Meta Description: # C++ 中的 break 語句：用法與示例 ## 簡介 `break` 語句是 C++ 中一個重要的控制語句，用於提前終止循環或 switch 語句的執行。在需要根據特定條件中止一個迴圈時，`break` 是一個非常有用的工具。 ## 文檔 ### 目的 `break` 語句的主要目的是當滿足特...
Meta Keywords: break, switch, case, int, cout
-->

# C++ 中的 break 語句：用法與示例

## 簡介
`break` 語句是 C++ 中一個重要的控制語句，用於提前終止循環或 switch 語句的執行。在需要根據特定條件中止一個迴圈時，`break` 是一個非常有用的工具。

## 文檔
### 目的
`break` 語句的主要目的是當滿足特定條件時，立即退出當前的循環或 switch 語句，從而幫助提高程式的效率和可讀性。

### 用法
`break` 語句可以用於以下兩種情況：
1. **循環結構**：如 `for`、`while` 或 `do-while` 循環。
2. **switch 語句**：用於結束一個 case 的執行。

語法：
```cpp
break;
```

### 詳細說明
在循環中，當 `break` 被執行時，控制流會立即跳出該循環，並繼續執行循環後的代碼。在 switch 語句中，`break` 使得控制流跳出 switch 結構，防止執行後續的 case。

## 示例
以下是 `break` 語句在 C++ 中的基本用法範例：

### 示例 1：在 for 循環中使用 break
```cpp
#include <iostream>
using namespace std;

int main() {
    for (int i = 0; i < 10; i++) {
        if (i == 5) {
            break; // 當 i 等於 5 時，退出循環
        }
        cout << i << " ";
    }
    return 0;
}
```
*輸出：0 1 2 3 4*

### 示例 2：在 switch 語句中使用 break
```cpp
#include <iostream>
using namespace std;

int main() {
    int x = 2;
    switch (x) {
        case 1:
            cout << "一";
            break; // 結束當前 case
        case 2:
            cout << "二";
            break; // 結束當前 case
        default:
            cout << "其他";
    }
    return 0;
}
```
*輸出：二*

## 解釋
使用 `break` 語句時需要注意以下幾點：
1. **不在循環外使用**：`break` 語句只能在循環或 switch 語句內部使用，否則會導致編譯錯誤。
2. **影響嵌套結構**：在嵌套循環中，`break` 只會結束最近一層的循環。如果需要跳出多層循環，可以使用標籤或其他控制結構。
3. **忽略後續 case**：在 switch 語句中，若不使用 `break`，則會出現「fall-through」現象，導致後續的 case 也被執行。

## 一句總結
`break` 語句用於提前終止循環或 switch 的執行，是 C++ 中一個基本而重要的控制流工具。