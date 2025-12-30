# Help

*Last Updated: 2025-12-30*

Multi-page help screen system providing game instructions and documentation.

## Purpose

This directory implements the in-game help system as a series of tabbed screens. Each screen covers a different aspect of gameplay, from basic controls to advanced features. The screens share common navigation through `HelpCommon` and use a consistent tab-based interface for switching between help topics.

## Key Classes

| Class | File | Purpose |
|-------|------|---------|
| `HelpCommon` | help_common.hpp | Shared navigation utilities and tab switching |
| `HelpScreen1` | help_screen_1.hpp | Basic game controls and driving instructions |
| `HelpScreen2` | help_screen_2.hpp | Powerups and items explanation |
| `HelpScreen3` | help_screen_3.hpp | Game modes overview |
| `HelpScreen4` | help_screen_4.hpp | Multiplayer and networking guide |
| `HelpScreen5` | help_screen_5.hpp | Banana and nitro tips |
| `HelpScreen6` | help_screen_6.hpp | Story mode and challenges |
| `HelpScreen7` | help_screen_7.hpp | Additional tips and advanced techniques |

## Architecture

All help screens inherit from both `GUIEngine::Screen` and `GUIEngine::ScreenSingleton<T>`:

```cpp
class HelpScreenN : public GUIEngine::Screen,
                    public GUIEngine::ScreenSingleton<HelpScreenN>
{
    // Standard screen callbacks
    virtual void loadedFromFile() OVERRIDE;
    virtual void eventCallback(Widget*, const std::string&, int) OVERRIDE;
    virtual void init() OVERRIDE;
};
```

## Navigation

The `HelpCommon::switchTab()` function handles navigation between help screens:

```cpp
namespace HelpCommon
{
    void switchTab(std::string selected_tab);
}
```

Each screen includes a ribbon widget with tabs that call `switchTab()` to transition between help pages while maintaining a consistent navigation experience.

## Screen Content

Help screens load their content from XML layout files in `data/gui/`:
- `help/help1.stkgui` through `help/help7.stkgui`

The layouts define static text, images, and navigation elements that explain game mechanics to the player.
