<p align="center">
  <img src="./assets/logo.png" alt="ChatBharo Logo" width="160" />
</p>

# 💬 ChatBharo - Modern Realtime Chat Web Application

[![Live Demo](https://img.shields.io/badge/Live_Demo-Blogspot-ff5722?style=for-the-badge&logo=blogger&logoColor=white)](https://chatbharo.blogspot.com/)
[![GitHub](https://img.shields.io/badge/GitHub-gitgaurav--web-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/gitgaurav-web/chatbharo)
[![Firebase](https://img.shields.io/badge/Firebase-Realtime_Database-FFA611?style=for-the-badge&logo=firebase&logoColor=white)](https://firebase.google.com/)
[![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)](https://developer.mozilla.org/)
[![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)](https://developer.mozilla.org/)
[![JavaScript](https://img.shields.io/badge/JavaScript-ES_Modules-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)](https://developer.mozilla.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg?style=for-the-badge)](LICENSE)

A high-performance, mobile-first **Realtime Chat Web Application** engineered with pure Vanilla HTML5, CSS3, JavaScript (ES Modules), and **Firebase Realtime Database**. Designed from the ground up for zero-dependency integration, silky 60/120fps UI smoothness, and seamless Blogger / GitHub Pages hosting.

🌐 **Live Demo on Blogspot:** [https://chatbharo.blogspot.com/](https://chatbharo.blogspot.com/)

---

## 🚀 Key Features & Highlights

### 📷 High-Definition (HD) Image Pipeline & Lightbox Viewer
- **Instant Client-Side HD Canvas Compression:** Compresses images to **1600 × 1600 px at 0.82 JPEG quality** directly on an in-memory Canvas. Reduces file size to **~150KB - 250KB** with crystal-clear sharpness, uploading in **< 200 ms** over Firebase Realtime Database.
- **In-Chat Fullscreen Lightbox Modal:** Tapping any photo opens a sleek dark glassmorphic viewer with original image name and an instant **⬇ Download HD** button (100% immune to mobile popup blockers).
- **⌨️ Send Photos with Enter (`↵`):** Selecting photos auto-focuses the message input and shows an interactive shortcut hint (`• Press Enter ↵ to Send`). Pressing Enter anywhere sends selected photos instantly!

### 📎 Universal Any-File & Folder Sharing (Up to 50MB)
- **Paperclip Attachment Menu (📎):** Tapping the paperclip opens a sleek action menu:
  - **📄 Send Files:** Supports **ANY file format up to 50MB**:
    - **Documents & Text:** .pdf, .doc, .docx, .xls, .xlsx, .ppt, .pptx, .txt, .csv, .md, .rtf, .odt
    - **Media:** Videos (.mp4, .mkv, .avi, .mov, .webm), Audio (.mp3, .wav, .m4a, .aac, .flac, .ogg), Images (.png, .jpg, .webp, .svg, .psd)
    - **Mobile Apps & Software:** .apk, .xapk, .exe, .msi, .dmg, .pkg, .deb
    - **Archives:** .zip, .rar, .7z, .tar, .gz, .iso
    - **Code & Scripts:** .py, .java, .cpp, .js, .ts, .html, .css, .json, .xml, .sql, .sh
    - **Any custom binary/data file**
  - **📁 Send Full Folder:** Select any folder on desktop or mobile — ChatBharo automatically packages all files and subdirectories client-side into a `.zip` archive (using JSZip) with live compression progress (`📦 45%`) and sends it up to 50MB!
- **🖱️ Drag & Drop Folders & Files:** On desktop, simply drag and drop folders or files directly onto the chat window to package and send instantly.
- **Dynamic File Type Icons & Folder Badge:** Automatically displays dedicated icons (📄 📑 📊 📽️ 🎵 🎬 🖼️ 📦 💻 📱 ⚙️ 🔤 📁), folder file counter badge (`FOLDER (24 files)`), and 1-tap local download button.
- **Multi-File Selection:** Select and send multiple files at once with live upload progress.

### 🔒 10-Day Auto-Delete & TTL Lifecycle (Room & Data Auto-Deletion)
- **Strict 10-Day Privacy TTL (`864,000,000 ms`):** Both chat rooms and all message data (text, HD photos, voice notes, files) are automatically destroyed after 10 days without requiring manual maintenance.
- **Header TTL Badge:** Live countdown indicator (`• ⏳ 10d left`) displayed in the room header so users always know the remaining room lifetime.
- **Auto-Pruning on Entry & In-Chat Watchdog:** Expired rooms are purged immediately upon creation, joining, or background sweeps. Messages older than 10 days are automatically deleted from Firebase Realtime Database.
- **Auto-Privacy Notice:** Clear privacy disclosure banner displayed on the login page informing users that all data auto-deletes every 10 days.

### ⏱️ WhatsApp-Style Message Status Ticks (Sent, Delivered, Seen)
- **🕒 Clock Icon (Sending):** Displayed beside the message timestamp while text, voice notes, or large 50MB files/folders are uploading.
- **✓ Single Grey Tick (Sent):** Confirms the message has successfully reached Firebase Realtime Database.
- **✓✓ Double Grey Tick (Delivered):** Confirms the message has reached other members in the room.
- **✓✓ Double Blue Tick (Seen / Read):** WhatsApp signature cyan/blue tick (`#53bdeb`) automatically turns on when other participants view the chat!

### 🎙️ High-Fidelity Voice Notes (MediaRecorder API)
- **Built-in Audio Recorder:** One-tap voice recording with live duration timer (`0:05`), pulsing red indicator, and cancel/send controls.
- **Custom Embedded Audio Player:** Features Play/Pause button, real-time waveform progress bar, and formatted duration labels.
- **Memory-Safe Teardown:** All microphone tracks and buffers are immediately released upon send or cancel.

### ❤️ Realtime Emoji Reactions
- **Quick Reaction Bar:** Instant emoji reaction row (`❤️`, `👍`, `😂`, `🔥`, `😮`, `😢`) via message context menu.
- **Live Reaction Badges:** Reaction counters rendered directly below message bubbles (`[❤️ 2]`, `[🔥 1]`).
- **Interactive Toggle:** Click any badge to toggle your reaction in real time across the room.

### 👥 Live Presence & Active Users Modal
- **"Who is Online" Bottom-Sheet:** Click `🟢 Active: X` in the header to view a complete list of online members with avatars and `(You)` indicator.
- **Auto-Cleanup on Disconnect:** Uses Firebase `onDisconnect()` to remove inactive members automatically.
- **Live Typing Broadcast:** Live `User is typing...` indicator with auto-debounced timeout.

### 🔔 Modern Floating Toast Notifications (No Harsh Alerts)
- Replaced intrusive browser `alert()` popups with an elegant, non-blocking **Glassmorphic Floating Toast (`#toastBox`)**.
- Animated slide-in and auto-fade for copy confirmation, deletions, and validation warnings.

### 📱 Scroll-Safe Touch Gesture Engine
- **Gesture Conflict Resolution:** Swipe-to-reply dynamically detects vertical scrolling vs. horizontal swipes. Vertical chat scrolling stays buttery smooth (60/120fps) without accidentally triggering swipes.
- **Touch-Move Context Cancel:** Long-press timer auto-cancels upon touch movement, preventing accidental menu popups during scrolling.

### 🔊 Hardware-Efficient Audio Chime
- Uses a single shared **AudioContext** to synthesize notification chimes on incoming messages.
- Prevents browser AudioContext limit crashes and eliminates audio playback latency.
- Header toggle button (`🔔` / `🔕`) to mute/unmute audio notifications anytime.

### 📶 Network Reconnection & Presence Restoration
- Listens to Firebase `.info/connected` status.
- Shows an animated warning banner (`⚠️ Connection lost. Reconnecting to server...`) if internet drops, and automatically restores online presence (`activeRef`) upon reconnection.

### 🔗 1-Click Room Sharing & Auto-URL Join
- **Room Share Button:** Click `🔗 Share` in the header to copy `https://chatbharo.blogspot.com/?room=XYZ` or trigger native mobile share sheets.
- **Auto-Fill Room URL:** Visiting a link with `?room=XYZ` automatically pre-fills the room code.
- **Auto-Linkify URLs:** Converts links in chat messages into secure, clickable links (`target="_blank" rel="noopener noreferrer"`).

### 📜 "Load Older Messages" Pagination
- Loads the latest 50 messages initially to ensure blazing-fast load times and zero lag.
- A `📜 Load Older Messages` button allows users to fetch earlier history on demand without losing scroll position.

### 🛡️ Built-in XSS Security Sanitization
- Complete HTML escaping (`&`, `<`, `>`, `"`, `'`) for all usernames, message contents, reply targets, and author names to prevent Stored XSS attacks.

### 😀 Integrated Searchable Emoji Picker
- Built-in library of 100+ categorized emojis with keyword tag search filter.

---

## 🛠️ Tech Stack & Architecture

| Component | Technology |
| :--- | :--- |
| **Frontend UI** | Pure HTML5 & CSS3 (Mobile-first, Flexbox, CSS Grid, Glassmorphism) |
| **Performance** | GPU Hardware Acceleration (`will-change`, `contain: content`) |
| **Client Scripting** | Vanilla JavaScript (ES Modules, MediaRecorder API, Web Audio API, Canvas API) |
| **Backend / Database** | Firebase Realtime Database (v12.6.0 Modular SDK) |
| **Deployment** | Single-file architecture compatible with Blogger Theme HTML and GitHub Pages |

---

## 📁 Project Structure

```text
realtim/
├── index.html            # Primary entry point (compatible with GitHub Pages)
├── realtime.html         # Standalone single-file HTML version
├── ChatBharo-Theme.xml   # Official 1-click Blogger XML Theme (mobile responsive, no ?m=1 bugs)
├── .gitignore            # Git ignore rules for system/scratch files
└── README.md             # Complete documentation and setup guide
```

---

## 📋 Blogger Deployment Guide

### Method 1: 1-Click Theme Restore (Recommended)
1. Download or locate `ChatBharo-Theme.xml`.
2. Go to your **Blogger Dashboard** -> **Theme**.
3. Click the dropdown arrow next to **Customize** -> Select **Restore**.
4. Choose `ChatBharo-Theme.xml` and click **Upload**.
5. Done! Your blog will now load ChatBharo cleanly on both desktop and mobile (`?m=1` redirection bypass).

### Method 2: Manual Edit HTML
1. Open `realtime.html` and copy the entire file contents (`Ctrl + A`, `Ctrl + C`).
2. Go to your **Blogger Dashboard** -> **Theme** -> Click the three dots next to **Customize** -> **Edit HTML**.
3. Select everything in the editor and replace it with your copied code.
4. Click **Save** (💾 icon) in the top right corner.
5. Visit your blog URL (e.g. `https://chatbharo.blogspot.com/`) to chat!

---

## 👨‍💻 Author

**Gaurav Kumar**
- GitHub: [@gitgaurav-web](https://github.com/gitgaurav-web)
- Live Project: [Modern Chat Rooms on Blogspot](https://chatbharo.blogspot.com/)

---

## 📄 License

This project is licensed under the [MIT License](LICENSE).
