# CMake Modules

Custom CMake modules for finding dependencies and cross-compilation toolchains.

## Purpose

This directory contains CMake find modules for locating third-party libraries and toolchain files for cross-compiling SuperTuxKart to various platforms.

## Key Files

| File | Description |
|------|-------------|
| **Find Modules** | |
| `FindAngelscript.cmake` | Locates AngelScript scripting library |
| `FindEGL.cmake` | Locates EGL graphics library |
| `FindFreetype.cmake` | Locates FreeType font rendering library |
| `FindLibbfd.cmake` | Locates GNU BFD library for debugging |
| `FindOggVorbis.cmake` | Locates Ogg Vorbis audio libraries |
| `FindWayland.cmake` | Locates Wayland display protocol libraries |
| `FindWiiUse.cmake` | Locates WiiUse library for Wiimote support |
| **Toolchain Files** | |
| `Toolchain-android.cmake` | Cross-compile for Android |
| `Toolchain-ios-xcode.cmake` | Cross-compile for iOS using Xcode |
| `Toolchain-mingw.cmake` | Cross-compile for Windows (32-bit) |
| `Toolchain-mingw-64bit.cmake` | Cross-compile for Windows (64-bit) |
| `Toolchain-llvm-mingw.cmake` | Cross-compile using LLVM MinGW |
| `Toolchain-cctools.cmake` | Cross-compile using cctools |
| **Build Configuration** | |
| `BuildTypeSTKRelease.cmake` | Defines STKRelease build type with -O2 optimization |
| `SourceGroupFunctions.cmake` | Helper functions for organizing source files |
| `XcodeHelper.cmake` | Helper functions for Xcode builds |

## Usage

CMake automatically searches this directory when configured. For cross-compilation:

```bash
cmake .. -DCMAKE_TOOLCHAIN_FILE=../cmake/Toolchain-android.cmake
```
