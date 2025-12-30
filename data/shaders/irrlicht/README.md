# Irrlicht Shaders

OpenGL ES 2.0 shaders for legacy and mobile rendering.

## Purpose

This directory contains shaders for the Irrlicht-based legacy renderer, targeting OpenGL ES 2.0. These shaders provide a fallback rendering path for older hardware, mobile devices, and platforms without Vulkan support. They implement a fixed-function-style pipeline with programmable shaders.

## File Formats

| Extension | Type | Description |
|-----------|------|-------------|
| `.fsh` | Fragment Shader | GLES 2.0 fragment/pixel shader |
| `.vsh` | Vertex Shader | GLES 2.0 vertex shader |

## Shader Files

| File | Purpose |
|------|---------|
| `COGLES2FixedPipeline.fsh/vsh` | Multi-purpose material shader supporting 12+ material types |
| `COGLES2NormalMap.fsh/vsh` | Normal mapping with per-pixel lighting |
| `COGLES2ParallaxMap.fsh/vsh` | Parallax/offset mapping for depth effects |
| `COGLES2Renderer2D.fsh/vsh` | 2D UI and sprite rendering |

## Material Types

The `COGLES2FixedPipeline` shader handles multiple material types via uniform switching:
- Solid, Solid2Layer, LightMap, DetailMap
- SphereMap, Reflection2Layer
- TransparentAlphaChannel, TransparentVertexAlpha
- StkGrass, StkBlend (SuperTuxKart-specific materials)

## How It Works

These shaders use GLES 2.0 syntax with `varying` instead of `in/out`, `gl_FragColor` for output, and `precision mediump float` declarations. The fixed pipeline shader includes inline utility functions (like HSV conversion) since GLES 2.0 lacks the `#include` preprocessor capability.
