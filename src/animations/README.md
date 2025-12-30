# Animations Module

*Last Updated: 2025-12-29*

Manages interpolation-based animations for position, rotation, and scale.

## Purpose

This module provides animation support using IPO (Interpolation Object) curves, originally from Blender's animation system. It handles cyclic and one-time animations for track objects, supporting bezier curves, linear interpolation, and various extend modes for seamless looping.

## Key Classes

| Class | File | Purpose |
|-------|------|---------|
| `AnimationBase` | animation_base.hpp | Base class for all animations, manages IPO curves and playback |
| `Ipo` | ipo.hpp | Represents a single Blender IPO curve with interpolation and timing |
| `ThreeDAnimation` | three_d_animation.hpp | Applies animations to 3D track objects |

## Dependencies

- **io/**: XML parsing for animation data from track files
- **utils/**: Vec3 for position/rotation/scale transformations
- **tracks/**: Track objects that use animations
