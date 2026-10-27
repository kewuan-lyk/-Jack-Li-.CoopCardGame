1. Game Introduction

Sonar Diver is a single-level, top-down 2D stealth-escape game set in a dark underwater environment.
Players must navigate a pitch-black maze to find an exit. The environment is invisible by default; players can press the Spacebar to emit a "Sonar Wave," which briefly illuminates the surrounding terrain and any lurking monsters. However, while sonar reveals the path forward, it also draws monsters toward the player.

Press the Spacebar to emit a sonar wave and use WASD to move around.
Quickly memorize the layout of the walls and the positions of monsters during the 1.5-second visibility window.
Monsters move toward the coordinates where sonar was last triggered, rather than tracking the player in real time.

Game Focus: An intense escape experience centered on memory, strategic observation, and using sound to manipulate enemy positions, rather than a high-speed chase based purely on reflexes.


2. Full Feature Set

Phase 1

- A fixed maze map
- The player moves with WASD or the arrow keys
- A darkness mask covers the screen
- A small, persistent light circle with a radius of 1.5 tiles surrounds the player, ensuring that players can still locate themselves in the dark
- Press Space to trigger an expanding circular wave centered on the player's position, with a 1.5-second cooldown
- The wave bounces back if meet the walls and uses distance-based calculations to reduce implementation complexity
- Walls, the exit, and monsters reached by the wave are highlighted for 1.5 seconds, then gradually fade back into darkness


Phase 2

- Place one moving mosters on the map
- Place 2–4 lurking monsters on the map. They remain stationary until they hear sonar
- When a monster hears sonar within its radius, it sets the player's position at the moment of emission as its target and moves toward it
- Upon reaching the target position, the monster moves around the point to search the player until it hears another sonar pulse
- The monsters can chase the player if it's close enouth(2-3 units, to be decided)
- The mosters move faster than the player but they lose direction if the distance is too far
- Adding more landscapes: poles, "mazes with blockers" ...

- Victory: Entering the exit tile triggers the victory screen.
- Defeat: Colliding with a monster triggers the defeat screen.
- Restart: Press R on the victory or defeat screen to reset the player, monsters, and game state without refreshing the page.

- When revealed by sonar, the exit must have a distinct green color or highlighted symbol.
- Revealed monsters appear as red warning icons.
- Tune player speed, sonar radius, and monster speed.


3. Acceptance Criteria

[Movement and Collision] Players can move smoothly through the maze using WASD or the arrow keys; movement through wall tiles is blocked.
[Persistent Field of View] When no keys are pressed, the entire screen remains dark except for a very small area, approximately 1–1.5 tiles, surrounding the player.
[Sonar Reveal] Pressing Space emits a sonar wave from the player's position. Walls and the exit swept by the wave become clearly visible, then fade back into darkness after 1.5 seconds.
[Sonar Cooldown] Sonar has a 1.5-second cooldown, preventing continuous rapid-fire use.
[Monster Response to Sonar] A monster within sonar range moves toward the coordinates where the player was located when sonar was triggered. If the player moves away, the monster stops upon reaching those coordinates rather than tracking the player's current position.
[Monster Behavior in Silence] Without a sonar pulse, idle monsters remain stationary. Monsters already moving toward a previous sound source continue to that target; silent player movement does not change their target.
[Exit Identification] When illuminated by sonar, the exit has a distinct color or visual marker, such as a green highlighted sign, to differentiate it from ordinary walls.
[Failure Condition] Touching any monster immediately freezes gameplay and displays "GAME OVER / You have been consumed."
[Victory Condition] Reaching the exit immediately freezes gameplay and displays "ESCAPE SUCCESSFUL / You have escaped."
[Reset Function] After the game ends, pressing R restarts the game, resets all entities to their original positions, and returns the map to its initial dark state.


4. Priorities & Triage

Highest Priority
- Player movement and wall collision.
- Darkness mask and sonar reveal/fade behavior with a 1.5-second visibility duration.
- Monster AI that moves toward the coordinates where sonar was emitted.
- Defeat on monster contact, victory upon reaching the exit, and restart with R.

Secondary Priority
- Distinct reveal effects for the exit and monsters, such as different colors or icons.
- Expanding sonar ripple animation.
- Smooth monster movement between tiles rather than instant jumps.

First to Cut When Time Is Limited
- Sound effects and background music.
- Multiple monster types or complex patrol routes.
- Dynamic particles and flickering lights.
- Multiple levels or randomly generated maps. Keep the game focused on one hand-designed or preset map.
