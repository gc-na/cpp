<!--
Meta Description: # C++의 switch-case 문: 조건 분기 처리하기 ## 개요 C++의 `case` 문은 `switch` 문과 함께 사용되며, 여러 개의 조건 중 하나를 선택하여 해당하는 코드 블록을 실행하는 데 사용됩니다. 이는 복잡한 조건문을 간결하게 만들어 주며, 코드의 ...
Meta Keywords: case, switch, break, cout, endl
-->

# C++의 switch-case 문: 조건 분기 처리하기

## 개요
C++의 `case` 문은 `switch` 문과 함께 사용되며, 여러 개의 조건 중 하나를 선택하여 해당하는 코드 블록을 실행하는 데 사용됩니다. 이는 복잡한 조건문을 간결하게 만들어 주며, 코드의 가독성을 향상시키는 데 도움을 줍니다.

## 문서화
`case` 문은 `switch` 문 내부에서 사용되며, 정수형 또는 열거형 값을 기준으로 분기 처리를 수행합니다. `switch` 문은 주어진 표현식의 값에 따라 여러 `case` 중 하나를 선택하여 해당하는 코드 블록을 실행합니다. `case` 문은 다음과 같은 형식으로 사용됩니다:

```cpp
switch (expression) {
    case constant1:
        // constant1에 해당할 때 실행될 코드
        break;
    case constant2:
        // constant2에 해당할 때 실행될 코드
        break;
    // 추가적인 case 문
    default:
        // 어떤 case에도 해당하지 않을 때 실행될 코드
}
```

### 목적
- 여러 조건을 간결하게 처리할 수 있습니다.
- 코드의 가독성을 높이고 유지보수를 용이하게 합니다.

### 사용법
1. `switch` 키워드로 시작합니다.
2. 괄호 안에 조건으로 사용할 표현식을 작성합니다.
3. 각 `case` 문에 상수 값을 작성하고, 그에 해당하는 코드를 블록 안에 작성합니다.
4. `break` 문을 사용하여 `switch` 문을 종료합니다. (생략할 경우 다음 `case`로의 흐름이 이어질 수 있습니다.)
5. 선택적으로 `default` 문을 사용하여 모든 `case`에 해당하지 않을 때 실행될 코드를 정의할 수 있습니다.

## 예제
아래는 `switch-case` 문을 사용한 간단한 예제입니다.

```cpp
#include <iostream>
using namespace std;

int main() {
    int day = 3;

    switch (day) {
        case 1:
            cout << "월요일" << endl;
            break;
        case 2:
            cout << "화요일" << endl;
            break;
        case 3:
            cout << "수요일" << endl;
            break;
        case 4:
            cout << "목요일" << endl;
            break;
        case 5:
            cout << "금요일" << endl;
            break;
        default:
            cout << "주말" << endl;
    }

    return 0;
}
```

위의 예제에서, 변수 `day`의 값이 3일 경우 "수요일"이 출력됩니다.

## 설명
- **중복된 case**: 동일한 상수 값을 가진 여러 `case`를 작성할 수 있으며, 이 경우 해당 `case` 블록이 실행됩니다.
- **break 문**: `break` 문을 생략하면, 다음 `case`로 흐름이 넘어가므로 주의해야 합니다. 이를 "fall-through"라고 하며, 경우에 따라 의도적으로 사용할 수 있습니다.
- **expression의 타입**: `switch` 문에서 사용할 수 있는 표현식은 정수형, 문자형, 열거형 등이 있습니다. 하지만 부동소수점형은 사용할 수 없습니다.

## 한 줄 요약
C++의 `case` 문은 `switch` 문과 함께 사용되어 여러 조건을 간결하게 처리하는 데 유용한 기능입니다.