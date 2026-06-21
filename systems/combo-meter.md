---
title: Combo Meter
description: Chain kills to climb damage tiers with speed, heal, crit, and lifesteal bonuses.
order: 5
published: true
---

# Combo Meter

Chain kills together to climb damage tiers and unlock powerful combat bonuses.

## Overview

The Combo Meter rewards aggressive, continuous combat. Every kill increases your combo counter. As the counter climbs, you pass through four damage tiers, each granting increasingly powerful effects. Stop killing for too long, and the meter decays back to zero.

## Damage tiers

| Tier | Damage | Bonus |
| --- | :---: | --- |
| ×2 — Baseline | 110 % | Baseline reward for keeping your combo alive |
| ×3 — Speed | 125 % | Movement speed boost — close gaps and maintain pressure |
| ×4 — Heal + Crit | 150 % | Each kill restores HP. Critical strike chance increases |
| FRENZY — Lifesteal | 200 % | Lifesteal on every kill. Pinnacle of the combo system |

## HUD overlay

When the combo meter is active, an on-screen HUD shows:

- **Combo count** — current consecutive kills
- **Current tier** — color-coded indicator
- **Decay timer** — shrinking bar showing how long until the combo drops
- **Personal best** — highest combo count ever, persistent across sessions

## Decay & reset

The combo meter begins to decay after 5 seconds without landing a kill (configurable). The decay timer resets with every successful kill. If the timer reaches zero, the combo resets entirely and all tier bonuses are lost.

Taking fatal damage also resets the combo to zero, regardless of the remaining decay timer.

## Configuration

All values editable live in `/eg config` (Misc tab) — no restart needed.

| Key | Default | Description |
| --- | :---: | --- |
| `Enabled` | true | Enable / disable the combo meter |
| `TimerSeconds` | 5.0 | Inactivity seconds before reset (1.0 – 30.0) |
| `DamageX2` | 1.10 | Damage multiplier at ×2 tier |
| `DamageX3` | 1.25 | Damage multiplier at ×3 tier |
| `DamageX4` | 1.50 | Damage multiplier at ×4 tier |
| `DamageFrenzy` | 2.00 | Damage multiplier at FRENZY tier |
| `TierEffectsEnabled` | true | Enable tier bonus effects (speed, heal, lifesteal) |
| `DecayEnabled` | true | Enable combo decay over time |
