# Config Module

*Last Updated: 2025-12-29*

Handles user configuration, game settings, and player profile management.

## Purpose

This module manages all persistent configuration in SuperTuxKart. It includes user preferences (graphics, audio, controls), global game parameters from `stk_config.xml`, player profiles with their achievements and story progress, and saved Grand Prix states for resuming interrupted tournaments.

## Key Classes

| Class | File | Purpose |
|-------|------|---------|
| `UserConfig` | user_config.hpp | Loads/saves user preferences; defines all config parameters via macros |
| `STKConfig` | stk_config.hpp | Global game constants (physics, timing, kart properties, URLs) |
| `PlayerManager` | player_manager.hpp | Manages player profiles (create, delete, switch, online login) |
| `PlayerProfile` | player_profile.hpp | Single player's data (name, achievements, story progress, favorites) |
| `SavedGrandPrix` | saved_grand_prix.hpp | Stores interrupted GP state for later resumption |
| `HardwareStats` | hardware_stats.hpp | Collects and reports hardware info for anonymous statistics |
| `FavoriteStatus` | favorite_status.hpp | Tracks player's favorite tracks and karts |

## Dependencies

- **achievements/**: Player profiles contain achievement status
- **challenges/**: Player profiles contain story mode progress
- **io/**: XML reading/writing for config files
- **online/**: Online player authentication
