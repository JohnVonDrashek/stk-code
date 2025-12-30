# Network Module

Multiplayer networking infrastructure for LAN and WAN gameplay.

## Purpose

This module implements the complete networking stack for SuperTuxKart multiplayer. It handles server/client architecture, peer-to-peer connections, game state synchronization, and network protocol management. The module supports both LAN discovery and WAN connections through the STK matchmaking server.

## Key Classes

| Class | File | Purpose |
|-------|------|---------|
| `STKHost` | stk_host.hpp | Main network host managing connections, peers, and the ENet interface |
| `NetworkConfig` | network_config.hpp | Singleton storing network configuration (server/client mode, LAN/WAN, IP type) |
| `STKPeer` | stk_peer.hpp | Represents a connected peer with network profile and communication methods |
| `ProtocolManager` | protocol_manager.hpp | Manages network protocols lifecycle and message routing |
| `RewindManager` | rewind_manager.hpp | Handles game state rewinding for lag compensation |
| `Server` | server.hpp | Server information and configuration for game lobbies |
| `NetworkString` | network_string.hpp | Serialization/deserialization of network messages |
| `GameSetup` | game_setup.hpp | Stores race configuration shared between server and clients |

## Subdirectories

- `protocols/` - Individual protocol implementations (lobby, game events, synchronization)

## Dependencies

- **online/** - HTTP requests for WAN server registration and authentication
- **race/** - Race configuration and game mode information
- **karts/** - Kart state synchronization
- **ENet** - UDP networking library (external dependency)
- **Crypto** - Encryption via OpenSSL, mbedTLS, or CryptoKit
