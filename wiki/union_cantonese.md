<!--
Meta Description: # C++ 的 Union：靈活的資料結構 ## 概述 在 C++ 中，`union` 是一種資料結構，它允許在相同的記憶體位置存儲不同類型的資料。這種特性使得 `union` 在需要節省記憶體時特別有用。 ## 文件說明 `union` 的主要目的是允許一個變數在不同時間儲存不同的類型。與結構 (...
Meta Keywords: union, data, intvalue, floatvalue, charvalue
-->

# C++ 的 Union：靈活的資料結構

## 概述
在 C++ 中，`union` 是一種資料結構，它允許在相同的記憶體位置存儲不同類型的資料。這種特性使得 `union` 在需要節省記憶體時特別有用。

## 文件說明
`union` 的主要目的是允許一個變數在不同時間儲存不同的類型。與結構 (`struct`) 不同，`union` 的所有成員共用相同的記憶體空間，這意味著只能在某一時間存取其中一個成員。

### 使用方式
定義 `union` 時，使用關鍵字 `union`，後面跟上名稱和成員變數。以下是 `union` 的基本語法：

```cpp
union UnionName {
    type1 member1;
    type2 member2;
    // 其他成員...
};
```

### 詳細說明
- **記憶體使用**：`union` 的大小是其最大成員大小的大小，這使得它比 `struct` 更加節省記憶體。
- **初始化**：`union` 只能初始化一個成員，並且在使用之前確保正確的成員被選擇。
- **訪問成員**：使用點運算符來訪問 `union` 成員，但要注意，訪問未初始化的成員會導致未定義行為。

## 示例
以下是 `union` 的基本示例：

```cpp
#include <iostream>
using namespace std;

// 定義 union
union Data {
    int intValue;
    float floatValue;
    char charValue;
};

int main() {
    Data data;

    // 儲存整數
    data.intValue = 10;
    cout << "整數值: " << data.intValue << endl;

    // 儲存浮點數
    data.floatValue = 220.5;
    cout << "浮點數值: " << data.floatValue << endl;

    // 儲存字符
    data.charValue = 'A';
    cout << "字符值: " << data.charValue << endl;

    return 0;
}
```

在這個例子中，儘管 `data` 可以儲存整數、浮點數和字符，但在任何時候只能安全地使用最後儲存的成員。

## 解釋
使用 `union` 時，以下是一些常見的陷阱與注意事項：
- **未初始化成員**：訪問未初始化的成員會導致未定義行為。
- **記憶體重疊**：因為所有成員共享相同的記憶體空間，最後寫入的成員將會覆蓋先前的成員。
- **建構與解構**：如果使用複雜類型的成員，必須顯式地管理建構和解構函數，以防止資源洩漏。

## 一句總結
`union` 是 C++ 中一種靈活的資料結構，允許在同一記憶體位置存儲不同類型的資料，並在需要時有效地使用記憶體。