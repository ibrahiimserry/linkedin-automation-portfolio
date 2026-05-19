# 🔗 LinkedIn Automation System | نظام أتمتة لينكد إن المتقدم

A high-performance, intelligent automation system designed to streamline LinkedIn outreach, lead generation, and automated messaging. Built on a modern **Laravel 12** backend coupled with robust **Python Selenium (undetected-chromedriver)** agents.

نظام أتمتة ذكي وعالي الأداء مصمم لتسهيل عمليات التواصل على لينكد إن، وتوليد العملاء المستهدفين، والمراسلة التلقائية. يعتمد على لوحة تحكم متكاملة بـ **Laravel 12** مع محركات أتمتة قوية بلغة **Python (Selenium)**.

---

> [!NOTE]  
> **Repository Scope | نطاق المستودع:**  
> This public repository serves as a portfolio showcase and contains only documentation. The proprietary source code is hosted in a private repository for security and intellectual property protection.  
> هذا المستودع العام مخصص للعرض والمحفظة البرمجية فقط ويحتوي على الشرح التوضيحي. الكود البرمجي الفعلي محفوظ بالكامل في مستودع خاص لحماية الملكية الفكرية والأمان.

---

## 📺 Video Showcase | عرض الفيديو التوضيحي
Below is a video walkthrough demonstrating the live execution of the tool:  
يوجد أدناه مقطع فيديو توضيحي يستعرض آلية عمل الأداة ولوحة التحكم بشكل حي:

📁 **[Watch the LinkedIn Pro Demo Video | شاهد الفيديو التوضيحي](DEMO_VIDEO_LINK_HERE)**

---

## 🏗️ Architecture Overview | نظرة عامة على بنية النظام

```
┌─────────────────────────────────────────────────────────────────────┐
│                        BROWSER (Arabic RTL UI)                      │
│  Settings | Scraped Leads | Auto-Connect | Auto-Message             │
└──────────────────────────┬──────────────────────────────────────────┘
                           │  HTTP (web routes)
                           ▼
┌─────────────────────────────────────────────────────────────────────┐
│                     LARAVEL BACKEND (PHP)                           │
│                                                                     │
│  Controllers          Services               Models                 │
│  ─────────────        ────────────           ──────                 │
│  SettingsController   LinkedInUrlParser       Setting               │
│  LeadsController      PythonRunner            Lead                  │
│  AutoConnectController                        ScrapeSession         │
│  AutoMessageController                        MessageTemplate       │
│                                               SentMessage           │
└──────────┬──────────────────────────────────┬───────────────────────┘
           │  proc_open (background)           │  HTTP POST callbacks
           ▼                                   │
┌──────────────────────┐                       │
│   PYTHON SCRIPTS     │ ──────────────────────┘
│                      │
│  url_parser.py       │  URL → Google Dork conversion
│  scraper.py          │  Google Dork → LinkedIn profile list
│  auto_connect.py     │  Undetected Chrome → send connection requests
│  auto_message.py     │  Undetected Chrome → send personalised messages
└──────────────────────┘
           │
           ▼
┌──────────────────────┐
│   MYSQL DATABASE     │
└──────────────────────┘
```

---

## 🇺🇸 English Version

### ✨ Key Capabilities & Features
* **🔍 Precision Lead Extraction (Google Dorking)**: Converts any LinkedIn search filter URL into an advanced Google search query to bypass LinkedIn search limits.
* **⚡ Autonomous Connection Builder (Macro Replay)**: Identifies connection layouts and executes connection flows with automated safety buffers.
* **🤖 AI-Enriched Messaging**: Generates personalized outreach messages using Gemini AI based on the lead's profile data.
* **📬 Inbox Monitor & Replied Tracker**: Background daemon scans the inbox, automatically tagging leads as `Replied` when they respond.
* **🛡️ Security Architecture**: Plain credentials are never exposed; AES-256 encrypted configuration stored in the database.

### 🛠️ Tech Stack
* **Backend & UI**: Laravel 12, Alpine.js, Tailwind CSS / Custom CSS Gradient UI.
* **Automation Core**: Python 3.13, Selenium, `undetected-chromedriver`.
* **AI Orchestration**: Google Gemini 2.5 Flash / Pro API.
* **Database**: MySQL.

---

## 🇪🇬 النسخة العربية (Arabic Version)

### ✨ المميزات والقدرات الرئيسية
* **🔍 استخراج دقيق للعملاء (Google Dorking)**: يحول روابط فلاتر البحث في لينكد إن إلى صيغ بحث متقدمة في جوجل لتخطي قيود البحث التجاري للينكد إن.
* **⚡ منشئ اتصالات تلقائي ذكي**: يتعرف على واجهات الإضافة ويقوم بمحاكاة نقرات الماوس وحركات العنصر البشري لإرسال طلبات الاتصال بأمان كامل.
* **🤖 مراسلة محسنة بالذكاء الاصطناعي**: يولد رسائل ترحيبية مخصصة للعملاء بالاعتماد على الذكاء الاصطناعي (Gemini AI) بناءً على بياناتهم الشخصية.
* **📬 مراقبة صندوق الوارد وتتبع الردود**: فاحص خلفي يقوم بمسح الرسائل الواردة بشكل دوري وتصنيف العميل كـ "تم الرد" تلقائياً عند إرساله أي رسالة.
* **🛡️ معايير أمان عالية**: يتم تشفير بيانات الحسابات الحساسة تلقائياً في قاعدة البيانات باستخدام خوارزميات التشفير المتقدمة (AES-256).

### 🛠️ التقنيات المستخدمة
* **لوحة التحكم والخلفية البرمجية**: Laravel 12، مع واجهات وتنسيقات CSS وتأثيرات بصرية متقدمة.
* **محرك الأتمتة**: لغة Python 3، ومكتبة Selenium، ومتصفح `undetected-chromedriver` لتخطي أنظمة الحماية.
* **الذكاء الاصطناعي**: واجهة برمجة تطبيقات Google Gemini 2.5 Flash / Pro.
* **قاعدة البيانات**: MySQL.

---

## ⚠️ Disclaimer | إخلاء المسؤولية
This tool is built for educational and research purposes. Automating LinkedIn interactions may violate LinkedIn's Terms of Service. Use responsibly and at your own risk.  
تم تطوير هذه الأداة لأغراض تعليمية وبحثية فقط. قد تؤدي أتمتة العمليات على لينكد إن إلى انتهاك شروط الخدمة الخاصة بالمنصة. استخدمها على مسؤوليتك الخاصة.
