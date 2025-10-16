# 👔 تطبيق الإدارة - الفلو الكامل

[← العودة للفهرس](./00_MASTER_INDEX.md)

## 📋 جدول الصفحات (19 صفحة)

| # | الصفحة | المسار | الانتقالات |
|---|--------|--------|------------|
| **1. التسجيل** |
| 1.1 | Admin Login | `screens/admin/auth/admin_login_screen.dart` | → Dashboard / 2FA |
| **2. لوحة التحكم** |
| 2.1 | Admin Dashboard | `screens/admin/dashboard/admin_dashboard_screen.dart` | → All Sections |
| **3. إدارة الشركات** |
| 3.1 | Companies List | `screens/admin/companies/companies_list_screen.dart` | → Company Details |
| 3.2 | Registration Requests | `screens/admin/companies/registration_requests_screen.dart` | → Review / Approve |
| 3.3 | Company Details | `screens/admin/companies/company_details_screen.dart` | → Edit / Suspend |
| 3.4 | Company Verification | `screens/admin/companies/company_verification_screen.dart` | → Approve / Reject |
| **4. إدارة المستخدمين** |
| 4.1 | Users List | `screens/admin/users/users_list_screen.dart` | → User Details |
| 4.2 | User Details | `screens/admin/users/user_details_screen.dart` | → Edit / Ban |
| 4.3 | Complaints | `screens/admin/users/complaints_screen.dart` | → Review / Action |
| **5. إدارة المحتوى** |
| 5.1 | Trips Review | `screens/admin/content/trips_review_screen.dart` | → Approve / Reject |
| 5.2 | Content Moderation | `screens/admin/content/content_moderation_screen.dart` | → Review |
| 5.3 | Reported Content | `screens/admin/content/reported_content_screen.dart` | → Action |
| **6. التقارير المالية** |
| 6.1 | Financial Dashboard | `screens/admin/finance/financial_dashboard_screen.dart` | → Details |
| 6.2 | Commissions | `screens/admin/finance/commissions_screen.dart` | → Payments |
| 6.3 | Payments Management | `screens/admin/finance/payments_management_screen.dart` | → Transfer |
| **7. إدارة النظام** |
| 7.1 | System Settings | `screens/admin/system/system_settings_screen.dart` | → Edit |
| 7.2 | Notifications Management | `screens/admin/system/notifications_management_screen.dart` | → Send |
| 7.3 | Analytics Dashboard | `screens/admin/system/analytics_dashboard_screen.dart` | → Reports |
| 7.4 | Logs & Monitoring | `screens/admin/system/logs_monitoring_screen.dart` | → Details |

---

## 🔄 الفلو الرئيسي (Admin Journey)

```
┌─────────────────┐
│   Admin Login   │
│   + 2FA Code    │
└────────┬────────┘
         │
         ↓
┌─────────────────┐
│ Admin Dashboard │ ◄─── المركز الرئيسي
└────────┬────────┘
         │
   ┌─────┼─────┬──────┬────────┐
   │     │     │      │        │
   ↓     ↓     ↓      ↓        ↓
┌──────┐┌────┐┌─────┐┌──────┐┌──────┐
│Companies│Users│Content│Finance│System│
└───┬──┘└──┬─┘└──┬──┘└───┬──┘└───┬──┘
    │      │     │       │       │
    ↓      ↓     ↓       ↓       ↓
  Approve Review Moderate Track Monitor
  Suspend  Ban   Approve  Pay   Config
```

---

## 📱 تفاصيل الصفحات

### 🔐 1. تسجيل الدخول

#### 1.1 Admin Login
```
المسار: screens/admin/auth/admin_login_screen.dart

🔒 تسجيل دخول آمن (2FA)

Step 1: البريد وكلمة المرور
┌───────────────────────────┐
│ 👔 لوحة الإدارة           │
│                           │
│ [__________] البريد       │
│ [__________] كلمة المرور  │
│                           │
│ [تسجيل الدخول]            │→ 2FA Screen
└───────────────────────────┘

Step 2: Two-Factor Authentication
┌───────────────────────────┐
│ رمز التحقق الثنائي        │
│ تم إرسال الرمز إلى:       │
│ ad***@miqat.sa           │
│                           │
│ [_] [_] [_] [_] [_] [_]  │
│                           │
│ [تحقق]                    │→ Dashboard
└───────────────────────────┘

🔒 Security Features:
- Two-Factor Authentication
- IP Whitelist
- Session Timeout
- Activity Logging
```

