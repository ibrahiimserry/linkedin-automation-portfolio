https://github.com/user-attachments/assets/a995bc7f-57bc-42c0-8ffe-54258c5440b3

# 🚀 LinkedIn Pro: Advanced Automation & Outreach Suite

A professional lead generation and automated outreach system that integrates a **Laravel 12** control panel with autonomous **Python Selenium** agents and **Google Gemini AI**.

> [!NOTE]  
> **Repository Scope:**  
> This public repository serves as a portfolio showcase and contains only documentation and architectural designs. The proprietary source code is hosted in a private repository for security and intellectual property protection.

---

## 🏗️ System Architecture & Complex Data Flow

This diagram illustrates the multi-tier architecture, showing how the control dashboard spawns background processes, schedules resources, and communicates with AI engines and browser drivers to automate operations.

```mermaid
graph TB
    subgraph WebInterface ["💻 Control Center (Laravel 12 Dashboard)"]
        UI["Vue/Alpine UI Dashboard"]
        C_Lead["Leads Controller (Deduplication & Queues)"]
        C_Conn["Auto-Connect Controller (Macro Batches)"]
        C_Msg["Auto-Message Controller (AI Orchestrator)"]
        C_Inbox["Inbox & Response Controller"]
    end

    subgraph BackendServices ["⚙️ Backend & DB Layer"]
        DB[("MySQL Database<br>leads | settings | sent_messages | inbox")]
        PR["PythonRunner Service (proc_open Spawner)"]
    end

    subgraph AutomationEngine ["🤖 Autonomous Python Agents"]
        Scraper["scraper.py<br>(Google Dork Parser & Subdomain Router)"]
        Connector["auto_connect.py<br>(Macro Replay & DPI Calibration)"]
        Messenger["auto_message.py<br>(Personalized Outreach Driver)"]
        Inbox["inbox_checker.py<br>(Background Response Polling Daemon)"]
    end

    subgraph APIs ["🌐 External Integrations & Browser"]
        Gemini["Google Gemini Pro 2.5 API<br>(Contextual Prompt Processing)"]
        UC["undetected-chromedriver (Chrome)<br>(Profile Cache & Human Typing Emulation)"]
        GoogleSearch["Google Search Engine"]
        LinkedIn["LinkedIn Platform"]
    end

    %% UI Interactions
    UI --> C_Lead & C_Conn & C_Msg & C_Inbox
    C_Lead & C_Conn & C_Msg & C_Inbox --> DB
    
    %% Spawning Processes
    C_Lead -->|Trigger Scrape| PR
    C_Conn -->|Trigger Connect| PR
    C_Msg -->|Trigger Message| PR
    C_Inbox -->|Trigger Monitor| PR
    
    PR -->|Execute CLI| Scraper & Connector & Messenger & Inbox
    
    %% Scraper Data Flow
    Scraper -->|Query Subdomain| GoogleSearch
    GoogleSearch -->|Return Profiles| Scraper
    Scraper -->|Callback: HTTP POST| C_Lead
    
    %% AI Generation Flow
    Messenger -->|Request Dynamic Text| Gemini
    Gemini -->|Return Personalized Message| Messenger
    
    %% Chrome Automation Flow
    Connector & Messenger & Inbox -->|Control API| UC
    UC -->|Interactions / Clicks| LinkedIn
    
    %% Database Updates
    Connector -->|Log Action| DB
    Messenger -->|Update Sent Status| DB
    Inbox -->|Sync Incoming Messages| DB
    
    classDef control fill:#1e293b,stroke:#38bdf8,stroke-width:2px,color:#f8fafc;
    classDef backend fill:#0f172a,stroke:#34d399,stroke-width:2px,color:#f8fafc;
    classDef engine fill:#312e81,stroke:#a78bfa,stroke-width:2px,color:#f8fafc;
    classDef api fill:#451a03,stroke:#fb923c,stroke-width:2px,color:#f8fafc;
    
    class UI,C_Lead,C_Conn,C_Msg,C_Inbox control;
    class DB,PR backend;
    class Scraper,Connector,Messenger,Inbox engine;
    class Gemini,UC,GoogleSearch,LinkedIn api;
```

