# Bundled Libraries

Third-party libraries bundled with SuperTuxKart for consistent builds across platforms.

## Purpose

This directory contains source code for external libraries that are compiled alongside SuperTuxKart. Bundling ensures version compatibility and simplifies cross-platform builds. Additional dependencies may be required from the `dependencies` repository for Android/iOS builds.

## Libraries

| Library | Description |
|---------|-------------|
| `angelscript/` | AngelScript - Scripting language for game logic |
| `bullet/` | Bullet Physics - 3D physics simulation engine |
| `enet/` | ENet - Reliable UDP networking library |
| `irrlicht/` | Irrlicht - 3D graphics engine (STK fork) |
| `libsquish/` | libSquish - DXT texture compression |
| `mcpp/` | MCPP - Portable C preprocessor |
| `mojoal/` | MojoAL - OpenAL implementation |
| `sheenbidi/` | SheenBidi - Unicode bidirectional algorithm |
| `tinygettext/` | TinyGettext - Lightweight gettext implementation |
| `wiiuse/` | WiiUse - Wiimote input library |
| `dnsc/` | DNS client utilities |
| `graphics_engine/` | STK graphics engine components |
| `graphics_utils/` | Graphics utility functions |
| `simd_wrapper/` | SIMD abstraction layer |

## Notes

- The Irrlicht version here is a customized fork maintained by the STK team
- Some libraries (curl, freetype, openal, etc.) for mobile builds are in a separate `dependencies` package
- See `irrlicht/README.stk` for STK-specific modifications

## Building

These libraries are built automatically by CMake as part of the main build process.
