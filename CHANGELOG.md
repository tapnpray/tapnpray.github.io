# Changelog

## v1.4.0 - 2026-04-23 (Performance + Polish + UX Improvements)

### ✨ Features & Enhancements

- Added **smart background sync system**
  - Background now only updates when time block changes (morning/day/evening/night)
  - Prevents unnecessary updates and improves performance
  - Reduces redundant calls to `updateBackground()`

- Improved **background flicker prevention**
  - Added `currentBackground` + `currentBrightness` tracking
  - Prevents re-applying identical background images
  - Smooth transitions between time-of-day changes

- Added **sync-safe time block handling**
  - Introduced `document.body.dataset.block` as a shared state source
  - Ensures DOM + JS stay in sync for background logic

- Enhanced **share button UX**
  - Added press animation (`scale down on tap`)
  - Added subtle haptic feedback (`navigator.vibrate(10)`)
  - Improved feedback timing before share sheet opens

- Improved **share system reliability**
  - Added `isSharing` lock to prevent duplicate share triggers
  - Added safe validation for `File` before invoking native share
  - Improved fallback flow for unsupported devices

- Upgraded **share image rendering**
  - Improved reference text rendering for mobile clarity
  - Fixed washed-out Bible reference color issue
  - Added dual-pass rendering for better contrast on iOS
  - Improved glass card shadow + edge glow system
  - Optimized background blur + brightness handling in canvas export

- Added **toast notification system improvements**
  - Centralized `showToast()` usage for share feedback
  - Improved timing and reduced UI spam
  - Ensured toast only appears after validation passes

- Improved **help modal UX**
  - Markdown rendering via `marked.js`
  - External links now open in new tab automatically
  - Added click-outside-to-close behavior

- Improved **streak system UI**
  - Better milestone messaging (7 / 30 / 100 days)
  - Improved progress bar scaling logic
  - Enhanced badge activation animation logic

- Enhanced **verse sharing animation**
  - Added button press feedback animation
  - Added haptic vibration on share trigger (mobile only)

---

### ⚙️ Performance Improvements

- Optimized background update loop:
  - Replaced unconditional interval updates with **change-detection system**
  - Now only updates every 2 minutes *if time block actually changes*

- Reduced unnecessary DOM + canvas work during background rendering

- Cached time-block logic for faster interval checks

---

### 🧠 Code Quality / Architecture

- Introduced reusable function:
  - `syncBackgroundBlock()` for consistent state syncing

- Improved separation of concerns:
  - Background logic now isolated from UI rendering logic
  - Share system now fully self-contained with validation gates

- Strengthened safety checks:
  - Blob validation before share/download
  - Defensive null checks for modal operations

---

### 🐛 Fixes

- Fixed potential mismatch between:
  - `getTimeBlock()` state
  - `document.body.dataset.block`

- Fixed share fallback modal appearing with invalid blob state

- Fixed rare issue where share toast appeared before validation completed

- Fixed reference text rendering inconsistency on mobile canvas export

---

### 📌 Notes

- No breaking changes
- Fully backward compatible with existing saved data (streaks, preferences)
- Performance improvements are passive (no user-facing behavior change unless background changes occur)

---
