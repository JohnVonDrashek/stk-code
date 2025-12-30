# Game Data and Assets

Core game assets, configuration files, and resources for SuperTuxKart.

## Purpose

This directory contains all runtime data needed by SuperTuxKart, including configuration files, shaders, GUI elements, translations, and various game assets. Note: Large assets like karts, tracks, and textures are stored in a separate `stk-assets` repository.

## Key Files and Directories

| Path | Description |
|------|-------------|
| **Configuration** | |
| `stk_config.xml` | Master game configuration (kart limits, server URLs, scoring) |
| `kart_characteristics.xml` | Kart physics and handling parameters |
| `powerup.xml` | Power-up behavior and spawn rates |
| `items.xml` | Item definitions |
| `achievements.xml` | Achievement definitions |
| `graphical_restrictions.xml` | GPU-specific graphics overrides |
| **Game Content** | |
| `challenges/` | Challenge mode definitions |
| `grandprix/` | Grand Prix configurations |
| `replay/` | Ghost replay data |
| `shaders/` | GLSL shader programs |
| `skins/` | UI skin themes |
| `gfx/` | Visual effects and particles |
| `gui/` | GUI layout definitions |
| **Localization** | |
| `po/` | Translation files (gettext .po format) |
| `CREDITS` | Contributor credits |
| **Resources** | |
| `ttf/` | TrueType fonts |
| `supertuxkart*.png` | Application icons (various sizes) |
| `supertuxkart.icns` | macOS application icon |
| `cacert.pem` | SSL certificates for online features |

## Related Files

- `supertuxkart.desktop` - Linux desktop entry
- `SuperTuxKart-Info.plist` - macOS application info
- `net.supertuxkart.SuperTuxKart.metainfo.xml` - AppStream metadata
