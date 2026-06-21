# Asset Notes

## Main Game Asset Paths

The current `index.html` expects these paths:

```text
assets/rooms/field.png
assets/rooms/assembly.png
assets/rooms/office.png
assets/rooms/design.png
assets/characters/cat.png
assets/characters/dog.png
assets/characters/owl.png
assets/icons/*.png
assets/machines/*.png
```

## Future Asset Direction

For animation, generate room backgrounds without characters.

Recommended future split:

```text
room background = no characters
character = transparent PNG or sprite sheet
effect = separate transparent PNG / CSS / canvas layer
```

## Room Backgrounds

Current rooms:

- `assets/rooms/field.png`
- `assets/rooms/assembly.png`
- `assets/rooms/office.png`
- `assets/rooms/design.png`

## Character Sprites

Current characters are static transparent PNGs:

- `assets/characters/cat.png`
- `assets/characters/dog.png`
- `assets/characters/owl.png`

Current animation is fake motion only.

Future sprite sheet needs:

- idle 4 frames
- work 6 frames
- walk 6 frames
- tired 4 frames
- alert 3 frames

## Release Warning

Some raw/generated AI assets may require re-generation or rights review before public release.
