<p align="center">
  <img src="./assets/logo.png" alt="ChatBharo Logo" width="160" />
</p>

# 💬 ChatBharo - Modern Realtime Chat Web Application

[![Live Demo](https://img.shields.io/badge/Live_Demo-Blogspot-ff5722?style=for-the-badge&logo=blogger&logoColor=white)](https://chatbharo.blogspot.com/)
[![GitHub](https://img.shields.io/badge/GitHub-gitgaurav--web-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/gitgaurav-web/realtime-chat)
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

### 📎 20MB Multi-Format Document & File Sharing
- **Paperclip Attachment (`📎`):** Supports all popular formats:
  - **Documents:** `.pdf`, `.doc`, `.docx`, `.txt`, `.md`
  - **Spreadsheets:** `.xls`, `.xlsx`, `.csv`
  - **Presentations:** `.ppt`, `.pptx`
  - **Archives:** `.zip`, `.rar`, `.7z`, `.tar`, `.gz`
  - **Code:** `.json`, `.js`, `.py`, `.html`, `.css`
- **Sleek In-Chat File Card:** Displays format-specific icons (`📄 📑 📊 📽️ 📦 📝`), original filename, formatted size, and local download button.

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
├── index.html       # Primary entry point (compatible with GitHub Pages)
├── realtime.html    # Standalone single-file version (ideal for Blogger Theme HTML)
├── .gitignore       # Git ignore rules for system/scratch files
└── README.md        # Complete documentation and setup guide
```

---

## 📋 Blogger Deployment Guide

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
