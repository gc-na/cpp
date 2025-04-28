<!--
Meta Description: # C++テンプレートの完全ガイド ## 概要 C++のテンプレートは、型に依存しないコードを柔軟に記述するための機能です。これにより、同じ関数やクラスが異なるデータ型で動作することが可能になり、コードの再利用性が向上します。 ## ドキュメント ### 目的 テンプレートは、C++プログラムにおい...
Meta Keywords: template, return, value, first, second
-->

# C++テンプレートの完全ガイド

## 概要
C++のテンプレートは、型に依存しないコードを柔軟に記述するための機能です。これにより、同じ関数やクラスが異なるデータ型で動作することが可能になり、コードの再利用性が向上します。

## ドキュメント
### 目的
テンプレートは、C++プログラムにおいて、同じ機能を異なる型に対して実装するための手段を提供します。これにより、型安全性を保持しつつ、一般化されたコードを記述することができます。

### 使用法
C++のテンプレートには、関数テンプレートとクラステンプレートの2種類があります。

#### 関数テンプレート
関数テンプレートは、特定の型に依存せず、任意の型に対して機能する関数を定義します。

```cpp
template <typename T>
T add(T a, T b) {
    return a + b;
}
```

#### クラステンプレート
クラステンプレートは、特定の型に依存しないクラスを定義します。

```cpp
template <typename T>
class Box {
public:
    Box(T value) : value(value) {}
    T getValue() const { return value; }
private:
    T value;
};
```

### 詳細
テンプレートは、コンパイル時に型が決定されるため、高いパフォーマンスを維持しつつ、型の柔軟性を提供します。テンプレートは、STL（Standard Template Library）などのライブラリで広く使用されており、リストやマップなどのデータ構造を一般化された形で提供します。

## 例
以下は、関数テンプレートとクラステンプレートの基本的な使用例です。

### 関数テンプレートの例

```cpp
#include <iostream>
using namespace std;

template <typename T>
T multiply(T a, T b) {
    return a * b;
}

int main() {
    cout << multiply<int>(2, 3) << endl;      // 出力: 6
    cout << multiply<double>(2.5, 3.0) << endl; // 出力: 7.5
    return 0;
}
```

### クラステンプレートの例

```cpp
#include <iostream>
using namespace std;

template <typename T>
class Pair {
public:
    Pair(T first, T second) : first(first), second(second) {}
    void display() {
        cout << first << ", " << second << endl;
    }
private:
    T first, second;
};

int main() {
    Pair<int> intPair(1, 2);
    intPair.display(); // 出力: 1, 2

    Pair<string> strPair("Hello", "World");
    strPair.display(); // 出力: Hello, World
    return 0;
}
```

## 説明
テンプレートを使用する際の一般的な落とし穴や注意点には以下のようなものがあります。

- **型の不一致**: テンプレートは型に依存しないため、異なる型の引数を渡すとコンパイルエラーが発生します。テンプレートの使用時には型が一致しているか確認することが重要です。
- **冗長なエラーメッセージ**: テンプレートに関連するエラーメッセージは、しばしば冗長で理解しにくい場合があります。エラーメッセージをよく読み、原因を特定することが必要です。
- **テンプレート特殊化**: 特定の型に対して異なる実装を提供したい場合、テンプレート特殊化を使用することができますが、これには注意が必要です。

## 一文のまとめ
C++のテンプレートは、型に依存しない柔軟なコードを実現し、再利用性を向上させる強力な機能です。