---

### 📊 2. لوحة التحكم الرئيسية

#### 2.1 Admin Dashboard
```
المسار: screens/admin/dashboard/admin_dashboard_screen.dart

┌─────────────────────────────────────┐
│ [☰] 🕋 ميقات إن - الإدارة    [🔔] │
├─────────────────────────────────────┤
│                                     │
│ 📊 إحصائيات عامة:                  │
│ ┌────┐ ┌────┐ ┌────┐ ┌────┐        │
│ │124 │ │1.2K│ │450 │ │98% │        │
│ │شركة│ │مستخدم│رحلة│ │نشاط│        │
│ └────┘ └────┘ └────┘ └────┘        │
│                                     │
├─────────────────────────────────────┤
│ ⚠️ يتطلب إجراء (8):                │
│ ┌─────────────────────────────────┐│
│ │ 🏢 5 طلبات تسجيل شركات جديدة  ││→ Registration Requests
│ │ 📋 12 رحلة قيد المراجعة       ││→ Trips Review
│ │ ⚠️ 3 شكاوى عاجلة              ││→ Complaints
│ └─────────────────────────────────┘│
│                                     │
├─────────────────────────────────────┤
│ 📈 الرسوم البيانية:                │
│ [نمو المستخدمين | الحجوزات]       │
│ [الإيرادات | معدلات النشاط]        │
│                                     │
├─────────────────────────────────────┤
│ 💰 الملخص المالي:                  │
│ - إيرادات اليوم: 25,450 ر         │→ Financial Dashboard
│ - عمولات مستحقة: 12,250 ر         │
│ - مدفوعات معلقة: 8,500 ر          │
│                                     │
├─────────────────────────────────────┤
│ 🔍 النشاط الأخير:                  │
│ - شركة الهدى أضافت رحلة جديدة     │
│ - 24 حجز جديد في آخر ساعة         │
│ - مستخدم جديد: أحمد محمد           │
└─────────────────────────────────────┘

Quick Actions:
[موافقة على شركة] [مراجعة رحلة] [إرسال إشعار]
```

---

### 🏢 3. إدارة الشركات

#### 3.1 Companies List
```
المسار: screens/admin/companies/companies_list_screen.dart

Filters:
[الكل] [معتمدة] [معلقة] [محظورة]

Search: [بحث بالاسم أو الرقم...]

Company Card:
┌───────────────────────────────────┐
│ 🏢 شركة الهدى للعمرة              │
│ 📋 ترخيص: 123456789              │
│ ⭐ 4.6 (248 تقييم)               │
│ 📊 24 رحلة | 450 حجز             │
│ 💰 إيرادات: 125,000 ر            │
│ ✅ الحالة: نشطة                  │
│                                   │
│ [تفاصيل] [تعليق] [تقارير]        │→ Actions
└───────────────────────────────────┘

Bulk Actions:
[☑️ تحديد الكل] [إرسال إشعار] [تصدير]
```

#### 3.2 Registration Requests
```
المسار: screens/admin/companies/registration_requests_screen.dart

Request Card:
┌───────────────────────────────────┐
│ 🆕 طلب تسجيل جديد                │
│                                   │
│ 🏢 شركة النور للرحلات             │
│ 📋 رقم الترخيص: 987654321        │
│ 📅 تاريخ الطلب: 15/10/2025       │
│ 📁 المستندات:                    │
│   ✅ الترخيص                      │
│   ✅ السجل التجاري                │
│   ✅ شهادة الضريبة                │
│                                   │
│ [مراجعة التفاصيل]                 │→ Company Verification
└───────────────────────────────────┘
```

