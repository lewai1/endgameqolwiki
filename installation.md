---
title: Installation
description: How to install, configure, and update Endgame & QoL on your Hytale server — requirements, steps, dependencies, and troubleshooting.
order: 2
published: true
---

# Installation Guide

How to install, configure, and update Endgame & QoL on your Hytale server.

## Requirements

| Requirement | Version | Notes |
| --- | --- | --- |
| Java | 25 | Bundled with Hytale Server |
| Hytale Server | Update 5 (≥ 0.5.0) | Required minimum version |

**No required mod dependencies.** Update 5 ships native multi-HUD support, so the old MultipleHUD requirement is gone.

**Recommended:** [Voile](https://www.curseforge.com/hytale/mods/docs) — extra in-game wiki access via `/voile` (the mod also ships its own Wiki tab in the Journal).

## Installation steps

1. **Download from CurseForge** — Visit the [Endgame & QoL CurseForge page](https://www.curseforge.com/hytale/mods/endgame-qol) and download the latest JAR.
2. **Place the JAR in `Mods/`** — Copy `EndgameQoL-x.x.x.jar` into your server's `Mods/` directory.
3. **Restart the server** — On boot the plugin initializes, registers all content, and generates its default configuration.

## First-time setup

On first launch, Endgame & QoL automatically generates its config at:

```
Config_Endgame&QoL/EndgameConfig.json
```

This file controls all plugin behavior — boss health, damage multipliers, feature toggles, and more. It can also be edited live in-game with `/eg config` (no restart).

Player data is stored via Hytale's built-in ECS system and auto-persisted to `universe/players/{UUID}.bson`. No manual JSON files are needed.

## Dependencies

The plugin runs **standalone** with no required dependencies in Update 5. Optional integrations activate automatically when their mod is installed:

| Dependency | Source | Why |
| --- | --- | --- |
| RPG Leveling | CurseForge | Boss kill XP, bounty XP, achievement XP |
| Endless Leveling | CurseForge | Mob-leveling integration — when active, EndgameQoL defers party + level scaling to EL to avoid double-stacking |
| OrbisGuard | CurseForge | Claim-aware spawn placement |
| QuestLines & Claims | CurseForge | Claim-aware spawn placement |

Optional dependencies are auto-detected at runtime. No configuration needed — drop the JAR into `Mods/` and the integration activates on next boot.

## Verify the installation

Once the server is running, join and run:

```
/eg status
```

This displays the plugin version, loaded content counts, active integrations, and configuration status. If the command is not recognized, the plugin did not load — check the server console for errors.

## Updating

1. Stop the server.
2. Replace the old JAR in `Mods/` with the new version.
3. Start the server. Existing configuration is preserved — new config keys are added with their defaults automatically.

## Uninstalling

1. Stop the server.
2. Remove the Endgame & QoL JAR from `Mods/`.
3. Delete the `Config_Endgame&QoL/` folder to remove all configuration data.

## Troubleshooting

| Problem | Cause | Solution |
| --- | --- | --- |
| Plugin not loading | Wrong folder or outdated server | Confirm the JAR is in `Mods/` (not a subfolder). Verify server is Hytale Update 5 (≥ 0.5.0). |
| Config not generating | File permission issue | Ensure the server process has write permissions to its own directory. Check console for errors during startup. |
| Commands not found | Plugin failed to initialize | Check server console for stack traces during startup. The most common cause is a version mismatch — update to the latest server build. |
| NPCs not spawning | Spawns disabled in config | Run `/eg config` and check that the relevant spawn toggles are enabled. |
| `CodecValidationException` on startup | Instance loads before plugin assets | Known non-blocking warning. The instance still loads correctly — safe to ignore. |
| Boss bar not showing | Player too far from boss | Boss bars appear within 50 m and hide beyond 55 m. Move closer. |
