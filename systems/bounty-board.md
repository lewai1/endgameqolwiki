---
title: Bounty Board
description: Daily and weekly quest system with reputation rewards, streak bonuses, and difficulty tiers.
order: 6
published: true
---

# Bounty Board

Daily and weekly quests with reputation rewards, streak bonuses, and difficulty tiers.

## Overview

The Bounty Board provides repeatable objectives that refresh on a schedule. Each day, every player receives **3 daily bounties** (1 easy, 1 medium, 1 hard) plus **1 weekly bounty** that cycles every 7 days.

Bounties are deterministic per player per day — the same player always gets the same bounties on the same day, ensuring fairness.

**Command:** `/eg journal` (Bounties tab) — Permission: `endgameqol.journal` (default: allow).

**v5.0.0 — Native Journal Page.** The Bounty Board is the first tab of the unified native `.ui` Journal page (Bounties / Bestiary / Achievements).

## Bounty types

| Type | Description | Example |
| --- | --- | --- |
| `KILL_NPC` | Kill a specific NPC type | Slay 10 Saurian Warriors |
| `KILL_ANY_BOSS` | Defeat any boss encounter | Defeat any boss |
| `COMPLETE_TRIAL` | Complete a Warden Trial at a minimum tier | Complete Warden Challenge Tier II+ |
| `COMBO_TIER` | Reach a combo tier during combat | Reach FRENZY combo tier |
| `SPEED_KILL_BOSS` | Kill a boss within a time limit | Defeat Frost Dragon in under 3 min |
| `KILL_UNIQUE_BOSSES` | Defeat several distinct boss types | Defeat 5 unique boss types |
| `REACH_FRENZY_COUNT` | Reach the FRENZY combo tier a number of times | Reach FRENZY 5 times |
| `KILL_ENDGAME_NPCS` | Kill any endgame NPCs (cumulative) | Kill 100 endgame NPCs |
| `CRAFT_ITEM` | Craft a specific item | Craft a Mithril Sword |
| `DUNGEON_CLEAR` | Clear a dungeon instance | Clear a dungeon instance |
| `DAMAGE_DEALT` | Deal cumulative damage to bosses | Deal 2 000 damage to bosses |
| `MINE_ORE` | Mine a specific ore type | Mine 25 Adamantite Ore |
| `EXPLORE_DUNGEON` | Enter a dungeon (optionally a specific one) | Enter the Frozen Dungeon |

## Difficulty tiers

| Tier | Description |
| --- | --- |
| Easy | Simple objectives like killing common NPCs or crafting basic items. Awards basic reputation and material rewards. |
| Medium | Moderate challenges such as killing elites, reaching combo tiers, or clearing dungeons. Better reputation and item rewards. |
| Hard | Demanding goals like speed-killing bosses, completing high-tier trials, or dealing massive damage. Best daily rewards. |

## Weekly bounties

Operate on a 7-day cycle and present significantly harder goals than dailies. Reward substantially more reputation and exclusive materials.

Examples: Kill 5 unique boss types · Reach FRENZY combo tier 5 times · Complete 3 Warden Trials at Tier III+ · Deal 10 000 total boss damage.

## Bonus objectives

Some bounties include cross-system bonus objectives that upgrade your reward if completed alongside the main goal.

Available bonus types: `combo_x3`, `combo_frenzy`, `at_full_hp`.

For example, a "Kill 5 Void Spectres" bounty might have a `combo_x3` bonus — maintain a 3× combo while completing it for an upgraded reward.

## Reputation system

Completing bounties earns reputation, which promotes you through named ranks as your total reputation grows.

| Rank | Reputation required |
| --- | :---: |
| Novice | 0 |
| Veteran | 500 |
| Elite | 1 500 |
| Legend | 3 000 |

## Streak bonus

Complete all 3 daily bounties in a single day to claim a streak bonus reward. The streak bonus provides an extra payout on top of individual bounty rewards, making full daily completion highly valuable.

## Configuration

All values editable live in `/eg config` (Misc tab) — no restart needed.

| Key | Default | Description |
| --- | :---: | --- |
| `Enabled` | true | Master toggle for the entire bounty system |
| `RefreshHours` | 24 | Hours between daily bounty refreshes |
| `StreakEnabled` | true | Whether daily streak bonus is active |
| `WeeklyEnabled` | true | Whether weekly bounties are generated |
