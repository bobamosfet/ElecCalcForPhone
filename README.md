# HP 48 G+ Simulator

A faithful simulation of the HP 48 G+ calculator, built as a self-contained HTML file that runs in any modern browser — no installation, no server, no dependencies.

Designed specifically for Android use with a built-in set of electrical engineering equations.

![HP 48 G+ Simulator](screenshot.png)

---

## Features

- **Full RPN stack** — 4-level stack display (levels 1–4) with authentic HP behavior
- **SHIFT key** — press once to access secondary functions shown in amber on each key
- **Electrical engineering equations** — one-tap calculations using stack values
- **RAD/DEG toggle** — switch angle modes; all trig functions update automatically
- **Variable storage** — store and recall named variables (STO/RCL)
- **EEX input** — scientific notation entry (e.g. `1.5E-9`)
- **Works offline** — single HTML file, zero external dependencies
- **Android PWA** — add to home screen and use like a native app

---

## Installation on Android

1. Download `hp48-calculator.html` to your Android device
2. Open **Chrome** and navigate to `chrome://downloads`
3. Tap the file to open it
4. Tap the **⋮ menu → Add to Home Screen**
5. The app will appear on your home screen and work fully offline

> **Tip:** Always open via Chrome's download manager (`chrome://downloads`) rather than Samsung My Files or another file manager. Opening via `content://` URIs can cause a slow white-screen load.

---

## How to Use RPN

RPN (Reverse Polish Notation) means you enter operands *before* the operator.

**Example: 3 + 4**
```
3  →  ENTER
4  →  +
Result: 7
```

**Example: (3 + 4) × 2**
```
3  →  ENTER
4  →  +
2  →  ×
Result: 14
```

Values accumulate on the stack. The stack levels are labeled 1 (bottom/active) through 4 (top).

---

## Key Reference

### Function Keys (Row 1)

| Key | Normal | SHIFT |
|-----|--------|-------|
| √x | Square root | x² (square) |
| LOG | Log base 10 | 10^x |
| LN | Natural log | e^x |
| SIN | Sine | ASIN |
| COS | Cosine | ACOS |
| TAN | Tangent | ATAN |

### Utility Keys (Row 2)

| Key | Normal | SHIFT |
|-----|--------|-------|
| 1/x | Reciprocal | y^x (power) |
| π | Push π | — |
| SWAP | Swap levels 1 & 2 | OVER (copy level 2 to top) |
| +/- | Change sign / negate exponent | ABS (absolute value) |
| EEX | Enter scientific notation exponent | ENG mode |
| DROP | Drop level 1 from stack | CLR (clear entire stack) |

### Stack Operations

| Key | Action |
|-----|--------|
| ENTER | Push input to stack (or duplicate level 1 if no input) |
| SWAP | Swap levels 1 and 2 |
| DUP | Duplicate level 1 |
| DROP | Remove level 1 |
| ⌫ (BKSP) | Delete last digit, or drop level 1 if no input |

### Using SHIFT

1. Press **SHIFT** — the button glows amber and key labels change to their shifted function
2. Press any key to execute its shifted function
3. SHIFT cancels automatically after one key press
4. Pressing a digit while SHIFT is active cancels SHIFT

---

## Electrical Equations

All equations use values already on the stack. Enter values in the order shown, then tap the equation button. A confirmation screen shows the values used before pushing the result.

### Xc — Capacitive Reactance
```
Formula:  Xc = 1 / (2π × f × C)
Level 2:  f  (frequency in Hz)
Level 1:  C  (capacitance in Farads)
Result:   Xc (reactance in Ω)
```

### XL — Inductive Reactance
```
Formula:  XL = 2π × f × L
Level 2:  f  (frequency in Hz)
Level 1:  L  (inductance in Henries)
Result:   XL (reactance in Ω)
```

### fc — RC Filter Cutoff Frequency
```
Formula:  fc = 1 / (2π × R × C)
Level 2:  R  (resistance in Ω)
Level 1:  C  (capacitance in Farads)
Result:   fc (cutoff frequency in Hz)
```

### R‖ — Resistors in Parallel
```
Formula:  R‖ = (R1 × R2) / (R1 + R2)
Level 2:  R1 (first resistor in Ω)
Level 1:  R2 (second resistor in Ω)
Result:   R‖ (parallel resistance in Ω)
```
> For more than two resistors, run R‖ repeatedly — each result becomes the new R1.

### LC — LC Resonance Frequency
```
Formula:  f = 1 / (2π × √(L × C))
Level 2:  L  (inductance in Henries)
Level 1:  C  (capacitance in Farads)
Result:   f  (resonant frequency in Hz)
```

---

## Variable Storage (STO / RCL)

1. Calculate or enter a value — it stays on the stack at level 1
2. Tap **STO →** to open the store panel
3. Type a name (up to 6 characters) and tap **STO →**
4. To recall, tap **← RCL**, type the name or tap it in the list

Variables persist for the current browser session. Stored variables appear in the list and can be tapped to recall or deleted with ✕.

---

## Angle Mode (RAD / DEG)

- The **RAD/DEG** button is in the top-right of the soft key row
- Default is **RAD** (radians) — button shows in blue/grey
- Tap to switch to **DEG** (degrees) — button glows amber
- The status bar in the screen updates to reflect the current mode
- All trig functions (SIN, COS, TAN, ASIN, ACOS, ATAN) use the selected mode

---

## EEX / Scientific Notation

To enter `1.5 × 10⁻⁹`:
```
1 . 5  →  EEX  →  9  →  +/-
Display: 1.5E-9
```

The **+/-** key toggles the sign of the exponent when in EEX mode, and toggles the sign of the mantissa otherwise.

---

## Technical Details

| Property | Value |
|----------|-------|
| Format | Single self-contained HTML file |
| Dependencies | None — no external fonts, scripts, or stylesheets |
| Browser support | Chrome 80+, Firefox 75+, Safari 13+ |
| Angle default | Radians |
| Number precision | 10 significant figures |
| Stack depth | Unlimited (displays top 4 levels) |
| Variable storage | Session-scoped (cleared on page reload) |

---

## File Structure

```
hp48-calculator.html    # The entire application — HTML, CSS, and JS in one file
README.md               # This file
USAGE.md                # Quick reference card
CHANGELOG.md            # Version history
```

---

## License

MIT License — free to use, modify, and distribute.
