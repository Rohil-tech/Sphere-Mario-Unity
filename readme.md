# Sphere Mario

A 3D collection game built in Unity, inspired by Super Mario. Players control a sphere across 3 levels of increasing difficulty, collecting coins and defeating enemies before time runs out.

🎮 **[Play on Unity Play](https://play.unity.com/en/games/937fe93c-d75b-4ac7-8550-fe392a553d8e/mca-2-sphere-mario)**

---

## Overview

Players navigate a physics-based sphere across handcrafted levels, collecting all coins before the timer expires. The final level introduces a flag-planting challenge that must be completed after collecting all coins. Death reloads the current level; completing a level advances to the next.

---

## Levels

| Level | Description |
|---|---|
| Level 1 | Standard collection level with 3 coins and 1 enemy |
| Level 2 | 4 coins, 2 enemies, and a brick bridge requiring stair climbing |
| Level 3 | 7 coins, 4 enemies, firebars, and a flag-planting challenge to complete the game |

---

## Gameplay

- **Movement** — Physics-based WASD/arrow key movement with inspector-configurable speed
- **Jumping** — Space bar jump with airborne prevention; configurable jump force
- **Enemies** — Follow the player while staying grounded; destroyed when stomped from above or hit by firebars/other enemies
- **Coins** — Oscillate and rotate continuously; shrink animation on collection; TAB destroys all instantly
- **Firebars** — Self-rotating bars with configurable speed and axis; destroy enemies and kill the player on contact
- **Flag** — Displays enemy flag by default; switches to Mario flag on player collision after all coins are collected
- **Death Zone** — Plane below the map triggers game over if the player falls off

---

## Systems

| System | Description |
|---|---|
| `LevelManager` | Tracks timer, score, win/lose states; supports standard and final-level win conditions |
| `PlayerController` | Physics-based movement using Rigidbody with ForceMode.Acceleration; smooth velocity stop on game end |
| `PlayerBehavior` | Stomp detection via contact normal; collision handling for enemies, firebars, and death zones |
| `PickupBehavior` | Oscillation, rotation, score tracking, and animation trigger on collection |
| `EnemyBehavior` | Grounded player-following with death animation and sound effect |
| `FireBarBehavior` | Constant rotation with inspector-configurable axis and speed |
| `FlagBehavior` | Material swap on player collision gated by pickup count |
| `CameraController` | Follows player with fixed offset; hosts background audio source |

---

## Built With

- **Unity**
- **C#**