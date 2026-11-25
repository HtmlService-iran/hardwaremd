# HardwareMD

> Your computer's health check, in plain language.
> بررسی سلامت کامپیوتر، به زبان ساده.

![demo](docs/demo.gif)

**[English](#english) | [فارسی](#فارسی)**

---

## English

**HardwareMD** is a lightweight, web-based dashboard that reads your computer's hardware sensors (CPU/GPU temperature, fan speed, memory usage, disk health) and tells you what they actually mean — no jargon, no command line, no confusing numbers.

### Why HardwareMD?

Most hardware monitoring tools show you a wall of numbers: 65°C, 1200 RPM, 42% usage. But if you're not a hardware enthusiast, you have no idea whether those numbers are good or bad.

HardwareMD is built for everyone else. It reads the same sensors, but translates them into:

- ✅ **Good** — everything is normal
- ⚠️ **Warning** — something needs attention (e.g., "Your CPU fan is running slower than usual")
- ❌ **Critical** — take action now (e.g., "Your GPU is overheating")

### Features

- 🖥️ **One-click scan** — open the page, click "Scan", get a health report
- 🌡️ **Real sensor data** — reads CPU/GPU temperature, fan speed, voltages, memory and disk usage
- 🗣️ **Plain-language explanations** — every metric comes with a short "what this means" note
- 📊 **Before/after comparison** — scan before and after running a game or heavy app, and see what changed
- 🔒 **Privacy first** — everything runs locally on your machine; no data is sent anywhere
- 🎨 **Clean web UI** — no installation, no terminal, just a browser tab

### Screenshots

| Dashboard | Health Report | Before/After |
|---|---|---|
| ![dashboard](docs/screenshot-dashboard.png) | ![report](docs/screenshot-report.png) | ![compare](docs/screenshot-compare.png) |

### How it works

1. A small Python backend reads sensor data using [LibreHardwareMonitor](https://github.com/LibreHardwareMonitor/LibreHardwareMonitor)'s web server (or `psutil` for basic metrics).
2. The data is served to a simple HTML/JS frontend.
3. The frontend displays a color-coded health report with plain-language explanations.

> **Note:** Temperature and fan sensors are only available on Windows via LibreHardwareMonitor. Basic metrics (CPU/memory/disk usage) work on Windows, macOS, and Linux via `psutil`.

### Quick start

```bash
# 1. Clone the repo
git clone https://github.com/yourusername/hardwaremd.git
cd hardwaremd

# 2. Install dependencies
pip install -r requirements.txt

# 3. (Windows only, for temperature/fan sensors) Download LibreHardwareMonitor
#    and enable "Remote Web Server" in Options
#    https://github.com/LibreHardwareMonitor/LibreHardwareMonitor/releases

# 4. Run
python app.py

# 5. Open http://localhost:5000 in your browser
