# 🧠 HamidCognition Real-Time Platform

**پلتفرم حرفه‌ای پیش‌بینی لحظه‌ای فارکس با موتور شناختی P/S/T**

این پلتفرم یک سیستم پیش‌بینی هوشمند و زنده برای بازار فارکس (EUR/USD) است که از ترکیب یادگیری ماشین و موتور شناختی منحصر به فرد HamidCognition استفاده می‌کند.

## ✨ ویژگی‌های کلیدی

### 🎯 پیش‌بینی دقیق
- پیش‌بینی قیمت برای **۵، ۱۰ و ۲۰ دقیقه** آینده
- محاسبه بازه اطمینان (Confidence Interval)
- نمایش جهت حرکت (صعودی/نزولی/خنثی)
- محاسبه تغییرات به صورت پیپ (Pip)

### 🧠 موتور شناختی HamidCognition
موتور شناختی مبتنی بر معماری **P/S/T** که شامل:
- **P (Power/Penetration)**: قدرت نفوذ و تأثیرگذاری
- **S (Synchronicity/Sensitivity)**: همزمانی و حساسیت به تغییرات
- **T (Tenacity/Stability)**: پایداری و مقاومت در برابر تغییرات

این موتور چهار فاز اصلی را تشخیص می‌دهد:
- `RUPTURE_IMMINENT`: خطر شکست و تغییر ناگهانی
- `SYNTHESIS_PEAK`: اوج هماهنگی و قدرت
- `UNSTABLE_CREATIVITY`: خلاقیت ناپایدار
- `STEADY_EXPLORATION`: کاوش پایدار

### 📊 تحلیل تکنیکال
- محاسبه نوسان (Volatility)
- قدرت روند (Trend Strength)
- مومنتوم (Momentum)
- RSI (Relative Strength Index)

### 🌐 داشبورد زنده
- رابط کاربری زیبا و مدرن
- به‌روزرسانی خودکار هر ۵ ثانیه
- نمایش گرافیکی وضعیت شناختی
- نمایش پیش‌بینی‌ها با سطح اطمینان

### 🔄 اتصال به داده‌های واقعی
- دریافت قیمت لحظه‌ای از yfinance
- قابلیت fallback به Alpha Vantage
- کش کردن داده‌ها برای کاهش درخواست‌های API
- به‌روزرسانی هر ۳۰ ثانیه

## 📦 نصب و راه‌اندازی

### پیش‌نیازها
- Python 3.8 یا بالاتر
- pip (Python package manager)

### نصب

```bash
# کلون کردن repository
git clone https://github.com/hamidhayatijozani/hamidcognition-realtime.git
cd hamidcognition-realtime

# نصب وابستگی‌ها
pip install -r requirements.txt

# اجرای پلتفرم
python app.py
```

سپس به آدرس `http://127.0.0.1:5000` بروید.

## 🚀 Deploy روی سرور

### گزینه ۱: Diploi (توصیه می‌شود)

**Diploi** یک پلتفرم رایگان و ساده برای deploy اپلیکیشن‌های Flask است.

