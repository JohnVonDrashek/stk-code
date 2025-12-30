# Documentation

*Last Updated: 2025-12-29*

Technical documentation for SuperTuxKart developers and content creators.

## Purpose

This directory contains developer-focused documentation covering the rendering pipeline, network protocols, and asset creation guidelines.

## Files

| File | Description |
|------|-------------|
| `supertuxkart.6` | Unix man page for the game |
| `pipeline_overview.txt` | Overview of the rendering pipeline passes |
| `graphics_xml.txt` | XML attributes for graphics effects (glow, bloom, fog, shadows, etc.) |
| `graphics_views.txt` | Camera and viewport documentation |
| `physics_order` | Physics simulation execution order |
| `protocols.xls` | Network protocol specifications (Excel format) |
| `assets_version` | Current assets version information |

## Rendering Pipeline

The rendering pipeline consists of four main phases:

1. **Init**: Glow initialization, 3D skybox rendering
2. **Main**: Solids, glows, shadows, lights, occlusion queries
3. **Transparent**: Transparent objects, displacement effects, post-processing
4. **GUI**: User interface overlay

## Graphics XML Reference

Content creators can use XML attributes to control visual effects:

- `forcedbloom="Y"` - Force object into bloom pass
- `glow="R G B"` - Add colored glow to objects
- `displacing="Y"` - Enable refraction/reflection effects
- Track-level: `bloom`, `lens-flare`, `god-rays`, `shadows`, `clouds`

See `graphics_xml.txt` for complete documentation.
