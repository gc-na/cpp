# [لينكس] C Shell (csh) tmux الاستخدام: إدارة الجلسات الطرفية

## نظرة عامة
يعتبر أمر tmux أداة قوية لإدارة الجلسات الطرفية، حيث يتيح للمستخدمين تشغيل عدة جلسات طرفية في نافذة واحدة، مما يسهل تنظيم العمل والتبديل بين المهام المختلفة.

## الاستخدام
يمكن استخدام الأمر tmux بكتابة الصيغة الأساسية التالية:

```bash
tmux [options] [arguments]
```

## الخيارات الشائعة
- `new`: لإنشاء جلسة جديدة.
- `attach`: للاتصال بجلسة موجودة.
- `detach`: لفصل الجلسة الحالية.
- `list-sessions`: لعرض جميع الجلسات المتاحة.
- `kill-session`: لإنهاء جلسة معينة.

## أمثلة شائعة
- لإنشاء جلسة جديدة:
  ```bash
  tmux new -s mysession
  ```

- للاتصال بجلسة موجودة:
  ```bash
  tmux attach -t mysession
  ```

- لفصل الجلسة الحالية:
  ```bash
  Ctrl + b ثم d
  ```

- لعرض جميع الجلسات:
  ```bash
  tmux list-sessions
  ```

- لإنهاء جلسة معينة:
  ```bash
  tmux kill-session -t mysession
  ```

## نصائح
- استخدم الاختصارات مثل `Ctrl + b` متبوعة بمفتاح آخر لتسهيل التنقل بين الأوامر.
- قم بتسمية الجلسات بشكل واضح لتسهيل التعرف عليها لاحقًا.
- احفظ الجلسات النشطة لتتمكن من العودة إليها بسهولة بعد فصلها.