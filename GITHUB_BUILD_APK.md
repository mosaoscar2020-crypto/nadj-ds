# بناء APK عبر GitHub Actions

1. أنشئ مستودع GitHub جديد.
2. ارفع **محتويات هذا المجلد** إلى المستودع (بحيث يظهر `.github/workflows/build-apk.yml` في الجذر).
3. افتح تبويب **Actions**.
4. اختر **Build Android APK**.
5. اضغط **Run workflow**.
6. انتظر انتهاء البناء.
7. افتح نتيجة التشغيل، ثم قسم **Artifacts**.
8. نزّل `LiveScreen-debug-apk.zip` وافتحه لتحصل على `app-debug.apk`.

مهم:
- المشروع يحتوي `android/app/google-services.json` الذي زودتني به.
- لا تضع LiveKit API Secret في GitHub.
- الـDevelopment Token Server الحالي مخصص للتطوير/الاختبار.
