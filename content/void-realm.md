---
title: Void Realm
description: Void Realm dimension — floating island arena, Golem Void boss, Void Gauntlet wave trial, and boss combat music.
order: 3
published: true
---

# Void Realm

<!-- screenshot pending: images/screenshots/void/overview.png (wide shot of the floating island arena in the void) -->

A new dimension introduced in v5.0.0 — floating island arena in the void, home of the Golem Void.

Replaces the old Shard of the Void portal system. The portal key was renamed from **Shard of the Void** to **Void Realm Key** (auto-migrated via the item ID migration system — old stacks convert on connect and chunk load).

## Overview

| | |
| --- | --- |
| **Entry key** | Void Realm Key |
| **Boss** | Golem Void (3 500 HP) |
| **Pre-boss arena** | Void Gauntlet — 3 waves |
| **Music** | Custom combat track across the entire dimension |

## Entry

1. **Acquire the key** — craft or loot a Void Realm Key.
2. **Activate the gateway** — right-click an Endgame Gateway block with the key. The gateway swaps to its Void-themed variant and the particle VFX activates.
3. **Walk through** — step into the portal to enter the Void Realm instance.

See [Portals & Gateways](portals-gateways) for the full key/portal flow.

## Golem Void

<img src="https://raw.githubusercontent.com/lewai1/endgameqolwiki/main/images/mobs/Golem_Void.png" width="120" style="float:right;margin:0 0 10px 16px;">

- **11 attacks** selected by the Combat Action Evaluator (distance-aware, cooldown-gated, HP-phase-gated)
- Knockback-immune
- Aggressive pursuer — closes distance fast across the floating island
- Signature **Jump Slam** unlocks at < 66 % HP, ramps at < 33 %
- **Void-safe fallback** — if players try to bait the boss over the void, it teleports back to its spawn position
- **Gated behind the Void Gauntlet** — clear the 3 waves first, then the Golem rises from the ruins at the arena center

<div style="clear:both;"></div>

Full attack set and phase notes: see [Bosses & Elites — Golem Void](bosses-elites).

<!-- screenshot pending: images/screenshots/void/golem-void-arena.png (Golem Void rising from the ruins at the arena center) -->

## Void Gauntlet

A wave-survival encounter that auto-starts on entry to the Void Realm (built on the [WaveArena framework](api)).

| Property | Value |
| --- | --- |
| Waves | 3 |
| Time limit | 360 seconds |
| Leash | None — leaving the arena zone does not fail the trial |
| Outcome | On clear, the Golem Void spawns at the arena center |

### Wave composition

| Wave | Mobs |
| :---: | --- |
| 1 — Swarm intro | 3× Spawn_Void · 3× Larva_Void · 1× Shadow_Knight |
| 2 — Pressure | 2× Crawler_Void · 2× Golem_Eye_Void · 1× Spectre_Void · 1× Necromancer_Void |
| 3 — Finale | 2× Spectre_Void · 2× Crawler_Void · 1× Necromancer_Void · 2× Shadow_Knight · 2× Golem_Eye_Void |

No-leash design makes the Void Gauntlet distinct from Warden Trials — you can reposition freely across the floating island.

## Void-fall safety

Falling off the floating island no longer kills you. A safety net catches you and teleports you back to the island surface with a chat line *"The Void pulls you back."* — zero death penalty. Works during the gauntlet and the Golem fight alike.

## Boss combat music

A dedicated combat track plays across the entire Void Realm dimension. It fades back to ambience on boss death or when you leave the realm.

## Void Blocks (decorative crafting)

The Void Realm is the only place to farm **Void Essence** in quantity — the material behind a full line of **10 decorative void blocks**. Learn the recipes from the **Void Architect's Tome**, an Epic consumable that drops from the Void Realm's loot chests and teaches all 10 at once, then craft them at the **Endgame Bench** (Void Blocks category, requires the bench upgraded to **Tier 1**).

Every block is placeable, pickaxe-mined, and stacks to 100. The only ingredients are **Void Essence** and plain **Rock** — `Void Block` is the hub the rest branch from.

| Block | Recipe | Yield |
| --- | --- | :---: |
| Void Block | Rock ×4 + Void Essence ×1 | 4 |
| Void Brick | Rock ×2 + Void Essence ×4 | 4 |
| Void Core *(glows)* | Void Block ×4 + Void Essence ×1 | 4 |
| Void Ancient Stone | Void Block ×4 + Void Essence ×2 | 4 |
| Corrupted Block | Void Block ×4 + Void Essence ×2 | 4 |
| Void Light | Void Block ×1 + Void Essence ×1 | 1 |
| Void Brick Light | Void Brick ×1 + Void Essence ×1 | 1 |
| Void Core Light | Void Core ×1 + Void Essence ×1 | 1 |
| Void Ancient Light | Void Ancient Stone ×1 + Void Essence ×1 | 1 |
| Corrupted Light | Corrupted Block ×1 + Void Essence ×1 | 1 |

**Where to farm Void Essence:** Void Realm loot chests (primary — and the only source of the Void Architect's Tome), **Void Frog** (4–6 per kill, the best repeatable farm), Golem Void, and Hedera (10–20). See [Materials](materials) for the full drop table.

## Getting in & out

Activate an Endgame Gateway with a Void Realm Key — the portal lights up purple and you walk in. A return portal inside sends you back to the exact gateway you came from. Reusable as many times as you want. See [Portals & Gateways](portals-gateways).
