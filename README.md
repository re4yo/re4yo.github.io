```md
# دليل كامل لتسجيل الدخول إلى Git ورفع التعديلات على iOS  

## 1. تثبيت الأدوات المطلوبة  
قبل البدء، قم بتثبيت الأدوات التالية من **Sileo**:  
- **Git** → لإدارة المستودعات.  
- **NewTerm** → لتنفيذ الأوامر على الجهاز.  
- **حزمة a7m.dev** → تحتوي على سكربتات تسهل إدارة المستودع.  

### إضافة سورس `a7m.dev` إلى Sileo:  
1. افتح **Sileo** وانتقل إلى **Sources**.  
2. اضغط **Add** وأدخل الرابط التالي:  
   ```
   https://a7m.dev
   ```
3. قم بتثبيت السكربتات المطلوبة.  

---

## 2. تسجيل الدخول إلى Git  
افتح **NewTerm** ونفذ الأوامر التالية:  
```sh
git config --global user.name "YourGitHubUsername"
git config --global user.email "YourEmail@example.com"
git config --global credential.helper store
```
- استبدل `"YourGitHubUsername"` باسم المستخدم الخاص بك.  
- استبدل `"YourEmail@example.com"` بالبريد المرتبط بحسابك على GitHub.  
- الأمر `credential.helper store` يحفظ التوكن حتى لا تحتاج إلى إدخاله في كل مرة.  

---

## 3. توليد وحفظ التوكن من GitHub  
1. انتقل إلى **[GitHub Developer Settings](https://github.com/settings/tokens)**.  
2. اضغط على **"Generate new token (classic)"**.  
3. حدد الصلاحيات المطلوبة مثل `repo` و `workflow`.  
4. بعد إنشاء التوكن، افتح **NewTerm** ونفذ الأمر التالي لحفظه في الجهاز:  
   ```sh
   echo "https://YourGitHubUsername:YourGitHubToken@github.com" > ~/.git-credentials
   git config --global credential.helper 'store --file ~/.git-credentials'
   ```
   - استبدل `YourGitHubUsername` باسم المستخدم.  
   - استبدل `YourGitHubToken` بالتوكن الذي قمت بإنشائه.  
   - سيتم حفظ التوكن ولن تحتاج لإدخاله عند تنفيذ `git push`.  

---

## 4. موقع المستودع داخل الجهاز  
بعد استنساخ المستودع، سيكون موجودًا في المسار التالي:  
```
/var/mobile/YourRepository
```
يمكنك الانتقال إليه عبر **NewTerm** باستخدام:  
```sh
cd /var/mobile/YourRepository
```
بعد تعديل الملفات، تابع الخطوات التالية لرفع التعديلات.  

---

## 5. إضافة الملفات ورفع التعديلات إلى GitHub  
```sh
git add --all
git commit -m "Init"
git push
```
- `git add --all` → إضافة جميع الملفات الجديدة والمعدلة.  
- `git commit -m "Init"` → حفظ التعديلات مع رسالة توضيحية.  
- `git push` → رفع التعديلات إلى GitHub.  

---

## 6. تحديث المستودع في حال وجود تغييرات جديدة  
```sh
git pull origin main
```

---

## 7. شرح عملي بالفيديو  
لمشاهدة شرح عملي لجميع الخطوات، يمكنك متابعة الفيديو التالي:  
[**مشاهدة الفيديو**](https://mega.nz/file/MqhlASiQ#ihOzpDlEq8wCj6Q0qh0kywXxW765yt_Zh1GjuPRUEbk)
```

```sh
git pull origin main
```
```
video : https://mega.nz/file/MqhlASiQ#ihOzpDlEq8wCj6Q0qh0kywXxW765yt_Zh1GjuPRUEbk
```md
# Complete Guide to Logging into Git and Pushing Changes on iOS  

## 1. Install Required Tools  
Before starting, install the following tools from **Sileo**:  
- **Git** → For managing repositories.  
- **NewTerm** → For running commands on the device.  
- **a7m.dev package** → Contains scripts to simplify repository management.  

### Add the `a7m.dev` source to Sileo:  
1. Open **Sileo** and go to **Sources**.  
2. Click **Add** and enter the following URL:  
   ```
   https://a7m.dev
   ```
3. Install the necessary scripts.  

---

## 2. Log in to Git  
Open **NewTerm** and run the following commands:  
```sh
git config --global user.name "YourGitHubUsername"
git config --global user.email "YourEmail@example.com"
git config --global credential.helper store
```
- Replace `"YourGitHubUsername"` with your GitHub username.  
- Replace `"YourEmail@example.com"` with the email linked to your GitHub account.  
- The `credential.helper store` command saves the token so you don't need to enter it every time.  

---

## 3. Generate and Save GitHub Token  
1. Go to **[GitHub Developer Settings](https://github.com/settings/tokens)**.  
2. Click **"Generate new token (classic)"**.  
3. Select the required permissions, such as `repo` and `workflow`.  
4. After generating the token, open **NewTerm** and run the following command to save it:  
   ```sh
   echo "https://YourGitHubUsername:YourGitHubToken@github.com" > ~/.git-credentials
   git config --global credential.helper 'store --file ~/.git-credentials'
   ```
   - Replace `YourGitHubUsername` with your username.  
   - Replace `YourGitHubToken` with the token you generated.  
   - The token will be saved, so you won’t need to enter it when running `git push`.  

---

## 4. Repository Location on Device  
After cloning the repository, it will be stored at:  
```
/var/mobile/YourRepository
```
You can navigate to it in **NewTerm** using:  
```sh
cd /var/mobile/YourRepository
```
After modifying your files, proceed with the following steps to push the changes.  

---

## 5. Add Files and Push Changes to GitHub  
```sh
git add --all
git commit -m "Init"
git push
```
- `git add --all` → Adds all new and modified files.  
- `git commit -m "Init"` → Saves changes with a commit message.  
- `git push` → Pushes changes to GitHub.  

---

## 6. Update the Repository if New Changes Exist  
```sh
git pull origin main
```
```
