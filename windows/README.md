# Windows Build Files

Windows-specific resources for building and packaging SuperTuxKart.

## Purpose

This directory contains Windows manifest files and resource definitions used when compiling SuperTuxKart for Windows platforms.

## Files

| File | Description |
|------|-------------|
| `dpi_aware.manifest` | Application manifest for DPI awareness |
| `windows_config.rc` | Windows resource configuration |

## DPI Awareness

The `dpi_aware.manifest` configures the application for proper high-DPI display support:

- **Windows 10+**: Uses Per-Monitor V2 DPI awareness
- **Windows 8.1**: Falls back to Per-Monitor V1
- **Windows 7/8**: Uses basic DPI awareness

This ensures the game renders correctly on high-resolution displays without blurriness.

## Windows Installer

For NSIS installer scripts and resources, see:
```
tools/windows_installer/
```

That directory contains:
- NSIS installer scripts (`.nsi` files)
- Installer icons and graphics
- Icon resource templates

## Building on Windows

SuperTuxKart can be built on Windows using:
- Visual Studio (recommended)
- MinGW-w64 (cross-compilation supported)

See the main project documentation for complete build instructions.
