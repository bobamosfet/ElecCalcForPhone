# HP 48 G+ Simulator — Quick Reference

## RPN Basics

| To do this... | Do this... |
|---------------|------------|
| Enter a number | Type digits, then ENTER |
| Enter negative | Type digits, press +/- |
| Enter scientific notation | Type mantissa, EEX, type exponent |
| Negate exponent | Press +/- after EEX |
| Calculate 3 + 4 | `3 ENTER 4 +` |
| Calculate 3 × (4 + 5) | `4 ENTER 5 + 3 ×` |
| Duplicate top of stack | DUP |
| Swap top two values | SWAP |
| Discard top value | DROP |
| Clear entire stack | SHIFT + DROP |

---

## Electrical Equations — Stack Setup

```
┌─────────────────────────────────────────────────────┐
│  Equation   │  Level 2 (enter first)  │  Level 1    │
├─────────────┼─────────────────────────┼─────────────┤
│  Xc         │  f  (Hz)                │  C  (F)     │
│  XL         │  f  (Hz)                │  L  (H)     │
│  fc         │  R  (Ω)                 │  C  (F)     │
│  R‖         │  R1 (Ω)                 │  R2 (Ω)     │
│  LC         │  L  (H)                 │  C  (F)     │
└─────────────┴─────────────────────────┴─────────────┘
```

---

## SHIFT Functions

Press **SHIFT** first, then the key:

| Key | Shifted Function |
|-----|-----------------|
| √x | x² |
| LOG | 10^x |
| LN | e^x |
| SIN | ASIN |
| COS | ACOS |
| TAN | ATAN |
| 1/x | y^x |
| +/- | ABS |
| SWAP | OVER |
| DROP | Clear stack |

---

## Common Workflows

**Ohm's Law (V = IR) — solve for V:**
```
Enter R  →  ENTER  →  Enter I  →  ×
```

**Two resistors in parallel, then series with a third:**
```
R1 ENTER  R2  R‖        ← get parallel result
R3 ENTER  SWAP  +        ← add R3 in series
```

**Capacitive reactance at 1kHz, 100nF:**
```
1000  ENTER           ← f = 1 kHz
100  EEX  9  +/-      ← C = 100 nF (1e-7 F)
[tap Xc]
```

**LC resonance for 10μH, 100pF:**
```
10  EEX  6  +/-       ← L = 10 μH
100  EEX  12  +/-     ← C = 100 pF
[tap LC]
```

**Store a result and reuse it:**
```
[calculate something]
[tap STO →]  →  type name e.g. "VOUT"  →  STO
[later: tap ← RCL  →  tap VOUT in list]
```

---

## Angle Mode

- Tap the **RAD/DEG** button (top row, far right) to toggle
- **RAD** = blue/grey button, status bar shows RAD
- **DEG** = amber button, status bar shows DEG
- Affects: SIN, COS, TAN, ASIN, ACOS, ATAN

---

## Unit Prefixes (for EEX entry)

| Prefix | Symbol | Exponent |
|--------|--------|----------|
| pico   | p      | EEX 12 +/- |
| nano   | n      | EEX 9 +/-  |
| micro  | μ      | EEX 6 +/-  |
| milli  | m      | EEX 3 +/-  |
| kilo   | k      | EEX 3      |
| mega   | M      | EEX 6      |
| giga   | G      | EEX 9      |
