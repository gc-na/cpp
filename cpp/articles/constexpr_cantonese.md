<!--
Meta Description: # C++ 中的 constexpr：提升性能的常量表達式 ## 概要 `constexpr` 是 C++11 引入的一種關鍵字，用於定義常量表達式，允許在編譯時進行計算，以提高性能和效率。 ## 文檔 `constexpr` 的主要目的在於允許開發者創建可在編譯時求值的常數。這意味著當你使用 `c...
Meta Keywords: constexpr, int, factorial, square, return
-->

# C++ 中的 constexpr：提升性能的常量表達式

## 概要
`constexpr` 是 C++11 引入的一種關鍵字，用於定義常量表達式，允許在編譯時進行計算，以提高性能和效率。

## 文檔
`constexpr` 的主要目的在於允許開發者創建可在編譯時求值的常數。這意味著當你使用 `constexpr` 修飾的變量或函數時，編譯器可以在編譯階段就計算出它們的值，從而減少運行時的計算負擔。

### 用法
- **變量**：使用 `constexpr` 修飾的變量必須被初始化為常量表達式。
- **函數**：使用 `constexpr` 定義的函數也必須在編譯時能夠求值。這意味著函數內部只能使用有限的語法結構，如基本數據類型、算術運算等。

### 詳細說明
1. **編譯時求值**: `constexpr` 使得變量和函數的計算可以在編譯時完成，從而提高程式的執行效率。
2. **範圍**: `constexpr` 不僅可以用於全局變量，也可以用於類的成員變量和方法。
3. **C++11 及以後的版本**: 隨著 C++14 和 C++17 的發展，`constexpr` 的功能得到增強，允許更複雜的計算和使用。

## 示例
以下是一些基本的 `constexpr` 使用示例：

```cpp
#include <iostream>

// constexpr 變量
constexpr int square(int x) {
    return x * x;
}

int main() {
    constexpr int s = square(5); // 編譯時求值
    std::cout << "Square of 5 is: " << s << std::endl; // 輸出: Square of 5 is: 25
    return 0;
}
```

```cpp
#include <iostream>

constexpr int factorial(int n) {
    return n <= 1 ? 1 : n * factorial(n - 1);
}

int main() {
    constexpr int fact5 = factorial(5); // 編譯時求值
    std::cout << "Factorial of 5 is: " << fact5 << std::endl; // 輸出: Factorial of 5 is: 120
    return 0;
}
```

## 解釋
- **常見陷阱**: 在使用 `constexpr` 時，確保函數內部的所有運算都是在編譯時可求值的。如果包含了運行時才知道的內容，將會導致編譯錯誤。
- **類型限制**: `constexpr` 函數只能返回基本數據類型、指針或其他 `constexpr` 類型的值，使用不當可能會引起錯誤。
- **性能優勢**: 充分利用 `constexpr` 可以顯著提升程式性能，特別是在需要大量計算的情況下。

## 一句話總結
`constexpr` 是 C++ 中一個強大的工具，用於在編譯時計算常量，以提升程式性能。