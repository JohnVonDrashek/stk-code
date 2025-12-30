# Physics Module

Bullet physics integration for kart dynamics and world collision.

## Purpose

This module wraps the Bullet physics library to provide realistic kart physics simulation. It implements a custom raycast vehicle model optimized for arcade-style kart racing, handles collision detection between karts and track objects, and provides physics debugging visualization.

## Key Classes

| Class | File | Purpose |
|-------|------|---------|
| `Physics` | physics.hpp | Main physics world manager handling collision detection and updates |
| `btKart` | btKart.hpp | Custom Bullet vehicle implementing kart-specific physics (suspension, friction, impulses) |
| `btKartRaycast` | btKartRaycast.hpp | Raycaster for wheel-ground contact detection |
| `PhysicalObject` | physical_object.hpp | Physics representation for track objects (static/dynamic) |
| `TriangleMesh` | triangle_mesh.hpp | Collision mesh for track geometry |
| `STKDynamicsWorld` | stk_dynamics_world.hpp | Extended Bullet dynamics world with STK-specific features |
| `IrrDebugDrawer` | irr_debug_drawer.hpp | Irrlicht-based debug visualization for physics shapes |
| `UserPointer` | user_pointer.hpp | Type-safe pointer for identifying collision object types |

## Dependencies

- **karts/** - Kart properties and state
- **tracks/** - Track geometry and physical objects
- **items/** - Physics for collectibles and projectiles
- **Bullet Physics** - Physics simulation library (external dependency)
