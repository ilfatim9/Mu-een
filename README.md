<div align="center">

<img src="docs/assets/logo-color.png" alt="MU'EEN logo" width="220">

# MU'EEN · مُعين

by **Team Innovision**

*We built MU'EEN to serve students in the best possible way at the lowest possible cost — a printed QR code instead of a smartwatch.*

### 🔗 [Live demo](https://yaass24.github.io/Mu-een/) · 🎨 [Figma design](https://www.figma.com/design/sXCsdqLnoGpQ19vTEYezXS/mu-een?node-id=78-2)

</div>

> ⚠️ **Prototype** — all data is simulated; this system does not replace official emergency services.

---

## ❗ The problem

Students with health needs often find out about a barrier only when they reach it — an elevator out of service, an inaccessible restroom, or a lecture moved to an unsuitable room. Support requests, schedules and facility status live in separate places, so no one connects them in time. There is also no single, clear and formal channel for students to submit their medical reports, so the university may not know a student's condition and needs. And in a health emergency on campus, bystanders may not know who to call or how to describe the exact location.

## 📚 Related research

| Study | Why it matters for MU'EEN |
|---|---|
| [Abed et al. (2025) — Evaluating Accessibility and Special Resources in Saudi Arabia's Higher Education for Students With Disabilities](https://journals.sagepub.com/doi/full/10.1177/21582440251368969) · *SAGE Open* | Surveys 173 Saudi undergraduates with disabilities on how well universities provide accessibility and special resources — the local gap MU'EEN addresses. |
| [Alhazmi et al. (2021) — The Impact of Sickle Cell Disease on Academic Performance among Affected Students](https://pmc.ncbi.nlm.nih.gov/articles/PMC8773889) · *Children*, Jazan | Students with sickle cell disease had lower GPAs and more absences than healthy peers (982 participants) — a chronic condition common in Saudi Arabia. |
| [Ball & Tuckwiller (2024) — Sick of Subpar Support: An Exploratory Study of Chronically Ill College Student Experiences](https://www.researchgate.net/publication/378255557_Sick_of_subpar_support_An_exploratory_study_of_chronically_ill_college_student_experiences) · *Journal of Diversity in Higher Education* | Explores how chronically ill college students experience campus support — the support-request flow MU'EEN streamlines. |
| [Chaudhry et al. (2020) — College Students with Inflammatory Bowel Disease](https://pmc.ncbi.nlm.nih.gov/articles/PMC7241053) · *Health Equity* | Students with invisible conditions need specific support to succeed in college — including reliable access to facilities such as restrooms. |

## 📌 Overview

**MU'EEN** is a proactive system that links students' approved health needs with their class schedules, room locations and campus facility status. It detects **conflicts early** (e.g. an elevator out of service in a building where a student with an approved mobility need has a lecture) and enables an **instant health alert** by scanning the QR code at the entrance of each floor.

Built around the **College of Computer Science & IT — Buildings A61 and A62** (two floors each).

## 💡 Our approach: maximum impact, minimum cost

We aimed to serve students in the most effective way at the lowest possible cost, using what the campus already has.

- **QR codes instead of wearables** — no smartwatches, panic buttons or sensors to buy, charge or maintain. A printed code at each floor entrance is enough.
- **Any phone works** — the built-in camera opens the alert page; no app to install and no account needed, so even a bystander can report.
- **Fastest possible alert** — scanning the code *is* the report: the alert is sent the moment the page opens, without pressing a single button.
- **Privacy by design** — anyone nearby can help without signing in or sharing any personal data: the alert carries the building and floor, with no medical details.
- **A clear, formal channel for medical reports** — the student uploads the report once with the request, so the university knows the student's condition and needs and can support them properly. The report can be opened only by the student and the university admin.
- **Exact location, automatically** — each code carries its building and floor, so no one has to describe where they are in an emergency.
- **Web-based** — runs in the browser on laptops and phones and can be installed as an app (PWA), with no extra hardware.

## 👥 Who is it for?

- **Students with health needs** — mobility and access needs, chronic conditions.
- **University admin** — reviews support requests, manages cases and resolves conflicts.
- **Facilities management** — updates temporary issues such as elevators or accessible restrooms out of service.
- **Health center** — receives SOS alerts and tracks the response.
- **Anyone nearby** — sends an alert with the exact location by scanning a QR code.

## 🔄 Example scenario

1. Facilities sets the **A61 elevator** to *Under maintenance*.
2. MU'EEN finds a student with an **approved mobility need** who has a lecture in that building.
3. The admin sees a **proactive conflict** and arranges an alternative; the student is notified.
4. When the facility is back in service, the case closes automatically.

## ✨ Features

| Role | Features |
|---|---|
| 🎓 **Student** | Support request with a medical report (PDF/image), request tracking, schedule & room locations, proactive alerts, profile |
| 🏛️ **University admin** | Dashboard, request review & approval, students, proactive conflicts, room changes with student notifications, building QR codes |
| 🏥 **Health center** | Real-time health alerts (including bystander QR alerts), response status tracking |
| 🛠️ **Facilities** | Facility status (Available / Maintenance / Unavailable) that automatically raises conflicts, QR codes |

### 🚨 Instant QR alert
- A unique QR code for **every floor** of every building.
- **Anyone** who scans it — even a bystander without an account — instantly notifies the health center with the **building and floor**.
- One confirmation screen with a *"Sent by mistake? Cancel"* option.
- Duplicate protection: one alert per floor per minute.

### 🎨 Interface
- Full **English / Arabic** UI with instant switching (LTR / RTL).
- Responsive on laptops, large screens and phones; each dashboard fits on one screen.
- Smooth page transitions; installable as an app (PWA).

## 🎯 Impact

- **Goal:** reduce barriers to attending lectures and exams, and speed up support.
- **Measured by:** conflict-detection accuracy, case resolution time, and task-completion ease.

## 🛣️ Next steps

- [x] Web prototype with four interfaces (student, admin, facilities, health center).
- [ ] Scenario and usability testing with real users.
- [ ] For deployment: access to university schedule and facility data, with clearly assigned responsibilities.
- [ ] Expand from our college to the whole campus, building a better university experience for every student.

## 👤 Demo accounts

Password for all accounts: `Mueen123!`

| Role | Email |
|---|---|
| University admin | `admin@mueen.test` |
| Health center | `clinic@mueen.test` |
| Facilities | `facilities@mueen.test` |
| Student | `student@mueen.test` |

## 📁 Project structure

```
mueen_v4/
├── index.php                 # App shell
├── app.js                    # Views, i18n, transitions
├── style.css                 # Styles
├── sw.js                     # Service worker (PWA)
├── manifest.webmanifest
├── setup.php                 # One-time local installer
├── db.php                    # Database connection & migrations
├── graph_config.example.php  # Optional Outlook settings
├── api/
│   ├── index.php             # REST-style JSON API
│   └── graph_mail.php        # Optional Outlook sender
└── assets/                   # Logos, icons, QR library
```

## 🧩 Code breakdown

**Front-end — `app.js`**

| Module | Responsibility |
|---|---|
| Core | App state, API requests, data loading, toasts, screen scaling |
| i18n | English / Arabic dictionary and LTR / RTL switching |
| Auth | Landing page, sign-in, session |
| Staff shell | Sidebar, tables, stat cards, charts |
| Admin | Requests & approval, students, conflicts, room changes |
| Health center | Alert list and response status |
| Facilities | Facility status (Available / Maintenance / Unavailable) |
| Student | Tabs, support request, schedule, account |
| QR | Per-floor codes, printing with stamp & signature, instant alert page |
| Notifications | Notice list, periodic sync, device notifications |
| Actions | Button, form and dialog handling |

**API — `api/index.php`**

| Group | Routes |
|---|---|
| Session | `login` · `logout` · `me` · `config` |
| Requests | `requests` · `requests/{id}/review` · `requests/{id}/attachment` |
| Emergencies | `emergencies` · `emergencies/{id}/status` |
| QR alerts | `qr/alert` · `qr/alert/cancel` · `qr/locations` · `qr/resolve` |
| Schedules | `schedules` · `sections` · `sections/{id}/room` |
| Facilities & conflicts | `facilities` · `facilities/{id}/status` · `conflicts` |
| Notifications | `notices` · `notices/read` · `push/test` · `push/subscribe` · `stream` |
| Mail | `outlook/outbox` |

**Database — MySQL**

| Tables | Purpose |
|---|---|
| `users` | Users and roles |
| `requests` | Health support requests and reports |
| `emergencies` | Health alerts (including QR alerts) |
| `facilities` | Facilities and their status |
| `schedules` · `course_sections` · `section_enrollments` | Schedules, sections and enrollments |
| `room_changes` | Room change log |
| `conflicts` | Proactive conflicts |
| `notices` · `email_outbox` | Notifications and outgoing mail |

> Source code is not published in this repository

---

<div dir="rtl">

## نبذة باللغة العربية

**المشكلة:** غالبًا ما يكتشف الطالب ذو الاحتياج الصحي العائق عند وصوله إليه، كمصعد معطّل أو قاعة غير مناسبة، لأن طلبات الدعم والجداول وحالة المرافق منفصلة عن بعضها. كما لا توجد قناة واحدة واضحة ورسمية لاستقبال التقارير الطبية، فقد لا تعرف الجامعة حالة الطالب واحتياجاته. وفي الحالات الطارئة قد لا يعرف من حول الحالة بمن يتصلون ولا كيف يصفون الموقع بدقة.

**مُعين** نظام ذكي من فريق **Innovision** لدعم الطلاب ذوي الاحتياجات الصحية وتسهيل وصولهم إلى مرافق الكلية. يربط الاحتياجات الصحية المعتمدة بجداول الطلاب ومواقع القاعات وحالة المرافق، فيكتشف **التعارضات مبكرًا**، ويتيح **بلاغًا صحيًا فوريًا** بمسح رمز QR عند مدخل كل دور.

صُمّم ليخدم الطلاب بأفضل طريقة وبأقل تكلفة: رموز QR مطبوعة عند كل دور بدل الساعات الذكية أو الأجهزة القابلة للارتداء، وتعمل بكاميرا أي جوال دون تثبيت تطبيق أو إنشاء حساب. ويُرسَل البلاغ فور مسح الرمز دون الضغط على أي زر، مع مراعاة الخصوصية؛ إذ لا يحتاج المُبلِّغ إلى تسجيل دخول أو مشاركة أي بيانات شخصية، ويحمل البلاغ المبنى والدور دون أي تفاصيل صحية. ويوفّر قناة رسمية وواضحة لرفع التقرير الطبي، لتتعرّف الجامعة على حالة الطالب واحتياجاته وتقدّم له الدعم المناسب، ولا يطّلع على التقرير إلا الطالب ومسؤول الجامعة.

طُبّق على مباني **كلية علوم الحاسب وتقنية المعلومات — A61 و A62** (دوران لكل مبنى).

🔗 [جرّب النسخة التجريبية](https://yaass24.github.io/Mu-een/) · 🎨 [التصميم على Figma](https://www.figma.com/design/sXCsdqLnoGpQ19vTEYezXS/mu-een?node-id=78-2) — كلمة المرور لجميع الحسابات: `Mueen123!`

</div>

---

<div align="center">

**Team Innovision** — MU'EEN © 2026 · All rights reserved

</div>
