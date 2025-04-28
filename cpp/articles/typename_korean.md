<!--
Meta Description: # C++에서 typename의 이해와 활용 ## 개요 C++에서 `typename`은 템플릿 프로그래밍에서 타입을 명시하는 데 사용되는 키워드로, 코드의 가독성을 높이고 타입 의도를 명확히 하는 데 중요한 역할을 합니다. ## 문서 ### 목적 `typename`은 ...
Meta Keywords: typename, 타입을, 의존적, 템플릿, std
-->

# C++에서 typename의 이해와 활용

## 개요
C++에서 `typename`은 템플릿 프로그래밍에서 타입을 명시하는 데 사용되는 키워드로, 코드의 가독성을 높이고 타입 의도를 명확히 하는 데 중요한 역할을 합니다.

## 문서
### 목적
`typename`은 템플릿 내에서 의도된 타입을 명시하고, 템플릿 매개변수가 타입임을 컴파일러에 알리는 데 사용됩니다. 이 키워드는 특히 템플릿을 사용할 때 타입을 추론하거나 지정하는 과정에서 발생할 수 있는 혼란을 줄여줍니다.

### 사용법
`typename` 키워드는 두 가지 주요 용도로 사용됩니다:
1. **템플릿 매개변수에서 타입을 정의할 때**
2. **의존적 이름(Dependent Names)에서 타입을 명시할 때**

#### 템플릿 매개변수에서의 사용
```cpp
template<typename T>
void func(T arg) {
    // T를 타입으로 사용하는 함수
}
```

#### 의존적 이름에서의 사용
```cpp
template<typename T>
void func() {
    typename T::type var; // T의 내부 타입을 명시
}
```

## 예제
### 기본 사용 예
아래는 `typename`의 기본적인 사용 예입니다.

```cpp
#include <iostream>

template<typename T>
void printType(T value) {
    std::cout << "Value: " << value << std::endl;
}

int main() {
    printType(10);        // int 타입
    printType(3.14);     // double 타입
    printType("Hello");   // const char* 타입
    return 0;
}
```

### 의존적 이름 예
아래는 의존적 이름에서 `typename`을 사용하는 예입니다.

```cpp
#include <iostream>
#include <vector>

template<typename T>
class MyClass {
public:
    using ValueType = typename T::value_type;

    void display() {
        std::cout << "ValueType: " << typeid(ValueType).name() << std::endl;
    }
};

int main() {
    MyClass<std::vector<int>> myObj;
    myObj.display(); // ValueType: i (int)
    return 0;
}
```

## 설명
`typename`을 잘못 사용하면 컴파일 오류가 발생할 수 있습니다. 특히, 의존적 이름을 사용할 때 타입을 명확히 하지 않으면, 컴파일러는 이를 변수로 해석하여 오류가 발생할 수 있습니다. 따라서, 의존적 이름을 사용할 경우 항상 `typename`을 사용하여 타입임을 명시해 주어야 합니다.

### 일반적인 오류 및 주의사항
- **타입과 변수를 혼동**: `typename`은 오직 타입을 명시할 때만 사용되며, 변수명을 사용할 때는 사용하지 않아야 합니다.
- **C++11 이전과 이후의 차이**: C++11 이전에는 `typename`이 필요했지만, C++11 이후에는 `decltype`와 같은 다른 기능이 추가되어 타입 추론이 더 용이합니다.

## 한 줄 요약
C++에서 `typename`은 템플릿에서 타입을 명시하는 데 사용되는 중요한 키워드입니다.