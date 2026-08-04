<div align="center">

<!-- Header Banner -->
<img src="https://capsule-render.vercel.app/api?type=waving&color=0:09090e,40:2a0845,100:640023&height=220&section=header&text=PAIN%20BOT%20v2.0&fontSize=52&fontColor=ffffff&animation=twinkling&fontAlignY=35" width="100%" />

<!-- Animated Typing Subtitle -->
<a href="https://drift.rip/muaz">
  <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=20&pause=1000&color=FF2E63&center=true&vCenter=true&width=700&lines=Multi-Device+WhatsApp+Bot;Powered+by+Baileys+(Node.js);Akatsuki+%26+Nagato+Themed;Engineered+by+Muaz" alt="Typing SVG" />
</a>

<br><br>

<!-- Showcase Media -->
<a href="https://drift.rip/muaz"> 
  <img src="https://i.postimg.cc/rFn9X6CL/bot-image.jpg" alt="Pain Bot Showcase" height="310" style="border-radius: 16px; box-shadow: 0 0 25px rgba(255, 46, 99, 0.4);"> 
</a>

<br><br>

<!-- Tech Badges -->
[![Node.js](https://img.shields.io/badge/Node.js-v18%2B-339933?style=for-the-badge&logo=nodedotjs&logoColor=white)](https://nodejs.org/)
[![Baileys](https://img.shields.io/badge/Library-Baileys-FF2E63?style=for-the-badge&logo=whatsapp&logoColor=white)](https://github.com/WhiskeySockets/Baileys)
[![License](https://img.shields.io/badge/License-MIT-00ADB5?style=for-the-badge&logo=open-source-initiative&logoColor=white)](LICENSE)
[![Developer](https://img.shields.io/badge/Developer-Muaz-8A2BE2?style=for-the-badge&logo=codeforces&logoColor=white)](https://drift.rip/muaz)

</div>

---

### 🐍 Contribution Activity

<div align="center">
  <img src="https://raw.githubusercontent.com/Platane/snk/output/github-contribution-grid-snake.svg" alt="GitHub Contribution Grid Snake" width="100%" />
</div>

---

> [!NOTE]
> **“The world shall know pain.”** — Pain Bot is a multi-device WhatsApp automation suite themed around **Pain / Nagato** from Naruto. Packed with high-speed group administration, AI interaction, media downloaders, canvas processing, and Akatsuki-exclusive features.

---

## ⚡ Core Architecture

<div align="center">
  <img src="https://i.imgur.com/dAnA42f.gif" width="100%" height="3px" />
</div>

* 🔄 **Hot-Reload Dynamic Prefix:** Reads command prefixes straight from `data/prefix.json`. Update on-the-fly using `.setprefix` without restarting the process.
* 🛡️ **Dual-Layer Access Control:** Toggle between `.mode public` and `.mode private` instantly. Private mode locks commands exclusively to Sudo/Owners while group moderation protection remains active.
* ⛔ **Global Bot-Level Ban Engine:** Lock unauthorized users out across all instances. Banned users encounter silent reactions with periodic warning prompts.
* 👥 **Sudo Authorization System:** Grant specific users elevated admin overrides independent of their WhatsApp group role.
* 🎯 **Strict Command Matching:** Zero-collision exact keyword evaluation prevents accidental triggers (e.g., `.bansho` won't trigger `.ban`).
* 🧹 **Automated Memory Guard:** Scheduled background cleanup clears temporary media and Baileys session files every 6 hours to minimize resource overhead.

---

## 📜 Command Hub

<details open>
<summary><b>🫸 Pain / Nagato Exclusive Commands</b></summary>

| Command | Description |
|---|---|
| `.pain` | Emits Pain's iconic *"Ore wa Pain"* dialogue with self-reaction. |
| `.about` | Displays in-character lore, Rinnegan powers, and 6 Paths breakdown. |
| `.intro` | Streams Pain’s cinematic entrance video. |
| `.theme` / `.themealt` | Plays the main or alternate Pain audio themes. |
| `.almpush` | Sound effect: *Almighty Push (Shinra Tensei)*. |
| `.uvpull` / `.uvpull-jp` | Sound effect: *Universal Pull (Bansho Ten'in)*. |
| `.shinra` / `.chibaku` | Sound effects for *Shinra Tensei* and *Chibaku Tensei*. |
| `.greater` | Plays the *Greater Pain* audio clip. |

</details>

<details>
<summary><b>👮 Group Administration & Moderation</b></summary>

*(Requires group admin status or owner/sudo privileges)*

| Command | Description |
|---|---|
| `.ban` / `.unban @user` | Applies or removes bot-level command restrictions. |
| `.kick` / `.promote` / `.demote` | Manages group member roles and membership. |
| `.mute [mins]` / `.unmute` | Mutes/unmutes group chat with optional auto-timer. |
| `.warn` / `.warnings @user` | Warns a user; automatically kicks upon 3 warnings. |
| `.delete` / `.del` | Removes specific messages or bulk deletes recent chat history. |
| `.tagall` / `.hidetag` / `.tag` | Tag members en masse or send stealth notifications. |
| `.tagnotadmin` | Mentions all non-admin members in a single sweep. |
| `.antilink` / `.antibadword` | Toggles automatic link deletion and obfuscation-resistant profanity filters. |
| `.antitag` | Blocks mass-mention spam attacks with automatic action execution. |
| `.welcome` / `.goodbye` | Configures welcome/leave greeting cards with variable interpolation. |
| `.resetlink` / `.setgdesc` | Administrative utility controls for group parameters. |

</details>

<details>
<summary><b>🔒 Owner & System Management</b></summary>

| Command | Description |
|---|---|
| `.mode public/private` | Toggles global accessibility for the bot. |
| `.setprefix <symbol>` | Updates the active trigger prefix live. |
| `.sudo add/del/list` | Manages elevated privilege access lists. |
| `.antidelete on/off` | Captures deleted messages and view-once media directly to owner DM. |
| `.clearsession` / `.cleartmp` | Cleans up session residue and temporary cache directories. |
| `.update [zip-url]` | Pulls latest repository builds and auto-restarts. |
| `.autostatus` / `.autoread` | Automated status viewing, reaction engine, and blue-tick toggles. |
| `.pmblocker` / `.anticall` | Auto-blocks unsolicited private messages and call attempts. |

</details>

<details>
<summary><b>🎨 Image, Sticker & Canvas Tools</b></summary>

| Command | Description |
|---|---|
| `.sticker` / `.crop` / `.simage` | Converts images/videos to stickers, square crops, or unpacks stickers to images. |
| `.take <packname>` | Repacks stickers with custom metadata branding. |
| `.removebg` / `.remini` | AI background removal and image quality upscaling. |
| `.emojimix` | Merges two emojis into a single custom sticker. |
| `.tgsticker <link>` | Downloads complete sticker packs directly from Telegram. |
| `.text-effects` | 17+ Stylized text effects (`.neon`, `.matrix`, `.hacker`, `.fire`, `.glitch`, etc.). |
| `.canvas-filters` | Canvas effects (`.wasted`, `.simp`, `.passed`, `.triggered`, `.tweet`, `.oogway`). |

</details>

<details>
<summary><b>📥 Media Downloaders & AI Tools</b></summary>

| Command | Description |
|---|---|
| `.play` / `.mp3` / `.video` | YouTube media searching and high-speed extraction. |
| `.spotify` / `.insta` / `.fb` / `.tt` | Multi-platform social media media content downloaders. |
| `.gpt` / `.gemini` | Solves complex prompts and queries using AI models. |
| `.imagine` / `.sora` | Generates text-to-image and short AI video media from text. |

</details>

---

## 🛠️ Setup & Deployment

### 📋 Prerequisites
* **Node.js** v18.0.0 or higher
* **Git** installed
* **FFmpeg** configured in your system environment PATH

### 🚀 Quick Start

```bash
# 1. Clone the repository
git clone [https://github.com/ahsanhabibmuaz/pain-bot-2.git](https://github.com/ahsanhabibmuaz/pain-bot-2.git)
cd pain-bot-2

# 2. Install dependencies
npm install

# 3. Configure settings
# Edit settings.js with your owner number and preferences

# 4. Launch Pain Bot
npm start
