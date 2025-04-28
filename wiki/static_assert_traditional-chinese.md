<!--
Meta Description: # C++ 的 static_assert：靜態斷言的使用與最佳實踐 ## 摘要 `static_assert` 是 C++11 引入的一個編譯時斷言工具，允許開發者在編譯階段檢查條件，這有助於捕捉錯誤並提高程式碼的安全性和可讀性。 ## 文檔 ### 目的 `static_assert` 主要用於...
Meta Keywords: static_assert, int, value, cpp, std
-->

# C++ 的 static_assert：靜態斷言的使用與最佳實踐

## 摘要
`static_assert` 是 C++11 引入的一個編譯時斷言工具，允許開發者在編譯階段檢查條件，這有助於捕捉錯誤並提高程式碼的安全性和可讀性。

## 文檔
### 目的
`static_assert` 主要用於在編譯期間檢查某些條件是否成立。若條件不成立，編譯器將生成錯誤訊息，這樣開發者可以及早發現問題，而不是在程式執行時才發現。

### 用法
`static_assert` 的語法如下：

```cpp
static_assert(condition, "error message");
```

- **condition**：一個編譯時期的布林表達式，若為假，則編譯失敗。
- **error message**：當斷言失敗時顯示的錯誤訊息。

### 詳細說明
- `static_assert` 可以用於各種情境，例如檢查類型的大小、確保模板參數滿足某些條件等。
- 其斷言條件必須是編譯時期已知的，這意味著不能使用運行時變量。
- 編譯器在遇到 `static_assert` 時，會立即評估條件並生成錯誤，如果條件為假，則停止編譯，並顯示提供的錯誤訊息。

## 範例
以下是幾個 `static_assert` 的基本用法範例：

### 範例 1：檢查類型大小
```cpp
#include <iostream>
static_assert(sizeof(int) == 4, "int size is not 4 bytes");

int main() {
    std::cout << "Size of int is 4 bytes." << std::endl;
    return 0;
}
```

### 範例 2：模板參數檢查
```cpp
template <typename T>
void process(T value) {
    static_assert(std::is_integral<T>::value, "T must be an integral type");
    // 進行處理
}
```

### 範例 3：檢查常量
```cpp
constexpr int value = 10;
static_assert(value > 5, "Value must be greater than 5");
```

## 解釋
- **常見陷阱**：`static_assert` 只能在模板參數或全域範圍內使用，不能放在函數內部。此外，檢查的條件必須是編譯時已知的。

- **錯誤訊息**：提供明確的錯誤訊息可以幫助開發者更快地定位問題，建議使用描述性強的訊息。

- **多次使用**：在同一個文件或類中可以多次使用 `static_assert`，不過要注意避免重複的條件檢查。

## 一句總結
`static_assert` 是一個強大的編譯時檢查工具，能夠提高 C++ 程式的安全性和可維護性。