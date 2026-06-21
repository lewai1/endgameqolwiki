---
title: Items & Weapons
description: All weapons, tools, consumables, boss materials, and crafting benches.
order: 0
published: true
---

# Items & Weapons

40+ weapons, 8 tools, consumables, boss materials, and crafting benches.

**v5.2.x Prisma weapon line** — the Prisma tier is now reworked end to end. The **Staff** (void-mage kit), **Shortbow** (Hardened volley + abilities), **Spear** (boomerang stance-switcher) and **Longsword** (greatblade + execute) join the reworked **Daggers** (assassin kit), **Sword**, **Mace** and **Frostbite Blade**. Every Prisma weapon sits one notch above Onyxium, carries the **Signature** damage class (so the Prisma armor set's signature/charged bonuses boost it), and is crafted at the Endgame Bench (Tier 5).

**v5.0.0 reworks** — Blazefist / Frostbite apply the vanilla `Burn` / `Freeze` (full polish: screen FX, sounds, icons), replacing the old custom status effects.

**Creative Library** — All items are available in Creative Mode under the **Endgame** category (7 subcategories: Weapons, Armor, Tools, Materials, Consumables, Portals, Misc).

**Endgame Journal Book** — rare item that opens the Journal directly on right-click (same UI as `/eg journal`). Crafted at the vanilla Workbench from **2× Light Hide + 4× Sticks**.

## Special weapons

Legendary weapons with unique signature abilities, passives, and special effects.

### Prisma Sword — Legendary

<img src="https://raw.githubusercontent.com/lewai1/endgameqolwiki/main/images/icons/Endgame_Sword_Prisma.png" width="72" style="float:right;margin:0 0 8px 14px;"> The pinnacle sword. Heavy melee with two prismatic active abilities.

| Slot | Ability | Cost |
| --- | --- | --- |
| Primary | Sword swings + thrust (vanilla chain) | Stamina |
| Secondary | Guard / block (vanilla) | Stamina |
| Ability1 (signature) | **Prismatic Judgment** — ground slam | 100 SE |
| Ability3 | **Prismatic Beam** — ranged projectile | 80 Mana |

**Base melee damage:** Swing 38–42 Physical, Swing Down 72, Thrust 105.

| Attack | Description | Damage |
| --- | --- | --- |
| Prismatic Beam | ~20-block projectile, AOE 3-block radius on impact | 100 Physical |
| Prismatic Judgment | 10-block AOE burst + knockup Force 22 + Prisma Shatter (60 % slow 4 s) | 220–280 Physical |

<div style="clear:both;"></div>

### Prisma Daggers — Legendary

<img src="https://raw.githubusercontent.com/lewai1/endgameqolwiki/main/images/icons/Endgame_Daggers_Prisma.png" width="72" style="float:right;margin:0 0 8px 14px;"> Assassin-class daggers with a full stealth-and-burst kit: a defensive Vanish, a two-beat Storm signature, and Mana-gated Empower / Dash finishers.

| Slot | Ability | Cost |
| --- | --- | --- |
| Primary | Dagger swings + stabs + pounce (builds Signature Energy) | Stamina |
| RMB | **Vanish** — 0.4 s i-frames + back-dash + AOE slash; primes a ×2.5 Stealth strike | 10 Stamina |
| Ability1 (signature) | **Storm** — two-beat prismatic tempest | 100 SE |
| Ability2 | **Empower** — next basic ×2 dmg + 1 s slow | 25 Mana |
| Ability3 | **Dash** — three piercing lunges | 85 Mana |

**Base melee damage:** Swing 15–19, Stab 48–55 (head 62–72), Pounce 125–152 (head 198). 30 % headshot bonus on stabs; backstab adds ~50 % (rear 180°).

| Attack | Description | Damage |
| --- | --- | --- |
| Vanish | i-frame smoke-step + AOE slash (Range 3) as you blink; next basic crits ×2.5 | 45 + Stealth |
| Storm | Wind-up → AOE strike (Range 5) + ground shockwave & 2.5 s slow → knockback finisher (Range 4) | 250 + 185 ≈ 435 |
| Dash | Three quick piercing blink-stabs | 70 × 3 = 210 |

**Combo flow:** Vanish → ×2.5 backstab → Empower → Dash → empowered hit → Storm. Vanish is gated by Stamina (defensive), Empower / Dash by Mana — so dodging never starves your burst.

<div style="clear:both;"></div>

### Prisma Mace — Legendary

<img src="https://raw.githubusercontent.com/lewai1/endgameqolwiki/main/images/icons/Weapon_Mace_Prisma.png" width="72" style="float:right;margin:0 0 8px 14px;"> Heavy two-handed mace. Vanilla Hytale shipped the model and texture but no usable item — the v5.2.0 release wires it up as a proper endgame weapon. Built for crowd-control via the Groundslam signature.

| Slot | Ability | Cost |
| --- | --- | --- |
| Primary | Mace swings (vanilla chain) | Stamina |
| Secondary | Charged swing | Stamina |
| Ability1 (signature) | **Groundslam** — AOE crash with damage variance | 100 SE |

**Base melee damage:** Swing 80 Physical, Charged 120.

| Attack | Description | Damage |
| --- | --- | --- |
| Groundslam | Leaping AOE crash **+ a landing shockwave** — radial knockback (Force 12) throws back any enemy within ~4 blocks you didn't directly hit (≈ 20 splash) | 260–320 Physical |

**Stats:** +200 Mana, +25 Stamina, +30 Signature Energy. Item Level 65. 320 durability. Signature energy glow at 25%+, full glow + ModelVFX at 100%.

**Recipe:** 14× Prisma Bar + 4× Prismic Leather + 2× Emerald Gem at the Endgame Bench (Tier 5).

<div style="clear:both;"></div>

### Prisma Staff — Legendary

<img src="https://raw.githubusercontent.com/lewai1/endgameqolwiki/main/images/icons/Endgame_Weapon_Staff_Prisma.png" width="72" style="float:right;margin:0 0 8px 14px;"> Void-mage staff — the first true caster endgame weapon. A buildable Signature Energy bar gates the beam, so the laser is *earned*, not spammed. Every void ability leaves Corruption.

| Slot | Ability | Cost |
| --- | --- | --- |
| Primary | **Void Orb** — charged projectile, detonates on impact (~45 + 20 splash), builds Signature Energy on hit | 40 Mana |
| Secondary | **Void Singularity** — pull enemies into an inward vortex, then erupt (Range 7, 48) | 35 Mana |
| Ability1 (signature) | **Void Beam** — channeled prismatic ray down your crosshair (~90 DPS, 2.5 s) | Full SE |
| Ability2 | **Void Bolts** — rapid 3-bolt volley (22 each) | 30 Mana |
| Ability3 | **Void Nova** — instant AoE pulse + knockback (Range 6, 38) | 25 Mana |

**Signature loop:** land Orb / Bolt / Nova hits to fill the Signature Energy bar (≈ 2 Orb hits or one Bolt volley), then unleash Void Beam. Item shows a "ready" glow at 100 %.

**Stats:** +250 Mana, +30 Signature Energy. Item Level 60. **Recipe:** 10× Prisma Bar + 4× Prismic Leather + 2× Emerald Gem + 3× Stick at the Endgame Bench (Tier 5).

<div style="clear:both;"></div>

### Prisma Shortbow — Legendary

<img src="https://raw.githubusercontent.com/lewai1/endgameqolwiki/main/images/icons/Endgame_Shortbow_Prisma.png" width="72" style="float:right;margin:0 0 8px 14px;"> Hardened-arrow marksman bow. Loads **Hardened Arrows** before Crude ones; while Hardened Arrows are carried they grant **+20 % bow/crossbow damage**.

| Slot | Ability | Cost |
| --- | --- | --- |
| Primary | Charged shot — 18 → 65 by draw (head ≤ 90) | Stamina + arrow |
| Secondary | **Void Dash** — backward dodge-hop for kiting | 15 Stamina |
| Ability1 (signature) | **Signature Volley** — land charged shots to fill the bar, then loose a spread of prismatic arrows (48 each) | Full SE |
| Ability2 | **Power Shot** — heavy single shot with strong knockback (75) | 15 Stamina |
| Ability3 | **Explosive Shot** — arrow that detonates on impact (AoE ~3.5-blk, 22) | 12 Stamina |

**Stats:** +200 Mana, +30 Signature Energy, +25 Stamina. Item Level 65. 300 durability. **Recipe:** 11× Prisma Bar + 4× Prismic Leather + 2× Emerald Gem at the Endgame Bench (Tier 5).

<div style="clear:both;"></div>

### Prisma Spear — Legendary

<img src="https://raw.githubusercontent.com/lewai1/endgameqolwiki/main/images/icons/Endgame_Spear_Prisma.png" width="72" style="float:right;margin:0 0 8px 14px;"> Stance-switching boomerang spear. A fast, flashy spinning melee combo that applies **Prisma Resonance**, with two stances — **Combat** and **Throw** (the glow shifts purple → cyan).

| Slot | Ability | Cost |
| --- | --- | --- |
| Primary | Spinning melee combo (builds Signature Energy) | Stamina |
| Secondary | Block | Stamina |
| Ability1 (Combat) | **Cyclone** (signature) — a spinning energy storm around you | SE |
| Ability1 (Throw) | **Throw** — a dead-straight spear that pierces every enemy in its path, then **boomerangs back** to your inventory | — |
| Ability2 | **Switch stance** — toggle Combat ⇄ Throw | Free |
| Ability3 (Combat) | **Impale** — a lunging pierce that closes the gap + shatters armor | Mana |

**Stats:** +200 Mana, +30 Signature Energy, +25 Stamina. Item Level 65. **Recipe:** 10× Prisma Bar + 4× Prismic Leather + 2× Emerald Gem at the Endgame Bench (Tier 5).

<div style="clear:both;"></div>

### Prisma Longsword — Legendary

<img src="https://raw.githubusercontent.com/lewai1/endgameqolwiki/main/images/icons/Endgame_Longsword_Prisma.png" width="72" style="float:right;margin:0 0 8px 14px;"> Prismatic greatblade. Heavy, weighty swings with a charging signature slam and a low-HP execute.

| Slot | Ability | Cost |
| --- | --- | --- |
| Primary | Heavy swing combo (42–66) | Stamina |
| Secondary | Block | Stamina |
| Ability1 (signature) | **Signature Slam** — hold to charge a sweeping slash into a leaping crashing slam (wide AOE + ground shockwave) | SE |
| Ability2 | **Execute** — short dash strike that hits harder the lower the target's HP (up to ~3× near death); heavily reduced vs bosses | SE |

**Base melee damage:** Swings 42–66, Charged 92 / Stab 112. **Signature:** Slash 80 → **Slam 109**.

**Stats:** +200 Mana, +30 Signature Energy, +25 Stamina. Item Level 65. 350 durability. **Recipe:** 14× Prisma Bar + 4× Prismic Leather + 2× Emerald Gem at the Endgame Bench (Tier 5).

<div style="clear:both;"></div>

### Vine-Twined Daggers — Legendary

<img src="https://raw.githubusercontent.com/lewai1/endgameqolwiki/main/images/icons/Weapon_Daggers_Hedera.png" width="72" style="float:right;margin:0 0 8px 14px;"> Nature-themed daggers (Hedera-themed daggers). Every hit applies **Poison** (5 dmg/tick × 4 ticks = 20 total) and **Lifesteal** (8 % of damage dealt heals the wielder).

<div style="clear:both;"></div>

### Pet Commander — Legendary command tool (v5.0.6)

<img src="https://raw.githubusercontent.com/lewai1/endgameqolwiki/main/images/icons/Endgame_Staff_Pet_Commander.png" width="72" style="float:right;margin:0 0 8px 14px;"> Not a combat weapon. Left-click fires a fast visual ray (zero damage, zero mana, zero durability) and orders your pet to engage whatever you are aiming at within 30 blocks. Right-click opens the Pet Companion menu.

**Mounted on Frost Dragon** — wielding this staff enables the dragon's auto-attack loop: it strikes where you aim on cooldown. Tier C+ unlocks melee (8 mana per swing). Tier B+ adds ranged Frost Bolt auto-fire when airborne or out of melee range (25 mana per shot). Damage scales with the pet tier (1.4× D → 3.5× SS) and stacks with EndlessLeveling STRENGTH / SORCERY. Switching to any other hotbar slot stops the loop.

| Slot | Ability | Cost |
| --- | --- | --- |
| Primary | **Commander Ping** — fast ray + pet target snap (aim cone ~50°) | None |
| Secondary | Open `/eg pet` menu | None |
| Mounted (Frost Dragon, C+) | Auto-attack melee on cooldown | 8 mana per swing |
| Mounted (Frost Dragon, B+) | Auto-attack ranged Frost Bolt when airborne / out of melee | 25 mana per shot |

**Recipe:** 6× Mithril Bar + 2× Stick at the Endgame Bench (Misc category, Tier 2, 3 s craft).

If pets are globally disabled or the current world is in the `/eg admin petblock` list, both actions fail silently with a chat notice.

<div style="clear:both;"></div>

### Frostbite Blade — Epic

<img src="https://raw.githubusercontent.com/lewai1/endgameqolwiki/main/images/icons/Weapon_Sword_Frost.png" width="72" style="float:right;margin:0 0 8px 14px;"> First zone-control weapon (v5.0.0). Ice weapon obtained from the Frozen Dungeon. Purchase from Korvyn for **45 Flocons**. Basic hits apply vanilla **Freeze**.

| Slot | Ability | Cost |
| --- | --- | --- |
| Primary | Sword swings (applies Freeze on hit) | Stamina |
| Ability1 (signature) | **Blizzard Stance** — 3 mobile AOE pulses | 100 SE |
| Ability3 | **Ice Field** — 3 AOE slow pulses (pure CC) | 50 Mana |

| Attack | Description | Damage |
| --- | --- | --- |
| Blizzard Stance | 3 mobile AOE pulses, final pulse freezes | 80 × 3 = 240 Ice |
| Ice Field | 3 AOE slow pulses — pure crowd control | Zone CC |

<div style="clear:both;"></div>

## Standard weapons

Tiered weapon progression from early-game to endgame materials. All crafted at the Weapon Bench or Endgame Bench.

| Type | Materials available |
| --- | --- |
| Sword | Bone Frost, Mithril, Onyxium, Frostbite, Prisma |
| Daggers | Mithril, Onyxium, Vine-Twined, Prisma |
| Longsword | Copper, Iron, Thorium, Cobalt, Adamantite, Mithril, Onyxium, Prisma |
| Spear | Crude, Copper, Iron, Thorium, Cobalt, Adamantite, Mithril, Onyxium, Prisma |
| Staff | Copper, Iron, Thorium, Cobalt, Adamantite, Mithril, Onyxium + Crystal Ice, Crystal Flame, Prisma |
| Shortbow | Mithril, Onyxium, Prisma |
| Shield | Mithril, Onyxium |
| Battleaxe | Mithril, Onyxium |
| Mace | Onyxium, Prisma |

## Tools

8 tools spanning pickaxes, hatchets, and shovels.

| Tool | Notes |
| --- | --- |
| <img src="https://raw.githubusercontent.com/lewai1/endgameqolwiki/main/images/icons/Endgame_Pickaxe_Prisma.png" width="30" style="vertical-align:middle;margin-right:6px;"> Prisma Pickaxe | 3×3 area break (toggle via Ability3). Instant mining on rocks and ores. (Void Pocket removed in v4.0.6.) |
| <img src="https://raw.githubusercontent.com/lewai1/endgameqolwiki/main/images/icons/Prisma_Hatchet_Icon.png" width="30" style="vertical-align:middle;margin-right:6px;"> Prisma Hatchet | 3×3 area break for wood and soft blocks. Does not break benches or furniture. |
| <img src="https://raw.githubusercontent.com/lewai1/endgameqolwiki/main/images/icons/Tool_Pickaxe_Mithril.png" width="30" style="vertical-align:middle;margin-right:6px;"> Mithril Pickaxe | Mid-tier pickaxe |
| <img src="https://raw.githubusercontent.com/lewai1/endgameqolwiki/main/images/icons/Tool_Pickaxe_Onyxium.png" width="30" style="vertical-align:middle;margin-right:6px;"> Onyxium Pickaxe / Hatchet | High-tier pickaxe and hatchet |
| <img src="https://raw.githubusercontent.com/lewai1/endgameqolwiki/main/images/icons/Tool_Shovel_Iron.png" width="30" style="vertical-align:middle;margin-right:6px;"> Shovels | Iron, Thorium, Cobalt (3 tiers) |
| Shears (Plant Silk-Touch) | Vanilla shears of any tier now silk-touch **every** plant block — bramble moss, bushes, leaves, grass variants, moss, cobwebs, etc. — so the full decorative set is obtainable for builders. Hand-breaking still drops vanilla materials. Applies automatically to every plant family (works with future plant additions). A utility on the vanilla shears item, not a new endgame tool. |

## Consumables — Combat Potions

A full reworked **Combat Potions** line, crafted at the Alchemy bench's *Combat Potions* tab. Four stats, each in an **instant** restore and an **over-time regen** variant, with grade-scaled quality (Common → Uncommon → Rare → Epic).

| Stat | Grades | Variants |
| --- | --- | --- |
| **Health** | Lesser · Small · Normal · Greater | Instant restore + Regen |
| **Mana** | Small · Normal · Large | Instant restore + Regen |
| **Stamina** | Lesser · Small · Normal · Greater | Instant restore + Regen |
| **Signature** | Lesser · Small · Normal · Greater | Instant restore + Regen |
| **Antidote** *(Rare)* | — | Cures all poison tiers + grants temporary poison immunity |

**Tiered recipes** — the higher the grade, the rarer the ingredients: crystal shards at low tiers, **Concentrated Life Essence** at Rare, and a themed **gem** (Ruby · Sapphire · Emerald · Zephyr) at Epic. All gated by Alchemy bench tier (1 → 4).

## Crafting benches

| Bench | Purpose | Recipe |
| --- | --- | --- |
| Endgame Bench | Central crafting station with 3 upgrade tiers. Unlocks Onyxium / Prisma armor, portals, challenge items, accessories. | 2 Thorium Bars + 10 Wood + 5 Rock at the Workbench |
| <img src="https://raw.githubusercontent.com/lewai1/endgameqolwiki/main/images/icons/Bench_Weapon.png" width="30" style="vertical-align:middle;margin-right:6px;"> Weapon Bench | Dedicated weapon crafting (swords, daggers, longswords, spears, staves, bows, maces, battleaxes). | 2 Copper Bars + 10 Wood + 5 Rock at the Workbench |
| <img src="https://raw.githubusercontent.com/lewai1/endgameqolwiki/main/images/icons/Hedera_Autel.png" width="30" style="vertical-align:middle;margin-right:6px;"> Hedera Autel | Swamp-themed bench. The only bench that crafts the Hedera Key. | Found in the swamp biome |
| Salvage Bench | Break down unwanted gear to recover materials. Prisma and Onyxium items return ~50 % of their crafting cost. | — |

## Salvage system

Use the Salvage Bench to break down Prisma and Onyxium items. You recover approximately 50 % of the original crafting materials. The recommended way to recycle gear as you upgrade through material tiers.
