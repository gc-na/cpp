<!--
Meta Description: # استخدام الـ "union" في C++ ## ملخص الـ "union" في لغة C++ هو نوع بيانات خاص يسمح بتخزين عدة أنواع من البيانات في نفس موقع الذاكرة. يمكن أن يكون مفيد...
Meta Keywords: union, الـ, student, data, int
-->

# استخدام الـ "union" في C++

## ملخص
الـ "union" في لغة C++ هو نوع بيانات خاص يسمح بتخزين عدة أنواع من البيانات في نفس موقع الذاكرة. يمكن أن يكون مفيدًا في حالات معينة حيث نحتاج إلى تخزين نوع واحد من البيانات في وقت معين، مما يساعد على توفير الذاكرة.

## الوثائق
يستخدم الـ "union" لتعريف مجموعة من المتغيرات التي تشترك في نفس مساحة الذاكرة. على الرغم من أن الـ "union" يمكن أن يحتوي على متغيرات من أنواع مختلفة، إلا أنه يمكن تخزين نوع واحد فقط في وقت واحد. يتم تحديد حجم الـ "union" بناءً على أكبر نوع بيانات موجود فيه.

### تعريف الـ union
يمكن تعريف الـ "union" بنفس طريقة تعريف الهيكل (`struct`). إليك الصيغة العامة لتعريف الـ "union":

```cpp
union UnionName {
    Type1 member1;
    Type2 member2;
    ...
};
```

### استخدام الـ union
لتعريف واستخدام الـ "union"، يمكنك القيام بما يلي:

```cpp
#include <iostream>
using namespace std;

union Data {
    int intValue;
    float floatValue;
    char charValue;
};

int main() {
    Data data;
    data.intValue = 5;
    cout << "Int Value: " << data.intValue << endl;

    data.floatValue = 3.14; // سيؤدي إلى الكتابة فوق intValue
    cout << "Float Value: " << data.floatValue << endl;

    return 0;
}
```

### ملاحظات هامة
- يمكن أن يؤدي استخدام الـ "union" بشكل غير صحيح إلى تلف البيانات، حيث إن الكتابة في أحد الأعضاء ستؤدي إلى فقدان البيانات المدخلة في الأعضاء الأخرى.
- يجب أن نكون حذرين عند استخدام الـ "union" مع الكائنات التي تحتوي على دوال بناء أو تدمير، فقد يؤدي ذلك إلى سلوك غير متوقع.

## أمثلة
### مثال بسيط لاستخدام الـ union
```cpp
#include <iostream>
using namespace std;

union Student {
    int id;
    float gpa;
};

int main() {
    Student student;
    student.id = 123;
    cout << "Student ID: " << student.id << endl;

    student.gpa = 3.75; // الكتابة فوق الـ id
    cout << "Student GPA: " << student.gpa << endl;
    return 0;
}
```

### مثال مع كائنات
```cpp
#include <iostream>
using namespace std;

union Value {
    int intVal;
    double doubleVal;
};

int main() {
    Value myValue;
    myValue.intVal = 10;
    cout << "Integer: " << myValue.intVal << endl;

    myValue.doubleVal = 20.5; // الكتابة فوق intVal
    cout << "Double: " << myValue.doubleVal << endl; // القيمة السابقة لـ intVal مفقودة
    return 0;
}
```

## ملخص جملة واحدة
الـ "union" في C++ هو نوع بيانات يتيح تخزين أنواع متعددة في نفس موقع الذاكرة، مما يساعد على توفير الذاكرة، ولكن يجب الحذر عند استخدامه لتجنب فقدان البيانات.