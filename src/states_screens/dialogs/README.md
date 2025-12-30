# Dialogs

*Last Updated: 2025-12-30*

Modal dialog screens and popup windows for user interaction throughout the game.

## Purpose

This directory contains modal dialog implementations that overlay the current screen to handle specific user interactions. Dialogs are used for confirmations, settings adjustment, information display, and data entry. All dialogs inherit from `GUIEngine::ModalDialog` and implement event processing for user input.

## Key Classes

| Class | File | Purpose |
|-------|------|---------|
| `MessageDialog` | message_dialog.hpp | Generic confirmation/message box with OK, Cancel, Yes/No options |
| `RacePausedDialog` | race_paused_dialog.hpp | In-race pause menu with resume, restart, quit options |
| `AddonsLoading` | addons_loading.hpp | Addon download progress and installation dialog |
| `ServerInfoDialog` | server_info_dialog.hpp | Server details with join/bookmark options |
| `ServerConfigurationDialog` | server_configuration_dialog.hpp | Server game mode and difficulty settings |
| `NetworkPlayerDialog` | network_player_dialog.hpp | Network lobby player interaction (kick, team, report) |
| `PlayerRankingsDialog` | player_rankings_dialog.hpp | Online player ranking display with top 10 list |
| `AchievementProgressDialog` | achievement_progress_dialog.hpp | Achievement details and progress tracking |
| `GhostReplayInfoDialog` | ghost_replay_info_dialog.hpp | Ghost replay management (play, compare, delete) |
| `HighScoreInfoDialog` | high_score_info_dialog.hpp | High score details with race replay option |
| `SelectChallengeDialog` | select_challenge.hpp | Challenge selection with difficulty levels |
| `CustomVideoSettingsDialog` | custom_video_settings.hpp | Advanced graphics settings configuration |
| `ConfirmResolutionDialog` | confirm_resolution_dialog.hpp | Resolution change confirmation with timeout |
| `MultitouchSettingsDialog` | multitouch_settings_dialog.hpp | Touch control sensitivity settings |
| `PressAKeyDialog` | press_a_key_dialog.hpp | Input binding capture for key/button mapping |
| `AddDeviceDialog` | add_device_dialog.hpp | Warning when creating multiple keyboard configs |
| `RegistrationDialog` | registration_dialog.hpp | Online account registration prompt |
| `VoteDialog` | vote_dialog.hpp | Addon rating submission dialog |
| `EnterAddressDialog` | enter_address_dialog.hpp | Manual server address entry |
| `SplitscreenPlayerDialog` | splitscreen_player_dialog.hpp | Local multiplayer player assignment |
| `UserInfoDialog` | user_info_dialog.hpp | Online user profile with friend actions |
| `DownloadAssets` | download_assets.hpp | Mobile asset download progress (MOBILE_STK only) |

## Architecture

All dialogs follow a common pattern:

```cpp
class ExampleDialog : public GUIEngine::ModalDialog
{
    // Event handling
    GUIEngine::EventPropagation processEvent(const std::string& eventSource);

    // Lifecycle callbacks
    void beforeAddingWidgets();
    void init();
    void onUpdate(float dt);

    // Self-destruction pattern (safe dismiss from event handlers)
    bool m_self_destroy;
};
```

## Dialog Types

- **Confirmation**: MessageDialog variants (OK, Yes/No, OK/Cancel)
- **Progress**: AddonsLoading, DownloadAssets with progress bars
- **Settings**: CustomVideoSettingsDialog, MultitouchSettingsDialog
- **Information**: HighScoreInfoDialog, AchievementProgressDialog
- **Network**: ServerInfoDialog, NetworkPlayerDialog, PlayerRankingsDialog
- **Input**: PressAKeyDialog, EnterAddressDialog
