

https://github.com/user-attachments/assets/a995bc7f-57bc-42c0-8ffe-54258c5440b3

# 🚀 LinkedIn Pro: Advanced Automation & Outreach Suite
### نظام أتمتة وإدارة عملاء لينكد إن المتقدم

A professional lead generation and automated outreach system that integrates a **Laravel 12** control panel with autonomous **Python Selenium** agents and **Google Gemini AI**.

نظام متميز لإدارة العملاء والتواصل التلقائي على منصة لينكد إن، يدمج بين لوحة تحكم بـ **Laravel 12** ومحركات أتمتة مستقلة بلغة **Python (Selenium)** مع دمج الذكاء الاصطناعي **Google Gemini AI**.

---

> [!NOTE]  
> **Repository Scope | نطاق المستودع:**  
> This public repository serves as a portfolio showcase and contains only documentation and architectural designs. The proprietary source code is hosted in a private repository for security and intellectual property protection.  
> هذا المستودع العام مخصص للعرض والمحفظة البرمجية فقط ويحتوي على الشرح الفني والهندسي للمشروع. الكود البرمجي الفعلي محفوظ بالكامل في مستودع خاص لحماية الملكية الفكرية والأمان.

---

## 🏗️ Architectural Overview & Data Flow / بنية النظام وتدفق البيانات

```mermaid
graph TD
    A["Web UI (Laravel Dashboard)"] -- "Spawns Background Process (proc_open)" --> B["PythonRunner Service"]
    B --> C["Python Automation Scripts"]
    C -- "Undetected Chromedriver" --> D["LinkedIn Platform"]
    C -- "JSON Callbacks / DB Queries" --> E["MySQL Database & Logs"]
    E --> A
```

---

## 🇺🇸 English Version

### 🌟 Core Workflows & Features

#### 1. Lead Extraction Flow (Google Dorking Engine)
Bypasses LinkedIn's commercial search limits by converting search filters into targeted Google Dork queries routed through geographic subdomains.

```mermaid
sequenceDiagram
    participant User as User / Admin
    participant Laravel as Laravel Backend
    participant Python as Python Scraper
    participant Google as Google Search API
    participant DB as MySQL Database

    User->>Laravel: Submits LinkedIn Search URL
    Laravel->>Python: Passes payload via secure temporary JSON
    Python->>Python: Parses URL parameters (Title, Geo, Industry)
    Python->>Python: Assembles advanced Google Dork Query
    Python->>Google: Executes query with randomized User-Agents
    Google-->>Python: Returns organic profile search results
    Python->>Laravel: Calls back with extracted profile details
    Laravel->>DB: Runs transactional uniqueness check & inserts
    DB-->>User: Renders leads list on Dashboard
```

#### 2. Connection Builder (Macro Replay Engine)
Automates invitations using DPI-calibrated mouse clicks. The agent automatically detects profile button layouts and triggers the correct connection flow (direct connect vs dropdown connect).

```mermaid
graph TD
    Start["Access Profile URL"] --> Check["Evaluate DOM Elements"]
    Check -->|Connect Button Visible| S1["Execute Scenario 1 Macro: Click Connect"]
    Check -->|Connect Button Hidden| S2["Execute Scenario 2: Click 'More' -> Click 'Connect'"]
    S1 --> CheckSent["Verify Invitation Sent Confirmation"]
    S2 --> CheckSent
    CheckSent -->|Success| Save["Update status to 'connection_sent'"]
    CheckSent -->|Failed/Blocked| Error["Log Error Reason in DB"]
```

#### 3. AI-Personalized Messaging & Response Tracking
* **Gemini AI Integration**: Generates contextual invitation and follow-up messages based on target's profile data.
* **Keystroke Simulation**: Types out messages with randomized delays (50-150ms) to bypass automation checks.
* **Inbox Monitoring**: Periodic background scans automatically mark leads as `Replied` when they respond.

### 🛠️ Technology Stack
* **Control Panel**: Laravel 12, Alpine.js, Tailwind CSS / Custom CSS.
* **Automation Core**: Python 3.13, Selenium, `undetected-chromedriver`.
* **AI Orchestration**: Google Gemini 2.5 Flash / Pro API.
* **Database**: MySQL.

