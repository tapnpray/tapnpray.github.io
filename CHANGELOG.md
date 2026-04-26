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
