# 🙏 Tap N Pray

**One Tap Closer to Christ**

Tap N Pray is a simple, beautifully designed web app that delivers a **daily Bible verse** with a calm, distraction-free experience. Built as a Progressive Web App (PWA), it feels like a native mobile app while remaining lightweight and accessible.

https://tapnpray.github.io/

---

## ✨ Features

* 📖 **Verse of the Day**
  Automatically displays a new Bible verse each day

* 🎧 **Listen to the Verse**
  Built-in audio playback using your device’s voice

* 🌧️ **Ambient Background Sound**
  Optional calming rain audio for a more meditative experience

* ⭐ **Save Favorite Verses**
  Store and revisit meaningful verses locally on your device

* 🔄 **Multiple Translations**
  Switch between KJV, NIV, and NLT instantly

* 🔥 **Tap Streak**
  Track your daily engagement and build a habit

* 🌅 **Dynamic Backgrounds**
  Peaceful rotating backgrounds that enhance focus

* 📲 **Installable App (PWA)**
  Add to your home screen for a native app-like experience

---

## 📱 How to Install (Mobile)

### iPhone (Safari)

1. Open the site
2. Tap the **Share** button
3. Select **“Add to Home Screen”**

### Android (Chrome)

1. Open the site
2. Tap the **menu (⋮)**
3. Select **“Install App”**

---

## 🛠️ Tech Stack

* HTML5
* CSS3 (Glassmorphism + responsive design)
* Vanilla JavaScript
* Web Speech API (text-to-speech)
* LocalStorage (favorites + streak tracking)
* Progressive Web App (manifest + service worker)

---

## 📁 Project Structure

```
tapnpray.github.io/
│
├── index.html
├── manifest.json
├── sw.js
├── logo.svg
├── icon-192.png
├── icon-512.png
│
├── backgrounds/
│   ├── morning1.png
│   ├── morning2.png
│   └── day1.png
│
├── sounds/
│   └── rain.mp3
│
└── BIBLE/
    ├── KJV/
    ├── NIV/
    └── NLT/
```

---

## ⚙️ How It Works

* A daily verse is selected using a **date-based seed**
* Bible data is fetched from JSON files stored in the repository
* Favorites and streak data are stored locally using **LocalStorage**
* Backgrounds rotate automatically for a calm, immersive experience
* The app runs fully client-side—no backend required

---

## 🚀 Future Improvements

* Push notifications (daily verse reminders)
* User accounts + cloud sync
* More ambient sound options
* Expanded devotional content
* Native app deployment (iOS / Android)

---

## 🙌 Mission

Tap N Pray was created to make it easier to pause, reflect, and connect with God—one simple tap at a time.

---

**“Be still, and know that I am God.” – Psalm 46:10**
