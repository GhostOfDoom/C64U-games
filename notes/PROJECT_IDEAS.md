# Project ideas

## Idea 1: forest path perspective showcase (2026-11-02)
An animation showcase (more about looking amazing than gameplay) to see what we can push the C64 to do.

- Scene: a painterly, almost watercolour bitmap of a **path leading off into a forest**.
  The path recedes into the distance instead of running straight up/down the screen.
- A character (or carriage) walks down the path and **gets smaller and smaller** (depth frames, see
  C64_DEV_MACHINE.md) until they reach the edge, then the screen **blinks to the next map**.
- Masking so the character can pass behind trees.
- Doesn't need to be one program on one REU: it can be split into several parts/scenes and
  joined together in editing.
- Recording: **OBS Studio** capture → edit in **DaVinci Resolve**.
- Output **1080p** is plenty. The C64 picture is 320x200 (384x272 with the border), so higher video resolution adds nothing.
  Tip: scale by whole numbers with nearest-neighbour (e.g. x3 → 1152x816 centred in 1080p, or x4 with the border cropped)
  so the pixels stay sharp and even.
- Built with nodes first (see THE RULE in C64_DEV_MACHINE.md).
