# StudyMate — Math Study Companion | همراه هوشمند مطالعه ریاضی

**AI-Powered Academic Assistant | دستیار هوشمند آموزشی**

<div align="center">
  <img src="src/assets/images/study_app_icon_1789490847832.jpg" alt="StudyMate icon" width="140" />
</div>

---

## Overview | معرفی پروژه

**English:**
StudyMate (Math Study Companion) is a personal AI-powered study assistant for 11th and 12th-grade mathematics-track students in Iran. It is a mobile-first web app (installable as a PWA) with a Persian right-to-left interface. Students can organize their study tasks, school timetable, exams, goals and daily practice tests in one place, and chat with an AI advisor that knows their academic situation, reschedules missed tasks, and suggests what to study next.

**فارسی:**
استادی‌میت (Math Study Companion) یک دستیار هوشمند آموزشی شخصی برای دانش‌آموزان رشته ریاضی پایه یازدهم و دوازدهم است. این برنامه یک وب‌اپ موبایل‌محور با رابط فارسی راست‌به‌چپ است که به‌صورت PWA هم قابل نصب است. دانش‌آموز می‌تواند برنامه‌های مطالعه، برنامه کلاسی مدرسه، امتحانات، اهداف و تست‌های روزانه‌اش را یک‌جا مدیریت کند و با یک مشاور هوشمند گفتگو کند؛ مشاوری که وضعیت تحصیلی او را می‌شناسد، کارهای عقب‌افتاده را دوباره برنامه‌ریزی می‌کند و پیشنهاد می‌دهد قدم بعدی چیست.

---

## Key Features | قابلیت‌ها

* **AI study advisor (chat) | مشاور هوشمند چت‌محور** — Persian-language advisor built on a detailed system prompt with the full 11th-grade math-track syllabus (Calculus 1, Geometry 2, Statistics & Probability, Physics 2, Chemistry 2, and more). | مشاوری فارسی‌زبان با سرفصل کامل دروس یازدهم ریاضی.
* **One-tap action proposals | پیشنهاد اقدام با تأیید دانش‌آموز** — the AI can propose adding tasks, goals, exams or test results; nothing is changed until the student confirms. | هوش مصنوعی می‌تواند افزودن تسک، هدف، امتحان یا نتیجه تست را پیشنهاد دهد و تا تأیید دانش‌آموز چیزی تغییر نمی‌کند.
* **Tracking unfinished tasks | پیگیری کارهای عقب‌افتاده** — detects missed tasks and smartly reschedules them. | تشخیص تسک‌های عقب‌افتاده و بازبرنامه‌ریزی هوشمند آن‌ها.
* **Study planning & goals | برنامه‌ریزی و اهداف** — tasks with priority and estimated time, goals with progress, exam countdowns. | تسک‌ها با اولویت و زمان تخمینی، اهداف با درصد پیشرفت، شمارش معکوس امتحانات.
* **School timetable | برنامه کلاسی مدرسه** — weekly school schedule so study plans fit real free time. | برنامه هفتگی مدرسه تا برنامه مطالعه با زمان آزاد واقعی هماهنگ شود.
* **Daily tests & analysis | تست‌های روزانه و تحلیل عملکرد** — log practice tests and see performance and study-history analysis. | ثبت تست‌های روزانه و مشاهده تحلیل عملکرد و تاریخچه مطالعه.
* **Personalized recommendations | پیشنهادهای شخصی‌سازی‌شده** — based on weak/strong subjects, study pace and daily goals. | بر اساس دروس ضعیف و قوی، سرعت مطالعه و هدف روزانه.
* **Smart notifications | یادآورهای هوشمند** — exam-eve, task-deadline and nightly-review reminders. | یادآوری شب امتحان، سررسید تسک‌ها و مرور شبانه.
* **Installable & offline-friendly | قابل نصب و نیمه‌آفلاین** — PWA with service worker caching. | PWA با کش سرویس‌ورکر.

