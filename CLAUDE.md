# CLAUDE.md

## Project Overview

Static web project containing two standalone HTML5 applications:

1. **Portfolio Website** (`index.html` + `style.css`) — French-language personal portfolio template with About, Projects, and Contact sections.
2. **N64-Style 3D Game** (`game.html`) — "Échos du Passé", a Zelda-inspired third-person adventure prototype built with Three.js. Self-contained single file with inline CSS and JavaScript.

## Project Structure

```
index.html    # Portfolio landing page (46 lines)
style.css     # Styles for the portfolio (67 lines)
game.html     # 3D game prototype, self-contained HTML + CSS + JS (404 lines)
```

No build system, no package manager, no bundler. Files run directly in a modern browser (Chrome/Firefox with WebGL support).

## External Dependencies

- **Three.js r128** — loaded via CDN in `game.html`: `https://cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.min.js`
- No npm packages or local dependencies.

## Development Workflow

- **Run**: Open `index.html` or `game.html` directly in a browser, or use any local static server.
- **No build step** required.
- **No tests** — manual browser testing only.
- **No linter or formatter** configured.
- **No CI/CD** pipelines.

## Portfolio Website

Simple French-language template with placeholder content:

- **Header**: `[Votre Nom]` title, subtitle "Développeur Web | Designer | Créateur"
- **Sections**: `#a-propos` (About), `#projets` (3 placeholder project cards using `.projet` class)
- **Footer**: Contact email link (`votre.email@example.com`)
- **CSS**: System font stack (`-apple-system, ...`), card-style sections with `border-radius: 8px` and `box-shadow`, centered `max-width: 800px` layout.

## Game Architecture

### Three.js Setup

- **Scene**: Sky blue background (`0x87CEEB`), linear fog near=10 far=60.
- **Camera**: `PerspectiveCamera` (75 FOV), orbits player at 10-unit distance, 5-unit height, with lerp smoothing (factor 0.1). Vertical rotation clamped to ±0.5 rad.
- **Renderer**: `WebGLRenderer` with antialiasing disabled (retro look), shadow mapping enabled. Responsive resize handler.
- **Lighting**: Ambient light (0.6 intensity) + directional light (0.8 intensity) at position (50, 100, 50) with 50x50 orthographic shadow camera.

### Game State

Single `gameState` object tracks all flags:

```
canMove: boolean        // Player movement and camera input enabled
dialogueOpen: boolean   // Dialogue box currently visible
questStarted: boolean   // Goron quest initiated
hasSword: boolean       // Kokiri Sword acquired from chest
```

Input flags: `moveForward`, `moveBackward`, `moveLeft`, `moveRight`. Camera angles: `rotX`, `rotY`.

### Key Functions

| Function | Purpose |
|----------|---------|
| `createTree(x, z)` | Generates low-poly tree (cylinder trunk + cone foliage) |
| `attack()` | 10-frame sword swing animation, disables movement during attack |
| `checkInteraction()` | Distance-based proximity check for NPCs (<4 units) and items (<3 units) |
| `showDialogue(speaker, text)` | Displays dialogue box, pauses movement |
| `closeDialogue()` | Closes dialogue, resumes control |
| `animate()` | Main `requestAnimationFrame` loop — movement, camera, rendering |

### Controls

| Input | Action |
|-------|--------|
| W/Z or Arrow Up | Move forward (camera-relative) |
| A/Q or Arrow Left | Strafe left |
| S or Arrow Down | Move backward |
| D or Arrow Right | Strafe right |
| E | Interact / close dialogue |
| Mouse move | Camera orbit (requires Pointer Lock) |
| Left click | Attack (when sword acquired) |
| Click canvas | Activates Pointer Lock for mouse look |

ZQSD layout supports French AZERTY keyboards.

### Environment

- **Ground**: 200x200 unit flat plane with grass material (`0x4caf50`).
- **Trees**: 40 procedurally placed low-poly trees, excluded from central 20-unit radius.
- **NPC**: Goron (dodecahedron mesh) at position (10, 0, -10) with breathing animation (`rotation.z = sin(time) * 0.05`).
- **Item**: Golden chest at (-15, 0.5, -5) containing "Épée Kokiri". Disappears on collection.

### Game Flow

```
Spawn at (0, 0, 0)
  → Explore procedural forest
  → Talk to Goron (quest starts, told to find sword)
  → Find golden chest at (-15, 0.5, -5)
  → Collect Kokiri Sword (chest disappears, sword visible on player)
  → Talk to Goron again (different dialogue, mentions Forest Temple)
  → Attack enabled via left-click
```

### Visual Effects

- **Scanlines**: CSS overlay with semi-transparent horizontal lines at 4px intervals (CRT aesthetic).
- **Fog**: Linear distance fog matches sky color, hides draw distance (N64 style).
- **Low-poly**: Minimal vertex counts, no antialiasing, intentionally chunky geometry.
- **Shadows**: Directional light casts shadows; ground receives, player and Goron cast.

### HUD Elements

- **Hearts**: 3 CSS-styled hearts (top-left), decorative only (no damage system).
- **Interaction prompt**: "Appuyez sur E pour interagir" shown near interactive objects.
- **Dialogue box**: 80%-width box at bottom center with speaker name and text.
- **Controls hint**: Bottom-right, always visible, lists key bindings.

## Language & Conventions

- **Content language**: French (UI text, dialogue, comments).
- **Code style**: Vanilla JavaScript (ES6+), 4-space indentation, no framework.
- **Naming**: Mix of French game terms (`goronGroup`, `showDialogue`) and English code patterns.
- **HTML**: Semantic HTML5 (`<header>`, `<main>`, `<section>`, `<footer>`), `lang="fr"`.
- **CSS**: Flexbox layout, BEM-inspired IDs/classes (e.g., `#hud-top`, `#dialogue-box`, `.heart`).
- **Game file**: Single-file architecture — all CSS and JS inline in `game.html`.

## Git Conventions

- Commit messages in French.
- Branch naming: `claude/<feature-description>`.
