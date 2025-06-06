<!--
Meta Description: # استخدام جملة "do" في لغة C++ ## ملخص تعد جملة "do" جزءًا مهمًا من بناء جملة التكرار في لغة C++، حيث تُستخدم في تركيب جملة "do-while" لتنفيذ كتلة من ...
Meta Keywords: جملة, while, التعليمات, واحدة, شرط
-->

# استخدام جملة "do" في لغة C++

## ملخص
تعد جملة "do" جزءًا مهمًا من بناء جملة التكرار في لغة C++، حيث تُستخدم في تركيب جملة "do-while" لتنفيذ كتلة من التعليمات على الأقل مرة واحدة، ثم التحقق من شرط معين للاستمرار.

## الوثائق
### الغرض
تتيح جملة "do" للمبرمجين تنفيذ مجموعة من التعليمات بشكل متكرر حتى يتوقف شرط معين عن أن يكون صحيحًا. يتم تنفيذ كتلة التعليمات داخل الجملة "do" مرة واحدة على الأقل قبل التحقق من الشرط.

### الاستخدام
تتكون جملة "do-while" من كلمتي "do" و"while"، وتتخذ الشكل التالي:

```cpp
do {
    // تعليمات
} while (شرط);
```

- **تعليمات**: هي الكود الذي سيتم تنفيذه.
- **شرط**: هو تعبير منطقي يُستخدم لتحديد ما إذا كان يجب تكرار التنفيذ.

### التفاصيل
- يتم تنفيذ كتلة التعليمات داخل جملة "do" مرة واحدة على الأقل، بغض النظر عن قيمة الشرط.
- يلي جملة "do" كلمة "while" متبوعة بشرط، ويجب أن تكون جملة الشرط محاطة بأقواس.
- يجب أن تنتهي جملة "while" بفاصلة منقوطة.

## أمثلة
### مثال 1: استخدام بسيط لجملة "do-while"
```cpp
#include <iostream>
using namespace std;

int main() {
    int count = 1;
    do {
        cout << "العدد: " << count << endl;
        count++;
    } while (count <= 5);
    return 0;
}
```
**النتيجة**:
```
العدد: 1
العدد: 2
العدد: 3
العدد: 4
العدد: 5
```

### مثال 2: استخدام جملة "do-while" مع شرط
```cpp
#include <iostream>
using namespace std;

int main() {
    int number;
    do {
        cout << "أدخل رقمًا (0 للخروج): ";
        cin >> number;
    } while (number != 0);
    return 0;
}
```
**النتيجة**: سيستمر البرنامج في طلب الأرقام حتى يتم إدخال الرقم 0.

## الشرح
### الأخطاء الشائعة
- **عدم وضع فاصلة منقوطة**: إذا نسيت وضع فاصلة منقوطة بعد جملة "while"، سيؤدي ذلك إلى حدوث أخطاء في الترجمة.
- **عدم استخدام الأقواس**: في حالة وجود أكثر من تعليمة داخل كتلة "do"، يجب استخدام الأقواس لتحديد كتلة التعليمات بشكل صحيح.
  
### ملاحظات إضافية
- جملة "do-while" مفيدة عندما تريد تنفيذ التعليمات مرة واحدة على الأقل، مثل قراءة المدخلات من المستخدم.
- استخدم "do-while" بحذر في التطبيقات التي تتطلب التحقق من الشروط بشكل متكرر، حيث يمكن أن تؤدي الحلقات غير المنتهية إلى مشاكل في الأداء.

## ملخص جملة واحدة
تتيح جملة "do" في C++ تنفيذ مجموعة من التعليمات مرة واحدة على الأقل قبل التحقق من شرط معين للاستمرار في التنفيذ.