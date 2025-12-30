# Options

*Last Updated: 2025-12-30*

Settings and configuration screens for game options, graphics, audio, and input.

## Purpose

This directory contains all settings screens accessible from the main menu options. The screens are organized as tabs sharing common navigation through `OptionsCommon`. Settings are persisted via `UserConfig` and applied immediately or on restart depending on the setting type.

## Key Classes

| Class | File | Purpose |
|-------|------|---------|
| `OptionsCommon` | options_common.hpp | Shared navigation utilities and tab switching |
| `OptionsScreenGeneral` | options_screen_general.hpp | General settings (internet, skins, misc options) |
| `OptionsScreenVideo` | options_screen_video.hpp | Graphics quality, effects, and rendering options |
| `OptionsScreenDisplay` | options_screen_display.hpp | Resolution, fullscreen, and camera settings |
| `OptionsScreenAudio` | options_screen_audio.hpp | Music and sound effects volume controls |
| `OptionsScreenInput` | options_screen_input.hpp | Input device list and configuration |
| `OptionsScreenDevice` | options_screen_device.hpp | Per-device key binding configuration |
| `OptionsScreenUI` | options_screen_ui.hpp | UI settings, skins, camera presets, minimap |
| `OptionsScreenLanguage` | options_screen_language.hpp | Language and localization selection |
| `BaseUserScreen` | user_screen.hpp | Player profile management and login |
| `UserScreen` | user_screen.hpp | Standalone user selection (first launch) |
| `TabbedUserScreen` | user_screen.hpp | User screen as options tab |

## Architecture

All options screens inherit from both `GUIEngine::Screen` and `GUIEngine::ScreenSingleton<T>`:

```cpp
class OptionsScreenVideo : public GUIEngine::Screen,
                           public GUIEngine::ScreenSingleton<OptionsScreenVideo>
{
    // Standard screen callbacks
    virtual void loadedFromFile() OVERRIDE;
    virtual void eventCallback(Widget*, const std::string&, int) OVERRIDE;
    virtual void init() OVERRIDE;
    virtual void tearDown() OVERRIDE;
};
```

## Navigation

The `OptionsCommon` namespace provides tab switching:

```cpp
namespace OptionsCommon
{
    void switchTab(std::string selected_tab);
    void setTabStatus();
}
```

## Options Categories

### General (OptionsScreenGeneral)
- Internet connectivity settings
- Skin selection
- Miscellaneous preferences

### Video (OptionsScreenVideo)
- Graphics presets (low to ultra)
- Advanced pipeline options
- Shadows, bloom, motion blur
- Image quality and RTT scaling

### Display (OptionsScreenDisplay)
- Screen resolution list
- Fullscreen/windowed mode
- Camera FOV and settings
- Split-screen layout

### Audio (OptionsScreenAudio)
- Master volume
- Music volume
- Sound effects volume
- Enable/disable audio

### Input (OptionsScreenInput)
- Connected device list
- Device icons and status
- Add new device option

### Device (OptionsScreenDevice)
- Action-to-key mapping
- Binding capture via PressAKeyDialog
- Conflict detection

### UI (OptionsScreenUI)
- Base skin and variants
- Camera preset selection
- Minimap settings
- Font scaling

### Language (OptionsScreenLanguage)
- Available language list
- Right-to-left language support

### User (BaseUserScreen)
- Player profile selection
- Online/offline mode toggle
- Login/logout functionality
- Profile creation and deletion

## Settings Persistence

Settings are saved to `UserConfig` (`user_config.hpp`) and written to `config.xml`. Some settings require restart:

- Resolution changes
- Renderer changes
- Some graphics options

The `ConfirmResolutionDialog` provides a timeout-based confirmation for resolution changes to prevent unusable configurations.
