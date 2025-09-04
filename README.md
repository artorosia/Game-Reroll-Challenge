# Game-Reroll-Challenge

A lightweight, browser-based challenge tracker with local save support and seed import/export for easy sharing. Designed for streamers, speedrunners, and solo players.

## Features

- Seed system: Export or import your challenge state to back it up or share with others.
- Streamer-friendly: Share a seed with your audience & they can replicate your run.
- Portable: Works anywhere you can open a modern web browser.

## Seed System

3. Export a seed to create a shareable code containing your current challenge setup.
4. Import a seed to load someone else’s challenge or restore your own from a backup.

Even if you clear your browser cache or switch devices, you can restore your progress by importing your saved seed.

## Rules

### Concept
The Reroll Challenge is designed to help you work through your game library by rotating through multiple games with escalating constraints.   
It is built for endurance rather than speed. play cleanly, manage risk, and keep momentum.

---

### Rotation and Sessions
- Set up **3–10 slots**, each representing one game in your rotation order.
- Each session lasts **1 hour per slot**, tracked with the slot’s timer widget.
- Progress through slots in order; when the final slot finishes, the rotation ends.

---

### Deaths and Temporary Handicaps
- When you die in a slot, immediately switch to the next slot.
- That death also triggers a **temporary handicap** assigned to a future slot within the same rotation.
  - Only slots appearing after the current slot can receive the handicap.
  - Slot 1 is immune to temporary handicaps caused in prior rotations, since all temps clear at rotation end.
- Temporary handicaps last **one session** and clear automatically at the end of the rotation.

---

### Permanent Handicaps
- Permanent handicaps are **game-specific constraints** that persist across rotations.
- Each game can have a maximum of **3 permanent handicaps** to avoid softlocks.
- Rolling a permanent handicap selects from that game’s database pool, avoiding duplicates.

---

### Tokens and Achievements
- Every achievement earned (in any game) has a **20% chance** to grant a token.
- Tokens can clear **one permanent handicap**.
- You may use at most **one token per rotation**.

---

### Rotation End
- Finishing a rotation(die in final game, or reach the the hour timer) clears all temporary handicaps.
- There is a **1% chance** at rotation end to also clear all permanent handicaps.
- Rotation count increments; token usage resets.

---

### Database and Slots
- Maintain a database of games with separate pools for permanent and temporary handicaps.
- Each slot lets you select a game from the database via a dropdown.
- Handicaps are automatically pulled for whatever game's actively slotted.

---

### Reset Behavior
- **Reset Progress** clears:
  - Deaths
  - Timers
  - Temporary handicaps
  - Permanent handicaps attached to slots
  - Token usage in the current rotation
  - Tokens
  - Rotation count
- Reset does **not** remove:
  - Slots
  - Selected games
  - The database itself

---

### Goal
Clear all games in the **fewest rotations possible**.  
Fewer deaths, smarter plays, faster clears.


## Getting Started

### Online Version
Visit the live site here:  
**[Live Demo](https://Artorosia.github.io/Game-Reroll-Challenge)**

### Local Version
1. Download or clone this repository.
2. Open `index.html` in your browser.
3. Start tracking your challenge.

## Folder Structure

