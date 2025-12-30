# Camera

*Last Updated: 2025-12-30*

In-game camera system with multiple view modes for racing, spectating, and debugging.

## Purpose

This module implements the camera system that follows karts during gameplay. It provides multiple camera types including the standard chase camera, first-person view, debug cameras for development, and cinematic end-race cameras. The system supports split-screen multiplayer with independent camera instances for each player.

## Key Classes

| Class | File | Purpose |
|-------|------|---------|
| Camera | camera.hpp | Base class managing camera instances, viewport setup, and mode switching |
| CameraNormal | camera_normal.hpp | Standard third-person chase camera with smooth kart following |
| CameraFPS | camera_fps.hpp | First-person camera with mouse look and optional kart attachment |
| CameraDebug | camera_debug.hpp | Development camera with fixed positions around the kart |
| CameraEnd | camera_end.hpp | Cinematic cameras activated at race finish (track-defined positions) |

## Camera Modes

The `Camera::Mode` enum defines available view modes:

| Mode | Description |
|------|-------------|
| CM_NORMAL | Standard behind-kart view |
| CM_CLOSEUP | Closer camera distance |
| CM_REVERSE | Backward-facing view |
| CM_FALLING | Activated when kart falls off track |
| CM_SPECTATOR_SOCCER | Follows the ball in soccer mode |
| CM_SPECTATOR_TOP_VIEW | Overhead view of the action |
| CM_SPECTATOR_TV | Track-designer placed cameras |

## Architecture

```
Camera (base)
    |
    +-- CameraNormal (chase camera)
    |       |
    |       +-- CameraDebug (debug positions)
    |       |
    |       +-- CameraEnd (race finish cinematics)
    |
    +-- CameraFPS (first-person view)
```

## Dependencies

- **karts/**: Attached to AbstractKart for position tracking
- **tracks/**: Reads end camera positions from scene.xml
- **Irrlicht**: Uses ICameraSceneNode for rendering
