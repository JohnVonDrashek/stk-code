# Development Utilities

*Last Updated: 2025-12-29*

Scripts and tools for building, testing, and maintaining SuperTuxKart.

## Purpose

This directory contains helper scripts for developers and release managers, including build automation, asset validation, code maintenance, and server deployment tools.

## Key Scripts

| Script | Description |
|--------|-------------|
| **Build Tools** | |
| `linux_builder.sh` | Creates Linux distribution packages using chroot |
| `android_builder.sh` | Automated Android build script |
| `build-linux-travis.sh` | CI build script for Travis |
| `build-cross-ispc.sh` | Cross-compilation with ISPC shader compiler |
| **Asset Tools** | |
| `check_textures.py` | Validates texture files and formats |
| `create_kart_properties.py` | Generates kart property definitions |
| `update_characteristics.py` | Updates kart characteristics XML |
| **Localization** | |
| `generate-country-names.py` | Generates country name translations |
| `generate-countries-table.py` | Creates country lookup tables |
| `generate-ip-mappings.py` | Generates IP geolocation mappings |
| **Server/Network** | |
| `run_server.sh` | Launches dedicated game server |
| `network_race_statistics` | Collects multiplayer statistics |
| `compute_client_error.py` | Analyzes network client errors |
| **Maintenance** | |
| `remove-whitespaces.py` | Cleans trailing whitespace from source |
| `update_copyright.sh` | Updates copyright headers |
| `find_unused.sh` | Finds unused assets |
| `update_google_play_listings.py` | Updates Play Store metadata |

## Subdirectories

| Directory | Description |
|-----------|-------------|
| `ai_test/` | AI behavior testing tools |
| `windows_installer/` | NSIS installer scripts and resources |
