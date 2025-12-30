# Game Data and Assets

*Last Updated: 2025-12-29*

Core game assets, configuration files, and resources for SuperTuxKart.

## Purpose

This directory contains all runtime data needed by SuperTuxKart, including configuration files, shaders, GUI elements, translations, and various game assets. Note: Large assets like karts, tracks, and textures are stored in a separate `stk-assets` repository.

## Directory Structure

| Directory | Description |
|-----------|-------------|
| `challenges/` | Story mode challenge definitions (`.challenge` XML) |
| `gamerzilla/` | Gamerzilla achievement system assets |
| `gfx/` | Particle effects and visual FX definitions |
| `grandprix/` | Grand Prix track sequences (`.grandprix` XML) |
| `gui/` | UI layouts, icons, and screen definitions |
| `po/` | Localization files (GNU gettext `.po` format) |
| `replay/` | Built-in ghost replay recordings |
| `shaders/` | GLSL shader programs (vertex, fragment, compute) |
| `skins/` | UI themes (cartoon, classic + color variants) |
| `ttf/` | TrueType fonts for internationalization |

## Configuration Files

### stk_config.xml
Master game configuration. Defines version compatibility, server URLs, and game constants.

```xml
<config>
  <kart-version min="2" max="3"/>           <!-- Kart format versions -->
  <track-version min="6" max="7"/>          <!-- Track format versions -->
  <karts max-number="20"/>                  <!-- Max karts in a race -->
  <OnlineServer url="https://online.supertuxkart.net/api/"/>
  <grand-prix>
    <points points="0"/>  <!-- Score distribution -->
  </grand-prix>
</config>
```

### kart_characteristics.xml
Physics parameters for all karts. Defines speed, acceleration, handling, etc.

```xml
<characteristics>
  <characteristic name="default">
    <engine power="450" max-speed="25"/>
    <wheels damping-relaxation="20"/>
    <suspension stiffness="50"/>
  </characteristic>
</characteristics>
```

### powerup.xml
Defines all collectible powerups, projectile physics, and item behavior.

```xml
<powerup>
  <item name="bowling" icon="bowling-icon.png"
        model="bowling.spm" speed="4.0" max-distance="25"/>
  <item name="cake" icon="cake-icon.png"
        model="cake.spm" speed="50" max-distance="90"/>
</powerup>
```

### Other Config Files

| File | Purpose |
|------|---------|
| `achievements.xml` | Achievement definitions with unlock criteria |
| `items.xml` | Collectible item types (bonus boxes, bananas, nitro) |
| `graphical_restrictions.xml` | GPU-specific graphics workarounds |
| `skin_names.xml` | Skin metadata and display names |
| `tips.xml` | Loading screen tips by category |

## Resource Files

| File | Purpose |
|------|---------|
| `cacert.pem` | SSL certificates for HTTPS (online features) |
| `CREDITS` | Contributor credits displayed in-game |
| `country_names.tsv` | Country name translations for flags |
| `localized_name.tsv` | Localized track/kart names |
| `thaidict.txt` | Thai word segmentation dictionary |
| `emoji_used.txt` | Emoji codepoints used in game |
| `supertuxkart*.png` | App icons (16px to 1024px) |
| `supertuxkart.icns` | macOS app icon bundle |

## Platform Files

| File | Purpose |
|------|---------|
| `supertuxkart.desktop` | Linux desktop entry (FreeDesktop spec) |
| `SuperTuxKart-Info.plist` | macOS application metadata |
| `SuperTuxKart-Info-iOS.plist` | iOS application metadata |
| `net.supertuxkart.SuperTuxKart.metainfo.xml` | AppStream metadata for Linux |

## Scripts

| File | Purpose |
|------|---------|
| `optimize_data.sh` | Optimizes PNG files for smaller builds |

## See Also

- Each subdirectory has its own README.md with detailed documentation
- `stk-assets` repository contains karts, tracks, and textures
