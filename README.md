# Mochi-Puff — 3D GPU Fur Simulation

Interactive 3D fur physics and hair shading simulation for a stylized creature,
rendered in real time with WebGL2 / GPGPU. A second scene — the GPU Grass
Painter — simulates thousands of wind-blown grass blades.

## What it does

- **GPGPU fur physics** — every fur strand is simulated on the GPU (gravity,
  wind, collisions, and spring-back), so thousands of strands move smoothly in
  real time.
- **Marschner hair shading** — physically-inspired hair lighting with
  primary/secondary highlights for soft, believable fur.
- **Mochi-Puff, the creature** — a stylized blob creature you can orbit, poke,
  and restyle: fur length, density, curl, colour, wind, and lighting are all
  adjustable from the control panel.
- **Three environments** — studio, nature, and live AR camera (your webcam
  becomes the backdrop).
- **GPU Grass Painter** — paint fields of grass that bend and ripple in the
  wind (`grass.html`).

## Tech

- Three.js (WebGL2), Vite, React
- GPGPU simulation via floating-point render targets
- Custom GLSL shaders (`src/furShaders.js`, `src/grassShaders.js`)
- Plain Node static server (`server.js`) for the production build

## Run locally

Prerequisites: Node.js 18+.

```bash
npm install
npm run dev        # → http://localhost:3000
```

No API key is required — the simulation runs fully in the browser.

## Build & serve the production bundle

```bash
npm run build      # outputs to dist/
npm start          # serves dist/ on http://localhost:3000
```

## Project layout

| Path | What it is |
| --- | --- |
| `index.html` | Mochi-Puff fur simulation entry |
| `grass.html` | GPU Grass Painter entry |
| `src/main.js` | Fur scene bootstrap |
| `src/grassMain.js` | Grass scene bootstrap |
| `src/furSystem.js` | Fur strand system |
| `src/gpuPhysics.js` | GPGPU physics step |
| `src/furShaders.js` / `src/grassShaders.js` | GLSL shaders |
| `src/blobCreature.js` | The creature mesh |
| `src/environments.js` | Studio / nature / AR environments |
| `src/ui.js` / `src/grassUI.js` | Control panels |
| `server.js` | Static file server for the production build |

## Origin

Exported from Google AI Studio and published here with a rewritten README,
MIT licence, and `.gitignore`. The original AI Studio app link is recorded in
`metadata.json`.

## Licence

MIT — see [LICENSE](LICENSE).
