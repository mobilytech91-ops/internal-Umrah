# 🕋 تطبيق ميقات إن - العمرة الداخلية
## الفهرس الرئيسي - Master Index

---

## 📚 نظرة عامة

هذا الدليل الشامل يحتوي على **الفلو الكامل** لتطبيق العمرة الداخلية (Internal Umrah App) المبني بتقنية **Flutter**.

التطبيق يتكون من **3 أنظمة رئيسية** داخل تطبيق واحد:
- 🧳 **تطبيق المستخدم** - للمعتمرين والزوار
- 🏢 **تطبيق الشركات** - لمنظمي الرحلات
- 👔 **تطبيق الإدارة** - للمراقبة والتحكم

بالإضافة إلى:
- 🔄 **الصفحات المشتركة** - تستخدم في جميع الأنظمة

---

## 📋 هيكل الوثائق

### [📱 01_USER_APP_FLOW.md](./01_USER_APP_FLOW.md)
**تطبيق المستخدم العادي (User App)**

#### المحتويات:
- ✅ صفحات التسجيل والدخول (7 صفحات)
- ✅ الصفحة الرئيسية والبحث (6 صفحات)
- ✅ تفاصيل الرحلات (5 صفحات)
- ✅ الحجز والدفع (6 صفحات)
- ✅ إدارة الرحلات (4 صفحات)
- ✅ التقييمات (3 صفحات)
- ✅ الملف الشخصي (8 صفحات)

**إجمالي:** ~39 صفحة رئيسية + صفحات فرعية

---

### [🏢 02_COMPANY_APP_FLOW.md](./02_COMPANY_APP_FLOW.md)
**تطبيق الشركات (Organizer Dashboard)**

#### المحتويات:
- ✅ التسجيل والدخول (3 صفحات)
- ✅ لوحة التحكم الرئيسية (1 صفحة)
- ✅ إدارة الرحلات (6 صفحات)
- ✅ إدارة الحجوزات (4 صفحات)
- ✅ إدارة الرحلة المباشرة (3 صفحات)
- ✅ التقارير والإحصائيات (4 صفحات)
- ✅ إدارة الموارد (5 صفحات)
- ✅ الإعدادات والملف (3 صفحات)

**إجمالي:** ~29 صفحة رئيسية

---

### [👔 03_ADMIN_APP_FLOW.md](./03_ADMIN_APP_FLOW.md)
**تطبيق الإدارة (Admin Panel)**

#### المحتويات:
- ✅ تسجيل الدخول (1 صفحة)
- ✅ لوحة التحكم الرئيسية (1 صفحة)
- ✅ إدارة الشركات (4 صفحات)
- ✅ إدارة المستخدمين (3 صفحات)
- ✅ إدارة الرحلات والمحتوى (3 صفحات)
- ✅ التقارير المالية (3 صفحات)
- ✅ إدارة النظام (4 صفحات)

**إجمالي:** ~19 صفحة رئيسية

---

### [🔄 04_SHARED_SCREENS.md](./04_SHARED_SCREENS.md)
**الصفحات المشتركة (Shared Screens)**

#### المحتويات:
- ✅ صفحات المساعدة والدعم (4 صفحات)
- ✅ صفحات قانونية (3 صفحات)
- ✅ صفحات إعلامية (3 صفحات)
- ✅ صفحات الخرائط (2 صفحات)
- ✅ صفحات الإشعارات (2 صفحات)
- ✅ صفحات الطوارئ (2 صفحات)
- ✅ Widgets مشتركة

**إجمالي:** ~16 صفحة مشتركة

---

## 📊 إحصائيات المشروع

| المكون | عدد الصفحات | الحالة |
|--------|-------------|--------|
| تطبيق المستخدم | 39+ صفحة | ✅ موثق |
| تطبيق الشركات | 29+ صفحة | ✅ موثق |
| تطبيق الإدارة | 19+ صفحة | ✅ موثق |
| الصفحات المشتركة | 16+ صفحة | ✅ موثق |
| **المجموع الكلي** | **103+ صفحة** | ✅ جاهز |

---

## 🎯 كيفية استخدام هذه الوثائق

