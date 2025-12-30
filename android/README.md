# Android Build Files

*Last Updated: 2025-12-29*

Build scripts and configuration for compiling SuperTuxKart for Android devices.

## Purpose

This directory contains everything needed to build SuperTuxKart APK packages for Android, including Gradle configuration, NDK build scripts, and asset generation tools.

## Key Files and Directories

| File/Directory | Description |
|----------------|-------------|
| `make.sh` | Main build script for compiling STK |
| `make_deps.sh` | Script to compile native dependencies |
| `generate_assets.sh` | Prepares game assets for APK packaging |
| `build.gradle` | Gradle build configuration |
| `Android.mk` | NDK makefile for native code |
| `AndroidManifest.xml` | Android application manifest |
| `README.ANDROID` | Detailed build instructions |
| `src/` | Java source files for Android integration |
| `gradle/` | Gradle wrapper files |
| `icon*.png` | Application icons (standard and adaptive) |

## Build Requirements

- Android SDK (API level 26+)
- Android NDK r23 (recommended)
- Linux build environment
- Dependencies: autoconf, automake, make, python, gradle, imagemagick, cmake, vorbis-tools, pngquant

## Quick Start

```bash
export SDK_PATH=/path/to/android/sdk
export NDK_PATH=/path/to/android/ndk
./generate_assets.sh
./make_deps.sh
./make.sh
```

## Environment Variables

- `COMPILE_ARCH`: Target architecture (all, armv7, aarch64, x86, x86_64)
- `BUILD_TYPE`: Build type (debug, release, beta)
- `PROJECT_VERSION`: Version string for the build
- `PROJECT_CODE`: Version code for manifest

See `README.ANDROID` for complete documentation.
