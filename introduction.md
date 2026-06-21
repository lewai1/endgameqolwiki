---
title: Introduction
description: Overview of everything Endgame & QoL adds to your Hytale server — content summary, material progression, and getting started steps.
order: 1
published: true
---

# Introduction

Endgame & QoL is a complete late-game content layer for Hytale. Once you've reached Adamantite tier in vanilla and the world starts feeling empty, this is what's next: 3 phased bosses, 6 elites, 6 instances (3 fixed dungeons + 3 temporal portals), a pet companion system, and 145+ items — all running on Hytale Update 5.

---

## Content overview

| Category | Count | Details |
| --- | --- | --- |
| Bosses | 3 | Dragon Frost (1 400 HP), Hedera (1 800 HP), Golem Void (3 500 HP) |
| Elites | 6 | Alpha Rex, Fire Dragon, Swamp Crocodile, Bramble Elite, Oakwood Warlord, Eldergrove Despot |
| Fixed dungeons | 3 | Frozen Dungeon, Swamp Dungeon, **Void Realm** (new dimension) |
| Temporal portals | 3 | Canopy Shrine (chill), Oakwood Refuge (mid), Eldergrove Hollow (hard) |
| Pets | 4 | Dragon Frost, Dragon Fire, Golem Void, Hedera — 6 tiers (D → SS) |
| Weapons | 40+ | Swords, daggers, longswords, spears, staves, bows, shields, battleaxes, maces |
| Armor | 5 sets | Diving Crude, Adamantite, Mithril, Onyxium, Prisma |
| Tools | 8 | Pickaxes, hatchets, shovels — Prisma tier has 3×3 area break |
| Accessories | 7 | 6 trinkets + the Trinket Pouch |
| Traders | 3 | Vorthak, Korvyn, Morghul (custom Trade UI) |
| Languages | 7 | EN, FR, ES, PT-BR, RU, TR, DE |
| Database | Optional | SQLite, MySQL, MariaDB, PostgreSQL |
| Developer APIs | 2 | BossBar + WaveArena frameworks (extractable, zero plugin imports) |

---

## What v5 adds on top

### Core v5

- **Void Realm** — a new dimension with a floating-island arena, home of the Golem Void.
- **Void Gauntlet** — 3-wave survival challenge inside the Void Realm; clear it to summon the Golem.
- **Pet Companion System** — 4 boss pets, 6 tiers (D → SS). Mount at Tier C, Tier S element wards, Tier SS auras, and an Equip / Ghost mode that activates the perk without spawning the pet.
- **Temporal Portals** — random particle portals lead to three challenge arenas (Canopy / Oakwood / Eldergrove).
- **Eldergrove Despot** — caster elite guarding Eldergrove Hollow with Ice Bolt / Fire Blast / Lightning Strike + a spiked-shield melee block.
- **Native Journal** — 7-tab unified UI (Bounty Board, Bestiary, Achievements, Featured Servers, Leaderboard, Wiki, Statistics) with paginated lists, filter chips, claim flow.
- **Endgame Journal Book** — craftable item that opens the Journal directly on right-click (2× Light Hide + 4× Sticks at the Workbench).
- **WaveArena framework** — generic wave engine powering Warden Trials and the Void Gauntlet, extractable for third-party mods.
- **BossBar redesign** — shared thematic bar across all bosses + elites, with proximity show/hide and cross-mod focus coordinator.
- **Endgame Gateway** — craftable portal block that swaps to its Frozen / Swamp / Void variant depending on the key.
- **Spear Pickup** — thrown spears drop as pickable items at the landing point (100 % return).

### Update 5 (v5.2.x) highlights

