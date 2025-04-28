<!--
Meta Description: # C++ 中的無符號整數 (unsigned) ## 摘要 在 C++ 中，`unsigned` 是一種修飾符，用於定義無符號整數類型，這意味著它們只能表示非負整數。這可擴展整數的正數範圍，並且在某些情況下可以提高程序的效率。 ## 文檔 ### 目的 `unsigned` 修飾符可用於整數類型（...
Meta Keywords: unsigned, int, sum, std, negativetest
-->

# C++ 中的無符號整數 (unsigned) 

## 摘要
在 C++ 中，`unsigned` 是一種修飾符，用於定義無符號整數類型，這意味著它們只能表示非負整數。這可擴展整數的正數範圍，並且在某些情況下可以提高程序的效率。

## 文檔
### 目的
`unsigned` 修飾符可用於整數類型（如 `int`、`short`、`long` 和 `char`），使其僅能表示非負值。這對於需要處理大量非負數值的情況特別有用，例如計數或存儲位元組數據。

### 用法
在宣告變數時，可以將 `unsigned` 用於整數類型。例如：
```cpp
unsigned int count;
```
這樣宣告的 `count` 變數將只能存儲非負整數，最大值取決於整數類型的大小。

### 詳細說明
- **範圍**：不同的 `unsigned` 整數類型的範圍如下：
  - `unsigned char`：0 到 255
  - `unsigned short`：0 到 65,535
  - `unsigned int`：0 到 4,294,967,295（在大多數系統上）
  - `unsigned long`：0 到 4,294,967,295（在 32 位系統上，64 位系統上可以更大）

- **運算**：`unsigned` 整數進行運算時不會出現負數情況，這樣可以避免負數溢位的錯誤。

- **類型轉換**：在進行不同類型之間的運算時，`unsigned` 整數會優先於有符號整數進行類型提升，可能導致意想不到的結果。

## 示例
以下是 `unsigned` 的基本用法示例：

```cpp
#include <iostream>

int main() {
    unsigned int a = 10;
    unsigned int b = 20;
    
    unsigned int sum = a + b;  // 正確，sum 為 30
    std::cout << "Sum: " << sum << std::endl;

    unsigned int negativeTest = -1;  // 會導致隱式轉換，negativeTest = UINT_MAX
    std::cout << "Negative Test: " << negativeTest << std::endl;

    return 0;
}
```

## 解釋
- **常見陷阱**：使用 `unsigned` 時，當從負數轉換到無符號整數時，會導致意想不到的結果。例如，`-1` 轉換為 `unsigned int` 時，結果會是 `UINT_MAX`，這可能在邏輯上引起錯誤。

- **比較問題**：在與有符號整數比較時，應小心。因為 `unsigned` 整數的最大值比大多數有符號整數大，這可能導致錯誤的比較結果。

- **使用建議**：當您確定變數只會存儲非負值時，使用 `unsigned` 可以提高代碼的清晰度和安全性。

## 總結
`unsigned` 是 C++ 中一種重要的整數修飾符，允許定義只存儲非負數的整數類型，從而擴展整數的範圍並提高程序效率。