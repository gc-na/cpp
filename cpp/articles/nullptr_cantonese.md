<!--
Meta Description: # C++ 中的 nullptr：現代 C++ 的空指針 ## 概述 `nullptr` 是 C++11 引入的一個關鍵字，用於表示空指針。它是一種類型安全的方式來表示指針不指向任何有效的物件，相比於之前的 `NULL`，`nullptr` 提供了更好的類型檢查和可讀性。 ## 文檔 `nullpt...
Meta Keywords: nullptr, std, int, ptr, cpp
-->

# C++ 中的 nullptr：現代 C++ 的空指針

## 概述
`nullptr` 是 C++11 引入的一個關鍵字，用於表示空指針。它是一種類型安全的方式來表示指針不指向任何有效的物件，相比於之前的 `NULL`，`nullptr` 提供了更好的類型檢查和可讀性。

## 文檔
`nullptr` 的主要目的是提供一個明確的表示空指針的方式。在 C++ 中，空指針的使用非常普遍，特別是在指針和動態記憶體管理方面。傳統上，開發者使用 `NULL`，但這會引起類型不明確的問題。`nullptr` 是一個具體的類型，類型為 `std::nullptr_t`，這使得它在函數重載時更具可預測性。

### 使用方式
使用 `nullptr` 非常簡單，只需在需要表示空指針的地方使用 `nullptr` 即可。以下是一些基本使用場景：

- 用於初始化指針：
  ```cpp
  int* ptr = nullptr;
  ```

- 用於函數參數：
  ```cpp
  void foo(int* p) {
      if (p == nullptr) {
          // 處理空指針情況
      }
  }

  foo(nullptr);
  ```

## 示例
以下是 `nullptr` 的一些基本範例：

### 示例 1：初始化指針
```cpp
#include <iostream>

int main() {
    int* ptr = nullptr; // 初始化指針為空
    if (ptr == nullptr) {
        std::cout << "指針是空的" << std::endl;
    }
    return 0;
}
```

### 示例 2：函數重載
```cpp
#include <iostream>

void func(int* ptr) {
    std::cout << "整數指針被調用" << std::endl;
}

void func(char* ptr) {
    std::cout << "字符指針被調用" << std::endl;
}

int main() {
    func(nullptr); // 將調用整數指針版本
    return 0;
}
```

## 解釋
使用 `nullptr` 時需要注意以下幾個常見的坑：
- **類型安全性**：`nullptr` 的類型為 `std::nullptr_t`，與其他整數類型（如 `0` 或 `NULL`）不同，這避免了某些類型不匹配的錯誤。
- **函數重載**：使用 `nullptr` 可以幫助明確知道調用哪個重載函數，這樣可以減少意外行為的發生。

## 總結
`nullptr` 是 C++11 之後的現代 C++ 中，表示空指針的一個安全且明確的方式，有助於提升代碼的可讀性和可維護性。