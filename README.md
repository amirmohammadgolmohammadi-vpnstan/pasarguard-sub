# قالب صفحه اشتراک PasarGuard

صفحه‌ی اشتراک مدرن، فارسی/انگلیسی، با حالت روشن و تاریک.

- حجم، انقضا، آخرین اتصال و آخرین آپدیت اشتراک
- لوکیشن‌ها گروه‌بندی‌شده بر اساس کشور، با کپی و QR جدا
- دکمه‌ی افزودن یک‌لمسی به Hiddify، v2rayNG و Streisand
- خواندن لینک پشتیبانی و اطلاعیه از تنظیمات اشتراک پنل
- بدون برند، با تم آبی نئونی

## نصب

```sh
curl -fsSL https://raw.githubusercontent.com/amirmohammadgolmohammadi-vpnstan/pasarguard-sub/main/install.sh | sudo bash
```

اگر مسیر نصب پنل فرق دارد:

```sh
curl -fsSL https://raw.githubusercontent.com/amirmohammadgolmohammadi-vpnstan/pasarguard-sub/main/install.sh | sudo ENV_FILE=/path/to/.env TPL_DIR=/path/to/templates bash
```

## به‌روزرسانی

همان دستور نصب را دوباره اجرا کنید (نسخه‌ی قبلی با پسوند `.bak` نگه داشته می‌شود).

## حذف

```sh
curl -fsSL https://raw.githubusercontent.com/amirmohammadgolmohammadi-vpnstan/pasarguard-sub/main/install.sh | sudo bash -s -- --uninstall
```

## نصب دستی

```sh
sudo mkdir -p /var/lib/pasarguard/templates/subscription
sudo wget -O /var/lib/pasarguard/templates/subscription/index.html \
  https://raw.githubusercontent.com/amirmohammadgolmohammadi-vpnstan/pasarguard-sub/main/index.html
```

در `/opt/pasarguard/.env`:

```dotenv
CUSTOM_TEMPLATES_DIRECTORY="/var/lib/pasarguard/templates/"
SUBSCRIPTION_PAGE_TEMPLATE="subscription/index.html"
```

سپس `pasarguard restart`.

## تنظیمات

دکمه‌ی «پشتیبانی» همیشه نمایش داده می‌شود. اگر در پنل (Settings ← Subscription ← Support URL) لینک بگذارید همان استفاده می‌شود، وگرنه به `https://t.me/` می‌رود. برای ثابت کردن لینک، متغیر `SUPPORT` بالای اسکریپت `index.html` را عوض کنید.
