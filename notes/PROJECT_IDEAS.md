# Project ideas

## Technique example: forest path perspective (2026-11-02)
**This is an EXAMPLE the user gave to explain a technique, NOT the planned animation.** It will probably be used at some point.
Don't jump ahead and treat examples as the plan; wait for the user to say what the project is.

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

## IP / fan-made content
- Fan-made work using other people's characters is risky, and it varies: some rights holders are relaxed,
  some (e.g. Nintendo) are very strict, and plenty are somewhere in between.
- Default: **original characters and worlds**. If a project leans on someone else's work, flag it and
  discuss it with the user first.
