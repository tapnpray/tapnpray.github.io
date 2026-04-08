<img src="icon-192.png" width="120" alt="Tap N Pray Logo" />
Tap N Pray — Daily Bible Verse Web App
https://tapnpray.github.io/
A peaceful, mobile‑first Scripture experience with premium sharing, streak tracking, and ambient reflection.

Tap N Pray is a beautifully designed Bible verse web app built for simplicity, calm, and daily spiritual consistency. Every day, users receive a new verse displayed on a dynamic background with a frosted‑glass verse card, optional ambient audio, and text‑to‑speech reading. The app also includes a premium share engine that generates high‑quality verse images perfect for social media.

This project is fully client‑side and hosted on GitHub Pages.

✨ Features
📅 Daily & Random Verses
Automatically generates a new verse each day

Random mode for instant inspiration

Supports NLT, NIV, and KJV

Smooth translation switching

🔊 Text‑to‑Speech with Word Highlighting
Reads the verse aloud

Highlights each word as it’s spoken

Works on mobile and desktop

🌿 Ambient Audio
Optional calming background audio

Smooth fade‑in / fade‑out transitions

🔥 Real Daily Streak System
Tracks daily visits

Resets if a day is missed

Milestone badges: 7‑day, 30‑day, 100‑day

Progress bar and streak modal

🧊 Frosted‑Glass Verse Box
Dark, semi‑transparent glass effect

Auto‑darkening background

Centered layout with mobile‑optimized spacing

🖼 Premium Share Engine (1080×1080)
Generates a square, social‑media‑ready image

Georgia font with auto‑fit text

Soft‑white verse text

Darkened verse panel

Includes your logo.svg and tapnpray.github.io branding

Native share on mobile

Download fallback on desktop

🌅 Dynamic Background System
Morning / Day / Evening / Night background sets

Auto‑brightness adjustment

Soft blur for premium aesthetic

📱 Mobile‑First Design
Optimized for all screen sizes

Safe‑area padding for modern phones

No popups or intrusive UI

📊 Google Analytics
Tracks page views and engagement

Lightweight and non‑intrusive

🛠 Tech Stack
HTML5

CSS3 (frosted‑glass UI, responsive layout)

Vanilla JavaScript

Canvas API (premium share engine)

Web Speech API (text‑to‑speech)

LocalStorage (streak tracking, daily verse seed)

GitHub Pages (hosting)

📂 Project Structure
Code
/
├── index.html
├── logo.svg
├── backgrounds/
│   ├── morning1.png
│   ├── morning2.png
│   ├── day1.png
│   ├── day2.png
│   ├── evening1.png
│   ├── evening2.png
│   ├── night1.png
│   └── night2.png
├── sounds/
│   └── calm.mp3
└── BIBLE/
    ├── NLT/NLT_bible.json
    ├── NIV/NIV_bible.json
    └── KJV/KJV_bible.json
🚀 How It Works
1. Daily Verse Generation
A deterministic seed based on the current date selects a verse, ensuring every user receives the same verse each day.

2. Streak Tracking
LocalStorage records the last visit date and increments or resets the streak accordingly.

3. Premium Share Engine
The app uses the Canvas API to generate a 1080×1080 image with:

Background

Frosted panel

Auto‑fit verse text

Reference

Logo + URL

4. Dynamic Backgrounds
Time‑based background sets create a peaceful, immersive experience.

🧪 Local Development
Clone the repo and open index.html in a browser:

bash
git clone https://github.com/<your-username>/tapnpray.github.io
cd tapnpray.github.io
open index.html
No build tools required.

🌐 Deployment (GitHub Pages)
Push your code to the main branch

Enable GitHub Pages in repo settings

Set the source to main

Your site will be live at:
https://tapnpray.github.io/

🖼 Branding
logo.svg is used in the UI and in generated share images

The site URL is automatically added to shared images

The top logo never overlaps the verse box

📜 License
This project is open‑source under the MIT License.

🙏 Acknowledgments
Tap N Pray was built to create a peaceful, distraction‑free way to engage with Scripture daily.
Thank you for using and supporting this project.
