# IO Module

Generic utility classes for file I/O and path management.

## Purpose

This module provides file system abstraction, path discovery, and XML parsing utilities. It handles locating game assets across different platforms, managing user configuration directories, and providing a unified interface for reading game data files including XML configuration.

## Key Classes

| Class | File | Purpose |
|-------|------|---------|
| FileManager | file_manager.hpp | Central file/path manager for all asset types |
| XMLNode | xml_node.hpp | XML document parsing and node traversal |
| UTFWriter | utf_writer.hpp | UTF-8/UTF-16 text file writing utilities |
| AssetsAndroid | assets_android.hpp | Android-specific asset extraction |
| RichPresence | rich_presence.hpp | Discord/platform rich presence integration |

## Dependencies

- **graphics/**: Provides texture and model search paths
- **config/**: User configuration directory management
- **Irrlicht**: XML reader and file system interfaces

## Asset Types

FileManager handles paths for: challenges, GFX, grand prix, GUI icons/screens/dialogs, replays, shaders, skins, fonts, translations, libraries, models, music, SFX, textures, and scripts.

## Platform Support

- Discovers root directories on Windows, macOS, Linux, and Android
- Handles platform-specific user data locations
- Supports addon content directories
