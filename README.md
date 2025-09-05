# Game-Reroll-Challenge

A lightweight, browser-based challenge tracker with local save support and seed import/export for easy sharing. Designed for streamers, speedrunners, and solo players.

## Getting Started

### Online Version
Visit the live site here:  
**[Live Demo](https://Artorosia.github.io/Game-Reroll-Challenge)**

### Local Version
1. Download or clone this repository.
2. Open `index.html` in your browser.
3. Start tracking your challenge.

## Features

- Seed system: Export or import your challenge state to back it up or share with others.
- Streamer-friendly: Share a seed with your audience & they can replicate your run.(Also potential stream overlay, if I get it working, [seen here](https://i.imgur.com/Enjv4rL.png))
- Portable: Works anywhere you can open a modern web browser.

## Seed System

3. Export a seed to create a shareable code containing your current challenge setup.
4. Import a seed to load someone else’s challenge or restore your own from a backup.

Even if you clear your browser cache or switch devices, you can restore your progress by importing your saved seed.

## Rules

### Concept
The Reroll Challenge began as a way for me to have fun clearing my backlog, games I otherwise wasn’t going to play. It worked by rotating through multiple titles with escalating constraints, keeping things fresh and giving me a reason to stick with them.

It has since grown into a modular framework that can be shaped to fit almost any style of play. You can:

    Build your own pool of games for any platform or genre.

    Create custom handicap lists, split into permanent and temporary rules.

    Adjust rotation rules to swap games after a set time, a death, a level, or any trigger you choose.

    Dynamically set different timers for each game, so a speedrun segment might get 15 minutes while a longer endurance section gets an hour.

    Export and import seeds so others can run the exact same setup, whether for casual play, community races, or competitive speedruns.

Because the system does not hook into game code, it works with any game. You can apply the same framework to everything you play and customise the rules to fit your style. A long‑form endurance run might rotate between three RPGs, each with its own 90‑minute timer and strict resource limits. A short experimental session could cycle through several platformers in 10‑minute bursts with temporary handicaps like “must keep moving” or “no jumping for 30 seconds.” A structured speedrun race could give each game a different timer based on its category length, paired with handicaps that force new routes or strategies. A community challenge night might use a viewer‑submitted seed with a curated mix of games, timers, and rules that everyone can load and attempt.


SECTION                  | DEFAULT RULE
------------------------ | --------------------------------------------------------------
SLOTS                    | 1–10 slots, each representing one game in the rotation order.
                         | More slots create more variety and allow temporary handicaps
                         | to spread across multiple games. Slots can also be used for
                         | different categories of the same game, alternate save files,
                         | or different difficulty settings.

SESSION LENGTH           | 1 hour per slot.
                         | Timer length is adjustable per slot (e.g., 15 min for short
                         | runs, 90 min for long RPG segments, or no timer for play
                         | until death).

ROTATION FLOW            | Progress through slots in order. When the final slot finishes,
                         | the rotation repeats. All temporary handicaps are cleared at
                         | the end of each rotation.

TEMPORARY HANDICAPS      | Triggered by a death, assigned to a future slot in the same
                         | rotation. Only later slots can receive them. Last one session
                         | and stack naturally if multiple deaths target the same slot.

PERMANENT HANDICAPS      | Game‑specific constraints that persist across rotations.
                         | Max 3 per game to avoid softlocks. No duplicates. At the end
                         | of each rotation there is a fixed 1% chance to clear all
                         | permanent handicaps (configurable in a future update).
                         | Beating a game completely clears 3–4 random permanent
                         | handicaps from the run.

TOKENS                   | 20% chance from any achievement to grant a token (fixed for
                         | now, configurable in a future update). Tokens clear one
                         | permanent handicap. Max one token use per rotation.

ROTATION END             | Clears all temporary handicaps. 1% chance to clear all
                         | permanent handicaps. Rotation counter increases by one and
                         | token usage resets.

DATABASE                 | Separate pools for permanent and temporary handicaps.
                         | Multiple databases can be kept for different genres,
                         | difficulty levels, or events. Handicaps are automatically
                         | pulled for the active slot. Manual assignment is not yet
                         | available but may be added in the future.

GOAL                     | Clear all games in the fewest rotations possible. Clearing a
                         | game entirely also clears 3–4 random permanent handicaps.
                         | Can also be adapted for variety streaming, speedrun gauntlets,
                         | or community challenge events.

