# 📱 تطبيق المستخدم - الفلو الكامل

[← العودة للفهرس](./00_MASTER_INDEX.md)

## 📋 جدول الصفحات (39 صفحة)

| # | الصفحة | المسار | الانتقالات |
|---|--------|--------|------------|
| **1. التسجيل والدخول** |
| 1.1 | Splash Screen | `screens/user/auth/splash_screen.dart` | → Welcome / Home |
| 1.2 | Welcome Screen | `screens/user/auth/welcome_screen.dart` | → User Type Selection / Login |
| 1.3 | User Type Selection | `screens/user/auth/user_type_selection_screen.dart` | → Login / Company App / Admin App |
| 1.4 | Login Screen | `screens/user/auth/login_screen.dart` | → OTP / Registration / Home (Social) |
| 1.5 | OTP Verification | `screens/user/auth/otp_verification_screen.dart` | → Home / Complete Profile |
| 1.6 | Registration | `screens/user/auth/registration_screen.dart` | → OTP |
| 1.7 | Complete Profile | `screens/user/auth/complete_profile_screen.dart` | → Home |
| **2. الرئيسية والبحث** |
| 2.1 | Home Screen | `screens/user/home/home_screen.dart` | → Trip Details / Search / My Trips / Profile |
| 2.2 | Advanced Search | `screens/user/search/advanced_search_screen.dart` | → Search Results |
| 2.3 | Search Results | `screens/user/search/search_results_screen.dart` | → Trip Details / Compare |
| 2.4 | Compare Trips | `screens/user/search/compare_trips_screen.dart` | → Trip Details / Booking |
| 2.5 | Trips List | `screens/user/trips/trips_list_screen.dart` | → Trip Details |
| 2.6 | Map View | `screens/user/search/map_view_screen.dart` | → Trip Details |
| **3. تفاصيل الرحلة** |
| 3.1 | Trip Details | `screens/user/trips/trip_details_screen.dart` | → Booking / Company / Hotel / Reviews |
| 3.2 | Company Details | `screens/user/companies/company_details_screen.dart` | → Trip Details / Contact |
| 3.3 | Hotel Details | `screens/user/hotels/hotel_details_screen.dart` | → Reviews / Contact |
| 3.4 | Transport Details | `screens/user/transport/transport_details_screen.dart` | → Trip Details |
| 3.5 | All Reviews | `screens/user/reviews/all_reviews_screen.dart` | → Report / Like |
| **4. الحجز والدفع** |
| 4.1 | Trip Type Selection | `screens/user/booking/trip_type_selection_screen.dart` | → Booking Form |
| 4.2 | Booking Form | `screens/user/booking/booking_form_screen.dart` | → Review Booking |
| 4.3 | Family Members | `screens/user/booking/family_members_screen.dart` | → Review Booking |
| 4.4 | Review Booking | `screens/user/booking/review_booking_screen.dart` | → Payment |
| 4.5 | Payment Screen | `screens/user/booking/payment_screen.dart` | → Confirmation |
| 4.6 | Booking Confirmation | `screens/user/booking/booking_confirmation_screen.dart` | → My Trips / Home |
| **5. إدارة الرحلات** |
| 5.1 | My Trips | `screens/user/trips/my_trips_screen.dart` | → Booked Trip Details |
| 5.2 | Booked Trip Details | `screens/user/trips/booked_trip_details_screen.dart` | → Live Tracking / Cancel |
| 5.3 | Live Tracking | `screens/user/trips/live_tracking_screen.dart` | → Contact Driver / Share |
| 5.4 | Cancel Booking | `screens/user/trips/cancel_booking_screen.dart` | → Refund Info / My Trips |
| **6. التقييمات** |
| 6.1 | Rating Screen | `screens/user/ratings/rating_screen.dart` | → My Trips |
| 6.2 | Review Submission | `screens/user/ratings/review_submission_screen.dart` | → Success |
| 6.3 | My Reviews | `screens/user/ratings/my_reviews_screen.dart` | → Edit Review |
| **7. الملف الشخصي** |
| 7.1 | Profile Screen | `screens/user/profile/profile_screen.dart` | → Edit Profile / Settings |
| 7.2 | Edit Profile | `screens/user/profile/edit_profile_screen.dart` | → Profile |
| 7.3 | Loyalty Points | `screens/user/profile/loyalty_points_screen.dart` | → Redeem |
| 7.4 | Favorites | `screens/user/profile/favorites_screen.dart` | → Trip Details |
| 7.5 | Booking History | `screens/user/profile/booking_history_screen.dart` | → Invoice |
| 7.6 | Settings | `screens/user/profile/settings_screen.dart` | → Notifications / Language |
| 7.7 | Notification Settings | `screens/user/profile/notification_settings_screen.dart` | → Settings |
| 7.8 | Change Password | `screens/user/profile/change_password_screen.dart` | → Settings |

