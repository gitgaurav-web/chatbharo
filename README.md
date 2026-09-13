# 💬 Modern Realtime Chat Room

[![Live Demo](https://img.shields.io/badge/Live_Demo-Blogspot-ff5722?style=for-the-badge&logo=blogger&logoColor=white)](https://realtimexyz.blogspot.com/)
[![Firebase](https://img.shields.io/badge/Firebase-Realtime_Database-FFA611?style=for-the-badge&logo=firebase&logoColor=white)](https://firebase.google.com/)
[![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)](https://developer.mozilla.org/)
[![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)](https://developer.mozilla.org/)
[![JavaScript](https://img.shields.io/badge/JavaScript-ES_Modules-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)](https://developer.mozilla.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg?style=for-the-badge)](LICENSE)

A modern, fast, and feature-packed **Realtime Chat Web Application** built with pure Vanilla HTML5, CSS3, JavaScript (ES Modules), and **Firebase Realtime Database**. Designed mobile-first with an elegant dark mode UI.

🌐 **Live Demo:** [https://realtimexyz.blogspot.com/](https://realtimexyz.blogspot.com/)

---

## ✨ Features

### ⚡ Realtime Messaging & Room System
- **Custom or Random Room Codes:** Create a new room with a custom code or generate a random 6-character room key.
- **Instant Messaging:** Push and receive text messages instantly via Firebase Realtime Database (`onChildAdded`, `onChildChanged`).
- **Soft Message Deletion:** Message owners can delete their messages, replacing the bubble with a deletion notice (`🚫 You deleted this message`).

### 🛡️ Security & Performance
- **Stored XSS Prevention:** Complete HTML escaping (`&`, `<`, `>`, `"`, `'`) for all usernames, message contents, reply targets, and author names.
- **Optimized Initial Load (`limitToLast(50)`):** Only the latest 50 messages load on entering a room, preventing device memory spikes and app freezing in large chat histories.
- **Safe DOM Image Viewer:** Opens images in a separate view without insecure `document.write`.

### 👥 Live Presence & Typing Indicators
- **Active Member Counter:** Realtime count of active participants in each room with automatic cleanup on disconnection (`onDisconnect`).
- **Typing Status Broadcast:** Live `User is typing...` indicator with auto-debounced timeout.

### 💬 WhatsApp-Style Reply & Gestures
- **Swipe-to-Reply:** Touch swipe right gesture on mobile to quickly quote and reply to any message.
- **Double-Click to Reply:** Quick double-click shortcut on desktop and touch devices.
- **Interactive Quoted Messages:** Clicking on a quoted reply smoothly scrolls directly to the original message and highlights it with a purple pulse animation.

### 📷 Client-Side Image Compression & Multi-Upload
- **HTML5 Canvas Compression:** Images are compressed on the client side (max 1280x720, 70% JPEG quality) before uploading to conserve bandwidth.
- **Multi-File Preview Bar:** Select multiple photos with thumbnail previews and a single-tap clear button.

### ⌨️ Dynamic Auto-Resizing Input & Smart Scroll
- **Auto-Expanding Textarea:** Typing box smoothly expands up to 130px for multi-line messages and automatically resets to 1 line on send.
- **Floating Scroll-to-Bottom Button:** Appears automatically when scrolled up.
- **Unread Badge Counter:** Displays the number of unread incoming messages when viewing earlier chat history.

### 😀 Integrated Searchable Emoji Picker
- Built-in library of 100+ categorized emojis.
- Realtime search filter by keywords and tags (e.g., *happy*, *love*, *fire*, *party*).

---

## 🛠️ Tech Stack

| Component | Technology |
| :--- | :--- |
| **Frontend UI** | HTML5, CSS3 (Mobile-first, Flexbox, CSS Grid) |
| **Client Scripting** | Vanilla JavaScript (ES Modules, Canvas API, Touch API) |
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
git clone https://github.com/YOUR_USERNAME/YOUR_REPOSITORY_NAME.git
cd YOUR_REPOSITORY_NAME
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
1. Push this repository to GitHub.
2. In your repository, navigate to **Settings > Pages**.
3. Under **Branch**, select `main` and folder `/ (root)`.
4. Click **Save**. Your site will be live at `https://YOUR_USERNAME.github.io/YOUR_REPOSITORY_NAME/`.

---

## 🤝 Contributing
Contributions, suggestions, and feature requests are welcome!
1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

## 📄 License
Distributed under the MIT License.

---

*Made with ❤️ by [Gaurav Kumar](https://github.com/)*
