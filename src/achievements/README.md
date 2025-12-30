# Achievements Module

*Last Updated: 2025-12-29*

Manages player achievements, tracking progress and completion status.

## Purpose

This module handles the achievement system for SuperTuxKart. It reads achievement definitions from `data/achievements.xml`, tracks player progress toward each achievement's goals, and synchronizes achievement status with the online server for logged-in players.

## Key Classes

| Class | File | Purpose |
|-------|------|---------|
| `AchievementsManager` | achievements_manager.hpp | Singleton that loads and manages all achievement definitions |
| `Achievement` | achievement.hpp | Tracks progress for a single achievement per player |
| `AchievementInfo` | achievement_info.hpp | Stores the static definition and goal tree for an achievement |
| `AchievementsStatus` | achievements_status.hpp | Holds all achievement progress for a player profile |
| `WebAchievementsStatus` | web_achievements_status.hpp | Syncs achievement data with the online server |

## Dependencies

- **config/**: Player profiles store achievement status
- **io/**: XML parsing for achievement definitions
- **online/**: Web synchronization of achievement progress
