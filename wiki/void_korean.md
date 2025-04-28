<!--
Meta Description: # C++에서의 void: 기본 개념과 사용법 ## 개요 C++에서 `void`는 반환값이 없음을 나타내는 데이터 유형으로, 함수의 반환 유형이나 포인터의 타입으로 주로 사용된다. `void`는 함수가 결과를 반환하지 않을 때, 또는 특정 데이터를 처리할 필요가 없을 ...
Meta Keywords: void, std, ptr, int, cpp
-->

# C++에서의 void: 기본 개념과 사용법

## 개요
C++에서 `void`는 반환값이 없음을 나타내는 데이터 유형으로, 함수의 반환 유형이나 포인터의 타입으로 주로 사용된다. `void`는 함수가 결과를 반환하지 않을 때, 또는 특정 데이터를 처리할 필요가 없을 때 유용하다.

## 문서화
### 목적
`void`는 C++에서 다음과 같은 목적으로 사용된다:
- 함수가 값을 반환하지 않을 때 `void`를 사용하여 명시적으로 나타냄.
- 포인터의 경우, `void*`는 어떤 타입의 데이터도 가리킬 수 있는 포인터를 의미함.

### 사용법
1. **함수 반환 타입으로서의 void**: 
   ```cpp
   void myFunction() {
       // 함수 내용
   }
   ```
   위와 같이 정의된 함수는 어떠한 값도 반환하지 않는다.

2. **void 포인터**: 
   ```cpp
   void* ptr;
   int a = 10;
   ptr = &a; // int형 변수를 가리킬 수 있음
   ```
   `void*` 포인터는 다양한 타입의 주소를 저장할 수 있으며, 이를 통해 타입 안전성을 유지하면서도 유연하게 데이터를 처리할 수 있다.

## 예제
1. **void 함수 예제**:
   ```cpp
   #include <iostream>
   
   void greet() {
       std::cout << "Hello, World!" << std::endl;
   }

   int main() {
       greet(); // 함수 호출
       return 0;
   }
   ```

2. **void 포인터 예제**:
   ```cpp
   #include <iostream>

   void printValue(void* ptr, char type) {
       if (type == 'i') {
           std::cout << *static_cast<int*>(ptr) << std::endl;
       } else if (type == 'f') {
           std::cout << *static_cast<float*>(ptr) << std::endl;
       }
   }

   int main() {
       int x = 5;
       float y = 3.14f;

       printValue(&x, 'i'); // 5
       printValue(&y, 'f'); // 3.14
       
       return 0;
   }
   ```

## 설명
- **일반적인 오류**: `void` 함수에서 값을 반환하려고 하면 컴파일 오류가 발생한다. 사용자가 반환값을 기대할 때는 `void` 대신 해당 타입으로 변경해야 한다.
- **포인터 사용 주의**: `void*` 포인터는 타입이 지정되어 있지 않기 때문에, 이를 사용할 때는 반드시 적절한 타입으로 캐스팅해야 한다. 그렇지 않으면 데이터 접근 시 예기치 않은 결과를 초래할 수 있다.
- **참조와 비교**: `void`는 기본적으로 데이터가 없음을 나타내지만, 참조자(reference)와는 다르다. 참조자는 항상 유효한 객체를 가리키지만, `void*`는 가리키는 데이터의 타입을 명확히 할 필요가 있다.

## 한 문장 요약
C++에서 `void`는 함수의 반환값이 없음을 나타내거나 다양한 타입을 가리킬 수 있는 포인터로 사용된다.