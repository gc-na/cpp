<!--
Meta Description: # النقطة العائمة (Float) في C++ ## ملخص تعتبر "float" نوع بيانات في C++ يستخدم لتخزين الأعداد العشرية (الأعداد ذات الفاصلة العائمة) بدقة أقل مقارنةً ب...
Meta Keywords: float, استخدام, دقة, الأعداد, العشرية
-->

# النقطة العائمة (Float) في C++

## ملخص
تعتبر "float" نوع بيانات في C++ يستخدم لتخزين الأعداد العشرية (الأعداد ذات الفاصلة العائمة) بدقة أقل مقارنةً بـ "double"، مما يوفر استخدامًا فعالًا للذاكرة في التطبيقات التي تحتاج إلى معالجة الأعداد العشرية.

## الوثائق
### الغرض
تُستخدم "float" لتخزين القيم العشرية في C++، حيث يُعتبر خيارًا مناسبًا في حالة الحاجة إلى دقة متوسطة والحد من استهلاك الذاكرة. على عكس "double"، الذي يقدم دقة أعلى، فإن "float" يستخدم 4 بايت فقط لتخزين القيمة.

### الاستخدام
لتعريف متغير من نوع "float"، يُمكن استخدام الكلمة المفتاحية "float" متبوعة باسم المتغير. إليك صيغة الاستخدام الأساسية:

```cpp
float اسم_المتغير = القيمة;
```

### التفاصيل
- **النطاق**: عادةً ما يتراوح النطاق لــ "float" بين 1.17549e-38 إلى 3.40282e+38.
- **الدقة**: توفر "float" دقة تصل إلى 6-7 أرقام عشرية.
- **العمليات**: يمكن استخدام "float" في جميع العمليات الحسابية الأساسية مثل الجمع، الطرح، الضرب، والقسمة.

## الأمثلة
### مثال 1: تعريف واستخدام متغير float
```cpp
#include <iostream>
using namespace std;

int main() {
    float عدد = 5.75;
    cout << "القيمة هي: " << عدد << endl;
    return 0;
}
```

### مثال 2: العمليات الحسابية
```cpp
#include <iostream>
using namespace std;

int main() {
    float عدد1 = 5.0;
    float عدد2 = 2.0;
    float مجموع = عدد1 + عدد2;
    cout << "المجموع هو: " << مجموع << endl;
    return 0;
}
```

### مثال 3: دقة float
```cpp
#include <iostream>
#include <iomanip>
using namespace std;

int main() {
    float عدد = 1.123456789;
    cout << fixed << setprecision(10) << "القيمة هي: " << عدد << endl;
    return 0;
}
```

## الشرح
### الأخطاء الشائعة
- **فقدان الدقة**: عند استخدام "float"، قد يحدث فقدان دقة بسبب القدرة المحدودة على تمثيل الأرقام العشرية. يُفضل استخدام "double" إذا كانت الدقة مهمة.
- **التقريب**: نتيجة لبعض العمليات، قد يتم تقريب الأعداد مما يؤدي إلى نتائج غير متوقعة. يجب الحذر عند إجراء العمليات الحسابية على أعداد "float".

### ملاحظات إضافية
- **استخدام "float" في التطبيقات**: يُفضل استخدام "float" في التطبيقات التي تتطلب أداءً عالياً ولكن مع دقة أقل، مثل معالجة الصور والألعاب.
- **المقارنة مع الأنواع الأخرى**: يُفضل استخدام "float" على "double" عندما تكون الذاكرة محدودة أو عندما تكون الأداء هو الأولوية.

## ملخص جملة واحدة
"float" هو نوع بيانات في C++ يُستخدم لتخزين الأعداد العشرية بدقة متوسطة وفعالية في استخدام الذاكرة.