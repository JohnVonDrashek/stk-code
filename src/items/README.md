# Items Module

*Last Updated: 2025-12-29*

Collectible items, powerups, and projectile management for SuperTuxKart.

## Purpose

This module manages all track items (nitro, bananas, gift boxes), powerups that karts can use, and flyable projectiles. It handles item spawning, collection, powerup selection based on race position, projectile physics, and network synchronization of item states.

## Key Classes

| Class | File | Purpose |
|-------|------|---------|
| ItemManager | item_manager.hpp | Manages all track items, handles collection and respawning |
| Item | item.hpp | Individual collectible item on track |
| PowerupManager | powerup_manager.hpp | Loads powerup data, manages weighted random selection |
| Powerup | powerup.hpp | Active powerup held by a kart |
| Flyable | flyable.hpp | Base class for all projectiles (physics-enabled) |
| ProjectileManager | projectile_manager.hpp | Tracks all active projectiles in the world |
| Attachment | attachment.hpp | Items attached to karts (parachute, bomb, anchor) |
| AttachmentManager | attachment_manager.hpp | Loads and manages attachment meshes |
| NetworkItemManager | network_item_manager.hpp | Synchronizes items in multiplayer |
| Bowling | bowling.hpp | Bowling ball projectile |
| Cake | cake.hpp | Cake projectile (homing) |
| Plunger | plunger.hpp | Plunger projectile with rubber band |
| RubberBall | rubber_ball.hpp | Homing "swatter" ball projectile |
| Swatter | swatter.hpp | Swatter attachment for hitting nearby karts |

## Dependencies

- **karts/**: Items interact with karts for collection and effects
- **graphics/**: Item mesh and particle rendering
- **physics/**: Projectile collision detection
- **network/**: Multiplayer item synchronization
