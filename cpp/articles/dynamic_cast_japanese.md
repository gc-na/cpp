<!--
Meta Description: # C++のdynamic_castについての徹底ガイド ## 概要 `dynamic_cast`は、C++における多態性を利用した型変換を行うための演算子です。特に、基底クラスから派生クラスへの安全なキャストを提供し、ランタイムに型のチェックを行います。 ## ドキュメンテーション ### 目的 ...
Meta Keywords: dynamic_cast, derived, base, class, public
-->

# C++のdynamic_castについての徹底ガイド

## 概要
`dynamic_cast`は、C++における多態性を利用した型変換を行うための演算子です。特に、基底クラスから派生クラスへの安全なキャストを提供し、ランタイムに型のチェックを行います。

## ドキュメンテーション

### 目的
`dynamic_cast`は、ポインタや参照を持つオブジェクトの型を安全に変換するために使用されます。特に、仮想関数を持つクラスに適用される場合、オブジェクトの実際の型を確認したり、基底クラスから派生クラスへのキャストを行う際に役立ちます。

### 使用法
基本的な構文は以下の通りです。

```cpp
dynamic_cast<新しい型>(オブジェクト)
```

返される型は、オブジェクトが指定された新しい型に変換可能であればその型のポインタまたは参照となり、変換できない場合はポインタの場合は`nullptr`、参照の場合は`std::bad_cast`例外がスローされます。

### 詳細
- `dynamic_cast`は、ポリモーフィズムが有効なクラスに対して使用されます。これには少なくとも1つの仮想関数が必要です。
- `dynamic_cast`は、基底クラスと派生クラス間のキャストを行う際に、オブジェクトの実際の型を確認するために使用されます。
- 型の不一致がある場合、変換は失敗し、ポインタの場合は`nullptr`、参照の場合は例外を返します。

## 例

### 基本的な使用例
以下の例では、`Base`クラスとその派生クラス`Derived`を定義し、`dynamic_cast`を使用して型変換を行います。

```cpp
#include <iostream>
using namespace std;

class Base {
public:
    virtual ~Base() {}
};

class Derived : public Base {
public:
    void show() { cout << "Derived class" << endl; }
};

int main() {
    Base* b = new Derived();
    Derived* d = dynamic_cast<Derived*>(b);
    
    if (d) {
        d->show(); // "Derived class"と表示される
    } else {
        cout << "Cast failed." << endl;
    }

    delete b;
    return 0;
}
```

### 失敗するケース
基底クラスのポインタが異なる派生クラスを指している場合の例です。

```cpp
class AnotherDerived : public Base {};

int main() {
    Base* b = new AnotherDerived();
    Derived* d = dynamic_cast<Derived*>(b); // nullptrが返される

    if (!d) {
        cout << "Cast failed." << endl; // "Cast failed."と表示される
    }

    delete b;
    return 0;
}
```

## 説明
`dynamic_cast`を使用する際の一般的な落とし穴は、仮想関数を持たないクラスに対して使用することです。また、`dynamic_cast`は、型チェックが必要な場合にのみ使用すべきで、パフォーマンスに影響を及ぼす可能性があるため、頻繁には使用しない方が良いです。ポインタのキャスト失敗時に`nullptr`が返ることを忘れないでください。

## 一文要約
`dynamic_cast`は、C++において多態性を利用した安全な型変換を実現するための演算子です。