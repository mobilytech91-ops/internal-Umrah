# 🔄 الصفحات المشتركة - Shared Screens

[← العودة للفهرس](./00_MASTER_INDEX.md)

## 📋 جدول الصفحات (18 صفحة)

| # | الصفحة | المسار | المستخدم |
|---|--------|--------|----------|
| **المساعدة والدعم** |
| 1 | FAQ | `screens/shared/support/faq_screen.dart` | All |
| 2 | Contact Us | `screens/shared/support/contact_us_screen.dart` | User, Company |
| 3 | Technical Support | `screens/shared/support/technical_support_screen.dart` | User, Company |
| 4 | Chat Support | `screens/shared/support/chat_support_screen.dart` | User, Company |
| **القانونية** |
| 5 | Terms & Conditions | `screens/shared/legal/terms_screen.dart` | All |
| 6 | Privacy Policy | `screens/shared/legal/privacy_screen.dart` | All |
| 7 | Refund Policy | `screens/shared/legal/refund_screen.dart` | User, Company |
| **الإعلامية** |
| 8 | About App | `screens/shared/info/about_screen.dart` | All |
| 9 | News & Updates | `screens/shared/info/news_screen.dart` | User, Company |
| 10 | How It Works | `screens/shared/info/how_it_works_screen.dart` | User |
| **الإشعارات** |
| 11 | Notifications | `screens/shared/notifications/notifications_screen.dart` | All |
| 12 | Notification Settings | `screens/shared/notifications/notification_settings_screen.dart` | All |
| **الخرائط** |
| 13 | Map View | `screens/shared/maps/map_view_screen.dart` | User, Company |
| 14 | Location Picker | `screens/shared/maps/location_picker_screen.dart` | Company |
| **الطوارئ** |
| 15 | Emergency | `screens/shared/emergency/emergency_screen.dart` | User |
| 16 | Safety Tracking | `screens/shared/emergency/safety_tracking_screen.dart` | User |
| **الوسائط** |
| 17 | Image Viewer | `screens/shared/media/image_viewer_screen.dart` | All |
| 18 | PDF Viewer | `screens/shared/media/pdf_viewer_screen.dart` | All |

---

## 📱 الأقسام الرئيسية

### 1. المساعدة والدعم

#### FAQ Screen
- بحث في الأسئلة
- تصنيفات (الحجز، الدفع، الإلغاء)
- Expandable answers
- رابط للدعم

#### Contact Us
- الهاتف
- واتساب
- البريد الإلكتروني
- العنوان + خريطة
- نموذج اتصال

#### Technical Support
- نوع المشكلة
- وصف المشكلة
- رفع صور
- معلومات الجهاز التلقائية
- تتبع البلاغات

#### Chat Support
- دردشة فورية
- AI Bot
- نقل للموظف
- إرفاق ملفات

---

### 2. القانونية

#### Terms & Conditions
- المقدمة
- قبول الشروط
- الحساب والتسجيل
- الحجز والدفع
- المسؤوليات
- الخصوصية

#### Privacy Policy
- جمع البيانات
- استخدام البيانات
- مشاركة البيانات
- أمان البيانات
- حقوق المستخدم

#### Refund Policy
- الإلغاء قبل 48 ساعة: 100%
- الإلغاء قبل 24 ساعة: 50%
- أقل من 24 ساعة: 0%
- حالات خاصة

---

### 3. الإعلامية

#### About App
- الرؤية والرسالة
- فريق العمل
- الشركاء
- الجوائز
- معلومات الاتصال
- وسائل التواصل

#### News & Updates
- الأخبار
- التحديثات
- الإعلانات

#### How It Works
- خطوات الاستخدام
- شرح مبسط
- فيديو توضيحي

---

### 4. الإشعارات

#### Notifications Screen
أنواع الإشعارات:
- 🔴 حجز جديد
- 🟢 تأكيد
- 🟡 تذكير
- 💰 دفعة
- ℹ️ معلومة
- ⭐ تقييم

Features:
- Tabs (الكل / غير مقروءة)
- Deep linking
- Swipe actions
- Badge counter

#### Notification Settings
إعدادات:
- 📱 إشعارات التطبيق
- 📧 البريد الإلكتروني
- 💬 SMS
- 🔕 عدم الإزعاج (وقت محدد)

تصنيفات:
- الحجوزات
- الرحلات
- المدفوعات
- التقييمات
- العروض

---

### 5. الخرائط

#### Map View
- عرض الخريطة التفاعلية
- Markers للرحلات/المواقع
- Info Window عند الضغط
- توجيهات (Google Maps)
- مشاركة الموقع

