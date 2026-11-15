# Subway Corridor + Basement

A small browser-based first-person experience built with **Three.js** (r160).
You wake up in a grimy subway corridor, shoot out the lights, smash the
control-room glass, and walk to the green door at the far end — where a
basement armory is waiting.

Everything you see is generated at runtime. **There are no image files, no
models, no audio files and no build step** — one HTML file, one CDN import map,
and a lot of `canvas.getContext('2d')`.

> ⚠️ Contains flickering lights, sudden loud noises and a train that does not
> stop. Headphones recommended, motion sensitivity advised.

---

## ✨ Features

**Environment**
- 60-unit subway corridor with tiled walls, graffiti, tactile floor paving,
  hazard-striped pillars, cable trays and pipework
- Ceiling fluorescents with shadow casting, plus one light that never stops
  flickering
- Turnstiles, benches, vending machine, wall clock, ticket machine, recycling
  bins, fire extinguisher, wet-floor signs, puddles, litter, newspapers
- Live departure board that re-renders its canvas every second
- Steam vent with drifting sprite steam, floating dust motes, and a rat that
  scurries along the left wall
- A **platform kiosk** built into the wall — counter, shelving, signage,
  security grilles and its own interior light

**Interactive**
- **Breakable control-room glass** — 1st and 2nd hit add procedural crack
  decals, 3rd hit shatters into 70 physics-driven shards
- **Train pass-by event** every 25–35 s: Web Audio low rumble, camera shake,
  and the corridor lights strobe out
- Blocked stairwell with a locked gate and cold blue light spilling down
- Green door at the end of the corridor opens into the **basement**: concrete
  walls, crates, barrels, pipes, a ladder — and a weapon cache with a
  hand-modelled rifle and pistol

**Rendering**
- Procedural bump maps and roughness maps derived from the generated colour
  textures (wet patches on the floor actually read as wet)
- PCF soft shadows, exponential fog, ACES filmic tone mapping
- Post-processing chain wired up (`EffectComposer` / `RenderPass` /
  `ShaderPass` / `OutputPass`)

**HUD**
- Ammo counter, crosshair, contextual hints (e.g. “press E”)

---

## 🎮 Controls

### Desktop
| Input | Action |
|---|---|
| `W A S D` | Move |
| Mouse | Look |
| `E` | Open / close door |
| Left click | Shoot |
| `R` | Reload |
| `F` | Toggle flashlight |
| Click | Enter (pointer lock) |

### Mobile
Touch build uses **dual on-screen sticks** plus on-screen buttons:

| Input | Action |
|---|---|
| Left thumbstick | Move |
| Right drag | Look |
| Fire button | Shoot |
| Reload / Flashlight / Interact buttons | Same as desktop keys |

*(Adjust the table above to match your actual mobile control layout.)*

---

## 🚀 Running it

No install, no bundler:

```bash
git clone https://github.com/<you>/<repo>.git
cd <repo>
# just open the file, or serve it if your browser complains about modules:
python3 -m http.server 8000
