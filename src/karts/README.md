# Karts Module

*Last Updated: 2025-12-29*

Kart properties, models, physics, and behavior management.

## Purpose

This module contains everything related to karts including their physical properties, 3D models, physics simulation, animations, and characteristics. It manages kart movement, skidding, speed limits, and provides the base classes that controllers (AI or player) interact with to drive karts.

## Key Classes

| Class | File | Purpose |
|-------|------|---------|
| Kart | kart.hpp | Main kart implementation with full physics and effects |
| AbstractKart | abstract_kart.hpp | Abstract interface for kart operations |
| KartProperties | kart_properties.hpp | All configurable kart parameters (speed, mass, etc.) |
| KartPropertiesManager | kart_properties_manager.hpp | Loads and manages all available kart types |
| KartModel | kart_model.hpp | 3D model, animations, and wheel positions |
| Moveable | moveable.hpp | Base class for physics-enabled moving objects |
| Skidding | skidding.hpp | Handles skid/drift mechanics and bonuses |
| MaxSpeed | max_speed.hpp | Speed capping from powerups, terrain, nitro |
| AbstractCharacteristic | abstract_characteristic.hpp | Base for kart characteristic values |
| KartGFX | kart_gfx.hpp | Visual effects (nitro flames, skid sparks) |
| GhostKart | ghost_kart.hpp | Replay ghost kart for time trials |
| KartRewinder | kart_rewinder.hpp | Network state rewinding support |
| AbstractKartAnimation | abstract_kart_animation.hpp | Base for rescue, explosion, cannon animations |

## Dependencies

- **controller/**: Subdirectory with AI and player controller implementations
- **physics/**: Bullet physics integration via btKart
- **graphics/**: Kart rendering, shadows, particle effects
- **items/**: Powerup and attachment handling
- **tracks/**: Terrain information for kart behavior
