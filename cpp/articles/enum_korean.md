<!--
Meta Description: # C++의 enum: 열거형 데이터 타입 완벽 가이드 ## 개요 C++의 enum(열거형)은 상수 값의 집합을 정의하는 데이터 타입으로, 코드의 가독성을 높이고 상수 값의 사용을 용이하게 만듭니다. ## 문서화 enum은 특정 값의 집합을 정의하고 싶을 때 사용되는 ...
Meta Keywords: enum, 열거형, std, 있습니다, color
-->

# C++의 enum: 열거형 데이터 타입 완벽 가이드

## 개요
C++의 enum(열거형)은 상수 값의 집합을 정의하는 데이터 타입으로, 코드의 가독성을 높이고 상수 값의 사용을 용이하게 만듭니다.

## 문서화
enum은 특정 값의 집합을 정의하고 싶을 때 사용되는 사용자 정의 데이터 타입입니다. C++에서 enum은 다음과 같은 목적을 가지고 있습니다:

- **가독성 향상**: 상수 값에 의미 있는 이름을 부여하여 코드의 이해도를 높입니다.
- **타입 안전성**: 열거형은 기본적으로 정수형으로 취급되지만, 명확한 타입을 제공하여 타입 안전성을 강화합니다.

### enum 선언
C++에서 enum은 다음과 같이 선언합니다:

```cpp
enum EnumName {
    Constant1,
    Constant2,
    Constant3 = 10,
    Constant4
};
```

여기서 `Constant1`, `Constant2`, `Constant3`, `Constant4`는 열거형 상수이며, `Constant3`는 10으로 초기화됩니다. 이후 `Constant4`는 `Constant3`의 다음 값인 11로 자동으로 초기화됩니다.

### 사용 예시
enum을 사용할 때, 일반적으로 switch 문과 함께 사용하여 조건문을 작성하는 데 유용합니다.

```cpp
#include <iostream>

enum Color {
    Red,
    Green,
    Blue
};

int main() {
    Color myColor = Green;

    switch (myColor) {
        case Red:
            std::cout << "Red Color" << std::endl;
            break;
        case Green:
            std::cout << "Green Color" << std::endl;
            break;
        case Blue:
            std::cout << "Blue Color" << std::endl;
            break;
    }

    return 0;
}
```

## 설명
### 일반적인 오류 및 주의 사항
- **명명 충돌**: 서로 다른 enum에서 같은 이름의 상수를 정의할 경우, 충돌이 발생할 수 있습니다. 이는 코드의 예측 가능성을 떨어뜨릴 수 있습니다.
  
- **기본형**: enum의 기본형은 정수형입니다. 따라서 enum의 값을 정수형으로 변환할 수 있지만, 이로 인해 타입 안전성이 손상될 수 있습니다.

- **스코프**: C++11부터 도입된 `enum class`를 사용하면, 열거형 상수는 열거형 이름의 스코프 내에서만 유효하므로 충돌을 방지할 수 있습니다.

### enum class 예시
```cpp
enum class Fruit {
    Apple,
    Banana,
    Cherry
};

Fruit myFruit = Fruit::Banana;
```

이 예제에서는 `Fruit`라는 enum class를 정의하고, `Fruit::Banana`와 같이 스코프를 명시하여 사용합니다.

## 한 줄 요약
C++의 enum은 상수 값의 집합을 정의하여 코드의 가독성을 높이고 타입 안전성을 제공하는 열거형 데이터 타입입니다.