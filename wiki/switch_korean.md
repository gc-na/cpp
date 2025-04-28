<!--
Meta Description: # C++에서의 switch 문: 조건문을 효율적으로 처리하는 방법 ## 개요 C++에서 `switch` 문은 여러 조건을 간단하게 처리할 수 있는 제어 구조로, 특정 변수의 값에 따라 서로 다른 코드 블록을 실행할 수 있게 해줍니다. `switch` 문은 특히 다수의...
Meta Keywords: case, break, switch, cout, endl
-->

# C++에서의 switch 문: 조건문을 효율적으로 처리하는 방법

## 개요
C++에서 `switch` 문은 여러 조건을 간단하게 처리할 수 있는 제어 구조로, 특정 변수의 값에 따라 서로 다른 코드 블록을 실행할 수 있게 해줍니다. `switch` 문은 특히 다수의 조건을 처리할 때 `if-else` 문보다 가독성이 좋고 성능이 우수합니다.

## 문서화

### 목적
`switch` 문은 특정 변수의 값에 따라 여러 개의 코드 경로 중 하나를 선택하는 데 사용됩니다. 이 구조는 복잡한 조건문을 간단하게 표현할 수 있게 해줍니다.

### 사용법
`switch` 문은 다음과 같은 형식으로 작성됩니다:

```cpp
switch (expression) {
    case constant1:
        // constant1에 해당하는 경우 실행할 코드
        break;
    case constant2:
        // constant2에 해당하는 경우 실행할 코드
        break;
    // 추가적인 case 문
    default:
        // 위의 case 중 어떤 것도 일치하지 않을 때 실행할 코드
}
```

- **expression**: 평가할 변수나 식입니다. 정수형, 문자형, 열거형 등의 값이 올 수 있습니다.
- **case**: `expression`의 값이 일치하는 경우 실행할 코드 블록을 정의합니다.
- **break**: 현재의 `case` 블록을 종료하고 `switch` 문을 빠져나갑니다. 이를 사용하지 않으면 다음 `case` 문으로 제어가 흘러갈 수 있습니다.
- **default**: `case` 문 중 어떤 것도 일치하지 않을 경우 실행될 코드 블록입니다. 선택적입니다.

## 예제

### 기본 사용 예제
```cpp
#include <iostream>
using namespace std;

int main() {
    int num;
    cout << "숫자를 입력하세요 (1-3): ";
    cin >> num;

    switch (num) {
        case 1:
            cout << "당신이 선택한 숫자는 1입니다." << endl;
            break;
        case 2:
            cout << "당신이 선택한 숫자는 2입니다." << endl;
            break;
        case 3:
            cout << "당신이 선택한 숫자는 3입니다." << endl;
            break;
        default:
            cout << "유효하지 않은 숫자입니다." << endl;
            break;
    }

    return 0;
}
```

### 여러 case 사용 예제
```cpp
#include <iostream>
using namespace std;

int main() {
    char grade;
    cout << "학점을 입력하세요 (A, B, C, D, F): ";
    cin >> grade;

    switch (grade) {
        case 'A':
        case 'B':
            cout << "우수한 성적입니다!" << endl;
            break;
        case 'C':
            cout << "보통 성적입니다." << endl;
            break;
        case 'D':
            cout << "재시험이 필요합니다." << endl;
            break;
        case 'F':
            cout << "실패입니다." << endl;
            break;
        default:
            cout << "유효하지 않은 입력입니다." << endl;
            break;
    }

    return 0;
}
```

## 설명
- **break 문**: 각 `case` 문 끝에 `break` 문을 잊지 않도록 주의해야 합니다. 만약 `break` 문이 없으면, 다음 `case` 문이 연속적으로 실행됩니다. 이를 'fall-through'라고 하며, 의도하지 않은 결과를 초래할 수 있습니다.
- **default 문**: 모든 `case`에 해당하지 않을 때 실행되는 블록으로, 선택 사항입니다. 하지만 프로그램의 안정성을 위해 포함하는 것이 좋습니다.
- **expression의 타입**: `switch` 문에서 `expression`은 정수형, 문자형, 또는 열거형이어야 하며, 부동소수점형은 사용할 수 없습니다.

## 한 줄 요약
C++의 `switch` 문은 특정 변수의 값에 따라 여러 조건을 간단하고 효율적으로 처리하는 제어 구조입니다.