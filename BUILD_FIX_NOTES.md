# إصلاح خطأ GitHub Actions

تم إصلاح مشكلتين ظهرتا في البناء:
- حذف اعتماد Firebase Database KTX غير المستخدم، لأن Firebase BoM الحديثة لم تعد توفر وحدات KTX بالطريقة القديمة.
- إضافة مستودع JitPack المطلوب لاعتماد LiveKit Android على audioswitch.

أعد رفع/استبدال الملفات التالية في GitHub:
android/app/build.gradle
android/build.gradle
android/settings.gradle

ثم أعد تشغيل Actions.
