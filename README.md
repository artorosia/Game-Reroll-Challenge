# Game-Reroll-Challenge

A lightweight, browser-based challenge tracker with local save support and seed import/export for easy sharing. Designed for streamers, speedrunners, and solo players.

## Table of Contents
- [Getting Started](#getting-started)
  - [Online Version](#online-version)
  - [Local Version](#local-version)
- [Features](#features)
- [Seed System](#seed-system)
- [Rules](#rules)
  - [Concept](#concept)
  - [Rotation and Sessions](#rotation-and-sessions)
  - [Deaths and Temporary Handicaps](#deaths-and-temporary-handicaps)
  - [Permanent Handicaps](#permanent-handicaps)
  - [Tokens and Achievements](#tokens-and-achievements)
  - [Rotation End](#rotation-end)
  - [Database and Slots](#database-and-slots)
  - [Goal](#goal)

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

## Concept

The Reroll Challenge began as a way for me to have fun clearing my backlog, games I otherwise was not going to play. It worked by rotating through multiple titles with escalating constraints, keeping things fresh and giving me a reason to stick with them.

It has since grown into a modular framework that can be shaped to fit almost any style of play. You can **build your own pool of games** for any platform or genre. You can **create custom handicap lists**, split into permanent and temporary rules. You can **adjust rotation rules** to swap games after a set time, a death, a level, or any trigger you choose. You can **dynamically set different timers** for each game, so a speedrun segment might get 15 minutes while a longer endurance section gets an hour. You can **export and import seeds** so others can run the exact same setup, whether for casual play, community races, or competitive speedruns.

Because the system does not hook into game code, it works with any game. You can apply the same framework to everything you play and customise the rules to fit your style. A long form endurance run might rotate between three RPGs, each with its own 90 minute timer and strict resource limits. A short experimental session could cycle through several platformers in 10 minute bursts with temporary handicaps like “must keep moving” or “no jumping for 30 seconds.” A structured speedrun race could give each game a different timer based on its category length, paired with handicaps that force new routes or strategies. A community challenge night might use a viewer submitted seed with a curated mix of games, timers, and rules that everyone can load and attempt.

---

## Rotation and Sessions

Set up **1–10 slots**, each representing one game in your rotation order. The challenge works with any number, but more slots create more variety and allow temporary handicaps to spread across multiple games. Slots can also be used for different categories of the same game, alternate save files, or different difficulty settings.

Each session lasts **1 hour per slot**, tracked with the slot’s timer widget. The timer length is fully adjustable per slot. You can give a speedrun segment 15 minutes, a grind heavy RPG 90 minutes, or run without a timer for a play until death format.

Progress through slots in order. When the final slot finishes, the rotation repeats. At the end of each rotation, all temporary handicaps are cleared.

---

## Deaths and Temporary Handicaps

When you die in a slot, immediately switch to the next slot. You can change this trigger to something else, such as swapping on boss defeat, level completion, or a set number of in game days.

That death also triggers a **temporary handicap** assigned to a future slot within the same rotation. Only slots appearing after the current slot can receive the handicap. Slot 1 is immune to temporary handicaps caused in prior rotations, since all temps clear at rotation end.

Temporary handicaps always last **one session** and naturally stack if multiple deaths target the same future slot. In a large rotation, the final slot can end up carrying several temporary handicaps at once.

---

## Permanent Handicaps

Permanent handicaps are **game specific constraints** that persist across rotations. You can make these as light or as punishing as you want, from “no fast travel” to “permadeath for party members.”

Each game can have a maximum of **3 permanent handicaps** to avoid softlocks. You can raise or lower this cap depending on how challenging you want the run to be.

Rolling a permanent handicap selects from that game’s database pool, avoiding duplicates.

At the end of each rotation there is a **1% chance** to clear all permanent handicaps. This chance is fixed in the current version, but the option to change it will be added in a future update.

**Beating a game completely** immediately clears **3–4 random permanent handicaps** from your entire run, giving a strong incentive to finish titles rather than just rotate through them.

---

## Tokens and Achievements

Every achievement earned (in any game) has a **20% chance** to grant a token. This chance is fixed in the current version, but the option to change it or tie tokens to other milestones will be added in a future update.

Tokens can clear **one permanent handicap**.

You may use at most **one token per rotation**.

---

## Rotation End

Finishing a rotation (dying in the final game, or reaching the hour timer) clears all temporary handicaps.

There is a **1% chance** at rotation end to also clear all permanent handicaps (configurable in a future update).

The rotation counter increases by one, and token usage limits reset.

---

## Database and Slots

Maintain a database of games with separate pools for permanent and temporary handicaps. You can keep multiple databases for different genres, difficulty levels, or community events.

Each slot lets you select a game from the database via a dropdown.

Handicaps are automatically pulled for whatever game is actively slotted.

Manual handicap assignment is not currently available, but may be added in the future for curated challenges.

---

## Goal

Clear all games in the **fewest rotations possible**. Fewer deaths, smarter plays, faster clears. Clearing a game entirely not only removes it from your backlog but also clears **3–4 random permanent handicaps**, making it a powerful way to improve your odds in the rest of the challenge. Or adapt the system for variety streaming, speedrun gauntlets, or community challenge events.
