---
title: Pets
description: 4 boss-tier pet companions — D → SS tier progression, per-pet mount rules, passive perks, and auras.
order: 3
published: true
---

# Pet Companions

<p class="eg-lead">4 boss-tier pets, unlocked by killing bosses, evolved from D → SS by feeding. Each pet has its own archetype, mount rules, Tier S perk, and Tier SS aura.</p>

<dl class="eg-defs">
  <dt>Command</dt><dd><code>/eg pet</code></dd>
  <dt>Permission</dt><dd><code>endgameqol.pet</code> (default: allow)</dd>
</dl>

<div class="eg-note">
<strong>Pet Details page.</strong> Each pet card has a <strong>Details</strong> button that opens a dedicated sub-page: large portrait, full ability progression D → SS with per-ability description and type tag (COMBAT / PASSIVE / AURA / UTILITY / MOBILITY), lock state, and inline Summon / Dismiss / Equip / Feed actions. Locked pets are previewable so you can see what unlocks at each tier before defeating the boss.
</div>

## Unlocking a pet

Each boss has a small chance to drop its pet spirit on kill. Default rates:

| Pet | Source | Default rate |
| --- | --- | :---: |
| Dragon Frost | Dragon Frost (Frozen Dungeon) | 30 % |
| Dragon Fire | Dragon Fire (volcano) | 30 % |
| Golem Void | Golem Void (Void Realm) | 30 % |
| Hedera | Hedera (Swamp Dungeon) | 30 % |

Drop chances are configurable in `/eg config` → **Pets** tab.

## Tier progression (D → SS)

Pets advance through 6 tiers by feeding them items in `/eg pet`. Each tier scales damage, health, and visual size.

<div class="eg-statsheet">
  <div class="eg-stat"><span class="eg-stat-label">Tier D</span><span class="eg-stat-val">×1.4 dmg</span></div>
  <div class="eg-stat"><span class="eg-stat-label">Tier C</span><span class="eg-stat-val">×1.8 dmg</span></div>
  <div class="eg-stat"><span class="eg-stat-label">Tier B</span><span class="eg-stat-val">×2.1 dmg</span></div>
  <div class="eg-stat"><span class="eg-stat-label">Tier A</span><span class="eg-stat-val">×2.5 dmg</span></div>
  <div class="eg-stat"><span class="eg-stat-label">Tier S</span><span class="eg-stat-val">×3.1 dmg</span></div>
  <div class="eg-stat"><span class="eg-stat-label">Tier SS</span><span class="eg-stat-val accent">×3.5 dmg</span></div>
</div>

| Tier | Damage | Health | Visual size |
| :---: | :---: | :---: | :---: |
| D  | 1.4× | 1.0× | base |
| C  | 1.8× | 1.2× | +5 % |
| B  | 2.1× | 1.4× | +10 % |
| A  | 2.5× | 1.6× | +20 % |
| S  | 3.1× | 1.8× | +30 % |
| SS | 3.5× | 2.0× | +40 % |

Damage was uniformly buffed +40 % across every tier in v5.0.6 so pets keep up with tanky mobs at high owner level. Health additionally scales with the owner's EndlessLeveling level when EL is installed (`1.0 + level × 0.05`).

## Per-pet archetypes

<div class="eg-profile">
  <div class="eg-profile-head">
    <h3 class="eg-profile-name">Dragon Frost</h3>
    <span class="eg-profile-tag">Mobility / Ice</span>
  </div>
  <div class="eg-profile-body">
<img src="https://raw.githubusercontent.com/lewai1/endgameqolwiki/main/images/mobs/Dragon_Frost.png" width="100" style="float:right;margin:0 0 8px 14px;">
<div class="eg-statsheet">
  <div class="eg-stat"><span class="eg-stat-label">Ground mount</span><span class="eg-stat-val">Tier C+</span></div>
  <div class="eg-stat"><span class="eg-stat-label">Ride + Fly</span><span class="eg-stat-val">Tier B+</span></div>
  <div class="eg-stat"><span class="eg-stat-label">Mounted melee</span><span class="eg-stat-val">Pet Commander · C+</span></div>
  <div class="eg-stat"><span class="eg-stat-label">Mounted ranged</span><span class="eg-stat-val">Pet Commander · B+</span></div>
  <div class="eg-stat"><span class="eg-stat-label">Mounted breath</span><span class="eg-stat-val">Frostbite Blade · A+</span></div>
  <div class="eg-stat"><span class="eg-stat-label">Tier S perk</span><span class="eg-stat-val accent">Frost Ward</span></div>
  <div class="eg-stat"><span class="eg-stat-label">Tier SS aura</span><span class="eg-stat-val">Freeze 5 blk</span></div>
