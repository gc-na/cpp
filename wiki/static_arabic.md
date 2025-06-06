<!--
Meta Description: # الكلمة الرئيسية "static" في C++ ## ملخص الكلمة الرئيسية "static" في لغة البرمجة C++ تُستخدم لتحديد مدة حياة المتغيرات، وتحديد نطاق الوصول، وضمان أن ...
Meta Keywords: static, المتغيرات, int, count, يمكن
-->

# الكلمة الرئيسية "static" في C++

## ملخص
الكلمة الرئيسية "static" في لغة البرمجة C++ تُستخدم لتحديد مدة حياة المتغيرات، وتحديد نطاق الوصول، وضمان أن المتغيرات لا تُعاد تهيئتها في كل مرة يتم فيها استدعاء الدالة.

## الوثائق
تعتبر "static" من الكلمات الأساسية المهمة في C++. عند استخدامها، يمكن أن تتسبب في سلوك غير عادي إذا لم يتم فهمها بشكل صحيح. هناك ثلاث استخدامات رئيسية لـ "static":

1. **المتغيرات الثابتة داخل الدوال**: عند إعلان متغير داخل دالة باستخدام الكلمة الرئيسية "static"، يتم الاحتفاظ بقيمة المتغير بين استدعاءات الدالة. على عكس المتغيرات المحلية العادية، لا يتم إعادة تهيئة المتغير الثابت في كل مرة يتم فيها استدعاء الدالة.

2. **المتغيرات الثابتة في الكائنات**: عند الإعلان عن متغير ثابت داخل فئة (Class)، يمكن أن يُستخدم ذلك المتغير في جميع الكائنات (Instances) من تلك الفئة ويكون له قيمة واحدة مشتركة.

3. **التخزين الثابت للملفات**: يمكن أيضًا استخدام الكلمة "static" لتحديد أن وظيفة معينة أو متغير في ملف مصدر معين لا يجب أن يكون له نطاق وصول خارجي، مما يعني أنه يمكن استخدامه فقط داخل ذلك الملف.

## الأمثلة
### مثال 1: المتغير الثابت داخل الدالة
```cpp
#include <iostream>
using namespace std;

void function() {
    static int count = 0; // غير مهيأ في كل استدعاء
    count++;
    cout << "Count: " << count << endl;
}

int main() {
    function(); // Count: 1
    function(); // Count: 2
    function(); // Count: 3
    return 0;
}
```

### مثال 2: المتغير الثابت في الكائنات
```cpp
#include <iostream>
using namespace std;

class MyClass {
public:
    static int staticValue; // إعلان متغير ثابت
    void setValue(int value) {
        staticValue = value;
    }
};

int MyClass::staticValue = 0; // تعريف المتغير الثابت

int main() {
    MyClass obj1, obj2;
    obj1.setValue(10);
    cout << obj2.staticValue; // يطبع 10
    return 0;
}
```

### مثال 3: الوظيفة الثابتة في الملفات
```cpp
#include <iostream>
using namespace std;

static void myStaticFunction() {
    cout << "This is a static function." << endl;
}

int main() {
    myStaticFunction(); // يمكن استدعاءها هنا فقط
    return 0;
}
```

## الشرح
- **الأخطاء الشائعة**: من الأخطاء الشائعة استخدام "static" في سياقات غير مناسبة، مثل محاولة استخدام متغير ثابت في دالة بدون فهم أن قيمته ستستمر بين استدعاءات الدالة.
- **نقاط يجب أخذها بعين الاعتبار**: يجب أن تكون حذرًا عند استخدام المتغيرات الثابتة، لأنها قد تؤدي إلى سلوك غير متوقع إذا كانت تتغير عبر استدعاءات متعددة. كما أن استخدام "static" في الملفات يمكن أن يكون مفيدًا لإخفاء الوظائف، ولكنه يقلل من إمكانية إعادة استخدام الشيفرة.

## ملخص من جملة واحدة
تُستخدم الكلمة الرئيسية "static" في C++ لتحديد مدة حياة المتغيرات ونطاق الوصول، مما يتيح الحفاظ على القيم بين استدعاءات الدوال.