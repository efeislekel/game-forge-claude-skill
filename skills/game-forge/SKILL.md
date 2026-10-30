---
name: game-forge
description: All-in-one game development toolkit for browser games, built around Three.js but with engine-neutral craft for 2D and top-down games too. Use for building, upgrading, polishing, debugging or shipping a game, and for any of these game topics - premium/AAA or less-basic graphics, materials, lighting, shaders, VFX, render budget; gameplay systems, core loop, controls, physics, collision, scoring; game feel and juice, screen shake, hit-stop, easing; cameras (follow, deadzone, orbit, first-person); HUD, menus, pause and settings screens, touch UI, responsive layout; level design, blockout, pacing, encounters; procedural generation, noise, dungeons, loot tables; enemy and NPC AI, state machines, behavior trees, pathfinding; save/load and autosave; low FPS, stutter, draw calls, profiling, blank canvas or render bugs; browser QA, playtests, production builds and release checks.
---

# Game Forge

One skill, fourteen specialist modules. This file is only a router: read it, pick the modules the request needs, then read those modules' `MODULE.md` files and follow them.

## How to use the modules

- Each module lives in `modules/<module-name>/`. Its instructions are in `modules/<module-name>/MODULE.md`. Paths a module mentions (`references/...`, `scripts/...`, `assets/...`) are relative to that module's own folder.
- The Three.js modules were written as separate sibling skills. Wherever a module says to read another skill such as `threejs-gameplay-systems`, `../<skill>/SKILL.md`, or `<threejs-...-skill-dir>`, use `modules/<that-name>/MODULE.md` and `modules/<that-name>/` instead.
- Load only what the request needs. A narrow edit loads one or two modules; a whole-game build or a broad upgrade starts with the director.
- The project's own style, scope and earlier decisions always win over module defaults.

## Not included: external asset generators

The original pack also had Tripo (3D), Gemini (image) and ElevenLabs (audio) generator skills that need paid API keys. They are not part of Game Forge. When a module calls for `threejs-3d-generator`, `threejs-image-generator` or `threejs-audio-generator`, or tells you to run a credential probe, treat those as unavailable: use procedural models, materials and audio from the modules, or the user's other 3D tools (Blender or Meshy skills) if they ask for them. Do not block on missing keys.

## Routing table

### Three.js modules

| Request is about | Module |
| --- | --- |
| Whole game: build, upgrade, polish or ship; anything spanning several areas below | `threejs-game-director` (start here, it routes the rest) |
| Design brief, core loop, entities, input, camera, physics, scoring, levels in a Three.js game; new Vite/TypeScript scaffold | `threejs-gameplay-systems` |
| Graphics look basic; premium/AAA visuals, materials, lighting, shaders, VFX, LOD/instancing, the 10-category visual scorecard | `threejs-aaa-graphics-builder` |
| HUD, menus, overlays, win/lose screens, touch UI, typography in a Three.js game | `threejs-game-ui-designer` |
| Blank canvas, render or runtime bugs, loading, mobile input, profiling draw calls/triangles/memory | `threejs-debug-profiler` |
| Browser QA, screenshots, bot playtests, production build, hosting base paths, release risk | `threejs-qa-release` |

### Engine-neutral craft modules (any engine, 2D or 3D)

| Request is about | Module |
| --- | --- |
| Juice: screen shake, hit-stop, easing, squash and stretch, knockback, impact feedback | `game-feel` |
| Low FPS, stutter, GC spikes, object pooling, batching, frame budget | `performance-optimization` |
| Camera follow, deadzone, look-ahead, smoothing, bounds, orbit, first-person look | `camera-systems` |
| HUD and menu architecture, scaling, safe areas, menu state stack, event-driven HUD | `game-ui-ux` |
| Level layout, blockout, pacing, critical path, encounter design | `level-design` |
| Seeded RNG, noise terrain, dungeon generation, wave function collapse, loot tables | `procedural-gen` |
| Enemy/NPC AI: state machines, behavior trees, steering, A* pathfinding | `game-ai` |
| Save/load, save slots, autosave, versioning old saves | `save-systems` |

### Common pairings

- Three.js game feels flat: `threejs-gameplay-systems` plus `game-feel`.
- Three.js game runs slow: `threejs-debug-profiler` plus `performance-optimization`.
- Game UI in Three.js: `threejs-game-ui-designer` for look and layout, `game-ui-ux` for menu flow and state wiring.
- A non-Three.js game (canvas 2D, Phaser, Pixi): use the engine-neutral modules and apply them to that engine's APIs.

## Credits

Three.js modules: threejs-game-skills by Majid Manzarpour (MIT License). Engine-neutral modules: awesome-gamedev-agent-skills by gamedev-skills (Apache License 2.0). Combined into Game Forge with module wrappers; module content is otherwise unchanged.
