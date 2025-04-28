<!--
Meta Description: # C++の「case」文: スイッチ文での選択肢の定義 ## 概要 C++における「case」文は、`switch`文の一部であり、特定の値に基づいて異なるコードブロックを実行するための選択肢を提供します。これにより、複数の条件を簡潔に管理でき、可読性の高いコードを書くことが可能になります。 ##...
Meta Keywords: case, break, switch, cout, endl
-->

# C++の「case」文: スイッチ文での選択肢の定義

## 概要
C++における「case」文は、`switch`文の一部であり、特定の値に基づいて異なるコードブロックを実行するための選択肢を提供します。これにより、複数の条件を簡潔に管理でき、可読性の高いコードを書くことが可能になります。

## ドキュメント
### 目的
「case」文は、`switch`文と共に使用され、指定された変数の値に応じた異なる処理を行うために利用されます。これは、複数の`if`文を使用するよりも効率的で、条件分岐を明確に表現します。

### 使用法
`switch`文は、次のように構成されます。

```cpp
switch (expression) {
    case constant1:
        // constant1に一致した場合の処理
        break;
    case constant2:
        // constant2に一致した場合の処理
        break;
    // 他のcase文
    default:
        // どのcaseにも一致しない場合の処理
}
```

ここで、`expression`は評価される値であり、`constant1`や`constant2`はその値と比較される定数です。`break`文は、特定のケースが実行された後に`switch`文から抜け出すために必要です。

## 例
以下は、基本的な使用例です。

```cpp
#include <iostream>
using namespace std;

int main() {
    int day = 4;

    switch (day) {
        case 1:
            cout << "月曜日" << endl;
            break;
        case 2:
            cout << "火曜日" << endl;
            break;
        case 3:
            cout << "水曜日" << endl;
            break;
        case 4:
            cout << "木曜日" << endl;
            break;
        case 5:
            cout << "金曜日" << endl;
            break;
        default:
            cout << "週末" << endl;
    }

    return 0;
}
```
この例では、`day`が4の場合、"木曜日"が出力されます。

## 説明
### 一般的な落とし穴
- **break文の欠如**: `break`文を忘れると、次の`case`文が実行されるフォールスルーが発生する可能性があります。これが意図しない動作を引き起こすことがあります。
- **デフォルトケースの省略**: `default`ケースを省略すると、どの`case`にも一致しない場合に何も実行されないため、エラー処理が行えなくなります。

### 注意点
- `switch`文で使用できるのは整数型（`int`や`char`など）や列挙型であり、浮動小数点数型や文字列型は使用できません。
- `case`ラベルに同じ定数を複数回使うとエラーになります。

## 一文要約
C++における「case」文は、`switch`文の一部として、特定の値に基づいて異なる処理を簡潔に定義するための機能です。