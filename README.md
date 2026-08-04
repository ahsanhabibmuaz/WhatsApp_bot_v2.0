<h2 align="center">PAIN BOT</h2>
<div align="center">
<!-- Animated Dynamic Typing Banner -->
<a href="https://drift.rip/muaz">
  <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=22&pause=1000&color=FF0055&center=true&vCenter=true&width=600&lines=Automated+WhatsApp+Bot;High-Performance+Group+Moderation;Encrypted+Session+Handling;Pain+Themed+WhatsApp+Bot;Developed+by+Muaz" alt="Typing SVG" />
</a>


<!-- Main Bot Banner Image -->
<a href="https://drift.rip/muaz"> 
  <img src="https://i.postimg.cc/rFn9X6CL/bot-image.jpg" alt="Pain Bot" height="300" style="border-radius: 14px; box-shadow: 0 0 20px rgba(255, 0, 85, 0.4);"> 
</a>
<br><br>

</div>
<br>

> [!CAUTION]
> 🔒 **This repository is now private.**  
> Due to security reasons, protecting API credentials, and ensuring project integrity, **Pain-Bot v2.0** is no longer maintained in a public repository. Source code access and active updates are restricted to authorized maintainers.


---

### 🔒 Why is this Repository Private?

* 🛡️ **Security & Confidentiality:** Core moderation scripts, administrative triggers, and backend mechanics are hidden to prevent security risks.
* 🗝️ **Credential & Token Protection:** Guarantees no exposure of session files, auth tokens, or private API keys.
* 🚫 **Anti-Cloning & Unauthorized Distribution:** Prevents outdated, unverified, or malicious public forks from circulating.

---

### 🚀 Key Features:

* ⚡ **Ultra-Fast Execution:** Optimized session handling with minimal latency.
* 🛡️ **Automated Moderation:** Smart keyword filtering, anti-spam mechanisms, and admin commands.
* 🛠️ **Utility & Media Engine:** Built-in sticker conversion, media downloaders, and custom auto-replies.
* 🔐 **Encrypted Session Guard:** Isolated environment configs for continuous, secure execution.
* 🤖 **AI-Powered Chat:** GPT & Gemini integration plus an always-on group chatbot mode.
* 🫸 **"Pain" Theme Pack:** A full set of Akatsuki-exclusive audio & lore commands.
* 🎮 **Built-In Mini-Games:** Tic-Tac-Toe, Hangman, Trivia, Truth or Dare.
* 🎨 **Sticker & Image Lab:** Text-effect generators, background removal, AI upscaling, and more.

---
### 📜 Full Command Reference:
<div align="center">

</div>

<details>
<summary><b>⚙️ Core Systems</b> — how the bot works</summary>
<br>

- **Dynamic Prefix** — the bot reads its command prefix from `data/prefix.json` on every message, so `.setprefix` (or hand-editing the file) takes effect instantly without a restart.
- **Public / Private Mode** — `.mode public` lets everyone use the bot; `.mode private` restricts commands to the owner/sudo only (moderation like antilink/antibadword/antitag still runs in groups either way).
- **Owner & Sudo System** — the bot owner and any number of sudo users (`.sudo add/del/list`) get elevated access to owner-only commands and moderation overrides, independent of WhatsApp group admin status.
- **Ban System** — `.ban` / `.unban` block a user from using *any* bot command. This is a bot-level restriction, so it works for the owner/sudo even without the bot being a group admin. Banned users get a silent 🚫 reaction per attempt, with an occasional reminder text every ~10–12 tries.
- **Exact Command Matching** — commands are matched precisely (e.g. `.bansho` will never accidentally trigger `.ban`).
- **Lightweight Message Store** — keeps a rolling window of recent messages per chat for `.delete`, antidelete, and quoting.
- **Auto Temp Cleanup** — temp/session files are periodically purged to avoid disk/RAM bloat on hosted panels.

</details>

<details>
<summary><b>🌐 General Commands</b></summary>
<br>

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
| `.settings` | Shows the current status of every toggleable feature — owner only. |

</details>

<details>
<summary><b>👮 Group Admin Commands</b></summary>
<br>

*Require the sender to be a group admin, or the bot owner/sudo. The bot itself must be a group admin for most of these.*

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
| `.warn @user` | Issues a warning to a user; auto-kicks after 3 warnings. |
| `.warnings @user` | Checks how many warnings a user has. |
| `.tag <message>` | Sends a message/media that tags every group member individually. |
| `.tagall` | Tags every group member in a single message. |
| `.tagnotadmin` | Tags only the non-admin members. |
| `.hidetag <message>` | Sends a message that mentions everyone without visibly listing their names. |
| `.antilink on/off/set` | Auto-deletes (or kicks/warns for) messages containing links. |
| `.antibadword on/off/set` | Filters profanity/slurs using obfuscation-resistant detection and deletes/kicks/warns offenders. |
| `.antitag on/off/set` | Detects and blocks mass-tagging spam (tagall abuse) with delete/kick actions. |
| `.chatbot on/off` | Enables an AI chatbot that responds when the bot is mentioned or replied to in the group. |
| `.welcome on/off/set` | Sends a custom welcome image/message to new members. |
| `.goodbye on/off/set` | Sends a custom goodbye message when members leave. |
| `.resetlink` / `.revoke` | Resets the group's invite link. |
| `.setgdesc <text>` | Updates the group description. |
| `.setgname <text>` | Updates the group name. |
| `.setgpp` | Updates the group profile picture (reply to an image). |
| `.clear` | Clears the bot's own recent message in the chat. |

