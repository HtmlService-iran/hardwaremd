<div align="center">

# 🩺 HardwareMD

**Your computer's health check, in plain language.**
**بررسی سلامت کامپیوتر، به زبان ساده.**

[![Python](https://img.shields.io/badge/Python-3.10%2B-blue?logo=python&logoColor=white)](https://www.python.org/)
[![Flask](https://img.shields.io/badge/Flask-3.x-black?logo=flask&logoColor=white)](https://flask.palletsprojects.com/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Platform](https://img.shields.io/badge/Platform-Windows%20%7C%20macOS%20%7C%20Linux-lightgrey)]()
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)]()

[![GitHub stars](https://img.shields.io/github/stars/HtmlService-iran/hardwaremd?style=social)](https://github.com/yourusername/hardwaremd)
[![GitHub forks](https://img.shields.io/github/forks/HtmlService-iran/hardwaremd?style=social)](https://github.com/yourusername/hardwaremd)

![demo](docs/demo.gif)

</div>

---

## 🎯 What is HardwareMD? | HardwareMD چیست؟

**HardwareMD** is a lightweight, web-based dashboard that reads your computer's hardware sensors (CPU/GPU temperature, fan speed, memory usage, disk health) and tells you what they actually mean — no jargon, no command line, no confusing numbers.

**HardwareMD** یک داشبورد سبک و تحت وب است که سنسورهای سخت‌افزاری کامپیوتر شما (دمای CPU/GPU، سرعت فن، مصرف حافظه، سلامت دیسک) را می‌خواند و به زبان ساده می‌گوید این اعداد چه معنایی دارند — بدون اصطلاحات فنی، بدون خط فرمان، بدون اعداد گیج‌کننده.

## 🖼️ Preview | پیش‌نمایش

<div align="center">

| Dashboard / داشبورد | Health Report / گزارش سلامت | Before/After / مقایسه |
|:---:|:---:|:---:|
| ![dashboard](docs/screenshot-dashboard.png) | ![report](docs/screenshot-report.png) | ![compare](docs/screenshot-compare.png) |

</div>

## ✨ Why HardwareMD? | چرا HardwareMD؟

Most tools show a wall of numbers: `65°C`, `1200 RPM`, `42% usage`. If you're not a hardware enthusiast, you have no idea whether those are good or bad.

بیشتر ابزارها یک دیوار از اعداد نشان می‌دهند: `۶۵°C`، `۱۲۰۰ RPM`، `۴۲٪ مصرف`. اگر علاقه‌مند به سخت‌افزار نباشید، نمی‌دانید این اعداد خوب هستند یا بد.

<div align="center">

| ✅ Good / خوب | ⚠️ Warning / هشدار | ❌ Critical / بحرانی |
|:---:|:---:|:---:|
| Everything is normal | Something needs attention | Take action now |
| همه چیز طبیعی است | چیزی نیاز به توجه دارد | همین حالا اقدام کنید |

</div>

## 🚀 Features | امکانات

<table>
<tr>
<td width="50%">

**English**
- 🖥️ **One-click scan** — open the page, click "Scan", get a health report
- 🌡️ **Real sensor data** — CPU/GPU temp, fan speed, voltages, memory, disk
- 🗣️ **Plain-language explanations** — every metric has a "what this means" note
- 📊 **Before/after comparison** — see what changed after running a game
- 🔒 **Privacy first** — runs locally, no data sent anywhere
- 🎨 **Clean web UI** — no install, no terminal, just a browser tab

</td>
<td width="50%">

**فارسی**
- 🖥️ **اسکن با یک کلیک** — صفحه را باز کن، «اسکن» را بزن، گزارش بگیر
- 🌡️ **داده واقعی سنسور** — دمای CPU/GPU، سرعت فن، ولتاژ، حافظه، دیسک
- 🗣️ **توضیح ساده** — هر معیار یک توضیح «یعنی چه» دارد
- 📊 **مقایسه قبل/بعد** — ببین بعد از بازی چه تغییری کرده
- 🔒 **حریم خصوصی** — محلی اجرا می‌شود، داده‌ای ارسال نمی‌شود
- 🎨 **رابط تمیز** — بدون نصب، بدون ترمینال، فقط یک تب مرورگر

</td>
</tr>
</table>

## ⚙️ How it works | نحوه کار

```mermaid
flowchart LR
    A[LibreHardwareMonitor<br/>or psutil] -->|sensor data| B[Python Backend<br/>Flask]
    B -->|JSON API| C[HTML/JS Frontend]
    C -->|color-coded report| D[🖥️ Browser]
