# SJ Applied Tech Tycoon v4 - Mobile / Animation Notes

## Why v3 images blinked
The v3 index referenced asset filenames that did not exist in the project folder, and the main room image was recreated as an `<img>` tag every game-hour render. At faster time speeds this looked like image blinking or broken image flashing.

v4 fixes both:

- all image references now point to existing files under `assets/`
- room backgrounds are applied as stable CSS backgrounds on `#roomStage`
- static room images are no longer recreated as `<img>` elements on every time tick
- missing icons were created or aliased from the provided icon sheets

## Character motion model
Current v4 uses light CSS motion:

- cat: small bob / machine-work motion
- dog: slow side-to-side work/cart motion
- owl: small inspect/look motion

This is not full character animation. It is a cheap but effective prototype layer. For commercial-grade motion, the game needs separate transparent sprite sheets:

- idle: 4 frames
- walk: 6 to 8 frames
- work/tooling: 6 frames
- tired/stress: 3 to 4 frames
- accident/alert reaction: 3 frames

Each character should be exported as transparent PNG sequences or a single sprite sheet.

## Recommended mobile layout
Mobile should not keep the desktop three-column layout.

Portrait phone layout:

1. Top sticky status area
   - date/time
   - survival days
   - cash, AR, AP, debt, burn, pressure in two-column cards
   - speed/pause buttons

2. Main room view
   - one full-screen-ish room panel
   - 60% of viewport height
   - no right/left rails over the image

3. Room visit tabs
   - four compact buttons: 현장 / 조립실 / 사무실 / 설계실
   - icon + short label only

4. Survival action grid
   - two columns
   - short action names only

5. Current room investment panel
   - stacked cards below actions

This preserves the core loop while reducing visual fatigue.

## Four-room content direction

### 현장
MCT/CNC/laser room. Emotion: pressure, machine utilization, safety.

### 조립실
36-unit SMT screen printer assembly. Emotion: visible progress and satisfaction.

### 사무실
Cashflow war room. Emotion: responsibility and organized fear.

### 설계실
CAD, PLC, standardization, fixtures. Emotion: today's loss for tomorrow's improvement.
