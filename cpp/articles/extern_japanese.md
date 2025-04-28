<!--
Meta Description: # C++におけるexternの使い方と特徴 ## 概要 `extern`は、C++のプログラミング言語において、変数や関数のスコープを指定するために使用されるキーワードです。これにより、他のファイルから変数や関数にアクセスできるようになります。 ## ドキュメンテーション `extern`キーワー...
Meta Keywords: extern, cpp, std, int, globalvar
-->

# C++におけるexternの使い方と特徴

## 概要
`extern`は、C++のプログラミング言語において、変数や関数のスコープを指定するために使用されるキーワードです。これにより、他のファイルから変数や関数にアクセスできるようになります。

## ドキュメンテーション
`extern`キーワードは、主に以下の目的で使用されます：

1. **変数の外部リンク**: `extern`を使うことで、他のソースファイルで定義された変数を参照することができます。この場合、変数は他のファイルで定義されている必要があります。
   
2. **関数の外部リンク**: 関数の宣言に`extern`を付けることで、他のファイルに定義された関数を使用することができます。

### 用法
- 変数の宣言：
  ```cpp
  extern int globalVar; // 他のファイルで定義されている変数を宣言
  ```

- 関数の宣言：
  ```cpp
  extern void myFunction(); // 他のファイルで定義されている関数を宣言
  ```

## 例
以下は`extern`の基本的な使用例です。

### 変数の例
**ファイル1: variable.cpp**
```cpp
#include <iostream>

int globalVar = 10; // 変数の定義

void printGlobalVar() {
    std::cout << "Global Variable: " << globalVar << std::endl;
}
```

**ファイル2: main.cpp**
```cpp
#include <iostream>

extern int globalVar; // 変数の宣言

int main() {
    std::cout << "Accessing Global Variable: " << globalVar << std::endl;
    return 0;
}
```

### 関数の例
**ファイル1: function.cpp**
```cpp
#include <iostream>

void myFunction() {
    std::cout << "Hello from myFunction!" << std::endl;
}
```

**ファイル2: main.cpp**
```cpp
#include <iostream>

extern void myFunction(); // 関数の宣言

int main() {
    myFunction(); // 関数の呼び出し
    return 0;
}
```

## 説明
`extern`を使用する際の一般的な落とし穴には以下のようなものがあります：

- **初期化をしない**: `extern`を使用した変数には、初期化を行わなければなりません。初期化を忘れると、未定義の動作が発生する可能性があります。

- **リンクエラー**: 他のファイルで変数や関数を定義していない場合、リンクエラーが発生します。

- **スコープの概念**: `extern`はあくまで変数や関数のスコープを指定するものであり、実際のメモリの配置や初期化は行いません。

## 一文要約
`extern`は、C++において他のソースファイルで定義された変数や関数にアクセスするためのキーワードです。