</div>

<div class="eg-note">
<strong>Ride and fly at the same time (Tier B+).</strong> Sprint while mounted to fly forward, look around to steer, release sprint to glide. Sprinting drains stamina; when it hits empty mid-flight, <strong>5 Flocon Currency</strong> (the snowflake currency dropped by every mob in the <a href="../content/frozen-dungeon.md">Frozen Dungeon</a>) are consumed automatically to top it back up. No Flocon Currency in inventory → no refill → the dragon glides to the ground.
</div>

<div class="eg-note">
<strong>Off-mount vs mounted combat.</strong> The dragon has two combat modes :
<ul>
<li><strong>Off-mount (autonomous)</strong> — the dragon picks targets and attacks on its own. Frost Claw melee unlocks at Tier D, Frost Bolt ranged at Tier A.</li>
<li><strong>Mounted (player-directed)</strong> — wield the <strong>Pet Commander</strong> staff and the dragon auto-attacks where you aim. Melee at Tier C+ (8 mana per swing). Frost Bolt added at Tier B+ when airborne or out of melee range (25 mana per shot). Wield the <strong>Frostbite Blade</strong> (Tier A+) instead and the dragon unleashes a continuous frost breath stream from its mouth in your aim direction.</li>
</ul>
All damage — autonomous or player-directed — scales with the pet tier multiplier (1.4× D → 3.5× SS) and, when <a href="../reference/configuration.md">EndlessLeveling</a> is present, with the rider's STRENGTH (physical) or SORCERY (ice) skill bonus.
</div>

| Tier | Ability | Description |
| :---: | --- | --- |
| D  | Frost Claw | <strong>Off-mount</strong> autonomous melee — pet picks targets on its own |
| C  | Rideable | Ground mount unlocked. <strong>Mounted</strong>: wield Pet Commander → dragon auto-attacks melee (8 mana per swing) |
| B  | **Skyborne** | Ride and fly at the same time — sprint to fly forward, glide otherwise. Costs 5 Flocon Currency (found in Frozen Dungeon) per stamina refill. <strong>Mounted</strong>: Pet Commander adds ranged Frost Bolt when airborne (25 mana per shot) |
| A  | Frost Bolt | <strong>Off-mount</strong> autonomous ranged ice projectile. <strong>Mounted</strong>: wield Frostbite Blade → continuous frost breath stream from the snout |
| S  | **Frost Ward** | Owner: 100 % Ice damage immunity |
| SS | **Frost Aura** | Freezes enemies within 5 blocks (pulses every 2 s) |

<div style="clear:both;"></div>
  </div>
</div>

<div class="eg-profile">
  <div class="eg-profile-head">
    <h3 class="eg-profile-name">Dragon Fire</h3>
    <span class="eg-profile-tag">DPS / Fire</span>
  </div>
  <div class="eg-profile-body">
<img src="https://raw.githubusercontent.com/lewai1/endgameqolwiki/main/images/mobs/Dragon_Fire.png" width="100" style="float:right;margin:0 0 8px 14px;">
<div class="eg-statsheet">
  <div class="eg-stat"><span class="eg-stat-label">Mount</span><span class="eg-stat-val">Tier C+</span></div>
  <div class="eg-stat"><span class="eg-stat-label">Flight</span><span class="eg-stat-val">Tier B+</span></div>
  <div class="eg-stat"><span class="eg-stat-label">Tier S perk</span><span class="eg-stat-val accent">Flame Ward</span></div>
  <div class="eg-stat"><span class="eg-stat-label">Tier SS aura</span><span class="eg-stat-val">Burn 5 blk</span></div>
</div>

Mount and flight are mutually exclusive on Dragon Fire (legacy model). The dragon either carries you on the ground, or flies autonomously above you when you are not mounted. Only Dragon Frost supports the new ride-and-fly hybrid at this point.

