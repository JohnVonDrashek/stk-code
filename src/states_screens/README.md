# states_screens

*Last Updated: 2025-12-29*

User interface screens and dialogs for SuperTuxKart's menu system.

## Purpose

This module contains all UI screens and dialogs that make up the STK user interface. It uses the `guiengine` module facilities to implement menu screens, race HUD elements, and popup dialogs. The `StateManager` coordinates screen transitions and manages active players during gameplay.

## Key Classes

| Class | File | Purpose |
|-------|------|---------|
| StateManager | state_manager.hpp | Manages screen transitions and active player state |
| MainMenuScreen | main_menu_screen.hpp | The game's main menu screen |
| RaceGUIBase | race_gui_base.hpp | Abstract base for in-race HUD rendering |
| RaceGUI | race_gui.hpp | Standard race HUD with speedometer, minimap, etc. |
| RaceResultGUI | race_result_gui.hpp | Post-race results display |
| KartSelectionScreen | kart_selection.hpp | Kart and player selection interface |
| TracksAndGPScreen | tracks_and_gp_screen.hpp | Track and Grand Prix selection |
| FeatureUnlockedScreen | feature_unlocked.hpp | Unlock celebration screen |

## Subdirectories

- `dialogs/` - Modal popup dialogs (e.g., confirmation, settings)
- `help/` - Help and tutorial screens
- `online/` - Online multiplayer screens (lobbies, servers)
- `options/` - Game settings and options screens

## Dependencies

- `guiengine` - Core GUI framework and widget system
- `config` - Player profiles and settings
- `input` - Input device management
- `karts` - Kart data for selection screens
- `tracks` - Track data for selection screens
