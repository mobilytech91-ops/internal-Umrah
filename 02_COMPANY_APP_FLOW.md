# 🏢 تطبيق الشركات - الفلو الكامل

[← العودة للفهرس](./00_MASTER_INDEX.md)

## 📋 جدول الصفحات (29 صفحة)

| # | الصفحة | المسار | الانتقالات |
|---|--------|--------|------------|
| **1. التسجيل والدخول** |
| 1.1 | Company Login | `screens/company/auth/company_login_screen.dart` | → Dashboard / Forgot Password |
| 1.2 | Company Registration | `screens/company/auth/company_registration_screen.dart` | → Verification |
| 1.3 | Forgot Password | `screens/company/auth/forgot_password_screen.dart` | → Reset Password |
| **2. لوحة التحكم** |
| 2.1 | Dashboard | `screens/company/dashboard/dashboard_screen.dart` | → All Sections |
| **3. إدارة الرحلات** |
| 3.1 | Trips List | `screens/company/trips/trips_list_screen.dart` | → Trip Details / Add Trip |
| 3.2 | Add Trip | `screens/company/trips/add_trip_screen.dart` | → Trip Details / Daily Program |
| 3.3 | Edit Trip | `screens/company/trips/edit_trip_screen.dart` | → Trip Details |
| 3.4 | Trip Details Management | `screens/company/trips/trip_details_management_screen.dart` | → Edit / Bookings |
| 3.5 | Daily Program | `screens/company/trips/daily_program_screen.dart` | → Add Trip |
| 3.6 | Trip Services | `screens/company/trips/trip_services_screen.dart` | → Add Trip |
| **4. إدارة الحجوزات** |
| 4.1 | Bookings List | `screens/company/bookings/bookings_list_screen.dart` | → Booking Details |
| 4.2 | Booking Details | `screens/company/bookings/booking_details_screen.dart` | → Confirm / Cancel / Contact |
| 4.3 | Passengers Management | `screens/company/bookings/passengers_management_screen.dart` | → Assign Seats / Rooms |
| 4.4 | Assign Seats | `screens/company/bookings/assign_seats_screen.dart` | → Passengers |
| **5. الرحلة المباشرة** |
| 5.1 | Start Trip | `screens/company/live/start_trip_screen.dart` | → Live Monitoring |
| 5.2 | Live Monitoring | `screens/company/live/live_monitoring_screen.dart` | → Contact Driver / Updates |
| 5.3 | End Trip | `screens/company/live/end_trip_screen.dart` | → Reports |
| **6. التقارير** |
| 6.1 | Financial Reports | `screens/company/reports/financial_reports_screen.dart` | → Export |
| 6.2 | Performance Reports | `screens/company/reports/performance_reports_screen.dart` | → Details |
| 6.3 | Customer Analytics | `screens/company/reports/customer_analytics_screen.dart` | → Graphs |
| 6.4 | Trip Reports | `screens/company/reports/trip_reports_screen.dart` | → Details |
| **7. إدارة الموارد** |
| 7.1 | Vehicles Management | `screens/company/resources/vehicles_management_screen.dart` | → Add / Edit |
| 7.2 | Hotels Management | `screens/company/resources/hotels_management_screen.dart` | → Add / Edit |
| 7.3 | Staff Management | `screens/company/resources/staff_management_screen.dart` | → Add / Edit |
| 7.4 | Drivers Management | `screens/company/resources/drivers_management_screen.dart` | → Add / Edit / Schedule |
| 7.5 | Schedules | `screens/company/resources/schedules_screen.dart` | → Assign |
| **8. الإعدادات** |
| 8.1 | Company Profile | `screens/company/profile/company_profile_screen.dart` | → Edit |
| 8.2 | Company Settings | `screens/company/settings/company_settings_screen.dart` | → All Settings |
| 8.3 | Reviews Management | `screens/company/reviews/reviews_management_screen.dart` | → Reply |

---

## 🔄 الفلو الرئيسي (Company Journey)

```
┌─────────────────┐
│  Company Login  │
└────────┬────────┘
         │ [تسجيل الدخول]
         ↓
┌─────────────────┐
│    Dashboard    │ ◄─── المركز الرئيسي
└────────┬────────┘
         │
   ┌─────┼─────┬──────┬────────┐
   │     │     │      │        │
   ↓     ↓     ↓      ↓        ↓
┌────┐┌─────┐┌─────┐┌──────┐┌─────┐
│Trips││Book.││Live ││Reports││Res. │
└──┬─┘└──┬──┘└──┬──┘└───┬──┘└──┬──┘
   │     │      │       │      │
   │     │      │       │      │
   ↓     ↓      ↓       ↓      ↓
┌──────────────────────────────────┐
│       جميع أقسام الإدارة          │
└──────────────────────────────────┘
```

