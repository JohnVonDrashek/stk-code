# utils

*Last Updated: 2025-12-30*

Shared GLSL utility modules for the graphics engine (GE) shader pipeline.

## Purpose

This directory contains reusable GLSL include files that provide common functionality for the Vulkan/OpenGL ES rendering pipeline. These utilities implement physically-based rendering (PBR) calculations, camera transformations, lighting systems, and mesh data handling used across multiple shaders.

## Contents

| File | Purpose |
|------|---------|
| `camera.glsl` | Camera uniform buffer with view/projection matrices, viewport, and screen dimensions |
| `constants_utils.glsl` | Specialization constants (IBL, SSR, deferred) and HDR tonemapping color conversion |
| `environment_map.glsl` | Cubemap sampling utilities, Hammersley sequence, and UV-to-direction conversion for IBL |
| `get_vertex_color.glsl` | Unpacks ARGB vertex colors from packed uint format to vec4 |
| `global_light_data.glsl` | Light data structures and uniform buffer for sun, ambient, fog, and up to 32 point/spot lights |
| `handle_pbr.glsl` | Main PBR entry points combining diffuse/specular IBL, sun lighting, and dynamic lights |
| `pbr_light.glsl` | PBR BRDF calculations for direct lighting, sun+ambient+emissive, and light accumulation loop |
| `pbr_utils.glsl` | Core PBR functions: GGX distribution, Smith visibility, Fresnel, Burley diffuse, environment BRDF |
| `sample_mesh_texture.glsl` | Texture sampling helpers supporting both bindless and traditional texture binding modes |
| `spm_data.glsl` | SPM (SuperTuxKart Particle Model) object/skinning buffers and material ID storage |
| `spm_layout.vert` | Standard vertex shader input/output layout for SPM meshes (position, normal, UV, tangent, joints) |
| `sun_direction.glsl` | Most Representative Point (MRP) area lighting for sun based on Frostbite PBR paper |
| `unproject_position.glsl` | Screen-space to view-space position reconstruction from fragment/UV coordinates |
