---
title: Achievements
description: 51 built-in achievements across 8 categories + JSON-driven custom achievements for server owners.
order: 8
published: true
---

# Achievements

**51 built-in achievements across 8 categories**, each with XP and (optional) item rewards — plus a JSON-driven custom-achievement system that lets server owners add unlimited extra entries without writing Java.

**Command:** `/eg journal` (Achievements tab) — Permission: `endgameqol.journal` (default: allow).

The Achievements tab is paginated (10 entries per page) and supports filter chips across the 8 categories. Custom achievements appear inline alongside the built-ins.

---

## Combat — 5 achievements

| Achievement | Objective | Target | XP |
| --- | --- | :---: | :---: |
| First Blood | Kill your first endgame NPC | 1 | 25 |
| Slayer | Kill 50 endgame NPCs | 50 | 100 |
| Veteran Slayer | Kill 100 endgame NPCs | 100 | 200 |
| Exterminator | Kill 500 endgame NPCs | 500 | 500 |
| Thousand Kills | Kill 1 000 endgame NPCs | 1 000 | 1 000 |

## Boss — 7 achievements

| Achievement | Objective | XP |
| --- | --- | :---: |
| Dragon Slayer | Defeat the Frost Dragon | 200 |
| Hedera's Bane | Defeat Hedera | 200 |
| Void Crusher | Defeat the Void Golem | 300 |
| Flame Tamer | Defeat the Fire Dragon | 150 |
| Boss Rush | Defeat all 4 boss types | 500 |
| Boss Hunter | Defeat 10 bosses total | 400 |
| Boss Executioner | Defeat 25 bosses total | 800 |

## Bounty — 10 achievements

| Achievement | Objective | Target | XP |
| --- | --- | :---: | :---: |
| Bounty Hunter | Complete your first bounty | 1 | 50 |
| Professional Hunter | Complete 10 bounties | 10 | 150 |
| Bounty Master | Complete 50 bounties | 50 | 400 |
| Bounty Legend | Complete 100 bounties | 100 | 700 |
| Weekly Warrior | Complete 5 Weekly bounties | 5 | 500 |
| Streak Starter | Claim 3 daily streak bonuses | 3 | 100 |
| Streak Veteran | Claim 7 daily streak bonuses | 7 | 250 |
| Veteran Hunter | Reach Veteran reputation rank (500 rep) | 1 | 200 |
| Elite Hunter | Reach Elite reputation rank (1 500 rep) | 1 | 500 |
| Legendary Hunter | Reach Legend reputation rank (3 000 rep) | 1 | 1 000 |

## Discovery — 6 achievements

| Achievement | Objective | Target | XP |
| --- | --- | :---: | :---: |
| Curious Explorer | Discover 5 NPC types | 5 | 50 |
| Explorer | Discover 10 NPC types | 10 | 100 |
| Seasoned Explorer | Discover 20 NPC types | 20 | 200 |
| Bestiary Adept | Discover at least 50% of the bestiary | 50% | 250 |
| Bestiary Scholar | Discover at least 75% of the bestiary | 75% | 400 |
| Naturalist | Discover all endgame NPC types | all | 500 |

## Crafting — 5 achievements

| Achievement | Objective | Target | XP |
| --- | --- | :---: | :---: |
| Apprentice Smith | Craft your first endgame weapon | 1 | 50 |
| Blacksmith | Craft 5 endgame weapons | 5 | 150 |
| Master Crafter | Craft 10 endgame weapons | 10 | 300 |
| Arsenal Builder | Craft one of each weapon type (8 types) | 8 | 500 |
| Prismatic Smith | Craft a Prisma-tier weapon | 1 | 500 |

## Exploration — 6 achievements

| Achievement | Objective | Target | XP |
| --- | --- | :---: | :---: |
| Dungeon Diver | Enter your first dungeon | 1 | 50 |
| Dungeon Crawler | Enter 5 dungeon instances | 5 | 150 |
| Dungeon Veteran | Enter 15 dungeon instances | 15 | 300 |
| Frostbitten | Enter the Frozen Dungeon | 1 | 100 |
| Swamp Walker | Enter the Swamp Dungeon | 1 | 100 |
| World Traveler | Enter both dungeon types | 2 | 250 |

## Speedrun — 6 achievements

