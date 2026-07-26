# BangFX — 2D Impact FX Playground

A standalone, single-file playground for prototyping hand-drawn-style 2D impact FX
(Spider-Verse / anime FX language) without knowing how to draw. Aimed at compers and
3D artists: you throw gestures, the tool supplies the shape language and timing.

**Run it:** open `index.html` in any modern browser. No build, no dependencies.

## What it does

- **Four archetypes** — impact **Burst**, smoke **Poof**, speed **Lines** (draw the
  arc yourself), and **Spark**. Each is a procedural generator, not a stock clip.
- **Timing grammar baked in** — every effect runs anticipation → white flash frame →
  peak → breakup/decay, held on 1s/2s/3s exposure at 24 fps. This is the part that
  usually requires an FX animator's instincts; here it's the default.
- **Inherent line boil** — every held drawing re-jitters its vertices from a
  per-drawing seed, so elements feel drawn, not tweened.
- **Gesture input** — drag on the plate: position, direction, and drag length drive
  placement, orientation bias, and scale. For Lines, your stroke *is* the path.
- **Seeded variation** — same recipe + same seed = same frames. Reroll for a fresh
  take that keeps the art direction.
- **Export** — transparent sprite-sheet PNG (one cell per drawing) named with the
  recipe (`bangfx_burst_1234_8dwg_on2s.png`), plus a copy-paste JSON recipe for
  sharing setups.

## Controls

| Control | Effect |
|---|---|
| Drag on plate | Spawn the current archetype |
| Energy / Detail / Jag | Scale, spike-or-cell count, edge roughness |
| Drawings / Exposure | Length of the lifecycle and hold (1s/2s/3s) |
| Flash frame / Debris | Toggle the white hit frame and particle pass |
| Seed / ⚄ | Deterministic reroll |
| Plate | Grey plate, dark, alpha checker, or painterly "shot" preview |
| Space / ← → | Play-pause, step a drawing at a time |
| Bottom ruler | X-sheet view of the lifecycle; scrub it |

## Why this shape of tool

Studying FX breakdowns (e.g. Nikolaos Finizio's *Across the Spider-Verse* elements),
the craft splits into silhouette language, timing grammar, and hand energy. Only the
first traditionally needs draftsmanship — and it parameterizes well. This prototype
tests the thesis that if the timing grammar ships as the default, non-drawers can get
convincing elements in seconds.

Next steps if the prototype earns it: PNG-sequence export with proper naming for
Nuke/AE, per-archetype extra knobs, palette editing, importing a hero frame,
and a Nuke gizmo / AE plugin port of the same generators.
