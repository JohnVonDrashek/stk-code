# widgets

*Last Updated: 2025-12-30*

Concrete widget implementations for the SuperTuxKart GUI engine.

## Purpose

This directory contains all widget types available in the GUI framework. Each widget inherits from the base `Widget` class and can be declared in XML layout files or created programmatically. Widgets handle their own rendering, input events, and state management.

## Key Classes

| Class | File | Purpose |
|-------|------|---------|
| `BubbleWidget` | bubble_widget.hpp | Expandable text widget that zooms when focused |
| `ButtonWidget` | button_widget.hpp | Standard text button |
| `CheckBoxWidget` | check_box_widget.hpp | Boolean toggle checkbox |
| `DynamicRibbonWidget` | dynamic_ribbon_widget.hpp | Scrollable multi-row icon grid with dynamic content |
| `IconButtonWidget` | icon_button_widget.hpp | Button with icon and optional label |
| `KartStatsWidget` | kart_stats_widget.hpp | Displays kart statistics (mass, speed, acceleration, nitro) |
| `LabelWidget` | label_widget.hpp | Static text display with optional scrolling |
| `ListWidget` | list_widget.hpp | Vertical list with sortable columns and icons |
| `ModelViewWidget` | model_view_widget.hpp | 3D model preview with rotation support |
| `PlayerKartWidget` | player_kart_widget.hpp | Composite widget for kart selection screen |
| `ProgressBarWidget` | progress_bar_widget.hpp | Animated progress indicator |
| `RatingBarWidget` | rating_bar_widget.hpp | Star rating display and input |
| `RibbonWidget` | ribbon_widget.hpp | Horizontal/vertical tab bar or toolbar |
| `SkillLevelWidget` | skill_level_widget.hpp | Icon with progress bar for stat display |
| `SpinnerWidget` | spinner_widget.hpp | Numeric/option selector with arrows |
| `TextBoxWidget` | text_box_widget.hpp | Text input field with keyboard support |

## Internal Irrlicht Widgets

| Class | File | Purpose |
|-------|------|---------|
| `CGUIEditBox` | CGUIEditBox.hpp | Low-level text editing with IME/composition support |
| `CGUISTKListBox` | CGUISTKListBox.hpp | Custom Irrlicht list box with multi-column cells |

## Widget Hierarchy

```
Widget (base class)
  |-- ButtonWidget
  |-- BubbleWidget
  |-- CheckBoxWidget
  |-- LabelWidget
  |-- ListWidget
  |-- ProgressBarWidget
  |-- RatingBarWidget
  |-- RibbonWidget
  |     \-- DynamicRibbonWidget
  |-- SpinnerWidget
  |-- TextBoxWidget
  |-- IconButtonWidget
  |     \-- ModelViewWidget
  |-- SkillLevelWidget
  |-- KartStatsWidget
  \-- PlayerKartWidget
```

## Common Patterns

- **add()**: Creates the underlying Irrlicht GUI element
- **resize()**: Handles layout recalculation on window resize
- **transmitEvent()**: Propagates UI events to parent widgets
- **focused()/unfocused()**: Handle focus state changes
- **update()**: Per-frame updates for animations

## XML Usage

Widgets are typically declared in screen XML files:

```xml
<button id="start_race" text="Start Race"/>
<spinner id="difficulty" min="0" max="3"/>
<ribbon id="tabs" type="tabs">
    <icon-button id="tab1" icon="..." text="Tab 1"/>
</ribbon>
```
