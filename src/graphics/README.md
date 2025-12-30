# Graphics Module

*Last Updated: 2025-12-29*

Core graphics engine providing a thin layer on top of Irrlicht with STK-specific features.

## Purpose

This module handles all rendering operations in SuperTuxKart including scene management, materials, shaders, particles, and visual effects. It provides mesh loading, texture management, post-processing effects, and camera systems while abstracting the underlying Irrlicht graphics library.

## Key Classes

| Class | File | Purpose |
|-------|------|---------|
| IrrDriver | irr_driver.hpp | Main graphics driver managing Irrlicht device, scene, and rendering |
| AbstractRenderer | abstract_renderer.hpp | Virtual base class for renderer implementations |
| ShaderBasedRenderer | shader_based_renderer.hpp | OpenGL shader-based rendering pipeline |
| Material | material.hpp | Stores material properties (textures, physics, rendering flags) |
| MaterialManager | material_manager.hpp | Loads and manages all game materials |
| ParticleEmitter | particle_emitter.hpp | Handles particle system rendering |
| PostProcessing | post_processing.hpp | Screen-space effects (bloom, motion blur, etc.) |
| Camera | camera/ | Camera system for player views |
| SkidMarks | skid_marks.hpp | Renders kart skid marks on track |
| SlipStream | slip_stream.hpp | Visual effect for drafting behind karts |

## Dependencies

- **io/**: Uses FileManager for asset loading
- **karts/**: Provides visual effects for karts (skid marks, particles)
- **items/**: Renders collectible items and projectiles
- **Irrlicht**: Core graphics library dependency
- **OpenGL**: Shader-based rendering backend
