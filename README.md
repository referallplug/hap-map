# Scanner Map [![Discord](https://img.shields.io/badge/Discord-Join%20Now-5865F2?style=flat-square&logo=discord&logoColor=white)](https://discord.gg/X7vej75zZy)

A **real-time mapping system** for radio signals.
Ingests signal events from SDRTrunk, TrunkRecorder, or any **rdio-scanner compatible endpoint**, then:

- Extracts and geocodes locations
- Displays signal activity on an interactive map with filtering, clustering, and **Discord integration**

<img width="1918" height="906" alt="434934279-4f51548f-e33f-4807-a11d-d91f3a6b4db1(1)" src="https://github.com/user-attachments/assets/801a6bb1-ee8b-4dcf-95a0-7b4d665ef394" />

---

## 🔥 Recent Updates

- **Admin-restricted marker editing** — Map marker editing now locked behind admin user when authentication is enabled
- **Purge calls from map** — New admin-only feature to remove calls by talkgroup category and time range, includes undo button to restore accidentally purged calls
- Full **one-command integration** (no multiple terminals)
- Auto-generated API keys & admin users
- Improved **AI summaries & Ask AI** features
- Improved signal event storage and moderation workflows
- **Two-tone detection** — powered by [icad-tone-detection](https://github.com/TheGreatCodeholio/icad-tone-detection).
  - Detects fire/EMS tones in radio signal traffic
  - Optionally restrict address extraction to toned calls only, or combine tone + address detection for greater accuracy

---

## ✨ Features

### 🚀 Core
- **One-command startup:** `node bot.js`
- **Automatic setup:** database, API keys, talkgroups, admin accounts
- **Integrated services:** Discord bot + webserver run together

### 🗺️ Mapping
- Real-time calls displayed on a Leaflet map
- Marker clustering, heatmaps, day/night/satellite views
- Call details focused on mapped signal activity
- Call filtering and marker editing (admin-restricted when auth enabled)
- **Call purging:** Admin-only bulk removal with undo functionality

### 🤖 AI Enhancements
- Address extraction + geocoding (Google Maps or LocationIQ)
- AI summaries of recent transmissions
- "Ask AI" chat about call history
- Optional two‑tone detection for toned call filtering

### 🎮 Discord Integration
- Auto-post signal events by talkgroup
- Keyword alerts
- AI summaries with refresh buttons

### 🔒 Security
- Optional user authentication
- Auto-generated API keys
- Secure session management
- Admin-only controls for sensitive operations

---

## 📦 Installation

Supports **Windows 10/11** and **Debian/Ubuntu Linux**.
Installation scripts handle dependencies, configuration, and setup.

### Prerequisites
- SDRTrunk, TrunkRecorder, or rdio-scanner configured
- Talkgroup export from RadioReference (Premium subscription recommended)
- API key for **Google Maps** or **LocationIQ**
- (Optional) Discord Bot application

### Quick Start
```bash
# Linux
sudo bash linux_install_scanner_map.sh

# Windows (PowerShell as Admin)
.\install_scanner_map.ps1
```

Then:
```bash
cd scanner-map
source .venv/bin/activate   # Linux
node bot.js
```

---

## ⚙️ Configuration

All main settings are in `.env`. Key options:

- `DISCORD_TOKEN` — your bot token
- `Maps_API_KEY` / `LOCATIONIQ_API_KEY` — geocoding provider
- `MAPPED_TALK_GROUPS` — talkgroups to monitor
- `STORAGE_MODE` — `local` or `s3`
- `ENABLE_TONE_DETECTION` — enable/disable two‑tone detection

Other files to edit:
- `public/config.js` ← map defaults (center, zoom, icons, etc.)
- `data/apikeys.json` ← auto-generated on first run

---

## 📡 Connecting Your Radio Software

- **SDRTrunk:** Configure Streaming → Rdio Scanner endpoint
- **TrunkRecorder:** Add an `uploadServer` entry pointing to `http://<server>:<port>/api/call-upload`
- **rdio-scanner downstream:** Add server + API key

---

## 💻 System Requirements
- OS: Windows 10/11 or Debian/Ubuntu
- CPU: Modern multi-core
- RAM: 16GB+ recommended
- GPU: Optional for accelerated workloads
- Storage: SSD (capacity for signal history and map data)

---

## 🛠 Troubleshooting
- Logs: `combined.log` and `error.log`
- Check `.env` values (especially API keys and modes)
- Verify dependencies: Node and Python installed correctly
- Ensure correct geocoding.js (Google vs LocationIQ)

---

## 🤝 Contributing
Pull requests and issue reports are welcome.

## 📬 Support
- Open a GitHub Issue
- Contact **poisonednumber** on Discord
