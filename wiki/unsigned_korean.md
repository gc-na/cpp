<!--
Meta Description: # C++에서의 unsigned: 부호 없는 정수형에 대한 완벽 가이드 ## 개요 C++에서 `unsigned`는 부호 없는 정수형 데이터 타입을 정의하는 키워드로, 양의 정수 값을 표현하는 데 사용됩니다. 이는 음수 값을 허용하지 않으며, 정수의 표현 범위를 두 배로...
Meta Keywords: unsigned, int, std, max, 오버플로우
-->

# C++에서의 unsigned: 부호 없는 정수형에 대한 완벽 가이드

## 개요
C++에서 `unsigned`는 부호 없는 정수형 데이터 타입을 정의하는 키워드로, 양의 정수 값을 표현하는 데 사용됩니다. 이는 음수 값을 허용하지 않으며, 정수의 표현 범위를 두 배로 늘립니다.

## 문서화
`unsigned`는 C++의 기본 데이터 타입인 `int`, `char`, `short`, `long` 등과 함께 사용됩니다. 부호가 없다는 것은 값이 0 이상의 정수로 제한된다는 의미입니다. 이를 통해 더 큰 양수 범위를 제공하며, 메모리 사용을 최적화하는 데 유용합니다.

### 사용법
`unsigned` 키워드는 다음과 같이 사용됩니다:

```cpp
unsigned int a = 10;       // 부호 없는 정수형 변수 a
unsigned char b = 255;     // 부호 없는 문자형 변수 b
unsigned long c = 4294967295; // 부호 없는 긴 정수형 변수 c
```

### 세부사항
- `unsigned`와 `signed`의 차이: `signed`는 기본적으로 음수와 양수를 모두 허용하지만, `unsigned`는 오직 양수 값만을 가집니다.
- 메모리 크기: `unsigned int`는 일반적으로 4바이트(32비트)를 차지하며, 값의 범위는 0부터 4,294,967,295까지입니다.
- 오버플로우: `unsigned` 타입의 숫자가 최대값을 초과할 경우, 값은 0으로 순환됩니다. 이는 일반적인 부호 있는 타입과 다르게 동작합니다.

## 예제
```cpp
#include <iostream>

int main() {
    unsigned int a = 10;
    unsigned int b = 20;
    unsigned int sum = a + b; // sum = 30
    std::cout << "Sum: " << sum << std::endl;

    unsigned int max = 4294967295; // 최대값
    std::cout << "Max: " << max << std::endl;

    max++; // 오버플로우 발생
    std::cout << "After Overflow: " << max << std::endl; // 0 출력
    return 0;
}
```

## 설명
`unsigned`를 사용할 때 주의해야 할 몇 가지 사항이 있습니다:
- **오버플로우**: 부호 없는 정수는 오버플로우 시 0으로 순환하므로, 이를 고려하여 연산을 수행해야 합니다. 예를 들어, `unsigned int`의 최대값에 1을 더하면 결과는 0이 됩니다.
- **형 변환**: `unsigned`와 `signed` 타입 간의 연산 시, 컴파일러는 자동으로 형 변환을 수행합니다. 이로 인해 의도하지 않게 음수 값이 발생할 수 있으므로, 이러한 상황을 피하기 위해 명시적인 형 변환을 사용하는 것이 좋습니다.

## 한 줄 요약
C++의 `unsigned` 키워드는 부호 없는 정수형을 정의하여 음수를 허용하지 않고, 더 큰 범위의 양의 정수를 사용할 수 있게 합니다.