1. به [diploi.com](https://diploi.com) بروید
2. با GitHub وارد شوید (بدون نیاز به کارت اعتباری)
3. New Project → Flask Stack را انتخاب کنید
4. این repository را متصل کنید
5. Diploi به صورت خودکار build و deploy می‌کند
6. آدرس وب شما: `hamidcognition.diploi.me`

**مزایا:**
- رایگان و بدون محدودیت زمانی
- HTTPS اتوماتیک
- Deploy اتوماتیک با هر push به GitHub
- بدون نیاز به تنظیمات پیچیده

### گزینه ۲: Render.com

1. به [render.com](https://render.com) بروید
2. New → Web Service را انتخاب کنید
3. این repository را متصل کنید
4. تنظیمات:
   - **Build Command**: `pip install -r requirements.txt`
   - **Start Command**: `gunicorn app:app`
   - **Environment**: Python 3

**توجه:** نسخه رایگان Render پس از ۱۵ دقیقه بی‌فعالی به حالت خواب می‌رود.

### گزینه ۳: Railway.app

1. به [railway.app](https://railway.app) بروید
2. New Project → Deploy from GitHub
3. این repository را انتخاب کنید
4. Railway تنظیمات را خودکار تشخیص می‌دهد

### گزینه ۴: Heroku

```bash
# نصب Heroku CLI
# ایجاد Procfile
echo "web: gunicorn app:app" > Procfile

# Deploy
heroku create hamidcognition
git push heroku main
```

## 📁 ساختار پروژه

```
hamidcognition-realtime/
├── app.py                      # سرور اصلی Flask
├── requirements.txt            # وابستگی‌های Python
├── README.md                   # این فایل
│
├── core/                       # هسته سیستم
│   ├── __init__.py
│   └── hamid_cognition.py     # موتور شناختی P/S/T
│
├── api/                        # لایه دریافت داده
│   ├── __init__.py
│   └── forex_data.py          # دریافت داده‌های فارکس
│
├── models/                     # مدل‌های پیش‌بینی
│   ├── __init__.py
│   └── predictor.py           # مدل ML و پیش‌بینی
│
├── ui/                         # رابط کاربری
│   ├── __init__.py
│   ├── templates/
│   │   └── dashboard.html     # داشبورد زنده
│   └── static/                # فایل‌های استاتیک
│
├── data/                       # داده‌ها (اختیاری)
└── logs/                       # لاگ‌ها (اختیاری)
```

## 🔧 تنظیمات پیشرفته

### تغییر نماد ارز

در فایل `app.py`:

```python
data_provider = ForexDataProvider(symbol="GBPUSD", cache_duration=30)
```

### تغییر بازه‌های زمانی پیش‌بینی

در فایل `models/predictor.py`:

```python
predictions = self.predictor.predict_future(
    current_price=current_price,
    data=historical_data,
    minutes=[5, 10, 20, 30],  # اضافه کردن ۳۰ دقیقه
    cognitive_bias=cognitive_bias
)
```

### افزودن API Key برای Alpha Vantage

در فایل `api/forex_data.py`:

```python
self.api_keys = {
    "alpha_vantage": "YOUR_API_KEY_HERE",  # کلید خود را وارد کنید
}
```

API Key رایگان از [Alpha Vantage](https://www.alphavantage.co/support/#api-key) دریافت کنید.

## 📊 API Endpoints

### `GET /`
داشبورد اصلی (HTML)

### `GET /api/live`
داده‌های زنده (JSON)

```json
{
  "status": "active",
  "current_price": 1.04567,
  "predictions": [
    {
      "timeframe": "+5 min",
      "forecast_price": 1.04580,
      "range": {"high": 1.04600, "low": 1.04560},
      "direction": "UP 🟢",
      "confidence": 85.5,
      "change_pips": 1.3
    }
  ],
  "cognitive_state": {
    "P": 0.750,
    "S": 0.650,
    "T": 0.500,
    "phase": "STEADY_EXPLORATION",
    "energy": 0.850,
    "confidence": 0.700
  },
  "market_context": {
    "volatility": 0.450,
    "trend_strength": 0.620,
    "momentum": 0.0012,
    "rsi": 54.3
  }
}
```

### `GET /api/status`
وضعیت سیستم

### `GET /api/history`
تاریخچه تصمیمات شناختی

## 🧪 تست

```bash
# تست اجرای سرور
python app.py

# تست API
curl http://127.0.0.1:5000/api/live
```

## 🔒 امنیت

- **هرگز API Key های خود را در کد commit نکنید**
- از متغیرهای محیطی (Environment Variables) استفاده کنید
- در production از HTTPS استفاده کنید
- Rate limiting را فعال کنید

## 📈 بهینه‌سازی عملکرد

- کش کردن داده‌های API (پیاده‌سازی شده)
- استفاده از Redis برای کش (اختیاری)
- Load balancing برای ترافیک بالا
- استفاده از CDN برای فایل‌های استاتیک

## 🐛 عیب‌یابی

### خطای "Unable to fetch current price"
- بررسی اتصال اینترنت
- بررسی API Key (اگر از Alpha Vantage استفاده می‌کنید)
- بررسی محدودیت‌های API

### خطای "Limited historical data"
- منتظر بمانید تا داده‌های کافی جمع‌آوری شود
- بازه زمانی را کاهش دهید

## 🤝 مشارکت

این پروژه open-source است و از مشارکت شما استقبال می‌کنیم!

1. Fork کنید
2. یک branch جدید بسازید (`git checkout -b feature/amazing-feature`)
3. تغییرات خود را commit کنید (`git commit -m 'Add amazing feature'`)
4. Push کنید (`git push origin feature/amazing-feature`)
5. یک Pull Request باز کنید

## 📝 مجوز

این پروژه تحت مجوز MIT منتشر شده است.

## 👨‍💻 توسعه‌دهنده

ساخته شده توسط **Hamid Hayati Jozani** با ❤️

- GitHub: [@hamidhayatijozani](https://github.com/hamidhayatijozani)

## 🙏 تشکر

- از **yfinance** برای داده‌های مالی
- از **Flask** برای فریمورک وب
- از **scikit-learn** برای ابزارهای ML
- از جامعه open-source

---

**⚠️ هشدار:** این پلتفرم صرفاً برای اهداف آموزشی و تحقیقاتی است. برای معاملات واقعی، حتماً تحلیل‌های بیشتری انجام دهید و از مشاوران مالی کمک بگیرید.
