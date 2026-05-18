# 🔐 NikVPN Mobile Codespace

<div dir="rtl">

> **برای کاربران ایرانی 🇮🇷** - یک راه‌حل سریع و آسان برای استفاده از VPN از طریق GitHub Codespace با پشتیبانی کامل موبایل

[![GitHub License](https://img.shields.io/github/license/nikvpn-iran/nikvpn-mobile-codespace)](LICENSE)
[![Stars](https://img.shields.io/github/stars/nikvpn-iran/nikvpn-mobile-codespace?style=social)](https://github.com/nikvpn-iran/nikvpn-mobile-codespace)

## 🌟 ویژگی‌های اصلی

✅ **دو کانفیگ یکجا**
- **VLESS + xHTTP**: کانفیگ مورد استفاده و ثابت‌شده
- **VLESS + XTLS**: بازدهی بالاتر و کمتر شناسایی

✅ **QR Code برای موبایل**
- نمایش تصویری و فوری
- بدون نیاز به کپی دستی
- دو کد برای دو کانفیگ مختلف

✅ **منوی تعاملی ساده**
- کنترل کامل از ترمینال
- نمایش لاگ‌ها و وضعیت سرویس
- مناسب برای استفاده از موبایل

✅ **راه‌اندازی خودکار**
- تنظیم خودکار GitHub Codespace
- بارگذاری خودکار بات و وابستگی‌ها
- اجرای خودکار پس از راه‌اندازی

---

## 🚀 شروع سریع

### 1️⃣ ایجاد Codespace جدید

```bash
gh codespace create \
  --repo nikvpn-iran/nikvpn-mobile-codespace \
  --branch main
```

یا از طریق وب:
1. رفتن به [مخزن](https://github.com/nikvpn-iran/nikvpn-mobile-codespace)
2. کلیک بر `Code` → `Codespaces` → `Create codespace on main`

### 2️⃣ انتظار برای راه‌اندازی

- Codespace به طور خودکار راه‌اندازی می‌شود
- Xray دانلود و نصب می‌شود
- منوی تعاملی نمایش داده می‌شود

### 3️⃣ انتخاب کانفیگ

هنگام اجرای `start.sh` برای اولین بار:

```
کدام کانفیگ را می‌خواهید استفاده کنید؟

1️⃣  VLESS + xHTTP (مورد استفاده موثر)
2️⃣  VLESS + XTLS (بازدهی بالاتر)

انتخاب کنید (1 یا 2):
```

### 4️⃣ اسکن QR Code

```
📱 QR Code:
████████████████████████████
██ ▄▄▄▄▄ █▀▀██▀ ██ ▄▄▄▄▄ ██
██ █   █ █▄█▀█▄ ██ █   █ ██
██ █▄▄▄█ █▀▀ █▀██ █▄▄▄█ ██
██▄▄▄▄▄▄▄█ ▀ █ ▀▄▄▄▄▄▄▄██
████████████████████████████
```

QR Code را با دوربین موبایل خود اسکن کنید و کانفیگ را به تطبیق VPN خود اضافه کنید.

---

## 📱 استفاده از موبایل

### پیش‌نیازها:
- تطبیق VPN سازگار (مثل Nekoray، V2rayNG، Clash ...)
- دسترسی به دوربین موبایل

### مراحل:

1. **دوربین را باز کنید** و QR Code را اسکن کنید
2. **تطبیق VPN را باز کنید** و کانفیگ را اضافه کنید
3. **متصل شوید** و لذت ببرید! 🎉

---

## 💻 منوی تعاملی

پس از راه‌اندازی، می‌توانید در ترمینال این دستورات را اجرا کنید:

```bash
# نمایش منوی اصلی
menu

# نمایش لینک‌های کانفیگ
show-configs

# نمایش QR Codes بزرگتر
generate-qr

# نمایش لاگ‌های Xray
tail -f /tmp/xray.log
```

### گزینه‌های منوی:

| گزینه | توضیح | استفاده |
|------|--------|--------|
| 1 | نمایش لینک‌ها و QR Codes | مشاهده کانفیگ‌های جاری |
| 2 | QR Codes بزرگتر | برای اسکن بهتر |
| 3 | نمایش لاگ‌های Xray | رفع‌الخلل |
| 4 | شروع دوباره Xray | برای تغییر کانفیگ |
| 5 | وضعیت Xray | بررسی سلامتی سرویس |
| 6 | ورود به tmux | کنترل پیشرفته |

---

## 🔧 کانفیگ‌های موجود

### VLESS + xHTTP (کانفیگ 1)
- **پورت**: 443
- **مناسب برای**: استفاده سنتی و مطمئن
- **بازدهی**: نرمال
- **درجه پنهان‌کاری**: خوب
- **نمونه لینک**:
```
vless://UUID@94.130.50.12:443?encryption=none&security=tls&sni=codespace-name.app.github.dev&type=xhttp&mode=packet-up
```

### VLESS + XTLS (کانفیگ 2) ⭐ توصیه‌شده
- **پورت**: 8443
- **مناسب برای**: بازدهی بالاتر و کمتر شناسایی
- **بازدهی**: بسیار بالا
- **درجه پنهان‌کاری**: بسیار خوب
- **ویژگی‌های خاص**:
  - XTLS-RPRX-Vision flow برای حداکثر بازدهی
  - TLS 1.2+ برای امنیت بالاتر
  - DNS بهتر شده برای تحل‌کنندگی سریع‌تر
- **نمونه لینک**:
```
vless://UUID@94.130.50.12:8443?encryption=none&security=tls&sni=codespace-name.app.github.dev&flow=xtls-rprx-vision&type=tcp
```

---

## 🔐 نکات امنیتی

⚠️ **مهم:**
- این پروژه برای استفاده شخصی طراحی شده است
- از GitHub Codespace برای اهداف کانونی استفاده کنید
- UUIDs و تنظیمات هنگام ایجاد جدید، تغییر می‌کنند
- Logs و داده‌های حساس محفوظ نگاه داشته می‌شوند

---

## 📊 ساختار پروژه

```
nikvpn-mobile-codespace/
├── Dockerfile                 # تصویر Docker
├── devcontainer.json         # تنظیمات Codespace
├── setup.sh                  # اسکریپت راه‌اندازی
├── start.sh                  # اسکریپت شروع
├── menu.sh                   # منوی تعاملی
├── show-configs.sh           # نمایش کانفیگ‌های فعلی
├── generate-qr.sh            # تولید QR Codes
├── config-vless-xhttp.json   # کانفیگ VLESS xHTTP
├── config-vless-xtls.json    # کانفیگ VLESS XTLS
├── README.md                 # این فایل
└── .gitignore               # فایل‌های نادیده‌گرفته
```

---

## 🌐 تطبیق‌های VPN سازگار

### موبایل (اندروید/iOS)

| تطبیق | سیستم‌عامل | نوت |
|--------|----------|------|
| **Nekoray** | Android | بهترین انتخاب |
| **V2rayNG** | Android | محبوب و سریع |
| **Clash for Windows** | Windows | رابط خوب |
| **Shadowrocket** | iOS | پرداخت‌ی |
| **Stash** | iOS | پرداخت‌ی |

### نحوه اضافه کردن کانفیگ:

1. تطبیق VPN را باز کنید
2. گزینه "اضافه کردن پروفایل" را انتخاب کنید
3. QR Code را اسکن کنید یا لینک را رونوشت کنید
4. تنظیمات را پذیرفته و متصل شوید

---

## 🛠️ عیب‌یابی

### مشکل: Xray شروع نمی‌شود

```bash
# بررسی لاگ‌ها
tail -100 /tmp/xray.log

# بررسی پروسس
pgrep -a xray

# راه‌اندازی دوباره
menu  # سپس گزینه 4 را انتخاب کنید
```

### مشکل: QR Code نمایش نداده می‌شود

```bash
# بررسی نصب qrencode
which qrencode

# دوباره نصب
sudo apt-get install -y qrencode

# نمایش دوباره
generate-qr
```

### مشکل: اتصال ناموفق

1. بررسی کنید پورت PUBLIC است (تب PORTS)
2. UUID و SNI را بررسی کنید (`show-configs`)
3. تطبیق VPN را مجدد راه‌اندازی کنید
4. یک کانفیگ دیگر امتحان کنید

---

## 📝 فایل‌های کانفیگ

### config-vless-xhttp.json
```json
{
  "inbounds": [
    {
      "port": 443,
      "protocol": "vless",
      "streamSettings": {
        "network": "xhttp",
        "xhttpSettings": {
          "mode": "packet-up"
        }
      }
    }
  ]
}
```

### config-vless-xtls.json
```json
{
  "inbounds": [
    {
      "port": 8443,
      "protocol": "vless",
      "settings": {
        "clients": [{
          "flow": "xtls-rprx-vision"
        }]
      },
      "streamSettings": {
        "network": "tcp",
        "security": "tls"
      }
    }
  ]
}
```

---

## 🤝 مشارکت

اگر ایده‌ های بهتری دارید:

1. Fork کنید
2. شاخه‌ای جدید بسازید (`git checkout -b feature/idea`)
3. تغییرات را commit کنید (`git commit -am 'Add feature'`)
4. Push کنید (`git push origin feature/idea`)
5. Pull Request بسازید

---

## ⚖️ لایسنس

MIT License - برای جزئیات [LICENSE](LICENSE) را ببینید

---

## 📞 پشتیبانی

اگر مشکلی پیدا کردید:

1. [Issues](https://github.com/nikvpn-iran/nikvpn-mobile-codespace/issues) را بررسی کنید
2. Issue جدید باز کنید با جزئیات مشکل
3. لاگ‌های خطا را شامل کنید

---

## 🙏 سپاس‌گزاری

- [Xray-core](https://github.com/XTLS/Xray-core) - هسته VPN
- [V2fly](https://github.com/v2fly) - GeoIP و GeoSite
- [GitHub Codespaces](https://github.com/features/codespaces) - سرویس میزبانی

---

## 📚 مراجع مفید

- [مستندات Xray](https://xtls.github.io/)
- [VLESS Protocol](https://xtls.github.io/config/inbound.html#inbound-object)
- [XTLS Flow](https://github.com/XTLS/Xray-core/blob/main/transport/internet/vision/vision.go)

---

## ⚡ نکات عملی

### برای بهترین تجربه:

1. **VLESS + XTLS را انتخاب کنید** - بازدهی بالاتر
2. **پورت‌ها را PUBLIC کنید** - برای دسترسی خارجی
3. **Keepalive فعال است** - اتصال ادامه می‌یابد
4. **QR Codes را اسکن کنید** - بدون خطا در تایپ

### دستورات مفید:

```bash
# مشاهده وضعیت
menu

# دیدن لاگ لحظه‌ای
tail -f /tmp/xray.log

# متصل شدن به tmux
tmux attach -t nikvpn

# لیست پنجره‌های tmux
tmux list-windows -t nikvpn
```

---

**آخرین بروزرسانی:** 2024
**نسخه:** 2.0
**وضعیت:** فعال و پشتیبانی‌شده ✅

</div>
