# Addons Module

Handles downloadable add-on content including tracks, karts, and arenas.

## Purpose

This module manages the add-on system that allows players to download and install community-created content. It maintains a list of available and installed add-ons, handles downloading from the add-on server, and manages news/announcements displayed in the game.

## Key Classes

| Class | File | Purpose |
|-------|------|---------|
| `AddonsManager` | addons_manager.hpp | Central manager for all add-on operations (install, uninstall, list) |
| `Addon` | addon.hpp | Represents a single add-on with metadata (name, type, version, status) |
| `NewsManager` | news_manager.hpp | Fetches and displays news/announcements from the server |
| `extractZip` | zip.hpp | Utility functions for extracting downloaded add-on archives |

## Dependencies

- **io/**: XML parsing and file operations
- **online/**: HTTP requests for downloading add-ons and fetching news
- **utils/**: Thread synchronization for background downloads
