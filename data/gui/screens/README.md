# Screen Layout Files

Full-screen menu layouts for SuperTuxKart's user interface.

## Purpose

This directory contains `.stkgui` layout files that define complete screen interfaces. Unlike dialogs, screens replace the entire view and represent major navigation points in the game such as the main menu, track selection, and options pages.

## File Format

Screens use full-viewport containers with complex nested layouts:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<stkgui>
    <div x="0" y="0" width="100%" height="100%" layout="vertical-row">
        <icon id="logo" align="center" icon="gui/icons/logo.png"/>
        <buttonbar id="menu_toprow" width="90%" align="center">
            <icon-button id="story" icon="gui/icons/menu_story.png" text="Story Mode"/>
        </buttonbar>
    </div>
</stkgui>
```

## Key Files

| File | Description |
|------|-------------|
| `main_menu.stkgui` | Primary game menu with mode selection |
| `karts.stkgui` | Kart selection screen |
| `tracks.stkgui` | Track/arena selection |
| `race_setup.stkgui` | Pre-race configuration (laps, difficulty) |
| `race_result.stkgui` | Post-race standings |
| `user_screen.stkgui` | Player profile management |
| `ghost_replay_selection.stkgui` | Replay browser |
| `addons_screen.stkgui` | Downloadable content manager |

## Subdirectories

- **help/** - Tutorial and help pages
- **online/** - Multiplayer lobby and server screens
- **options/** - Settings category screens (audio, video, input)

## How the Game Uses These Files

Each screen has a corresponding C++ class that manages state and handles events. Screen transitions are managed by a state machine that loads the appropriate layout. Element IDs in the XML map directly to event callbacks, enabling the C++ code to respond to user interactions.
