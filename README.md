# ⚡️ Bunny & 10MS Stream Downloader Bot (DataSynth)

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.10%2B-blue?style=for-the-badge&logo=python" alt="Python Version" />
  <img src="https://img.shields.io/badge/Pyrogram-v2.0.106-green?style=for-the-badge&logo=telegram" alt="Pyrogram" />
  <img src="https://img.shields.io/badge/Flask-Web%20Server-orange?style=for-the-badge&logo=flask" alt="Flask" />
  <img src="https://img.shields.io/badge/Developer-Rabbi%20Sudo-purple?style=for-the-badge" alt="Developer" />
</p>

A high-performance, asynchronous Telegram bot built with **Pyrogram**, **Flask**, and **FFmpeg** for capturing, processing, and downloading video streams from **Bunny CDN** and **10 Minute School (10MS)** with live progress tracking, custom thumbnail handling, and multi-layer bytecode encryption.

---

## 👨‍💻 Developer Information

- **Developer:** **Rabbi Sudo**
- **Website:** [https://rabbisudo.dev/](https://rabbisudo.dev/)
- **Contact Email:** [rabbisudo@gmail.com](mailto:rabbisudo@gmail.com)
- **Telegram:** [Direct Message Rabbi Sudo](tg://user?id=6355601354)

---

## 🚀 Key Features

### 1. 🐰 Bunny CDN Video Downloader (`/bunny`)
- Automatic header and referer spoofing (`iframe.mediadelivery.net`).
- Concurrent fragment downloading via `yt-dlp` for maximum bandwidth utilization.
- Automatic CDN thumbnail and metadata extraction.
- Optional custom title assignment.

### 2. 🎓 10 Minute School Downloader (`/10ms`)
- **M3U8 Playlist Engine:** Injects signed URL credential parameters (`?md5=...&expires=...`) into every internal `.ts` segment.
- **Local Proxy Streaming:** Built-in Flask dynamic playlist server for seamless stream muxing.
- Direct remuxing to MP4 format with audio sync.

### 3. 🖼 Custom Thumbnail Suite
- **Caption Thumbnail:** Send an image with `/bunny [link]` or `/10ms [link]` in the caption to automatically attach that image as the video thumbnail.
- **Video Retouching:** Reply to any existing video with a photo to swap its thumbnail!
- **Default Thumbnail:**
  - `/setthumb` — Save a default thumbnail for all future downloads.
  - `/viewthumb` — View your current saved thumbnail.
  - `/delthumb` — Delete your saved thumbnail.

### 4. 📊 Live Visual Progress Bar
- Displays interactive percentage bar `[██████░░░░]`.
- Real-time download & upload speeds (`MB/s`).
- Live ETA countdown and dynamic size reporting.

### 5. 🌐 Integrated Flask Web Server
- Built-in lightweight web server running concurrently on port `8000` / `8080`.
- Health check endpoints (`/` and `/status`) for keep-alive services like UptimeRobot, Render, or Koyeb.

### 6. 🔒 7-Layer Bytecode Obfuscator (`encrypt.py`)
- Self-contained encryption tool that compiles source code into **7x nested Python bytecode (Marshal + Zlib + Base64)**.
- Produces `main_enc.py` which runs directly without exposing readable Python source code.

---

## 📋 Commands Reference

| Command | Description |
|---|---|
| `/start` | Welcome message and bot service overview |
| `/bunny [link] [title]` | Download video from Bunny Stream CDN |
| `/10ms [link] [title]` | Download video stream from 10 Minute School |
| `/setthumb` | Save or reply to a photo to set permanent thumbnail |
| `/viewthumb` | View your current saved thumbnail |
| `/delthumb` | Delete your saved thumbnail |
| `/dev` | Developer contact profile & inquiries |

---

## 🛠 Prerequisites

1. **Python 3.10 to 3.13** installed on your system.
2. **FFmpeg** installed and accessible in your system's PATH.
   - *Windows:* `winget install Gyan.FFmpeg` or download from [ffmpeg.org](https://ffmpeg.org/).
   - *Ubuntu / Debian:* `sudo apt update && sudo apt install -y ffmpeg`

---

## ⚙️ Installation & Setup

### 1. Clone the Repository
```bash
git clone https://github.com/rabbisudo/DataSynth.git
cd DataSynth
```

### 2. Install Dependencies
```bash
pip install -r requirements.txt
```

### 3. Configure Environment Variables
Create a `.env` file in the root directory (refer to `example.env`):

```env
API_ID=your_api_id
API_HASH=your_api_hash
BOT_TOKEN=your_telegram_bot_token
ADMIN_IDS=your_telegram_numeric_id
PORT=8000
```

> **Where to get credentials:**
> - `API_ID` & `API_HASH`: Get from [my.telegram.org](https://my.telegram.org/).
> - `BOT_TOKEN`: Create via [@BotFather](https://t.me/BotFather) on Telegram.
> - `ADMIN_IDS`: Your Telegram user ID (comma-separated for multiple admins).

---

## 🏃‍♂️ Running the Bot

```bash
python main.py
```

---

## 📄 License & Intellectual Property

© **Rabbi Sudo** — All Rights Reserved.  
For custom bots, web automation, scraping solutions, or licensing, contact: [rabbisudo@gmail.com](mailto:rabbisudo@gmail.com) or visit [https://rabbisudo.dev/](https://rabbisudo.dev/).