---

## 🇪🇬 النسخة العربية (Arabic Version)

### 🌟 مسارات العمل والمميزات الرئيسية

#### 1. تدفق استخراج العملاء المستهدفين (محرك Google Dorking)
يتخطى قيود البحث التجاري للينكد إن عبر تحويل فلاتر البحث إلى استعلامات بحث متقدمة في جوجل وتوجيهها إقليمياً.

```mermaid
sequenceDiagram
    participant User as المستخدم / المدير
    participant Laravel as لوحة التحكم (لارافيل)
    participant Python as سكربت الاستخراج (بايثون)
    participant Google as محرك بحث جوجل
    participant DB as قاعدة البيانات (MySQL)

    User->>Laravel: إرسال رابط بحث لينكد إن المستهدف
    Laravel->>Python: تمرير البيانات عبر ملف JSON مشفر ومؤقت
    Python->>Python: تحليل معايير البحث (الوظيفة، الموقع، المجال)
    Python->>Python: تكوين استعلام Google Dork المتقدم
    Python->>Google: تنفيذ البحث بمتصفحات ووكلاء مستخدم عشوائيين
    Google-->>Python: إرجاع روابط الملفات الشخصية المطابقة
    Python->>Laravel: إرسال البيانات المستخرجة لحظياً
    Laravel->>DB: فحص تكرار الحسابات وحفظ البيانات الجديدة
    DB-->>User: عرض قوائم العملاء الجدد في لوحة التحكم
```

#### 2. منشئ الاتصالات التلقائي (محرك محاكاة السيناريوهات)
يؤتمت إرسال الطلبات بالاعتماد على إحداثيات شاشة دقيقة. يتعرف البوت تلقائياً على واجهة زر الإضافة ويحدد سيناريو الضغط المناسب (إضافة مباشرة أم عبر قائمة المزيد).

```mermaid
graph TD
    Start["الدخول إلى ملف العميل الشخصي"] --> Check["تحليل عناصر الصفحة (DOM)"]
    Check -->|زر الإضافة ظاهر| S1["تنفيذ السيناريو 1: الضغط على الإضافة مباشرة"]
    Check -->|زر الإضافة مخفي| S2["تنفيذ السيناريو 2: الضغط على 'المزيد' ثم 'إضافة'"]
    S1 --> CheckSent["التحقق من ظهور رسالة تأكيد الإرسال"]
    S2 --> CheckSent
    CheckSent -->|تم بنجاح| Save["تحديث حالة العميل إلى 'تم إرسال الطلب'"]
    CheckSent -->|فشلت العملية| Error["تسجيل سبب الفشل في قاعدة البيانات للتحليل"]
```

#### 3. مراسلة معززة بالذكاء الاصطناعي وتتبع الردود
* **دمج مع Gemini AI**: صياغة رسائل مخصصة للعملاء بناءً على مسمياتهم الوظيفية الحالية.
* **محاكاة الكتابة**: كتابة الرسائل حرفاً بحرف بتأخير عشوائي مابين (50 إلى 150 مللي ثانية) لتفادي الكشف.
* **مراقبة صندوق الوارد**: فحص دوري يقوم بتحديث حالة العميل إلى "تم الرد" تلقائياً في لوحة التحكم عند استلام رده.

### 🛠️ التقنيات البرمجية المستخدمة
* **لوحة التحكم والخلفية البرمجية**: Laravel 12، مع واجهات CSS وتأثيرات بصرية متقدمة.
* **محرك الأتمتة**: لغة Python 3، ومكتبة Selenium، ومتصفح `undetected-chromedriver`.
* **الذكاء الاصطناعي**: واجهة برمجة تطبيقات Google Gemini 2.5.
* **قاعدة البيانات**: MySQL.

---

## ⚠️ Disclaimer | إخلاء المسؤولية
This tool is built for educational and research purposes. Automating LinkedIn interactions may violate LinkedIn's Terms of Service. Use responsibly and at your own risk.  
تم تطوير هذه الأداة لأغراض تعليمية وبحثية فقط. قد تؤدي أتمتة العمليات على لينكد إن إلى انتهاك شروط الخدمة الخاصة بالمنصة. استخدمها على مسؤوليتك الخاصة.
