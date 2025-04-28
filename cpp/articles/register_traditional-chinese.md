<!--
Meta Description: # C++ 中的 register 關鍵字：用於變數存儲的優化 ## 概要 `register` 是 C++ 中的一個存儲類別指示符，用於提示編譯器將變數儲存在 CPU 的暫存器中，以期提高變數的存取速度。 ## 文件說明 在 C++ 中，`register` 關鍵字主要用於優化變數的存取速度。當編...
Meta Keywords: register, int, sum, cpu, cpp
-->

# C++ 中的 register 關鍵字：用於變數存儲的優化

## 概要
`register` 是 C++ 中的一個存儲類別指示符，用於提示編譯器將變數儲存在 CPU 的暫存器中，以期提高變數的存取速度。

## 文件說明
在 C++ 中，`register` 關鍵字主要用於優化變數的存取速度。當編譯器遇到 `register` 關鍵字時，它會優先使用 CPU 的暫存器來存儲該變數。如果變數的存取頻率很高，這樣的做法可以顯著提高程式的執行效率。

### 用法
- `register` 關鍵字只能用於局部變數。
- 使用範例如下：

```cpp
void exampleFunction() {
    register int count = 0;
    for (register int i = 0; i < 100; ++i) {
        count += i;
    }
}
```

### 細節
- `register` 不保證變數一定會存儲在暫存器中，這只是對編譯器的一種建議。
- 由於暫存器空間有限，編譯器可能會忽略此建議。
- 使用 `register` 變數無法取得其地址，因為暫存器變數可能不在記憶體中。

## 範例
以下是使用 `register` 的簡單範例：

```cpp
#include <iostream>

int main() {
    register int sum = 0;
    for (register int i = 1; i <= 10; ++i) {
        sum += i;
    }
    std::cout << "Sum is: " << sum << std::endl;
    return 0;
}
```

在這個範例中，`sum` 和 `i` 都被標記為 `register`，旨在提高存取速度。

## 解釋
- **常見陷阱**：不應過度使用 `register`，因為編譯器通常能夠自行優化變數的存儲。過度使用可能導致編譯器的優化效果減弱。
- **注意事項**：如果變數需要經常被取址，則不應使用 `register`，因為這會導致編譯錯誤。

## 一句話總結
`register` 是 C++ 中的一個關鍵字，用於提示編譯器將高頻存取的局部變數儲存在暫存器中，以提高執行效能。