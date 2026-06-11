# ImageGen Asset Manifest

Production assets use the **Current Folk** storybook-electromechanical direction.

## Camera Rule

All gameplay racers are shown from directly behind, moving straight away from the player. Side and three-quarter animation sheets are rejected for runtime use.

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

The matching chroma-key masters are retained under `assets/sprites/source/`.
Character atlases are integrated into gameplay. The obstacle atlas is production-ready reference material; hazards remain procedural until its silhouettes are individually cut and collision-matched.

## Concept References

- `assets/concepts/noderunner-lineup.png`
- `assets/concepts/noderunner-3000-penguin-direction.png`
- `assets/concepts/electromechanical-world-direction.png`

## Generation

The assets were generated with the built-in ImageGen tool. Chroma-key backgrounds were removed locally with the Codex ImageGen skill's `remove_chroma_key.py` helper.
