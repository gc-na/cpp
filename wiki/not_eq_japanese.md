<!--
Meta Description: # C++ の not_eq: 等しくない比較演算子 ## 概要 C++ の `not_eq` は、2つの値が等しくないかどうかを比較するための論理演算子です。この演算子は、特に STL（Standard Template Library）での比較に利用されます。 ## ドキュメント `not_eq...
Meta Keywords: not_eq, std, int, include, value1
-->

# C++ の not_eq: 等しくない比較演算子

## 概要
C++ の `not_eq` は、2つの値が等しくないかどうかを比較するための論理演算子です。この演算子は、特に STL（Standard Template Library）での比較に利用されます。

## ドキュメント
`not_eq` は、C++11 で導入された演算子で、`!=` 演算子の代替として使用されます。これは、より可読性の高いコードを書くために使用され、特に条件式の中で論理演算子を使う際に便利です。`not_eq` は、`std::not_equal_to` としても知られ、関数オブジェクトとしても利用できます。

### 用法
`not_eq` は、以下のように使用します。

```cpp
#include <functional>

bool result = std::not_eq(value1, value2);
```

ここで、`value1` と `value2` は比較対象の値です。これにより、`value1` が `value2` と等しくない場合に `true` を返します。

## 例
以下は、`not_eq` の基本的な使用例です。

```cpp
#include <iostream>
#include <functional>

int main() {
    int a = 5;
    int b = 10;

    if (std::not_equal_to<int>()(a, b)) {
        std::cout << "a と b は等しくありません。" << std::endl;
    } else {
        std::cout << "a と b は等しいです。" << std::endl;
    }

    return 0;
}
```

この例では、`a` と `b` が等しくないことを確認し、その結果に基づいてメッセージを表示します。

## 説明
`not_eq` を使用する際の一般的な落とし穴は、型の整合性です。異なる型の値を比較しようとすると、コンパイルエラーや予期しない動作が発生する可能性があります。また、ポインタの比較やカスタムクラスの比較を行う際には、適切に演算子オーバーロードが実装されていることを確認する必要があります。

さらに、`not_eq` は STL のアルゴリズムと組み合わせて使用されることが多く、例えば `std::remove_if` や `std::count_if` などの関数と併用することが可能です。

## 一文の要約
C++ の `not_eq` は、2つの値が等しくないかどうかを比較するための便利な演算子です。