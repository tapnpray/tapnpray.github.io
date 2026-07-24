
# Changelog
All notable changes to this project will be documented in this file.

# Changelog
 
**Current Version: 1.3.4**
 
- **Improved Navigation:** Updated menu controls for better accessibility, responsiveness, and a more consistent mobile experience.
 
- **Streak Fixes:** Eliminated duplicate streak processing during startup to ensure streak tracking and notifications behave consistently. 【1-4dfc03】
 
- **Verse Layout Improvements:** Refined verse rendering to improve line wrapping and maintain proper centered alignment for longer passages while preserving word-by-word highlighting during audio playback.
 
- **Verse Loading Protection:** Added safeguards to prevent blank verse displays if content is temporarily unavailable. 【1-4dfc03】
 
- **Better Popup Experience:** Help, Share, and Streak windows can now be dismissed by tapping outside the popup area. 【1-4dfc03】
 
- **Code Optimization:** Performed code cleanup, standardized button styling, and improved maintainability to support future feature development. 【1-4dfc03】

## [1.3.3] - 2026-06-12
### Fixed
- **Facebook Share Reliability:** Resolved the "grayed out" button issue by optimizing the Web Share API data handling and UI stacking, ensuring the generated image `Blob` is correctly passed to the OS share sheet.
- **UI Stacking:** Resolved a rendering conflict where the "Toast" notification was blocked by other components due to incorrect z-index layering.
- **Notification Triggers:** Fixed a bug where "Streak" and "Tap" hint bubbles were failing to appear on the initial page load by improving initialization logic.

### Improved
- **CSS Architecture:** Consolidated popup and notification styles into a unified stacking system to ensure consistent visibility across mobile browsers.
- **Initialization:** Added a page-load delay to guarantee that notification animations trigger reliably after the DOM is fully ready.

---

## [1.3.2] - 2026-06-05
### Added
- Implemented NFC tag interaction tracking.
- Added ambient audio toggle with smooth fade-in/out transitions.

### Changed
- Refactored verse selection to use a stable deterministic seed, ensuring all users see the same daily verse.
- Optimized image generation for social sharing with a minimalist layout.

---

## [1.3.2] - 2026-06-05
### Added
- Implemented NFC tag interaction tracking.
- Added ambient audio toggle with smooth fade-in/out transitions.

### Changed
- Refactored verse selection to use a stable deterministic seed, ensuring all users see the same daily verse.
- Optimized image generation for social sharing with a minimalist layout.

---


## [1.3.2] - 2026-05-31

### Added

* Added NFC tag analytics tracking using Google Analytics.
* Added `nfc_tag_tap` event for visits originating from NFC keytags (`?src=nfc`).
* Added `verse_heard` event to track completed Text-to-Speech verse playback.
* Added verse reference and translation metadata to completed listen analytics.

### Improved

* Expanded engagement analytics to better measure user interaction.
* Added visibility into:

  * NFC keytag scans
  * Verse audio starts (`read_aloud`)
  * Verse audio completions (`verse_heard`)
  * Verse share generation
  * Donation intent clicks
  * Translation changes

### Fixed

* Resolved GitHub Pages SSL certificate issues affecting the root domain.
* Corrected HTTPS support for NFC URLs and direct access to `https://tapnpray.com`.
* Updated custom domain configuration to support both root and www domains securely.

### Analytics Events

* `nfc_tag_tap`
* `read_aloud`
* `verse_heard`
* `share_image_generated`
* `donation_intent`
* `change_translation`


## Version 1.3.1 — Stability & Streak Improvements

### Fixed
- Fixed streak tracking not incrementing correctly across consecutive days.
- Corrected date handling logic that could prevent streak progression.
- Standardized streak calculations using UTC-based dates for improved consistency across devices and time zones.

### Improved
- Daily streaks now update reliably alongside the Daily Verse system.
- Improved long-term streak persistence and rollover behavior.
- Added safer share handling for browsers that do not fully support file sharing.
- Share image modal now closes automatically after saving an image.
- Improved voice-loading reliability for text-to-speech playback on supported browsers.
- Simplified Random Verse pool handling by removing unnecessary cache resets.

### Technical
- Replaced legacy date string storage with standardized `YYYY-MM-DD` UTC format.
- Updated streak comparison calculations to use `Date.UTC()` for accurate day-to-day tracking.
- Added modern Web Share API compatibility checks using `navigator.canShare()`.
- Cleaned up internal Random Verse selection logic for improved efficiency.

### Notes
- Mobile verse highlighting remains unchanged and optimized for the primary Tap N Pray experience.
- Desktop browser word-highlighting behavior may vary depending on the browser's Web Speech API implementation.




## Version 1.3.0 — Streak System Fix

### Fixed
- Fixed streak tracking logic not incrementing correctly across days
- Rebuilt streak date comparison system using stable UTC formatting
- Fixed incompatible date parsing issue caused by mixed date formats
- Improved cross-device and timezone consistency for streak tracking

### Improved
- Daily streaks now update reliably at day rollover
- Streak persistence is now synchronized with the app’s UTC daily verse system