#### Location Picker
- اختيار موقع على الخريطة
- بحث عن عنوان
- GPS الحالي
- تأكيد الموقع

---

### 6. الطوارئ والأمان

#### Emergency Screen
أرقام الطوارئ:
- 📞 الشرطة: 999
- 🚑 الإسعاف: 997
- 🚒 الدفاع المدني: 998
- 📱 الشركة المنظمة
- 💬 الدعم الفني

إجراءات سريعة:
- [اتصل الآن]
- [مشاركة الموقع]
- [إبلاغ عن مشكلة]

#### Safety Tracking
- مشاركة الموقع مع العائلة
- تنبيهات الأمان
- SOS Button
- جهات اتصال الطوارئ

---

### 7. الوسائط

#### Image Viewer
- عرض الصور بالحجم الكامل
- Zoom in/out
- Pinch to zoom
- Swipe للتنقل
- مشاركة/تحميل

#### PDF Viewer
- عرض ملفات PDF
- Zoom
- تصفح الصفحات
- مشاركة/تحميل
- طباعة

---

## 🔧 Widgets مشتركة

### Bottom Sheets
```dart
widgets/shared/bottom_sheets/
- filter_bottom_sheet.dart
- sort_bottom_sheet.dart
- action_bottom_sheet.dart
```

### Dialogs
```dart
widgets/shared/dialogs/
- confirmation_dialog.dart
- info_dialog.dart
- error_dialog.dart
- loading_dialog.dart
```

### Cards
```dart
widgets/shared/cards/
- trip_card.dart
- booking_card.dart
- company_card.dart
- review_card.dart
```

### Buttons
```dart
widgets/shared/buttons/
- primary_button.dart
- secondary_button.dart
- icon_button.dart
- floating_action_button.dart
```

### Input Fields
```dart
widgets/shared/inputs/
- text_field.dart
- dropdown.dart
- date_picker.dart
- search_bar.dart
```

### Loading States
```dart
widgets/shared/loading/
- shimmer_loading.dart
- circular_progress.dart
- skeleton_loader.dart
```

### Empty States
```dart
widgets/shared/empty/
- no_data.dart
- no_results.dart
- no_connection.dart
```

---

## 🎨 Theme Components

### Colors
```dart
lib/core/theme/colors.dart

Primary: #1B5E20 (أخضر)
Secondary: #FFB300 (ذهبي)
Accent: #00838F (تركواز)
Background: #FAFAFA
Error: #D32F2F
Success: #388E3C
```

### Typography
```dart
lib/core/theme/typography.dart

Heading1: 24sp Bold
Heading2: 20sp Bold
Heading3: 18sp SemiBold
Body: 16sp Regular
Caption: 14sp Regular
```

### Spacing
```dart
lib/core/theme/spacing.dart

xs: 4px
sm: 8px
md: 16px
lg: 24px
xl: 32px
```

---

## 🔗 Navigation Helpers

### Deep Linking
```dart
lib/navigation/deep_link_handler.dart

Routes:
- miqat://trip/:id
- miqat://booking/:id
- miqat://company/:id
- miqat://notification/:id
```

### Route Guards
```dart
lib/navigation/route_guards.dart

- AuthGuard
- RoleGuard (User/Company/Admin)
- SubscriptionGuard
```

---

## 📡 API Integration

### Base URLs
```
Production: https://api.miqat.sa/v1
Staging: https://staging-api.miqat.sa/v1
Development: http://localhost:3000/api/v1
```

### Shared Endpoints
```
GET /api/support/faq
POST /api/support/contact
GET /api/legal/terms
GET /api/legal/privacy
GET /api/news
GET /api/notifications
POST /api/notifications/read
```

---

## 🔐 Security Features

### Authentication
- JWT Token
- Refresh Token
- Biometric (Face ID / Touch ID)
- Two-Factor Authentication (2FA)

### Encryption
- SSL/TLS
- End-to-End Encryption للدردشة
- Encrypted Storage للبيانات الحساسة

### Permissions
```dart
- Location (GPS)
- Camera (للصور)
- Gallery (رفع صور)
- Notifications
- Phone (للاتصال)
```

---

## 📊 Analytics Events

### Shared Events
```dart
- screen_view
- button_click
- search
- filter_applied
- share
- download
- support_contact
```

---

## 🌐 Localization

### Supported Languages
- العربية (ar) - Primary
- English (en) - Secondary

### Translation Files
```
lib/l10n/
- app_ar.arb
- app_en.arb
```

---

[✅ النهاية - جميع الملفات جاهزة](./00_MASTER_INDEX.md)
