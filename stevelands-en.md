# SteveLands <span class="version-badge">MC 1.20+</span>

Protected land claim plugin for Minecraft Java Edition by **StevePlugins**.

<div class="lang-switch">
  <a href="#/stevelands-pt">🇧🇷 Português</a>
  <a href="#/stevelands-en" class="active">🇺🇸 English</a>
</div>

<div class="platform-tags">
  <span class="platform-tag">📄 Paper</span>
  <span class="platform-tag">🔧 Spigot</span>
  <span class="platform-tag">⚡ Folia</span>
  <span class="platform-tag">🔨 Mohist</span>
</div>

---

## Requirements

- Minecraft Java 1.20+
- Paper, Spigot, Folia, or Mohist
- GriefPrevention installed on the server
- Valid license key (purchased at [steveplugins.com](https://steveplugins.com))

## Installation

1. Place `SteveLands.jar` in your server's `plugins/` folder
2. Restart the server
3. Edit `plugins/SteveLands/config.yml` and enter your license key
4. Run `/land reload` or restart the server


> **💡 Tip:** After the first startup, the plugin automatically generates configuration and message files.

## Configuration

The file `plugins/SteveLands/config.yml` controls all settings:

```yaml
# Language: "pt" (Portuguese) or "en" (English)
language: "en"

# Your license key
license-key: "your-key-here"

# Available land sizes (in blocks)
claim-sizes:
  - 10
  - 20
  - 50

# Maximum claims per player
max-claims-per-player: 3

# Cooldown between purchases (seconds)
cooldown-seconds: 60

# Worlds where claims are allowed
enabled-worlds:
  - "world"
  - "world_nether"
  - "world_the_end"

# Entry notification cooldown (seconds)
entry-notification-cooldown-seconds: 5

# House per chest size
# "default" = starter house | "none" = no house | "name" = custom schematic
chest-schemas:
  10: "default"
  20: "default"
  50: "default"
```

## Languages

The plugin ships with English and Portuguese. Change `language` in config.yml.

Messages are stored in editable files:
- `plugins/SteveLands/messages_en.yml`
- `plugins/SteveLands/messages_pt.yml`

> **💡 Tip:** You can customize any message, color, and placeholder. Supports Minecraft color codes and hex colors.


## Commands

All commands work in both Portuguese and English.

| Command | Alias | Description |
|---|---|---|
| `/land buy <size>` | `/terreno comprar` | Buy a land claim |
| `/land list` | `/terreno lista` | List your claims |
| `/land help` | `/terreno ajuda` | Show help |
| `/land reload` | `/terreno recarregar` | Reload configuration |
| `/land give <player> <size> [amount]` | `/terreno dar` | Give a claim chest |
| `/land schema pos1` | — | Mark corner 1 |
| `/land schema pos2` | — | Mark corner 2 |
| `/land schema save <name>` | `salvar` | Save schematic |
| `/land schema list` | `lista` | List schematics |

Main command aliases: `/terreno`, `/stevelands`, `/sl`

## Permissions

| Permission | Default | Description |
|---|---|---|
| `stevelands.buy` | everyone | Buy claims |
| `stevelands.list` | everyone | List claims |
| `stevelands.reload` | op | Reload config |
| `stevelands.give` | op | Give claim chests |
| `stevelands.admin` | op | Create/manage schematics |
| `stevelands.bypass.limit` | nobody | Bypass claim limit |
| `stevelands.bypass.cooldown` | nobody | Bypass cooldown |
| `stevelands.claims.<N>` | nobody | Custom claim limit (e.g. `stevelands.claims.5`) |

### Permission-Based Limits (VIP)

Use permissions in the format `stevelands.claims.<number>` to set different limits per group:

| Group | Permission | Limit |
|---|---|---|
| Default player | *(none)* | Uses config.yml value (default: 3) |
| VIP | `stevelands.claims.5` | 5 claims |
| VIP+ | `stevelands.claims.10` | 10 claims |
| Admin | `stevelands.bypass.limit` | Unlimited |

> **💡 Tip:** The plugin uses the highest permission value found. Configure in LuckPerms or your permissions plugin.


## Claim Chest

The claim chest is a special item that, when placed on the ground:

1. Creates a protected land claim centered on the position
2. Places oak fences around the border
3. Generates a starter house (or custom schematic)

To give chests to players:

```bash
/land give PlayerName 20 1
```

> **💡 Tip:** To integrate with kit plugins, use the command above in your kit configuration.

## Custom Schematics

Schematics let you create custom houses for each land size.

1. Build the desired house in-game
2. Go to the lower corner: `/land schema pos1`
3. Go to the opposite upper corner: `/land schema pos2`
4. Save: `/land schema save vip-house`
5. In config.yml, associate with a size:

```yaml
chest-schemas:
  10: "small-house"
  20: "medium-house"
  50: "vip-house"
```

> **⚠️ Warning:** The schematic must fit within the land size. Schematics larger than the land will be clipped.

## Entry Notifications

When a player enters a claim:
- The visitor sees the owner's name on the ActionBar
- The owner receives a notification of who entered
- Notifications have a configurable throttle to prevent spam

When a player leaves a claim:
- They receive an ActionBar message informing they left

## Support

- 🌐 Website: [steveplugins.com](https://steveplugins.com)
- 🔑 License issues: check your key in `config.yml`
- 📋 Errors: check the server log at `logs/latest.log`

---

<div class="doc-footer">
  Made with 💜 by <a href="https://steveplugins.com">StevePlugins</a>
</div>