# Challenges Module

*Last Updated: 2025-12-29*

Manages the story mode challenge system and unlockable content.

## Purpose

This module implements the challenge/story mode system where players complete races under specific conditions to unlock new tracks, karts, and game modes. It tracks challenge completion across difficulty levels, manages unlock requirements, and provides the speedrun timer for story mode.

## Key Classes

| Class | File | Purpose |
|-------|------|---------|
| `UnlockManager` | unlock_manager.hpp | Main controller for challenge loading and unlock detection |
| `ChallengeData` | challenge_data.hpp | Defines a challenge's requirements, rewards, and race parameters |
| `ChallengeStatus` | challenge_status.hpp | Tracks completion state per difficulty for a single challenge |
| `StoryModeStatus` | story_mode_status.hpp | Aggregates all challenge progress for a player profile |
| `StoryModeTimer` | story_mode_timer.hpp | Tracks total play time for speedrun mode |

## Dependencies

- **config/**: Player profiles store story mode progress
- **race/**: RaceManager for setting up challenge races
- **audio/**: Locked sound effect when accessing unavailable content
- **io/**: XML parsing for challenge definition files