---

## Target Audience | مخاطبان

High school mathematics students (11th and 12th grade) preparing for school exams and the Konkur.
دانش‌آموزان رشته ریاضی در دوره متوسطه دوم (یازدهم و دوازدهم) که برای امتحانات مدرسه و کنکور آماده می‌شوند.

---

## Technologies Used | تکنولوژی‌های استفاده‌شده

| Layer / لایه | Technology / تکنولوژی |
|---|---|
| Frontend | React 19, TypeScript, Vite 6 |
| Styling & UI | Tailwind CSS 4, Lucide React icons, Motion (animations) |
| Backend | Node.js, Express 4 (REST API), `tsx` for development |
| AI | Google Gemini via `@google/genai` SDK; optional OpenRouter (Gemini 2.5 Flash with a free-model fallback) |
| Database | Firebase Firestore (cloud persistence) + Firebase Anonymous Auth |
| PWA | Web App Manifest, Service Worker, Web Notifications API |
| Language / locale | Persian (RTL), Jalali (Persian) date utilities |

---

## How to Run | نحوه اجرا

**Prerequisites | پیش‌نیازها:** [Node.js](https://nodejs.org/) 18 or newer, and an API key from [Google AI Studio](https://aistudio.google.com/apikey) (Gemini) or [OpenRouter](https://openrouter.ai/).
Node.js نسخه ۱۸ یا بالاتر و یک کلید API از Google AI Studio (جمنای) یا OpenRouter.

1. **Install dependencies | نصب وابستگی‌ها**
   ```bash
   npm install
   ```
2. **Set environment variables | تنظیم متغیرهای محیطی** — copy the example file and fill in your key.
   کپی فایل نمونه و وارد کردن کلید:
   ```bash
   cp .env.example .env.local
   ```
   ```env
   GEMINI_API_KEY=your_gemini_key_here
   # Optional: if set, OpenRouter is used first
   OPENROUTER_API_KEY=
   ```
   > ⚠️ Never commit your `.env.local` file. The AI key stays on the server and is never sent to the browser.
   > فایل `.env.local` را هرگز در گیت قرار ندهید. کلید فقط روی سرور استفاده می‌شود.
3. **Firebase** — the project ships with `firebase-applet-config.json`. To use your own Firebase project, replace the values in that file and enable Firestore and Anonymous sign-in.
   برای استفاده از پروژه Firebase خودتان، مقادیر این فایل را عوض کنید و Firestore و ورود ناشناس را فعال کنید.
4. **Start the app | اجرای برنامه**
   ```bash
   npm run dev
   ```
   Open **http://localhost:3000** | آدرس **http://localhost:3000** را در مرورگر باز کنید.

**Production build | ساخت نسخه نهایی**
```bash
npm run build   # builds frontend + bundles the server into dist/
npm start       # runs dist/server.cjs
```
Type-check: `npm run lint`

---

## How It Works | نحوه کار

**English:**
1. The student's data (tasks, goals, exams, school timetable, daily tests, preferences) is stored in Firestore and shown in the 8 app screens.
2. When the student sends a message, the server builds a **structured context** of their academic state (today's tasks, missed tasks, upcoming exams, weak subjects, etc.) and sends it to the AI together with the advisor system prompt.
3. The AI answers in Persian and may attach an `ACTION_PROPOSAL` (e.g. "add this task"). The app shows it as a suggestion card.
4. Only after the student confirms, the server runs the action through a **controlled action registry**: a fixed list of validated actions (create task, reschedule task, create goal, update goal progress, log study session, record test result, update preferences, reorganize schedule). Every execution is audit-logged, so the AI can never change data freely.
5. If no API key is set, the app falls back to a built-in mock advisor so the UI still works.

**فارسی:**
۱. اطلاعات دانش‌آموز (تسک‌ها، اهداف، امتحانات، برنامه کلاسی، تست‌های روزانه و تنظیمات) در Firestore ذخیره و در ۸ صفحه برنامه نمایش داده می‌شود.
۲. با ارسال هر پیام، سرور یک **زمینه ساختاریافته** از وضعیت تحصیلی دانش‌آموز (تسک‌های امروز، عقب‌افتاده‌ها، امتحانات نزدیک، دروس ضعیف و …) می‌سازد و همراه با پرامپت مشاور برای هوش مصنوعی می‌فرستد.
۳. هوش مصنوعی فارسی پاسخ می‌دهد و ممکن است یک `ACTION_PROPOSAL` (مثلاً «این تسک اضافه شود») پیوست کند که به‌صورت کارت پیشنهاد نمایش داده می‌شود.
۴. فقط پس از تأیید دانش‌آموز، سرور آن اقدام را از طریق **رجیستری اقدامات کنترل‌شده** اجرا می‌کند؛ فهرستی ثابت از اقدامات اعتبارسنجی‌شده (ساخت تسک، تغییر زمان تسک، ساخت هدف، به‌روزرسانی پیشرفت هدف، ثبت جلسه مطالعه، ثبت نتیجه تست، تغییر تنظیمات، بازچینی برنامه). هر اجرا در لاگ ثبت می‌شود، پس هوش مصنوعی هرگز نمی‌تواند آزادانه داده‌ها را تغییر دهد.
۵. اگر کلید API تنظیم نشده باشد، یک مشاور شبیه‌سازی‌شده داخلی جایگزین می‌شود تا رابط کاربری همچنان کار کند.

### App Screens | صفحات برنامه

| Screen | صفحه | Description |
|---|---|---|
| Home | میز کار | Today's overview, quote, alerts |
| Advisor | مشاور | AI chat |
| Tasks | برنامه‌ها | Study tasks and missed tasks |
| Goals | اهداف | Long-term goals and progress |
| Exams | امتحانات | Exam calendar and countdown |
| School Schedule | برنامه مدرسه | Weekly timetable |
| Daily Tests | تست‌های روزانه | Practice-test log |
| Analysis | تحلیل | Performance and study history |

### Project Structure | ساختار پروژه

```
server.ts            # Express server + Vite middleware
server/ai/           # System prompt, LLM client, tools schema, action registry
server/routes/api.ts # REST API (/api/tasks, /api/goals, /api/exams, /api/ai/chat, ...)
server/db/store.ts   # Server-side data store
src/components/      # React screens and UI components
src/services/        # Firestore, planner logic, notifications, mock advisor
src/utils/           # Persian (Jalali) date helpers
public/              # PWA manifest, service worker, icons
```
## Browser Requirements | نیازمندی‌های مرورگر

* A modern browser: **Chrome / Edge 100+, Safari 15.4+ (iOS 16.4+ for PWA notifications), Firefox 100+**.
  مرورگر مدرن: کروم و اج ۱۰۰ به بالا، سافاری ۱۵.۴ به بالا، فایرفاکس ۱۰۰ به بالا.
* JavaScript and an internet connection (for Firestore and the AI advisor).
  جاوااسکریپت فعال و اتصال اینترنت (برای Firestore و مشاور هوشمند).
* Optional: allow **Notifications** for reminders; use "Add to Home Screen" to install as an app.
  اختیاری: اجازه اعلان‌ها برای یادآورها و «افزودن به صفحه اصلی» برای نصب به‌صورت اپ.
* Best experienced on a phone-sized screen (mobile-first design).
  تجربه بهتر روی صفحه موبایل (طراحی موبایل‌محور).

## Project Status | وضعیت پروژه

🚧 **In active development / Working prototype** | در حال توسعه — نسخه اولیه قابل اجرا

* ✅ Core screens, Firestore persistence, AI advisor chat, controlled actions, PWA & notifications
* 🔜 Full 12th-grade syllabus inside the AI advisor, proper user login, stricter Firestore security rules

---

## Developer | توسعه‌دهنده

Personal Project | پروژه شخصی