---

## 📱 تفاصيل الصفحات

### 🔐 1. التسجيل والدخول

#### 1.1 Company Login
```
المسار: screens/company/auth/company_login_screen.dart

العناصر:
- [البريد الإلكتروني] Input
- [كلمة المرور] Password Input
- [☑️ تذكرني] Checkbox
- [تسجيل الدخول] Button → Dashboard
- [نسيت كلمة المرور؟] Link → Forgot Password
- [ليس لديك حساب؟ سجّل الآن] Link → Registration

API: POST /api/company/auth/login
```

#### 1.2 Company Registration
```
المسار: screens/company/auth/company_registration_screen.dart

الحقول:
- اسم الشركة
- رقم الترخيص
- البريد الإلكتروني
- رقم الجوال
- المدينة
- العنوان
- رفع المستندات:
  - الترخيص
  - السجل التجاري
  - شهادة الضريبة

[إرسال الطلب] → Waiting for Admin Approval

API: POST /api/company/register
```

---

### 📊 2. لوحة التحكم الرئيسية

#### 2.1 Dashboard
```
المسار: screens/company/dashboard/dashboard_screen.dart

الأقسام:

┌─────────────────────────────────┐
│ [☰] 🏢 شركة الهدى     [🔔] [⚙️]│
├─────────────────────────────────┤
│                                 │
│ ┌─────┐ ┌─────┐ ┌─────┐ ┌─────┐│
│ │ 24  │ │ 156 │ │4.6⭐│ │15K ر││
│ │رحلات│ │حجوزات│ │تقييم│ │ربح ││
│ └─────┘ └─────┘ └─────┘ └─────┘│
├─────────────────────────────────┤
│ 📊 الرحلات النشطة (5):         │
│ ┌───────────────────────────┐  │
│ │ رحلة 1 - جارية الآن      │→ Live Monitoring
│ │ 📍 في الطريق | 15 راكب   │  │
│ └───────────────────────────┘  │
├─────────────────────────────────┤
│ 🔔 الحجوزات الجديدة (8):      │
│ ┌───────────────────────────┐  │
│ │ حجز #1234 | أحمد محمد     │→ Booking Details
│ │ 350 ر | قيد الانتظار      │  │
│ │ [قبول] [رفض]              │  │
│ └───────────────────────────┘  │
├─────────────────────────────────┤
│ 📅 التقويم الشهري              │
│ [Calendar Widget]              │→ Trips by Date
├─────────────────────────────────┤
│ 📈 التقارير السريعة            │
│ - إيرادات اليوم: 5,250 ر      │→ Financial Reports
│ - معدل الإشغال: 85%           │→ Performance
│ - تقييمات جديدة: 12           │→ Reviews
└─────────────────────────────────┘

Quick Actions:
[+ إضافة رحلة] → Add Trip
[📋 الحجوزات] → Bookings List
[🚍 المركبات] → Vehicles
[📊 التقارير] → Reports
```

---

### 🚌 3. إدارة الرحلات

#### 3.1 Trips List
```
المسار: screens/company/trips/trips_list_screen.dart

Tabs:
- القادمة (Upcoming)
- الجارية (Active)
- المنتهية (Completed)
- الملغية (Cancelled)

Trip Card:
┌───────────────────────────┐
│ 🖼️ [صورة]                │
│ رحلة عمرة VIP - جدة/مكة  │
│ 📅 الجمعة 10 رمضان       │
│ 💺 18/20 محجوز           │
│ 💰 7,000 ر إجمالي        │
│ [تعديل] [حذف] [عرض]      │→ Edit / Delete / View
└───────────────────────────┘

[+ إضافة رحلة جديدة] → Add Trip
```

#### 3.2 Add Trip (Multi-Step)
```
المسار: screens/company/trips/add_trip_screen.dart

Step 1: المعلومات الأساسية
- اسم الرحلة
- نوع الرحلة (رجال/نساء/عائلات)
- مدينة الانطلاق
- نقطة التجمع (خريطة)
- التاريخ والوقت
- عدد المقاعد
- السعر للفرد

Step 2: البرنامج اليومي
- [+ إضافة يوم]
  - اليوم: الأول
  - الأنشطة: [+ إضافة نشاط]
    - الوقت
    - النشاط
    - المكان

Step 3: الخدمات المتضمنة
- ☑️ فندق → اختر الفندق
- ☑️ نقل → اختر المركبة
- ☑️ وجبات → حدد الوجبات
- ☑️ مرشد → اختر المرشد
- ☑️ تأمين

Step 4: الصور والوسائط
- رفع صور الرحلة (3-10 صور)
- رفع برنامج PDF (optional)

Step 5: المراجعة والنشر
- معاينة كل التفاصيل
- [حفظ كمسودة] [نشر]

Navigation:
[حفظ] → Trips List (Draft)
[نشر] → Pending Admin Approval → Trips List
```

