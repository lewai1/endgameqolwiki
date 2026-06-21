---
title: Bosses & Elites
description: All boss encounters and elite mobs in Endgame & QoL — phases, attacks, drops, difficulty presets, player scaling, and enrage mechanics.
order: 0
published: true
---

# Bosses & Elites

<p class="eg-lead">3 phased dungeon bosses, 6 elites, shared kill credit, proximity HP bar, and a unified enrage system.</p>

<div class="eg-note">
<strong>Shared boss kill credit</strong> — every player in the instance receives kill credit, bestiary progress, and XP when a boss dies. Toggleable via <code>SharedBossKillCredit</code>.
</div>

<div class="eg-note">
<strong>Proximity boss bar</strong> — bosses and elites display their HP bar when a player is within <strong>50 blocks</strong> (auto-hides at 55, hysteresis). No damage required to show the bar.
</div>

<div class="eg-note">
<strong>Instance-locked bosses</strong> — Dragon Frost, Hedera, and Golem Void cannot spawn outside their Endgame instance worlds; every spawn path (markers, <code>/spawnnpc</code>, third-party mods, admin debug) is caught and the boss is removed. The wild Dragon Fire and all elites are unaffected. Server owners with the tier-A license can disable this restriction.
</div>

## Boss bar & music

All bosses and elites share a unified boss bar — thematic per-boss color fill, glossy overlay, gold phase threshold markers, numeric HP (`current / max · %`), plus **INVULNERABLE** and **ENRAGED** badges. Only one bar shows at a time per player; it always tracks the boss that last hit you.

Dedicated combat music plays across the entire **Void Realm** dimension. Frozen and Swamp dungeons use their own ambient environment music.

## Dungeon bosses

<div class="eg-profile">
  <div class="eg-profile-head">
    <h3 class="eg-profile-name">Dragon Frost</h3>
    <span class="eg-profile-tag">Frozen Dungeon</span>
  </div>
  <div class="eg-profile-body">
<img src="https://raw.githubusercontent.com/lewai1/endgameqolwiki/main/images/mobs/Dragon_Frost.png" width="120" style="float:right;margin:0 0 10px 16px;">
<div class="eg-statsheet">
  <div class="eg-stat"><span class="eg-stat-label">Health</span><span class="eg-stat-val accent">1 400</span></div>
  <div class="eg-stat"><span class="eg-stat-label">Player scaling</span><span class="eg-stat-val">+50 %</span></div>
  <div class="eg-stat"><span class="eg-stat-label">Detection</span><span class="eg-stat-val">25 blk</span></div>
  <div class="eg-stat"><span class="eg-stat-label">Phases</span><span class="eg-stat-val">3</span></div>
</div>

Fly/walk hybrid with 3 HP-based phases and **alternating immunity**. Detection range 25 blocks (prevents aggro through dungeon ceilings). Hitting the boss with an immune damage type fires a one-time chat hint.

<div class="eg-phases">
  <span class="eg-phase">Sky Sentinel · &gt; 70 %</span>
  <span class="eg-phase">Ground Fury · 70 – 40 %</span>
  <span class="eg-phase">Hybrid Frenzy · &lt; 40 %</span>
</div>

| Phase | Behavior | Counter |
| --- | --- | --- |
| Sky Sentinel | Flying. **Melee-immune.** Frost Bolt barrage + Icy Wind radial. | Bows, crossbows, staves, spears |
| Ground Fury | Grounded. **Projectile-immune.** Melee chain + Ground Slam + Frost Breath cone. | Melee weapons |
| Hybrid Frenzy | Cycles fly/ground every 8–10 s, alternating immunity. | Both — adapt on the fly |

<div class="eg-attacks">
  <div class="eg-attack"><span class="eg-attack-name">Frost Bolt</span><span class="eg-attack-desc">Aerial barrage in P1 / P3-air</span><span class="eg-attack-dmg">Ranged</span></div>
  <div class="eg-attack"><span class="eg-attack-name">Icy Wind</span><span class="eg-attack-desc">Radial gust in P1 / P3-air</span><span class="eg-attack-dmg">AOE</span></div>
  <div class="eg-attack"><span class="eg-attack-name">Swing / Bite</span><span class="eg-attack-desc">Melee in P2 / P3-ground</span><span class="eg-attack-dmg">12 + 8 ice</span></div>
  <div class="eg-attack"><span class="eg-attack-name">Ground Slam</span><span class="eg-attack-desc">AOE + camera shake + Stagger</span><span class="eg-attack-dmg">24 + 10 ice (34)</span></div>
  <div class="eg-attack"><span class="eg-attack-name">Frost Breath</span><span class="eg-attack-desc">Ground cone</span><span class="eg-attack-dmg">Cone</span></div>
