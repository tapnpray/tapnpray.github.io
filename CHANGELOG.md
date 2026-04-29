
# Changelog

All notable changes to the Tap N Pray web application will be documented in this file.

## [2026-04-28]

### Added
- **Dynamic Background System**: Implemented a localized day/night toggle switching between `morning.png` and `night.png` based on the user's local 24-hour clock.
- **Pre-Blurred Assets**: Integrated `morning-blurred.png` and `night-blurred.png` specifically for the sharing system to bypass iOS-specific rendering bugs.
- **Branded Share View**: Added bottom-left branding to shared images, including the logo and URL.
- 
### Changed
- **OG Image Alignment**: Updated the Open Graph (`og:image`) strategy to ensure link previews across Facebook, iMessage, and X (Twitter) remain consistent with the new high-resolution nature theme.
- **Minimalist Share UI**: Removed the "Glassmorphism" card in favor of full-bleed imagery with floating text for a more majestic feel.
- **Typography & Legibility**: Implemented high-contrast `text-shadow` layers ($0\ 2px\ 12px\ rgba(0,0,0,0.9)$) to ensure the verse remains readable over the morning sun.
- **Canvas Logic Refactor**: Switched from `ctx.filter` to pre-rendered assets, resolving the WebKit (iOS) failure to render blurs in shared canvases.

### Fixed
- **iOS Image Sharing**: Resolved the issue where shared images appeared un-blurred on iPhones by using static blurred backdrops.
- **Text Clipping**: Optimized the `maxWidth` and `lineHeight` in the canvas generator to prevent verse text from hitting the screen edges on mobile shares.



---------------------------------------------------------------------------------------------------------------------------------------------------------------------------


# Changelog - Tap N Pray (index.html)

All notable changes to the Tap N Pray web application are documented in this file.

## [1.2.0] - 2026-04-26

### Added
- **GA4 Advanced Event Tracking**: Integrated a comprehensive analytics suite to monitor user engagement:
  - `read_aloud`: Tracks when users engage with the text-to-speech feature.
  - `change_translation`: Monitors preference shifts between NLT, NIV, and KJV.
  - `view_mode_change`: Tracks usage of 'Daily' vs 'Random' verse modes.
  - `ambient_toggle`: Tracks engagement with background sounds.
  - `donation_intent`: Tracks clicks on the support/Venmo heart icon.
- **Elite Curated Verse System**: Expanded and organized the core database into 200+ verses, categorized by theme (Anxiety, Strength, Love, Hope, Wisdom, etc.) for easier maintenance and variety.

### Changed
- **Global Synchronization Logic**: Updated the daily verse generator to use a calendar-based seed (`getSeed(today)`). This ensures all users globally see the exact same "Daily Bible Verse" simultaneously.
- **Improved Randomization**: Re-engineered the "Random" button logic to include an anti-overlap filter, ensuring the random verse never matches the currently displayed daily verse.
- **Calendar-Based Look-Back**: Implemented a 7-day mathematical "look-back" in the sync logic to prevent a verse from repeating as the "Daily Verse" within the same week.

### Fixed
- **Code Organization**: Cleaned up the JavaScript structure by moving verse data into categorized blocks, improving code readability and reducing logic errors during the 365-day rotation.

---
*Generated for the Tap N Pray Version 1.2.0 Release.*







# Changelog

All notable changes to the **Tap N Pray** project will be documented in this file.

## [1.1.0] - 2026-04-25

### Added
- **Elite Curated Verse System:** Integrated a weighted verse selection engine that prioritizes high-impact verses (Weight 5) over general faith verses.
- **Seasonal Boost Logic:** Implemented a dynamic date checker for Christmas and Easter (using the Butcher-Meeus Algorithm for dynamic Easter calculation) to surface relevant scriptures.
- **App Bootstrapper:** Added a robust `initApp()` function to handle translation fetching and event listener binding upon DOM completion.
- **Speech Highlighting:** Integrated `onboundary` event tracking in the Web Speech API to highlight individual words in the UI as they are read aloud.
- **Toast Notification System:** Added a non-intrusive UI feedback mechanism for status updates (e.g., "Generating image...").

### Fixed
- **iOS Canvas Blur (Triple Draw):** Resolved a critical rendering bug where filters would not apply to shared images on iOS. Implemented a "Triple Draw" GPU priming hack to force-render the 30px blur.
- **Z-Index Layering:** Fixed an issue where background elements could overlap the main content container; established a strict Z-index hierarchy.
- **Text Contrast:** Enhanced readability by implementing multi-layered CSS text-shadows and a dynamic `--brightness` CSS variable for background images.
- **Safe Area Insets:** Corrected layout shifting on modern mobile devices by utilizing `env(safe-area-inset-top)` for fixed headers and icons.
- **CSS Duplication:** Removed redundant `display` properties in the `#helpModal` styles that were causing layout conflicts.

### Changed
- **Typography:** Standardized the use of the 'Merriweather' font family across the app and the canvas generation engine for brand consistency.
- **Icon System:** Updated the `icon-btn` class to include a floating idle animation and distinct touch feedback (`pressed` state) optimized for iOS Safari.
- **Navigation Layout:** Adjusted the positioning of the Streak pill and UI icons to prevent overlapping with the "Daily/Random" toggle buttons.

## [1.0.0] - 2026-04-20
### Initial Release
- Core Bible engine with NLT, NIV, and KJV support.
- Localized streak tracking via `localStorage`.
- Ambient audio implementation.
- Basic image sharing capabilities.
