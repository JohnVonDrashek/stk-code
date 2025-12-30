# Race Module

*Last Updated: 2025-12-29*

Race configuration, grand prix management, and highscore tracking.

## Purpose

This module manages the high-level race state that persists across individual races. It stores user-selected race parameters (track, karts, difficulty), handles grand prix progression and scoring, and maintains highscore records. The RaceManager acts as a bridge between the UI menus and the World gameplay classes.

## Key Classes

| Class | File | Purpose |
|-------|------|---------|
| `RaceManager` | race_manager.hpp | Central singleton storing race configuration, kart setup, and GP progress |
| `GrandPrixData` | grand_prix_data.hpp | Defines a grand prix (track list, name, groups) |
| `GrandPrixManager` | grand_prix_manager.hpp | Loads and manages all available grand prix definitions |
| `Highscores` | highscores.hpp | Stores best times/scores for a specific track and mode |
| `HighscoreManager` | highscore_manager.hpp | Manages all highscore entries, handles load/save |
| `History` | history.hpp | Records input history for deterministic replay in debug builds |

## Race Modes

- **Linear Races**: Normal, Time Trial, Follow the Leader, Lap Trial
- **Battle Arenas**: 3 Strikes, Free for All, Capture the Flag, Soccer
- **Special**: Easter Egg Hunt, Overworld, Cutscene

## Dependencies

- **modes/** - Game mode implementations (World subclasses)
- **karts/** - Kart selection and AI configuration
- **tracks/** - Track selection and properties
- **network/** - RemoteKartInfo for multiplayer kart assignment