### Technical
- Replaced `toDateString()` streak storage with standardized `YYYY-MM-DD` UTC format
- Corrected day-difference calculations using `Date.UTC()`
- Prevented invalid date parsing from freezing streak progression




# Version 1.2.9

### ✅ Daily Verse System Overhaul
Fixed an issue where the Verse of the Day could become stuck on the same verse across multiple days.

#### Changes
- Rebuilt daily verse generation using a true UTC-based date key.
- Daily verse now changes exactly at midnight UTC worldwide.
- All users now receive the exact same daily verse globally.
- Removed browser locale dependency from verse generation.
- Stabilized deterministic verse selection logic.

#### Technical Improvements
- Replaced local date generation with:
  ```js
  YYYY-MM-DD (UTC)
  ```
- Added automatic midnight UTC refresh scheduling.
- Fixed stale `localStorage` reuse issues.

---

### ✅ Auto Midnight Refresh
Added a live rollover system so the app updates automatically at midnight UTC without requiring a page refresh.

#### Added
- `setAutoRefreshAtMidnight()`

#### Result
- Daily verse updates automatically while the app remains open.

---

### ✅ Date Display Upgrade
Updated verse date formatting to include the weekday.

#### Before
```text
May 27, 2026
```

#### After
```text
Wed May 27 2026
```

---

### ✅ Verse Engine Improvements
Enhanced deterministic verse selection architecture.

#### Improvements
- Preserved globally identical verse pool ordering.
- Maintained weighted curation system.
- Preserved recent verse filtering for random mode.
- Preserved seasonal verse boosting system.

---

### ✅ Easter Seasonal Logic Fix
Fixed a UTC inconsistency inside the Easter seasonal calculation.

#### Fix
- Converted Easter date generation to UTC-safe handling.

#### Result
- Seasonal verse boosts now behave consistently worldwide.

---

### ✅ Seed Hash Upgrade
Improved deterministic seed distribution logic.

#### Benefits
- Better long-term verse distribution
- Reduced clustering/repetition patterns
- Improved randomness quality while remaining deterministic

---

# Result

The Verse of the Day system is now:

- UTC synchronized
- Globally consistent
- Deterministic
- Auto-refreshing
- Season-aware
- Weighted and curated
- Frontend-only
- Backend-free
- Mobile-safe


## [1.2.8] - 2026-05-24

### Fixed
- **Daily Verse Synchronization**: Resolved an issue where the verse failed to update at midnight. Standardized date calculations using `en-CA` locale formatting for seed generation, ensuring consistent daily triggers across all devices and browsers.
- **UI Date Consistency**: Synchronized the displayed date format with the backend seed-generation logic to eliminate "off-by-one" day discrepancies caused by time zone offsets.
- **Storage Reliability**: Improved the `dailyVerse` caching mechanism to prevent local storage conflicts during daily resets.

### Optimized
- **Codebase Stability**: Refactored `generateDaily` and `updateVerse` to use unified date handling.
- **Version Tracking**: Formalized internal versioning structure to align with repository releases.

## [1.2.7] - 2026-05-22

### Fixed
- **Mobile Layout Overlap:** Fixed an issue where long Bible verses would vertically overflow and overlap with the top logo or the bottom menu button (FAB) on mobile devices.
- **Daily Verse Synchronization:** Resolved a bug causing different devices (e.g., desktop vs. mobile) to display different "Daily Verses" on the same day. The Daily Verse is now generated from a globally synchronized static pool, ensuring a unified experience across all platforms.

### Changed
- **UI Optimization:** Reduced the size of the top logo and shifted it higher up the screen to maximize readable space for longer verses.
- **Dynamic Padding:** Updated the main content container to use dynamic safe-area padding (`env(safe-area-inset-top/bottom)`) and `min-height`. This allows natural scrolling for massive verses while keeping short verses perfectly centered.
- **Verse Generation Logic:** Refactored the core verse pool generation logic (`buildWeightedPool` and `getStaticPool`). The global Daily Verse now ignores local history to stay synced, while the "Random" button retains its local anti-repeat protection.




## [1.2.6] - 2026-05-16

### Added
- **Elite Curated Verse System:** Integrated a structured script-side collection of cornerstone scriptural references organized by emotional and spiritual themes (Anxiety, Strength, Comfort, etc.).
- **Global Synchronization Roll:** Added a custom deterministic mathematical date-seeding engine (`getSeed`) ensuring all global users receive the exact same "Daily Verse" seamlessly without server-side dependencies.
- **Seasonal Event Engine:** Added smart utility hooks to dynamically compute complex variable holidays (like Easter via astronomical algorithms) and trigger target content boosts during key calendar ranges (Christmas, Good Friday, Resurrection Sunday).
- **Recent Verse Cache:** Implemented a rolling `localStorage` sliding-window mechanism (`recentVerses`) to block chosen references from immediately repeating within a 14-day cycle.

