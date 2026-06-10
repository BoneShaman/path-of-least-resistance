# Development History

This document preserves the creator-supplied origin prompt and condenses the major design iterations that produced the playable game.

## Original Concept Prompt

> I want the simplest most beautifully elegant and simple game that requires, left right up and down.
>
> You are Noderunner 3000, and you're goal is to be the smartest and fastest wire runner planet Nodewazzle has ever seen.
>
> You are determined. To defeat Noderunner 4000 who took your job as the node running puzzle solving system on planet Nodewazzle.
>
> You've been training hard and will show people that the old model is superior to the new one. Why did you have a pure heart, yet all the versions after you get meaner and meaner to their prior Noderunner versions.
>
> All the versions before you loved you and you loved them. So you must do it for the Noderunners or their sparks will die out.
>
> In this classic bird on a wire style node runner game, you dodge, jump and speed to the finish line against a treacherous 5 foes in races with 3 arcs.
>
> Run, jump, dodge the spark snuffers which make you dizzy and slow you down.
>
> Face off against the 5 Noderunner versions after you. Noderunner 3200, 3400, 3600, 3800 and 4000.
>
> Teach them to be nice by snuffing their soldering butts.
>
> At each leg of the race you will solve a sliding puzzle. Where you have a certain about of Electric Node Juice.
>
> You do a sliding pipe puzzle and the fluid pours in. It is a Dykstra style shortest path. You've got exactly enough juice to solve each one.
>
> Then you run.
>
> Run, solve, run, solve, run, solve.
>
> Welcome to The Path of Least Resistance.
>
> Fun, whacky, heartfelt. Incredibly simple to understand, play, and scale in your skills.

## Design Evolution

### Core Loop

The first playable build established the rhythm:

`run -> dodge -> solve -> surge -> run`

It included lane switching, jumping, ducking, three arcs, spark snuffers, OHM Gate puzzles, and a rival moving through the same race structure.

### Puzzle Integrity

The puzzle generator moved from loose scrambling to breadth-first-search frontier selection. Every board begins at a known legal distance from the goal, so difficulty and available Electric Node Juice can be controlled precisely.

Early opponents receive shallower puzzles and reserve juice. Later opponents require exact shortest-path solutions.

### Running Readability

Hazards developed distinct physical grammar:

- Full block: change lanes
- Low barrier: jump
- High gate: duck or belly-slide
- Spark: collect for recovery and speed

Ground shadows, action cues, obstacle silhouettes, and removal of passed hazards make decisions readable at speed.

### Physical Rival

The opponent evolved from a progress bar into a visible runner that:

- Changes lanes
- Jumps
- Ducks
- Chases and passes the player
- Enters a physical puzzle terminal
- Solves the same starting puzzle through a legal shortest path
- Charges and departs before counting as escaped

### Spark Heart

Noderunner 3000 carries three visible sparks. Collisions permanently dim them for the current run. The final loss causes a physical collapse rather than an abstract game-over counter.

### Tutorial

Noderunner 1000 demonstrates:

1. Move left
2. Move right
3. Jump
4. Duck or belly-slide
5. Collect a spark
6. Solve a one-move OHM Gate

The complete teaching sequence remains, but travel and demonstration delays were compressed for competition pacing.

### Flow Pressure

Regular races were made denser and faster. Consecutive clean actions now build Flow, creating a temporary speed advantage and a reason to keep moving precisely.

### Progressive Assistance

Puzzle guidance now escalates at 10, 15, and 20 seconds. Each revealed shortest-path move is numbered directly on the relevant tile, keeping the race moving without replacing player control.

### Music and Presentation

Five supplied tracks now follow the game state: menu, tutorial, race, puzzle, and between-round scenes.

The new art direction rejects generic neon mascot styling in favor of a handmade electrical world and a repaired mechanical penguin protagonist. See [ART_DIRECTION.md](ART_DIRECTION.md).

## Codex Attribution

The creator-provided project history describes the original implementation and iteration work as being completed with ChatGPT and then moved into Codex once a basic scaffold was completed.
