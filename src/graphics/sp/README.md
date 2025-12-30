# SP (Shader Pipeline)

*Last Updated: 2025-12-30*

Modern OpenGL shader-based rendering subsystem with instanced drawing and GPU skinning.

## Purpose

The SP module provides a high-performance rendering pipeline using OpenGL shaders, instanced draw calls, and GPU-based mesh skinning. It replaces Irrlicht's fixed-function rendering with a modern deferred approach that supports advanced effects like shadows, glow, and efficient batching of similar objects.

## Key Classes

| Class | File | Purpose |
|-------|------|---------|
| SPShader | sp_shader.hpp | Shader program wrapper with uniform management and render passes |
| SPShaderManager | sp_shader_manager.hpp | Singleton that loads, caches, and manages all shader programs |
| SPMesh | sp_mesh.hpp | Skinned mesh container implementing ISkinnedMesh interface |
| SPMeshBuffer | sp_mesh_buffer.hpp | GPU buffer for vertices, indices, and instanced draw data |
| SPMeshNode | sp_mesh_node.hpp | Scene node for SP meshes with animation and glow support |
| SPTexture | sp_texture.hpp | Texture wrapper with threaded loading and mipmap generation |
| SPTextureManager | sp_texture_manager.hpp | Thread-safe texture caching and loading manager |
| SPDynamicDrawCall | sp_dynamic_draw_call.hpp | Runtime-generated geometry (particles, billboards) |
| SPUniformAssigner | sp_uniform_assigner.hpp | Type-safe shader uniform value setter |
| SPPerObjectUniform | sp_per_object_uniform.hpp | Per-object uniform callback system |
| SPInstancedData | sp_instanced_data.hpp | Packed transform data for GPU instancing (44 bytes) |

## Core Functions (sp_base.hpp)

| Function | Purpose |
|----------|---------|
| `SP::init()` | Initialize the shader pipeline |
| `SP::destroy()` | Clean up all SP resources |
| `SP::prepareDrawCalls()` | Collect and batch visible objects |
| `SP::draw()` | Execute draw calls for a render pass |
| `SP::drawGlow()` | Render glow effects |
| `SP::addObject()` | Register a mesh node for rendering |

## Render Passes

| Pass | Description |
|------|-------------|
| RP_1ST | Main color pass with lighting |
| RP_SHADOW | Shadow map generation (4 cascades) |
| RP_RESERVED | Reserved for future use |

## Draw Call Types

| Type | Description |
|------|-------------|
| DCT_NORMAL | Standard opaque geometry |
| DCT_SHADOW1-4 | Shadow cascade passes |
| DCT_TRANSPARENT | Alpha-blended objects |

## Dependencies

- **graphics/**: Integrates with ShaderBasedRenderer
- **io/**: Shader file loading via FileManager
- **Irrlicht**: Scene node base classes, image loading
- **OpenGL**: Direct GL calls for rendering
