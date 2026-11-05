---
name: Get to 1 second
description: One kitchen egg timer — hold winds time, release freezes the dial.
colors:
  tomato: "#e23a2e"
  tomato-deep: "#c92218"
  tomato-stem-end: "#a81610"
  tomato-shadow: "#8e1610"
  ground: "#c8d4c0"
  ground-mid: "#dce6d4"
  ground-deep: "#b4c2aa"
  dial: "#f0e6d8"
  dial-light: "#fffaf2"
  dial-shade: "#e2d4c4"
  ink: "#2a2e2c"
  ink-soft: "#3a4338"
  chrome: "#9aa3a8"
  chrome-light: "#efe6da"
  chrome-rim-hi: "#c4cbcf"
  chrome-rim-mid: "#7f878c"
  chrome-rim-lo: "#b8c0c4"
  focus: "#1f6b4a"
  stem-label: "#ffffff"
  selection: "#e23a2e33"
typography:
  display:
    fontFamily: "Bricolage Grotesque, system-ui, sans-serif"
    fontSize: "clamp(3.4rem, 14vw, 5.75rem)"
    fontWeight: 800
    lineHeight: 1
    letterSpacing: "-0.04em"
    fontFeature: "tabular-nums"
  title:
    fontFamily: "Bricolage Grotesque, system-ui, sans-serif"
    fontSize: "clamp(1.15rem, 4.4vw, 1.75rem)"
    fontWeight: 800
    lineHeight: 1.1
    letterSpacing: "-0.03em"
  body:
    fontFamily: "Figtree, system-ui, sans-serif"
    fontSize: "clamp(0.95rem, 2.4vw, 1.125rem)"
    fontWeight: 500
    lineHeight: 1.45
  label:
    fontFamily: "Figtree, system-ui, sans-serif"
    fontSize: "clamp(1.05rem, 2.8vw, 1.2rem)"
    fontWeight: 700
    letterSpacing: "0.06em"
  result:
    fontFamily: "Figtree, system-ui, sans-serif"
    fontSize: "clamp(0.95rem, 2.8vw, 1.1rem)"
    fontWeight: 600
    lineHeight: 1.2
rounded:
  dial: "50%"
  stem: "999px"
  hand: "3px"
  pivot: "50%"
spacing:
  stage-pad: "clamp(1.5rem, 5vw, 3rem)"
  stage-gap: "clamp(1.5rem, 4vh, 2.75rem)"
  dial-size: "min(78vw, 520px)"
  dial-size-mobile: "min(72vw, 300px)"
  rim-inset: "28px"
  face-chrome-ring: "10px"
  stem-height: "4.5rem"
  stem-height-mobile: "3.5rem"
  stem-press: "8px"
  hint-max: "28rem"
components:
  stem:
    backgroundColor: "linear-gradient(180deg, {colors.tomato-deep}, {colors.tomato-stem-end})"
    textColor: "{colors.stem-label}"
    typography: "{typography.label}"
    rounded: "{rounded.stem}"
    padding: "0"
    height: "{spacing.stem-height}"
    width: "min(58%, 220px)"
  stem-hover:
    backgroundColor: "linear-gradient(180deg, {colors.tomato-deep}, {colors.tomato-stem-end})"
    textColor: "{colors.stem-label}"
    rounded: "{rounded.stem}"
  stem-active:
    backgroundColor: "linear-gradient(180deg, {colors.tomato-deep}, {colors.tomato-stem-end})"
    textColor: "{colors.stem-label}"
    rounded: "{rounded.stem}"
    height: "{spacing.stem-height}"
  dial-face:
    backgroundColor: "{colors.dial}"
    textColor: "{colors.ink}"
    rounded: "{rounded.dial}"
    size: "{spacing.dial-size}"
  readout:
    backgroundColor: "transparent"
    textColor: "{colors.ink}"
    typography: "{typography.display}"
  hint:
    backgroundColor: "transparent"
    textColor: "{colors.ink-soft}"
    typography: "{typography.body}"
---

# Design System: Get to 1 second

## Overview

**Creative North Star: "The Kitchen Egg Timer"**

The product is one physical kitchen timer sitting on a soft sage countertop. The viewport is that object: chrome rim, cream enamel face, tomato-red second hand, and a tomato stem you press. Hold winds time; release freezes the dial. Exact 1.000 earns confetti. Everything else is atmosphere around a single circular silhouette.

Personality is playful restraint — enamel and chrome, not neon UI chrome. Density is sparse: title, tabular readout, hand, stem, one hint. The system refuses the centered-title-plus-blue-button microgame template and refuses cards, dashboards, and multi-control layouts.

