# 🫸 Pain Bot v2.0

A feature-packed WhatsApp bot built with the **Baileys** (Node.js) library, themed around **Pain / Nagato** from Naruto. Pain Bot handles group moderation, downloads, AI chat, games, image/sticker tools, and a full set of Akatsuki-flavored fun commands — all from a simple `.` prefix.

<div align="center"> 
  <a href="https://git.io/typing-svg"> 
    <img src="https://readme-typing-svg.demolab.com?font=Ribeye&size=50&pause=1000&color=33ff00&center=true&width=910&height=100&lines=Pain-Bot;Multi+Device+WhatsApp+Bot;Coded+By+Muaz" alt="Typing SVG" />
  </a> 
</div>

<div align="center"> 
  <a href="https://drift.rip/muaz"> 
    <img src="https://i.postimg.cc/rFn9X6CL/bot-image.jpg" alt="Pain Bot" height="300"> 
  </a> 
</div>

---

## 📖 About

Pain Bot is a multi-device WhatsApp bot powered by [Baileys](https://github.com/WhiskeySockets/Baileys). It runs entirely in Node.js, connects via QR code or pairing code, and gives group admins powerful moderation tools while also packing in AI chat, media downloaders, sticker creation, games, and a dedicated **Pain (Nagato)**-themed command set.

Default command prefix is `.` and can be changed live with `.setprefix`.

---

## ⚙️ Core Systems

- **Dynamic Prefix** — the bot reads its command prefix from `data/prefix.json` on every message, so `.setprefix` (or hand-editing the file) takes effect instantly without a restart.
- **Public / Private Mode** — `.mode public` lets everyone use the bot; `.mode private` restricts commands to the owner/sudo only (moderation like antilink/antibadword/antitag still runs in groups either way).
- **Owner & Sudo System** — the bot owner (set in `settings.js`) and any number of sudo users (`.sudo add/del/list`) get elevated access to owner-only commands and moderation overrides, independent of WhatsApp group admin status.
- **Ban System** — `.ban` / `.unban` block a user from using *any* bot command. This is a bot-level restriction (not a WhatsApp group action), so it works for the owner/sudo even without the bot being a group admin. Banned users get a silent 🚫 reaction on each attempt, with an occasional reminder message every ~10–12 tries.
- **Exact Command Matching** — commands are matched precisely (e.g. `.bansho` will never accidentally trigger `.ban`), preventing prefix-collision bugs.
- **Lightweight Message Store** — keeps a small rolling window of recent messages per chat for features like `.delete`, antidelete, and quoting.
- **Auto Temp Cleanup** — temp/session files are periodically purged to avoid disk/RAM bloat on hosted panels.

---

## 🌐 General Commands

| Command | Description |
|---|---|
| `.help` / `.menu` / `.bot` / `.list` | Shows the full categorized command list with the bot's current prefix and version. |
| `.ping` | Checks the bot's response latency and uptime. |
| `.alive` | Confirms the bot is online and shows its current mode/version. |
| `.tts <text>` | Converts text into a spoken voice note (Text-to-Speech). |
| `.owner` | Sends the bot owner's contact card (vCard). |
| `.joke` | Fetches a random dad joke. |
| `.quote` | Sends a random inspirational quote. |
| `.fact` | Sends a random fun/useless fact. |
| `.weather <city>` | Gets current weather and temperature for any city. |
| `.news` | Shows the latest top headlines. |
| `.lyrics <song title>` | Fetches lyrics for a song. |
| `.8ball <question>` | Ask the magic 8-ball a yes/no question. |
| `.groupinfo` / `.infogp` | Displays group ID, name, member count, owner, admins, and description. |
| `.staff` / `.admins` / `.listadmin` | Lists all group admins with mentions. |
| `.vv` | Reveals/re-sends a "view once" image or video you reply to. |
| `.translate <text> <lang>` / `.trt` | Translates text (or a replied message) into any language. |
| `.ss <url>` / `.ssweb` / `.screenshot` | Takes a screenshot of any website. |
| `.jid` | Shows the current group's JID. |
| `.url` | Uploads a replied/attached media file and returns a direct download URL. |
| `.settings` | Shows the current status of every toggleable feature (mode, autoread, antilink, etc.) — owner only. |

---

## 👮 Group Admin Commands

*(Require the sender to be a group admin, or the bot owner/sudo. The bot itself must be a group admin for most of these.)*

| Command | Description |
|---|---|
| `.ban @user` | Bans a user from using any bot command (bot-level ban, not a WhatsApp removal). |
| `.unban @user` | Lifts a bot-level ban. |
| `.promote @user` | Promotes a member to group admin. |
| `.demote @user` | Removes a member's admin status. |
| `.kick @user` | Removes a member from the group. |
| `.mute [minutes]` | Locks the group so only admins can send messages; optional auto-unmute timer. |
| `.unmute` | Unlocks the group for everyone. |
| `.delete` / `.del [count] [@user]` | Deletes recent messages — from a specific user, a replied message, or the last N group messages. |
| `.kick`, `.warn @user` | Issues a warning to a user; auto-kicks after 3 warnings. |
| `.warnings @user` | Checks how many warnings a user has. |
| `.tag <message>` | Sends a message/media that tags every group member individually. |
| `.tagall` | Tags every group member in a single message. |
| `.tagnotadmin` | Tags only the non-admin members. |
| `.hidetag <message>` | Sends a message that mentions everyone without visibly listing their names. |
| `.antilink on/off/set` | Auto-deletes (or kicks/warns for) messages containing links. |
| `.antibadword on/off/set` | Filters profanity/slurs using obfuscation-resistant detection (leetspeak, separators) and deletes/kicks/warns offenders. |
| `.antitag on/off/set` | Detects and blocks mass-tagging spam (tagall abuse) with delete/kick actions. |
| `.chatbot on/off` | Enables an AI chatbot that responds when the bot is mentioned or replied to in the group. |
| `.welcome on/off/set` | Sends a custom welcome image/message to new members (supports `{user}`, `{group}`, `{description}` variables). |
| `.goodbye on/off/set` | Sends a custom goodbye message when members leave. |
| `.resetlink` / `.revoke` | Resets the group's invite link. |
| `.setgdesc <text>` | Updates the group description. |
| `.setgname <text>` | Updates the group name. |
| `.setgpp` | Updates the group profile picture (reply to an image). |
| `.clear` | Clears the bot's own recent message in the chat. |

---

## 🔒 Owner-Only Commands

| Command | Description |
|---|---|
| `.mode public/private` | Switches the bot between public (anyone) and private (owner/sudo only) access. |
| `.setprefix <. + * #>` | Changes the active command prefix. |
| `.sudo add/del/list` | Manages sudo users who get elevated bot permissions. |
| `.clearsession` | Cleans up stale Baileys session/auth files to improve performance. |
| `.antidelete on/off` | Captures deleted messages/media (including view-once) and forwards them to the owner. |
| `.cleartmp` | Manually clears the temp media folder (also runs automatically every 6 hours). |
| `.update [zip-url]` | Pulls the latest bot code via Git (or a ZIP fallback) and restarts. |
| `.setpp` | Changes the bot's own WhatsApp profile picture (reply to an image). |
| `.areact` / `.autoreact on/off` | Toggles automatic ⏳ reactions on every command. |
| `.autostatus on/off` / `.autostatus react on/off` | Auto-views contacts' WhatsApp statuses and optionally reacts to them. |
| `.autotyping on/off` | Shows a fake "typing…" indicator before the bot replies. |
| `.autoread on/off` | Automatically marks incoming messages as read. |
| `.anticall on/off` | Auto-rejects and blocks anyone who calls the bot. |
| `.pmblocker on/off/status/setmsg` | Blocks/auto-responds to direct messages from non-owners. |
| `.setmention` | Sets a custom media/text reply for when the bot is @mentioned. |
| `.mention on/off` | Toggles the custom mention-reply feature. |

---

## 🎨 Image & Sticker Commands

| Command | Description |
|---|---|
| `.sticker` / `.s` | Converts a replied/sent image or video into a sticker. |
| `.simage` | Converts a replied sticker back into an image. |
| `.crop` | Converts media into a square-cropped sticker. |
| `.take <packname>` | Re-packs a replied sticker under a new sticker pack name. |
| `.blur` | Applies a blur effect to a replied/sent image. |
| `.removebg` / `.rmbg` / `.nobg` | Removes the background from an image. |
| `.remini` / `.enhance` / `.upscale` | AI-enhances/upscales a photo's quality. |
| `.emojimix <emoji1>+<emoji2>` | Fuses two emojis into a single sticker (Emoji Kitchen style). |
| `.tgsticker <link>` / `.tg` | Downloads an entire Telegram sticker pack. |
| `.attp <text>` | Generates an animated blinking-text sticker. |
| `.igs <link>` / `.igsc <link>` | Converts Instagram photos/reels into stickers (with optional square crop). |
| `.metallic`, `.ice`, `.snow`, `.impressive`, `.matrix`, `.light`, `.neon`, `.devil`, `.purple`, `.thunder`, `.leaves`, `.1917`, `.arena`, `.hacker`, `.sand`, `.blackpink`, `.glitch`, `.fire` `<text>` | 17 different stylized text-effect image generators. |

---

## 📥 Media Downloaders

| Command | Description |
|---|---|
| `.play` / `.mp3` / `.ytmp3` / `.song <query>` | Downloads a song as an MP3 from YouTube by name or link. |
| `.video` / `.ytmp4 <query>` | Downloads a YouTube video as MP4. |
| `.music <query>` | Alternate music downloader endpoint. |
| `.spotify <query>` | Searches and downloads a track from Spotify. |
| `.instagram` / `.insta` / `.ig <link>` | Downloads Instagram photos/reels/videos. |
| `.facebook` / `.fb <link>` | Downloads Facebook videos. |
| `.tiktok` / `.tt <link>` | Downloads TikTok videos without watermark. |
| `.imagine` / `.flux` / `.dalle <prompt>` | Generates an AI image from a text prompt. |
| `.sora <prompt>` | Generates a short AI text-to-video clip. |

---

## 🎮 Game Commands

| Command | Description |
|---|---|
| `.tictactoe` / `.ttt [room name]` | Starts or joins a Tic-Tac-Toe match; play by typing numbers 1–9. |
| `.hangman` | Starts a game of Hangman. |
| `.guess <letter>` | Guesses a letter in the current Hangman game. |
| `.trivia` | Starts a random trivia question. |
| `.answer <answer>` | Submits an answer to the active trivia question. |
| `.truth` | Sends a random Truth prompt. |
| `.dare` | Sends a random Dare prompt. |

---

## 🤖 AI Commands

| Command | Description |
|---|---|
| `.gpt <question>` | Asks a question to a ChatGPT-style AI. |
| `.gemini <question>` | Asks a question to Google's Gemini AI. |
| `.chatbot on/off` | Enables free-flowing AI conversation when the bot is mentioned/replied to (group admin command). |

---

## 🎯 Fun & Social Commands

| Command | Description |
|---|---|
| `.compliment @user` | Sends a random wholesome compliment to a mentioned/replied user. |
| `.insult @user` | Sends a random (playful) roast to a mentioned/replied user. |
| `.flirt` | Sends a random pickup line. |
| `.shayari` | Sends a random shayari (poetic verse). |
| `.goodnight` / `.gn` / `.lovenight` | Sends a goodnight message. |
| `.roseday` | Sends a Rose Day themed message. |
| `.character @user` | Generates a fun randomized "character analysis" card for a user. |
| `.wasted @user` | Overlays the GTA "WASTED" effect on a user's profile picture. |
| `.ship @user1 @user2` | Randomly ships two group members together with a compatibility message. |
| `.simp @user` | Generates a "simp card" image for a user. |
| `.stupid @user [text]` / `.itssostupid` | Generates a meme "it's so stupid" card for a user. |

---

## 🧩 Misc Canvas Commands

| Command | Description |
|---|---|
| `.heart` | Generates a heart-frame avatar image. |
| `.horny` | Generates a "horny" badge overlay. |
| `.circle` | Crops your/replied avatar into a circle. |
| `.lgbt` | Adds a pride-flag overlay to an avatar. |
| `.lolice` | Generates a "lolice" badge overlay. |
| `.namecard <username|birthday|desc>` | Generates a personalized name card. |
| `.oogway <quote>` / `.oogway2` | Generates a Master Oogway wisdom-quote image. |
| `.tweet <name|handle|comment|theme>` | Generates a fake tweet screenshot. |
| `.ytcomment <username|comment>` | Generates a fake YouTube comment screenshot. |
| `.comrade`, `.gay`, `.glass`, `.jail`, `.passed`, `.triggered` | Various avatar overlay filters/effects. |

---

## 🖼️ Anime Reaction Commands

| Command | Description |
|---|---|
| `.nom`, `.poke`, `.cry`, `.kiss`, `.pat`, `.hug`, `.wink`, `.facepalm` | Sends an anime reaction GIF/sticker for the given action. |
| `.animu <type>` | General command to fetch any supported anime reaction type. |
| `.animuquote` / `.quote` (anime) | Sends a random anime quote. |

---

## 🥧 Pies (Regional Meme Images)

| Command | Description |
|---|---|
| `.pies <country>` | Fetches a themed meme image for a supported country. |
| `.china`, `.indonesia`, `.japan`, `.korea`, `.india`, `.malaysia`, `.thailand` | Quick-access shortcuts for each country's pies command. |

---

## 💻 GitHub / Repo Commands

| Command | Description |
|---|---|
| `.git` / `.github` / `.sc` / `.script` / `.repo` | Shows the bot's GitHub repository stats (stars, forks, size, last update). |

---

## 🫸 Pain (Nagato) Exclusive Commands

A full Akatsuki-themed command set dedicated to Pain/Nagato from Naruto.

| Command | Description |
|---|---|
| `.pain` | Sends Pain's signature line *"Ore wa Pain"* and self-reacts with 🫸. |
| `.about` | Sends a full in-character bio of Pain — who he is, his goal of "shared pain," the Rinnegan, and each of his 6 bodies' unique abilities. |
| `.intro` | Plays Pain's intro video. |
| `.theme` | Streams Pain's theme song. |
| `.themealt` | Plays an alternate version of the theme song. |
| `.almpush` | Plays the *Almighty Push* sound effect. |
| `.uvpull` | Plays the *Universal Pull* sound effect. |
| `.uvpull-jp` | Plays the Japanese-named *Bansho Ten'in* (Universal Pull) sound effect. |
| `.shinra` | Plays the *Shinra Tensei* sound effect. |
| `.chibaku` | Plays the *Chibaku Tensei* sound effect. |
| `.greater` | Plays the *Greater Pain* audio clip. |

---

## 🛠️ Setup & Installation

### Prerequisites
- Node.js **v18+**
- Git
- `ffmpeg` installed and available in your system PATH (required for stickers/audio/video conversion)

### Steps

```bash
# 1. Clone the repository
git clone https://github.com/ahsanhabibmuaz/pain-bot-2.git
cd pain-bot-2

# 2. Install dependencies
npm install

# 3. Configure the bot
# Edit settings.js to set your ownerNumber, bot name, and other options

# 4. Run the bot
node index.js
```

On first run, scan the QR code (or use pairing code mode) with **Linked Devices** in WhatsApp to connect your account.

### Useful npm scripts

| Script | Purpose |
|---|---|
| `npm start` | Starts the bot normally. |
| `npm run start:optimized` | Starts with memory-optimized Node flags. |
| `npm run cleanup` | Cleans up temp/session clutter. |
| `npm run reset-session` | Wipes the current session for a fresh login. |
| `npm run start:clean` | Cleanup + optimized start. |
| `npm run start:fresh` | Fresh session + normal start. |

---

## ⚠️ Disclaimer

This bot is created for **educational purposes only**. It is **not** an official WhatsApp product. Using automated/unofficial clients can result in your WhatsApp account being banned — use at your own risk. The developers assume no liability for misuse, spam, or account restrictions.

- Not affiliated with, authorized, maintained, sponsored, or endorsed by WhatsApp.
- Do not use this bot to spam or send unsolicited bulk messages.
- Use in compliance with all applicable laws.

---

## 📄 License

Licensed under the [MIT License](https://opensource.org/licenses/MIT). You must retain original license/copyright notices, credit original authors, and not use the project for spam or malicious purposes.

---

## 🙌 Credits

- [Baileys](https://github.com/WhiskeySockets/Baileys) — WhatsApp Web API library
- Coded & maintained by **Muaz**
- Pairing code implementation inspired by TechGod143 & Dgxeon

---

## ☕ Support

<div align="center">
<a href="https://buymeacoffee.com/ahsanhabibmuaz" target="_blank">
  <img src="https://img.shields.io/badge/Buy%20Me%20a%20Coffee-Support%20Developer-FF813F?style=for-the-badge&logo=buy-me-a-coffee&logoColor=white" alt="Buy Me a Coffee">
</a>
</div>

> Made with ♥ from Bangladesh — *Feel Pain, Accept Pain, Know Pain* 🫸
