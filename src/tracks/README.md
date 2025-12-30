# tracks

Track data, drivelines, checklines, and track object management.

## Purpose

This module handles all track-related functionality including loading track geometry, managing driveline graphs for AI navigation, handling checkpoint/lap detection, and managing dynamic track objects. It supports racing tracks, battle arenas, and soccer fields with appropriate graph structures for each.

## Key Classes

| Class | File | Purpose |
|-------|------|---------|
| Track | track.hpp | Main track class - loads and manages all track data |
| TrackManager | track_manager.hpp | Singleton managing all available tracks |
| TrackObject | track_object.hpp | Dynamic objects placed on tracks |
| TrackObjectManager | track_object_manager.hpp | Manages all track objects during gameplay |
| Graph | graph.hpp | Base class for quad-based navigation graphs |
| DriveGraph | drive_graph.hpp | Driveline graph for racing tracks |
| ArenaGraph | arena_graph.hpp | Navigation mesh for battle arenas |
| CheckStructure | check_structure.hpp | Base class for checkpoint detection |
| CheckManager | check_manager.hpp | Manages all checkpoints on a track |
| CheckLine | check_line.hpp | Line-based checkpoint for lap counting |
| CheckCannon | check_cannon.hpp | Checkpoint that launches karts |

## Graph System

- `DriveGraph`/`DriveNode` - Quad-based path for racing tracks (used by AI)
- `ArenaGraph`/`ArenaNode` - Navmesh for arena-style maps
- Both support 2D and 3D variants for different track geometries

## Dependencies

- `graphics` - Rendering and scene management
- `physics` - Collision meshes via Bullet
- `items` - Item placement on tracks
- `utils` - Vec3, logging, and other utilities
- `io` - XML parsing for track configuration
