---
title: Premium & Patreon
description: Patreon tiers, the premium licensing system, and what each rank unlocks.
order: 2
published: true
---

# Premium & Patreon

The base mod is **fully free** — every boss, dungeon, weapon, pet, and framework works with no license. Paid Patreon tiers unlock a small set of **optional, additive** server-owner perks via a signed license token. No tier is required to play.

Subscribe at [patreon.com/cw/endgameqol](https://www.patreon.com/cw/endgameqol).

## Patreon tiers

Three **cumulative** tiers — each higher rank includes everything in the one below.

| Perk | Rank A — Bronze | Rank S — Silver | Rank SSS — Gold |
| --- | --- | --- | --- |
| **Faster updates** (Patreon before CurseForge) | ✅ | ✅ | ✅ |
| **Overworld bosses** — re-enable Dragon Frost / Hedera / Golem Void spawning outside their instances (`OVERWORLD_BOSSES`) | ✅ | ✅ | ✅ |
| **Future customization perks** | ✅ | ✅ | ✅ |
| **Ad-free Journal** — hides the Featured Servers tab from `/eg journal` (`AD_FREE`) | — | ✅ | ✅ |
| **Full rebranding** — white-label via `Rebranding.json` (`REBRANDING`) | — | — | ✅ |
| **Featured Listing** — your server's card shown in every other server's in-game Journal | — | — | ✅ |

### Rank A — Bronze
Faster updates (Patreon releases land before CurseForge), the `OVERWORLD_BOSSES` flag to re-enable Dragon Frost / Hedera / Golem Void spawning outside Endgame instances, plus future customization perks as they ship.

### Rank S — Silver
Everything in Rank A, plus `AD_FREE` — hides the Featured Servers tab from the `/eg journal` page on your server.

### Rank SSS — Gold
Everything in Rank S, plus:

- **`REBRANDING`** — drop a `Rebranding.json` next to `EndgameConfig.json` to override the mod's chat prefix, brand name, Wiki URL, boss bar subtitle, Patreon CTA, and ~250 other user-facing strings.
- **Featured Listing** — your server's card is displayed in `/eg journal` → Featured Servers on every other EndgameQoL server, with a custom accent color, optional 600×300 PNG banner, filterable tags, and a one-click Join button via the native referral packet. The card auto-rotates daily across all featured partners (shuffled per UTC date) so everyone gets equal exposure.

## Applying a license

Licenses are server-wide (active for everyone, no per-player setup) and additive on top of the free base mod. Two supported methods:

1. **In-game config UI (recommended)** — `/eg config` → **License** tab → paste your token into the field → **Apply**. The page refreshes and shows Status, Tier, Expiry, and the active feature flags.
2. **Drop-in file** — for tokens too long to paste comfortably (they can hit ~300 chars): paste the single-line token into `Saves/<world>/mods/Config_Endgame&QoL/license.dat`, then run `/eg admin reload` or restart the server.

> There is **no chat command**. Earlier versions had `/eg license <key>`, but Hytale's chat input truncates pastes around ~100 characters while licence tokens are 280–320 chars, so it always failed and was removed. Use the License tab or the drop-in file.

## Privacy & telemetry

- **No call-home, no telemetry** for validation. The only network call is a once-per-day fetch of the revocation list, so cancelled or revoked keys stop working within 24h.
- **No personal data** in the token — the Ed25519-signed payload contains only a license id (your label, e.g. `PATREON-yourname`), the unlocked feature flags, and an expiry timestamp.
- **No machine fingerprinting.**

## Renewal

Tokens renew each Patreon cycle (~31 days) and stay valid for the full window even after you unsubscribe. The plugin logs a boot warning when a token has under 7 days left so you know to apply the renewed one.

Server-owner setup details (getting a key, Featured Listing onboarding, troubleshooting) live in `LICENSE_SETUP.md`. Questions: DM `lewaii` on the [EndgameQoL Discord](https://discord.gg/mrCyvJmC28).
