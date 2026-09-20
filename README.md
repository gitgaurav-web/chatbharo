# 💬 Modern Realtime Chat Room

[![Live Demo](https://img.shields.io/badge/Live_Demo-Blogspot-ff5722?style=for-the-badge&logo=blogger&logoColor=white)](https://realtimexyz.blogspot.com/)
[![GitHub](https://img.shields.io/badge/GitHub-gitgaurav--web-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/gitgaurav-web/realtime-chat)
[![Firebase](https://img.shields.io/badge/Firebase-Realtime_Database-FFA611?style=for-the-badge&logo=firebase&logoColor=white)](https://firebase.google.com/)
[![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)](https://developer.mozilla.org/)
[![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)](https://developer.mozilla.org/)
[![JavaScript](https://img.shields.io/badge/JavaScript-ES_Modules-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)](https://developer.mozilla.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg?style=for-the-badge)](LICENSE)

A modern, fast, and feature-packed **Realtime Chat Web Application** built with pure Vanilla HTML5, CSS3, JavaScript (ES Modules), and **Firebase Realtime Database**. Designed mobile-first with an elegant dark mode UI.

🌐 **Live Demo on Blogspot:** [https://realtimexyz.blogspot.com/](https://realtimexyz.blogspot.com/)

---

## ✨ Features

### 🎙️ Voice Notes (Audio Messaging)
- **Built-in Audio Recorder:** Record audio notes directly from the browser with live recording timer (`0:05`), pulsing red indicator, and cancel/send controls.
- **Custom Audio Player Bubble:** Sleek embedded player with Play/Pause, dynamic waveform track progress, and timestamp duration.

### ❤️ Message Emoji Reactions
- **Quick Reaction Bar:** Instant emoji reaction row (`❤️`, `👍`, `😂`, `🔥`, `😮`, `😢`) via message context menu.
- **Live Reaction Badges:** Reaction counters rendered directly below message bubbles (`[❤️ 2]`, `[🔥 1]`).
- **Interactive Toggle:** Click any badge to toggle your reaction in real time across the room.

### 👥 Live Presence & Active Users Modal
- **"Who is Online" Bottom-Sheet:** Click `🟢 Active: X` in the header to view a complete list of online members with avatars and `(You)` indicator.
- **Auto-Cleanup on Disconnect:** Uses Firebase `onDisconnect()` to remove inactive members automatically.
- **Live Typing Broadcast:** Live `User is typing...` indicator with auto-debounced timeout.

### 📶 Real-time Connection State & Offline Banner
- Listens to Firebase `.info/connected` status.
- Shows an animated warning banner (`⚠️ Connection lost. Reconnecting to server...`) if internet drops, and hides it upon reconnection.

### 🔗 1-Click Share & Smart Linkify
- **Room Share Button:** Click `🔗 Share` in the header to copy `https://realtimexyz.blogspot.com/?room=XYZ` or trigger native mobile share sheets.
- **Auto-Fill Room URL:** Visiting a link with `?room=XYZ` automatically pre-fills the room code.
- **Auto-Linkify URLs:** Converts links in chat messages into secure, clickable links (`target="_blank" rel="noopener noreferrer"`).

### 🔔 Sweet Notification Chime
- In-browser synthesized audio chime (Web Audio API) for incoming messages.
- Header toggle button (`🔔` / `🔕`) to mute/unmute audio notifications anytime.

### 💬 WhatsApp-Style Reply & Gestures
- **Swipe-to-Reply:** Touch swipe right gesture on mobile to quickly quote and reply to any message.
- **Double-Click to Reply:** Quick double-click shortcut on desktop and touch devices.
- **Interactive Quoted Messages:** Clicking a quoted reply smoothly scrolls to the original message with a purple pulse highlight.

### 📷 Client-Side Image Compression & Multi-Upload
- **HTML5 Canvas Compression:** Images are compressed on the client side (max 1280x720, 70% JPEG quality) before uploading to conserve bandwidth.
- **Multi-File Preview Bar:** Select multiple photos with thumbnail previews and a single-tap clear button.

### ⌨️ Dynamic Auto-Resizing Input & Smart Scroll
- **Auto-Expanding Textarea:** Typing box smoothly expands up to 130px for multi-line messages and automatically resets to 1 line on send.
- **Floating Scroll-to-Bottom Button:** Appears automatically when scrolled up.
- **Unread Badge Counter:** Displays the number of unread incoming messages when viewing earlier chat history.

### 📜 "Load Older Messages" Pagination
- Loads the latest 50 messages initially to ensure blazing-fast load times and zero lag.
- A `📜 Load Older Messages` button allows users to fetch earlier history on demand without losing scroll position.

### 🛡️ Built-in XSS Security Sanitization
- Complete HTML escaping (`&`, `<`, `>`, `"`, `'`) for all usernames, message contents, reply targets, and author names to prevent Stored XSS attacks.

### 😀 Integrated Searchable Emoji Picker
- Built-in library of 100+ categorized emojis with keyword tag search filter.

---

## 🛠️ Tech Stack

| Component | Technology |
| :--- | :--- |
| **Frontend UI** | HTML5, CSS3 (Mobile-first, Flexbox, CSS Grid, Glassmorphism) |
| **Client Scripting** | Vanilla JavaScript (ES Modules, MediaRecorder API, Web Audio API, Canvas API) |
| **Backend / Database** | Firebase Realtime Database (v12.6.0 Modular SDK) |
| **Icons & Design** | Inline SVG & Unicode Emojis |

---

## 📁 Project Structure

```text
realtim/
├── index.html       # Primary entry point (compatible with GitHub Pages)
├── realtime.html    # Standalone single-file version (ideal for Blogger/custom hosting)
├── .gitignore       # Git ignore rules for system/scratch files
└── README.md        # Complete documentation and setup guide
```

---

## 🚀 Quick Start & Local Setup

### 1. Clone the Repository
```bash
git clone https://github.com/gitgaurav-web/realtime-chat.git
cd realtime-chat
```

### 2. Run Locally
No build step or `npm install` is required!
- Simply double-click `index.html` to open it in any modern web browser.
- Or use VS Code **Live Server** / Python HTTP server:
  ```bash
  python -m http.server 8000
  ```
  Then visit `http://localhost:8000` in your browser.

---

## ⚙️ Firebase Configuration

The application connects to Firebase Realtime Database. You can replace the default credentials in `index.html` (lines 894-902) with your own Firebase project credentials:

```javascript
const firebaseConfig = {
    apiKey: "YOUR_API_KEY",
    authDomain: "YOUR_PROJECT_ID.firebaseapp.com",
    databaseURL: "https://YOUR_PROJECT_ID-default-rtdb.firebaseio.com",
    projectId: "YOUR_PROJECT_ID",
    storageBucket: "YOUR_PROJECT_ID.firebasestorage.app",
    messagingSenderId: "YOUR_MESSAGING_SENDER_ID",
    appId: "YOUR_APP_ID"
};
```

### Recommended Firebase Security Rules
In your Firebase Console under **Realtime Database > Rules**, configure:

```json
{
  "rules": {
    "rooms": {
      "$roomCode": {
        ".read": true,
        ".write": true
      }
    }
  }
}
```

---

## 🌐 Deployment

### Option 1: Blogger / Blogspot (Current Live Method)
1. Open your **Blogger Dashboard** ([blogger.com](https://www.blogger.com)).
2. Navigate to **Theme > Edit HTML**.
3. Replace all existing template code with the contents of `realtime.html`.
4. Click **Save (💾)**. Your chat room will be live at your `.blogspot.com` address over HTTPS!

### Option 2: GitHub Pages (Free 1-Click Hosting)
1. In your GitHub repository [gitgaurav-web/realtime-chat](https://github.com/gitgaurav-web/realtime-chat), navigate to **Settings > Pages**.
2. Under **Branch**, select `main` and folder `/ (root)`.
3. Click **Save**. Your site will be live at `https://gitgaurav-web.github.io/realtime-chat/`.

---

## 📄 License
Distributed under the MIT License.

---

*Made with ❤️ by [Gaurav Kumar](https://github.com/gitgaurav-web)*
