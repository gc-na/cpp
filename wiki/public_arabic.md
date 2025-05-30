<!--
Meta Description: # الوصول العام (public) في C++ ## ملخص الكلمة المفتاحية "public" في C++ تُستخدم لتحديد مستوى الوصول إلى الأعضاء (الخصائص والدوال) داخل الصفوف (classes...
Meta Keywords: public, الوصول, الأعضاء, إلى, يمكن
-->

# الوصول العام (public) في C++

## ملخص
الكلمة المفتاحية "public" في C++ تُستخدم لتحديد مستوى الوصول إلى الأعضاء (الخصائص والدوال) داخل الصفوف (classes). الأعضاء المعنونة بـ "public" يمكن الوصول إليهم من أي جزء من البرنامج.

## الوثائق
### الغرض
تُعتبر "public" جزءًا من نظام التحكم في الوصول في C++. يتيح لك تحديد ما إذا كان يمكن الوصول إلى الأعضاء من خارج الصف أو لا. تتضمن مستويات الوصول الأخرى "private" و "protected".

### الاستخدام
عند تعريف صف، يمكنك الإعلان عن الأعضاء كـ "public" لتوفير واجهة برمجية تتيح للمستخدمين الوصول إلى هذه الأعضاء مباشرة. إذا لم يتم تحديد مستوى الوصول، فإن الأعضاء في الصف تكون بشكل افتراضي "private".

### التفاصيل
- **الترتيب**: يمكن وضع الكلمة المفتاحية "public" في أي مكان داخل تعريف الصف، ولكن من الشائع وضعها في بداية القسم الذي يحتوي على الأعضاء العامة.
- **الوصول**: يمكن للبرامج الخارجية، الكائنات، أو الصفوف المشتقة الوصول إلى الأعضاء العامة.

## الأمثلة
### مثال بسيط
```cpp
#include <iostream>
using namespace std;

class MyClass {
public:
    int myNumber; // عضو عام

    void display() { // دالة عامة
        cout << "My number is: " << myNumber << endl;
    }
};

int main() {
    MyClass obj;
    obj.myNumber = 10; // الوصول إلى العضو العام
    obj.display(); // استدعاء الدالة العامة
    return 0;
}
```

### مثال على الصفوف المشتقة
```cpp
#include <iostream>
using namespace std;

class Base {
public:
    void display() {
        cout << "Hello from Base class." << endl;
    }
};

class Derived : public Base {
public:
    void show() {
        cout << "Hello from Derived class." << endl;
    }
};

int main() {
    Derived obj;
    obj.display(); // يمكن الوصول إلى الدالة العامة من الصف الأساسي
    obj.show();
    return 0;
}
```

## الشرح
### الأخطاء الشائعة
1. **عدم استخدام الكلمة المفتاحية "public"**: إذا كنت بحاجة إلى أن يكون العضو متاحًا خارج الصف، فتأكد من وضع الكلمة المفتاحية "public" قبل تعريف العضو.
2. **الخلط بين مستويات الوصول**: يُفضل فهم الاختلاف بين "public" و "private" و "protected" لتجنب مشكلات في التصميم.
3. **إنشاء واجهة معقدة**: على الرغم من أنه يمكن جعل جميع الأعضاء "public"، إلا أنه من الأفضل تحديد الأعضاء العامة فقط عند الحاجة لتقليل التعقيد.

## ملخص جملة واحدة
الكلمة المفتاحية "public" في C++ تُستخدم لتحديد الأعضاء التي يمكن الوصول إليها من خارج الصف، مما يسهل التفاعل مع الكائنات.