---

## 🔄 الفلو الرئيسي (Main User Journey)

```
┌─────────────┐
│   Splash    │ (3s Auto)
└──────┬──────┘
       │
  ┌────┴────┐
  │ Welcome │
  └────┬────┘
       │ [ابدأ الآن]
       ↓
┌──────────────┐
│ User Type    │
│ Selection    │
└──────┬───────┘
       │ [معتمر]
       ↓
┌──────────────┐
│    Login     │
└──────┬───────┘
       │ [إرسال OTP]
       ↓
┌──────────────┐
│     OTP      │
└──────┬───────┘
       │ [تحقق]
       ↓
┌──────────────┐
│     Home     │ ◄─── نقطة البداية الأساسية
└──────┬───────┘
       │
   ┌───┼───┐
   │   │   │
   ↓   ↓   ↓
┌─────┐┌────┐┌───────┐
│Search││Trips││Profile│
└──┬──┘└─┬──┘└───┬───┘
   │     │       │
   ↓     ↓       ↓
┌──────────────────┐
│   Trip Details   │
└────────┬─────────┘
         │ [احجز]
         ↓
┌──────────────────┐
│  Trip Type       │
│  Selection       │
└────────┬─────────┘
         │
         ↓
┌──────────────────┐
│  Booking Form    │
└────────┬─────────┘
         │
         ↓
┌──────────────────┐
│ Review Booking   │
└────────┬─────────┘
         │
         ↓
┌──────────────────┐
│    Payment       │
└────────┬─────────┘
         │
         ↓
┌──────────────────┐
│  Confirmation    │
└────────┬─────────┘
         │
         ↓
┌──────────────────┐
│   My Trips       │
└────────┬─────────┘
         │
         ↓
┌──────────────────┐
│  Live Tracking   │
└────────┬─────────┘
         │ (بعد انتهاء الرحلة)
         ↓
┌──────────────────┐
│     Rating       │
└──────────────────┘
```

---

## 📱 تفاصيل الصفحات الرئيسية

### 🔐 1. صفحات التسجيل

#### 1.1 Splash → 1.2 Welcome → 1.3 User Type → 1.4 Login → 1.5 OTP → Home

**العناصر التفاعلية الرئيسية:**
- Login: `[رقم الجوال]` `[إرسال OTP]` `[Apple Sign In]` `[Google]` `[سجّل الآن]`
- OTP: `[4 أرقام]` `[تحقق]` `[أعد الإرسال]`
- Registration: جميع الحقول + `[إنشاء الحساب]`

---

### 🏠 2. الصفحة الرئيسية

#### Home Screen - المحور الرئيسي

**الأقسام:**
1. **Header**: `[☰ Menu]` `[🔔 Notifications]` `[👤 Profile]`
2. **Search Bar**: → Advanced Search
3. **Interactive Map**: Markers → Trip Details
4. **رحلات قريبة منك**: Cards → Trip Details
5. **رحلات نهاية الأسبوع**: Cards → Trip Details
6. **عروض خاصة**: Banners → Offer Details
7. **الشركات الموصى بها**: Cards → Company Details

**Bottom Navigation:**
- `[🏠 الرئيسية]` `[🔍 بحث]` `[📋 رحلاتي]` `[👤 حسابي]`

---

### 🔍 3. البحث

#### Search Flow: Home → Advanced Search → Results → Trip Details

**Advanced Search Filters:**
- مدينة الانطلاق (Multi-select)
- تاريخ الرحلة (Date Range)
- نوع الرحلة (رجال/نساء/عائلات)
- نطاق السعر (Range Slider)
- مستوى الخدمة (Dropdown)
- مدة الرحلة (Chips)
- الخدمات (Checkboxes)

