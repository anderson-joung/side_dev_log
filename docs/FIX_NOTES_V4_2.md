# SJ Applied Tech Tycoon v4.2 Hotfix

## Fixed
- Corrected broken image path references from v3.
- Added four full-screen room background assets:
  - `assets/room_field.png`
  - `assets/room_assembly.png`
  - `assets/room_office.png`
  - `assets/room_design.png`
- Disabled the image-opacity preload bug that made backgrounds appear blank/flicker.
- Reduced full DOM rebuild frequency so room backgrounds do not reload every simulated hour.
- Added lightweight CSS character motion using existing cat/dog/owl sprites.

## Character motion scope
This version uses simple UI-level animation:
- idle bobbing
- slight walking drift
- inspection bobbing

For production-quality movement, the next asset requirement is a sprite sheet for each worker:
- idle 4 frames
- walk 6 frames
- work 6 frames
- panic/tired 4 frames
