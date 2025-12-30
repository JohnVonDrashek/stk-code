# Network Protocols

*Last Updated: 2025-12-30*

Implementation of multiplayer network protocols for client-server communication.

## Purpose

This module contains the protocol implementations that handle all networked multiplayer communication. Protocols manage connection establishment, lobby synchronization, game state transmission, and in-game events. The architecture uses a base `Protocol` class with specialized implementations for lobby management (client/server), gameplay synchronization, and peer connections.

## Key Classes

| Class | File | Purpose |
|-------|------|---------|
| `LobbyProtocol` | `lobby_protocol.hpp` | Abstract base class for lobby protocols; manages voting, game setup, and player state synchronization |
| `ClientLobby` | `client_lobby.hpp` | Client-side lobby handling; connection state machine, server info, kart/track selection, live join support |
| `ServerLobby` | `server_lobby.hpp` | Server-side lobby management; player connections, voting, race lifecycle, AI profiles, ban lists |
| `GameProtocol` | `game_protocol.hpp` | In-race state synchronization; controller actions, item updates, time adjustments, rewind support |
| `GameEventsProtocol` | `game_events_protocol.hpp` | Major game events (race finish, goals, CTF scores, startup boost, checkpoint validation) |
| `ConnectToServer` | `connect_to_server.hpp` | Client protocol to establish connection with a server; handles NAT traversal and STK registration |
| `ConnectToPeer` | `connect_to_peer.hpp` | Server protocol to connect with incoming peers; broadcasts "aloha-stk" packets for NAT punch-through |
| `Ranking` | `ranking.hpp` | Player ranking calculations; Glicko-2-style scoring with deviation and match result processing |
| `ChatCommands` | `chat_commands.hpp` | Server-side chat command handling (`/help`, `/spectate`, `/kick`, `/mute`, addon queries) |

## Protocol Lifecycle

1. **Connection**: `ConnectToServer` (client) and `ConnectToPeer` (server) establish peer connections
2. **Lobby**: `ClientLobby`/`ServerLobby` manage player lists, voting, and race configuration
3. **Racing**: `GameProtocol` handles controller inputs and state rewind; `GameEventsProtocol` broadcasts major events
4. **Results**: Lobby protocols display results and optionally update `Ranking` scores

## Lobby Events (LE_*)

The `LobbyProtocol` defines message types for client-server communication:
- Connection: `LE_CONNECTION_REQUESTED`, `LE_CONNECTION_ACCEPTED`, `LE_CONNECTION_REFUSED`
- Selection: `LE_START_SELECTION`, `LE_KART_SELECTION`, `LE_VOTE`
- Race flow: `LE_LOAD_WORLD`, `LE_START_RACE`, `LE_RACE_FINISHED`, `LE_BACK_LOBBY`
- Live join: `LE_LIVE_JOIN`, `LE_LIVE_JOIN_ACK`, `LE_KART_INFO`
- Chat/Admin: `LE_CHAT`, `LE_KICK_HOST`, `LE_COMMAND`

## Game Events (GE_*)

`GameEventsProtocol` handles synchronization of major race milestones:
- `GE_KART_FINISHED_RACE` - Kart crossed finish line
- `GE_STARTUP_BOOST` - Starting boost/penalty calculation
- `GE_BATTLE_KART_SCORE` - Free-for-all score updates
- `GE_CTF_SCORED` - Capture the Flag scoring
- `GE_RESET_BALL` / `GE_PLAYER_GOAL` - Soccer mode events
- `GE_CHECK_LINE` - Checkpoint validation
