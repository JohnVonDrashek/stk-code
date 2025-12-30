# Common Skin Assets

Shared UI assets used across multiple SuperTuxKart themes.

## Purpose

This directory contains UI element images that are common to multiple skins. When a skin element specifies `common="y"` in its XML definition, the game loads the image from this directory instead of the skin's own folder. This reduces asset duplication and ensures visual consistency for shared elements.

## File Types

All assets are PNG images with transparency support for UI overlay rendering.

## Key Assets

| Category | Files | Description |
|----------|-------|-------------|
| Backgrounds | `background.jpg`, `bottom_bar.png` | Default background and bottom bar |
| Dialogs | `dialog.png`, `tooltip.png` | Modal dialog and tooltip backgrounds |
| Buttons | `glassbutton_deactivated.png` | Disabled button state |
| Checkboxes | `glasscheckbox_*.png` | Checkbox states (checked, deactivated) |
| Spinners | `glassspinner*.png`, `spinner_rainbow*.png` | Number selector and color picker spinners |
| Focus Halos | `glass_square_focused_*.png` | Player-colored focus indicators (cyan, yellow, red, green, pink, black) |
| List UI | `list_sort_up.png`, `list_sort_down.png`, `table_header.png` | Table sorting and headers |
| Scrollbars | `scrollbar_*.png` | Scrollbar background, thumb, and buttons |
| Arrows | `left_arrow.png`, `right_arrow.png` | Navigation arrows |
| Progress | `progress_bg.png`, `gauge_fill_rainbow.png` | Progress bars and color gauge fills |
| Rating | `rating_star.png` | Star rating display |
| Glass Sections | `glass_section.png`, `glass_rsection.png`, `glass_square_*.png` | Decorative glass panel elements in various colors |

## Usage

Skins reference these assets with:
```xml
<element type="bottom-bar" common="y" image="bottom_bar.png"/>
<element type="squareFocusHalo1" common="y" image="glass_square_focused_cyan.png"/>
```

The `common="y"` attribute tells the skin loader to look in this directory.