</div>

<div style="clear:both;"></div>

**Drops:** Dragon Heart, Mithril Bar (×4–5), Storm Hide, Ice Essence, Sapphire Gem (×3–6), Frostbite Blade (rare, ~3%).

<p>
<img src="https://raw.githubusercontent.com/lewai1/endgameqolwiki/main/images/icons/Dragon_Heart.png" width="34" title="Dragon Heart" style="vertical-align:middle;margin-right:8px;">
<img src="https://raw.githubusercontent.com/lewai1/endgameqolwiki/main/images/icons/Ingredient_Bar_Mithril.png" width="34" title="Mithril Bar" style="vertical-align:middle;margin-right:8px;">
<img src="https://raw.githubusercontent.com/lewai1/endgameqolwiki/main/images/icons/Ingredient_Hide_Storm.png" width="34" title="Storm Hide" style="vertical-align:middle;margin-right:8px;">
<img src="https://raw.githubusercontent.com/lewai1/endgameqolwiki/main/images/icons/Weapon_Sword_Frost.png" width="34" title="Frostbite Blade" style="vertical-align:middle;margin-right:8px;">
</p>
  </div>
</div>

<div class="eg-profile">
  <div class="eg-profile-head">
    <h3 class="eg-profile-name">Hedera</h3>
    <span class="eg-profile-tag">Swamp Dungeon</span>
  </div>
  <div class="eg-profile-body">
<img src="https://raw.githubusercontent.com/lewai1/endgameqolwiki/main/images/mobs/Hedera.png" width="120" style="float:right;margin:0 0 10px 16px;">
<div class="eg-statsheet">
  <div class="eg-stat"><span class="eg-stat-label">Health</span><span class="eg-stat-val accent">1 800</span></div>
  <div class="eg-stat"><span class="eg-stat-label">Player scaling</span><span class="eg-stat-val">+50 %</span></div>
  <div class="eg-stat"><span class="eg-stat-label">Phases</span><span class="eg-stat-val">3</span></div>
</div>

<div class="eg-phases">
  <span class="eg-phase">Vine Growth · &gt; 66 %</span>
  <span class="eg-phase">Toxic Bloom · 66 – 33 %</span>
  <span class="eg-phase">Corrupted Fury · &lt; 33 %</span>
</div>

| Phase | Behavior |
| --- | --- |
| Vine Growth | Base kit: Poison Strike, Root AOE, Scream |
| Toxic Bloom | Adds Vine Grab, Ground Slam, lingering Poison Clouds |
| Corrupted Fury | Adds the Charge lunge |

<div class="eg-attacks">
  <div class="eg-attack"><span class="eg-attack-name">Poison Strike</span><span class="eg-attack-desc">Melee + DOT (all phases)</span><span class="eg-attack-dmg">Melee + DOT</span></div>
  <div class="eg-attack"><span class="eg-attack-name">Root AOE</span><span class="eg-attack-desc">Eruption, snares players</span><span class="eg-attack-dmg">AOE</span></div>
  <div class="eg-attack"><span class="eg-attack-name">Scream</span><span class="eg-attack-desc">Circular knockback</span><span class="eg-attack-dmg">AOE</span></div>
  <div class="eg-attack"><span class="eg-attack-name">Vine Grab</span><span class="eg-attack-desc">Pulls player toward boss (P2+)</span><span class="eg-attack-dmg">Pull</span></div>
  <div class="eg-attack"><span class="eg-attack-name">Ground Slam</span><span class="eg-attack-desc">7-block AOE + camera shake + Stagger</span><span class="eg-attack-dmg">AOE + Stagger</span></div>
  <div class="eg-attack"><span class="eg-attack-name">Charge</span><span class="eg-attack-desc">Lunge with run animation (P3)</span><span class="eg-attack-dmg">Lunge</span></div>
  <div class="eg-attack"><span class="eg-attack-name">Poison Clouds</span><span class="eg-attack-desc">Lingering zone DOT every 18–25 s</span><span class="eg-attack-dmg">Zone DOT</span></div>
