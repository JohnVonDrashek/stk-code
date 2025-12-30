# Modes Module

Game mode logic for races, battles, and other gameplay types.

## Purpose

This module contains the core game loop and logic for all gameplay modes in SuperTuxKart. It manages race state, kart updates, timing, lap counting, scoring, and win conditions. Each game mode inherits from the base World class and implements mode-specific rules.

## Key Classes

| Class | File | Purpose |
|-------|------|---------|
| World | world.hpp | Base class for all game modes, manages karts and race state |
| WorldStatus | world_status.hpp | Race clock and phase management (ready/set/go/racing) |
| WorldWithRank | world_with_rank.hpp | Adds ranking/position tracking to World |
| LinearWorld | linear_world.hpp | Standard lap-based racing with driveline tracking |
| StandardRace | standard_race.hpp | Normal race mode implementation |
| FollowTheLeader | follow_the_leader.hpp | Elimination mode where last place is removed |
| ThreeStrikesBattle | three_strikes_battle.hpp | Arena battle with lives |
| SoccerWorld | soccer_world.hpp | Soccer/football game mode |
| CaptureTheFlag | capture_the_flag.hpp | CTF battle mode |
| FreeForAll | free_for_all.hpp | Deathmatch-style battle mode |
| EasterEggHunt | easter_egg_hunt.hpp | Collectible hunt mode |
| CutsceneWorld | cutscene_world.hpp | Non-interactive story sequences |
| Overworld | overworld.hpp | Story mode hub world |
| DemoWorld | demo_world.hpp | Attract mode / demo playback |

## Dependencies

- **karts/**: Creates and updates all karts in the race
- **tracks/**: Track loading and checkpoint management
- **items/**: Item and projectile management during gameplay
- **graphics/**: Weather effects, race GUI rendering
- **network/**: Multiplayer game state synchronization
- **race/**: RaceManager provides race configuration
