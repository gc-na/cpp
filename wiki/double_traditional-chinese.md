<!--
Meta Description: # C++ 中的 double 資料類型：詳細介紹與範例 ## 摘要 在 C++ 中，`double` 是一種基本的浮點數資料類型，專門用於表示具有小數部分的數值。其精度高於 `float`，適合需要高精度計算的應用。 ## 文檔 ### 目的 `double` 資料類型在 C++ 中用來表示雙精度...
Meta Keywords: double, std, sum, product, cout
-->

# C++ 中的 double 資料類型：詳細介紹與範例

## 摘要
在 C++ 中，`double` 是一種基本的浮點數資料類型，專門用於表示具有小數部分的數值。其精度高於 `float`，適合需要高精度計算的應用。

## 文檔
### 目的
`double` 資料類型在 C++ 中用來表示雙精度浮點數，通常用於需要更高精度或範圍的數值計算。其標準大小為 8 個位元組（64 位元），可以表示範圍更大的數字以及更為精確的小數。

### 使用方法
在 C++ 中使用 `double` 非常簡單，您可以像使用其他基本資料類型一樣聲明並初始化它。以下是基本的聲明和初始化方式：

```cpp
double myNumber = 3.14159;
```

您也可以進行數學運算、比較，或將其用於函數計算中。

### 詳細資訊
- **範圍與精度**：`double` 提供大約 15 到 17 位的十進制有效數字，範圍從約 1.7E-308 到 1.7E+308。
- **自動轉換**：在數學運算中，如果涉及 `double` 和其他整數類型，C++ 會自動將整數類型轉換為 `double` 以避免精度損失。
- **庫函數**：C++ 標準庫提供了多種數學函數（如 `sin()`, `cos()`, `sqrt()` 等），這些函數接受 `double` 型別參數並返回 `double` 型別結果。

## 範例
### 基本使用
```cpp
#include <iostream>
#include <cmath>

int main() {
    double a = 5.0;
    double b = 2.0;
    double sum = a + b; // 加法
    double product = a * b; // 乘法

    std::cout << "Sum: " << sum << std::endl; // 輸出結果
    std::cout << "Product: " << product << std::endl; // 輸出結果

    // 使用數學函數
    double squareRoot = sqrt(a);
    std::cout << "Square Root of " << a << " is " << squareRoot << std::endl;

    return 0;
}
```

### 輸出結果
```
Sum: 7
Product: 10
Square Root of 5 is 2.23607
```

## 解釋
- **常見陷阱**：使用 `double` 進行比較時需謹慎，因為浮點數的精度問題可能導致預期外的結果。建議使用一個小的容忍度來比較 `double` 值。
- **初始化**：在未初始化之前使用 `double` 變數，會導致未定義行為。務必在使用前將其初始化。
- **性能考量**：在某些性能敏感的應用中，使用 `float` 可能會更高效，因為它的大小較小，但這需要根據具體需求來考量。

## 一句總結
`double` 是 C++ 中用於表示高精度浮點數的基本資料類型，適合進行涉及小數的計算。