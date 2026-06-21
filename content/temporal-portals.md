---
title: Temporal Portals
description: Random spawning particle portals leading to temporary dungeon instances — Canopy Shrine (chill), Oakwood Refuge (mid), Eldergrove Hollow (harder).
order: 4
published: true
---

# Temporal Portals

Random particle-only portals that spawn near players and lead to temporary challenge instances. Introduced in v5.0.0.

**Pool: three live destinations.** Canopy Shrine (chill / no boss), Oakwood Refuge (mid / Warlord), and Eldergrove Hollow (harder / Despot).

## How it works

| | |
| --- | --- |
| **Spawn cadence** | Every ~1h30 (configurable up to 2h). 50 % roll per attempt, up to 3 concurrent portals server-wide. |
| **Position** | 80–300 blocks from a player, on the surface (scans for solid ground, rejects buried / cave pockets). |
| **Particle-only** | No block placement, no permanent world change. Grief-free. |
| **Claim-aware** | Skips zones protected by OrbisGuard / SimpleClaims / QuestLines & Claims. |

## Lifetime & warnings

Portals decay through four states before collapsing. Chat warnings fire before expiration.

| Status | Particle hue | Meaning |
| --- | --- | --- |
| STABLE | Ambient purple | Fresh portal, full lifetime remaining |
| DESTABILIZING | Ambient purple | Halfway through lifetime |
| CRITICAL | Fire-tinted | Final stretch before collapse |
| COLLAPSING | Fire-tinted | Grace period (~30 s) — still usable but imminent |

| When | Event |
| --- | --- |
| 5 min before expiration | Chat warning |
| 1 min before expiration | Chat warning + sound |
| Portal collapse | 30-second grace period begins |

## Entering & returning

Walk into the particle column to teleport into the instance. A return portal is placed inside — walk back through to return to the exact overworld location.

If the portal collapses while you are inside, the instance remains valid until you leave or the instance time limit (default 15 min) hits. The return portal still works.

## The instances

### Canopy Shrine — Chill

Sky-temple built across treetops. Misty-blue skybox, high-mobility arena. **No boss, no elite — exploration only.** Three themed chests scattered across the platforms (common / rare / hidden tiers).

Lowest spawn weight in the pool (50 % default, vs 30 % Oakwood and 10 % Eldergrove — chill content is more frequent).

### Oakwood Refuge — Mid-tier — Oakwood Warlord (1 000 HP)

<img src="https://raw.githubusercontent.com/lewai1/endgameqolwiki/main/images/mobs/Oakwood_Warlord.png" width="100" style="float:right;margin:0 0 8px 14px;">

Dense oak grove with elevated platforms. Warm-oak skybox fixed at night (22:00) for the Warlord encounter.

| Attack | Description | Damage |
| --- | --- | --- |
| Triple Strike | 3× melee battleaxe swings | 25 Physical × 3 |
| Scepter Shot | 3-orb purple projectile barrage | 25 Physical × 3 |
| Ground Slam | AOE with purple telegraph ring | 60 Physical AOE |
| Death Summon | Spawns a 400 HP withered husk on kill | — |

**Drops:** 2–4 Mithril Bars guaranteed + 1 aleatory slot (Voidheart / Adamantite Bar). Chest loot scattered across the arena (common / rare / hidden tiers).

<div style="clear:both;"></div>

### Eldergrove Hollow — Harder — Eldergrove Despot (1 800 HP)

<img src="https://raw.githubusercontent.com/lewai1/endgameqolwiki/main/images/mobs/Eldergrove_Despot.png" width="100" style="float:right;margin:0 0 8px 14px;">

Ancient forest ruins under a fading canopy. The Despot is a **pure caster**: kites the player at range with three elemental schools while a spiked shield deflects melee bursts.

| Attack | Description | Damage |
| --- | --- | --- |
| Ice Bolt | Long-range ice projectile (preferred at 8–12 blocks) | Ice |
| Fire Blast | Close-range explosion when the player closes in (< 7 blocks) | Fire AOE |
| Lightning Strike | Mid-range burst at 3–8 blocks, longer cooldown | Lightning |
| Shield Block | Spiked shield raised every ~5 s — blocks melee bursts | Defensive |

**Drops:** 2–4 Mithril Bars guaranteed + 1 aleatory slot (Voidheart 50 % · Adamantite Bar 30 % · Emerald 20 %). +33 % XP reward vs the Warlord (400 vs 300).

<div style="clear:both;"></div>

## Configuration

Exposed in `/eg config → Misc → Temporal Portals`. Live-reload, no restart.

| Key | Default | Description |
| --- | --- | --- |
| `Enabled` | `true` | Master toggle |
| `SpawnIntervalMin` / `SpawnIntervalMax` | 5400s / 5400s | Cooldown window (~1h30) |
| `SpawnChance` | 0.50 | Probabilistic roll per attempt |
| `MaxConcurrentPortals` | 3 | Simultaneous portals server-wide |
| `SpawnMinDistance` / `SpawnMaxDistance` | 80 / 300 blk | Range from the player |
| `MinDistanceBetweenPortals` | 100 blk | Minimum spacing |
| `GracePeriodSeconds` | 30 s | Extra visible time after expiration |
| `AnnounceRadius` | 100 blk | Chat announcement range |
| `Dungeons.<id>.Enabled` | — | Per-dungeon enable flag |
| `Dungeons.<id>.PortalDuration` | 180 s | Portal lifetime |
| `Dungeons.<id>.InstanceTimeLimit` | 900 s | Instance time limit once entered |
| `Dungeons.<id>.AllowRespawnInside` | `false` | Respawn inside on death vs kick to overworld |

## Compatibility & framework

Warden Challenges are blocked inside temporal instances (and all dungeon instances). Using one inside prints a chat warning.

Temporal dungeon waves and future gauntlet-style encounters run on the shared [WaveArena framework](api) — public API for third-party mods to build custom wave arenas on the same engine.
