# Shaders

GLSL shaders for SuperTuxKart's rendering pipeline.

## Purpose

This directory contains the GPU shader programs that control how SuperTuxKart renders 3D graphics. These shaders handle materials, lighting, shadows, post-processing effects, and particle systems using OpenGL Shading Language (GLSL).

## File Formats

| Extension | Type | Description |
|-----------|------|-------------|
| `.frag` | Fragment Shader | Calculates pixel colors, textures, and lighting |
| `.vert` | Vertex Shader | Transforms vertex positions and passes data to fragment shaders |
| `.geom` | Geometry Shader | Generates or modifies geometry (e.g., normal visualization) |
| `.comp` | Compute Shader | GPU compute operations (blur, SSAO, hierarchical depth) |
| `.xml` | Shader Pipeline | Defines shader combinations and rendering passes |

## Key Shader Categories

| Prefix | Purpose |
|--------|---------|
| `sp_*` | SP (SuperTuxKart Pipeline) shaders for materials and rendering |
| `sps_*.xml` | Shader pipeline definitions linking vertex/fragment shaders |
| `gaussian*`, `bilateral*` | Blur and filtering effects |
| `ssao`, `IBL` | Screen-space ambient occlusion and image-based lighting |
| `sunlight*` | Sun and shadow rendering with PCF/PCSS filtering |
| `mlaa_*` | Morphological anti-aliasing |
| `bloom`, `dof`, `tonemap` | Post-processing effects |

## Subdirectories

- **ge_shaders/** - Graphics Engine (Vulkan/modern GL) shaders
- **irrlicht/** - Legacy OpenGL ES 2.0 shaders for mobile/fallback rendering
- **utils/** - Shared utility functions (BRDF, normals, color conversion)

## How It Works

Shaders use `#stk_include "utils/..."` to include shared code. The `sps_*.xml` files define complete shader pipelines, specifying vertex shaders, fragment shaders, texture bindings, and uniform variable assignments. The game selects appropriate shaders based on graphics settings and hardware capabilities.
