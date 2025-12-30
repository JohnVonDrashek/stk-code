# Karts/Controller

*Last Updated: 2025-12-30*

Kart controller implementations for human players and AI opponents.

## Purpose

This module provides the abstraction layer between kart input and kart behavior. Controllers translate either player input or AI decisions into `KartControl` commands (steering, acceleration, braking, items, etc.). The hierarchy supports multiple game modes with specialized AI behaviors for racing, battle, and soccer.

## Key Classes

| Class | File | Purpose |
|-------|------|---------|
| `Controller` | controller.hpp | Abstract base class for all controllers |
| `KartControl` | kart_control.hpp | Data structure holding steering, acceleration, brake, nitro, fire, rescue, and skid state |
| `AIProperties` | ai_properties.hpp | Difficulty-based AI tuning parameters (item collection, skidding probability, speed caps) |

### Player Controllers

| Class | File | Purpose |
|-------|------|---------|
| `PlayerController` | player_controller.hpp | Base class for human-controlled karts; handles input actions |
| `LocalPlayerController` | local_player_controller.hpp | Local player with camera, sound effects, haptic feedback, and achievements |
| `NetworkPlayerController` | network_player_controller.hpp | Remote player in multiplayer; applies steering reduction to compensate for latency |
| `NetworkAIController` | network_ai_controller.hpp | Server-side AI that converts AI decisions to player actions for network sync |

### AI Controllers - Racing

| Class | File | Purpose |
|-------|------|---------|
| `AIBaseController` | ai_base_controller.hpp | Common AI utilities: steering, collision detection, stuck detection |
| `AIBaseLapController` | ai_base_lap_controller.hpp | Extends base for lap-based races; path computation through track graph |
| `SkiddingAI` | skidding_ai.hpp | Primary racing AI; handles steering, items, nitro, crash avoidance, and skidding |
| `TestAI` | test_ai.hpp | Development/testing variant of SkiddingAI for comparing AI algorithms |

### AI Controllers - Arena Modes

| Class | File | Purpose |
|-------|------|---------|
| `ArenaAI` | arena_ai.hpp | Base AI for navmesh-based arenas; pathfinding, stuck recovery, u-turns |
| `BattleAI` | battle_ai.hpp | AI for battle mode (Three Strikes, Capture the Flag, Free for All) |
| `SoccerAI` | soccer_ai.hpp | AI for soccer mode; ball chasing, team coordination, overtaking |
| `SpareTireAI` | spare_tire_ai.hpp | AI for spare tire powerup karts in battle mode |

### Special Controllers

| Class | File | Purpose |
|-------|------|---------|
| `EndController` | end_controller.hpp | Replaces kart controller after race finish; drives kart automatically while preserving player identity |
| `GhostController` | ghost_controller.hpp | Replays recorded kart movements for ghost races |

## Class Hierarchy

```
Controller
├── PlayerController
│   ├── LocalPlayerController
│   ├── NetworkPlayerController
│   └── NetworkAIController
├── AIBaseController
│   ├── AIBaseLapController
│   │   ├── SkiddingAI
│   │   ├── TestAI
│   │   └── EndController
│   └── ArenaAI
│       ├── BattleAI
│       │   └── SpareTireAI
│       └── SoccerAI
└── GhostController
```

## KartControl State

The `KartControl` class encapsulates all kart input state:
- **Steering**: [-1.0, 1.0] range (left to right)
- **Acceleration**: [0.0, 1.0] range
- **Brake**: boolean
- **Nitro**: boolean
- **Skid**: SC_NONE, SC_NO_DIRECTION, SC_LEFT, SC_RIGHT
- **Fire**: boolean (use item)
- **Rescue**: boolean
- **Look Back**: boolean (also affects item firing direction)

## AI Difficulty System

AI behavior is tuned per difficulty level via `AIProperties`:
- Item collection probability based on distance to player
- Speed caps for rubber-banding (slower when ahead)
- Skidding probability
- Start delay ranges
- Slipstream usage
- Item usage skill level (0-5)
- Nitro usage strategy (0-4)