#### 3.3 Company Verification
```
المسار: screens/admin/companies/company_verification_screen.dart

الخطوات:
┌───────────────────────────────────┐
│ Step 1: التحقق من المستندات       │
│ ┌─────────────────────────────┐  │
│ │ 📄 الترخيص                 │  │
│ │ [عرض] [تحميل]              │  │
│ │ ☑️ صالح ☐ منتهي ☐ مزور    │  │
│ └─────────────────────────────┘  │
│                                   │
│ Step 2: التحقق من البيانات        │
│ - الاسم: ✅ مطابق                │
│ - الرقم: ✅ صحيح                 │
│ - العنوان: ⚠️ يحتاج تأكيد       │
│                                   │
│ Step 3: التواصل (optional)        │
│ [اتصل] [بريد] [ملاحظات]          │
│                                   │
│ Step 4: القرار النهائي            │
│ ┌─────────────────────────────┐  │
│ │ ⚪ موافقة وتفعيل الحساب     │  │
│ │ ⚪ رفض مع ذكر السبب         │  │
│ │ ⚪ طلب مستندات إضافية       │  │
│ └─────────────────────────────┘  │
│                                   │
│ ملاحظات الإدارة:                 │
│ [_______________________]        │
│                                   │
│ [إرسال القرار]                    │
└───────────────────────────────────┘

Actions:
[موافقة] → Email Notification → Companies List (Active)
[رفض] → Email with Reason → Archive
[طلب مستندات] → Email Request → Pending
```

#### 3.4 Company Details
```
المسار: screens/admin/companies/company_details_screen.dart

Tabs:
1. المعلومات الأساسية
2. الرحلات (24)
3. الحجوزات (450)
4. التقييمات (248)
5. المالية
6. السجل

Actions:
[تعديل] [تعليق الحساب] [إلغاء التعليق] [حذف]
```

---

### 👥 4. إدارة المستخدمين

#### 4.1 Users List
```
المسار: screens/admin/users/users_list_screen.dart

Filters:
[الكل] [نشط] [محظور] [VIP]

User Card:
┌───────────────────────────────────┐
│ 👤 أحمد محمد عبدالله              │
│ 📱 +966 50 123 4567              │
│ 📧 ahmed@email.com               │
│ 📅 عضو منذ: 5 أشهر               │
│ 🎁 نقاط: 1,250                  │
│ 📋 12 رحلة | ⭐ 4.8              │
│ ✅ نشط                           │
│                                   │
│ [تفاصيل] [حظر] [رسالة]           │→ Actions
└───────────────────────────────────┘
```

#### 4.2 User Details
```
المسار: screens/admin/users/user_details_screen.dart

Tabs:
1. الملف الشخصي
2. سجل الحجوزات
3. المدفوعات
4. التقييمات
5. النشاط

Actions:
[تعديل] [حظر] [إلغاء الحظر] [حذف الحساب]

Ban Dialog:
┌───────────────────────────────────┐
│ حظر المستخدم                      │
│                                   │
│ السبب:                            │
│ ⚪ انتهاك الشروط                 │
│ ⚪ سلوك غير لائق                 │
│ ⚪ احتيال                         │
│ ⚪ آخر: [________]                │
│                                   │
│ المدة:                            │
│ ⚪ أسبوع ⚪ شهر ⚪ دائم           │
│                                   │
│ [تأكيد الحظر] [إلغاء]            │
└───────────────────────────────────┘
```

#### 4.3 Complaints
```
المسار: screens/admin/users/complaints_screen.dart

Status Filters:
[جديدة] [قيد المراجعة] [محلولة] [مرفوضة]

Complaint Card:
┌───────────────────────────────────┐
│ ⚠️ شكوى #1234 - عاجل             │
│                                   │
│ 👤 من: أحمد محمد                 │
│ 🏢 ضد: شركة الهدى                │
│ 📋 رحلة: #5678                   │
│ 📅 التاريخ: 15/10/2025           │
│                                   │
│ الموضوع: "تأخير في الرحلة..."   │
│                                   │
│ [مراجعة التفاصيل]                 │→ Review Dialog
└───────────────────────────────────┘

Review Dialog:
- قراءة الشكوى الكاملة
- التواصل مع الطرفين
- مراجعة السجلات
- اتخاذ الإجراء:
  - قبول الشكوى
  - رفض الشكوى
  - تحذير الشركة
  - تعليق الشركة
  - تعويض المستخدم
```

