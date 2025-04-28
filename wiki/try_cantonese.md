<!--
Meta Description: # C++ 中的 try 關鍵字：異常處理的基石 ## 概述 在 C++ 中，`try` 是一個關鍵字，用於異常處理的機制中，主要用來捕獲和處理可能發生的錯誤，確保程式的穩定性和可靠性。 ## 文檔 ### 目的 `try` 關鍵字的主要目的是包裹可能引發異常的代碼，並與 `catch` 區塊結合使...
Meta Keywords: try, catch, std, cpp, const
-->

# C++ 中的 try 關鍵字：異常處理的基石

## 概述
在 C++ 中，`try` 是一個關鍵字，用於異常處理的機制中，主要用來捕獲和處理可能發生的錯誤，確保程式的穩定性和可靠性。

## 文檔
### 目的
`try` 關鍵字的主要目的是包裹可能引發異常的代碼，並與 `catch` 區塊結合使用，允許開發者對異常進行捕獲和處理，從而防止程式崩潰。

### 使用方法
在 C++ 中，`try` 區塊用於標記一段代碼，該代碼可能會拋出異常。當異常發生時，控制權會被轉移到與 `try` 區塊相對應的 `catch` 區塊，以執行相應的錯誤處理邏輯。

#### 語法
```cpp
try {
    // 可能會拋出異常的代碼
} catch (const ExceptionType& e) {
    // 處理異常的代碼
}
```

### 詳細說明
使用 `try` 和 `catch` 的結構使得 C++ 支持異常處理的機制。關鍵點包括：
- `try` 區塊可以包含任何可能引發異常的代碼。
- 當異常被拋出時，程序的控制流會直接跳轉到與之匹配的 `catch` 區塊。
- 一個 `try` 區塊可以有多個 `catch` 區塊，以處理不同類型的異常。

## 示例
以下是使用 `try` 和 `catch` 的簡單示例：

```cpp
#include <iostream>
#include <stdexcept>

void mightGoWrong() {
    bool errorOccurred = true; // 模擬錯誤
    if (errorOccurred) {
        throw std::runtime_error("發生錯誤！");
    }
}

int main() {
    try {
        mightGoWrong();
    } catch (const std::runtime_error& e) {
        std::cout << "捕獲到異常: " << e.what() << std::endl;
    }
    return 0;
}
```

## 解釋
### 常見陷阱
- **未捕獲的異常**：如果 `try` 區塊中的異常未被任何 `catch` 區塊捕獲，程式將終止執行。
- **異常類型不匹配**：`catch` 區塊必須與拋出的異常類型匹配，否則將跳過該 `catch` 區塊。
- **多重異常**：在多個 `catch` 區塊中，應該將最具體的異常類型置於前面，因為 C++ 會按照從上到下的順序進行匹配。

## 一句總結
`try` 關鍵字在 C++ 中用於異常處理，幫助開發者捕獲和處理潛在的錯誤，提升程式的穩定性。