| Achievement | Objective | XP |
| --- | --- | :---: |
| Blizzard Blitz | Defeat the Frost Dragon in under 3 minutes | 300 |
| Root Ripper | Defeat Hedera in under 4 minutes | 300 |
| Void Velocity | Defeat the Void Golem in under 5 minutes | 400 |
| Inferno Rush | Defeat the Fire Dragon in under 2 minutes | 250 |
| Speed Demon | Speed-kill any 3 bosses | 500 |
| Perfectionist | Speed-kill all 4 boss types | 800 |

## Mining — 6 achievements

| Achievement | Objective | Target | XP |
| --- | --- | :---: | :---: |
| Prospector | Mine your first Mithril or Adamantite Ore | 1 | 25 |
| Ore Hoarder | Mine 50 Mithril or Adamantite Ore | 50 | 150 |
| Deep Miner | Mine 200 Mithril or Adamantite Ore | 200 | 400 |
| Mithril Seeker | Mine 25 Mithril Ore | 25 | 200 |
| Adamantite Hunter | Mine 25 Adamantite Ore | 25 | 250 |
| Earthshaker | Mine 1 000 blocks total | 1 000 | 500 |

---

## Custom Achievements via JSON (5.2.0+)

Server owners can add unlimited custom achievements without writing Java. Drop one or more `.json` files into:

```
Saves/<world>/mods/Config_Endgame&QoL/CustomAchievements/
```

The plugin creates this folder on first launch with a README and an example file. Each file may contain a single achievement or an `{"Achievements": [ … ]}` array.

### Minimal entry

```json
{
  "Id":              "mymod_skeleton_slayer",
  "Name":            "Skeleton Slayer",
  "Description":     "Kill 100 skeletons",
  "Category":        "Combat",
  "Target":          100,
  "XpReward":        200,
  "RewardDropTable": "Endgame_Drop_Reward_10",
  "Trigger": { "Type": "KillNpc", "Target": "Skeleton" }
}
```

### Supported trigger types

| Trigger | Target | Extra | Increments |
| --- | --- | --- | --- |
| `KillNpc` | NPC type id | — | +1 per kill |
| `KillBoss` | Boss type id (or omitted = any) | — | +1 per credited kill |
| `SpeedKillBoss` | Boss type id | Max seconds | +1 per qualifying speed kill |
| `CompleteBounty` | — | — | +1 per bounty claimed |
| `CompleteBountyOfDifficulty` | `EASY` / `MEDIUM` / `HARD` / `WEEKLY` | — | +1 per matching bounty |
| `ReachComboTier` | — | Tier 1-4 (×2 / ×3 / ×4 / FRENZY) | +1 each time the player reaches at least that tier |
| `EnterDungeon` | World-name prefix or any | — | +1 per entry |
| `MineOre` | Ore item id | — | +1 per ore mined |
| `CraftItem` | Item id | — | +1 per craft |
| `DamageDealt` | Boss type id or any | — | +`amount` per hit |
| `CompleteTrial` | — | Minimum tier | +1 per qualifying clear |
| `ReachBountyRank` | `NOVICE` / `VETERAN` / `ELITE` / `LEGEND` (or omitted = any) | — | +1 per rank-up crossing that threshold |

### Hot reload

Run `/eg admin reload` after editing the JSON files — the registry swaps atomically and players keep their existing progress on unchanged ids. No restart needed.

### Validation

Malformed entries are skipped with a `WARNING` log line citing the file + index + reason. The rest of the file continues to load. A custom id that collides with a built-in or another custom is rejected with a warning (first occurrence wins).

**Full schema documentation:** see `CUSTOM_ACHIEVEMENTS_GUIDE.md` in the repository.

---

## Shared boss kill credit

When `SharedBossKillCredit` is enabled in the config (default: on), boss achievements are awarded to all players in the same instance when a boss is defeated — not just the player who lands the killing blow. Group content rewards all participants equally.

---

## Total XP summary

| Category | Achievements | Total XP |
| --- | :---: | :---: |
| Combat | 5 | 1 825 |
| Boss | 7 | 2 550 |
| Bounty | 10 | 3 850 |
| Discovery | 6 | 1 500 |
| Crafting | 5 | 1 500 |
| Exploration | 6 | 950 |
| Speedrun | 6 | 2 550 |
| Mining | 6 | 1 525 |
| **Total** | **51** | **16 250** |

Custom achievements contribute their own `XpReward` value on top of this total.
