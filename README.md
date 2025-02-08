شرح كامل لتسجيل الدخول إلى Git ورفع التعديلات على iOS

1- تحميل الأدوات المطلوبة

قبل البدء، يجب تثبيت الأدوات التالية من Sileo:

	•	Git → لإدارة المستودعات.
	•	NewTerm → لتنفيذ الأوامر داخل الجهاز.
‎	•	حزمة a7m.dev → تحتوي على سكربتات تسهل إدارة المستودع.

إضافة السورس a7m.dev إلى Sileo:
افتح Sileo وانتقل إلى Sources ثم اضغط Add وأضف الرابط التالي:

https://a7m.dev

ثم قم بتحميل السكربتات المساعدة.

2- تسجيل الدخول إلى Git

افتح NewTerm ونفذ الأوامر التالية:

git config --global user.name "YourGitHubUsername"
git config --global user.email "YourEmail@example.com"
git config --global credential.helper store

	•	استبدل "YourGitHubUsername" باسم المستخدم الخاص بك.
	•	استبدل "YourEmail@example.com" بالبريد المرتبط بحسابك على GitHub.
	•	الأمر credential.helper store سيحفظ التوكن حتى لا تحتاج إلى إدخاله في كل مرة.

3- توليد وحفظ التوكن من GitHub

	1.	انتقل إلى GitHub Developer Settings.
	2.	اضغط على “Generate new token (classic)”.
	3.	حدد الصلاحيات المطلوبة مثل repo و workflow.
	4.	بعد إنشاء التوكن، افتح NewTerm ونفذ الأمر التالي لحفظه في الجهاز:

echo "https://YourGitHubUsername:YourGitHubToken@github.com" > ~/.git-credentials
git config --global credential.helper 'store --file ~/.git-credentials'

	•	استبدل YourGitHubUsername باسم المستخدم.
	•	استبدل YourGitHubToken بالتوكن الذي قمت بإنشائه.
	•	سيتم حفظ التوكن ولن تحتاج لإدخاله عند تنفيذ git push.

4- موقع السورس داخل الجهاز

بعد استنساخ المستودع، سيكون ملف السورس موجودًا في:

/var/mobile/YourRepository

يمكنك الدخول إليه عبر NewTerm باستخدام:

cd /var/mobile/YourRepository

بعد التعديل على الملفات، تابع الخطوات التالية لرفعها.

5- إضافة الملفات ورفع التعديلات إلى GitHub

git add --all
git commit -m "Init"
git push

	•	git add --all → إضافة جميع الملفات الجديدة والمعدلة.
	•	git commit -m "Init" → حفظ التعديلات مع رسالة توضيحية.
	•	git push → رفع التعديلات إلى GitHub.

6- تحديث المستودع في حال وجود تغييرات جديدة

git pull origin main
