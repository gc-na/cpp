<!--
Meta Description: # C++ 中的 unsigned 類型：無符號整數的詳細解析 ## 概述 在 C++ 編程中，`unsigned` 代表無符號整數類型，它可以存儲非負整數。這個特性使得 `unsigned` 在處理需要正整數的計算時十分有用。 ## 文檔 `unsigned` 是 C++ 中一個基本數據類型的修飾...
Meta Keywords: unsigned, int, sum, std, letter
-->

# C++ 中的 unsigned 類型：無符號整數的詳細解析

## 概述
在 C++ 編程中，`unsigned` 代表無符號整數類型，它可以存儲非負整數。這個特性使得 `unsigned` 在處理需要正整數的計算時十分有用。

## 文檔
`unsigned` 是 C++ 中一個基本數據類型的修飾符，通常用於整數類型（如 `int`、`short`、`long` 和 `char`）。使用 `unsigned` 修飾符的變量只能存儲 0 或正整數，這使得它能夠擴展數值範圍。例如，`unsigned int` 的取值範圍是從 0 到 4,294,967,295，而 `int` 的範圍是 -2,147,483,648 到 2,147,483,647。

### 目的
使用 `unsigned` 的主要目的是提高整數的最大值，因為它不需要保存負數的位元。這在某些情況下（例如計算數量、索引或其他需要非負值的場景）是非常有用的。

### 使用方式
在 C++ 中，您可以通過在基本整數類型前添加 `unsigned` 來聲明無符號整數。示例如下：

```cpp
unsigned int a = 10;
unsigned short b = 20;
unsigned long c = 300000;
```

## 示例
以下是使用 `unsigned` 的一些基本範例：

```cpp
#include <iostream>

int main() {
    unsigned int num1 = 5;
    unsigned int num2 = 10;
    unsigned int sum = num1 + num2;

    std::cout << "Sum: " << sum << std::endl; // 輸出：Sum: 15

    unsigned char letter = 'A';
    std::cout << "Letter: " << letter << std::endl; // 輸出：Letter: A

    return 0;
}
```

## 解釋
使用 `unsigned` 類型時，有幾個常見的陷阱和注意事項：

1. **負數賦值**：將負數賦值給 `unsigned` 變量會導致未定義行為，通常會出現意外的結果。例如，`unsigned int x = -1;` 會導致 `x` 存儲一個非常大的正數。

2. **溢出運算**：當進行運算時，如果結果超過 `unsigned` 類型的最大值，則會回繞至 0，這可能會導致邏輯錯誤。

3. **比較行為**：在進行比較時，`unsigned` 和 `signed` 整數類型的變量可能會導致意外的行為，因為 C++ 會自動進行類型提升。

4. **類型轉換**：在進行數學運算時，`unsigned` 類型可能需要特別小心，因為與其他類型的轉換可能會改變結果。

## 總結
`unsigned` 是 C++ 中一種用於表示非負整數的數據類型，能夠有效擴展整數的範圍，特別適合用於需要正整數的場合。