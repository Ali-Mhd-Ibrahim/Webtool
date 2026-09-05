# 🇸🇾 MTN Syria — كتيب الخدمات التدريبي

موقع تعريفي تفاعلي يُعرض على **GitHub Pages** لتعريف المتدربين الجدد في MTN Syria
بجميع الخدمات المتوفرة، مع **شرح نصي تفصيلي** و**فيديو توضيحي** لكل خدمة.

> موقع ثابت 100% — HTML / CSS / JavaScript فقط، بدون أي خادم أو قاعدة بيانات.

---

## ✨ المميزات

| الميزة | الوصف |
|--------|-------|
| 🌐 **ثنائي اللغة** | عربي (RTL) + إنجليزي (LTR) مع زر تبديل فوري |
| 🌙 **الوضع الداكن** | Dark / Light Mode مع حفظ التفضيل |
| 🔍 **بحث متقدم** | بحث في العنوان والشرح والتصنيف (Ctrl+K) |
| 🗂️ **تصنيفات** | شريط جانبي + شريط شرائح للجوال |
| 📄 **صفحة لكل خدمة** | رابط خاص مثل `#/service/sim-replacement` |
| 🎬 **الفيديو** | يدعم YouTube + Google Drive + ملف محلي MP4 |
| 📊 **تتبع التقدم**

https://github.com/user-attachments/assets/5f84e5c9-056a-4b89-9905-4f660d59dcd0

 | المتدرب يعلّم «تمت المشاهدة» ويُحتسب تقدمه |
| 👁 **عداد المشاهدات** | يُحسب لكل صفحة خدمة (localStorage) |
| 🖨️ **تصدير PDF** | زر طباعة يصدّر صفحة الخدمة كـ PDF |
| 📱 **متجاوب** | يعمل على الجوال واللوحي والكمبيوتر |

---

## 📁 هيكل المشروع

```
├── index.html          # الصفحة الرئيسية
├── css/
│   └── style.css      # التصميم (RTL/LTR + Dark/Light)
├── js/
│   ├── app.js         # الراوتر + عرض الخدمات + البحث + الفيديو
│   ├── i18n.js        # نصوص اللغتين
│   └── theme.js       # الوضع الداكن/الفاتح
├── data/
│   └── services.js    # ⭐ بيانات الخدمات — عدّله لإضافة خدماتك
├── assets/
│   └── videos/        # ضع ملفات الفيديو هنا (اختياري)
└── README.md
```

---

## ⭐ إضافة خدمة جديدة (الأهم)

افتح ملف **`data/services.js`** وأضف كائنًا جديدًا لقائمة `SERVICES_DATA`:

```js
{
  id: "service-id",          // معرّف فريد باللاتيني (يُستخدم في الرابط)
  category: "c-mobile",      // معرّف التصنيف من CATEGORIES
  icon: "📱",                // أي أيقونة emoji
  title_ar: "العنوان بالعربية",
  title_en: "English Title",
  summary_ar: "ملخص قصير بالعربية",
  summary_en: "Short English summary",
  description_ar: "الشرح التفصيلي بالعربية \n\n فقرة ثانية عبر سطر فارغ",
  description_en: "Detailed English description",
  steps_ar: ["خطوة 1", "خطوة 2", "خطوة 3"],
  steps_en: ["Step 1", "Step 2", "Step 3"],
  video_url: "",             // راجع الأسفل
  time_ar: "10 دقائق"        // الزمن المتوقع (اختياري)
}
```

**أضف/عدّل الفئات** في قائمة `CATEGORIES`:

```js
{ id: "c-mobile", icon: "📱", title_ar: "خطوط الجوال", title_en: "Mobile Lines" }
```

> ✅ بعد التعديل أعد تحميل الصفحة وستظهر الخدمة فورًا.

---

## 🎬 إضافة الفيديو

| المصدر | مثال | ملاحظة |
|--------|------|--------|
| YouTube | `https://www.youtube.com/watch?v=VIDEO_ID` | الأنسب (مجاني + سريع) — ارفع الفيديو بصيغة **Unlisted** |
| YouTube | `https://youtu.be/VIDEO_ID` | صيغة مختصرة |
| Google Drive | `https://drive.google.com/file/d/FILE_ID/view` | رفع خاص، قد يحجب أحيانًا |
| ملف محلي | `assets/videos/service-name.mp4` | ارفعه مع المشروع بجانب الكود |

**توصية:** ارفع فيديوهاتك على YouTube **(غير مدرج - Unlisted)** وضع الرابط،
هذا الأدوم من ناحية السرعة والحجم. **لا ترفع ملفات فيديو كبيرة على GitHub**
(الحد الأقصى للملف 100MB).

إذا تركت `video_url` فارغًا (`""`) سيُخفى قسم الفيديو تلقائيًا.

---

## 🚀 النشر على GitHub Pages

1. أنشئ حساب على [GitHub](https://github.com) إن لم يكن لديك.
2. أنشئ **Repository جديد** باسم مثل `mtn-training-guide` (Public).
3. ارفع مجلد المشروع كاملًا إلى المستودع:
   ```bash
   git init
   git add .
   git commit -m "MTN Syria training guide"
   git branch -M main
   git remote add origin https://github.com/<اسمك>/mtn-training-guide.git
   git push -u origin main
   ```
4. افتح: **Settings ← Pages ← Deploy from a branch ← Main (أو master) ← / (root) ← Save**.
5. سيصبح موقعك متاحًا خلال دقيقة على:
   ```
   https://<اسمك>.github.io/mtn-training-guide/
   ```

> 💡 موقع ثابت لا يحتاج أي إعدادات إضافية — لا دالة خادم ولا بناء.

---

## 💻 التشغيل محليًا (للتجربة)

افتح `index.html` مباشرة في المتصفح، أو اعمل له `serve` محلي:

```bash
# بأي طريقة:
python -m http.server 8000
# ثم افتح http://localhost:8000
```

---

## 🧠 ملاحظات تقنية

- **التقدم والمشاهدات** تُحفظ في `localStorage` — خاصة بكل متصفح/جهاز.
- **الخطوط**: Cairo للعربية و Inter للإنجليزية (من Google Fonts).
- **الألوان**: هوية MTN — أصفر `#FFCB00` + أسود `#000000`.

## 📄 الترخيص

استخدم داخليًا لأغراض التدريب في MTN Syria. أُعِد بناءً على احتياجات فريق التدريب.
