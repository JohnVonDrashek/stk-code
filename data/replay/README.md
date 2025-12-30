# Ghost Replay Recordings

*Last Updated: 2025-12-29*

Pre-recorded race replays used for ghost mode and benchmarking.

## Purpose

This directory contains replay files that record kart positions, rotations, and inputs throughout a race. These replays serve as ghost opponents in time trial mode, allowing players to race against recorded performances. They also provide benchmarking data and challenge targets.

## File Format

Replay files use a space-delimited text format with a header section followed by frame data:

```
version: 4
stk_version: 1.5_bench
kart: pidgin
difficulty: 3
mode: time-trial
track: black_forest
laps: 1
min_time: 73.286743
size: 1149
0.000000  -106.975 6.200 65.907  -0.002 0.934 0.008 0.356  0.000  0.000  ...
0.045833  -106.714 6.202 65.623  -0.001 0.934 0.005 0.356  5.528  0.000  ...
```

Each frame line contains: timestamp, position (x,y,z), rotation quaternion (x,y,z,w), speed, steering, wheel positions, and input flags.

## Naming Conventions

| Pattern | Description |
|---------|-------------|
| `benchmark_*.replay` | Performance testing replays |
| `challenge_*_[difficulty].replay` | Story mode challenge targets |
| `standard_[difficulty]_[track].replay` | Default ghost for each track/difficulty |
| `wr_[track]_[date]_*.replay` | World record replays |

## Key Files

- `benchmark_black_forest.replay` - GPU/CPU performance benchmark
- `standard_novice_*.replay` - Beginner-level ghost opponents
- `standard_supertux_*.replay` - Expert-level ghost opponents
- `wr_*.replay` - Community world record times

## How the Game Uses These Files

In ghost replay mode, the game loads a replay file and spawns a semi-transparent ghost kart that follows the recorded path. Players race against this ghost to compare performance. The game also records player replays which can be saved for later playback or shared.
