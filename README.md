# HardwareMD

> Your computer's health check, in plain language.
> بررسی سلامت کامپیوتر، به زبان ساده.

![demo](docs/demo.gif)

---

## What is HardwareMD? | HardwareMD چیست؟

**HardwareMD** is a lightweight, web-based dashboard that reads your computer's hardware sensors (CPU/GPU temperature, fan speed, memory usage, disk health) and tells you what they actually mean — no jargon, no command line, no confusing numbers.

**HardwareMD** یک داشبورد سبک و تحت وب است که سنسورهای سخت‌افزاری کامپیوتر شما (دمای CPU/GPU، سرعت فن، مصرف حافظه، سلامت دیسک) را می‌خواند و به زبان ساده می‌گوید این اعداد چه معنایی دارند — بدون اصطلاحات فنی، بدون خط فرمان، بدون اعداد گیج‌کننده.

### Why? | چرا؟

Most hardware monitoring tools show a wall of numbers: 65°C, 1200 RPM, 42% usage. If you're not a hardware enthusiast, you have no idea whether those numbers are good or bad. HardwareMD reads the same sensors, but translates them into:

بیشتر ابزارهای نظارت بر سخت‌افزار یک دیوار از اعداد نشان می‌دهند: ۶۵ درجه، ۱۲۰۰ دور فن، ۴۲٪ مصرف. اگر علاقه‌مند به سخت‌افزار نباشید، نمی‌دانید این اعداد خوب هستند یا بد. HardwareMD همان سنسورها را می‌خواند، اما آن‌ها را به این صورت ترجمه می‌کند:

- ✅ **Good / خوب** — everything is normal / همه چیز طبیعی است
- ⚠️ **Warning / هشدار** — something needs attention / چیزی نیاز به توجه دارد (مثلاً «فن CPU کندتر از حد معمول کار می‌کند»)
- ❌ **Critical / بحرانی** — take action now / همین حالا اقدام کنید (مثلاً «GPU در حال داغ شدن بیش از حد است»)

## Features | امکانات

- 🖥️ **One-click scan** — open the page, click "Scan", get a health report.
  **اسکن با یک کلیک** — صفحه را باز کنید، روی «اسکن» کلیک کنید، گزارش سلامت را بگیرید.
- 🌡️ **Real sensor data** — CPU/GPU temperature, fan speed, voltages, memory and disk usage.
  **داده‌های واقعی سنسور** — دمای CPU/GPU، سرعت فن، ولتاژ، مصرف حافظه و دیسک.
- 🗣️ **Plain-language explanations** — every metric comes with a short "what this means" note.
  **توضیح به زبان ساده** — هر معیار با یک توضیح کوتاه «این یعنی چه» همراه است.
- 📊 **Before/after comparison** — scan before and after running a game, and see what changed.
  **مقایسه قبل و بعد** — قبل و بعد از اجرای بازی اسکن کنید و ببینید چه تغییری کرده.
- 🔒 **Privacy first** — everything runs locally; no data is sent anywhere.
  **حریم خصوصی اول** — همه چیز محلی اجرا می‌شود؛ هیچ داده‌ای ارسال نمی‌شود.
- 🎨 **Clean web UI** — no installation, no terminal, just a browser tab.
  **رابط وب تمیز** — بدون نصب، بدون ترمینال، فقط یک تب مرورگر.

## Screenshots | تصاویر

| Dashboard / داشبورد | Health Report / گزارش سلامت | Before/After / مقایسه |
|---|---|---|
| ![dashboard](docs/screenshot-dashboard.png) | ![report](docs/screenshot-report.png) | ![compare](docs/screenshot-compare.png) |

## How it works | نحوه کار

1. A small Python backend reads sensor data using [LibreHardwareMonitor](https://github.com/LibreHardwareMonitor/LibreHardwareMonitor)'s web server (or `psutil` for basic metrics).
   یک بک‌اند کوچک پایتون داده‌ها را از سرور وب LibreHardwareMonitor (یا `psutil` برای معیارهای پایه) می‌خواند.
2. The data is served to a simple HTML/JS frontend.
   داده‌ها به یک فرانت‌اند ساده HTML/JS ارسال می‌شوند.
3. The frontend displays a color-coded health report with plain-language explanations.
   فرانت‌اند یک گزارش سلامت رنگی با توضیحات ساده نمایش می‌دهد.

> **Note:** Temperature and fan sensors are currently Windows-only via LibreHardwareMonitor. Basic metrics (CPU/memory/disk) work on Windows, macOS, and Linux via `psutil`.
> **توجه:** سنسورهای دما و فن فعلاً فقط روی ویندوز و از طریق LibreHardwareMonitor در دسترس هستند. معیارهای پایه (CPU/حافظه/دیسک) روی ویندوز، مک و لینوکس با `psutil` کار می‌کنند.

## Quick start | شروع سریع

```bash
git clone https://github.com/yourusername/hardwaremd.git
cd hardwaremd
pip install -r requirements.txt
# Windows only (for temperature/fan sensors): enable "Remote Web Server" in LibreHardwareMonitor Options
python app.py
# Open http://localhost:5000
