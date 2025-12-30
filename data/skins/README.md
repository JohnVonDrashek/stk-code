# Skins

*Last Updated: 2025-12-29*

UI themes and visual styles for SuperTuxKart's menu system.

## Purpose

This directory contains skin themes that customize the appearance of SuperTuxKart's user interface, including buttons, checkboxes, spinners, dialogs, backgrounds, and color schemes. Each skin defines a complete visual style through XML configuration and PNG image assets.

## Theme System

SuperTuxKart uses a hierarchical theme system with **base themes** and **color variants**:

| Base Theme | Variants |
|------------|----------|
| `cartoon` | cartoon-coal, cartoon-desert, cartoon-forest, cartoon-ocean, cartoon-ruby |
| `classic` | classic-coal, classic-desert, classic-forest, classic-ocean, classic-ruby |

Variant themes use `base_theme="cartoon"` or `base_theme="classic"` to inherit unspecified elements from their parent, reducing asset duplication.

## Skin Structure

Each skin folder contains:
- `stkskin.xml` - Theme configuration defining UI elements and colors
- `background.jpg` - Main menu background image
- `*.png` - UI element images (buttons, checkboxes, spinners, etc.)
- `licenses.txt` - Asset licensing information
- `data/` (optional) - Custom icons and additional assets

## XML Format

The `stkskin.xml` file defines:
```xml
<skin base_theme_name="Cartoon" variant_name="Ocean" base_theme="cartoon">
  <element type="button" state="neutral" image="button.png"
           left_border="40" right_border="40" .../>
  <color type="text" state="neutral" r="0" g="0" b="0"/>
</skin>
```

Key attributes:
- **type** - Widget type (button, checkbox, spinner, dialog, etc.)
- **state** - Widget state (neutral, focused, down, deactivated)
- **image** - PNG file for this element
- **border sizes** - 9-slice stretching configuration
- **common="y"** - Load from `common/` shared assets

## Subdirectory

- **common/** - Shared UI assets used across multiple themes

See `SKIN_MAKING.md` for detailed skin creation instructions.
