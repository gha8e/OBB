
Code Explanation

استيراد المكتبات:

cv2: للتعامل مع الكاميرا وعرض الإطارات.

YOLO من ultralytics: لتحميل النموذج واستخدامه.

تحميل النموذج:

model = YOLO("yolo11n-obb") يقوم بتحميل نموذج YOLO لاكتشاف الصناديق المحورية.

فتح الكاميرا:

cap = cv2.VideoCapture(0) يفتح كاميرا الويب.

بدء حلقة التقاط الفيديو:

قراءة الإطارات: success, frame = cap.read()

إذا نجحت القراءة، يتم تمرير الإطار إلى النموذج باستخدام results = model(frame).

يتم استخراج الإطار المعالج الذي يحتوي على الرسومات التوضيحية annotated_frame = results[0].plot().

يتم عرض الإطار باستخدام cv2.imshow("YOLO Inference", annotated_frame).

إيقاف البرنامج:

عند الضغط على 'q'، يتم كسر الحلقة والخروج.

تحرير الموارد:

cap.release() لإغلاق الكاميرا.

cv2.destroyAllWindows() لإغلاق النوافذ.
