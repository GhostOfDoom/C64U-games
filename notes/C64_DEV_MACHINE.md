# C64 Dev Machine: how it works

"Nodes" = **C64 Dev Machine** by Polytricity, a visual node-based tool for building C64 software.
- Download/changelog: https://polytricity.itch.io/the-c64-dev-machine
- Windows and macOS. Paid Pro version plus a free Lite build. Uses the VICE emulator to run builds.
- Code is built from connected nodes; each node maps to a 6502 machine instruction.
  "Macros" are bigger ready-made blocks (e.g. Bitmap Macro, sound effects, collision).
- Sprite editing goes through SPRED64 (Pro, v086_A and above).
- The project changes quickly, so check the changelog before assuming a feature is there or missing.

The user builds in Dev Machine, so I design and plan to fit it (node logic, memory layout, assets).
I can't run Dev Machine from the cloud container.

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

## To fill in
- The user's message was cut off at "...straight bitmaps or quad". Ask what the other modes are.
- Bitmap mode used (multicolor or hires?), piece sizes, how pieces are positioned (cell coordinates?).
- Where screen RAM and colour data go for the $4000 bitmap.
