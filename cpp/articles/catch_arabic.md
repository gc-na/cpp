<!--
Meta Description: # استخدام جملة "catch" في لغة C++ ## ملخص تعتبر جملة "catch" جزءاً أساسياً من معالجة الاستثناءات في لغة C++. تُستخدم لالتقاط الأخطاء التي قد تحدث أثنا...
Meta Keywords: catch, جملة, std, استثناء, استخدام
-->

# استخدام جملة "catch" في لغة C++

## ملخص
تعتبر جملة "catch" جزءاً أساسياً من معالجة الاستثناءات في لغة C++. تُستخدم لالتقاط الأخطاء التي قد تحدث أثناء تنفيذ البرنامج، مما يسمح للمطور بالتعامل مع هذه الأخطاء بشكل مناسب.

## الوثائق
جملة "catch" تُستخدم مع جملة "try" في C++ لإنشاء كتلة معالجة استثناءات. عند استخدام "try"، يتم وضع الكود الذي قد يُثير استثناءً داخل هذه الكتلة. إذا حدث استثناء، يتم تمرير التحكم إلى كتلة "catch" المناسبة.

### الغرض
الغرض من استخدام "catch" هو التعامل مع الأخطاء والاستثناءات بطريقة منظمة دون التسبب في انهيار البرنامج.

### الاستخدام
تستخدم جملة "catch" كالتالي:

```cpp
try {
    // كود قد يثير استثناء
} catch (نوع_الاستثناء& e) {
    // معالجة الاستثناء
}
```

يمكن لـ "catch" التقاط أنواع مختلفة من الاستثناءات، حيث يمكن تحديد نوع الاستثناء في أقواس الجملة.

### التفاصيل
- يمكن أن تحتوي جملة "catch" على عدة كتل، كل واحدة منها تتعامل مع نوع مختلف من الاستثناءات.
- يُفضل أن يتم وضع جملة "catch" العامة في نهاية قائمة كتل "catch" لتجنب التقاط استثناءات غير محددة قبل وصولها إلى كتل أكثر تحديدًا.

## الأمثلة
### مثال 1: معالجة استثناء بسيط
```cpp
#include <iostream>
#include <stdexcept>

int main() {
    try {
        throw std::runtime_error("خطأ في وقت التشغيل");
    } catch (std::runtime_error& e) {
        std::cout << "تم القبض على الاستثناء: " << e.what() << std::endl;
    }
    return 0;
}
```

### مثال 2: استخدام كتل متعددة من "catch"
```cpp
#include <iostream>
#include <stdexcept>

int main() {
    try {
        throw 20; // استثناء من نوع int
    } catch (int e) {
        std::cout << "استثناء من النوع int: " << e << std::endl;
    } catch (std::exception& e) {
        std::cout << "استثناء آخر: " << e.what() << std::endl;
    }
    return 0;
}
```

## الشرح
### الأخطاء الشائعة
- **عدم مطابقة نوع الاستثناء:** تأكد من أن نوع الاستثناء في جملة "catch" يتطابق مع النوع المثار في جملة "try".
- **تجاهل الاستثناءات:** قد يؤدي عدم استخدام جملة "catch" إلى انهيار البرنامج بدون معالجة الأخطاء.
- **استخدام كتل "catch" غير محددة مسبقاً:** إذا وضعت كتلة "catch" عامة قبل الكتل الأكثر تحديدًا، قد لا يتم تشغيل الكتل المحددة.

## ملخص جملة واحدة
تُستخدم جملة "catch" في C++ لالتقاط ومعالجة الاستثناءات، مما يساعد على تحسين استقرار البرنامج.