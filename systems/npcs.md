---
title: NPCs
description: All endgame NPCs with stats, attacks, and locations.
order: 9
published: true
---

# NPCs & Mobs

Custom NPCs in Zone 4 (using unused vanilla models / animations) plus enhanced versions of vanilla mobs whose damage was broken in vanilla.

## Bosses & solo elites

| NPC | HP | Location | Notes |
| --- | ---: | --- | --- |
| <img src="https://raw.githubusercontent.com/lewai1/endgameqolwiki/main/images/mobs/Dragon_Frost.png" width="38" style="vertical-align:middle;margin-right:8px;"> Dragon Frost (boss) | 1 400 | Frozen Dungeon arena | 3-phase fly / walk with alternating immunity. Drops Dragon Heart. |
| <img src="https://raw.githubusercontent.com/lewai1/endgameqolwiki/main/images/mobs/Hedera.png" width="38" style="vertical-align:middle;margin-right:8px;"> Hedera (boss) | 1 800 | Swamp Dungeon arena | 3-phase poison + roots boss. Drops Hedera Gem. |
| <img src="https://raw.githubusercontent.com/lewai1/endgameqolwiki/main/images/mobs/Golem_Void.png" width="38" style="vertical-align:middle;margin-right:8px;"> Golem Void (boss) | 3 500 | Void Realm arena (post-Gauntlet) | Tankiest boss, 3 phases. KB-immune leap attack. Drops Voidheart, Onyxium Bars. |
| <img src="https://raw.githubusercontent.com/lewai1/endgameqolwiki/main/images/mobs/Dragon_Fire.png" width="38" style="vertical-align:middle;margin-right:8px;"> Dragon Fire (elite) | 1 000 | Volcanoes — centered on gold-block deposits | Fireball projectile (80-block range), 360° stomp AOE, melee swing (27 Physical + 10 Fire). Effectively knockback-immune (KB scale 0.05). |

See [Bosses & Elites](bosses-elites) for full attack tables, phase thresholds, and counter strategies. See the dungeon pages for arena layouts and access keys.

## Zone 4 — Wastes

| NPC | HP | Speed | Damage | Notes |
| --- | ---: | :---: | --- | --- |
| <img src="https://raw.githubusercontent.com/lewai1/endgameqolwiki/main/images/mobs/Ghoul.png" width="38" style="vertical-align:middle;margin-right:8px;"> Ghoul | 193 | 10 | 70 Physical | Fast undead predator. Bite (2.5 m range, 60° arc), moderate knockback. Day & night. |
| <img src="https://raw.githubusercontent.com/lewai1/endgameqolwiki/main/images/mobs/Zombie_Aberrant.png" width="38" style="vertical-align:middle;margin-right:8px;"> Zombie Aberrant | 400 | 10 | 119 Physical | High single-hit damage. Drops Voidheart (1) and Adamantite Bar (1–2). Day & night, weight 2. |
| <img src="https://raw.githubusercontent.com/lewai1/endgameqolwiki/main/images/mobs/Onyxium_Encounter.png" width="38" style="vertical-align:middle;margin-right:8px;"> Onyxium Encounter | 700 | 6 | 85 Physical | Warrior in full Onyxium armor wielding Onyxium Daggers. **Passive until attacked.** Drops Onyxium Bar (2–4), Voidheart (50 %), Storm Hide (2–3, 25 %), rare Onyxium weapon (10 %), armor (5 %). Very rare spawn. |

## Zone 4 — Jungles

| NPC | HP | Speed | Damage | Notes |
| --- | ---: | :---: | --- | --- |
| <img src="https://raw.githubusercontent.com/lewai1/endgameqolwiki/main/images/mobs/Saurian_Warrior.png" width="38" style="vertical-align:middle;margin-right:8px;"> Saurian Warrior | 220 | 6 | 45 Physical | Heavy-hitting melee. Slower but tankier. Daytime only (6:00–18:00). |
| <img src="https://raw.githubusercontent.com/lewai1/endgameqolwiki/main/images/mobs/Saurian_Hunter.png" width="38" style="vertical-align:middle;margin-right:8px;"> Saurian Hunter | 180 | 8 | 65 Physical | Mid-speed skirmisher. Daytime only. |
| <img src="https://raw.githubusercontent.com/lewai1/endgameqolwiki/main/images/mobs/Saurian_Rogue.png" width="38" style="vertical-align:middle;margin-right:8px;"> Saurian Rogue | 150 | 10 | 55 Physical | Fastest variant. 70° arc, 0.3 s attack speed. Daytime only. |
| <img src="https://raw.githubusercontent.com/lewai1/endgameqolwiki/main/images/mobs/Alpha_Rex.png" width="38" style="vertical-align:middle;margin-right:8px;"> Alpha Rex (elite) | 1000 | 9 | 80 Physical | Fast aggressive predator with heavy knockback. Rare spawn (weight 0.5). 350 XP. Drops Apex Sovereign Leather (2–3), Alpha Trex Meat (3–6). |

