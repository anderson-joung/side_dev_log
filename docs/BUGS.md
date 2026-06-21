# Bugs

## Active

- Mobile layout needs more testing.
- Character animation is not true sprite animation yet.
- Some room images may still need compression for faster loading.
- Some generated images contain baked-in characters, which limits future animation.
- `index.html` is still monolithic and will become harder to maintain as content grows.

## Fixed

### v4.2

- Fixed broken image paths.
- Fixed flickering caused by repeated image reload behavior.
- Connected room images to actual asset files.

### v4.3 Package

- Organized asset paths and patched references.
