<img width="192" height="192" alt="icon-192" src="https://github.com/user-attachments/assets/a7f31f77-7f1b-4192-8ad1-8ad41b17b887" />


Tap N Pray is a lightweight, mobile‑optimized Bible verse experience designed for simplicity, beauty, and daily encouragement.  
The app delivers a daily verse, supports multiple translations, includes ambient audio, and features a real daily streak system to help build consistent spiritual habits.

Live Site: tapnpray.github.io

## ✨ Features

### 📖 Daily & Random Bible Verses
- Pulls verses from NLT, NIV, and KJV JSON datasets  
- Daily verse is generated deterministically using a date‑based seed  
- Random mode available for exploration  

### 🎧 Ambient Mode
- Optional calming background audio  
- Smooth fade‑in / fade‑out transitions  

### 🔊 Text‑to‑Speech Reading
- Tap the verse or speaker icon to hear the verse read aloud  
- Word‑by‑word highlighting for readability  

### 🔥 Real Daily Streak System
- Streak increases only when visiting on a new day  
- Resets if a day is missed  
- Includes milestone badges (7, 30, 100 days)  
- Progress bar toward 100‑day achievement  

### 🌄 Auto‑Darkening Backgrounds
- Background images change based on time of day  
- Medium darkening applied at night for readability  
- Smooth transitions  

### 📤 Universal Sharing
- Uses native share APIs when available  
- Clipboard fallback  
- Download fallback  
- All errors silently suppressed  

### 📱 Mobile‑First Design
- Optimized for iOS and Android  
- Smooth scrolling  
- Large tap targets  
- Safe‑area padding for notched devices  

## 🛠️ Tech Stack
- **HTML5 / CSS3 / JavaScript**
- **LocalStorage** for streaks and daily verse caching  
- **Web Speech API** for text‑to‑speech  
- **Canvas API** (optional image generation)  
- **Responsive design** with mobile‑first layout  

## 📂 Project Structure
/BIBLE/
/NLT/
/NIV/
/KJV/
backgrounds/
sounds/
index.html
logo.svg
README.md



## 🚀 Getting Started

1. Clone the repository:
   ```bash
   git clone https://github.com/<your-username>/tapnpray.git
Open index.html in any modern browser

(Optional) Host on GitHub Pages for instant deployment

📄 License
This project is open-source under the MIT License.

🙏 Acknowledgements
Scripture text sourced from public JSON datasets

Background images and audio provided by the project owner

Built with love to encourage daily time in the Word