| Tier | Ability | Description |
| :---: | --- | --- |
| D  | Flame Claw | Basic melee fire attack |
| C  | Fire Breath | Short-range cone fire; ground mount also unlocks |
| B  | Skyborne | Pet flies on its own and follows you in the air; only when not mounted |
| A  | Fireball | Explosive ranged projectile |
| S  | **Flame Ward** | Owner: 100 % Fire damage immunity |
| SS | **Immolation** | Burns enemies within 5 blocks (pulses every 2 s) |

<div style="clear:both;"></div>
  </div>
</div>

<div class="eg-profile">
  <div class="eg-profile-head">
    <h3 class="eg-profile-name">Golem Void</h3>
    <span class="eg-profile-tag">Tank / Protection</span>
  </div>
  <div class="eg-profile-body">
<img src="https://raw.githubusercontent.com/lewai1/endgameqolwiki/main/images/mobs/Golem_Void.png" width="100" style="float:right;margin:0 0 8px 14px;">
<div class="eg-statsheet">
  <div class="eg-stat"><span class="eg-stat-label">Mount</span><span class="eg-stat-val">Tier S+</span></div>
  <div class="eg-stat"><span class="eg-stat-label">Flight</span><span class="eg-stat-val">—</span></div>
  <div class="eg-stat"><span class="eg-stat-label">Tier S perk</span><span class="eg-stat-val accent">Void Armor</span></div>
  <div class="eg-stat"><span class="eg-stat-label">Tier SS aura</span><span class="eg-stat-val">Void Barrier</span></div>
</div>

Heavier mount, only unlocks at Tier S. Mount point sits at shoulder height on the scaled model.

| Tier | Ability | Description |
| :---: | --- | --- |
| D  | Void Fist | Basic melee void attack |
| C  | Provoke | Taunts nearby hostile mobs onto the pet |
| B  | Ground Slam | AOE attack with knockback |
| A  | Boulder Throw | Heavy ranged projectile |
| S  | **Void Armor** | Owner: −10 % Physical + full knockback immunity; mount unlocks |
| SS | **Void Barrier** | Extra −8 % Physical & Projectile (stacks with Void Armor) |

<div style="clear:both;"></div>
  </div>
</div>

<div class="eg-profile">
  <div class="eg-profile-head">
    <h3 class="eg-profile-name">Hedera</h3>
    <span class="eg-profile-tag">Support / Poison</span>
  </div>
  <div class="eg-profile-body">
<img src="https://raw.githubusercontent.com/lewai1/endgameqolwiki/main/images/mobs/Hedera.png" width="100" style="float:right;margin:0 0 8px 14px;">
<div class="eg-statsheet">
  <div class="eg-stat"><span class="eg-stat-label">Mount</span><span class="eg-stat-val">—</span></div>
  <div class="eg-stat"><span class="eg-stat-label">Flight</span><span class="eg-stat-val">—</span></div>
  <div class="eg-stat"><span class="eg-stat-label">Tier S perk</span><span class="eg-stat-val accent">Nature's Guard</span></div>
  <div class="eg-stat"><span class="eg-stat-label">Tier SS aura</span><span class="eg-stat-val">Poison 5 blk</span></div>
</div>

Support archetype — never mountable regardless of tier.

| Tier | Ability | Description |
| :---: | --- | --- |
| D  | Thorn Scratch | Basic melee nature attack |
| C  | Healing Spore | Heals owner within 15 blocks (2 / 3 / 4 HP/s at C–A / S / SS) |
| B  | War Cry | AOE slow on nearby enemies |
| A  | Vine Grab | Pulls one enemy toward the pet |
| S  | **Nature's Guard** | Owner: full poison immunity (vanilla sources included) |
| SS | **Nature's Blessing** | Poisons enemies within 5 blocks (pulses every 2 s) |

<div style="clear:both;"></div>
  </div>
</div>

## Mount summary

| Pet | Mount tier | Notes |
| --- | :---: | --- |
| Dragon Frost | C+ | Ground mount at C+, ride-and-fly hybrid at B+ (sprint to fly, 5 Flocon Currency from the Frozen Dungeon per stamina refill) |
| Dragon Fire  | C+ | Ground mount only — autonomous flight at Tier B+, exclusive of being ridden |
| Golem Void   | S+ | Heavier mount, only unlocks at Tier S |
| Hedera       | —  | Never mountable (support) |

