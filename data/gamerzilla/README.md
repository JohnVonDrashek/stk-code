# Gamerzilla

*Last Updated: 2025-12-29*

Achievement integration assets for the Gamerzilla open-source achievement system.

## Purpose

Gamerzilla is an open gaming achievement platform that allows games to track and display achievements across a unified system. This directory contains the image assets used when SuperTuxKart registers its achievements with a local or remote Gamerzilla server.

## Contents

| File | Description |
|------|-------------|
| `supertuxkart.png` | Main game icon displayed in Gamerzilla clients |
| `achievement0.png` | Icon for locked/incomplete achievements |
| `achievement1.png` | Icon for unlocked/completed achievements |

## How the Game Uses These Files

When compiled with `GAMERZILLA` support enabled, SuperTuxKart:

1. Initializes Gamerzilla with a local cache directory (`~/.config/supertuxkart/gamerzilla/`)
2. Registers the game using `supertuxkart.png` as the game icon
3. Registers each in-game achievement with `achievement0.png` (locked) and `achievement1.png` (unlocked) states
4. Syncs achievement progress with the configured Gamerzilla server

The actual achievement definitions are in the game's code (`src/achievements/`), not in this data directory. These PNG files are purely visual assets for the Gamerzilla UI.

## More Information

- Gamerzilla project: https://github.com/dulsi/gamerzilla
- Achievement logic: `src/achievements/web_achievements_status.cpp`
