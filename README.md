# 🚀 LinkedIn Pro: Advanced Automation Suite

A high-performance, robust, and intelligent automation system designed to streamline LinkedIn outreach, lead generation, and automated messaging. Built on a modern **Laravel 12** backend coupled with robust **Python Selenium (undetected-chromedriver)** agents, this tool automates target extraction, macro replay connection building, and AI-powered inbox follow-ups.

> [!NOTE]  
> **Repository Scope:** This public repository serves as a portfolio showcase. The proprietary source code is hosted in a private repository for security and intellectual property protection.

---

## 📺 Video Demonstration & Showcase
Below is a video walkthrough demonstrating the live execution of the extraction, connection macro replays, and the admin interface in action:

📁 **[Watch the LinkedIn Pro Demo Video](DEMO_VIDEO_LINK_HERE)** *(Replace with your video link)*

---

## ✨ Key Capabilities & Features

### 1. 🔍 Precision Lead Extraction (Google Dorking Scraper)
* **Automated Dorking**: Converts any LinkedIn search filter URL into an advanced Google search query to bypass LinkedIn commercial search limits.
* **Country Subdomain Mapping**: Automatically routes search queries through global subdomains (supporting 190+ countries) matching the target region.
* **Automated Data Capture**: Captures names, headlines, current company, location, and avatars directly to a centralized leads database.
* **Smart Duplication Guard**: Compares scraped leads against existing contacts to prevent duplicate outreach.

### 2. ⚡ Autonomous Connection Builder (Macro Replay Engine)
* **Human-Mimicking Interaction**: Uses localized coordinate replay to bypass standard automation detectors.
* **Dynamic Scenario Replay**: Identifies the layout (visible Connect button vs. dropdown dropdowns) and dynamically executes the exact connection flow.
* **Automated Safety Buffers**: Implements humanized delay ranges, randomized page load stabilization pauses, and configurable automation speed profiles (e.g., *Safe Mode*).

### 3. 🤖 AI-Enriched Messaging & Outreach
* **Gemini AI Integration**: Generates personalized, context-aware outreach messages based on the lead's profile data, company, and industry.
* **Auto-Message Dispatcher**: Automatically opens conversation streams, types messages, and manages delivery.
* **Live Status Log**: Full real-time feedback with live progress percentages, estimated time of completion (ETA), and interactive log feeds.

### 4. 📬 Smart Inbox Monitor & Replied Tracker
* **Background Inbox Daemon**: Periodically scans the LinkedIn inbox for incoming messages.
* **Auto-Status Progression**: Automatically tags leads as `Replied` when they respond, allowing operators to easily track hot leads.
* **Centralized Dashboard**: Fully-featured dashboard built with dark-mode aesthetic, detailed stats panels, and customizable automation configurations.

---

## 🛠️ Architecture & Tech Stack

* **Backend & Dashboard**: Laravel 12, Alpine.js, Tailwind CSS / Custom CSS Gradient UI.
* **Database**: MySQL (relational tracking, connection status, log stores).
* **Automation Core**: Python 3.13, Selenium, `undetected-chromedriver` (configured for subprocess dispatch on Windows).
* **AI Orchestration**: Google Gemini 2.5 Flash / Pro API (custom prompt mapping).
* **Process Runner**: Detached batched process spawning on Windows (proc_open wrappers) ensuring synchronous web performance isn't blocked by long-running background tasks.

---

## 👤 Developer & Credits
Developed and designed with ❤️ by **Ibrahim Serry**.
* **Email**: [ibrahiim.serry@gmail.com](mailto:ibrahiim.serry@gmail.com)
* **Status**: Custom Professional Automation Suite.