**Key Characteristics:**
- One circular dial owns the viewport; no cards or side panels
- Soft sage ground, cream enamel face, tomato stem/hand, ink numerals
- Display face Bricolage Grotesque; UI Figtree
- CSS-native materials only (gradients, masks, inset chrome) — no shipping illustration rasters
- Stem is the sole control; hard emboss offset lives only on that control

## Colors

Sage countertop ground, cream enamel dial, tomato accent for the only interactive and timing signals, ink for face type.

### Primary
- **Tomato** (`#e23a2e`): Second hand fill, stem border, win-state emphasis partner, selection tint base. The only loud accent.
- **Tomato Deep** (`#c92218`): Stem gradient start; win readout and result text (AA against cream).
- **Tomato Stem End** (`#a81610`): Stem gradient end — paired with Tomato Deep under a Tomato border for AA label contrast.
- **Tomato Shadow** (`#8e1610`): Stem emboss shelf only.

### Neutral
- **Sage Ground** (`#c8d4c0`): Page field mid-tone.
- **Sage Lift** (`#dce6d4`) / **Sage Depth** (`#b4c2aa`): Radial countertop falloff around the dial.
- **Enamel Dial** (`#f0e6d8`): Face body; **Enamel Light** (`#fffaf2`) and **Enamel Shade** (`#e2d4c4`) form the radial enamel gradient.
- **Ink** (`#2a2e2c`): Title, readout, tick marks.
- **Ink Soft** (`#3a4338`): Hint and result copy at rest.
- **Chrome** (`#9aa3a8`) with rim stops **Chrome Rim Hi/Mid/Lo** (`#c4cbcf` / `#7f878c` / `#b8c0c4`) and **Chrome Light** (`#efe6da`) for the face inset ring.
- **Focus Sage** (`#1f6b4a`): Stem `:focus-visible` outline only.
- **Stem Label** (`#ffffff`): Hold label on tomato stem.
- **Selection Wash** (`#e23a2e33`): Text selection.

### Named Rules
**The One Accent Rule.** Tomato family is reserved for hand, stem, and win feedback. Never recolor ground, enamel, or chrome with tomato fills.

**The Enamel Face Rule.** Face type and ticks stay Ink on cream enamel. Win may deepen readout/result to Tomato Deep; idle never paints the face tomato.

## Typography

**Display Font:** Bricolage Grotesque (with system-ui, sans-serif)
**Body Font:** Figtree (with system-ui, sans-serif)

**Character:** Heavy, slightly condensed display numerals own the face; softer geometric UI type runs the stem label and hint so the dial reads as object, not app chrome.

### Hierarchy
- **Display / Readout** (800, `clamp(3.4rem, 14vw, 5.75rem)`, line-height 1, tracking `-0.04em`, `tabular-nums`): Millisecond clock on the face.
- **Title** (800, `clamp(1.15rem, 4.4vw, 1.75rem)`, line-height 1.1, tracking `-0.03em`): Product name on the dial face.
- **Body / Hint** (500, `clamp(0.95rem, 2.4vw, 1.125rem)`, line-height 1.45): Instruction under the timer; strong ink weight 700 for the `1.000` callout.
- **Label / Stem** (700, `clamp(1.05rem, 2.8vw, 1.2rem)`, tracking `0.06em`, uppercase): Hold control label.
- **Result** (600, `clamp(0.95rem, 2.8vw, 1.1rem)`): Post-release message on the face.

### Named Rules
**The Face Type Rule.** Only Bricolage Grotesque sits on the enamel (title + readout). Figtree never becomes face display type.

**The Tabular Clock Rule.** The readout always uses tabular numerals so digits do not jitter while winding.

## Layout

Centered stage grid: one dial, then one hint. Stage padding `clamp(1.5rem, 5vw, 3rem)` and gap `clamp(1.5rem, 4vh, 2.75rem)`. Dial diameter `min(78vw, 520px)` (mobile `min(72vw, 300px)`). Rim inset leaves a ~14px chrome band; face chrome ring is a 10px inset. Stem hangs below the circle (`bottom: -2.1rem`, mobile `-1.35rem`). Hint max-width `28rem` (mobile `18rem`). Below `480px`, stage content starts near the top with extra bottom padding for the hanging stem.

### Named Rules
**The One Silhouette Rule.** The first viewport is the circular timer plus stem and hint. No cards, stats strips, side panels, or second CTAs.

## Elevation & Depth

Hybrid: soft object shadow on the whole timer mass, inset enamel and chrome on the face, and a physical emboss shelf only on the stem (the wind button).

