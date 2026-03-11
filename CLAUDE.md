# CLAUDE.md

## Project Overview

Static web project containing two standalone HTML5 applications:

1. **Portfolio Website** (`index.html` + `style.css`) — French-language personal portfolio template with About, Projects, and Contact sections.
2. **N64-Style 3D Game** (`game.html`) — "Échos du Passé", a Zelda-inspired third-person adventure prototype built with Three.js. Self-contained single file with inline CSS and JavaScript.

## Project Structure

```
index.html    # Portfolio landing page
style.css     # Styles for the portfolio
game.html     # 3D game prototype (self-contained: HTML + CSS + JS)
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

## Language & Conventions

- **Content language**: French (UI text, comments, variable names like `goronGroup`, `checkInteraction`, `showDialogue`).
- **Code style**: Vanilla JavaScript (ES6+), 4-space indentation, no framework.
- **HTML**: Semantic HTML5 (`<header>`, `<main>`, `<section>`, `<footer>`), `lang="fr"`.
- **CSS**: Flexbox layout, BEM-inspired IDs/classes (e.g., `#hud-top`, `#dialogue-box`, `.heart`).
- **Game architecture**: Single-file with functional style — game state in top-level variables, `requestAnimationFrame` loop, keyboard/mouse event listeners, Pointer Lock API for camera.

## Git Conventions

- Commit messages in French.
- Branch naming: `claude/<feature-description>`.
