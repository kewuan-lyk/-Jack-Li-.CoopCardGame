# Sonar Diver

This repository currently contains the first browser-based map prototype for **Sonar Diver**.

## Run the Prototype

Open `index.html` in a web browser, then use **WASD** or the **arrow keys** to move through the basin. Browser audio begins after the first click or keypress.

No installation, package manager, or local server is required.

## Current Features

- A procedurally generated 52-by-48 underwater basin with a camera that follows the player
- Smooth player movement
- Collision with the rocky boundary and up to 23 randomized reef formations
- Open loops and gaps around reefs that can be used to evade monsters
- Deep-water lighting, drifting particles, seabed details, and a submarine player
- A visible water surface, sunlight beams, rising bubbles, and progressive darkness while descending
- An on-screen depth meter that reinforces downward exploration
- Near-total darkness beginning at a depth of 10 meters, with a small local light around the submarine
- An expanding sonar pulse activated with Space, a 1.5-second cooldown, and temporary terrain reveals
- Layered animated deep-sea fog with drifting density, irregular visibility edges, and glowing multi-ring sonar waves
- A rolling, uneven seafloor instead of a straight bottom boundary
- A rescue beacon positioned in the deep central basin rather than a fixed corner
- One test creature that hears every sonar pulse, pathfinds to its source, and searches several nearby positions for seven seconds
- Sonar propagation made from reflected rays that bounce from reefs and reveal their reflected paths
- A second, purple hunter creature that continuously pathfinds toward the submarine at a much slower speed
- A locked rescue beacon that requires an access key placed at a random valid location each run
- A temporary yellow sonar arrow that points toward the key with an intentional 8–22 degree error and never shows distance
- A new map, rolling seafloor, reef layout, exit, key, and monster placement after every restart
- Procedural urgent background music generated in the browser; press M to mute it
- Large squid and shark silhouettes for the two monster types
- Victory at the green rescue beacon, defeat on monster contact, and restart with R
- A clearly marked green rescue beacon

## Current Objective

Find the randomized access key, then reach the rescue beacon without touching either monster. The red giant squid investigates every sonar source and searches nearby; the slower shark continuously tracks the submarine.

The map is generated near the top of `game.js`. Each generated character represents one tile:

- `#` — wall
- `.` — open floor
- `P` — player starting position
- `E` — exit
