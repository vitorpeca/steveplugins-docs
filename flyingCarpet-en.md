# FlyingCarpet <span class="version-badge">MC 1.20+</span>

Flying carpet plugin for Minecraft Java Edition by **StevePlugins**.

<div class="lang-switch">
  <a href="#/flyingCarpet-pt">🇧🇷 Português</a>
  <a href="#/flyingCarpet-en" class="active">🇺🇸 English</a>
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
- Valid license key (purchased at [steveplugins.com](https://steveplugins.com))

## Installation

1. Place `FlyingCarpet.jar` in your server's `plugins/` folder
2. Restart the server
3. Edit `plugins/FlyingCarpet/config.yml` and enter your license key
4. Run `/carpet reload` or restart the server


> **💡 Tip:** After the first startup, the plugin automatically generates configuration and message files.

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

> **💡 Tip:** You can customize any message, color, and placeholder. Supports Minecraft color codes and hex colors.


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

| Control | Action |
|---|---|
| **Jump** (space) | The carpet rises |
| **Sneak** (shift) | The carpet descends |
| **Walk** | The carpet follows horizontally |

> **💡 Tip:** The carpet respects existing builds — solid blocks are never replaced. When deactivating or leaving the server, all original blocks are automatically restored.

## Compatibility

<div class="platform-tags">
  <span class="platform-tag">📄 Paper (recommended)</span>
  <span class="platform-tag">🔧 Spigot</span>
  <span class="platform-tag">🔨 Mohist</span>
  <span class="platform-tag">⚡ Folia</span>
</div>

Minimum version: Minecraft 1.20+

## Soft-Dependencies (optional)

The plugin automatically detects the following protection plugins when installed:

| Plugin | Behavior |
|---|---|
| **GriefPrevention** | The carpet will not place blocks on claims where the player lacks build permission |
| **WorldGuard** | The carpet respects protected regions where the player cannot build |

> **💡 Tip:** These plugins are optional. FlyingCarpet works normally without them.

## Support

- 🌐 Website: [steveplugins.com](https://steveplugins.com)
- 🔑 License issues: check your key in `config.yml`
- 📋 Errors: check the server log at `logs/latest.log`

---

<div class="doc-footer">
  Made with 💜 by <a href="https://steveplugins.com">StevePlugins</a>
</div>