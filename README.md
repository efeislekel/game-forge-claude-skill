# Game Forge: Claude Skill for Three.js Browser Game Development

[![Latest release](https://img.shields.io/github/v/release/efeislekel/game-forge-claude-skill?label=release)](https://github.com/efeislekel/game-forge-claude-skill/releases/latest) [![Downloads](https://img.shields.io/github/downloads/efeislekel/game-forge-claude-skill/total?label=downloads)](https://github.com/efeislekel/game-forge-claude-skill/releases) [![GitHub stars](https://img.shields.io/github/stars/efeislekel/game-forge-claude-skill?style=flat&label=stars)](https://github.com/efeislekel/game-forge-claude-skill/stargazers) [![License: MIT + Apache-2.0](https://img.shields.io/badge/license-MIT%20%2B%20Apache--2.0-blue)](NOTICE)

**Game Forge** is an all-in-one [Claude Skill](https://docs.claude.com/en/docs/agents-and-tools/agent-skills/overview) (Agent Skill, `SKILL.md` format) that turns Claude into a game development partner for **Three.js browser games**, **WebGL games** and **2D / top-down web games**. One skill, fourteen specialist modules: premium graphics, gameplay systems, game feel, game UI, camera systems, level design, procedural generation, enemy AI, save systems, performance optimization, debugging and release QA.

Install it once and Claude picks the right module automatically when you ask things like *"make my game's graphics premium"*, *"the shooting doesn't feel punchy"*, *"my game drops to 30 FPS"* or *"generate a dungeon map"*.

Works in **claude.ai**, **Claude Code** and other agents that support the Agent Skills standard.

---

## Why Game Forge?

Separate game dev skills compete with each other and with your other installed skills. Game Forge bundles the best of two popular open-source skill collections behind a single router `SKILL.md`, so:

- **One install, one name.** No overlapping skills fighting to trigger.
- **Loads only what is needed.** The router reads one or two module files per request, keeping context small.
- **Nothing cut.** Every module keeps its full instructions, references, scripts and the Three.js + Vite starter template.
- **No API keys required.** Works fully with procedural models, materials and audio.

## What's inside: 14 modules

### Three.js modules

| Module | What it does |
| --- | --- |
| `threejs-game-director` | Entry point for building, upgrading, polishing or shipping a whole Three.js game; routes work across modules |
| `threejs-gameplay-systems` | Core loop, controls, camera, collision, physics, scoring, levels, Vite + TypeScript starter scaffold |
| `threejs-aaa-graphics-builder` | Premium / AAA browser graphics: PBR materials, lighting, shaders, VFX, LOD, instancing, 10-category visual scorecard |
| `threejs-game-ui-designer` | HUDs, menus, pause/win/lose screens, touch controls, responsive game UI |
| `threejs-debug-profiler` | Blank canvas fixes, render bugs, draw calls, triangles, memory and bundle profiling |
| `threejs-qa-release` | Browser QA, Playwright bot playtests, canvas pixel checks, production builds, release reports |

### Engine-neutral game design modules (2D or 3D, any engine)

| Module | What it does |
| --- | --- |
| `game-feel` | Juice: screen shake, hit-stop, easing, squash and stretch, knockback, layered feedback |
| `performance-optimization` | Frame budget, CPU vs GPU bottlenecks, object pooling, batching, GC spikes |
| `camera-systems` | 2D follow with deadzone and look-ahead, 3D orbit, first-person look, camera shake |
| `game-ui-ux` | HUD and menu architecture, safe areas, scaling, menu state stack, event-driven HUD |
| `level-design` | Blockout to playable, pacing and flow, critical path, encounter design |
| `procedural-gen` | Seeded RNG, Perlin / Simplex noise terrain, dungeon generation, wave function collapse, loot tables |
| `game-ai` | Enemy and NPC AI: finite state machines, behavior trees, steering, A* pathfinding |
| `save-systems` | Save / load, save slots, autosave, crash-safe writes, save versioning and migration |

## Installation

### claude.ai (no coding needed)

1. Download **[game-forge.zip](https://github.com/efeislekel/game-forge-claude-skill/releases/latest/download/game-forge.zip)** (always the latest version).
2. In claude.ai, open Settings and go to the Skills section.
3. Upload `game-forge.zip`. Keep it as a zip, do not extract it.

### Claude Code

```bash
npx skills add efeislekel/game-forge-claude-skill -a claude-code
```

Or copy the skill folder manually:

```bash
git clone https://github.com/efeislekel/game-forge-claude-skill.git
cp -r game-forge-claude-skill/skills/game-forge ~/.claude/skills/
```

## Example prompts

- "Make my Three.js idle RPG's graphics premium. Score the current look first."
- "Add game feel to the sword hits: hit-stop, screen shake and knockback."
- "My browser game stutters on mobile. Find out why."
- "Build a top-down camera that follows the car with look-ahead."
- "Design a save system with 3 slots and autosave."
- "Generate a procedural dungeon with rooms and corridors."
- "Write enemy AI that patrols, chases and returns home."

## Repository structure

```
game-forge-claude-skill/
└── skills/game-forge/
    ├── SKILL.md                # router: picks the right module
    ├── modules/<module>/
    │   ├── MODULE.md           # module instructions
    │   ├── references/         # deep-dive guides
    │   ├── scripts/            # helper scripts (some modules)
    │   └── assets/             # templates and anchors (some modules)
    └── licenses/
```

## Credits and licenses

Game Forge is a curated bundle. Module content comes from these open-source projects and is otherwise unchanged:

- **Three.js modules:** [threejs-game-skills](https://github.com/majidmanzarpour/threejs-game-skills) by Majid Manzarpour, MIT License.
- **Engine-neutral modules:** [awesome-gamedev-agent-skills](https://github.com/gamedev-skills/awesome-gamedev-agent-skills) by gamedev-skills, Apache License 2.0.

Changes made for this bundle: each original `SKILL.md` was renamed to `MODULE.md` with a short header, Codex-only `agents/` files and the three paid-API asset generator skills were left out, and a router `SKILL.md` was added. Full license texts are in [`skills/game-forge/licenses`](./skills/game-forge/licenses). See [NOTICE](./NOTICE).

Bundled by [Anemon Creative](https://anemoncreative.com).

---

## Türkçe

**Game Forge**, Three.js ile tarayıcı oyunu yapanlar için hazırlanmış hepsi bir arada bir Claude skill'idir. Tek skill içinde 14 modül var: premium grafik, oynanış sistemleri, oyun hissi, oyun arayüzü, kamera, bölüm tasarımı, prosedürel harita üretimi, düşman yapay zekası, kayıt sistemi, performans, hata ayıklama ve yayın öncesi test.

**Kurulum (claude.ai):** [game-forge.zip](https://github.com/efeislekel/game-forge-claude-skill/releases/latest/download/game-forge.zip) dosyasını indir, claude.ai ayarlarındaki Skills bölümünden zip olarak yükle. Kod bilgisi gerekmez.

Kurduktan sonra "oyunumun grafiklerini premium yap", "vuruşlar daha tok hissettirsin" ya da "oyun kasıyor, neden?" gibi isteklerde Claude doğru modülü kendisi seçer.

---

**Keywords:** Claude skill, Claude Skills, Agent Skills, SKILL.md, Claude Code skill, Anthropic, Three.js game development, threejs game, WebGL game, browser game, HTML5 game, JavaScript game, TypeScript game, Vite, game design, game feel, game juice, procedural generation, game AI, behavior tree, A* pathfinding, game UI, HUD, level design, game optimization, AI game development.