### 🌟 Core Features & Workflows
* **🔍 Lead Extraction (Google Dorking)**: Bypasses LinkedIn's commercial search limits by converting search filters into targeted Google Dork queries.
* **⚡ Connection Builder (Macro Replay)**: Automates invitations using DPI-calibrated mouse clicks and automatically adapts to profile button layouts.
* **🤖 AI-Personalized Messaging**: Generates contextual invitation and follow-up messages using Google Gemini AI.
* **📬 Inbox Monitoring**: Periodic background scans automatically mark leads as `Replied` on the dashboard when they respond.

### 🛠️ Technology Stack
* **Control Panel**: Laravel 12, Alpine.js, Tailwind CSS / Custom CSS.
* **Automation Core**: Python 3.13, Selenium, `undetected-chromedriver`.
* **AI Orchestration**: Google Gemini 2.5 Flash / Pro API.
* **Database**: MySQL.

---

# 🚀 نظام أتمتة وإدارة عملاء لينكد إن المتقدم

نظام متميز لإدارة العملاء والتواصل التلقائي على منصة لينكد إن، يدمج بين لوحة تحكم بـ **Laravel 12** ومحركات أتمتة مستقلة بلغة **Python (Selenium)** مع دمج الذكاء الاصطناعي **Google Gemini AI**.

> [!NOTE]  
> **نطاق المستودع:**  
> هذا المستودع العام مخصص للعرض والمحفظة البرمجية فقط ويحتوي على الشرح الفني والهندسي للمشروع. الكود البرمجي الفعلي محفوظ بالكامل في مستودع خاص لحماية الملكية الفكرية والأمان.

---

## 🏗️ نظرة عامة على بنية النظام وهندسة البيانات

يوضح هذا المخطط الهيكلي بنية النظام متعددة الطبقات، وكيفية إطلاق العمليات في الخلفية وجدولة المهام والتواصل مع نماذج الذكاء الاصطناعي ومحركات المتصفح لتنفيذ العمليات.

