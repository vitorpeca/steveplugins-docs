# FlyingCarpet — Administrator Guide

Flying carpet plugin for Minecraft Java Edition by **StevePlugins**.

---

## Requirements

- Minecraft Java 1.20+
- Paper, Spigot, Folia, or Mohist
- Valid license key (purchased at steveplugins.com)

## Installation

1. Place `FlyingCarpet.jar` in your server's `plugins/` folder
2. Restart the server
3. Edit `plugins/FlyingCarpet/config.yml` and enter your license key
4. Run `/carpet reload` or restart the server

## Configuration

The file `plugins/FlyingCarpet/config.yml` controls all settings:

```yaml
# Language: "pt" (Portuguese) or "en" (English)
language: "pt"

# Your license key
license-key: "your-key-here"

# Rise speed in blocks (1-5)
rise-speed: 1

# Descend speed in blocks (1-5)
descend-speed: 1

# Check interval in ticks (1 tick = 50ms)
check-interval-ticks: 2

# Carpet block type (Minecraft Material name)
carpet-block: "GLASS"

# Worlds where the carpet is allowed
enabled-worlds:
  - "world"
  - "world_nether"
  - "world_the_end"
```

## Languages

The plugin ships with Portuguese and English. Change `language` in config.yml.

Messages are stored in editable files:
- `plugins/FlyingCarpet/messages_pt.yml`
- `plugins/FlyingCarpet/messages_en.yml`

You can customize any message, color, and placeholder.

## Commands

All commands work in both Portuguese and English.

| Command | Alias | Description |
|---|---|---|
| `/carpet activate` | `/tapete ativar` | Activate the flying carpet |
| `/carpet deactivate` | `/tapete desativar` | Deactivate the flying carpet |
| `/carpet help` | `/tapete ajuda` | Show help |
| `/carpet reload` | `/tapete recarregar` | Reload configuration |

Main command aliases: `/tapete`, `/fc`

## Permissions

| Permission | Default | Description |
|---|---|---|
| `flyingcarpet.use` | everyone | Use the flying carpet |
| `flyingcarpet.reload` | op | Reload configuration |
| `flyingcarpet.admin` | op | Administrative permission |

## How It Works

The flying carpet creates a 3x3 platform of glass blocks below the player:

- **Jump (space)**: the carpet rises
- **Sneak (shift)**: the carpet descends
- **Walk**: the carpet follows the player horizontally

The carpet respects existing builds — solid blocks are never replaced. When deactivating or leaving the server, all original blocks are automatically restored.

## Compatibility

The plugin is compatible with the following server platforms:

- **Paper** (recommended)
- **Spigot**
- **Mohist**
- **Folia**

Minimum version: Minecraft 1.20+

## Soft-Dependencies (optional)

The plugin automatically detects the following protection plugins when installed:

- **GriefPrevention** — the carpet will not place blocks on claims where the player lacks build permission
- **WorldGuard** — the carpet respects protected regions where the player cannot build

These plugins are optional. FlyingCarpet works normally without them.

## Support

- Website: steveplugins.com
- License issues: check your key in config.yml
- Errors: check the server log at `logs/latest.log`
