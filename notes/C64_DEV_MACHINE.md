# C64 Dev Machine: how it works

"Nodes" = **C64 Dev Machine** by Polytricity, a visual node-based tool for building C64 software.
- Download/changelog: https://polytricity.itch.io/the-c64-dev-machine
- Windows and macOS. Paid Pro version plus a free Lite build. Uses the VICE emulator to run builds.
- Code is built from connected nodes; each node maps to a 6502 machine instruction.
  "Macros" are bigger ready-made blocks (e.g. Bitmap Macro, sound effects, collision).
- Sprite editing goes through SPRED64 (Pro, v086_A and above).
- The project changes quickly, so check the changelog before assuming a feature is there or missing.

- **ADAM** is the Amiga version of the same tool. We're using the C64 Dev Machine.
- **Claude can work with Dev Machine through an MCP connection**: write code blocks into it and pull nodes from it.
  It has been done in earlier sessions. (It wasn't connected in the 2026-11-02 session, which was fine for planning.)

## THE RULE: nodes first
- Build everything with Dev Machine **nodes**. Almost everything can be turned into nodes.
- Use a **code block** only for the few things that genuinely can't be done as nodes.
- Never code-block the whole thing just because it's easier. "What's the point in having Dev Machine
  if you're not going to use the nodes? It's like having a car and walking to work."
- So: learn the nodes, how they work, and which ones exist. Record them here as we go.

## Bitmap Builder: building screens from chunks (from the user, 2026-11-02)
Same idea as The Last Ninja: the screen is built from pieces
(load a tree, then a bit of path, then something else) rather than stored as one whole picture per screen.

- Uses **two bitmaps**:
  1. **Atlas bitmap** at **$8000**: holds all the image pieces (trees, paths, rocks...).
     It's never displayed; it's the parts bin.
  2. **Main display bitmap** at **$4000**: what the player sees.
- Pieces are cut from the atlas and pasted where they're wanted on the main bitmap.
- Dev Machine **always** uses these addresses: atlas $8000, display $4000. It doesn't do it any other way.
- My reading of why: $4000 is the start of VIC bank 1 ($4000-$7FFF), so the display bitmap
  and its screen/colour data live in the bank the VIC chip shows. $8000 is outside that bank,
  so the atlas is just stored data that gets copied from.
- Why it matters: many screens from one set of pieces = far less memory than full pictures per screen.
- Atlas pieces should line up with the 8x8 cell grid (4x8 wide pixels in multicolor),
  because colours are stored per cell. A piece's colour data must be copied with its pixels.

## Art direction: push the limits
- Not flat "it's a dungeon wall" screens. The goal is beautiful, almost **watercolour-style** bitmap scenes
  (see the reference art in C64_ART_NOTES.md).
- **Perspective by shrinking sprites:** the player character gets smaller as they walk "into" the picture,
  e.g. down a path into the distance.
  How (from the user): the hardware can't shrink a sprite, so **draw the smaller sizes as extra animation frames**.
  We know the depth (screen Y position / path position), so pick the frame set for that depth.
  - Works the same with 1, 2 or 4 sprites per character: a big character made of several sprites,
    or stacked layers (e.g. extra colour/outline overlays). Every layer swaps to its matching depth frame.
  - Plan: a depth table (screen Y -> size set), with each size set holding the full walk cycle.
    The far sizes may need fewer sprites (e.g. 4 near, 2 mid, 1 far), which frees sprites for other things.
- **Masking:** the character can walk behind things (trees, pillars) cheaply.
  Options to explore: sprite-behind-background priority, a mask from the atlas, or overlay sprites.
  Find out which way Dev Machine does it.

## To fill in
- An earlier message ended "...But it comes a bit just straight bitmaps or quad". Was that about other bitmap modes/layouts?
- Bitmap mode used (multicolor or hires?), piece sizes, how pieces are positioned (cell coordinates?).
- Where screen RAM and colour data go for the $4000 bitmap.
