# GUI Layout Files

User interface layout definitions for SuperTuxKart menus and dialogs.

## Purpose

This directory contains XML-based layout files that define the structure and appearance of all in-game user interface elements. The game engine parses these files at runtime to render menus, dialogs, and HUD components with proper positioning, sizing, and interactive behavior.

## File Format

Files use the `.stkgui` extension with a custom XML schema:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<stkgui>
    <div x="0" y="0" width="100%" height="100%" layout="vertical-row">
        <label id="title" text="Hello" />
        <icon-button id="confirm" icon="gui/icons/green_check.png" text="OK" />
    </div>
</stkgui>
```

Key XML elements include:
- `<div>` - Container with layout options (`vertical-row`, `horizontal-row`)
- `<label>` - Text display with alignment and wrapping options
- `<icon-button>` - Clickable button with icon and text
- `<buttonbar>` - Horizontal row of buttons
- `<spacer>` - Empty space for layout control

Positioning uses percentages (`width="90%"`) or fixed pixels (`height="128"`). The `I18N` attribute marks strings for translation.

## Subdirectories

- **dialogs/** - Modal popup dialogs (confirmations, settings panels)
- **icons/** - PNG image assets used by UI elements
- **screens/** - Full-screen menu layouts (main menu, track selection, options)

## How the Game Uses These Files

The GUI engine loads `.stkgui` files based on the current game state. Each screen or dialog has a corresponding C++ class that handles events from interactive elements identified by their `id` attribute. Icon paths are relative to `data/gui/`.