#### 3.3 Edit Trip
```
نفس خطوات Add Trip مع البيانات المملوءة مسبقاً
```

---

### 📋 4. إدارة الحجوزات

#### 4.1 Bookings List
```
المسار: screens/company/bookings/bookings_list_screen.dart

Filters:
[الكل] [قيد الانتظار] [مؤكد] [ملغي]

Booking Card:
┌───────────────────────────┐
│ حجز #1234                 │
│ 👤 أحمد محمد              │
│ 📅 رحلة: الجمعة 10 رمضان │
│ 💰 1,050 ر (3 أفراد)     │
│ 🟡 قيد الانتظار          │
│ [تفاصيل] [قبول] [رفض]    │→ Actions
└───────────────────────────┘
```

#### 4.2 Booking Details
```
المسار: screens/company/bookings/booking_details_screen.dart

الأقسام:
1. معلومات الحجز
   - رقم الحجز
   - التاريخ
   - الحالة

2. معلومات المسافرين
   - القائمة الكاملة
   - [إدارة المسافرين] → Passengers Management

3. تفاصيل الدفع
   - المبلغ المدفوع
   - طريقة الدفع
   - العمولة

4. الإجراءات
   - [تأكيد الحجز] → Update Status
   - [إلغاء الحجز] → Cancel Dialog
   - [اتصل بالعميل] → Phone
   - [إرسال رسالة] → SMS/WhatsApp
```

#### 4.3 Passengers Management
```
المسار: screens/company/bookings/passengers_management_screen.dart

الوظائف:
- عرض جميع المسافرين للرحلة
- توزيع المقاعد
- توزيع الغرف (للعائلات)
- طباعة قائمة الركاب
- تصدير Excel

Passenger Card:
┌───────────────────────────┐
│ 👤 أحمد محمد عبدالله     │
│ 🆔 1234567890            │
│ 📱 0501234567            │
│ 💺 مقعد: A12            │
│ 🏨 غرفة: 205            │
│ [تعديل] [حذف]            │
└───────────────────────────┘

[توزيع تلقائي] [حفظ التوزيع]
```

---

### 🎬 5. الرحلة المباشرة

#### 5.1 Start Trip
```
المسار: screens/company/live/start_trip_screen.dart

قبل البدء:
┌───────────────────────────┐
│ رحلة: جدة - مكة          │
│ 📅 الجمعة 10 رمضان       │
│ 💺 18 راكب مسجل          │
│                           │
│ Checklist:               │
│ ☑️ جميع المسافرين حضروا  │
│ ☑️ المركبة جاهزة         │
│ ☑️ السائق حاضر           │
│ ☑️ المرشد حاضر           │
│                           │
│ [بدء الرحلة] Button      │→ Live Monitoring
└───────────────────────────┘
```

#### 5.2 Live Monitoring
```
المسار: screens/company/live/live_monitoring_screen.dart

الواجهة:
┌───────────────────────────────┐
│ 🔴 Live | الرحلة جارية الآن    │
├───────────────────────────────┤
│                               │
│    🗺️ خريطة GPS               │
│    📍 الموقع الحالي           │
│    🚍 ← متحرك                 │
│                               │
├───────────────────────────────┤
│ معلومات الرحلة:              │
│ - البداية: 8:00 ص            │
│ - الوقت الحالي: 9:15 ص       │
│ - الوصول المتوقع: 10:30 ص    │
│ - المسافة المتبقية: 45 كم    │
├───────────────────────────────┤
│ السائق: أحمد محمد            │
│ [📞 اتصل] [💬 رسالة]         │
├───────────────────────────────┤
│ المسافرين (18):              │
│ [عرض القائمة]                │→ Passengers
├───────────────────────────────┤
│ التحديثات:                   │
│ [إرسال تحديث للمسافرين]      │→ Notification
│ - وصلنا مكة                  │
│ - استراحة 15 دقيقة           │
│ - تأخير في الطريق            │
└───────────────────────────────┘

[إنهاء الرحلة] → End Trip
```

#### 5.3 End Trip
```
المسار: screens/company/live/end_trip_screen.dart

التأكيد:
┌───────────────────────────┐
│ إنهاء الرحلة              │
│                           │
│ ☑️ وصول جميع المسافرين   │
│ ☑️ تسليم الأمتعة         │
│ ☑️ إغلاق التتبع           │
│                           │
│ ملاحظات (optional):      │
│ [________________]        │
│                           │
│ [تأكيد الإنهاء]           │→ Trip Completed
└───────────────────────────┘

بعد التأكيد:
- إرسال طلب تقييم للمسافرين
- إنشاء تقرير الرحلة
- تحديث الإحصائيات
```

