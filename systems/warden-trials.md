---
title: Warden Trials
description: 4-tier wave survival combat encounters. Built on the WaveArena framework.
order: 4
published: true
---

# Warden Trials

4-tier wave survival combat encounters, migrated onto the generic WaveArena framework in v5.0.0.

Start a Warden Trial by using a **Warden Challenge** item (Tier I through IV). Each trial consists of 5 waves of enemies that must be cleared before the timer expires.

Higher tiers feature stronger enemies, longer timers, and greater rewards. The final wave of Tiers II–IV includes a boss-tier enemy.

**v5.0.0** — Warden Trials run on the data-driven [WaveArena framework](api) (shared with temporal portals and the Void Realm Gauntlet). The framework is documented for third-party mods.

**Blocked inside instances** — by default, Warden Challenge items cannot be used inside dungeon instances (temporal portals, Void Realm, Frozen / Swamp Dungeons). Using one inside prints a chat warning and cancels the trial. Server owners control where they're blocked with the `WardenTrialBlockedWorlds` config — clear it to allow trials anywhere, or list your own world-name fragments.

## State flow

`COUNTDOWN (3 s) → SPAWNING → ACTIVE → WAVE_CLEAR → INTERVAL (8 s)` — repeat — `→ COMPLETED` or `FAILED`.

## Leash / arena boundary

Players are leashed to a 50-block radius around the arena center. Leaving the radius doesn't fail the trial — the zone just warns you. The arena particle boundary visualizes the leash.

## Tier I — Adamantite

**4:30 timer · 150 XP · no final boss**

| Wave | Composition | Total |
| :---: | --- | :---: |
| 1 | Goblin Scrapper ×3, Skeleton Archer ×2 | 5 |
| 2 | Skeleton Soldier ×2, Skeleton Mage ×2, Spider ×1 | 5 |
| 3 | Hyena ×2, Goblin Lobber ×2, Skeleton Ranger ×1 | 5 |
| 4 | Outlander Brute ×1, Skeleton Archmage ×1, Skeleton Soldier ×2 | 4 |
| 5 | Toad Rhino ×1, Outlander Hunter ×2, Skeleton Knight ×2 | 5 |

## Tier II — Mithril

**6:00 timer · 300 XP · final boss: Goblin Duke**

| Wave | Composition | Total |
| :---: | --- | :---: |
| 1 | Trork Brawler ×2, Skeleton Ranger ×2, Trork Hunter ×1 | 5 |
| 2 | Outlander Marauder ×2, Outlander Stalker ×2, Skeleton Archmage ×1 | 5 |
| 3 | Tiger Sabertooth ×2, Trork Sentry ×2, Skeleton Mage ×1 | 5 |
| 4 | Saurian Warrior ×2, Ghoul ×2, Outlander Sorcerer ×1 | 5 |
| 5 | **Goblin Duke ×1**, Saurian Hunter ×1, Skeleton Burnt Wizard ×1, Werewolf ×1 | 4 |

## Tier III — Onyxium

**7:30 timer · 450 XP · final boss: Necromancer Void**

| Wave | Composition | Total |
| :---: | --- | :---: |
| 1 | Saurian Rogue ×2, Skeleton Sand Mage ×2, Ghoul ×1 | 5 |
| 2 | Werewolf ×2, Skeleton Burnt Gunner ×2, Skeleton Burnt Wizard ×1 | 5 |
| 3 | Goblin Duke ×1, Saurian Warrior ×1, Skeleton Sand Archmage ×1, Skeleton Burnt Gunner ×1 | 4 |
| 4 | Shadow Knight ×2, Skeleton Burnt Gunner ×2, Golem Eye Void ×1 | 5 |
| 5 | **Necromancer Void ×1**, Shadow Knight ×1, Skeleton Sand Archmage ×1, Skeleton Burnt Gunner ×2 | 5 |

## Tier IV — Prisma

**9:00 timer · 600 XP · final boss: Shadow Knight + full roster**

| Wave | Composition | Total |
| :---: | --- | :---: |
| 1 | Goblin Duke ×1, Necromancer Void ×1, Skeleton Burnt Gunner ×2, Skeleton Burnt Wizard ×1 | 5 |
| 2 | Alpha Rex ×1, Werewolf ×1, Skeleton Burnt Wizard ×2, Golem Eye Void ×1 | 5 |
| 3 | Necromancer Void ×1, Alpha Rex ×1, Skeleton Sand Archmage ×2, Golem Eye Void ×2 | 6 |
| 4 | Alpha Rex ×2, Goblin Duke ×1, Skeleton Burnt Gunner ×2 | 5 |
| 5 | **Shadow Knight ×1**, Alpha Rex ×1, Skeleton Sand Archmage ×1, Skeleton Burnt Gunner ×1, Golem Eye Void ×1, Necromancer Void ×1 | 6 |

## Wave timer

Each tier has a configurable total timer. The HUD displays a countdown during active waves. The last 10 seconds are displayed in red as a warning.

Setting a timer to `0` disables the timer for that tier, allowing unlimited time to clear waves.

## Fail conditions

- **Death** — player is killed during any wave
- **Disconnect** — player disconnects from the server (`FailReason.DISCONNECT`)
- **Timer expired** — wave timer reaches zero before all enemies are defeated
- **Instance blacklist** — attempting to start inside a dungeon instance

## HUD overlay

During an active trial, a persistent HUD overlay displays:

- Wave counter — current wave / total
- Difficulty color — tier-coded indicator
- Progress bar — visual wave completion progress
- Kill count — enemies remaining in wave
- Status / timer — current state + countdown (red at 10 s)

## Rewards

Each tier has its own drop table. XP is awarded on completion using the formula `XP = Tier × 150`.

| Tier | XP | Material level |
| --- | :---: | --- |
| I | 150 | Adamantite-tier drops |
| II | 300 | Mithril-tier drops |
| III | 450 | Onyxium-tier drops |
| IV | 600 | Prisma-tier drops |

## Configuration

| Key | Default | Description |
| --- | :---: | --- |
| `EnableWardenTrial` | true | Enable / disable Warden Trials |
| `WardenTrialBlockedWorlds` | `instance-` | World-name fragments (CSV) where trials are blocked; empty = anywhere |
| `WardenTrialTimerTier1` | 270 | Tier I timer in seconds (4:30). Set to 0 to disable. |
| `WardenTrialTimerTier2` | 360 | Tier II timer in seconds (6:00). Set to 0 to disable. |
| `WardenTrialTimerTier3` | 450 | Tier III timer in seconds (7:30). Set to 0 to disable. |
| `WardenTrialTimerTier4` | 540 | Tier IV timer in seconds (9:00). Set to 0 to disable. |

## Framework

Warden Trials are a concrete `WaveArenaConfig` registered with the shared engine. Third-party mods can build custom wave arenas (fixed waves or pool-generated) using the same API. See the [Developer API](api) page.
