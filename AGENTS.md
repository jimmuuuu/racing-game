# BRAINROT RACING

A self-contained 3D kart racing game built with raw WebGL. There is no build system, no package manager, and no external runtime dependencies — everything (HTML, CSS, JS, WebGL shaders) is inlined in single HTML files.

- `index.html` — the main game (menu, character/track select, 3D race). This is the file to develop and test.
- `kart3d.html` — an alternate/older standalone version of the game.
- `launcher.html` — a thin loader that fetches the latest `index.html` from GitHub at runtime (used to distribute the game without re-saving); not needed for local development.

## Cursor Cloud specific instructions

- There is nothing to install or build. To develop/test, serve the repo root over HTTP and open the page in a browser. Any static file server works, e.g. `python3 -m http.server 8000`, then open `http://localhost:8000/index.html`.
- Do NOT open the file via `file://` — the game and (for `launcher.html`) `fetch()` behave best over HTTP.
- There is no lint or automated test suite. "Testing" means manually playing the game in a WebGL-capable browser: from the menu, START RACE → pick a character → NEXT → pick a track → START RACE, then drive with Arrow keys (Up = accelerate, Left/Right = steer, Space = drift/brake). Verify the 3D canvas renders and the kart moves with a live HUD (speed, lap, position, timer, minimap).
- `launcher.html` is hardcoded to fetch `index.html` from the `claude/sleepy-bell-2z5nua` branch on GitHub; it requires internet access and reflects the published branch, not your local edits. Test local changes via `index.html` directly.
