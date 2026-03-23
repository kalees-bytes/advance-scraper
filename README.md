# 🕷️ Web Scraper Pro v3.0

> Advanced Python web scraper with AI parsing, scheduling, change detection, proxy rotation, login support, and multi-format export.

---

## ✨ Features

| Feature | Description |
|---|---|
| 🤖 **3-Engine Fallback** | requests → cloudscraper → Playwright. Never fails. |
| 🧠 **AI Content Parsing** | Uses OpenAI GPT to auto-label extracted data |
| ⏰ **Scheduler** | Run scrapes hourly, daily, weekly, or every N minutes |
| 🔔 **Change Detection** | Detects when a page changes and alerts you |
| 🔄 **Proxy Rotation** | Load a proxy list and auto-rotate between IPs |
| 🔐 **Login Support** | Scrape behind login walls — form-based & browser |
| 📊 **Multi-format Export** | JSON, CSV, Excel (.xlsx), SQLite, Markdown |
| 📧 **Notifications** | Email or Telegram alerts on page changes |

---

## 📦 Installation

```bash
git clone https://github.com/YOUR_USERNAME/web-scraper-pro
cd web-scraper-pro
pip install -r requirements.txt
playwright install chromium
```

---

## 🚀 Usage

```bash
# Basic scrape (auto-detects everything)
python advanced_scraper.py https://srmist.edu.in

# Specific modes
python advanced_scraper.py https://srmist.edu.in --mode emails
python advanced_scraper.py https://srmist.edu.in --mode links
python advanced_scraper.py https://srmist.edu.in --mode tables
python advanced_scraper.py https://srmist.edu.in --mode prices

# Export formats
python advanced_scraper.py https://srmist.edu.in --output excel
python advanced_scraper.py https://srmist.edu.in --output sqlite
python advanced_scraper.py https://srmist.edu.in --output csv

# Force real browser (works on any JS site)
python advanced_scraper.py https://srmist.edu.in --playwright

# Crawl multiple pages
python advanced_scraper.py https://srmist.edu.in --pages 5

# Custom CSS selectors
python advanced_scraper.py https://books.toscrape.com --mode custom \
  --selectors title=h3>a price=.price_color rating=.star-rating

# Proxy rotation
python advanced_scraper.py https://srmist.edu.in --proxy-file proxies.txt

# Login support
python advanced_scraper.py https://site.com/login \
  --login user=myuser pass=mypassword

# AI-powered content analysis
python advanced_scraper.py https://srmist.edu.in --ai-parse \
  --ai-key YOUR_OPENAI_KEY

# Change detection + Telegram alert
python advanced_scraper.py https://srmist.edu.in --watch --notify telegram

# Change detection + Email alert
python advanced_scraper.py https://srmist.edu.in --watch \
  --notify email --notify-target you@gmail.com

# Scheduled scraping (runs daily at 9am)
python advanced_scraper.py https://srmist.edu.in --schedule daily

# Every 30 minutes
python advanced_scraper.py https://srmist.edu.in --schedule 30
```

---

## 🔧 Environment Variables

Set these for notifications and AI:

```bash
# Windows PowerShell
$env:OPENAI_API_KEY = "sk-..."
$env:TELEGRAM_BOT_TOKEN = "123456:ABC..."
$env:TELEGRAM_CHAT_ID = "123456789"
$env:NOTIFY_EMAIL = "you@gmail.com"
$env:NOTIFY_PASS = "your_app_password"
```

---

## 📁 Proxy File Format

Create `proxies.txt` with one proxy per line:

```
123.456.789.0:8080
http://user:pass@proxy.example.com:3128
socks5://127.0.0.1:1080
```

---

## 📤 Output Files

| Format | Flag | File |
|---|---|---|
| JSON | `--output json` | `scraped_*.json` |
| CSV | `--output csv` | `scraped_*.csv` |
| Excel | `--output excel` | `scraped_*.xlsx` |
| SQLite DB | `--output sqlite` | `scraped_*.db` |
| Markdown | `--output md` | `scraped_*.md` |

---

## 🌐 Supported Site Types

| Site Type | Engine Used |
|---|---|
| Normal HTML sites | requests |
| Cloudflare-protected | cloudscraper |
| React/Vue/Angular JS apps | Playwright |
| Login-required pages | requests session / Playwright |
| Any site | Playwright (--playwright flag) |

---

## 📋 Requirements

- Python 3.8+
- Windows / Mac / Linux

---

## 📄 License

MIT License — free to use and modify.
