---
title: Armor & Accessories
description: 5 armor sets with passive bonuses and 6 trinket accessories.
order: 1
published: true
---

# Armor & Accessories

5 armor sets with passive bonuses, plus 6 trinket accessories with unique endgame effects.

## Armor sets

| Set | Tier | Mana regen / piece | HP regen / piece | Special |
| --- | :---: | :---: | :---: | --- |
| <img src="https://raw.githubusercontent.com/lewai1/endgameqolwiki/main/images/icons/Armor_Diving_Crude_Chest.png" width="30" style="vertical-align:middle;margin-right:6px;"> Diving Crude | Starter | — | — | Underwater breathing |
| <img src="https://raw.githubusercontent.com/lewai1/endgameqolwiki/main/images/icons/Armor_Adamantite_Chest.png" width="30" style="vertical-align:middle;margin-right:6px;"> Adamantite | 1 | — | — | Basic protection |
| <img src="https://raw.githubusercontent.com/lewai1/endgameqolwiki/main/images/icons/Armor_Mithril_Chest.png" width="30" style="vertical-align:middle;margin-right:6px;"> Mithril | 2 | 0.5/s | — | — |
| <img src="https://raw.githubusercontent.com/lewai1/endgameqolwiki/main/images/icons/Armor_Onyxium_Chest.png" width="30" style="vertical-align:middle;margin-right:6px;"> Onyxium | 3 | 0.75/s | 0.5/s | — |
| <img src="https://raw.githubusercontent.com/lewai1/endgameqolwiki/main/images/icons/Armor_Prisma_Chest.png" width="30" style="vertical-align:middle;margin-right:6px;"> Prisma | 4 | 1.0/s | 0.75/s | Fire + fall resistance |

**HP regen** activates 15 seconds after the last damage taken. Configurable by server admins.

**Mana regen** stacks per piece worn. You can mix armor sets and receive the sum of each individual piece's mana regen. There is no set bonus for wearing all four pieces of the same tier.

Each armor set consists of 4 pieces: Head, Chest, Hands, Legs.

## Trinket Pouch

<img src="https://raw.githubusercontent.com/lewai1/endgameqolwiki/main/images/icons/Endgame_Accessory_Pouch.png" width="72" style="float:left;margin:0 14px 8px 0;"> The Trinket Pouch is a portable container with 6 accessory slots. Place accessories inside to gain their passive bonuses.

<div style="clear:both;"></div>

| Property | Value |
| --- | --- |
| Slots | 6 accessory slots |
| Config toggle | `AccessoriesEnabled` (true) |
| Recipe | 6× Storm Leather + 2× Voidheart + 4× Mithril Bars (Endgame Bench Tier 2) |

## Accessories

Six unique accessories, each obtained from different endgame content. Place them in the Trinket Pouch to activate.

| Accessory | Effect | Source |
| --- | --- | --- |
| <img src="https://raw.githubusercontent.com/lewai1/endgameqolwiki/main/images/icons/Endgame_Accessory_Frostwalkers.png" width="30" style="vertical-align:middle;margin-right:6px;"> Frostwalkers | Walk on water by creating temporary ice (2-block radius). Ice melts shortly after you leave. | Frozen Dungeon chest (25 %) |
| <img src="https://raw.githubusercontent.com/lewai1/endgameqolwiki/main/images/icons/Endgame_Accessory_Ocean_Striders.png" width="30" style="vertical-align:middle;margin-right:6px;"> Ocean Striders | Double swimming speed when fully submerged. | Humpback Whale drop (15 %) |
| <img src="https://raw.githubusercontent.com/lewai1/endgameqolwiki/main/images/icons/Endgame_Accessory_Void_Amulet.png" width="30" style="vertical-align:middle;margin-right:6px;"> Void Amulet | Survive a lethal hit at 1 HP with 3 s of invulnerability. Reusable — **not** consumed, but has a 5-min cooldown before it can trigger again. | Golem Void drop (15 %) |
| <img src="https://raw.githubusercontent.com/lewai1/endgameqolwiki/main/images/icons/Endgame_Accessory_Blazefist.png" width="30" style="vertical-align:middle;margin-right:6px;"> Blazefist | Melee hits apply burn and trigger an AOE fire burst within 3 m. 50 dmg × 3 ticks (configurable). | Dragon Fire drop (15 %) |
| <img src="https://raw.githubusercontent.com/lewai1/endgameqolwiki/main/images/icons/Endgame_Accessory_Pocket_Garden.png" width="30" style="vertical-align:middle;margin-right:6px;"> Pocket Garden | HP regeneration **only when near farming crops**. Auto-fertilizes soil in a 5-block radius. Conditional regen — must be near crops. | Swamp Dungeon chest (20 %) |
| <img src="https://raw.githubusercontent.com/lewai1/endgameqolwiki/main/images/icons/Endgame_Accessory_Hedera_Seed.png" width="30" style="vertical-align:middle;margin-right:6px;"> Hedera Seed | When you take damage, 15 % chance to root the attacker for 2 s. Rooted enemies cannot move but can still attack. | Hedera drop (15 %) |

Removing an accessory from the Trinket Pouch immediately deactivates its effect. The Void Amulet is kept on trigger (it is not consumed) and simply goes on a cooldown before it can save you again. All accessories can be freely swapped without penalty.

## Storage

### Backpack upgrades

Your main backpack expands along a single ordered path — each step adds 9 slots:

**vanilla I → vanilla II → vanilla III → Endgame Backpack Upgrade** → **36 slots** total.

| Property | Value |
| --- | --- |
| Endgame Backpack Upgrade | +9 slots (27 → 36), one-time use |
| Recipe | 1× Voidheart + 8× Adamantite Bar + 8× Apex Sovereign Leather (Endgame Bench Tier 2) |
| Requirement | Memories Level 5, and the 3 vanilla upgrades applied first |

Upgrades must be applied **in order** — using the Endgame Backpack Upgrade out of sequence shows a "use the previous upgrade first" message.

### Endgame Backpack

<img src="https://raw.githubusercontent.com/lewai1/endgameqolwiki/main/images/icons/Endgame_Upgrade_Backpack_1.png" width="72" style="float:left;margin:0 14px 8px 0;"> A separate craftable storage bag with its **own 27-slot window**, fully independent of your main inventory. Right-click to open it (same UX as the Trinket Pouch); contents are saved per character.

<div style="clear:both;"></div>

| Property | Value |
| --- | --- |
| Slots | 27 (its own window) |
| Rarity | Epic (ItemLevel 3) |
| Recipe | 3× Voidheart + 6× Mithril Bar + 12× Apex Sovereign Leather (Endgame Bench Tier 3) |

Craft it once your main backpack is maxed (36 slots) for extra storage on top.