- **Hytale Update 5 (≥ 0.5.0) full compatibility** — every API call migrated, native multi-HUD adopted (MultipleHUD no longer required).
- **Localized item names** in every supported language (FR / ES / PT-BR / RU / TR / DE).
- **Shared Loot** — every player who participated in a co-op mob kill inside a dungeon gets their own independent loot roll. Extensible via `Shared_Loot.json`.
- **Bossbar Themes JSON** — third-party mods register custom boss bars with full auto-tracking (phase transitions, enrage, target switching, KB suppression) via `Bossbar_Themes.json`.
- **Custom Achievements JSON** — server owners define their own achievements in `CustomAchievements/*.json` without writing Java; 11 trigger types cover the common cases. See [Achievements](achievements).
- **Premium licensing system** — Ed25519-signed tokens unlock optional features (overworld bosses, ad-free Journal, full rebranding). Sub on Patreon, apply via `/eg config` → License tab.
- **Prisma Mace** — vanilla shipped the model + texture but no item; now a proper Legendary endgame weapon with Groundslam signature.
- **Dragon Frost Freezing Breath** — new cone breath attack with dedicated animation, particles and SFX.
- **Frost Dragon ride-and-fly hybrid** + **mounted combat** (Pet Commander) + **breath** (Frostbite Blade) at Tier B+.
- **Featured Servers tab** — daily-rotating partner server list with tag filter chips, per-server accent color, Patreon partnership CTA.
- **Wiki tab** — one-click external documentation link, replaces the older kill-gated Lore tab.
- **Full weapon tier rebalance** — clean +30% damage step at every tier; Frost Dragon damage pulled back to survivable values.
- **EndlessLeveling double-scaling fix** — when EL is detected, EndgameQoL defers party + level scaling to EL entirely.
- **Shears silk-touch every plant block** — bramble moss, bushes, leaves, grass variants, moss, cobwebs, etc.

### Update 5 — Frost Dragon mount package (5.1.x)

- **Ride-and-fly hybrid** (Tier B+) — sprint to climb, look around to steer, glide when not sprinting. Stamina auto-tops with Flocon Currency mid-flight.
- **Pet Commander mounted combat** — melee at Tier C+ (8 mana per swing), ranged Frost Bolt at Tier B+ (25 mana per shot).
- **Frostbite Blade breath** — at Tier A+, continuous frost breath cone from the dragon's mouth aimed at the rider's crosshair.

---

## Material progression

| # | Tier | Source | Notable on |
| :---: | --- | --- | --- |
| 1 | Adamantite | Vanilla survival cap | Starter endgame gear |
| 2 | Mithril | Frozen Dungeon, Oakwood Warlord, Eldergrove Despot | Mana regen on armor |
| 3 | Onyxium | Swamp Dungeon, Golem Void | HP regen on armor |
| 4 | Prisma | Golem Void only | Unique signature attack on every weapon |

Prisma is exclusive to the Void Realm. Eldergrove Hollow and Oakwood Refuge drop Onyxium, never Prisma.

---

## Getting started

1. **Install the plugin** — Download from CurseForge and drop the JAR into your server's `Mods/` folder. See the [Installation Guide](installation) for required dependencies.
2. **Gear up** — Gather Adamantite ore and craft your first endgame armor and weapons at the Endgame Bench. Trade with Vorthak at the Forgotten Temple for shortcuts.
3. **Dungeon run** — Craft a key, place an Endgame Gateway, and activate it. Recommended progression: Frozen → Swamp → Void Realm.
4. **Master the endgame** — Complete bounties, unlock achievements, fill the bestiary, raise boss pets to Tier SS, and push through the Warden Trials.

---

## Quick links

- [Installation](installation) — setup, requirements, dependencies
- [Bosses & Elites](bosses-elites) — phases, mechanics, loot
- [Void Realm](void-realm) — the new dimension and the Golem Void
- [Temporal Portals](temporal-portals) — three challenge arenas
- [Pets](pets) — D → SS progression, perks, mounts
- [Items & Weapons](items-weapons) — full catalogue
- [Bounty Board](bounty-board) — daily and weekly quests
- [Achievements](achievements) — 51 built-in achievements across 8 categories + custom JSON system for server owners
- [Commands](commands) — slash commands and permissions
- [Developer API](api) — BossBar + WaveArena frameworks