</details>

<details>
<summary><b>🔒 Owner-Only Commands</b></summary>
<br>

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

</details>

<details>
<summary><b>🎨 Image & Sticker Commands</b></summary>
<br>

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
| `.metallic`, `.ice`, `.snow`, `.impressive`, `.matrix`, `.light`, `.neon`, `.devil`, `.purple`, `.thunder`, `.leaves`, `.1917`, `.arena`, `.hacker`, `.sand`, `.blackpink`, `.glitch`, `.fire` `<text>` | 17 stylized text-effect image generators. |

</details>

<details>
<summary><b>📥 Media Downloaders</b></summary>
<br>

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

</details>

<details>
<summary><b>🎮 Game Commands</b></summary>
<br>

| Command | Description |
|---|---|
| `.tictactoe` / `.ttt [room name]` | Starts or joins a Tic-Tac-Toe match; play by typing numbers 1–9. |
| `.hangman` | Starts a game of Hangman. |
| `.guess <letter>` | Guesses a letter in the active Hangman game. |
| `.trivia` | Starts a random trivia question. |
| `.answer <answer>` | Submits an answer to the active trivia question. |
| `.truth` | Sends a random Truth prompt. |
| `.dare` | Sends a random Dare prompt. |

</details>

<details>
<summary><b>🤖 AI Commands</b></summary>
<br>

| Command | Description |
|---|---|
| `.gpt <question>` | Asks a question to a ChatGPT-style AI. |
| `.gemini <question>` | Asks a question to Google's Gemini AI. |
| `.chatbot on/off` | Enables free-flowing AI conversation when the bot is mentioned/replied to (group admin command). |

</details>

<details>
<summary><b>🎯 Fun & Social Commands</b></summary>
<br>

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

</details>

<details>
<summary><b>🧩 Misc Canvas Commands</b></summary>
<br>

| Command | Description |
|---|---|
| `.heart` | Generates a heart-frame avatar image. |
| `.horny` | Generates a "horny" badge overlay. |
| `.circle` | Crops your/replied avatar into a circle. |
| `.lgbt` | Adds a pride-flag overlay to an avatar. |
| `.lolice` | Generates a "lolice" badge overlay. |
| `.namecard <username\|birthday\|desc>` | Generates a personalized name card. |
| `.oogway <quote>` / `.oogway2` | Generates a Master Oogway wisdom-quote image. |
| `.tweet <name\|handle\|comment\|theme>` | Generates a fake tweet screenshot. |
| `.ytcomment <username\|comment>` | Generates a fake YouTube comment screenshot. |
| `.comrade`, `.gay`, `.glass`, `.jail`, `.passed`, `.triggered` | Various avatar overlay filters/effects. |

</details>

<details>
<summary><b>🖼️ Anime Reaction Commands</b></summary>
<br>

| Command | Description |
|---|---|
| `.nom`, `.poke`, `.cry`, `.kiss`, `.pat`, `.hug`, `.wink`, `.facepalm` | Sends an anime reaction GIF/sticker for the given action. |
| `.animu <type>` | General command to fetch any supported anime reaction type. |
| `.animuquote` / `.quote` (anime) | Sends a random anime quote. |

</details>

<details>
<summary><b>🥧 Pies (Regional Meme Images)</b></summary>
<br>

| Command | Description |
|---|---|
| `.pies <country>` | Fetches a themed meme image for a supported country. |
| `.china`, `.indonesia`, `.japan`, `.korea`, `.india`, `.malaysia`, `.thailand` | Quick-access shortcuts for each country's pies command. |

</details>

<details>
<summary><b>💻 GitHub / Repo Commands</b></summary>
<br>

| Command | Description |
|---|---|
| `.git` / `.github` / `.sc` / `.script` / `.repo` | Shows the bot's GitHub repository stats (stars, forks, size, last update). |

</details>

<details>
<summary><b>🫸 Pain Exclusive Commands</b></summary>
<br>

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

</details>

- - -
  
### ⚠️ Disclaimer

This bot is created for **educational purposes only**. It is **not** an official WhatsApp product. Using automated/unofficial clients can result in your WhatsApp account being banned — use at your own risk. The developers assume no liability for misuse, spam, or account restrictions.

---

### 👤 Developer(s):

- **Muaz** (Dev)
- **Sonali** (Bug Tester)


<div align="center">

[![GitHub Profile](https://img.shields.io/badge/GitHub-@ahsanhabibmuaz-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/ahsanhabibmuaz)

</div>

<div align="center">
  <img src="https://raw.githubusercontent.com/Platane/snk/output/github-contribution-grid-snake.svg" alt="GitHub Contribution Grid Snake" width="100%" />
</div>

<div align="center">
  <sub>© Pain-Bot Project. All rights reserved.</sub>
</div>