```mermaid
graph TB
    subgraph WebInterface ["💻 مركز التحكم (لوحة تحكم لارافيل 12)"]
        UI["واجهة المستخدم ولوحة البيانات"]
        C_Lead["متحكم العملاء (إلغاء التكرار والجدولة)"]
        C_Conn["متحكم الاتصالات (دفعات الماكرو التلقائية)"]
        C_Msg["متحكم الرسائل (صياغة الذكاء الاصطناعي)"]
        C_Inbox["متحكم صندوق الوارد والردود"]
    end

    subgraph BackendServices ["⚙️ طبقة الخدمات وقاعدة البيانات"]
        DB[("قاعدة بيانات MySQL<br>العملاء | الإعدادات | سجل الرسائل")]
        PR["خدمة تشغيل سكربتات بايثون (PythonRunner)"]
    end

    subgraph AutomationEngine ["🤖 محركات أتمتة بايثون المستقلة"]
        Scraper["مستخرج البيانات scraper.py<br>(توجيه النطاقات والبحث الجغرافي)"]
        Connector["منشئ الاتصالات auto_connect.py<br>(محاكاة النقرات وحل إحداثيات الشاشة)"]
        Messenger["منشئ الرسائل auto_message.py<br>(مراسلة مخصصة وبسرعات بشرية)"]
        Inbox["فاحص الرسائل inbox_checker.py<br>(مراقبة صندوق الوارد وجلب الردود)"]
    end

    subgraph APIs ["🌐 التكامل الخارجي وحماية المتصفح"]
        Gemini["واجهة Google Gemini API<br>(توليد نصوص ذكية مخصصة)"]
        UC["متصفح كروم الآمن (undetected-chromedriver)<br>(محاكاة الكتابة وملفات التعريف المعزولة)"]
        GoogleSearch["محرك بحث جوجل"]
        LinkedIn["منصة لينكد إن"]
    end

    %% UI Interactions
    UI --> C_Lead & C_Conn & C_Msg & C_Inbox
    C_Lead & C_Conn & C_Msg & C_Inbox --> DB
    
    %% Spawning Processes
    C_Lead -->|بدء الاستخراج| PR
    C_Conn -->|بدء طلبات الإضافة| PR
    C_Msg -->|بدء المراسلة| PR
    C_Inbox -->|بدء مراقبة الرسائل| PR
    
    PR -->|تشغيل السكربتات| Scraper & Connector & Messenger & Inbox
    
    %% Scraper Data Flow
    Scraper -->|بحث متقدم بالنطاق الجغرافي| GoogleSearch
    GoogleSearch -->|إرجاع روابط الملفات الشخصية| Scraper
    Scraper -->|إشعار خلفي (HTTP POST)| C_Lead
    
    %% AI Generation Flow
    Messenger -->|طلب توليد نص مخصص للعميل| Gemini
    Gemini -->|إرجاع نص الرسالة الذكي| Messenger
    
    %% Chrome Automation Flow
    Connector & Messenger & Inbox -->|التحكم في العمليات| UC
    UC -->|تنفيذ النقرات والمحاكاة| LinkedIn
    
    %% Database Updates
    Connector -->|تحديث حالة الإرسال| DB
    Messenger -->|تحديث حالة الرسالة| DB
    Inbox -->|حفظ الرسائل الواردة وتحديث الردود| DB
    
    classDef control fill:#1e293b,stroke:#38bdf8,stroke-width:2px,color:#f8fafc;
    classDef backend fill:#0f172a,stroke:#34d399,stroke-width:2px,color:#f8fafc;
    classDef engine fill:#312e81,stroke:#a78bfa,stroke-width:2px,color:#f8fafc;
    classDef api fill:#451a03,stroke:#fb923c,stroke-width:2px,color:#f8fafc;
    
    class UI,C_Lead,C_Conn,C_Msg,C_Inbox control;
    class DB,PR backend;
    class Scraper,Connector,Messenger,Inbox engine;
    class Gemini,UC,GoogleSearch,LinkedIn api;
```

### 🌟 مسارات العمل والمميزات الرئيسية
* **🔍 استخراج العملاء المستهدفين (Google Dorking)**: يتخطى قيود البحث التجاري للينكد إن عبر تحويل فلاتر البحث إلى استعلامات بحث متقدمة في جوجل وتوجيهها إقليمياً.
* **⚡ منشئ الاتصالات التلقائي**: يؤتمت إرسال طلبات الإضافة بالاعتماد على إحداثيات دقيقة ويتعرف تلقائياً على واجهة الأزرار وسيناريو الضغط المناسب.
* **🤖 مراسلة معززة بالذكاء الاصطناعي**: صياغة رسائل مخصصة للعملاء بناءً على مسمياتهم الوظيفية الحالية باستخدام Gemini AI.
* **📬 مراقبة صندوق الوارد**: فحص دوري يقوم بتحديث حالة العميل إلى "تم الرد" تلقائياً في لوحة التحكم عند استلام رده.

### 🛠️ التقنيات البرمجية المستخدمة
* **لوحة التحكم والخلفية البرمجية**: Laravel 12، مع واجهات CSS وتأثيرات بصرية متقدمة.
* **محرك الأتمتة**: لغة Python 3، ومكتبة Selenium، ومتصفح `undetected-chromedriver`.
* **الذكاء الاصطناعي**: واجهة برمجة تطبيقات Google Gemini 2.5.
* **قاعدة البيانات**: MySQL.

---

## ⚠️ Disclaimer | إخلاء المسؤولية
This tool is built for educational and research purposes. Automating LinkedIn interactions may violate LinkedIn's Terms of Service. Use responsibly and at your own risk.  
تم تطوير هذه الأداة لأغراض تعليمية وبحثية فقط. قد تؤدي أتمتة العمليات على لينكد إن إلى انتهاك شروط الخدمة الخاصة بالمنصة. استخدمها على مسؤوليتك الخاصة.
