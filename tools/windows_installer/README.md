# Windows Installer

*Last Updated: 2025-12-30*

NSIS installer scripts and resources for Windows distribution.

## Purpose

This directory contains NSIS (Nullsoft Scriptable Install System) scripts and graphical resources for building Windows installers. These scripts create professional installers with Start Menu integration, Add/Remove Programs entries, and proper uninstall support.

## Contents

| File | Purpose |
|------|---------|
| `supertuxkart-64bit-mingw.nsi` | NSIS script for 64-bit MinGW builds |
| `supertuxkart-mingw.nsi` | NSIS script for 32-bit MinGW builds |
| `supertuxkart-github-actions.nsi` | NSIS script for CI/CD builds (multi-arch) |
| `icon.ico` | Main application icon (270KB) |
| `install.ico` | Installer wizard icon |
| `uninstall.ico` | Uninstaller wizard icon |
| `stk_installer.bmp` | Welcome page banner (164x314) |
| `logo_slim.bmp` | Header logo for installer pages |
| `icon_rc.template` | CMake template for Windows resource file |

## Usage

### Prerequisites

1. Install [NSIS](https://nsis.sourceforge.io/)
2. Install the [ShellLink plugin](http://nsis.sourceforge.net/ShellLink_plug-in)
3. Build SuperTuxKart with MinGW
4. Have `stk-assets` cloned as a sibling directory

### Building an Installer

For 64-bit builds:
```cmd
cd tools\windows_installer
makensis supertuxkart-64bit-mingw.nsi
```

For 32-bit builds:
```cmd
cd tools\windows_installer
makensis supertuxkart-mingw.nsi
```

The installer will be created as `SuperTuxKart X.Y.Z installer-64bit.exe` (or 32bit).

### Installer Features

- Modern UI with custom graphics
- License agreement (GPL)
- Custom installation directory
- Start Menu shortcuts
- Proper Add/Remove Programs registry entries
- Clean uninstaller
