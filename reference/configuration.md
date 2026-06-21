---
title: Configuration
description: Full configuration reference with every config key, default value, and range organized by section.
order: 1
published: true
---

# Configuration

Every config key, default value, and range — organized by section.

## How to configure

| Method | How |
| --- | --- |
| In-game UI | `/eg config` (requires `endgameqol.config` permission) |
| JSON file | `Config_Endgame&QoL/EndgameConfig.json` |
| Hot reload | `/eg admin reload` |

## Difficulty

| Key | Default | Description |
| --- | --- | --- |
| `Preset` | MEDIUM | EASY / MEDIUM / HARD / EXTREME / CUSTOM |
| `AffectsBosses` | true | Apply difficulty multipliers to bosses |
| `AffectsMobs` | true | Apply difficulty multipliers to regular mobs |
| `CustomHealthMultiplier` | 1.0 | HP multiplier when Preset=CUSTOM (0.1 – 10.0) |
| `CustomDamageMultiplier` | 1.0 | Damage multiplier when Preset=CUSTOM (0.1 – 10.0) |

**Presets** — Easy 60 % HP / 50 % DMG · Medium 100 % / 100 % · Hard 150 % / 150 % · Extreme 250 % / 200 %.

## Weapons

| Key | Default | Description |
| --- | --- | --- |
| `HederaPoisonEnabled` | true | Hedera Daggers poison on hit |
| `HederaPoisonDamage` | 5.0 | Damage per poison tick (0.1 – 50) |
| `HederaPoisonTicks` | 4 | Number of poison ticks (1 – 20) |
| `HederaLifestealEnabled` | true | Hedera Daggers lifesteal |
| `HederaLifestealPercent` | 0.08 | Lifesteal percentage (8 %) |
| `BlazefistBurnDamage` | 50.0 | Blazefist burn damage per tick |
| `BlazefistBurnTicks` | 3 | Number of burn ticks (1 – 10) |

Prisma Sword and Prisma Daggers abilities (Beam, Judgment, Dash, Razor Storm) are fully defined in JSON and have no runtime config toggles. Balance values (mana cost, damage, cooldown) are edited directly in the interaction JSON files under `Server/Item/Interactions/Weapons/{Sword,Daggers}/`.

## Armor

| Key | Default | Description |
| --- | --- | --- |
| `ManaRegenEnabled` | true | Passive mana regen on endgame armor |
| `ManaRegenMithrilPerPiece` | 0.5 | Mana/s per Mithril piece (0 – 5) |
| `ManaRegenOnyxiumPerPiece` | 0.75 | Mana/s per Onyxium piece |
| `ManaRegenPrismaPerPiece` | 1.0 | Mana/s per Prisma piece |
| `HPRegenEnabled` | true | Passive HP regen on Onyxium / Prisma |
| `HPRegenDelaySec` | 15.0 | Seconds after last damage before regen starts (1 – 60) |
| `HPRegenOnyxiumPerPiece` | 0.5 | HP/s per Onyxium piece |
| `HPRegenPrismaPerPiece` | 0.75 | HP/s per Prisma piece |

## Combo

| Key | Default | Description |
| --- | --- | --- |
| `Enabled` | true | Enable combo meter |
| `TimerSeconds` | 5.0 | Decay timer (1 – 30) |
| `DamageX2 / X3 / X4 / Frenzy` | 1.10 / 1.25 / 1.50 / 2.00 | Damage multiplier per tier |
| `TierEffectsEnabled` | true | Speed, heal, lifesteal bonuses |

## Bounty

| Key | Default | Description |
| --- | --- | --- |
| `Enabled` | true | Enable bounty system |
| `RefreshHours` | 24 | Hours between bounty refresh (1 – 168) |
| `StreakEnabled` | true | Streak bonus for completing all 3 daily |
| `WeeklyEnabled` | true | Enable weekly bounties |

## Misc

| Key | Default | Description |
| --- | --- | --- |
| `PvpEnabled` | false | PvP in endgame instances |
| `EnableDungeonBlockProtection` | true | Block building inside dungeons |
| `EnableWardenTrial` | true | Enable Warden Trial system |
| `WardenTrialBlockedWorlds` | `instance-` | Comma-separated world-name fragments where Warden Trials can't be started (empty = anywhere) |
| `AccessoriesEnabled` | true | Enable Trinket Pouch accessories |
| `BossTargetSwitchEnabled` | true | Boss target switching in multi-player |
| `BossTargetSwitchIntervalMs` | 8000 | Target switch interval (2000 – 30000) |
| `SharedBossKillCredit` | true | All players in instance get boss kill achievements & bounty credit |
| `VorthakEnabled` | true | Vorthak merchant spawning |
| `WardenTrialTimerTier1–4` | 270 / 360 / 450 / 540 | Per-tier wave timer in seconds (0 = disabled, max 600) |
| `LeaderboardEnabled` | true | Show the Leaderboard tab in the Journal |
| `LeaderboardHeadAvatars` | true | Render per-row player head avatars on the Leaderboard |

## Pets

| Key | Default | Description |
| --- | --- | --- |
| `Enabled` | true | Master on/off for the Endgame pet system |
| `DragonFrostUnlockChance` | 0.30 | Pet Dragon Frost drop rate (0.0 – 1.0) |
| `DragonFireUnlockChance` | 0.30 | Pet Dragon Fire drop rate |
| `GolemVoidUnlockChance` | 0.30 | Pet Golem Void drop rate |
| `HederaUnlockChance` | 0.30 | Pet Hedera drop rate |
| `TeleportDistance` | 35.0 | Blocks the pet can stray before auto-teleporting back (10 – 100) |
| `DisabledWorldPrefixes` | `""` | Comma-separated world-name prefixes where pets are blocked. Managed via `/eg admin petblock`. |

