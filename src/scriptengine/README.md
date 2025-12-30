# Script Engine Module

*Last Updated: 2025-12-29*

AngelScript integration for track and cutscene scripting.

## Purpose

This module embeds the AngelScript scripting language to enable custom track behaviors, cutscenes, and challenge logic. It exposes game APIs for manipulating karts, track objects, GUI elements, and physics. Scripts are loaded per-track and can register timed callbacks for delayed execution.

## Key Classes

| Class | File | Purpose |
|-------|------|---------|
| `ScriptEngine` | script_engine.hpp | Singleton managing AngelScript engine, script compilation, and execution |
| `PropertyAnimator` | property_animator.hpp | Animates object properties over time via script control |

## Script Bindings

| File | Exposed API |
|------|-------------|
| `script_track.cpp` | Track objects, animations, triggers, particle emitters |
| `script_kart.cpp` | Kart teleportation, squashing, speed manipulation |
| `script_gui.cpp` | On-screen text, animations, GUI manipulation |
| `script_challenges.cpp` | Challenge completion, unlockables |
| `script_audio.cpp` | Sound and music playback |
| `script_physics.cpp` | Physics impulses and object manipulation |
| `script_utils.cpp` | Logging, random numbers, time functions |

## Support Files

- `scriptvec3.cpp` - Vec3 type binding for 3D vectors
- `scriptarray.cpp` - Array container binding
- `scriptstdstring.cpp` - String type binding

## Dependencies

- **tracks/** - TrackObject and TrackObjectPresentation access
- **karts/** - Kart state and control
- **guiengine/** - GUI overlay system
- **AngelScript** - Scripting language library (external dependency)