### Shadow Vocabulary
- **Timer mass** (`filter: drop-shadow(0 28px 48px rgba(40, 50, 40, 0.28))`): Soft sage-tinted ground contact under the dial.
- **Face enamel** (`inset 0 0 0 10px #efe6da, inset 0 0 42px rgba(0,0,0,0.06)`): Chrome-light ring + soft inner shade.
- **Holding halo** (`0 0 0 3px rgba(226, 58, 46, 0.35)`): Added while winding — tomato ring, not a card elevation.
- **Rim metal** (`inset 0 2px 3px rgba(255,255,255,0.45), inset 0 -3px 4px rgba(0,0,0,0.2)`): Chrome bevel.
- **Stem emboss** (`0 10px 0 #8e1610, 0 18px 28px rgba(140, 30, 20, 0.32)` resting; pressed `0 2px 0` + shorter soft shadow): Exclusive to the Hold stem.
- **Hand halo** (`0 0 0 2px rgb(255 250 242 / 0.45)` plus pivot ring `0 0 0 3px #fffaf2`): Keeps the hand readable on enamel.

### Named Rules
**The Stem-Only Emboss Rule.** Hard offset shadow is native to the tomato stem as a physical wind button. Do not apply hard offset shelves to the dial, hint, or future surfaces.

**The Soft Dial Rule.** The circular mass lifts with a soft drop-shadow and inset chrome, never a card box-shadow or floating panel.

## Shapes

Geometry is circular-first. Dial, rim, face, ticks mask, and hand pivot are full circles (`50%`). Stem is a stadium pill (`999px`). Hand shaft uses a 3px radius. Tick marks are a masked repeating-conic ring — part of the egg-timer object, not decorative stripes elsewhere.

### Named Rules
**The Circle Owns the Page Rule.** New UI that is not the stem must defer to the circular dial silhouette; rectangular cards and inset media frames are out of world.

## Components

### Stem (Hold control)
Tactile tomato wind stem — the only button.
- **Shape:** Pill (`999px`); width `min(58%, 220px)` (mobile `min(72%, 200px)`); height `4.5rem` / `3.5rem`
- **Primary:** Vertical gradient `#c92218 → #a81610`, `2px` Tomato border, white uppercase Figtree label, emboss shelf `#8e1610`
- **Hover:** Slight brightness lift (`filter: brightness(1.04)`)
- **Active / Holding:** Translate down `8px`, emboss collapses to `2px` shelf
- **Focus:** `3px` Focus Sage outline, `4px` offset

### Dial / Timer (signature)
CSS-native kitchen timer object.
- **Rim:** Circular metal gradient (`#c4cbcf → #7f878c → #b8c0c4`) with inset bevel
- **Face:** Enamel radial (`#fffaf2 → #f0e6d8 → #e2d4c4`) with chrome-light inset ring
- **Ticks:** Ink repeating-conic marks, masked to an outer ring, idle opacity `0.45`; holding chases with a 1s linear nudge
- **Hand:** Tomato shaft + pivot; idle opacity `0.55`, full opacity while holding or on win
- **States:** `idle` / `holding` (scale `1.018` + tomato halo) / `win` (`win-pop` scale pulse; readout/result → Tomato Deep)
- **Motion:** Ease `cubic-bezier(0.16, 1, 0.3, 1)`; respect `prefers-reduced-motion` by killing transitions/animations

### Readout
- Centered tabular Bricolage Grotesque clock; scales subtly via `--readout-scale` while winding

### Hint
- Figtree body under the object; Ink Soft with Ink strong on the `1.000` target

### Cards / Containers
- **None.** Do not introduce card chrome.

### Inputs / Fields / Navigation / Chips
- **None** in the shipped build. Future surfaces should invent from tokens, not from a second control language.

## Do's and Don'ts

### Do:
- **Do** keep one circular timer as the first-viewport composition (dial + stem + hint).
- **Do** use Tomato only for hand, stem, holding halo, and win feedback.
- **Do** set face display type in Bricolage Grotesque with tabular numerals on the readout.
- **Do** build materials with CSS gradients, masks, and inset chrome — no shipping illustration rasters for the dial.
- **Do** reserve hard emboss offset for the stem control.
- **Do** honor `prefers-reduced-motion` by removing timer/stem/readout motion.

### Don't:
- **Don't** ship a centered-title-plus-blue-button microgame layout.
- **Don't** introduce cards, dashboards, icon rows, or secondary CTAs.
- **Don't** put Figtree on the enamel as display type, or Bricolage on the stem label.
- **Don't** flood the sage ground with tomato fills or purple/glow UI tropes.
- **Don't** treat review screenshots under `.impeccable/review/` as shipping brand assets.
