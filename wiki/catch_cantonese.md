<!--
Meta Description: # C++ 中的 "catch" 關鍵字：異常處理的基石 ## 摘要 在 C++ 中，`catch` 關鍵字是異常處理機制的一部分，與 `try` 和 `throw` 一起使用，用來捕獲和處理執行期間發生的異常。 ## 文件說明 `catch` 是 C++ 的一個關鍵字，主要用於捕獲由 `throw...
Meta Keywords: catch, try, std, throw, maygowrong
-->

# C++ 中的 "catch" 關鍵字：異常處理的基石

## 摘要
在 C++ 中，`catch` 關鍵字是異常處理機制的一部分，與 `try` 和 `throw` 一起使用，用來捕獲和處理執行期間發生的異常。

## 文件說明
`catch` 是 C++ 的一個關鍵字，主要用於捕獲由 `throw` 表達式拋出的異常。異常處理使得程序能夠在遇到錯誤時，優雅地處理問題，而不至於造成程序崩潰。使用 `try` 來包裝可能會產生異常的代碼，然後使用 `catch` 來捕獲這些異常並執行相應的錯誤處理邏輯。

### 用法
基本語法如下：
```cpp
try {
    // 可能拋出異常的代碼
} catch (const ExceptionType &e) {
    // 處理異常的代碼
}
```
在 `try` 區塊內的代碼如果拋出異常，程序將跳轉到相應的 `catch` 區塊，並執行其中的代碼。

## 例子
以下是一個簡單的例子，展示如何使用 `catch` 來捕獲和處理異常：
```cpp
#include <iostream>
#include <stdexcept>

void mayGoWrong() {
    bool errorOccurred = true; // 假設發生錯誤
    if (errorOccurred) {
        throw std::runtime_error("出現了錯誤！");
    }
}

int main() {
    try {
        mayGoWrong();
    } catch (const std::runtime_error &e) {
        std::cout << "捕獲異常: " << e.what() << std::endl;
    }
    return 0;
}
```
在這個例子中，`mayGoWrong` 函數可能會拋出 `std::runtime_error` 異常，而在 `main` 函數中，我們捕獲它並輸出錯誤信息。

## 解釋
使用 `catch` 時需要注意以下幾點：
1. **異常類型**：`catch` 語句必須與 `throw` 語句拋出的異常類型相匹配，否則將不會捕獲該異常。
2. **多個 `catch` 區塊**：可以為同一個 `try` 區塊設置多個 `catch` 區塊，處理不同類型的異常。
3. **不捕獲所有異常**：如果未能捕獲異常，程序將會終止並打印堆棧跟蹤信息。

## 總結一句話
`catch` 是 C++ 中用於捕獲和處理異常的關鍵字，是異常處理機制的重要組成部分。