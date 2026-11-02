# C64 Art & Dev Notes

Read this before any C64 work. Add to it whenever new reference images or guidance arrive.

## Working agreement
- The user is the architect and I'm the builder.
- Process: user brings a game idea → we discuss what it has to do → agree the design → then build. Don't dump loads of code up front.
- Games are original designs or genre games, not copies of specific existing titles.

## Hardware constraints (graphics)
- Fixed 16-colour palette: black, white, red, cyan, purple, green, blue, yellow,
  orange, brown, light red, dark grey, mid grey, light green, light blue, light grey.
- Multicolor bitmap: 160x200 wide pixels. Each 4x8 cell = 1 shared background colour + 3 colours of its own.
- Hires bitmap: 320x200. Each 8x8 cell = 2 colours.
- Colour changes follow the cell grid, so plan artwork around it.

## Batch 1: reference art (5 images, 2026-11-02)
Subjects: plumber/ape platform homage, wraith + circuit board, woman + skull,
gorilla with curly hair, screaming split face.

Techniques seen:
- **Brightness ramps:** e.g. black → brown → red → light red → pink → yellow → white;
  black → blue → purple → light blue → cyan → white.
- **Dithering:** checkerboard/ordered patterns blend neighbouring ramp colours
  (cheeks, fur, fades into backgrounds).
- **Hue shifting:** shadows go cool (blue/purple), highlights go warm (yellow/pink).
- **Black outlines and solid black areas** keep shapes readable.
- **Composition:** large focal face with high contrast; the brightest highlights are on the eyes.
- **Horizontal colour bands/stripes** in backgrounds match the cell grid well.
- **Thin grid-aligned linework** (circuit board) can look detailed with only 2-3 colours.

## Open questions
- "Nodes" = C64 Dev Machine nodes. See C64_DEV_MACHINE.md.
