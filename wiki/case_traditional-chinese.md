<!--
Meta Description: # C++中的case語句：使用與最佳實踐 ## 概述 在C++中，`case`語句是`switch`語句的一部分，用於控制多重選擇結構。它提供了一種簡便的方式來根據變量的值執行不同的代碼塊。 ## 文檔 ### 目的 `case`語句的主要目的是為了簡化基於整數或字符變量的多重條件判斷，使代碼更為...
Meta Keywords: case, break, switch, cout, endl
-->

# C++中的case語句：使用與最佳實踐

## 概述
在C++中，`case`語句是`switch`語句的一部分，用於控制多重選擇結構。它提供了一種簡便的方式來根據變量的值執行不同的代碼塊。

## 文檔
### 目的
`case`語句的主要目的是為了簡化基於整數或字符變量的多重條件判斷，使代碼更為清晰和易於維護。

### 使用方法
`case`語句必須與`switch`語句一起使用。基本語法如下：

```cpp
switch (expression) {
    case constant1:
        // 執行代碼塊1
        break;
    case constant2:
        // 執行代碼塊2
        break;
    default:
        // 如果沒有匹配到任何case，執行這裡的代碼
}
```

- `expression`：被評估的變量，通常是整型或字符型。
- `case constantN`：當`expression`的值等於`constantN`時執行的代碼。
- `break`：用於跳出`switch`語句，防止執行到後續的`case`。
- `default`：可選的，當沒有匹配的`case`時執行。

### 詳細說明
在`switch`語句中，`case`標籤必須是常量表達式。這意味著不能使用變量或運算式來定義`case`標籤。`break`語句是可選的，但如果省略，則會導致“fall-through”行為，後續的`case`也會被執行，直到遇到`break`或`switch`結束。

## 範例
以下是一些基本的使用範例：

### 範例1：簡單的switch-case
```cpp
#include <iostream>
using namespace std;

int main() {
    int day = 4;
    
    switch (day) {
        case 1:
            cout << "星期一" << endl;
            break;
        case 2:
            cout << "星期二" << endl;
            break;
        case 3:
            cout << "星期三" << endl;
            break;
        case 4:
            cout << "星期四" << endl;
            break;
        default:
            cout << "無效的星期" << endl;
    }
    return 0;
}
```

### 範例2：使用default
```cpp
#include <iostream>
using namespace std;

int main() {
    char grade = 'B';
    
    switch (grade) {
        case 'A':
            cout << "優秀" << endl;
            break;
        case 'B':
            cout << "良好" << endl;
            break;
        case 'C':
            cout << "及格" << endl;
            break;
        default:
            cout << "不及格" << endl;
    }
    return 0;
}
```

## 解釋
使用`case`語句時，開發者需要注意以下幾點：

1. **fall-through行為**：如果不使用`break`，將導致後續`case`的代碼被執行，這可能會導致意料之外的結果。
2. **常量要求**：`case`標籤必須是常量，不能使用變量。
3. **數據類型限制**：`switch`語句僅支持整數和字符，其他類型（如浮點數或字符串）無法使用。

## 一句總結
`case`語句在C++中提供了一種有效的多重選擇結構，方便根據變量值執行不同的代碼塊。