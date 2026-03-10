# 💬 Messenger App

A real-time 2-person chat app built with Node.js, Express, and Socket.io.

---

## 📁 File Structure

```
messenger/
├── server.js          ← Node.js backend
├── package.json       ← Dependencies
├── README.md
└── public/
    └── index.html     ← Frontend (auto-served)
```

---

## 🚀 Run Locally

### 1. Install dependencies
```bash
npm install
```

### 2. Start the server
```bash
npm start
```

### 3. Open in browser
```
http://localhost:3000
```

To test with 2 people, open the same URL in **two browser tabs** (or two different devices on the same WiFi).

---

## 🌐 Deploy to Railway (Free Hosting)

1. Go to https://railway.app and sign up (free)
2. Click **"New Project"** → **"Deploy from GitHub repo"**
3. Push your code to GitHub first:
   ```bash
   git init
   git add .
   git commit -m "messenger app"
   git push
   ```
4. Railway auto-detects Node.js and deploys it
5. Click **"Generate Domain"** to get a public URL like:
   `https://your-app.up.railway.app`

Share that URL with the other person — they open it and you can chat in real time! 🎉

---

## 🌐 Alternative: Deploy to Render (Also Free)

1. Go to https://render.com → New Web Service
2. Connect your GitHub repo
3. Set **Start Command** to: `npm start`
4. Deploy — you get a free URL

---

## ✨ Features

- Real-time messaging via WebSockets
- Typing indicator ("Alex is typing...")
- Online user count
- Join/leave notifications
- Clean dark UI
- Works on mobile

---

## 🔧 How It Works

```
Browser A  ──send_message──▶  Server  ──receive_message──▶  Browser B
Browser A  ◀─receive_message─  Server  ◀──send_message──  Browser B
```

Socket.io keeps a persistent connection open between the browser and server.
When someone sends a message, the server instantly broadcasts it to everyone connected.
