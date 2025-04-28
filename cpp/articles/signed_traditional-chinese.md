<!--
Meta Description: # C++中的「signed」：數據類型的符號修飾 ## 摘要 在C++中，「signed」是用於定義整數數據類型的符號性質的關鍵字。它允許變數儲存負數和正數，並且通常是整數類型的預設屬性。 ## 文檔 ### 目的 「signed」關鍵字用於告訴編譯器，該整數變數可以儲存負值。它主要用於整數類型，...
Meta Keywords: signed, int, short, long, unsigned
-->

# C++中的「signed」：數據類型的符號修飾

## 摘要
在C++中，「signed」是用於定義整數數據類型的符號性質的關鍵字。它允許變數儲存負數和正數，並且通常是整數類型的預設屬性。

## 文檔
### 目的
「signed」關鍵字用於告訴編譯器，該整數變數可以儲存負值。它主要用於整數類型，例如`int`、`short`和`long`，以指明這些類型的符號性。

### 使用方式
在C++中，數據類型的默認屬性取決於其類型：
- `int`、`short`和`long`默認為`signed`。
- `unsigned`用於定義只能儲存非負整數的變數。

使用「signed」的語法如下：
```cpp
signed int a;       // 可以儲存負數和正數
signed short b;     // 可以儲存負數和正數
signed long c;      // 可以儲存負數和正數
```

### 詳細信息
- **預設行為**：在C++中，整數類型（如`int`）預設為`signed`，因此可以直接使用而無需明確聲明。
- **明確聲明**：雖然可以不使用`signed`關鍵字，但明確聲明可以增強程式碼的可讀性。
- **範圍**：`signed int`的範圍通常是-2,147,483,648到2,147,483,647，具體範圍依賴於平台。

## 示例
以下是幾個簡單的範例來演示「signed」的使用：

```cpp
#include <iostream>

int main() {
    signed int a = -10; // 使用signed int
    signed short b = 20; // 使用signed short
    signed long c = -30000; // 使用signed long

    std::cout << "a: " << a << ", b: " << b << ", c: " << c << std::endl;
    return 0;
}
```

輸出：
```
a: -10, b: 20, c: -30000
```

## 解釋
### 常見誤區
- **不必要的聲明**：由於整數類型默認為`signed`，開發者在定義整數時不必每次都使用`signed`，但在某些情況下，為了強調變數的性質，明確聲明是有用的。
- **混淆不同類型**：開發者應注意在使用`signed`和`unsigned`時，兩者之間的區別，因為將`signed`與`unsigned`變數進行運算可能會引發錯誤或未定義行為。

## 單行摘要
在C++中，「signed」關鍵字用於定義可儲存負數和正數的整數數據類型。