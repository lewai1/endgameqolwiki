---
title: Commands
description: All commands, permission nodes, and the config UI reference.
order: 0
published: true
---

# Commands & Permissions

All Endgame & QoL commands are under `/eg`.

## /eg

| Subcommand | Description | Permission |
| --- | --- | --- |
| `/eg journal` | Open the Journal (7 tabs: Bounty Board, Bestiary, Achievements, Featured Servers, Leaderboard, Wiki, Statistics) | endgameqol.journal |
| `/eg pet` | Open the Pet UI (tier badge, ability list, Detail page, feed) | endgameqol.pet |
| `/eg config` | Open the configuration UI (10 tabs, search, recipe editor) | endgameqol.config |
| `/eg status` | Diagnostics dashboard | endgameqol.admin |
| `/eg petattack` | Make your ridden Frost Dragon attack (S/SS only) | endgameqol.pet |
| `/eg lang <locale\|auto>` | Set display language (EN, FR, ES, PT-BR, RU, TR, DE) | None |

## /eg journal

The native Journal is a single 7-tab `.ui` page:

- **Bounty Board** — active daily / weekly bounties, progress bars, streak tracker, reputation rank (Novice → Veteran → Elite → Legend).
- **Bestiary** — paginated mob cards (10 per page), kill milestones per category (gold = reachable, green = claimed, muted = unreached), discovery badges, filter chips by category.
- **Achievements** — 51 built-in achievements + any custom achievements from `CustomAchievements/*.json`, with progress and claim state, filter chips across 8 categories.
- **Featured Servers** — community partner servers running EndgameQoL. Order rotates every 24 hours, filterable by tag, each partner has a custom accent color. Hidden for players whose server has the Ad-Free Patreon tier active.
- **Leaderboard** — server-wide rankings with per-row player head avatars, sortable across 6 columns (Points, Kills, Achievements, Bestiary, Reputation, Bounties).
- **Wiki** — one-click external link to the official documentation.
- **Statistics** — 8-tile dashboard (total kills, bosses slain, mobs discovered, bounty rep, achievements unlocked, points, bounties done, bounty rank) + per-boss kill breakdown.

## /eg pet

Opens the native Pet UI. Shows the active pet's tier badge (D → SS), ability list, Detail sub-page, and feed button. See [Pets](pets).

## /eg config

Opens the native configuration UI with **10 tabs**: Difficulty, Scaling, Weapons, Armor, Crafting, Misc, **Pets**, Integration, Addons, **License**.

Features: global search bar, editable value fields, recipe override editor with per-recipe editing, colored ON / OFF toggles, dark theme, a dedicated License tab with input field for Premium tokens.

Permission: `endgameqol.config` (op-only by default).

## /eg admin

Permission: `endgameqol.admin` (op-only).

| Subcommand | Description |
| --- | --- |
| `/eg admin reset bounties <player\|all>` | Force refresh bounties (requires confirmation) |
| `/eg admin reload` | Reload config from disk (async) |
| `/eg admin portal <dungeonId>` | Force-spawn a temporal portal near you |
| `/eg admin pet give <player\|me> <petId\|all> <tier>` | Grant any pet at any tier (D → SS) |
| `/eg admin pet take <player\|me> [petId\|all]` | Remove a pet (despawns active entity) |
| `/eg admin pet list <player\|me>` | List unlocked pets and tiers |
| `/eg admin petblock list` | Show world-name prefixes where pets auto-disable |
| `/eg admin petblock add <prefix>` | Add a world-name prefix (case-insensitive) |
| `/eg admin petblock remove <prefix>` | Remove an entry from the pet block list |

## Destructive-command confirmation flow

Destructive admin commands (starting with `/eg admin reset bounties`) require a **confirm-within-30 s** pattern:

1. Run the command → server echoes a warning: `WARNING: This will reset bounties for '<target>'. Re-run the same command within 30s to confirm.`
2. Re-run the **exact same** command within 30 s → action executes.
3. Wait longer than 30 s, or run a different destructive command → pending confirmation discarded, cycle restarts.

Every executed destructive action is written to a rolling audit log on the dedicated `EndgameQoL.AdminAudit` logger, including timestamp, sender UUID + username, command, and target. Enable with:

```
/log EndgameQoL.AdminAudit --level=INFO
```

## Permission model

| Group | Nodes | Behavior |
| --- | --- | --- |
| Default-allow | `endgameqol.journal`, `endgameqol.pet`, `endgameqol.lang` | Work for all players by default (LuckPerms-compatible) |
| Op-only | `endgameqol.admin`, `endgameqol.config` | Require operator |
| Deny | Negation: `-endgameqol.journal`, `-endgameqol.*` | Use to revoke specific permissions |

## Removed commands

**v5.0.0**
- `/gauntlet` — infinite-wave arena removed. Replaced by wave system inside temporal portal instances.
- `/bounty` — merged into `/eg journal`.

**v5.2.0**
- `/eg license <key>` — Hytale's chat input truncates pastes around ~100 characters but licence tokens are 280-320 chars, so the chat path never reliably worked. Removed. Use `/eg config` → License tab → paste → Apply, or drop the token into `Saves/<world>/mods/Config_Endgame&QoL/license.dat` and `/eg admin reload`.