---

### 📝 5. إدارة المحتوى

#### 5.1 Trips Review
```
المسار: screens/admin/content/trips_review_screen.dart

Pending Trips (12):
┌───────────────────────────────────┐
│ 📋 رحلة قيد المراجعة              │
│                                   │
│ 🏢 شركة: الهدى                   │
│ 📅 التاريخ: 20 رمضان             │
│ 💰 السعر: 350 ر                  │
│ 💺 المقاعد: 20                   │
│                                   │
│ البرنامج:                         │
│ - اليوم 1: الانطلاق...           │
│ - اليوم 2: الطواف...             │
│                                   │
│ ☑️ المعلومات كاملة               │
│ ☑️ الصور مناسبة                  │
│ ☑️ السعر معقول                   │
│                                   │
│ [موافقة ونشر] [رفض] [طلب تعديل]  │
└───────────────────────────────────┘
```

#### 5.2 Content Moderation
```
المسار: screens/admin/content/content_moderation_screen.dart

Types:
[الصور] [الأوصاف] [التعليقات] [التقييمات]

Review Queue:
- صور الرحلات
- أوصاف الخدمات
- مراجعات المستخدمين
- تعليقات الشركات

Actions:
[موافقة] [رفض] [تعديل] [حذف]
```

---

### 💰 6. التقارير المالية

#### 6.1 Financial Dashboard
```
المسار: screens/admin/finance/financial_dashboard_screen.dart

┌───────────────────────────────────┐
│ 💰 الملخص المالي - أكتوبر 2025   │
├───────────────────────────────────┤
│ إجمالي المعاملات: 450            │
│ إجمالي الحجوزات: 225,000 ر       │
│ العمولات (10%): 22,500 ر         │
│ الضرائب (15%): 3,375 ر           │
│ الصافي: 19,125 ر                 │
├───────────────────────────────────┤
│ 📊 توزيع الإيرادات:              │
│ - شركة الهدى: 8,500 ر            │
│ - شركة السلام: 5,200 ر           │
│ - شركة النور: 6,400 ر            │
├───────────────────────────────────┤
│ 💳 المدفوعات:                    │
│ - مدفوعة: 15,000 ر               │
│ - معلقة: 4,125 ر                 │
│ - مستحقة: 0 ر                    │
└───────────────────────────────────┘

[تحميل التقرير] [تصدير Excel]
```

#### 6.2 Commissions
```
المسار: screens/admin/finance/commissions_screen.dart

Commission Card:
┌───────────────────────────────────┐
│ 🏢 شركة الهدى                    │
│ 📅 الفترة: 1-15 أكتوبر          │
│                                   │
│ عدد الحجوزات: 24                 │
│ إجمالي المبيعات: 18,500 ر        │
│ العمولة (10%): 1,850 ر           │
│ الخصومات: -50 ر                  │
│ الصافي: 1,800 ر                  │
│                                   │
│ الحالة: 🟡 معلق                  │
│                                   │
│ [تفاصيل] [دفع الآن] [تصدير]      │
└───────────────────────────────────┘
```

#### 6.3 Payments Management
```
المسار: screens/admin/finance/payments_management_screen.dart

Pending Payments (5):
┌───────────────────────────────────┐
│ 💳 دفعة مستحقة                   │
│                                   │
│ 🏢 إلى: شركة الهدى               │
│ 💰 المبلغ: 1,800 ر               │
│ 📅 تاريخ الاستحقاق: 20/10        │
│ 🏦 الحساب: SA123456789           │
│                                   │
│ [معالجة الدفع] [تأجيل] [رفض]     │
└───────────────────────────────────┘

Process Payment:
- تأكيد المبلغ
- تأكيد الحساب البنكي
- إرسال الدفع
- إشعار الشركة
```

---

### ⚙️ 7. إدارة النظام

