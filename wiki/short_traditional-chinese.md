<!--
Meta Description: # C++ 的 short 數據類型：基礎與應用 ## 簡介 在 C++ 中，`short` 是一種整數數據類型，通常用於需要節省內存空間的情況。這個數據類型的大小通常為 16 位，能夠儲存的整數範圍通常是 -32,768 到 32,767。 ## 文檔 ### 目的 `short` 數據類型主要用...
Meta Keywords: short, cpp, unsigned, int, variablename
-->

# C++ 的 short 數據類型：基礎與應用

## 簡介
在 C++ 中，`short` 是一種整數數據類型，通常用於需要節省內存空間的情況。這個數據類型的大小通常為 16 位，能夠儲存的整數範圍通常是 -32,768 到 32,767。

## 文檔
### 目的
`short` 數據類型主要用於儲存小範圍的整數值，以減少內存消耗。這在處理大量數據時特別有用。

### 使用方式
在 C++ 中，`short` 數據類型可以這樣宣告：
```cpp
short variableName;
```
也可以直接在宣告時初始化：
```cpp
short variableName = 100;
```

此外，C++ 提供了無符號的 `unsigned short`，它可以儲存 0 到 65,535 之間的整數值：
```cpp
unsigned short variableName = 50000;
```

### 詳細信息
- **大小**：`short` 類型的大小通常為 2 字節（16 位），具體大小可能因編譯器和平台而異。
- **範圍**：
  - 有符號 `short` 的範圍：-32,768 到 32,767。
  - 無符號 `unsigned short` 的範圍：0 到 65,535。
- **使用場合**：適合於不需要使用大型整數的情況，例如計數器或小範圍的狀態變量。

## 範例
以下是使用 `short` 的一些基本範例：

### 宣告與初始化
```cpp
#include <iostream>
using namespace std;

int main() {
    short num = 150;
    cout << "數字是: " << num << endl;
    return 0;
}
```

### 使用 unsigned short
```cpp
#include <iostream>
using namespace std;

int main() {
    unsigned short unum = 60000;
    cout << "無符號數字是: " << unum << endl;
    return 0;
}
```

### 數學運算
```cpp
#include <iostream>
using namespace std;

int main() {
    short a = 10;
    short b = 20;
    short sum = a + b;
    cout << "總和是: " << sum << endl;
    return 0;
}
```

## 解釋
在使用 `short` 時，有一些常見的陷阱和注意事項：
- **溢出**：如果你嘗試儲存超出 `short` 範圍的數值，將會導致溢出，這可能會引發未定義行為。
- **類型轉換**：在進行數學運算時，`short` 可能會自動轉換為 `int`，這可能會影響性能和存儲。
- **平台依賴性**：雖然 `short` 的大小在大多數平台上為 2 字節，但仍然有可能因編譯器或平台而異，開發者應該小心確認。

## 總結
`short` 數據類型在 C++ 中是一個有效的工具，用於儲存小範圍整數以節省內存空間。