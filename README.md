# 🧬 Neon Cells

*Game of Life with neon glow. Watch patterns evolve, draw your own cells, tweak rules, pick palettes. Hypnotic pattern generator.*

---

## What is this?

Conway's Game of Life, but glowy. A grid of cells lives and dies by simple rules, creating emergent patterns that evolve over generations. Neon Cells adds a cyberpunk aesthetic: glowing cells, smooth rendering, multiple color palettes, and different rule sets (HighLife, Seeds, Maze). Click and drag to draw cells. Adjust speed. Watch gliders blink across the screen. It's cellular automata as a visual toy.

---

## Features

- **Classic Game of Life** — B3/S23 rule (birth on 3 neighbors, survive on 2–3)
- **Alternative rules:** HighLife (B3/S23 + B6), Seeds (B2), Maze (B3/S12345)
- **Neon aesthetics** — glowing cells with shadow blur, dark background
- **Multiple palettes:** Cyber (cyan/pink), Inferno (red/orange), Matrix (greens), Ocean (blues), Rainbow (cycling), Monochrome
- **Interactive drawing** — click/drag to add or erase cells
- **Speed control** — Slow/Normal/Fast/Ultra
- **Density presets** — Sparse/Medium/Dense/Full Random initial patterns
- **Stats display** — generation count, population, FPS
- **Keyboard shortcuts** — Space = pause, C = clear, R = randomize
- **Touch support** — draw on mobile
- **Single HTML file** — pure canvas, no dependencies

---

## How to Use

1. Open `index.html`
2. The simulation runs automatically (paused by default? Actually it starts running)
3. **Draw:** click or drag on grid to add cells (or erase if starting on existing cell)
4. **Speed:** use dropdown to change evolution speed
5. **Palette:** change color scheme for different vibes
6. **Density:** randomize new boards with varying initial randomness
7. **Rules:** switch to different cellular automaton rule sets
8. **Clear:** wipe grid, start fresh
9. **Random:** populate randomly with current density

---

## Rules Explained

- **Conway (Classic):** Live cell with 2–3 neighbors survives; dead cell with exactly 3 neighbors becomes alive. Produces gliders, blinkers, still lifes.
- **HighLife:** Like Conway but also births on 6 neighbors. Supports replicators.
- **Seeds:** Only births on exactly 2 neighbors, no survival. Explosive, chaotic growth.
- **Maze:** Survives with 1–5 neighbors, births on 3. Creates mazelike structures.

---

## Technical Notes

- Grid: 100×75 cells (800×600 canvas, 8px cells)
- Toroidal topology: edges wrap around (modular arithmetic)
- Double buffering: `grid` and `nextGrid` swapped each generation
- Counting neighbors: 3×3 kernel excluding center
- Rendering: each cell drawn with `fillRect`, alive cells have `shadowBlur` for glow
- Rainbow palette uses HSL with time-based hue cycling
- Speed controlled by `setTimeout` / `requestAnimationFrame` delta threshold
- Touch events map to grid coordinates

---

## The Real Story

Cellular automata are fascinating: simple rules yield complex behavior. Game of Life is the iconic one — you can build computers in it. I wanted a visually appealing implementation that doesn't take itself too seriously. The neon glow makes it feel like a screensaver from a cyberpunk future. The ability to draw your own patterns lets you play "God" with glowing cells. Different rule sets change the entire personality of the simulation.

Also: gliders are cool.

---

*Made with ✨ and some serious cellular curiosity during a heartbeat build cycle.*

**Repo:** https://github.com/Kiloooai/neon-cells
