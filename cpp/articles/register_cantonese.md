<!--
Meta Description: # C++ 中的 register 關鍵字：用途與範例 ## 簡介 在 C++ 中，`register` 是一個儲存類型的修飾符，用於提示編譯器將變數儲存在 CPU 的寄存器中，以提高存取速度。 ## 文檔 `register` 修飾符的主要目的是提高變數的存取效率。當你將變數聲明為 `regist...
Meta Keywords: register, sum, int, 關鍵字, cpu
-->

# C++ 中的 register 關鍵字：用途與範例

## 簡介
在 C++ 中，`register` 是一個儲存類型的修飾符，用於提示編譯器將變數儲存在 CPU 的寄存器中，以提高存取速度。

## 文檔
`register` 修飾符的主要目的是提高變數的存取效率。當你將變數聲明為 `register` 時，編譯器會優先考慮將該變數儲存在 CPU 的寄存器中，而不是主記憶體。這通常用於頻繁訪問的變數。

### 用法
要使用 `register`，只需在變數聲明前加上 `register` 關鍵字，例如：

```cpp
register int count;
```

此聲明告訴編譯器，`count` 變數應儲存在寄存器中。如果寄存器不足，則可能無法將該變數儲存在寄存器中，這取決於具體的編譯器和硬體架構。

### 詳細說明
- **限制**：`register` 變數不能取地址，因為寄存器不具備記憶體地址。
- **編譯器優化**：即使使用 `register`，編譯器仍然有權決定如何儲存變數，這意味著在某些情況下，可能不會將變數儲存在寄存器中。
- **建議使用場景**：適合在迴圈中或計算密集型的函式中使用，因為這些情況下，變數的存取頻率較高。

## 範例
以下是使用 `register` 的基本範例：

```cpp
#include <iostream>
using namespace std;

int main() {
    register int sum = 0;

    for (register int i = 1; i <= 100; ++i) {
        sum += i;
    }

    cout << "Sum of 1 to 100 is: " << sum << endl;
    return 0;
}
```

在這個範例中，`sum` 和 `i` 都是被宣告為 `register`，這樣編譯器可能會在寄存器中儲存它們，以提高迴圈的執行效率。

## 解釋
### 常見問題
1. **不能取地址**：如果你嘗試對 `register` 變數使用取地址運算子（`&`），將會導致編譯錯誤。
2. **編譯器行為**：使用 `register` 並不保證變數一定會被儲存在寄存器中，這取決於編譯器的決策。
3. **對現代編譯器的影響**：在許多情況下，現代編譯器會自動進行優化，可能會忽略 `register` 的提示，因此其實際效果可能有限。

## 一行總結
在 C++ 中，`register` 關鍵字用於提示編譯器將變數儲存在寄存器中，以提高存取效率，但其使用效果取決於編譯器的決策。