</div>

<div style="clear:both;"></div>

**Drops:** Hedera Gem, Onyxium Bar (×3–7), Forest Essence (×10–15), Void Essence (×10–20), Swamp Currency (×8–15), Voidheart, Hedera Seed accessory (~15 %).

<p>
<img src="https://raw.githubusercontent.com/lewai1/endgameqolwiki/main/images/icons/Hedera_Gem.png" width="34" title="Hedera Gem" style="vertical-align:middle;margin-right:8px;">
<img src="https://raw.githubusercontent.com/lewai1/endgameqolwiki/main/images/icons/Ingredient_Forest_Essence.png" width="34" title="Forest Essence" style="vertical-align:middle;margin-right:8px;">
</p>
  </div>
</div>

<div class="eg-profile">
  <div class="eg-profile-head">
    <h3 class="eg-profile-name">Golem Void</h3>
    <span class="eg-profile-tag">Void Realm</span>
  </div>
  <div class="eg-profile-body">
<img src="https://raw.githubusercontent.com/lewai1/endgameqolwiki/main/images/mobs/Golem_Void.png" width="120" style="float:right;margin:0 0 10px 16px;">
<div class="eg-statsheet">
  <div class="eg-stat"><span class="eg-stat-label">Health</span><span class="eg-stat-val accent">3 500</span></div>
  <div class="eg-stat"><span class="eg-stat-label">Player scaling</span><span class="eg-stat-val">+50 %</span></div>
  <div class="eg-stat"><span class="eg-stat-label">Phases</span><span class="eg-stat-val">3</span></div>
  <div class="eg-stat"><span class="eg-stat-label">Knockback</span><span class="eg-stat-val">Immune</span></div>
</div>

Spawn gated behind the **Void Gauntlet** — a 3-wave survival encounter. Clear the waves and the Golem rises from the ruins at the arena center. Aggressive pursuer — closes distance fast across the floating island.

<div class="eg-phases">
  <span class="eg-phase">Void Awakening · &gt; 66 %</span>
  <span class="eg-phase">Rift Surge · 66 – 33 %</span>
  <span class="eg-phase">Void Collapse · &lt; 33 %</span>
</div>

| Phase | Behavior |
| --- | --- |
| Void Awakening | Melee + Rumble + ranged volleys |
| Rift Surge | Adds Ground Slam (single / double) |
| Void Collapse | Adds Jump Slam signature + Danger Zone DOT aura |

<div class="eg-attacks">
  <div class="eg-attack"><span class="eg-attack-name">Swing</span><span class="eg-attack-desc">Melee AOECircle hitbox</span><span class="eg-attack-dmg">Melee</span></div>
  <div class="eg-attack"><span class="eg-attack-name">Rumble / Spin</span><span class="eg-attack-desc">AOE biased toward multiple nearby players</span><span class="eg-attack-dmg">AOE</span></div>
  <div class="eg-attack"><span class="eg-attack-name">Ground Slam</span><span class="eg-attack-desc">Single / Double AOECircle, Stagger on heavy</span><span class="eg-attack-dmg">AOE + Stagger</span></div>
  <div class="eg-attack"><span class="eg-attack-name">Projectile Volley</span><span class="eg-attack-desc">Ranged, LaunchForce 80–90, HeadMotion Aim</span><span class="eg-attack-dmg">Ranged</span></div>
  <div class="eg-attack"><span class="eg-attack-name">Jump Slam (sig)</span><span class="eg-attack-desc">Telegraph → jumps → teleports above target → crash. Void-safe fallback.</span><span class="eg-attack-dmg">80 + 1 s stagger</span></div>
  <div class="eg-attack"><span class="eg-attack-name">Danger Zone</span><span class="eg-attack-desc">8 m persistent DOT aura (P3)</span><span class="eg-attack-dmg">Zone DOT</span></div>
</div>

<div style="clear:both;"></div>

**Drops:** Onyxium Bar **OR** Prisma Bar (weighted 60 % / 40 %, not both), Emerald (~50 %), Portal Luminia, Void Amulet accessory (~15 %).

