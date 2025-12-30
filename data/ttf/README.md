# TTF Fonts

*Last Updated: 2025-12-29*

TrueType and OpenType font files for SuperTuxKart text rendering.

## Purpose

This directory contains the font files used to render all text in SuperTuxKart, including menus, in-game HUD, chat messages, and player names. The fonts support multiple scripts and languages to enable worldwide localization.

## File Formats

| Extension | Format | Description |
|-----------|--------|-------------|
| `.ttf` | TrueType | Standard font format |
| `.otf` | OpenType | Extended font format with advanced features |

## Font Files

| Font | Script/Purpose |
|------|----------------|
| `Cantarell-Regular.otf` | Primary Latin UI font |
| `SigmarOne.otf` | Display/title font |
| `wqy-microhei.ttf` | CJK (Chinese, Japanese, Korean) characters |
| `NotoColorEmoji.ttf` | Color emoji support |
| `NotoNaskhArabicUI-Regular.ttf` | Arabic script |
| `NotoSansBengali-Regular.ttf` | Bengali script |
| `NotoSansDevanagari-Regular.ttf` | Devanagari (Hindi, Sanskrit) |
| `NotoSansGeorgian-Regular.ttf` | Georgian script |
| `NotoSansHebrew-Regular.ttf` | Hebrew script |
| `NotoSansMalayalam-Regular.ttf` | Malayalam script |
| `NotoSansThai-Regular.ttf` | Thai script |

## Font Fallback System

SuperTuxKart uses a font fallback chain: when a character is not found in the primary font, subsequent fonts in the list are checked. This allows mixing Latin UI text with localized content in various scripts. The Noto font family provides comprehensive Unicode coverage.

## Licensing

See `LICENSE` and `SIL Open Font License.txt` for font licensing terms. Most fonts are distributed under the SIL Open Font License, permitting free use and redistribution.

## Custom Fonts in Skins

Skins can specify custom fonts via the `<advanced>` tag in `stkskin.xml`:
```xml
<advanced normal_ttf="CustomFont.ttf" digit_ttf="Numbers.ttf"/>
```