**Search Results:**
- قائمة الرحلات
- فلترة سريعة (Chips)
- `[❤️ مفضلة]` `[⚖️ مقارنة]` `[احجز]`
- زر المقارنة العائم

---

### 📋 4. تفاصيل الرحلة

#### Trip Details Screen

**Tabs:**
1. **البرنامج اليومي**: جدول تفصيلي
2. **الخدمات**: فندق + نقل + وجبات + مرشد
3. **موقع التجمع**: خريطة + توجيهات
4. **التقييمات**: قائمة المراجعات

**الروابط:**
- `[الشركة]` → Company Details
- `[الفندق]` → Hotel Details
- `[النقل]` → Transport Details
- `[التقييمات]` → All Reviews
- `[احجز الآن]` → Trip Type Selection

---

### 💳 5. الحجز والدفع

#### Booking Flow: Trip Type → Form → Review → Payment → Confirmation

**Trip Type Selection:**
- `[👨 رجال]` `[👩 نساء]` `[👨‍👩‍👧 عائلات]`

**Booking Form:**
- بيانات المسافر الرئيسي
- عدد الأفراد
- `[+ إضافة أفراد العائلة]` → Family Members Screen

**Family Members:**
- قائمة الأفراد (ذكور/إناث/أطفال)
- حقول لكل فرد

**Review Booking:**
- ملخص الرحلة
- قائمة المسافرين
- إجمالي التكلفة
- `[رمز خصم]` (optional)

**Payment:**
- طرق الدفع (Mada / Apple Pay / STC Pay / Visa)
- `[ادفع الآن]` → Payment Gateway

**Confirmation:**
- رقم الحجز
- QR Code
- موقع التجمع
- معلومات الاتصال
- `[تحميل PDF]` `[مشاركة]`

---

### 📱 6. إدارة الرحلات

#### My Trips Screen

**Tabs:**
- القادمة (Upcoming)
- الجارية (In Progress)
- السابقة (Past)
- الملغية (Cancelled)

**Booked Trip Details:**
- تفاصيل الرحلة
- قائمة المسافرين
- معلومات الاتصال
- `[إلغاء الحجز]` `[تتبع الرحلة]` `[تواصل مع الشركة]`

**Live Tracking:**
- خريطة GPS للباص
- الموقع الحالي
- الوقت المتوقع للوصول (ETA)
- معلومات السائق
- `[اتصل بالسائق]` `[شارك موقعي]`

---

### ⭐ 7. التقييمات

#### Rating Screen (بعد انتهاء الرحلة)

**أقسام التقييم:**
1. **السائق**: نجوم + تعليق
2. **المشرف**: نجوم + تعليق
3. **الخدمات العامة**: نجوم + تعليق
4. **رفع صور** (optional)

`[إرسال التقييم]` → Success → My Trips

---

### 👤 8. الملف الشخصي

#### Profile Screen

**الأقسام:**
- الصورة والمعلومات الأساسية
- `[تعديل الملف الشخصي]`
- نقاط الولاء: `1250 نقطة`
- `[رحلاتي]` `[المفضلة]` `[سجل الحجوزات]`
- `[الإعدادات]` `[الدعم]` `[تسجيل الخروج]`

**Loyalty Points:**
- الرصيد الحالي
- تاريخ النقاط
- `[استبدال النقاط]`
- العروض المتاحة

**Settings:**
- الإشعارات
- اللغة
- الوضع الليلي
- `[تغيير كلمة المرور]`
- `[حذف الحساب]`

---

## 🔗 روابط الانتقال السريعة

### من Home:
- Search Bar → `advanced_search_screen.dart`
- Trip Card → `trip_details_screen.dart`
- Company Card → `company_details_screen.dart`
- Notifications → `notifications_screen.dart`

### من Trip Details:
- احجز → `trip_type_selection_screen.dart`
- الشركة → `company_details_screen.dart`
- الفندق → `hotel_details_screen.dart`
- التقييمات → `all_reviews_screen.dart`

### من My Trips:
- Trip Card → `booked_trip_details_screen.dart`
- تتبع → `live_tracking_screen.dart`
- قيّم → `rating_screen.dart`

---

[📄 التالي: تطبيق الشركات →](./02_COMPANY_APP_FLOW.md)
