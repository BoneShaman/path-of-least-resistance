# ImageGen Asset Manifest

Production assets use the **Current Folk** storybook-electromechanical direction.

## Camera Rule

All gameplay racers are shown from directly behind, moving straight away from the player. Side and three-quarter animation sheets are rejected for runtime use.

UI contexts use front-facing model art: briefing portraits, the shared race timeline, and OHM puzzle terminals. Rear-facing art is reserved for physical raceway movement.

## Runtime Atlases

- `assets/sprites/runtime/noderunner-3000-actions.png`
  - 4 columns x 3 rows
  - Row 1: run cycle
  - Row 2: jump and belly-slide
  - Row 3: hurt and victory
- `assets/sprites/runtime/noderunner-1000-actions.png`
  - 4 columns x 2 rows
  - Row 1: run cycle
  - Row 2: jump and belly-slide
- `assets/sprites/runtime/rivals-run.png`
  - 4 columns x 3 rows
  - Rows: Noderunner 3200, 3600, 4000
- `assets/sprites/runtime/electromechanical-obstacles.png`
  - 4 columns x 2 rows
  - Barriers, duck gate, blocker, pickup, OHM Gate, and relay props
- `assets/sprites/runtime/clear-slide-gate.png`
  - Dedicated empty raised crossbar for belly-slide hazards
  - Replaces the hanging-duck gate art
  - Matching chroma master: `assets/sprites/source/clear-slide-gate-chroma.png`
- `assets/sprites/runtime/clinger-actions.png`
  - 2 columns x 2 rows
  - Warning descent, attached hover, shake reaction, and broken spin-away
  - Matching chroma master: `assets/sprites/source/clinger-actions-chroma.png`

The matching chroma-key masters are retained under `assets/sprites/source/`.
Character atlases are integrated into gameplay. The obstacle atlas supplies the jump barrier, blocker, spark pickup, and OHM Gate; the dedicated clear gate supplies slide hazards. The Clinger sheet supplies the rare magnetic pursuit hazard introduced in the second duel. Procedural glow, shadows, and action prompts preserve collision readability.

## Backgrounds

- `assets/backgrounds/nodewazzle-raceway-title.png`
  - Title-screen key art
  - Low-opacity race-world layer behind the procedural track
  - Centered direct-forward wire perspective with title-safe sky

## Concept References

- `assets/concepts/noderunner-lineup.png`
- `assets/concepts/noderunner-3000-penguin-direction.png`
- `assets/concepts/electromechanical-world-direction.png`

## Generation

The assets were generated with the built-in ImageGen tool. Chroma-key backgrounds were removed locally with the Codex ImageGen skill's `remove_chroma_key.py` helper.
