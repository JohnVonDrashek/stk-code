# Nintendo Switch Port

Build scripts and resources for the Nintendo Switch homebrew port of SuperTuxKart.

## Purpose

This directory contains the tooling needed to compile SuperTuxKart as a Nintendo Switch homebrew application (.nro format). The port uses devkitPro toolchain and produces a distributable ZIP package.

## Files

| File | Description |
|------|-------------|
| `make.sh` | Main build script - compiles STK and creates package |
| `package.sh` | Creates the .nro executable from compiled binaries |
| `decode.js` | JavaScript utility for data decoding |
| `pkgbuild-scripts/` | Package building helper scripts |
| `supertuxkart_256.jpg` | Icon for Switch home menu |

## Requirements

- [devkitPro](https://devkitpro.org/) toolchain installed
- `DEVKITPRO` environment variable set
- Switch portlibs with aarch64 cmake toolchain

## Building

```bash
# Ensure devkitPro is installed and configured
export DEVKITPRO=/opt/devkitpro

# Run the build script
./make.sh
```

## Output

The build produces a ZIP file at:
```
cmake_build/bin/SuperTuxKart-${PROJECT_VERSION}-switch.zip
```

This ZIP contains:
- `switch/stk.nro` - The executable
- `stk-data/` - Game data files

Copy the contents to your Switch SD card to install.
