# 🧠 HamidCognition Real-Time Platform

> **Repository status:** Historical / experimental real-time trading implementation.
>
> The current canonical research and provenance record is **[HamidCognition-Unified](https://github.com/hamidhayatijozani/HamidCognition-Unified)**. This repository remains preserved because its implementation, assumptions, and issues are part of the project's research lineage. Its historical README claims are not, by themselves, evidence of validated live-trading performance.
>
> For current status, evidence levels, repository roles, and citation rules, see `RESEARCH/REPOSITORY_GOVERNANCE.md` in the Unified repository.

**پلتفرم حرفه‌ای پیش‌بینی لحظه‌ای فارکس با موتور شناختی P/S/T**

این پلتفرم یک سیستم پیش‌بینی هوشمند و زنده برای بازار فارکس (EUR/USD) است که از ترکیب یادگیری ماشین و موتور شناختی HamidCognition استفاده می‌کند.

## جایگاه پژوهشی

این مخزن یک **artifact تاریخی/آزمایشی** است، نه اعلامیهٔ production readiness. برای استناد دقیق به کد یا رفتار این نسخه، نام مخزن و commit/path مربوطه را ذکر کنید. ادعاهای عملکردی باید با آزمایش مستقل و evidence متناظر سنجیده شوند.

## ✨ ویژگی‌های کلیدی

### 🎯 پیش‌بینی
- پیش‌بینی قیمت برای **۵، ۱۰ و ۲۰ دقیقه** آینده
- محاسبه بازه اطمینان (Confidence Interval)
- نمایش جهت حرکت (صعودی/نزولی/خنثی)
- محاسبه تغییرات به صورت پیپ (Pip)

### 🧠 موتور شناختی HamidCognition
موتور شناختی مبتنی بر معماری **P/S/T** که شامل:
- **P (Power/Penetration)**
- **S (Synchronicity/Sensitivity)**
- **T (Tenacity/Stability)**

این موتور چهار فاز اصلی را تشخیص می‌دهد:
- `RUPTURE_IMMINENT`
- `SYNTHESIS_PEAK`
- `UNSTABLE_CREATIVITY`
- `STEADY_EXPLORATION`

## 📦 نصب و راه‌اندازی

### پیش‌نیازها
- Python 3.8 یا بالاتر
- pip

### نصب

```bash
git clone https://github.com/hamidhayatijozani/hamidcognition-realtime.git
cd hamidcognition-realtime
pip install -r requirements.txt
python app.py
```

سپس به `http://127.0.0.1:5000` بروید.

## 📊 API Endpoints

- `GET /` — داشبورد اصلی
- `GET /api/live` — داده‌های زنده
- `GET /api/status` — وضعیت سیستم
- `GET /api/history` — تاریخچه تصمیمات شناختی

## 🧪 وضعیت شواهد

این repository برای پژوهش و بازبینی کد قابل استفاده است. اعداد confidence، prediction accuracy یا readiness موجود در artifactهای آن نباید بدون اجرای مستقل و ثبت fingerprint به‌عنوان نتیجهٔ تأییدشده نقل شوند.

## 🔒 امنیت

- API Key را commit نکنید.
- از Environment Variables استفاده کنید.
- برای سرویس عمومی HTTPS و کنترل دسترسی مناسب لازم است.

## 📝 مجوز و انتساب

وضعیت حقوقی و citation فعلی پروژه در Unified ثبت می‌شود. پیش از بازاستفاده یا توزیع، فایل‌های حقوقی همین repository و Unified را بررسی کنید.

## 👨‍💻 توسعه‌دهنده

**Hamid Hayati Jozani**

## Canonical research record

**HamidCognition-Unified:** https://github.com/hamidhayatijozani/HamidCognition-Unified

⚠️ این نرم‌افزار صرفاً برای پژوهش/آزمایش است و این README تضمین‌کنندهٔ سود یا اعتبار معاملاتی نیست.
