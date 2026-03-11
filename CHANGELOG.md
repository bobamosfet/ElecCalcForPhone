# Changelog

All notable changes to the HP 48 G+ Simulator are documented here.

---

## [1.4.0] — Current

### Added
- **LC resonance frequency** equation button (`f = 1 / (2π × √(L × C))`)
- **RAD/DEG toggle** soft key — switches angle mode for all trig functions
- Trig functions (SIN, COS, TAN, ASIN, ACOS, ATAN) now respect RAD/DEG mode
- Status bar updates to show current angle mode (RAD or DEG)

---

## [1.3.0]

### Added
- **SHIFT key** — replaces ROLL key; press once to access secondary functions
- Shifted functions: x², 10^x, e^x, ASIN, ACOS, ATAN, y^x, ABS, OVER, CLR stack
- Keys highlight in amber when SHIFT is active; labels swap to show shifted function
- Shift auto-cancels after one key press; digits also cancel shift

### Changed
- Increased font sizes throughout: key labels, stack display, input line, soft keys
- Soft key row reorganized into two rows to accommodate new buttons
- STO/RCL moved to wider buttons in second soft key row

---

## [1.2.0]

### Fixed
- **Bottom cutoff on Android** — switched from `100vh` to `100dvh` (dynamic viewport height) so the calculator no longer clips behind the Android navigation bar
- Added `padding-bottom: max(20px, env(safe-area-inset-bottom))` as additional safe area fallback
- Added `viewport-fit=cover` meta tag

### Fixed
- **+/- with EEX** — pressing +/- after entering a scientific notation exponent (e.g. `9E8`) now correctly negates the exponent (`9E-8`) rather than the mantissa

---

## [1.1.0]

### Fixed
- **White screen on Android** — removed Google Fonts `@import` which caused Chrome to fail silently when opening the file via `content://` URI
- File is now 100% self-contained with zero external dependencies

---

## [1.0.0] — Initial Release

### Features
- Full RPN 4-level stack with authentic HP 48 behavior
- Stack operations: ENTER, SWAP, DUP, DROP, ROLL, OVER
- Arithmetic: +, −, ×, ÷
- Scientific functions: √x, LOG, LN, SIN, COS, TAN, 1/x, π, +/−, EEX
- Electrical equation soft keys: Xc, XL, fc (RC cutoff), R‖ (parallel resistors)
- Variable storage: STO and RCL with named variables, persistent within session
- Equation confirmation modal showing stack values used before pushing result
- Keyboard input support for desktop use
- Android PWA support (Add to Home Screen)
- Authentic HP 48 visual design with green phosphor screen, CRT scanlines
- Status bar showing angle mode, RPN indicator, SHIFT state
