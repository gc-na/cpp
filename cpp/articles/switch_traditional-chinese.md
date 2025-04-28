<!--
Meta Description: # C++ 中的 switch 陳述式：用於多重條件選擇的強大工具 ## 概述 在 C++ 中，`switch` 陳述式是一種控制結構，用於根據變數的值選擇執行的程式碼區塊。這種結構特別適用於需要基於整數或字元類型的多重選擇情況，能夠提高程式碼的可讀性與維護性。 ## 文檔 ### 目的 `swit...
Meta Keywords: case, switch, break, cout, endl
-->

# C++ 中的 switch 陳述式：用於多重條件選擇的強大工具

## 概述
在 C++ 中，`switch` 陳述式是一種控制結構，用於根據變數的值選擇執行的程式碼區塊。這種結構特別適用於需要基於整數或字元類型的多重選擇情況，能夠提高程式碼的可讀性與維護性。

## 文檔
### 目的
`switch` 陳述式的主要目的是提供一種簡單易讀的方式來處理多重選擇。它提供了比一系列 `if-else` 陳述式更清晰的語法結構。

### 用法
`switch` 的基本語法如下：

```cpp
switch (expression) {
    case constant1:
        // 執行語句
        break;
    case constant2:
        // 執行語句
        break;
    default:
        // 執行語句
}
```

- **expression**：一個整數或字元類型的表達式，該表達式的值將與 `case` 標籤進行比較。
- **case constant**：每個 `case` 標籤後面跟著一個常數，如果 `expression` 的值等於這個常數，則執行對應的語句。
- **break**：用於終止 `switch` 陳述式，防止執行後續的 `case`。
- **default**：可選的，當沒有任何 `case` 匹配時執行的語句。

### 詳細說明
- `switch` 陳述式只能基於整數、字元或枚舉類型的表達式進行判斷。
- 每個 `case` 標籤必須是唯一的，並且必須是常量表達式。
- 忘記 `break` 陳述式會導致陷入“fall-through”情況，即會繼續執行後面的 `case` 陳述式，這可能是預期的行為或不預期的錯誤。

## 示例
### 基本用法
以下是一個簡單的 `switch` 使用範例：

```cpp
#include <iostream>
using namespace std;

int main() {
    int day = 3;
    
    switch (day) {
        case 1:
            cout << "今天是星期一" << endl;
            break;
        case 2:
            cout << "今天是星期二" << endl;
            break;
        case 3:
            cout << "今天是星期三" << endl;
            break;
        default:
            cout << "無效的日期" << endl;
    }
    
    return 0;
}
```

### 多重選擇範例
以下是一個包含多個 `case` 的範例：

```cpp
#include <iostream>
using namespace std;

int main() {
    char grade = 'B';
    
    switch (grade) {
        case 'A':
            cout << "優秀！" << endl;
            break;
        case 'B':
        case 'C':
            cout << "良好！" << endl;
            break;
        case 'D':
            cout << "及格！" << endl;
            break;
        default:
            cout << "不及格！" << endl;
    }
    
    return 0;
}
```

## 解釋
在使用 `switch` 陳述式時，有一些常見的陷阱和注意事項：
- **缺失的 `break` 陳述式**：這會導致不必要的程式碼執行，注意在每個 `case` 的結尾加上 `break`。
- **多個 `case` 標籤**：可以將多個標籤放在同一個 `case` 中，以簡化程式碼。
- **非整數或字元類型**：`switch` 陳述式不支援浮點數或字串類型的表達式。

## 一句總結
`switch` 陳述式在 C++ 中提供了一種有效的方式來處理多重條件選擇，提升程式碼的可讀性與效率。