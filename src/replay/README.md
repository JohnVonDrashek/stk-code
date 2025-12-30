# Replay Module

*Last Updated: 2025-12-29*

Race replay recording and ghost kart playback system.

## Purpose

This module handles recording race sessions and playing them back as ghost karts. It captures kart transforms, physics state, and item usage at regular intervals, storing them in versioned replay files. Replays are used for time trial ghosts, allowing players to race against their previous best times.

## Key Classes

| Class | File | Purpose |
|-------|------|---------|
| `ReplayBase` | replay_base.hpp | Base class defining replay data structures (TransformEvent, PhysicInfo, BonusInfo) |
| `ReplayRecorder` | replay_recorder.hpp | Records kart state during races, saves to replay files |
| `ReplayPlay` | replay_play.hpp | Loads replay files and provides ghost kart data for playback |

## Data Structures

- **TransformEvent**: Position and rotation at a specific time
- **PhysicInfo**: Speed, steering, suspension state, skidding
- **BonusInfo**: Attachments, nitro, items, mode-specific values
- **KartReplayEvent**: Distance, nitro/zipper usage, visual effects

## File Format

Replay files use a versioned binary format (current version: 4, minimum supported: 3) stored in the user data directory.

## Dependencies

- **karts/** - GhostKart for playback visualization
- **items/** - Attachment and powerup type encoding
- **modes/** - World access during recording
