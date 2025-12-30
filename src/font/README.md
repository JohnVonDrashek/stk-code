# Font Module

*Last Updated: 2025-12-29*

Manages font loading, text shaping, and character rendering.

## Purpose

This module handles all text rendering in SuperTuxKart using FreeType for font loading and HarfBuzz for complex text shaping. It supports multiple font faces (regular, bold, digit), lazy-loads glyphs into texture atlases, handles Unicode including color emoji, and provides proper line breaking rules for internationalization.

## Key Classes

| Class | File | Purpose |
|-------|------|---------|
| `FontManager` | font_manager.hpp | Singleton that loads TTF files and manages all font instances |
| `FontWithFace` | font_with_face.hpp | Abstract base converting vector fonts to bitmaps for rendering |
| `RegularFace` | regular_face.hpp | Standard text font implementation |
| `BoldFace` | bold_face.hpp | Bold/outline text font with stroke effect |
| `DigitFace` | digit_face.hpp | Specialized font for race timer digits |
| `FaceTTF` | face_ttf.hpp | Container for multiple TTF files with fallback support |
| `FontSettings` | font_settings.hpp | Rendering options (scale, shadow, outline color) |
| `FontDrawer` | font_drawer.hpp | Low-level glyph drawing utilities |

## Dependencies

- **config/**: Font size preferences and TTF file paths from stk_config
- **FreeType**: External library for font loading and rasterization
- **HarfBuzz**: External library for complex text shaping (Arabic, Thai, etc.)
- **guiengine/**: GUI system uses fonts for all text display