<p>
<img src="https://raw.githubusercontent.com/lewai1/endgameqolwiki/main/images/icons/Ingredient_Bar_Prisma.png" width="34" title="Prisma Bar" style="vertical-align:middle;margin-right:8px;">
<img src="https://raw.githubusercontent.com/lewai1/endgameqolwiki/main/images/icons/Endgame_Portal_Luminia.png" width="34" title="Portal Luminia" style="vertical-align:middle;margin-right:8px;">
</p>
  </div>
</div>

## Elites

6 active elites — 4 world-roaming, 2 temporal-instance-bound. Difficulty scaling applies to elite HP and damage. **No player-count scaling.** Compact elite health bar displayed overhead.

| Elite | Health | Location | Notes |
| --- | ---: | --- | --- |
| <img src="https://raw.githubusercontent.com/lewai1/endgameqolwiki/main/images/mobs/Dragon_Fire.png" width="38" style="vertical-align:middle;margin-right:8px;"> Dragon Fire | 1 000 | Volcanoes — centered on gold-block deposits | Fireball projectile (80-block range) + 360° stomp + melee swing (27 Physical + 10 Fire). Fire-immune, knockback-immune. Drops Storm Hide + Adamantite Bar + Blazefist accessory (~15 %). |
| <img src="https://raw.githubusercontent.com/lewai1/endgameqolwiki/main/images/mobs/Alpha_Rex.png" width="38" style="vertical-align:middle;margin-right:8px;"> Alpha Rex | 1000 | Zone 4 jungles | Powerful cave predator, territorial |
| <img src="https://raw.githubusercontent.com/lewai1/endgameqolwiki/main/images/mobs/Swamp_Crocodile.png" width="38" style="vertical-align:middle;margin-right:8px;"> Swamp Crocodile | 900 | Swamp Dungeon | Ambush predator, poison bite |
| <img src="https://raw.githubusercontent.com/lewai1/endgameqolwiki/main/images/mobs/Bramble_Elite.png" width="38" style="vertical-align:middle;margin-right:8px;"> Bramble Elite | 550 | Swamp Dungeon | Thorny guardian, root + poison |
| <img src="https://raw.githubusercontent.com/lewai1/endgameqolwiki/main/images/mobs/Oakwood_Warlord.png" width="38" style="vertical-align:middle;margin-right:8px;"> Oakwood Warlord | 1 000 | Oakwood Refuge (temporal · mid) | Revenant warlord — Triple Strike / Scepter Shot / Ground Slam AOE + death-summons a 400 HP husk. Drops Mithril. |
| <img src="https://raw.githubusercontent.com/lewai1/endgameqolwiki/main/images/mobs/Eldergrove_Despot.png" width="38" style="vertical-align:middle;margin-right:8px;"> Eldergrove Despot | 1 800 | Eldergrove Hollow (temporal · hard) | Goblin tyrant — pure caster (Ice Bolt / Fire Blast / Lightning Strike) + spiked-shield block every ~5 s. Drops Mithril + a 50/30/20 chance of Voidheart / Adamantite / Emerald. |

## Difficulty & scaling

| Preset | HP × | Damage × |
| --- | :---: | :---: |
| Easy | 0.60 | 0.50 |
| Medium | 1.00 | 1.00 |
| Hard | 1.50 | 1.50 |
| Extreme | 2.50 | 2.00 |
| Custom | 0.10 – 10 | 0.10 – 10 |

**Player scaling formula**

```
multiplier = 1.0 + (playerCount − 1) × (scalingPercent / 100)
```

Example — Golem Void on Hard, 4 players, 50 % scaling: `3 500 × 1.5 × (1 + 3 × 0.5) = 3 500 × 1.5 × 2.5 = 13 125 HP`.

## Enrage

When a boss takes **more than 200 damage in 5 seconds**, it enters an enraged state.

<dl class="eg-defs">
  <dt>Damage bonus</dt><dd>×1.5 for 8 seconds</dd>
  <dt>Cooldown</dt><dd>15 s before re-trigger</dd>
  <dt>Trigger</dt><dd>DPS &gt; 200 over a 5 s window</dd>
  <dt>Badge</dt><dd><code>ENRAGED</code> on the boss bar</dd>
</dl>

All values configurable bulk-across-bosses in `/eg config → Scaling`.

## Stagger effect

These heavy AOE attacks apply **Endgame_Stagger** (1 s stun, derived from vanilla `Stun`):

- Void Golem Ground Slam / Jump Slam
- Frost Dragon Ground Slam
- Hedera Ground Slam
