# Dialog Layout Files

Modal popup dialogs displayed over the main game screens.

## Purpose

This directory contains `.stkgui` layout files for dialog windows that appear on top of the current screen. Dialogs are used for confirmations, settings adjustments, and information display without leaving the current context.

## File Format

Dialogs use the same XML format as screen layouts, but typically define smaller, centered containers:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<stkgui>
    <div x="2%" y="5%" width="96%" height="90%" layout="vertical-row">
        <label id="title" text_align="center" word_wrap="true"/>
        <buttonbar id="buttons" height="30%" width="70%" align="center">
            <icon-button id="cancel" icon="gui/icons/red_x.png" text="Cancel"/>
            <icon-button id="confirm" icon="gui/icons/green_check.png" text="Yes"/>
        </buttonbar>
    </div>
</stkgui>
```

## Key Files

| File | Description |
|------|-------------|
| `confirm_dialog.stkgui` | Generic yes/no confirmation prompt |
| `race_paused_dialog.stkgui` | Pause menu during races |
| `custom_video_settings.stkgui` | Advanced graphics options |
| `ghost_replay_info_dialog.stkgui` | Replay file details and actions |
| `press_a_key_dialog.stkgui` | Input binding capture |

## Subdirectories

- **android/** - Android-specific dialog variants
- **online/** - Multiplayer and network-related dialogs

## How the Game Uses These Files

Dialog classes inherit from a base modal handler. When triggered, the dialog loads its layout, renders over the current screen with a dimmed background, and captures all input until dismissed. The element IDs map to event handlers in the corresponding C++ dialog class.
