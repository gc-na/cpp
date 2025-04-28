<!--
Meta Description: # C++ 中的 static_assert：靜態斷言詳解 ## 簡介 `static_assert` 是 C++ 中的一個編譯期斷言指令，用於在編譯時期檢查條件是否為真，若為假則會產生編譯錯誤。這有助於捕捉潛在的錯誤，增強代碼的安全性和可維護性。 ## 文檔 `static_assert` 的主要...
Meta Keywords: static_assert, checksize, bytes, int, cpp
-->

# C++ 中的 static_assert：靜態斷言詳解

## 簡介
`static_assert` 是 C++ 中的一個編譯期斷言指令，用於在編譯時期檢查條件是否為真，若為假則會產生編譯錯誤。這有助於捕捉潛在的錯誤，增強代碼的安全性和可維護性。

## 文檔
`static_assert` 的主要目的是讓開發者能夠在編譯階段進行條件檢查。它的語法如下：

```cpp
static_assert(condition, "Error message");
```

- **condition**：一個編譯期可評估的布爾表達式。
- **"Error message"**：當條件不成立時顯示的錯誤訊息。

### 使用場景
- 確保類型的大小符合預期。
- 驗證模板參數的特性。
- 檢查常數表達式的有效性。

### 詳細說明
`static_assert` 主要用於進行靜態檢查，這意味著在編譯期間就能捕捉到錯誤，避免在運行時出現不必要的崩潰或錯誤行為。這在大型專案中尤其重要，因為它能夠減少運行時錯誤的機會。

## 範例
以下是 `static_assert` 的基本用法範例：

```cpp
#include <iostream>

template <typename T>
void checkSize() {
    static_assert(sizeof(T) == 4, "Type T must be 4 bytes");
}

int main() {
    checkSize<int>();    // 正確，因為 int 通常是 4 bytes
    // checkSize<double>(); // 錯誤，因為 double 通常不是 4 bytes
    return 0;
}
```

在這個例子中，如果嘗試檢查一個大小不為4的類型，編譯器將會報錯並顯示指定的錯誤訊息。

## 解釋
- **常見陷阱**：使用 `static_assert` 時，必須確保條件在編譯時期可被評估，否則將會導致編譯錯誤。
- **注意**：`static_assert` 只在 C++11 及之後的版本中可用，舊版本的 C++ 不支持此功能。

## 簡單總結
`static_assert` 是一個強大的編譯期工具，用於確保條件在編譯時成立，以增強代碼的安全性和穩定性。