### 1️⃣ للمطورين (Developers)
```
استخدم المسارات المحددة في كل ملف لإنشاء:
- هيكل المجلدات (Folder Structure)
- تسمية الملفات (File Naming)
- Navigation Routes
```

### 2️⃣ لمصممي الواجهات (UI/UX Designers)
```
استخدم الفلو المرسوم لفهم:
- User Journey
- Screen Transitions
- Interactive Elements
```

### 3️⃣ لمديري المشاريع (Project Managers)
```
استخدم القوائم المفصلة لـ:
- تقدير الوقت (Time Estimation)
- توزيع المهام (Task Distribution)
- متابعة التقدم (Progress Tracking)
```

---

## 🗂️ هيكل المجلدات المقترح (Flutter)

```
lib/
├── main.dart
├── app.dart
│
├── core/
│   ├── constants/
│   ├── theme/
│   ├── utils/
│   └── services/
│
├── models/
│   ├── user.dart
│   ├── trip.dart
│   ├── booking.dart
│   ├── company.dart
│   └── ...
│
├── providers/ (أو blocs/)
│   ├── auth_provider.dart
│   ├── trip_provider.dart
│   ├── booking_provider.dart
│   └── ...
│
├── screens/
│   ├── user/           → 01_USER_APP_FLOW.md
│   │   ├── auth/
│   │   ├── home/
│   │   ├── search/
│   │   ├── trips/
│   │   ├── booking/
│   │   └── profile/
│   │
│   ├── company/        → 02_COMPANY_APP_FLOW.md
│   │   ├── auth/
│   │   ├── dashboard/
│   │   ├── trips/
│   │   ├── bookings/
│   │   └── reports/
│   │
│   ├── admin/          → 03_ADMIN_APP_FLOW.md
│   │   ├── auth/
│   │   ├── dashboard/
│   │   ├── companies/
│   │   ├── users/
│   │   └── reports/
│   │
│   └── shared/         → 04_SHARED_SCREENS.md
│       ├── support/
│       ├── legal/
│       ├── notifications/
│       └── emergency/
│
├── widgets/
│   ├── common/
│   ├── cards/
│   ├── buttons/
│   └── dialogs/
│
├── navigation/
│   ├── app_router.dart
│   ├── user_routes.dart
│   ├── company_routes.dart
│   └── admin_routes.dart
│
└── data/
    ├── repositories/
    ├── api/
    └── local/
```

---

## 🔗 روابط سريعة

### المسارات الرئيسية (Main Flows)

#### 1. User Journey - رحلة المستخدم
```
Welcome → Login → OTP → Home → Search → Trip Details → Booking → Payment → Confirmation → Tracking → Rating
```
📄 **التفاصيل:** [01_USER_APP_FLOW.md](./01_USER_APP_FLOW.md)

---

#### 2. Company Journey - رحلة الشركة
```
Company Login → Dashboard → Add Trip → Manage Bookings → Start Trip → Live Tracking → End Trip → Reports
```
📄 **التفاصيل:** [02_COMPANY_APP_FLOW.md](./02_COMPANY_APP_FLOW.md)

---

#### 3. Admin Journey - رحلة الإدارة
```
Admin Login → Dashboard → Approve Companies → Review Trips → Monitor System → Financial Reports
```
📄 **التفاصيل:** [03_ADMIN_APP_FLOW.md](./03_ADMIN_APP_FLOW.md)

---

## 🎨 قواعد التصميم

### الألوان الرئيسية
```dart
Primary Color: #1B5E20 (أخضر إسلامي)
Secondary Color: #FFB300 (ذهبي)
Accent Color: #00838F (تركواز)
Background: #FAFAFA
Text Primary: #212121
Text Secondary: #757575
Error: #D32F2F
Success: #388E3C
```

### الخطوط
```
العربية: Cairo / Tajawal
English: Roboto / Inter
```

### الأحجام
```
Heading 1: 24sp
Heading 2: 20sp
Heading 3: 18sp
Body: 16sp
Caption: 14sp
Small: 12sp
```

---

## 📱 أولويات التطوير

### المرحلة الأولى - MVP (8 أسابيع)
**الأساسيات الضرورية**

#### Week 1-2: Authentication & User Setup
- [ ] Splash & Welcome
- [ ] Login/Register (User)
- [ ] OTP Verification
- [ ] Basic Profile

