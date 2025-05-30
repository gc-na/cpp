<!--
Meta Description: # C++における「return」ステートメントの使い方 ## 概要 C++における「return」ステートメントは、関数の実行を終了し、呼び出し元に制御を戻すために使用されます。この文は、関数の戻り値を指定する際にも重要な役割を果たします。 ## ドキュメンテーション ### 目的 「return...
Meta Keywords: return, int, cpp, ステートメントは, std
-->

# C++における「return」ステートメントの使い方

## 概要
C++における「return」ステートメントは、関数の実行を終了し、呼び出し元に制御を戻すために使用されます。この文は、関数の戻り値を指定する際にも重要な役割を果たします。

## ドキュメンテーション
### 目的
「return」ステートメントは、関数の結果を呼び出し元に返すために使用されます。戻り値の型が指定されている場合、関数が終了する際にその値を返す必要があります。また、戻り値が必要ない場合は、単に「return;」と書くことで関数を終了させることが可能です。

### 使用法
- **基本構文**:
  ```cpp
  return [値];
  ```

- **戻り値のある関数の例**:
  ```cpp
  int add(int a, int b) {
      return a + b;  // a + bの結果を返す
  }
  ```

- **戻り値のない関数の例**:
  ```cpp
  void printMessage() {
      std::cout << "Hello, World!" << std::endl;
      return;  // 明示的にreturnを使うことも可能だが、省略してもよい
  }
  ```

### 詳細
- 戻り値の型は、関数定義で指定される必要があります。戻り値のない関数は「void」と宣言されます。
- 複数のreturnステートメントを持つ関数も可能ですが、どのreturnが実行されるかに注意が必要です。
- 戻り値が必要な関数でreturnを使わないと、コンパイラエラーが発生します。

## 例
以下は、基本的な「return」の使用例です。

```cpp
#include <iostream>
using namespace std;

int multiply(int x, int y) {
    return x * y;  // xとyの積を返す
}

int main() {
    int result = multiply(4, 5);  // multiply関数を呼び出し
    cout << "Result: " << result << endl;  // 結果を出力
    return 0;  // main関数の終了
}
```

## 説明
- **共通の落とし穴**: 
  - 戻り値が必要な関数でreturnを忘れると、未定義の動作になる可能性があります。
  - 常に関数の戻り値が正しい型であることを確認してください。

- **注意点**:
  - return文は、関数内の任意の場所に置くことができますが、関数の実行フローを理解しておくことが重要です。
  - returnの後にコードがある場合、そのコードは実行されません。

## ワンライング要約
C++の「return」ステートメントは、関数から値を返し、制御を呼び出し元に戻すための重要な要素です。