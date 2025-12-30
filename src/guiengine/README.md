# GUI Engine Module

*Last Updated: 2025-12-29*

Generic GUI framework providing widgets, screens, skins, and event handling for SuperTuxKart.

## Purpose

This module contains the complete GUI subsystem including widget definitions, screen management, layout engine, skinning support, and input event handling. It provides a declarative XML-based UI system built on top of Irrlicht's GUI facilities with custom focus management to support multiple players.

## Key Classes

| Class | File | Purpose |
|-------|------|---------|
| GUIEngine | engine.hpp | Core engine initialization, font management, device access |
| Widget | widget.hpp | Base class for all UI widgets with properties and badges |
| Screen | screen.hpp | Base class for full-screen UI pages |
| ModalDialog | modaldialog.hpp | Popup dialog windows |
| Skin | skin.hpp | Handles visual theming and widget rendering |
| EventHandler | event_handler.hpp | Processes and dispatches UI input events |
| LayoutManager | layout_manager.hpp | Calculates widget positions from XML layouts |
| AbstractStateManager | abstract_state_manager.hpp | Manages screen transitions and game state |
| ScreenKeyboard | screen_keyboard.hpp | On-screen keyboard for touch/gamepad input |

## Dependencies

- **input/**: Receives input events for UI navigation
- **graphics/**: Uses IrrDriver for rendering
- **states_screens/**: Contains actual STK screen implementations (separate module)
- **Irrlicht**: Underlying GUI and font systems

## Widget Types

Supports: ribbons, buttons, checkboxes, labels, spinners, lists, textboxes, progress bars, model views, and dynamic ribbons.