#### 7.1 System Settings
```
المسار: screens/admin/system/system_settings_screen.dart

Sections:

1. إعدادات العمولة
   - نسبة العمولة: [10%]
   - نسبة الضريبة: [15%]

2. إعدادات الحجز
   - حد أقصى للمقاعد: [50]
   - فترة الإلغاء: [24 ساعة]

3. إعدادات التقييم
   - الحد الأدنى للتقييم: [1]
   - إلزامية التقييم: [نعم]

4. إعدادات الإشعارات
   - إشعارات البريد: [✅]
   - إشعارات SMS: [✅]
   - إشعارات Push: [✅]

5. إعدادات الأمان
   - Two-Factor Auth: [✅]
   - Session Timeout: [30 دقيقة]

[حفظ التغييرات]
```

#### 7.2 Notifications Management
```
المسار: screens/admin/system/notifications_management_screen.dart

Send Notification:
┌───────────────────────────────────┐
│ إرسال إشعار عام                  │
│                                   │
│ إلى:                              │
│ ⚪ جميع المستخدمين               │
│ ⚪ جميع الشركات                  │
│ ⚪ مجموعة مخصصة                  │
│                                   │
│ العنوان:                          │
│ [_______________________]        │
│                                   │
│ الرسالة:                          │
│ [_______________________]        │
│ [_______________________]        │
│                                   │
│ القنوات:                          │
│ ☑️ تطبيق ☑️ بريد ☑️ SMS          │
│                                   │
│ الجدولة:                          │
│ ⚪ الآن ⚪ لاحقاً [📅]             │
│                                   │
│ [إرسال] [معاينة] [إلغاء]         │
└───────────────────────────────────┘
```

#### 7.3 Analytics Dashboard
```
المسار: screens/admin/system/analytics_dashboard_screen.dart

Metrics:
┌───────────────────────────────────┐
│ 📊 تحليلات المنصة                │
│                                   │
│ النمو الشهري:                    │
│ - مستخدمون جدد: +250 (+15%)     │
│ - شركات جديدة: +5 (+12%)        │
│ - رحلات جديدة: +45 (+18%)       │
│                                   │
│ النشاط:                           │
│ - زيارات اليوم: 1,250           │
│ - حجوزات اليوم: 24              │
│ - معدل التحويل: 2.8%            │
│                                   │
│ الأداء:                           │
│ - سرعة التحميل: 1.2s            │
│ - نسبة الخطأ: 0.1%              │
│ - معدل الارتداد: 35%            │
└───────────────────────────────────┘

Charts:
- خط نمو المستخدمين
- توزيع الحجوزات
- أكثر المدن نشاطاً
```

#### 7.4 Logs & Monitoring
```
المسار: screens/admin/system/logs_monitoring_screen.dart

Types:
[System] [Security] [Errors] [API] [Database]

Log Entry:
┌───────────────────────────────────┐
│ [ERROR] | 2025-10-17 14:23:45   │
│ API_TIMEOUT: /api/trips/search   │
│ User: ahmed@email.com            │
│ IP: 192.168.1.100                │
│ Details: Request timeout after 30s│
│                                   │
│ [عرض التفاصيل] [حل المشكلة]      │
└───────────────────────────────────┘

Filters:
- الفترة الزمنية
- نوع السجل
- مستوى الخطورة
- المستخدم/الشركة
```

---

## 🔗 مسارات الإدارة الرئيسية

### Approval Flow:
```
Company Registration Request
    ↓
Verification Review
    ↓
[Approve] → Active Company
[Reject] → Email Notification
```

### Content Moderation Flow:
```
New Trip Posted
    ↓
Admin Review
    ↓
[Approve] → Published
[Request Changes] → Back to Company
[Reject] → Archived
```

### Complaint Resolution Flow:
```
User Files Complaint
    ↓
Admin Review
    ↓
Contact Both Parties
    ↓
Decision
    ↓
[Accept] → Action Taken + Compensation
[Reject] → Close with Reason
```

---

[📄 التالي: الصفحات المشتركة →](./04_SHARED_SCREENS.md)
