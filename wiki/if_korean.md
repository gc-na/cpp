<!--
Meta Description: # C++의 if 문: 조건문을 통한 흐름 제어 ## 개요 C++에서 `if` 문은 프로그램 실행 중 특정 조건을 평가하고, 그 결과에 따라 코드의 흐름을 제어하는 데 사용됩니다. 이 구조는 조건부 로직을 구현하는데 필수적입니다. ## 문서화 `if` 문은 주어진 조건...
Meta Keywords: std, else, cout, endl, 조건이
-->

# C++의 if 문: 조건문을 통한 흐름 제어

## 개요
C++에서 `if` 문은 프로그램 실행 중 특정 조건을 평가하고, 그 결과에 따라 코드의 흐름을 제어하는 데 사용됩니다. 이 구조는 조건부 로직을 구현하는데 필수적입니다.

## 문서화
`if` 문은 주어진 조건이 참(true)일 경우 특정 블록의 코드를 실행하도록 하는 제어 구조입니다. 기본 문법은 다음과 같습니다:

```cpp
if (조건) {
    // 조건이 참일 때 실행될 코드
}
```

### 사용법
- 조건은 불리언 표현식이어야 하며, 참 또는 거짓으로 평가됩니다.
- `if` 문은 선택적으로 `else` 또는 `else if`와 함께 사용될 수 있습니다.

### 문법 예시
```cpp
if (x > 0) {
    std::cout << "x는 양수입니다." << std::endl;
} else if (x < 0) {
    std::cout << "x는 음수입니다." << std::endl;
} else {
    std::cout << "x는 0입니다." << std::endl;
}
```

## 예제
다음은 `if` 문을 사용하는 간단한 예제입니다.

```cpp
#include <iostream>

int main() {
    int number;
    std::cout << "숫자를 입력하세요: ";
    std::cin >> number;

    if (number > 0) {
        std::cout << "입력한 숫자는 양수입니다." << std::endl;
    } else if (number < 0) {
        std::cout << "입력한 숫자는 음수입니다." << std::endl;
    } else {
        std::cout << "입력한 숫자는 0입니다." << std::endl;
    }

    return 0;
}
```

## 설명
- **중괄호의 사용**: `if` 문에서 중괄호 `{}`는 조건이 참일 때 실행될 코드 블록을 정의합니다. 단일 문장일 경우 생략할 수 있지만, 명확성을 위해 사용하는 것이 좋습니다.
- **조건 평가**: C++에서 조건은 0이 아닌 값은 참(true)으로, 0은 거짓(false)으로 평가됩니다.
- **다중 조건**: 여러 조건을 평가할 때는 `else if`를 사용하여 추가 조건을 연결할 수 있습니다.

### 일반적인 실수
- **조건이 항상 참인 경우**: 조건이 잘못 설정되어 항상 참이 되면 무한 루프가 발생할 수 있습니다.
- **중괄호 생략**: 단일 문장일 경우 중괄호를 생략하는 것은 가능하지만, 나중에 코드가 변경될 경우 의도치 않은 오류를 초래할 수 있습니다.

## 한 줄 요약
C++의 `if` 문은 주어진 조건에 따라 코드의 실행 흐름을 제어하는 데 사용되는 기본적인 조건문입니다.