## Enhanced vanilla mobs

These are vanilla NPCs with corrected damage values (vanilla `InteractionVars` bug caused them to deal only 5 damage).

| NPC | Damage | Drops | Spawns |
| --- | --- | --- | --- |
| Outlander Brute | 35 (swings), 55 (ground slam), 40 (stomp + AOE slow), 25 (grab) | Adamantite Bar (2–4), Shadoweave Fabric Scrap (1–4), Mithril Bar (1–2, 25 %) | Vanilla |
| Scarak Broodmother | 25 Physical + 50 % slow 3 s (venom projectiles) | Adamantite Bar (5–6) | Vanilla |
| Scarak Fighter | 20 Physical (corrected from vanilla 5) | Sturdy Chitin (1–2), Venom Sac (30 %) | Vanilla |

## Spawn locations

**Zone 4 Wastes** (day & night)

| NPC | Weight |
| --- | ---: |
| Ghoul | 4 |
| Zombie Aberrant | 2 |
| Onyxium Encounter | 1 (passive) |

**Zone 4 Jungles** (daytime 6:00–18:00)

| NPC | Weight |
| --- | ---: |
| Saurian Warrior | 1 |
| Saurian Hunter | 1 |
| Saurian Rogue | 1 |
| Alpha Rex | 0.5 (rare) |

**Frozen biome** (around the Frozen Dungeon and snow biomes)

| NPC | Notes |
| --- | --- |
| Frost Yeti | Wandering ambient spawn (also appears inside the Frozen Dungeon). |

Enhanced mobs (Scarak Fighter, Broodmother, Outlander Brute) use vanilla spawn locations — no custom spawns.

Solo-spawn elites (Dragon Fire) use scripted overworld spawns rather than biome weights — see [Bosses & Elites](bosses-elites).

## Swamp Dungeon

| NPC | HP | Damage / Notes | Drops |
| --- | ---: | --- | --- |
| <img src="https://raw.githubusercontent.com/lewai1/endgameqolwiki/main/images/mobs/Grooble.png" width="38" style="vertical-align:middle;margin-right:8px;"> Grooble | 250 | Physical. Burrowing beast that erupts from the ground. | Raw Wildmeat |
| <img src="https://raw.githubusercontent.com/lewai1/endgameqolwiki/main/images/mobs/Fen_Stalker.png" width="38" style="vertical-align:middle;margin-right:8px;"> Fen Stalker | 200 | 29 Physical. Swift amphibian predator. | Raw Wildmeat, Medium Hide |
| <img src="https://raw.githubusercontent.com/lewai1/endgameqolwiki/main/images/mobs/Spirit_Root.png" width="38" style="vertical-align:middle;margin-right:8px;"> Root Spirit | 200 | Nature damage. Elemental, manual-trigger spawn. | Swamp Currency |
| <img src="https://raw.githubusercontent.com/lewai1/endgameqolwiki/main/images/mobs/Swamp_Crocodile.png" width="38" style="vertical-align:middle;margin-right:8px;"> Swamp Crocodile | 900 | Elite. Heavy bite + tail swipe. Drops the Crocodile Scale required for the Hedera Key. | Crocodile Scale (guaranteed) |
| <img src="https://raw.githubusercontent.com/lewai1/endgameqolwiki/main/images/mobs/Bramble_Elite.png" width="38" style="vertical-align:middle;margin-right:8px;"> Bramble Elite | 550 | Bite 90 + Swipe 70 + Poison T3. Mini-boss with elite bar. | Hedera's Bramble (guaranteed), Swamp Currency |

Plus the trader **Morghul** (non-hostile NPC) — see [Swamp Dungeon → Morghul](swamp-dungeon) for inventory.

## Frozen Dungeon

