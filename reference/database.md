---
title: Database
description: Optional SQL database for cross-server player data sync.
order: 3
published: true
---

# Database Setup

Optional SQL database for cross-server player data sync. ECS remains the primary source of truth.

Endgame & QoL stores all per-player data in **ECS components** that Hytale auto-saves to each player's `universe/players/<UUID>.bson` file — no database needed. The optional database feature syncs player data across sessions or multiple server instances.

The database is a **secondary backup**. ECS component files remain the primary source of truth. If the database goes down, nothing breaks.

## What gets synced?

| Feature | Contents |
| --- | --- |
| Bounty progress | Daily / weekly bounty state, streak count, total completed |
| Achievements | Completion, progress, claimed rewards per player |
| Bestiary | NPC kill counts, discoveries, milestones |
| Accessory Pouch | Trinket Pouch equipped accessories |
| Pet Data | Active pet, tier, hunger, mount state, ability cooldowns |
| Combo personal best | Highest kill streak record (never decreases) |

**Not synced to DB** — server config, difficulty settings, and recipe overrides live in `Saves/save/mods/Config_Endgame&QoL/` JSON files. Player language is stored in the ECS component but does not cross-server sync.

## When does sync happen?

Data is saved to the database **when a player disconnects**. There is no periodic auto-save — Hytale's ECS auto-save handles per-player persistence. The database acts as a secondary persistence layer for cross-server sync.

On server shutdown, the plugin waits up to 5 seconds for any pending writes to complete before stopping.

Combo personal best uses a `MAX(...)` comparison in SQL — a lower value will never overwrite a higher one, even if the player disconnects mid-run.

## Supported databases

| Database | Best for |
| --- | --- |
| SQLite | Single server, zero setup, local file storage |
| MySQL 8.0 | Dedicated servers, multi-instance, most common |
| MariaDB 3.3 | Drop-in MySQL replacement (OVH, Hetzner, etc.) |
| PostgreSQL 42.7 | Alternative for Pterodactyl and similar panels |

**No JDBC drivers are bundled.** You must download the driver JAR for your chosen database and place it in your server's `Mods/` folder. The driver is auto-detected from the JDBC URL prefix.

## Driver downloads

All drivers are available on Maven Central (`repo1.maven.org/maven2/`). Search for the artifact name below, download the `.jar` file, and drop it in your `Mods/` folder.

| Database | Artifact |
| --- | --- |
| SQLite | `sqlite-jdbc` |
| MySQL | `mysql-connector-j` |
| MariaDB | `mariadb-java-client` |
| PostgreSQL | `postgresql` |

## Configuration

The config file is created automatically on first boot at:

```
Saves/save/mods/Config_Endgame&QoL/DatabaseConfig.json
```

| Field | Default | Description |
| --- | --- | --- |
| `Enabled` | false | Toggle database sync |
| `JdbcUrl` | `jdbc:sqlite:./data/endgame_sync.db` | JDBC connection URL |
| `Username` | empty | Database username (leave empty for SQLite) |
| `Password` | empty | Database password (leave empty for SQLite) |
| `MaxPoolSize` | 10 | Maximum connections in pool |

### Validation rules

The plugin validates your config at startup and logs an error if:

- `JdbcUrl` does not start with `jdbc:`
- Remote databases (MySQL / MariaDB / PostgreSQL) are missing a `Username`
- PostgreSQL URL contains embedded credentials (use the Username / Password fields instead)
- `MaxPoolSize` is less than 1

## Quick start — SQLite

SQLite requires no external database server — just a driver JAR and one toggle.

1. Download `sqlite-jdbc` from Maven Central and place the JAR in your server's `Mods/` folder.
2. Open `Config_Endgame&QoL/DatabaseConfig.json`.
3. Set `"Enabled": true`.
4. Restart the server. The plugin creates `data/endgame_sync.db` automatically. No username or password needed.

Best for single servers that want a backup or easier data migration.

## MySQL / MariaDB setup

1. Download the JDBC driver from Maven Central — `mysql-connector-j` for MySQL or `mariadb-java-client` for MariaDB — and place the JAR in your server's `Mods/` folder.
2. Create the database on your MySQL / MariaDB server:

   ```sql
   CREATE DATABASE endgame;
   ```

3. Create a user with access (or use an existing one):

   ```sql
   GRANT ALL PRIVILEGES ON endgame.* TO 'hytaleuser'@'localhost';
   ```

4. Edit `DatabaseConfig.json`:

   ```json
   {
     "Enabled": true,
     "JdbcUrl": "jdbc:mysql://localhost:3306/endgame",
     "Username": "hytaleuser",
     "Password": "yourpassword",
     "MaxPoolSize": 10
   }
   ```

   For MariaDB, replace `jdbc:mysql://` with `jdbc:mariadb://`.

