# SuperTuxKart - Claude Onboarding

Open-source kart racing game written in C++. Uses CMake build system.

> **Note**: Each directory has its own README.md with detailed documentation.

## Quick Start

```bash
# Dependencies (macOS)
brew bundle

# Build
mkdir cmake_build && cd cmake_build
cmake .. -DCMAKE_BUILD_TYPE=Release
make -j$(nproc)

# Run
./bin/supertuxkart.app/Contents/MacOS/supertuxkart
```

Assets required: Clone `stk-assets` as sibling directory via SVN (see INSTALL.md).

## Key Entry Points

| File | Purpose |
|------|---------|
| `src/main.cpp` | Application entry, initialization, CLI parsing |
| `src/main_loop.cpp` | Main game loop (`MainLoop::run()`) |
| `src/race/race_manager.hpp` | Race configuration, mode selection, kart management |
| `src/states_screens/state_manager.hpp` | UI state machine, screen transitions |
| `src/graphics/irr_driver.cpp` | Graphics initialization and rendering driver |

## Top-Level Directory Guide

| Directory | Purpose | Key Contents |
|-----------|---------|--------------|
| `android/` | Android build system | `make.sh`, Gradle config, JNI bindings |
| `cmake/` | CMake modules | Find*.cmake, toolchain files for cross-compilation |
| `data/` | Game assets & configs | `stk_config.xml`, shaders/, skins/, po/ (localization) |
| `doc/` | Developer documentation | Pipeline overview, graphics XML docs, protocols |
| `lib/` | Bundled libraries | irrlicht, bullet, enet, angelscript, wiiuse, etc. |
| `src/` | Game source code | 25 modules (see below) |
| `switch/` | Nintendo Switch port | devkitPro build scripts, Switch-specific code |
| `tools/` | Development utilities | Build scripts, asset tools, server deployment |
| `windows/` | Windows build files | Installer resources, DPI manifest |

## Source Code Modules (src/)

### Core Systems
| Module | Key Class | Purpose |
|--------|-----------|---------|
| `modes/` | `World`, `LinearWorld` | Game mode logic (races, battles, soccer) |
| `race/` | `RaceManager` | Race configuration singleton, mode selection |
| `karts/` | `Kart`, `KartProperties` | Kart physics, models, characteristics |
| `tracks/` | `Track`, `TrackManager` | Track loading, navigation graphs, checkpoints |
| `physics/` | `Physics`, `btKart` | Bullet physics integration, raycast vehicle |

### Graphics & Audio
| Module | Key Class | Purpose |
|--------|-----------|---------|
| `graphics/` | `IrrDriver`, `AbstractRenderer` | Irrlicht wrapper, rendering pipeline |
| `audio/` | `SFXManager`, `MusicManager` | OpenAL sound effects and music |
| `font/` | `FontManager`, `FontWithFace` | FreeType/HarfBuzz text rendering |
| `animations/` | `AnimationBase`, `Ipo` | IPO-based animations from Blender |

### UI & Input
| Module | Key Class | Purpose |
|--------|-----------|---------|
| `guiengine/` | `GUIEngine`, `Widget` | Generic GUI framework, XML layouts |
| `states_screens/` | `StateManager`, `Screen` | UI screens, dialogs, state machine |
| `input/` | `InputManager`, `DeviceManager` | Keyboard, gamepad, Wiimote handling |

### Networking & Online
| Module | Key Class | Purpose |
|--------|-----------|---------|
| `network/` | `STKHost`, `NetworkConfig` | Multiplayer infrastructure, protocols |
| `online/` | `RequestManager`, `HTTPRequest` | HTTP requests, user auth, profiles |

### Content & Progression
| Module | Key Class | Purpose |
|--------|-----------|---------|
| `items/` | `ItemManager`, `Powerup` | Collectibles, weapons, powerups |
| `challenges/` | `UnlockManager`, `ChallengeData` | Story mode progression, unlocks |
| `achievements/` | `AchievementsManager` | Achievement tracking, online sync |
| `addons/` | `AddonsManager`, `Addon` | Downloadable content management |

### Utilities
| Module | Key Class | Purpose |
|--------|-----------|---------|
| `config/` | `UserConfig`, `STKConfig` | Configuration management, player profiles |
| `io/` | `FileManager`, `XMLNode` | File I/O, XML parsing, path management |
| `utils/` | `StringUtils`, `Log`, `Vec3` | Common utilities, math, logging |
| `scriptengine/` | `ScriptEngine` | AngelScript integration for tracks |
| `replay/` | `ReplayRecorder`, `ReplayPlay` | Ghost kart recording and playback |
| `tips/` | `TipsManager` | Loading screen tips |

## Architecture Overview

```
main.cpp → MainLoop → StateManager (menus) ↔ RaceManager → World (game modes)
                              ↓                                    ↓
                        GUIEngine (widgets)              Karts, Tracks, Items
                              ↓                                    ↓
                        IrrDriver (graphics)  ←───────────  Physics (Bullet)
```

### Core Singletons
- `main_loop` - Game loop timing and execution
- `race_manager` - Race configuration and state
- `irr_driver` - Irrlicht graphics wrapper
- `stk_config` - Global game configuration
- `StateManager::get()` - UI state machine
- `input_manager` - Input device handling

### Game Modes (src/modes/)
All inherit from `World`:
- `StandardRace` - Normal racing
- `SoccerWorld` - Ball-based mode
- `CaptureTheFlag` - Team CTF
- `FreeForAll` - Battle mode
- `FollowTheLeader` - Chase mode
- `EasterEggHunt` - Collectible hunt

## Patterns & Conventions

### Naming
- Classes: `PascalCase`
- Methods: `camelCase`
- Members: `m_snake_case`
- Files: `snake_case.cpp/.hpp`

### Code Style
- Header guards: `#ifndef HEADER_FILENAME_HPP`
- Doxygen comments for public APIs
- Extensive use of manager pattern (KartPropertiesManager, TrackManager, etc.)

### Coordinate System
- **STK**: X right, Y up, Z forwards
- **Blender**: X right, Y forwards, Z up
- Export tools handle conversion automatically

## Build Options

| CMake Option | Description |
|-------------|-------------|
| `SERVER_ONLY=ON` | Headless server build |
| `USE_GLES2=ON` | OpenGL ES2 renderer (mobile/ARM) |
| `BUILD_RECORDER=OFF` | Disable in-game recording |
| `USE_WIIUSE=OFF` | Disable Wiimote support |

## Testing

No formal test suite. Manual testing via game execution.
Server testing: `supertuxkart --server-config=config.xml --network-console`

## Key Documentation

- `README.md` - Project overview
- `INSTALL.md` - Build instructions per platform
- `NETWORKING.md` - Server hosting guide
- `CHANGELOG.md` - Version history
- `src/main.cpp` - Module interaction diagram (Doxygen)
- `doc/pipeline_overview.txt` - Rendering pipeline

## Rendering Pipeline

1. Init: glow setup → 3D skybox
2. Main: solids → glows → shadows → lights → post-processing
3. Transparent: transparents → displacement → final PP
4. GUI: overlay rendering
