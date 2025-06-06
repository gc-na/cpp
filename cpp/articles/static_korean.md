<!--
Meta Description: # C++에서의 static 키워드: 정의와 사용법 ## 개요 C++에서 `static` 키워드는 변수와 함수의 저장 기간 및 가시성을 제어하는 데 사용되는 중요한 키워드입니다. 이 키워드는 프로그램의 메모리 관리와 성능에 직접적인 영향을 미칠 수 있으며, 코드의 유지...
Meta Keywords: static, count, int, 키워드는, 변수는
-->

# C++에서의 static 키워드: 정의와 사용법

## 개요
C++에서 `static` 키워드는 변수와 함수의 저장 기간 및 가시성을 제어하는 데 사용되는 중요한 키워드입니다. 이 키워드는 프로그램의 메모리 관리와 성능에 직접적인 영향을 미칠 수 있으며, 코드의 유지 보수성을 높이는 데 기여합니다.

## 문서화

### 목적
`static` 키워드는 세 가지 주요 용도로 사용됩니다:
1. **정적 지역 변수**: 함수 내부에서 선언된 `static` 변수는 함수가 호출될 때마다 초기화되지 않고, 프로그램 종료 시까지 값을 유지합니다.
2. **정적 전역 변수**: 파일 내에서 선언된 전역 변수에 `static`을 사용하면 해당 변수가 파일 내에서만 가시성을 가집니다. 다른 파일에서는 접근할 수 없습니다.
3. **정적 클래스 멤버**: 클래스 내에서 `static`으로 선언된 멤버는 클래스의 모든 인스턴스에서 공유됩니다. 이러한 멤버는 클래스의 인스턴스 없이도 접근이 가능합니다.

### 사용법
`static` 키워드는 다음과 같이 사용할 수 있습니다:

1. **정적 지역 변수**:
    ```cpp
    void function() {
        static int count = 0; // 초기화는 한 번만 수행됨
        count++;
        std::cout << count << std::endl;
    }
    ```

2. **정적 전역 변수**:
    ```cpp
    static int globalVar = 5; // 이 변수는 같은 파일에서만 접근 가능
    ```

3. **정적 클래스 멤버**:
    ```cpp
    class MyClass {
    public:
        static int staticVar; // 클래스의 모든 인스턴스가 공유함
    };

    int MyClass::staticVar = 0; // 정의 및 초기화
    ```

### 예제
```cpp
#include <iostream>

void increment() {
    static int count = 0; // 정적 변수, 함수가 호출될 때마다 값 유지
    count++;
    std::cout << "Count: " << count << std::endl;
}

int main() {
    increment(); // Count: 1
    increment(); // Count: 2
    increment(); // Count: 3

    return 0;
}
```

### 설명
- **정적 지역 변수의 초기화**: 정적 지역 변수는 프로그램의 시작 시 한 번만 초기화되며, 이후 함수가 호출될 때마다 그 값이 유지됩니다. 이는 상태를 유지하는 데 유용하지만, 여러 스레드에서 접근할 경우 동기화 문제가 발생할 수 있습니다.
- **정적 전역 변수의 가시성**: 정적 전역 변수는 파일 내에서만 유효하므로, 같은 이름의 변수를 다른 파일에서 선언할 수 있습니다.
- **정적 멤버의 접근**: 정적 멤버는 클래스의 인스턴스를 생성하지 않고도 접근할 수 있으며, 모든 인스턴스가 동일한 값을 공유합니다. 이는 메모리 사용을 줄이는데 도움이 됩니다.

### 주의사항
- 정적 변수는 상태를 유지하므로, 코드의 복잡성이 증가할 수 있습니다. 특히 멀티스레드 환경에서의 사용은 주의가 필요합니다.
- 정적 멤버는 클래스의 모든 인스턴스가 공유하는 값이므로, 의도치 않게 데이터가 변경될 수 있습니다.

## 한 줄 요약
C++에서 `static` 키워드는 변수와 함수의 저장 기간 및 가시성을 제어하여 메모리 관리와 코드의 유지 보수성을 높이는 데 사용됩니다.