| NPC | HP | Damage / Notes | Drops |
| --- | ---: | --- | --- |
| <img src="https://raw.githubusercontent.com/lewai1/endgameqolwiki/main/images/mobs/Rat_Frost.png" width="38" style="vertical-align:middle;margin-right:8px;"> Ice Rat | 35 | Physical. Smallest frost mob, fastest. | 2–3 Flocons |
| <img src="https://raw.githubusercontent.com/lewai1/endgameqolwiki/main/images/mobs/Toad_Frost.png" width="38" style="vertical-align:middle;margin-right:8px;"> Frost Toad | 124 | 18–35 Physical. | 3–5 Flocons |
| <img src="https://raw.githubusercontent.com/lewai1/endgameqolwiki/main/images/mobs/Frost_Feran.png" width="38" style="vertical-align:middle;margin-right:8px;"> Frost Feran | 150 | 35 Physical. Frost-touched warrior with bone sword. | 4–6 Flocons, Medium Hides, Cobalt Bars |
| <img src="https://raw.githubusercontent.com/lewai1/endgameqolwiki/main/images/mobs/Spirit_Frost.png" width="38" style="vertical-align:middle;margin-right:8px;"> Frost Spirit | 200 | Ice damage. Elemental, manual-trigger spawn. | 5–8 Flocons |
| <img src="https://raw.githubusercontent.com/lewai1/endgameqolwiki/main/images/mobs/Golem_Crystal_Frost.png" width="38" style="vertical-align:middle;margin-right:8px;"> Frost Crystal Golem | 300 | Physical. Heavy melee. | 8–12 Flocons |
| <img src="https://raw.githubusercontent.com/lewai1/endgameqolwiki/main/images/mobs/Yeti.png" width="38" style="vertical-align:middle;margin-right:8px;"> Frost Yeti | 400 | Physical. Also spawns in the Frozen biome (overworld). | 10–15 Flocons |

Plus the trader **Korvyn** (non-hostile NPC) — see [Frozen Dungeon → Korvyn](frozen-dungeon) for inventory.

## Void Realm

These mobs spawn only inside the Void Gauntlet wave arena (Void Realm dimension) — they do not appear in the open world.

| NPC | Notes | Drops |
| --- | --- | --- |
| <img src="https://raw.githubusercontent.com/lewai1/endgameqolwiki/main/images/mobs/Void_Frog.png" width="38" style="vertical-align:middle;margin-right:8px;"> Void Frog | Physical leap attacker. Wave filler. | Voidheart |
| <img src="https://raw.githubusercontent.com/lewai1/endgameqolwiki/main/images/mobs/Golem_Eye_Void.png" width="38" style="vertical-align:middle;margin-right:8px;"> Golem Eye Void | Stationary ranged. Fires void orbs. | Voidheart |

See [Void Realm](void-realm) for the full wave composition.

## Temporal Portals

Mobs exclusive to Temporal Portal instances. Canopy Shrine has no enemies (exploration only).

| NPC | Location | Notes |
| --- | --- | --- |
| <img src="https://raw.githubusercontent.com/lewai1/endgameqolwiki/main/images/mobs/Oakwood_Warlord.png" width="38" style="vertical-align:middle;margin-right:8px;"> Oakwood Warlord (elite) | Oakwood Refuge | Mid-tier elite. On death, summons one **Oakwood Warlord (small)**. |
| <img src="https://raw.githubusercontent.com/lewai1/endgameqolwiki/main/images/mobs/Oakwood_Warlord_Small.png" width="38" style="vertical-align:middle;margin-right:8px;"> Oakwood Warlord (small) | Oakwood Refuge | Spawned only when the parent Warlord dies. Faster, lower HP, distinct moveset (Charge Strike, Flip Cast, Kick, Bite). |
| <img src="https://raw.githubusercontent.com/lewai1/endgameqolwiki/main/images/mobs/Eldergrove_Despot.png" width="38" style="vertical-align:middle;margin-right:8px;"> Eldergrove Despot (elite) | Eldergrove Hollow | Hard-tier elite. |

See [Bosses & Elites](bosses-elites) for full attack tables.

## Warden's Trial exclusive

These NPCs only appear in Warden's Trial waves — they do not spawn in the open world.

| NPC | HP | Speed | Damage | Notes |
| --- | ---: | :---: | --- | --- |
| <img src="https://raw.githubusercontent.com/lewai1/endgameqolwiki/main/images/mobs/Werewolf.png" width="38" style="vertical-align:middle;margin-right:8px;"> Werewolf | 283 | 10 | 90 Physical | Fast. Grab (3 m, 80° arc) with extended vertical hitbox. Strong knockback. |
| <img src="https://raw.githubusercontent.com/lewai1/endgameqolwiki/main/images/mobs/Shadow_Knight.png" width="38" style="vertical-align:middle;margin-right:8px;"> Shadow Knight | 400 | 6 | 150 Physical | Tankiest and hardest-hitting. Heavy knockback. Extremely dangerous in groups. |
| <img src="https://raw.githubusercontent.com/lewai1/endgameqolwiki/main/images/mobs/Necromancer_Void.png" width="38" style="vertical-align:middle;margin-right:8px;"> Void Necromancer | 500 | 5 | 35 (void orbs ranged) / 55 (melee fallback) | Spellcaster with Demon Spellbook. Summons 6 random skeletons. |
| <img src="https://raw.githubusercontent.com/lewai1/endgameqolwiki/main/images/mobs/Goblin_Duke.png" width="38" style="vertical-align:middle;margin-right:8px;"> Goblin Duke | 350 | 6 | 75 Physical | Goblin leader with Doomed Club. Wide 90° arc. Immune to Goblin and Self damage. High knockback. |
