# GUI Icon Assets

PNG image files used throughout the SuperTuxKart user interface.

## Purpose

This directory contains all graphical assets displayed in menus, dialogs, and HUD elements. Icons provide visual feedback for buttons, game modes, power-ups, difficulty levels, and status indicators.

## File Format

All icons are PNG files with transparency support. Common sizes include:
- **64x64** - Small toolbar buttons and indicators
- **128x128** - Standard menu buttons and mode icons
- **Larger** - Logo and decorative elements

## Naming Conventions

| Pattern | Usage |
|---------|-------|
| `main_*.png` | Main menu button icons |
| `menu_*_focus.png` | Hover/focus state variants |
| `mode_*.png` | Game mode indicators (normal, time-trial, soccer) |
| `options_*.png` | Settings category icons |
| `difficulty_*.png` | Easy, medium, hard, expert indicators |
| `cup_*.png` | Trophy icons (bronze, silver, gold, platinum) |
| `*-icon.png` | Power-up and item icons |

## Key Files

- `logo.png` / `logo_slim.png` - SuperTuxKart branding
- `green_check.png` / `red_x.png` - Confirmation/cancel buttons
- `loading.png` - Loading screen indicator
- `licenses.txt` - Attribution and license information for all assets

## Subdirectories

- **android/** - Mobile-specific UI elements
- **online/** - Multiplayer status and lobby icons

## How the Game Uses These Files

UI layout files reference icons by relative path (e.g., `icon="gui/icons/main_race.png"`). The renderer loads these on demand and caches them for performance. Focus variants provide visual feedback when elements are selected via keyboard or gamepad navigation.
