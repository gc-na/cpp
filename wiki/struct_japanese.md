<!--
Meta Description: # C++におけるstructの使い方と特徴 ## 概要 C++における`struct`は、データの集合を定義するためのユーザー定義型です。クラスと同様の機能を持ちながら、デフォルトでメンバーがパブリックである点が特徴です。 ## ドキュメンテーション `struct`は、関連するデータをグループ化...
Meta Keywords: struct, int, rect, cpp, point
-->

# C++におけるstructの使い方と特徴

## 概要
C++における`struct`は、データの集合を定義するためのユーザー定義型です。クラスと同様の機能を持ちながら、デフォルトでメンバーがパブリックである点が特徴です。

## ドキュメンテーション
`struct`は、関連するデータをグループ化するために使用されます。C++では、`struct`は以下のように定義されます。

### 基本構文
```cpp
struct StructName {
    // メンバー変数
    DataType member1;
    DataType member2;
    // メンバー関数
    ReturnType functionName(parameters);
};
```

### 使用目的
- データのグループ化：複数の関連するデータを一つの型で扱うことができ、コードの可読性が向上します。
- カスタムデータ型の作成：クラスと同様に、ユーザー定義型を作成できます。

### 詳細
- `struct`のメンバーはデフォルトでパブリックです。これに対して、クラスのメンバーはデフォルトでプライベートになります。
- メンバー関数を定義することもでき、オブジェクト指向プログラミングの一部として機能します。
- 継承が可能であり、他の`struct`やクラスから派生することもできます。

## 例
以下は、`struct`の基本的な使用例です。

### 例1: 簡単な構造体の定義
```cpp
#include <iostream>
using namespace std;

struct Point {
    int x;
    int y;
};

int main() {
    Point p1; // Point構造体のインスタンスを作成
    p1.x = 10; // メンバーに値を代入
    p1.y = 20;
    
    cout << "Point p1: (" << p1.x << ", " << p1.y << ")" << endl;
    return 0;
}
```

### 例2: メンバー関数を持つ構造体
```cpp
#include <iostream>
using namespace std;

struct Rectangle {
    int width;
    int height;

    int area() {
        return width * height; // 面積を計算するメンバー関数
    }
};

int main() {
    Rectangle rect;
    rect.width = 5;
    rect.height = 10;

    cout << "Area of rectangle: " << rect.area() << endl;
    return 0;
}
```

## 説明
`struct`を使用する際に注意すべきポイントは以下の通りです。
- **デフォルトのアクセス修飾子**：`struct`のメンバーはデフォルトでパブリックであるため、意図しないアクセスが発生する可能性があります。プライベートメンバーにしたい場合は、明示的に`private`を指定する必要があります。
- **クラスとの違い**：`struct`とクラスは非常に似ていますが、デフォルトのアクセス修飾子や継承の扱いに違いがあります。用途に応じて使い分けることが重要です。

## 一文要約
C++における`struct`は、関連するデータをグループ化し、データ型をカスタマイズするための強力で簡潔な方法です。