### Changed
- **Minimalist Share Architecture:** Completely overhauled the `shareVerse` canvas generator, shifting from heavy structural UI cards to a sleek, modern, background-bleeding floating typography design.
- **Brand Identity Layout:** Reworked image compilation layouts to anchor an official brand logo and the site domain (`www.tapnpray.com`) cleanly into the bottom-left quadrant of shared graphics.
- **Responsive Text Scaling:** Implemented dynamic width reflow boundaries (`maxWidth = size - 160`) and contextual font resizing rules inside the HTML5 Canvas layout loop to maximize legibility.

### Fixed
- **Mobile Menu Startup Halt:** Resolved a critical out-of-order `ReferenceError` during top-down asset parsing by hoisting core app tracking parameters and variables to the top of the instantiation script, ensuring the floating navigation FAB (`#menuFab`) initializes flawlessly.
- **WebKit Audio Playback Hangs:** Fixed a WebKit/Safari speech-queue limitation by implementing a cross-browser voice allocation engine hook (`onvoiceschanged`) to prevent text-to-speech rendering routines from dropping on iOS devices.
- **Infinite File Load Inversion Loop:** Refactored error handling boundaries inside the `changeTranslation` router to block recursive infinite layout update loops if localized resources are delayed or missing.
- **Typography Readability:** Added strong, multi-pass opaque drop shadows (`shadowBlur = 25`) to canvas text render layers to enforce high-contrast legibility over bright background imagery.



## [1.2.5] - 2026-05-16

### Added
- **Elite Curated Verse System Engine:** Fully wired the advanced weighting engine to the front-end display, enabling smart distribution across custom categories (Gospel, Peace, Strength, Hope, etc.).
- **Seasonal Holiday Boost System:** Integrated dynamic calculation utilities (including a tracking algorithm for Easter dates) to automatically increase the frequency of relevant scriptures during key holiday windows.
- **History Avoidance Rotation:** Implemented a `localStorage` loop tracking the last 14 unique verses (`recentVerses`) to filter out recent repeats and keep user engagement high.

### Fixed
- **Engine Hook Synchronizations:** Rewrote `generateDaily()` and `showRandom()` to accurately reference and pull from the active weighted pool rather than old fallback arrays.
- **Runtime Reference Safeguards:** Wrapped external script references (`setAutoRefreshAtMidnight`, `fadeIn`, `fadeOut`) in type-checks to prevent uncaught runtime exceptions and lock down script stability.
- **Syntax Validation:** Resolved unclosed code structures and formatted nested object properties inside the script container for error-free deployment.


## [1.2.4] - 2026-05-16

### Added
- Implemented an automated background midnight refresh scheduler via lightweight UTC millisecond offsets, synchronizing active browser tabs and standalone PWA installations globally when the verse rolls over.
- Embedded asynchronous browser voice engine pre-fetching logic using `onvoiceschanged` initialization handlers to gracefully cache natural native devices profiles on boot.

### Fixed
- Fixed critical isolated state variances in standalone iOS "Add to Home Screen" PWA sandboxes by migrating all date-seeding and calculation logic to a strict time-zone agnostic UTC format.
- Resolved page execution freezing by restructuring closing bracket scope boundaries around core framework listeners and eliminating unhandled elements within the help modal binding routines.
- Corrected synchronized speech boundary rendering inside the audio narration tracking sequence, ensuring precise character-by-character text highlight extraction and full tracking resets on completion.
- Remediated local timezone offset shifts across midnight thresholds in sub-container tracking fields, securing uninterrupted sequential user streak calculation metrics.

## [1.2.3] - 2026-05-13

### Added
- **Floating Action Button (FAB):** Integrated a new brand-specific blue (#108cd7) button at the bottom center.
- **Christian Cross Icon:** Implemented a custom CSS-based cross that morphs into an "X" when the menu is active.
- **Streak Hint Bubble:** Added a floating notification to display the user's current activity streak count.
- **Ambient Toggle:** New menu action for triggering ambient background effects.

### Changed
- **Navigation Layout:** Transitioned the menu system to a fixed, bottom-centered position for better reachability.
- **Visual Design:** Updated the UI to prioritize clean typography and high-contrast readability over previous glassmorphism styles.
- **Scrolling Behavior:** Restored vertical page scrolling while keeping the FAB and navigation menu in a fixed position.

### Fixed
- **Mobile Rendering:** Resolved issues where the FAB was hidden behind mobile browser navigation bars or clipped by containers.
- **Layering Issues:** Corrected z-index conflicts that caused the menu icon to appear behind the verse text.
- **Responsiveness:** Optimized viewport height (vh) calculations to ensure UI elements are visible across various mobile browsers.


# [1.2.2] - 2026-05-08

### Enhanced
*   **Typography Contrast:** Significantly increased text-shadow depth and spread on daily verses to ensure high-contrast readability against bright background assets.
*   **Background Dimming:** Implemented a darker overlay tint (50% for daytime, 70% for night) on both the live site and the generated share images to prevent text "washout" on high-luminance areas.
*   **Share Image Legibility:** Boosted canvas shadow rendering parameters (25px blur and 6px offset) to maintain sharp, clean typography in exported project assets.

### Fixed
*   **Mobile Rendering:** Refined the background filter logic to reduce processing overhead on iOS WebKit while maintaining visual depth.




# [1.2.1] [2026-04-28]

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
