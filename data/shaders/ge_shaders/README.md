# GE Shaders (Graphics Engine)

*Last Updated: 2025-12-29*

Modern shaders for SuperTuxKart's Vulkan-based Graphics Engine renderer.

## Purpose

This directory contains shaders optimized for the modern Graphics Engine (GE) renderer, which supports Vulkan and modern OpenGL. These shaders use newer GLSL features like `#include` directives, explicit layout bindings, and Physically Based Rendering (PBR) when enabled.

## File Formats

| Extension | Type | Description |
|-----------|------|-------------|
| `.frag` | Fragment Shader | Per-pixel color and material calculations |
| `.vert` | Vertex Shader | Vertex transformation and attribute passing |
| `.comp` | Compute Shader | GPU compute for irradiance and specular prefiltering |
| `.xml` | Settings | Shader configuration and feature toggles |

## Key Files

| File | Purpose |
|------|---------|
| `solid.frag` | Standard opaque material rendering with optional PBR |
| `spm.vert` | SPM (SuperTuxKart Polygon Mesh) vertex shader |
| `spm_skinning.vert` | Animated/skinned mesh vertex shader |
| `normalmap.frag` | Normal-mapped material with tangent space lighting |
| `deferred_pbr.frag` | Deferred shading PBR lighting pass |
| `diffuse_irradiance.comp` | Computes diffuse IBL from environment maps |
| `specular_prefilter.comp` | Prefilters specular IBL for roughness levels |

## Architecture

GE shaders use a modular include system via `utils/` subdirectory. The `PBR_ENABLED` preprocessor flag toggles between simple and physically-based rendering paths. Shaders access material data through descriptor sets and storage buffers, enabling efficient instanced rendering.

## Subdirectory

- **utils/** - Shared GLSL includes for camera matrices, PBR calculations, mesh texture sampling, and lighting utilities
