# AI Test

*Last Updated: 2025-12-30*

Automated AI kart testing scripts for performance benchmarking.

## Purpose

This directory contains scripts for automated AI testing and profiling of kart performance across all game tracks. The test runs multiple AI-controlled karts through each track to measure performance metrics and verify AI behavior.

## Contents

| File | Purpose |
|------|---------|
| `test_track.sh` | Runs 15 AI karts through all tracks with profiling enabled |

## Usage

Run the script with the path to the SuperTuxKart executable:

```bash
./test_track.sh /path/to/supertuxkart
```

The script:
- Tests all standard tracks (abyss, candela_city, cocoa_temple, etc.)
- Runs 15 Nolok AI karts per track at highest difficulty
- Profiles 10 laps per track in headless mode (no graphics)
- Outputs results to `stdout.<trackname>` files for analysis