5. Restart the server. Tables are created automatically.

Best for multi-instance servers or networks that need shared player data.

## PostgreSQL setup

1. Download the `postgresql` driver from Maven Central and place the JAR in your server's `Mods/` folder.
2. Create the database:

   ```sql
   CREATE DATABASE endgame;
   ```

3. Edit `DatabaseConfig.json`:

   ```json
   {
     "Enabled": true,
     "JdbcUrl": "jdbc:postgresql://localhost:5432/endgame",
     "Username": "hytaleuser",
     "Password": "yourpassword",
     "MaxPoolSize": 10
   }
   ```

   **Important:** do not put credentials in the URL. Always use the `Username` / `Password` fields.

4. Restart the server. Tables are created automatically.

## Connection pool (HikariCP)

The plugin uses HikariCP for connection management (bundled in the JAR).

| Setting | Value |
| --- | --- |
| Pool name | EndgameQoL-DB |
| Min idle connections | 1 |
| Max pool size | Configurable (default 10) |
| Connection timeout | 10 seconds |
| Idle timeout | 5 minutes |
| Max connection lifetime | 10 minutes |

For most servers, the default pool size of 10 is more than enough. Only increase it if you have 50+ concurrent players and see connection wait times in logs.

## Database tables

The plugin creates one table automatically (no manual SQL needed).

### Endgame_PlayerData

One row per player. Stores all synced features as JSON blobs.

| Column | Description |
| --- | --- |
| `uuid` | Player UUID (primary key) |
| `username` | Last seen player name |
| `bounty_state` | Bounties JSON (progress, streak, daily / weekly) |
| `achievement_data` | Achievements JSON (progress, claimed) |
| `bestiary_data` | Bestiary JSON (kills, discoveries, milestones) |
| `accessory_pouch` | Trinket Pouch JSON |
| `pet_data` | Pet companion JSON (active pet, tier, hunger, cooldowns) |
| `combo_personal_best` | Best combo streak (integer) |
| `last_updated` | Timestamp of last save |

The table uses `CREATE TABLE IF NOT EXISTS` — safe to run every startup. Columns added across v4.x / v5.x (`achievement_data`, `bestiary_data`, `accessory_pouch`, `pet_data`, `combo_personal_best`) are auto-migrated via `ALTER TABLE`.

## Verifying it works

After restarting, check the server logs for:

- `[EndgameQoL.Database] Connection validated`
- `[EndgameQoL.Database] Tables and indexes verified/created`
- `[EndgameQoL.Database] Sync service initialized`

You can also run `/eg status` — the database health indicator shows `Healthy` or `Degraded`.

## Graceful degradation

If the database connection fails:

1. The plugin **keeps working** with JSON files — no data is lost, no crash.
2. After 3 consecutive failures, the service enters **DEGRADED** mode (visible in `/eg status`).
3. Writes continue to retry on every player disconnect — there is no permanent cutoff.
4. When the connection is restored, the service self-heals automatically and logs a recovery message.

If the database fails at startup, the plugin starts normally with JSON-only persistence. A warning is logged but it is non-fatal.

## Troubleshooting

| Problem | Solution |
| --- | --- |
| Driver not found / `ClassNotFoundException` | The JDBC driver JAR is missing. Download the correct driver for your database and place it in `Mods/`. |
| Connection refused | Check that your database server is running and the URL / port are correct. Verify firewall rules. |
| Access denied | Verify username / password and that the user has permissions. For MySQL: `GRANT ALL PRIVILEGES ON endgame.* TO 'user'@'host';` |
| Tables not created | Tables are created automatically. Check server logs for SQL errors — most common cause is insufficient permissions. |
| No sync happening | Make sure `Enabled` is `true` and restart the server. A config reload is not enough. |
| Degraded in `/eg status` | The database had 3+ consecutive failures. Check your database server is online. The plugin auto-recovers once restored. |
| Data not appearing on another server | Both servers must point to the same database. SQLite files are local-only — use MySQL / MariaDB / PostgreSQL for multi-server sync. |
| Slow player disconnects | Database writes are async and should not block disconnects. If you see delays, check your database server latency and increase `MaxPoolSize`. |

## Recommended pool sizes

| Players | MaxPoolSize |
| ---: | :---: |
| 1 – 20 | 5 |
| 20 – 50 | 10 |
| 50 – 100 | 15 |
| 100+ | 20 |

SQLite does not benefit from pool sizes above 3 — it uses file-level locking.
