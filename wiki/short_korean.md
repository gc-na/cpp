<!--
Meta Description: # C++에서의 short: 데이터 타입의 이해와 사용법 ## 개요 C++에서 `short`는 메모리 사용을 최적화하고 적은 범위의 정수를 저장하기 위해 사용되는 기본 데이터 타입입니다. 이 타입은 특히 메모리 제약이 있는 환경에서 유용합니다. ## 문서화 ### 목적...
Meta Keywords: short, 있습니다, 데이터, signed, unsigned
-->

# C++에서의 short: 데이터 타입의 이해와 사용법

## 개요
C++에서 `short`는 메모리 사용을 최적화하고 적은 범위의 정수를 저장하기 위해 사용되는 기본 데이터 타입입니다. 이 타입은 특히 메모리 제약이 있는 환경에서 유용합니다.

## 문서화

### 목적
`short`는 정수를 저장하기 위한 데이터 타입 중 하나로, 2바이트(16비트)의 메모리를 차지합니다. 이는 일반적인 `int`보다 적은 메모리를 사용하지만, 저장할 수 있는 값의 범위가 제한적입니다.

### 사용법
C++에서 `short`은 다음과 같이 선언할 수 있습니다:
```cpp
short variableName;
```
변수 선언 후, 정수 값을 할당할 수 있습니다:
```cpp
short num = 10;
```
또한, `short`는 `signed`와 `unsigned`로도 사용할 수 있습니다. 기본적으로 `short`는 `signed`입니다:
```cpp
signed short signedNum = -10;
unsigned short unsignedNum = 20;
```

### 세부 사항
- **메모리 크기**: `short`는 일반적으로 2바이트입니다.
- **값의 범위**: `signed short`는 -32,768에서 32,767까지, `unsigned short`는 0에서 65,535까지의 값을 저장할 수 있습니다.
- **타입 변환**: `short`는 다른 정수형 타입으로 자동 변환될 수 있으며, 이로 인해 데이터 손실이 발생할 수 있으므로 주의해야 합니다.

## 예제
```cpp
#include <iostream>
using namespace std;

int main() {
    short a = 100;
    short b = 200;
    short sum = a + b; // 덧셈
    cout << "Sum: " << sum << endl;
    
    unsigned short u = 60000;
    cout << "Unsigned short: " << u << endl;

    return 0;
}
```

## 설명
`short` 타입을 사용할 때 주의해야 할 점은 다음과 같습니다:
- **범위 초과**: `short`의 범위를 초과하는 값을 할당하면, undefined behavior가 발생할 수 있습니다. 예를 들어, `signed short`에 40,000을 할당하면 오버플로우가 발생합니다.
- **타입 변환**: 다른 정수형 타입으로의 변환 시, 예상치 못한 결과가 나올 수 있습니다. 특히 `short`에서 `int`로 변환할 때 부호가 변경될 수 있으므로 주의해야 합니다.
- **플랫폼 의존성**: `short`의 크기는 대부분의 시스템에서 2바이트이지만, 특정 플랫폼에 따라 다를 수 있으므로, 이식성을 고려해야 합니다.

## 한 줄 요약
C++에서 `short`는 메모리를 절약하기 위해 사용되는 2바이트 정수형 데이터 타입으로, 제한된 범위의 정수를 저장하는 데 적합하다.