#### Week 3-4: Core User Features
- [ ] Home Screen
- [ ] Search & Filters
- [ ] Trip Details
- [ ] Basic Booking

#### Week 5-6: Company Dashboard
- [ ] Company Login
- [ ] Add/Edit Trips
- [ ] View Bookings
- [ ] Basic Reports

#### Week 7-8: Admin & Payment
- [ ] Admin Login
- [ ] Approve Companies
- [ ] Payment Integration
- [ ] Testing & Bug Fixes

---

### المرحلة الثانية - Core Features (6 أسابيع)
**الميزات الأساسية**

#### Week 9-10: Booking & Tracking
- [ ] Complete Booking Flow
- [ ] Family Booking
- [ ] Live GPS Tracking
- [ ] Trip Management

#### Week 11-12: Reviews & Ratings
- [ ] Multi-level Rating System
- [ ] Reviews Management
- [ ] Company Performance

#### Week 13-14: Advanced Features
- [ ] Loyalty Points
- [ ] Favorites
- [ ] Notifications System
- [ ] Maps Integration

---

### المرحلة الثالثة - Advanced (4 أسابيع)
**الميزات المتقدمة**

#### Week 15-16: Analytics & Reports
- [ ] User Analytics
- [ ] Company Reports
- [ ] Admin Dashboard
- [ ] Financial Reports

#### Week 17-18: Polish & Optimization
- [ ] UI/UX Enhancements
- [ ] Performance Optimization
- [ ] Security Hardening
- [ ] Final Testing

---

## 🔐 الأمان والصلاحيات

### User Roles
```dart
enum UserRole {
  user,        // مستخدم عادي
  company,     // شركة
  admin,       // إدارة
  superAdmin   // إدارة عليا
}
```

### Permissions Matrix
| Feature | User | Company | Admin | Super Admin |
|---------|------|---------|-------|-------------|
| Search Trips | ✅ | ✅ | ✅ | ✅ |
| Book Trips | ✅ | ❌ | ✅ | ✅ |
| Add Trips | ❌ | ✅ | ❌ | ✅ |
| Approve Companies | ❌ | ❌ | ✅ | ✅ |
| System Settings | ❌ | ❌ | ❌ | ✅ |

---

## 🧪 Testing Checklist

### User App
- [ ] Registration Flow
- [ ] Search & Filter
- [ ] Booking Process
- [ ] Payment Integration
- [ ] GPS Tracking
- [ ] Rating System

### Company App
- [ ] Trip Creation
- [ ] Booking Management
- [ ] Live Tracking
- [ ] Reports Generation

### Admin App
- [ ] Company Approval
- [ ] Content Moderation
- [ ] Financial Reports
- [ ] System Monitoring

---

## 📞 الدعم والمساهمة

### للاستفسارات التقنية
- 📧 Email: dev@miqat.sa
- 💬 Slack: #miqat-dev
- 📱 WhatsApp: +966 XX XXX XXXX

### للإبلاغ عن المشاكل
- 🐛 GitHub Issues
- 📝 Jira Board
- 📊 Analytics Dashboard

---

## 📚 مصادر إضافية

### Documentation
- [Flutter Docs](https://flutter.dev/docs)
- [Material Design](https://material.io/design)
- [Firebase Docs](https://firebase.google.com/docs)

### APIs & SDKs
- Google Maps API
- Payment Gateway (Tap/HyperPay)
- SMS Gateway (Twilio/Unifonic)
- Push Notifications (FCM)

---

## 🎉 ملاحظات ختامية

هذا الدليل هو **وثيقة حية** تتطور مع تطور المشروع.

### التحديثات
- ✅ النسخة 1.0 - التوثيق الأولي (Oct 2025)
- 🔄 النسخة 1.1 - قريباً...

### المساهمون
- 👨‍💻 فريق التطوير
- 🎨 فريق التصميم
- 📊 فريق المنتج
- 🧪 فريق الاختبار

---

**🚀 جاهز للبدء؟ افتح الملف الأول:**

### [📱 ابدأ مع تطبيق المستخدم →](./01_USER_APP_FLOW.md)

---

*آخر تحديث: Oct 17, 2025*
*إصدار: 1.0*