## Integration

Optional mod integrations are auto-detected on first boot. Enable / disable in `/eg config` Integration tab.

| Mod | Key | Default | Features |
| --- | --- | --- | --- |
| RPG Leveling | `RPGLevelingEnabled` | false | Boss kill XP, bounty XP, achievement XP |
| Endless Leveling | `EndlessLevelingEnabled` | false | Party XP sharing, bounty / trial / achievement XP |
| OrbisGuard | `OrbisGuardEnabled` | false | Auto-protect dungeon instances (block build, PvP, commands) |
| QuestLines & Claims | `QuestLinesClaimsEnabled` | false | Temporal portals skip claimed land |

## Crafting toggles

| Key | Default | Description |
| --- | --- | --- |
| `EnableGlider` | true | Endgame glider recipe |
| `EnableMithrilOre` | false | Mithril Ore crafting (bypass dungeon) |
| `EnablePortalHedera` | true | Hedera portal key recipe |
| `EnablePortalGolemVoid` | true | Golem Void portal key recipe |

Individual recipe visibility is managed via `RecipeOverrides.json` (separate file, toggled in `/eg config` Crafting tab).

## Shared Loot (`Shared_Loot.json`)

Per-player loot drops can be extended to third-party mods' instances. The 6 built-in Endgame instances (Frozen, Swamp, Void Realm, Eldergrove, Oakwood, Canopy) are always covered — no entry needed.

File: `Config_Endgame&QoL/Shared_Loot.json`. Reload via `/eg admin reload`.

| Key | Value |
| --- | --- |
| `Scopes` | Map: `"world-name-prefix": "comma,separated,mob,ids"`. Empty CSV = every mob in instances matching the prefix. |

Example:
```json
{
  "Scopes": {
    "MyMod_Trial":     "",
    "OtherMod_Arena":  "Boss_Big,Boss_Mini"
  }
}
```

Matching is substring case-insensitive on `world.getName()`, so multi-instance suffixes (`MyMod_Trial_1`, `MyMod_Trial_2`, …) all hit the same scope. Mobs only get per-player drops when at least two players damaged them within 30 s of death.

## Boss bar themes & auto-tracking (`Bossbar_Themes.json`)

Third-party mods (or server owners) can add fully-tracked boss bars without writing Java. The 11 built-in Endgame themes are always registered first; entries with the same npcTypeId in the JSON override them (visual only — built-in callback logic stays).

File: `Config_Endgame&QoL/Bossbar_Themes.json`. Reload requires a server restart (themes are wired at boot).

### Per-theme keys

| Key | Required | Description |
| --- | --- | --- |
| `DisplayName` | yes | Label shown above the bar (uppercase recommended) |
| `NameColor` | yes | Hex `#rrggbb` for the name |
| `BarColor` | yes | Hex `#rrggbb` for the bar fill |
| `Phases` | yes | Map: `"phase-number": { Name, TextColor, Threshold }`. Empty or single-entry = elite-style bar; multi-entry = boss-style with phase markers. |
| `Encounter` | no | When present with `AutoTrack: true`, the boss is wired into the full EndgameQoL pipeline (auto-register on spawn, phase transitions, knockback suppression, target switching, friendly-fire block, enrage). Absent or `AutoTrack: false` = theme only; the mod must trigger show/hide via the Java API. |

### Phase keys

| Key | Description |
| --- | --- |
| `Name` | Label shown for the phase (e.g. "Awakened", "Enraged") |
| `TextColor` | Hex `#rrggbb` for the phase label |
| `Threshold` | HP fraction (0.0–1.0) below which this phase activates. Phase 1 should be 1.0. |

### Encounter keys (auto-track block)

| Key | Default | Description |
| --- | --- | --- |
| `AutoTrack` | false | Master switch — enables full pipeline tracking |
| `PhaseInvulnerabilityMs` | 0 | Brief invuln window applied on each phase transition |
| `EnrageDamageThreshold` | 0 | Sustained damage required to enrage (0 = disabled) |
| `EnrageWindowMs` | 5000 | Sliding damage window for enrage detection |
| `EnrageDurationMs` | 10000 | How long the enraged state lasts |
| `EnrageDamageMultiplier` | 1.0 | Damage multiplier while enraged |
| `EnrageCooldownMs` | 30000 | Cooldown after enrage ends before it can re-trigger |

### Example (full tracked boss)

```json
{
  "Themes": {
    "MyMod_BigBoss": {
      "DisplayName": "MY BIG BOSS",
      "NameColor": "#ff0000",
      "BarColor":  "#aa0000",
      "Phases": {
        "1": { "Name": "Awakened",  "TextColor": "#ffffff", "Threshold": 1.0 },
        "2": { "Name": "Enraged",   "TextColor": "#ff8800", "Threshold": 0.5 }
      },
      "Encounter": {
        "AutoTrack":               true,
        "PhaseInvulnerabilityMs":  2000,
        "EnrageDamageThreshold":   500,
        "EnrageWindowMs":          5000,
        "EnrageDurationMs":        10000,
        "EnrageDamageMultiplier":  1.5,
        "EnrageCooldownMs":        30000
      }
    },
    "OtherMod_Elite": {
      "DisplayName": "OTHER ELITE",
      "NameColor":   "#ff8800",
      "BarColor":    "#c86633",
      "Phases":      { },
      "Encounter":   { "AutoTrack": true }
    }
  }
}
```

Endgame-only behaviours (pet drops, Endgame achievements, Endgame bounty targets, Prisma weapon/armor anti-boss damage) stay bound to the built-in `BossType` enum and do not apply to third-party bosses.
