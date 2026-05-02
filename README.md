<div align="center">

# ✨ FastVM

### 🌐 Linux Desktop. In a Tab.

**Transform your browser into a full Linux desktop environment.** No installation. No configuration. Just fork, click, and code.

[![Build and Publish FastVM Images](https://github.com/CloudCompile/fastvm/actions/workflows/build-images.yml/badge.svg?branch=main)](https://github.com/CloudCompile/fastvm/actions/workflows/build-images.yml)
[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![Docker Image](https://img.shields.io/badge/docker-ghcr.io-blue?logo=docker)](https://github.com/CloudCompile/fastvm/pkgs/container/fastvm)
[![GitHub stars](https://img.shields.io/github/stars/CloudCompile/fastvm?style=flat&color=yellow)](https://github.com/CloudCompile/fastvm/stargazers)

---

## 🚀 What is FastVM?

FastVM runs a **complete Linux desktop environment** inside a Docker container, streamed directly to your browser via KasmVNC. Built for **GitHub Codespaces** — everything you need is already there.

- ✅ **Zero setup** — Fork → Codespace → Run → Desktop
- ✅ **7 desktop environments** — XFCE4, KDE, GNOME, Cinnamon, LXQT, i3, Budgie
- ✅ **14 prebuilt images** — Deploy in 30-60 seconds
- ✅ **Full persistence** — Your files survive across sessions
- ✅ **Cloud-native** — Access from any device, anywhere

</div>

---

## 📑 Quick Navigation

| 🎯 | Topic | ⏱️ Time |
|---|-------|--------|
| 🚀 | [Quick Start](#-quick-start) | 5 min |
| ⚡ | [Prebuilt Images](#-using-prebuilt-images-fastest) | 1 min |
| 🔧 | [Customization](#️-customizing-fastvm) | 10 min |
| 🎨 | [Desktop Environments](#choosing-a-desktop-environment) | 2 min |
| 📊 | [Performance Tips](#troubleshooting) | 5 min |
| 🤝 | [Contributing](#-contributing) | — |

---

## 💡 How It Works

FastVM runs a full Linux desktop environment inside a Docker container. The desktop is streamed to your browser via a built-in web interface — no VNC client needed. Because it runs inside a GitHub Codespace, everything happens in the cloud:

- **No local installs** — Docker, Git, and everything else are already in the Codespace
- **Access from anywhere** — open your Codespace from any device with a browser
- **Persistent storage** — your files survive Codespace restarts via the `data/` folder
- **Auto-restart** — the container restarts automatically when your Codespace resumes

---

## 🚀 Quick Start

<table>
<tr><td>

### 1️⃣ Fork the Repository
Click **Fork** at the top of this page to create your own copy of FastVM.

</td><td>

### 2️⃣ Open in Codespace
On your forked repo, click **Code → Codespaces → Create codespace on main**

> 💡 **Pro Tip:** Choose a **4-core / 16 GB** machine for the best experience. XFCE4 works on 2-core; KDE/GNOME need more.

</td></tr>
<tr><td>

### 3️⃣ Configure (Optional)
Edit `config.env` to customize:

```bash
FASTVM_TZ=America/New_York   # Your timezone
FASTVM_DE=XFCE4              # Desktop (KDE, GNOME, etc.)
```

</td><td>

### 4️⃣ Install
In the terminal:

```bash
chmod +x fastvm-install.sh
./fastvm-install.sh
```

⏳ Grab coffee — first build takes 5–15 minutes

</td></tr>
<tr><td colspan="2">

### 5️⃣ Access Your Desktop
When ready, you'll see:
```
  ✓ Local URL: http://localhost:3000
```

Click **Open in Browser** or use the Ports tab. Your desktop loads in seconds. 🎉

</td></tr>
</table>

---

## ⚡ Using Prebuilt Images (Instant!)

### 🎯 One-liner Deployments

Skip the 5–15 minute build. Deploy in **30-60 seconds**:

```bash
# 🔥 Blazing Fast (30s)  — XFCE4 + Minimal
docker run -d -p 3000:3000 ghcr.io/cloudcompile/fastvm:xfce4-fast-latest

# 🪶 Lightweight (40s) — LXQT + Minimal  
docker run -d -p 3000:3000 ghcr.io/cloudcompile/fastvm:lxqt-fast-latest

# 👑 Full-Featured (60s) — KDE Desktop
docker run -d -p 3000:3000 ghcr.io/cloudcompile/fastvm:kde-latest
```

Then open **http://localhost:3000** in your browser. Done! 🚀

---

### 📦 All Available Variants

<details>
<summary><strong>Click to expand all 14 variants</strong></summary>

| Desktop | ⚙️ Standard | ⚡ Fast (Optimized) |
|---------|-----------|-----------------|
| **XFCE4** 🏃 | `xfce4-latest` | `xfce4-fast-latest` |
| **KDE** 👑 | `kde-latest` | `kde-fast-latest` |
| **GNOME** 🍒 | `gnome-latest` | `gnome-fast-latest` |
| **Cinnamon** 🎨 | `cinnamon-latest` | `cinnamon-fast-latest` |
| **LXQT** 🪶 | `lxqt-latest` | `lxqt-fast-latest` |
| **i3** ⌨️ | `i3-latest` | `i3-fast-latest` |
| **Budgie** 🎯 | `budgie-latest` | `budgie-fast-latest` |

</details>

---

### 🔄 Standard vs Fast

| Feature | Standard | ⚡ Fast |
|---------|----------|---------|
| **Preset** | Full (Wine, Chrome, etc.) | Minimal (Terminal + Browser) |
| **Audio** | ✅ Enabled | ❌ Disabled |
| **Recording** | ✅ Enabled | ❌ Disabled |
| **Backups** | ✅ Enabled | ❌ Disabled |
| **Size** | ~2.5 GB | ~1.7 GB |
| **Startup** | 60s | 30-40s |

---

### 🛠️ Custom Builds

Need a specific combination? Build it yourself:

```bash
./fastvm-install.sh
```

The installer gives you total control over features and desktop environment.

---

## 🖥️ Accessing Your Desktop

### 🔗 Finding the URL

**After Codespace restart:**
1. Open **Ports** tab in VS Code (`Ctrl+Shift+P` → "Ports")
2. Find port **3000** → Click the globe 🌐

**Or directly:** `http://localhost:3000`

---

### 🌐 Sharing with Others

| Scenario | Steps |
|----------|-------|
| **Private** (just you) | Default — nothing to do |
| **Share temporarily** | Ports tab → Right-click 3000 → **Port Visibility → Public** |
| **Permanent share** | Use Codespace settings to enable public ports |

> ⚠️ **Security:** Public ports are accessible by anyone with the URL. Only enable if you trust your users.

---

### 🎨 What You'll See

Your desktop is ready to use! Standard features:

```
┌─────────────────────────────────────┐
│  🖱️  Right-click       → App menu    │
│  📁  File Manager     → Browse files │
│  💻  Terminal        → Run commands  │
│  🌐  Browser         → Web access   │
└─────────────────────────────────────┘
```

---

## ⚙️ Customizing FastVM

Edit `config.env` and restart FastVM for changes to take effect.

### 🎨 Choose Your Desktop

| Desktop | Characteristics | Best For |
|---------|---|---|
| 🏃 **XFCE4** | Fast, lightweight, clean | **👍 Recommended** — default choice |
| 👑 **KDE** | Full-featured, eye candy | Power users, 4+ cores |
| 🍒 **GNOME** | Modern, polished, heavy | Modern workflow, 8+ cores |
| 🎨 **Cinnamon** | Windows-like feel | Windows users, 4+ cores |
| 🪶 **LXQT** | Ultra-light, minimal | 2-core Codespaces |
| ⌨️ **i3** | Keyboard-driven tiling | Terminal power users |
| 🎯 **Budgie** | Minimal, clean | Fast desktops |

**Setting:** `FASTVM_DE=XFCE4`

---

### 📦 Select Apps to Install

```bash
# Productivity
FASTVM_APP_WINE=true              # Windows .exe support
FASTVM_APP_LIBREOFFICE=false      # Office suite

# Media & Entertainment
FASTVM_APP_CHROME=true            # Chrome browser
FASTVM_APP_DISCORD=false          # Discord
FASTVM_APP_STEAM=false            # Game launcher
FASTVM_APP_VLC=false              # Media player

# Development
FASTVM_PROG_VSCODIUM=false        # VS Code (open-source)
FASTVM_PROG_JAVA17=false          # Java 17 compiler
```

> 💡 Fewer apps = faster builds & smaller images

---

### 🖥️ Pick Your Codespace Size

<table>
<tr><th>Machine</th><th>RAM</th><th>Recommended</th><th>Notes</th></tr>
<tr><td>2-core</td><td>8 GB</td><td>XFCE4 · LXQT</td><td>✅ Works · ⚠️ Avoid heavy apps</td></tr>
<tr><td>4-core</td><td>16 GB</td><td>XFCE4 · KDE · Cinnamon</td><td>✅ Comfortable · Good balance</td></tr>
<tr><td>8-core</td><td>32 GB</td><td>Any</td><td>✅ Smooth · All features shine</td></tr>
</table>

---

## 🐳 Managing FastVM

Use these commands to control your FastVM container:

| Command | What It Does |
|---------|---|
| `docker-compose up -d` | Start FastVM |
| `docker-compose stop` | Stop FastVM (preserve data) |
| `docker-compose restart` | Restart FastVM |
| `docker-compose logs -f` | View live logs |
| `docker-compose down` | Remove container (data stays) |

> 🔐 **Your data is always safe** in `./data/` — even after `docker-compose down`

### 🔄 Update to Latest

```bash
git pull                    # Get latest FastVM code
docker-compose build        # Rebuild with new changes
docker-compose up -d        # Start updated version
```

---

## 🛠️ Troubleshooting

<details>
<summary><strong>❌ Port isn't showing / page won't load</strong></summary>

The container may still be starting. Wait 60 seconds and refresh.

**Check if it's running:**
```bash
docker ps
```

**View logs if it's not:**
```bash
docker-compose logs
```

</details>

<details>
<summary><strong>🐢 Desktop is slow</strong></summary>

**Option 1:** Upgrade your Codespace → Codespace settings → 4-core or 8-core machine

**Option 2:** Use a lighter desktop in `config.env`:
```bash
FASTVM_DE=XFCE4  # or LXQT for ultra-light
```

**Option 3:** Increase shared memory:
```bash
FASTVM_SHM_SIZE=4gb
```

</details>

<details>
<summary><strong>🔒 "Permission denied" errors</strong></summary>

Fix file ownership:
```bash
sudo chown -R 1000:1000 ./data
```

</details>

<details>
<summary><strong>💥 Build failed</strong></summary>

Try a clean rebuild:
```bash
docker-compose down
docker-compose build --no-cache
docker-compose up -d
```

</details>

<details>
<summary><strong>⚙️ Changes to config.env not taking effect</strong></summary>

You need to restart from scratch:
```bash
docker-compose down
./fastvm-install.sh
```

</details>

---

## 📁 File Structure

```
fastvm/
├── config.env              ← Edit this to customize FastVM
├── docker-compose.yml      ← Defines how Docker runs the container
├── Dockerfile.optimized    ← Instructions for building the image
├── fastvm-install.sh       ← The installer script
├── fastvm-setup.sh         ← Sets up the desktop environment inside the container
├── installapps-parallel.sh ← Installs your selected apps in parallel
├── README.md               ← This file
├── data/                   ← Your persistent files (created on first run)
└── logs/                   ← Log files (created on first run)
```

---

## 🤝 Contributing

Contributions are welcome! When contributing code, please follow these conventions already used in the project:

- Scripts use `set -euo pipefail` for strict error handling
- No unnecessary `sleep` delays
- Use `jq -e` instead of `jq | grep`
- Consolidate APT operations into a single `apt-get update`
- Add logging with the `log_info` / `log_success` / `log_warn` / `log_error` helpers

---

<div align="center">

## 💝 Support

Found a bug? Have an idea? 

**[Open an Issue](https://github.com/CloudCompile/fastvm/issues)** · **[Start a Discussion](https://github.com/CloudCompile/fastvm/discussions)**

---

## 📜 License & Credits

**License:** MIT — See [LICENSE](LICENSE)

**Built on:** [BlobeVM](https://github.com/DockSTARTER/blobevmx) · **Base image:** [LinuxServer.io](https://www.linuxserver.io/) · **Powered by:** [Docker](https://www.docker.com/)

---

### ⭐ Enjoying FastVM? Star us on GitHub!

</div>
