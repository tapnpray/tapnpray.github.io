<img src="icon-192.png" width="120" alt="Tap N Pray Logo" />

**One Tap. One Verse. One Step Closer to Christ.**

Tap N Pray is a minimalist, immersive web application designed to bring the Word of God into your daily life with simplicity and focus. Built for deep reflection, meditation, and prayer, it delivers a meticulously curated Bible verse experience through a high-contrast, distraction-free typography interface.

## 🚀 Project Status
For a detailed breakdown of codebase development, please refer to the [Full Changelog](./CHANGELOG.md).

**Current Version: 1.3.3**
- **Facebook Share Reliability:** Resolved the "grayed out" button issue, ensuring native sharing correctly recognizes and processes generated images.
- **UI/UX Enhancements:** Fixed rendering conflicts with "Toast" notifications and optimized stacking context for a smoother, more reliable interface.
- **Notification Fixes:** Resolved an issue where "Streak" and "Tap" hint bubbles were failing to trigger on initial app load.

## ✨ Core Features

### 📖 Immersive Verse Experience
- **Daily & Random Modes** Start your day with a globally synchronized **Daily Bible Verse** or explore scripture dynamically using the **Random** toggle.
- **Elite Curated System** Rather than pulling completely raw random data, Tap N Pray utilizes an internal **weighted mathematical pool system** to prioritize balance across custom thematic categories (Gospel, Peace, Strength, Love, Hope, Wisdom, Faith, Praise, and Comfort).
- **Seasonal Holiday Logic** Integrated dynamic calculation utilities (including a manual tracking algorithm for Easter dates) to automatically increase the frequency of relevant scriptures during key holiday windows (Christmas, Good Friday, Easter Sunday).
- **History Avoidance Rotation** The selection engine features an explicit `localStorage` rotation buffer tracking the last 14 unique verses (`recentVerses`) to filter out recent repeats and maintain high user engagement.
- **Multiple Translations** Seamlessly switch on the fly between optimized database structures for:
  - **NLT** (New Living Translation)
  - **NIV** (New International Version)
  - **KJV** (King James Version)

---

### 🔊 Premium Narration & Soundscapes
- **High-Fidelity Neural TTS** Tap any verse to hear it read aloud. The engine automatically targets and hooks into premium, natural-sounding neural audio profiles natively installed on the user's local operating system (such as iOS Premium/Natural layers or Google US English).
- **Asynchronous Voice Pre-Fetching** Utilizes native `onvoiceschanged` lifecycle listeners to cache system audio modules immediately on boot, eliminating mobile interface delay during tap interactions.
- **Real-Time Word Highlighting** Words smoothly illuminate individually as they are spoken, functioning as a clean tracking cursor that auto-resets on completion to help you focus and meditate deeply.
- **Ambient Soundscape** Toggle the 🌿 button to crossfade a calming, low-volume background loop (`calm.mp3`) for a peaceful, undistracted prayer environment.

---

### 🔥 PWA Optimization & Habits
- **Cross-Platform Global Sync** Engineered to bridge standalone PWA sandboxes. By shifting seed calculations to an explicit, time-zone agnostic UTC date string blueprint, both standard mobile Safari/Chrome tabs and installed **Add to Home Screen** app containers display the exact same synchronized verse worldwide.
- **Automated Midnight Refresh** Includes an integrated, ultra-lightweight midnight timer loop. It calculates the exact milliseconds remaining until the next global UTC rollover and triggers an automated silent page update, ensuring open apps update without requiring a manual app relaunch.
- **Timezone-Agnostic Streak Tracking** Build consistency in your quiet time with streak metrics that parse strict date objects, preventing accidental local timezone offset resets at midnight.
  - 🌿 7 days — *Initial Habit Milestone*
  - 🔥 30 days — *Consistency Milestone*
  - 👑 100 days — *Spiritual Momentum*

---

### 🎨 Clean UI & Social Canvas Sharing
- **High-Contrast Readability** Intentionally completely clean layout optimized for legibility, removing heavy visual decoration in favor of elegant font weights, adaptive scale margins, and premium typography.
- **Sequenced Micro-Onboarding** Subtle, timed interface hint bubbles that glide into position sequentially to guide user engagement smoothly without cluttering the screen.
- **Dynamic Image Generator Canvas** Generates high-resolution $1080 \times 1080$ sharing graphics on demand. Features text shadow protections for readability over beautiful pre-blurred daytime/nighttime environmental visual assets, custom automatic text-wrapping algorithms, and embedded **Tap N Pray** branding footprints.

---

## 🛠️ Technical Overview

- **Frontend Architecture**: Vanilla ECMAScript 6 / HTML5 Canvas / CSS3 (Variables & Custom Properties).
- **Data Hydration**: Highly optimized, decoupled JSON book-chapter translation trees for instantaneous asset loads.
- **Runtime Reference Safeguards**: Global utility hooks and external script parameters are wrapped in explicit type-checks to guarantee runtime application stability across distinct mobile and web environments.
- **Analytics Pipeline**: Integrated Google Analytics tracking layer (`gtag`) mapping application engagement triggers like view modes, translation adaptations, and generation intents.
- **PWA Architecture**: Standalone web app manifest ready with native mobile environment safe-area padding layouts (`env(safe-area-inset)`).

---

## 🙏 Mission

The mission of **Tap N Pray** is to completely remove the digital friction between a busy, fast-paced life and the grounding presence of the Word of God. 

Through minimalist design and thoughtful front-end engineering, the goal is to provide a clean space to help you take **one step closer to Christ every single day**.

---

## 💛 Support the Project

If Tap N Pray has encouraged your daily walk, you can directly support the development mission:

👉 [Support on Venmo](https://venmo.com/u/tapnpray)

### What your support helps fund:
- Production of physical **Tap N Pray NFC keytags**
- Deployment tools to share Scripture easily
- Continued, ad-free app speed and stability improvements

### Why keytags?
These custom integration tag tools are designed to:
- Be shared easily in modern ministry settings  
- Serve as prompt physical touchpoints in daily life  
- Help others discover God’s Word with a simple tap  

<img src="TapPray-NFCTag.gif" width="240" alt="NFC Keytag Demo" />

---

## ❤️ Created For

Built with love for the Kingdom.
