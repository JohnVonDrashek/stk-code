# Challenges

*Last Updated: 2025-12-29*

Game challenge definitions that unlock tracks, karts, and difficulty levels in Story Mode.

## Purpose

Challenges define the progression system in SuperTuxKart's Story Mode. Each challenge specifies a race or Grand Prix that players must complete to earn trophies and unlock new content. The trophy system gates access to harder challenges and rewards.

## File Format

Files use `.challenge` extension with XML structure (version 3):

```xml
<challenge version="3">
    <unlock_list list="false"/>           <!-- Show in unlock list UI -->
    <track id="track_id" laps="3" reverse="false"/>  <!-- Or grandprix id="..." -->
    <mode major="single" minor="quickrace"/>  <!-- Game mode -->
    <requirements trophies="0"/>          <!-- Trophies needed to attempt -->

    <best>                                <!-- SuperTux difficulty -->
        <karts number="7"/>
        <requirements position="1" time="130"/>
    </best>
    <hard>...</hard>
    <medium>...</medium>
    <easy>...</easy>

    <unlock kart="kart_id"/>              <!-- Optional: content unlocked -->
</challenge>
```

## Key Elements

| Element | Description |
|---------|-------------|
| `track` / `grandprix` | Race type - single track or GP series |
| `mode` | `single`/`grandprix` major; `quickrace`/`timetrial` minor |
| `requirements` | Trophy count needed to unlock challenge |
| `karts number` | Number of AI opponents per difficulty |
| `replay_file` | Ghost replay for time trial challenges |
| `unlock` | Kart, track, or difficulty to unlock on completion |

## Challenge Types

- **Track challenges** (`*.challenge`): Race on individual tracks (e.g., `abyss.challenge`)
- **Grand Prix challenges** (`gp*.challenge`): Complete a GP series
- **Unlock challenges** (`unlock_*.challenge`): Trophy-gated unlocks for karts/difficulties

## How the Game Uses These Files

The challenge manager loads all `.challenge` files at startup and builds the Story Mode progression tree. Players earn trophies (1 easy, 2 medium, 3 hard, 4 best) per challenge, which accumulate to unlock higher-tier challenges.
