# 🙏 Tap N Pray

**Tap N Pray** is a minimalist, distraction-free web app that delivers a daily Bible verse experience with audio playback, ambient sound, and a habit-forming streak system.

Built as a lightweight static site, it focuses on simplicity, consistency, and a calming user experience.

---

## ✨ Features

### 📖 Daily Verse System

* Displays a **new Bible verse each day**
* The verse remains consistent throughout the day
* Automatically updates the next day
* Uses a deterministic seed based on the current date

---

### 🔀 Random Verse Mode

* Switch between:

  * **Daily Verse**
  * **Random Verse**
* Instant updates without reloading the page

---

### 🌍 Multiple Translations

* Supports:

  * NLT (default)
  * NIV
  * KJV
* Loads verse data from local JSON files
* Remembers user’s selected translation

---

### 🔊 Audio Playback (Text-to-Speech)

* Tap the speaker icon or verse to:

  * Hear the verse read aloud
  * Watch words highlight in sync
* Uses the browser’s built-in Speech Synthesis API

---

### 🌿 Ambient Sound

* Optional background audio for a calming experience
* Smooth fade-in / fade-out transitions

---

### 🎨 Dynamic Backgrounds

* Background changes based on time of day:

  * Morning
  * Day
  * Evening
  * Night
* Subtle zoom animation for a premium feel
* Transitions smoothly without flicker

---

### 🔥 Tap Streak System

* Tracks daily engagement
* Displays streak at bottom of screen
* Includes:

  * Grace day (miss one day without reset)
  * Milestone badges (7 / 30 / 100 days)
  * Progress bar toward next goal
* Tap to open full streak dashboard

---

### 📤 Share Feature

* Generates a **shareable image** of the current verse
* Includes:

  * Current background
  * Verse text
  * Reference
  * Logo (bottom-left)
  * Website branding
* Uses Canvas API + native share (if supported)

---

## 🧠 How It Works

### Daily Verse Logic

The app generates a consistent daily verse using the current date:

```js
const today = new Date().toDateString();
dailyKey = keys[getSeed(today) % keys.length];
```

This ensures:

* Same verse all day
* New verse each day
* No server required

---

### Data Source

Bible data is loaded from local JSON files:

```
/BIBLE/
  NLT/NLT_bible.json
  NIV/NIV_bible.json
  KJV/KJV_bible.json
```

Each verse is flattened into a key format:

```
"John 3:16"
```

---

### State Management

Uses `localStorage` to persist:

* Daily verse key
* Streak count
* Last visit date
* Preferred translation

---

## 📁 Project Structure

```
/
├── index.html
├── /backgrounds
├── /sounds
│   └── calm.mp3
├── /BIBLE
│   ├── NLT/
│   ├── NIV/
│   └── KJV/
├── logo.svg
```

---

## ⚙️ Initialization Flow

1. Load Bible translations
2. Restore saved translation preference
3. Generate daily verse
4. Update UI
5. Start streak tracking

---

## 📱 Design Philosophy

* Minimal UI
* No distractions
* Mobile-first layout
* Fast load time
* No frameworks or dependencies

---

## 🚀 Future Improvements

* Background preloading (zero flicker)
* Swipe navigation between verses
* Progressive Web App (PWA) support
* Daily reminders / notifications
* Global synced daily verse

---

## 🛠️ Tech Stack

* HTML5
* CSS3 (Glassmorphism + animations)
* Vanilla JavaScript
* Web APIs:

  * Speech Synthesis API
  * Canvas API
  * LocalStorage API
  * Web Share API

---

## ❤️ Purpose

Tap N Pray is designed to:

* Encourage daily reflection
* Build a consistent habit
* Provide a peaceful, focused experience

---

## 🌐 Live Site

https://tapnpray.github.io

---

## 📜 License

This project is open and free to use for personal or inspirational purposes.
