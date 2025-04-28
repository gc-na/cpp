<!--
Meta Description: # C++ 中的「if」語句：條件判斷的基石 ## 概述 「if」語句是 C++ 中最基本的控制結構之一，用於基於某個條件的真假來決定程式的執行路徑。 ## 文檔 ### 目的 「if」語句的主要目的是根據布林條件的結果執行不同的程式碼塊。這使得程式能夠根據用戶輸入或其他情況的變化做出反應。 ###...
Meta Keywords: else, number, cpp, int, cout
-->

# C++ 中的「if」語句：條件判斷的基石

## 概述
「if」語句是 C++ 中最基本的控制結構之一，用於基於某個條件的真假來決定程式的執行路徑。

## 文檔
### 目的
「if」語句的主要目的是根據布林條件的結果執行不同的程式碼塊。這使得程式能夠根據用戶輸入或其他情況的變化做出反應。

### 使用方法
基本語法如下：
```cpp
if (條件) {
    // 當條件為真時執行的語句
}
```
如果需要在條件不成立時執行其他操作，可以使用「else」語句：
```cpp
if (條件) {
    // 當條件為真時執行的語句
} else {
    // 當條件為假時執行的語句
}
```
還可以使用「else if」來處理多個條件：
```cpp
if (條件1) {
    // 當條件1為真時執行的語句
} else if (條件2) {
    // 當條件2為真時執行的語句
} else {
    // 當所有條件都不成立時執行的語句
}
```

## 範例
以下是一些基本的「if」語句示例：

### 範例 1：簡單的條件判斷
```cpp
#include <iostream>
using namespace std;

int main() {
    int number = 10;

    if (number > 5) {
        cout << "數字大於5" << endl;
    }

    return 0;
}
```

### 範例 2：使用「else」語句
```cpp
#include <iostream>
using namespace std;

int main() {
    int number = 3;

    if (number > 5) {
        cout << "數字大於5" << endl;
    } else {
        cout << "數字不大於5" << endl;
    }

    return 0;
}
```

### 範例 3：使用「else if」
```cpp
#include <iostream>
using namespace std;

int main() {
    int number = 5;

    if (number > 5) {
        cout << "數字大於5" << endl;
    } else if (number == 5) {
        cout << "數字等於5" << endl;
    } else {
        cout << "數字小於5" << endl;
    }

    return 0;
}
```

## 解釋
使用「if」語句時，有幾個常見的陷阱需要注意：
1. **條件表達式**：確保條件表達式正確，常見的錯誤是使用賦值運算符（=）而非比較運算符（==）。
2. **多重條件**：在使用「else if」時，確保條件的邏輯正確，否則可能會導致錯誤的執行路徑。
3. **大括號的使用**：即使只需要執行一個語句，也建議使用大括號來明確界定執行區塊，這樣可以避免未來的維護問題。

## 一句總結
C++ 中的「if」語句是用於根據條件執行不同程式碼的基本工具。