Right-click the pet to mount once the tier is unlocked. **Dragon Frost** at B+ can be ridden AND flown at the same time (sprint to fly, glide otherwise, 5 Flocon Currency per stamina refill). Dragon Fire still uses the legacy mutually-exclusive model — dismount to let it fly autonomously.

## Feeding & respawn

Open `/eg pet` to see the feed panel. Each tier has its own item cost (shown on the Feed button). Feeding consumes the items from your inventory and advances the active pet by one tier. The page scroll position is preserved after feeding — you can click Feed multiple times without losing your place.

If a pet dies, it enters a **30-second respawn cooldown**. You cannot summon a new pet during that window.

## Nameplate

The nameplate displays `[Tier] PetName` and is colored by tier:

`D` gray · `C` green · `B` blue · `A` purple · `S` orange · `SS` red.

## Pet Commander staff

<img src="https://raw.githubusercontent.com/lewai1/endgameqolwiki/main/images/icons/Endgame_Staff_Pet_Commander.png" width="72" style="float:right;margin:0 0 8px 14px;">

The **Pet Commander** staff (Legendary, crafted with 6 Mithril Bars + 2 Sticks at the Endgame Bench → Misc) acts as a live control tool for your pet. Zero durability, zero damage, zero mana on its own — pure command tool. Wielding it while mounted on a Frost Dragon turns it into the auto-attack trigger.

- **Left-click** — fires a fast visual ray and snaps your pet's target to the nearest hostile in a ~50° aim cone within 30 blocks. Dragon pets fire their ranged bolt in sync; melee pets (Hedera, Golem Void) charge and engage.
- **Right-click** — opens the Pet Companion menu directly (same as `/eg pet`).
- **Mounted on Frost Dragon, Tier C+** — the dragon auto-attacks melee on cooldown where you aim (8 mana per swing).
- **Mounted on Frost Dragon, Tier B+** — adds ranged Frost Bolt auto-fire when airborne or out of melee range (25 mana per shot).

Damage from mounted Pet Commander attacks runs through the pet tier multiplier (1.4× D → 3.5× SS) and, when EndlessLeveling is installed, stacks the rider's STRENGTH (physical) or SORCERY (ice) bonus on top.

See [Items & Weapons](items-weapons) for the full rundown.

<div style="clear:both;"></div>

## Frostbite Blade — Frost Dragon breath

<img src="https://raw.githubusercontent.com/lewai1/endgameqolwiki/main/images/icons/Weapon_Sword_Frost.png" width="72" style="float:right;margin:0 0 8px 14px;">

When mounted on a **Tier A+** Frost Dragon and wielding the **Frostbite Blade** (dropped by the Frost Dragon boss in the Frozen Dungeon), the dragon unleashes a **continuous frost breath stream** from its mouth in your aim direction. The cone deals ice damage to any NPC inside it on a 250 ms tick, and damage scales identically to the Pet Commander attacks (pet tier × EL SORCERY if installed).

Switching to any other hotbar slot stops the breath immediately.

<div style="clear:both;"></div>

## Configuration

`/eg config` → **Pets** tab exposes:

- Pet system on/off toggle
- Per-pet **unlock chance** (Dragon Frost / Dragon Fire / Golem Void / Hedera)
- **Teleport distance** — how far the pet can stray before auto-teleporting back to the owner (clamped 10–100 blocks, default 35)
- **Blocked world prefixes** — read-only view; edited via `/eg admin petblock add <prefix>` / `remove <prefix>` / `list`. Any world whose name starts (case-insensitive) with a listed prefix auto-despawns pets on entry and refuses new summons. Default empty — useful for PvP arenas or event dungeons.

## Cross-mod integration

**EndlessLeveling** — when installed, pet HP scales with the owner's EL level at spawn (`1.0 + level × 0.05`), pet damage stacks the owner's **STRENGTH** bonus on physical attacks and **SORCERY** bonus on ice/fire attacks (chosen by the damage cause), and the nameplate shows the owner's current level. This applies to every dragon attack — autonomous claws/bolts, mounted Pet Commander hits, and the Frostbite Blade breath — on top of the tier multiplier. Re-syncs automatically on XP grant and level-up. Without EL, the pet system works standalone with tier multipliers only.
