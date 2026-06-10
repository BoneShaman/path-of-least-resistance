# The Path of Least Resistance

A heartfelt four-button arcade puzzle-racer about an obsolete mechanical penguin proving that kindness is not a legacy defect.

![Noderunner 3000 direction](assets/concepts/noderunner-3000-penguin-direction.png)

## What I Made

You play as Noderunner 3000, an older wire-running machine whose job was taken by faster and increasingly hostile successor models.

Each duel alternates between:

- High-pressure three-lane running
- Jumping, lane dodging, and electrical belly-slides
- Chainable Flow speed boosts
- Competitive shortest-path sliding puzzles
- Three race arcs against a physical rival

The complete campaign faces Noderunners `3200`, `3400`, `3600`, `3800`, and `4000`. Winning is not about destroying them. It is about reconnecting the kindness their optimization removed.

## Play

The game runs locally without a build step:

```bash
python3 -m http.server 8000
```

Then open [http://localhost:8000](http://localhost:8000).

## Controls

| Action | Keyboard |
| --- | --- |
| Move left | `Left Arrow` or `A` |
| Move right | `Right Arrow` or `D` |
| Jump | `Up Arrow` or `W` |
| Belly-slide | `Down Arrow` or `S` |
| Move puzzle tiles | The same four directions |
| Fullscreen | `F` |
| Mute | Music button |

Touch controls are included for mobile play.

## Flow

Clean actions build a Flow chain:

- Jumping barriers
- Belly-sliding under gates
- Collecting sparks
- Passing close to lane blockers

Flow temporarily raises speed. Continue moving cleanly to preserve it. A collision breaks the chain.

## OHM Gate Assistance

Each puzzle is generated from a known breadth-first-search distance from the solved state.

If a player is stuck:

- At 10 seconds, the first optimal tile is highlighted and numbered `1`.
- At 15 seconds, the next valid tile is numbered `2`.
- At 20 seconds, the final hint is numbered `3`.

Hints recalculate against the current board and never reveal more than one new move at a time.

## How Codex Helped

Project scaffold was done in ChatGPT, and then moved to Codex. Codex was used as a design, implementation, testing, and release collaborator.

It helped:

- Translate the original four-button concept into a playable game loop
- Build deterministic, solvable OHM Gate puzzles using breadth-first search
- Implement rival racing and parallel puzzle timing
- Tune obstacle readability, tutorial timing, Flow chaining, and failure recovery
- Integrate music and state-based audio
- Add deterministic game-state and time-stepping hooks for automated playtesting
- Inspect screenshots and gameplay state with Playwright
- Develop the original mechanical-penguin art direction
- Prepare repository documentation and deployment

See [DEVELOPMENT_HISTORY.md](DEVELOPMENT_HISTORY.md) for the original concept and iteration trail.

## Music

- `Brass for Baxter` - menu and introduction
- `Burnout Line` - tutorial
- `Noderunner 3000` - races
- `Circuit Shuffle` - OHM Gate puzzles
- `Circuit Shuffle 2` - between rounds

## Visual Direction

The production direction is storybook electromechanics: worn enamel, porcelain, copper, relay towers, glass current, and an expressive mechanical penguin whose signature move is a sparking belly-slide.

See [ART_DIRECTION.md](ART_DIRECTION.md).

## Technical Notes

- Single-page HTML, CSS, Canvas, and JavaScript
- No framework or build system
- Works as a static GitHub Pages site
- Procedural Web Audio effects plus supplied music tracks
- Local progress saved with `localStorage`
- `window.render_game_to_text()` exposes concise game state for testing
- `window.advanceTime(ms)` enables deterministic simulation
