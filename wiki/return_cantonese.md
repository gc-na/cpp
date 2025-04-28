<!--
Meta Description: # C++ 中的 "return" 關鍵字 ## 摘要 在 C++ 中，`return` 關鍵字用於從函數返回值，並結束該函數的執行。 ## 文檔 `return` 是 C++ 中的保留關鍵字，主要用於函數的返回操作。當函數執行到 `return` 語句時，該函數的執行會立即中斷，並將指定的值返回給...
Meta Keywords: return, void, int, 返回類型的函數, 的函數
-->

# C++ 中的 "return" 關鍵字

## 摘要
在 C++ 中，`return` 關鍵字用於從函數返回值，並結束該函數的執行。

## 文檔
`return` 是 C++ 中的保留關鍵字，主要用於函數的返回操作。當函數執行到 `return` 語句時，該函數的執行會立即中斷，並將指定的值返回給函數的調用者。`return` 語句可以不帶值（適用於返回類型為 `void` 的函數），也可以帶有一個值（適用於非 `void` 返回類型的函數）。

### 用法
- 在函數內部使用 `return` 語句返回結果。
- 對於非 `void` 返回類型的函數，必須指定一個與返回類型相符的值。
- 對於 `void` 返回類型的函數，可以使用 `return;` 來提前結束函數執行。

### 詳細說明
- 對於函數，`return` 語句不僅返回值，還會影響函數的控制流。
- 使用 `return` 返回的值會被用來替換函數調用的位置。

## 示例
### 基本範例
```cpp
#include <iostream>
using namespace std;

// 返回整數的函數
int add(int a, int b) {
    return a + b; // 返回 a 和 b 的和
}

int main() {
    int result = add(5, 3); // 調用函數
    cout << "結果是: " << result << endl; // 輸出結果
    return 0; // 主函數返回 0
}
```

### 返回空值的範例
```cpp
#include <iostream>
using namespace std;

// 返回 void 的函數
void printMessage() {
    cout << "Hello, World!" << endl;
    return; // 可選的 return；結束函數
}

int main() {
    printMessage(); // 調用函數
    return 0; // 主函數返回 0
}
```

## 解釋
- **常見陷阱**：在非 `void` 函數中忘記使用 `return` 來返回值，將導致未定義行為。
- **類型不匹配**：返回的值必須與函數聲明的返回類型一致，否則編譯器會報錯。
- **多重返回**：函數中可以有多個 `return` 語句，但一旦執行某個 `return`，後面的 `return` 將不會被執行。

## 一句總結
`return` 關鍵字在 C++ 中用於結束函數執行並返回指定的值或不返回值。