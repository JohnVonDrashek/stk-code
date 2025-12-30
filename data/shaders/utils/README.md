# Shader Utilities

Shared GLSL functions and includes for SuperTuxKart shaders.

## Purpose

This directory contains reusable shader code that is included by other shaders via `#stk_include` directives. These utilities provide common mathematical functions, BRDF implementations, color space conversions, and coordinate transformations used across multiple rendering passes.

## File Formats

| Extension | Type | Description |
|-----------|------|-------------|
| `.frag` | Fragment Include | Utility functions for fragment shaders |
| `.vert` | Vertex Include | Utility functions for vertex shaders |

## Utility Files

| File | Purpose |
|------|---------|
| `DiffuseBRDF.frag` | Lambert diffuse BRDF model |
| `SpecularBRDF.frag` | Blinn-Phong specular with Fresnel approximation |
| `DiffuseIBL.frag` | Diffuse image-based lighting lookup |
| `SpecularIBL.frag` | Specular IBL with roughness-based LOD |
| `encode_normal.frag` | Encodes world normals to G-buffer format |
| `decodeNormal.frag` | Decodes normals from G-buffer |
| `rgb_conversion.frag` | RGB to HSV and HSV to RGB color conversion |
| `getPosFromUVDepth.frag` | Reconstructs world position from UV and depth |
| `getCIEXYZ.frag` / `getRGBfromCIEXxy.frag` | CIE color space conversions |
| `get_world_location.vert` | Transforms vertices using quaternion rotation and scale |
| `sp_texture_sampling.frag` | Texture sampling with triplanar blending support |
| `screen_space_reflection.frag` | SSR ray marching utilities |
| `SunMRP.frag` | Sun most representative point for area lighting |
| `displace_utils.frag` | Displacement/water distortion helpers |

## Usage

Include these utilities in shaders with:
```glsl
#stk_include "utils/rgb_conversion.frag"
#stk_include "utils/encode_normal.frag"
```

The STK shader preprocessor resolves these paths relative to the shader directory.
