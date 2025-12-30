# Online

*Last Updated: 2025-12-30*

Online multiplayer and networking UI screens for server browsing, lobbies, and profiles.

## Purpose

This directory contains all screens related to online multiplayer functionality. It handles user authentication, server discovery and selection, network lobby management, player profiles, and online racing setup. These screens integrate with the `network/` and `online/` modules for actual network communication.

## Key Classes

| Class | File | Purpose |
|-------|------|---------|
| `OnlineScreen` | online_screen.hpp | Main networking menu with news, login status, and mode selection |
| `OnlineProfileBase` | online_profile_base.hpp | Base class for tabbed profile screens (friends, achievements, settings) |
| `OnlineProfileFriends` | online_profile_friends.hpp | Friends list management and search |
| `OnlineProfileAchievements` | online_profile_achievements.hpp | Achievement display with sorting and progress |
| `OnlineProfileSettings` | online_profile_settings.hpp | Account settings (password, email changes) |
| `OnlineProfileServers` | online_profile_servers.hpp | Quick play and server access |
| `NetworkingLobby` | networking_lobby.hpp | Pre-race lobby with chat, player list, and game configuration |
| `ServerSelection` | server_selection.hpp | Server browser with filtering, search, and bookmarks |
| `CreateServerScreen` | create_server_screen.hpp | Server creation with game mode and player limit settings |
| `OnlineLanScreen` | online_lan.hpp | LAN game discovery and hosting |
| `RegisterScreen` | register_screen.hpp | Account registration (new, existing, or offline) |
| `OnlineUserSearch` | online_user_search.hpp | Search for players by username |
| `TracksScreen` | tracks_screen.hpp | Track voting and selection for online races |
| `NetworkKartSelectionScreen` | network_kart_selection.hpp | Kart selection with server-allowed kart filtering |

## Architecture

### Profile Screens

Profile screens share a common base with tab navigation:

```cpp
class OnlineProfileBase : public GUIEngine::Screen
{
protected:
    GUIEngine::RibbonWidget* m_profile_tabs;
    Online::OnlineProfile* m_visiting_profile;
};

class OnlineProfileFriends : public OnlineProfileBase,
                             public GUIEngine::ScreenSingleton<OnlineProfileFriends>
```

### Lobby System

The `NetworkingLobby` handles the pre-game waiting room:

- Player list with ping display
- Chat system with scrollback
- Server info and configuration
- Ready/start game flow
- Live join support

### Server Browser

`ServerSelection` provides server discovery:

- Filters: private servers, IPv6, bookmarks
- Search by server name
- Column sorting (players, ping, difficulty)
- Auto-refresh with configurable interval

## Screen Flow

```
OnlineScreen
    |
    +-> RegisterScreen (new account)
    |
    +-> ServerSelection -> ServerInfoDialog -> NetworkingLobby
    |                                              |
    +-> CreateServerScreen -> NetworkingLobby      +-> NetworkKartSelectionScreen
    |                                              |
    +-> OnlineLanScreen                            +-> TracksScreen (voting)
    |
    +-> OnlineProfileBase tabs
            |
            +-> OnlineProfileFriends
            +-> OnlineProfileAchievements
            +-> OnlineProfileSettings
```

## Key Features

- **News Feed**: OnlineScreen displays game news with headline icons
- **Server Bookmarks**: Save favorite servers for quick access
- **Chat**: Real-time chat in lobby with emoji support
- **Player Management**: Kick, report, change teams in lobby
- **Track Voting**: Peer-to-peer track selection with timer
