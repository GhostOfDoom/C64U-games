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
- The user's view: most authors tolerate fan-made YouTube videos if they're not sold, don't give the whole story away,
  and don't put the text up on screen.

## Possible direction: the real Brothers Grimm (raised 2026-11-02, NOT decided)
- Retell old fairy tales the way they were originally told: grim, nasty, evil. Not the Disney versions.
- Example: Aschenputtel (Cinderella). One stepsister cuts off her toe and the other her heel to fit the
  slipper (golden in the Grimm version, not glass). Birds give the game away ("blood in the shoe"),
  and at the wedding the doves peck out the sisters' eyes.
- The Grimm tales (1812-1857 editions) are **public domain**, so they're safe to use.
- Watch out for:
  - **Disney's own designs** (e.g. Cinderella's blue dress, the Fairy Godmother, Bibbidi-Bobbidi-Boo).
    The Grimm version doesn't even have a fairy godmother; it has a hazel tree on her mother's grave and birds.
  - **Modern translations** can be copyrighted. Work from the original German or old public-domain
    translations, or write our own retelling.
- Fits the dark, painterly C64 art style in the reference images.
