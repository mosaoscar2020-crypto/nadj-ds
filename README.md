# LiveScreen — Ultra Speed / Single Upload / SFU

هذه النسخة تغيّر البنية إلى SFU باستخدام LiveKit:
S9+ يرفع **مسار فيديو واحد فقط** إلى LiveKit، وLiveKit يوزعه على جميع المشاهدين.

## لماذا LiveKit؟
لأنه SFU مخصص لـ WebRTC منخفض التأخير. الهاتف لا يرسل نسخة منفصلة لكل مشاهد.

## المطلوب قبل التشغيل
تحتاج LiveKit Cloud أو LiveKit Server خاص بك.
ستحصل على:
- LIVEKIT_URL (مثال wss://...)
- LIVEKIT_API_KEY
- LIVEKIT_API_SECRET

لا تضع API_SECRET داخل Android أو GitHub.

## Firebase
ملف google-services.json الموجود داخل android/app مأخوذ من ملف Firebase الذي زودتني به.
Firebase يمكن إبقاؤه للمصادقة/إدارة الغرفة، لكن الفيديو نفسه لا يمر عبر Firebase.

## Android
التطبيق يطلب MediaProjection ثم ينشر شاشة الهاتف كـ video track فقط، بدون microphone/audio.
إعدادات الهدف:
- 60 FPS
- 720p
- H.264 عند توفر hardware encoder
- bitrate منخفض نسبيًا للأولوية على التأخير
- لا يوجد مسار صوت

## Web
صفحة المشاهد تتصل بغرفة LiveKit وتستقبل screen-share track.

## Token server
يجب أن يعطي token قصير العمر للمضيف والمشاهد. ضع LiveKit API key/secret في متغيرات بيئة على الخادم فقط.