---

### 📊 6. التقارير والإحصائيات

#### 6.1 Financial Reports
```
المسار: screens/company/reports/financial_reports_screen.dart

الفترة:
[اليوم] [الأسبوع] [الشهر] [السنة] [مخصص]

الإحصائيات:
┌───────────────────────────┐
│ 💰 إجمالي الإيرادات     │
│    15,250 ر              │
├───────────────────────────┤
│ 📊 توزيع الإيرادات:     │
│ - الحجوزات: 13,500 ر    │
│ - العمولة: -1,500 ر     │
│ - الضرائب: -750 ر       │
│ - الصافي: 11,250 ر      │
├───────────────────────────┤
│ 📈 مقارنة بالشهر السابق: │
│ +15% ⬆️                  │
└───────────────────────────┘

[تحميل PDF] [تصدير Excel]
```

#### 6.2 Performance Reports
```
المسار: screens/company/reports/performance_reports_screen.dart

المؤشرات:
- معدل التقييم: ⭐ 4.6
- معدل الإشغال: 85%
- نسبة الإلغاءات: 3%
- معدل تكرار العملاء: 45%

Graphs:
- عدد الرحلات الشهرية
- معدل الحجوزات
- أوقات الذروة
```

#### 6.3 Customer Analytics
```
المسار: screens/company/reports/customer_analytics_screen.dart

التحليلات:
- المدن الأكثر طلباً
- الأعمار الأكثر حجزاً
- أنواع الرحلات المفضلة
- أوقات الحجز المفضلة
- معدل الإنفاق للعميل
```

---

### 🔧 7. إدارة الموارد

#### 7.1 Vehicles Management
```
المسار: screens/company/resources/vehicles_management_screen.dart

Vehicle Card:
┌───────────────────────────┐
│ 🚍 مرسيدس 2025          │
│ 📋 لوحة: أ ب ج 1234     │
│ 💺 سعة: 20 مقعد          │
│ ✅ الحالة: متاح           │
│ 🔧 آخر صيانة: 15/08      │
│ [تعديل] [صيانة] [جدولة]  │
└───────────────────────────┘

[+ إضافة مركبة]
```

#### 7.2 Hotels Management
```
المسار: screens/company/resources/hotels_management_screen.dart

Hotel Card:
┌───────────────────────────┐
│ 🏨 فندق الماسة           │
│ ⭐⭐⭐⭐ | مكة            │
│ 📍 600م من الحرم          │
│ 💰 السعر: 200 ر/ليلة     │
│ 🛏️ 50 غرفة متاحة         │
│ [تعديل] [حجز] [عقد]      │
└───────────────────────────┘

[+ إضافة فندق شريك]
```

#### 7.3 Staff Management
```
المسار: screens/company/resources/staff_management_screen.dart

Staff Card:
┌───────────────────────────┐
│ 👤 أحمد محمد - مرشد      │
│ 📱 0501234567            │
│ ⭐ 4.8/5                 │
│ 🗓️ متاح: نعم            │
│ [تعديل] [جدولة] [تقييم]  │
└───────────────────────────┘

الأدوار:
- مرشد
- مشرف
- منسق
- سائق (→ Drivers Management)
```

---

### ⚙️ 8. الإعدادات والملف

#### 8.1 Company Profile
```
المسار: screens/company/profile/company_profile_screen.dart

الأقسام:
- معلومات الشركة
- الترخيص والوثائق
- معلومات الاتصال
- الحساب البنكي
- [تعديل الملف]
```

#### 8.2 Reviews Management
```
المسار: screens/company/reviews/reviews_management_screen.dart

Review Card:
┌───────────────────────────┐
│ ⭐⭐⭐⭐⭐ أحمد محمد      │
│ "خدمة ممتازة..."         │
│ 📅 منذ يومين              │
│ [الرد] [إبلاغ]            │
└───────────────────────────┘

[الرد على التقييم] → Reply Dialog
```

---

## 🔗 روابط الانتقال الرئيسية

### من Dashboard:
- Quick Actions → المهام السريعة
- Active Trips → Live Monitoring
- New Bookings → Booking Details
- Stats → Reports

### دورة الرحلة:
Add Trip → Trips List → Bookings → Start Trip → Live → End Trip → Reports

---

[📄 التالي: تطبيق الإدارة →](./03_ADMIN_APP_FLOW.md)
