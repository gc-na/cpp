<!--
Meta Description: # C++ 中的 void：用途與範例 ## 概述 在 C++ 中，`void` 是一種特殊的資料型別，用於表示「無」或「不返回任何值」。它通常用於函數聲明中，指示函數不會返回任何數據。 ## 文件說明 `void` 資料型別的主要用途是在函數的定義或聲明中，表示該函數不會傳回任何值。當你希望創建一...
Meta Keywords: void, int, ptr, cpp, myfunction
-->

# C++ 中的 void：用途與範例

## 概述
在 C++ 中，`void` 是一種特殊的資料型別，用於表示「無」或「不返回任何值」。它通常用於函數聲明中，指示函數不會返回任何數據。

## 文件說明
`void` 資料型別的主要用途是在函數的定義或聲明中，表示該函數不會傳回任何值。當你希望創建一個只執行某些操作而不需要返回結果的函數時，`void` 是最佳選擇。使用 `void` 可以增強程式碼的可讀性，因為它清楚地表明函數的意圖。

### 用法
1. **函數返回類型**：當函數不需要返回值時，使用 `void` 來定義其返回類型。
   ```cpp
   void myFunction() {
       // 做某事
   }
   ```

2. **指針類型**：`void*` 是一種通用指針，可以指向任何類型的數據。這在需要傳遞任意類型資料的情況下非常有用。
   ```cpp
   void* ptr;
   int x = 10;
   ptr = &x;  // void 指針可以指向 int
   ```

## 範例
### 基本用法範例
```cpp
#include <iostream>
using namespace std;

void greet() {
    cout << "Hello, World!" << endl;  // 無返回值的函數
}

int main() {
    greet();  // 呼叫 greet 函數
    return 0;
}
```

### void 指針範例
```cpp
#include <iostream>
using namespace std;

void display(void* ptr, char type) {
    if (type == 'i') {
        cout << "整數: " << *(static_cast<int*>(ptr))) << endl;
    } else if (type == 'f') {
        cout << "浮點數: " << *(static_cast<float*>(ptr))) << endl;
    }
}

int main() {
    int a = 5;
    float b = 3.14;
    display(&a, 'i');  // 傳遞整數
    display(&b, 'f');  // 傳遞浮點數
    return 0;
}
```

## 解釋
- **常見陷阱**：使用 `void` 作為返回類型的函數不能在調用時用於賦值，這樣會導致編譯錯誤。例如，`int x = myFunction();` 是錯誤的，因為 `myFunction` 不返回值。
- **指針使用**：當使用 `void*` 指針時，必須小心類型轉換。未經適當轉換直接使用 `void*` 可能導致未定義行為。

## 一句話總結
`void` 在 C++ 中用來表示不返回值的函數，並可作為通用指針類型使用。