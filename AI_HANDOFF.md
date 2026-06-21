# SJ Applied Tech Tycoon - AI Handoff

## Current Version

v4.3 GitHub upload package

## Core Direction

Korean manufacturing survival tycoon.

The game is about surviving as a small manufacturing company under cashflow pressure.

Visual tone:

- Cute cat, dog, and owl workers
- Bright, readable UI
- Korean industrial manufacturing background
- Black-comedy survival pressure
- Not pure joy; the main emotion is responsibility, pressure, and small relief

## Game Structure

The game uses a four-room visit structure.

Rooms:

1. 현장
   - MCT
   - CNC
   - laser
   - tools
   - machined parts

2. 조립실
   - SMT screen printer assembly
   - 36-unit batch
   - frame assembly
   - internal assembly and PLC
   - idle run

3. 사무실
   - cash
   - accounts receivable
   - accounts payable
   - debt
   - burn rate
   - pressure
   - bank / supplier / legal decisions

4. 설계실
   - CAD
   - drawings
   - PLC
   - design standardization
   - future improvements

## Core Layout

Desktop:

- Top: resource strip
- Left: room navigation and survival actions
- Center: current room full-screen
- Right: room stats and investments

Mobile target:

- Top: compact resource strip
- Center: current room image
- Bottom: room navigation, actions, and upgrades

## Assembly System

Total: 36 machines.

Batch structure:

- Batch 1: frame assembly, 12 units
- Batch 2: internal assembly and PLC, 12 units
- Batch 3: idle run, 12 units

When all 36 units are complete:

- Ship batch
- Increase receivables
- Slightly improve reputation
- Reduce pressure
- Start next 36-unit batch

## Emotional Roles

- 현장 = tension
- 조립실 = visible progress
- 사무실 = fear and responsibility
- 설계실 = hope and future improvement

The game should feel like:

> I cannot fix everything, but I can survive today.

## Current Known Issues

- Character animation is fake motion only.
- Best future setup is character-free room backgrounds plus separate transparent character sprites.
- Some raw/experimental AI assets may not be final-release safe.
- Mobile layout needs further tuning.
- `index.html` is still a single large file. Later it should be split into JS/CSS/data modules.

## Design Decisions

- Do not return to one giant company map.
- Use four full-screen rooms instead.
- Keep UI bright because the subject matter is already heavy.
- Use cute animals to soften the pressure, not to remove it.
- Left side is for room visits and survival actions.
- Right side is for the current room's stats and investments.
- Top bar is for resources and time.

## Next Tasks

1. Verify image loading on desktop and mobile.
2. Improve mobile layout.
3. Separate room backgrounds from character sprites.
4. Add better character animation.
5. Improve 36-unit assembly progress feedback.
6. Crop and assign action icons properly.
7. Add office/design room-specific gameplay.
8. Split index into modular source files when the prototype stabilizes.

## Asset Notes

Current asset paths used by `index.html`:

```text
assets/rooms/field.png
assets/rooms/assembly.png
assets/rooms/office.png
assets/rooms/design.png
assets/characters/cat.png
assets/characters/dog.png
assets/characters/owl.png
assets/icons/*.png
```

Future room backgrounds should ideally have no characters. Characters should be transparent PNG or sprite sheets.

## Do Not Change

- Cute animal workers
- Korean small manufacturing company feeling
- MCT/CNC + SMT screen printer company identity
- Survival pressure + black-comedy tone
- Four-room visit structure
