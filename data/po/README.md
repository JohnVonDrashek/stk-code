# Localization Files

Translation files for SuperTuxKart's internationalization (i18n) system.

## Purpose

This directory contains GNU gettext translation files that enable SuperTuxKart to display text in over 60 languages. Translations cover all user-facing strings including menus, dialogs, achievement descriptions, and in-game messages.

## File Format

The localization system uses standard gettext format:

- **`supertuxkart.pot`** - Template file containing all translatable strings extracted from source code and data files
- **`*.po`** - Language-specific translation files (e.g., `es.po` for Spanish, `zh_CN.po` for Simplified Chinese)

PO file structure:
```po
#. I18N: In the main screen
msgid "Quit"
msgstr "Salir"

#. I18N: ./data/achievements.xml
msgid "Play every official track at least once."
msgstr "Juega a todos los circuitos oficiales al menos una vez."
```

## Naming Conventions

Files follow ISO 639 language codes:
- `de.po` - German
- `fr.po` - French
- `pt_BR.po` - Brazilian Portuguese (with regional variant)
- `zh_TW.po` - Traditional Chinese (Taiwan)

## Utility Scripts

| Script | Purpose |
|--------|---------|
| `update_pot.sh` | Regenerate template from source files |
| `extract_strings_from_XML.py` | Extract translatable strings from data XML files |
| `update_po_authors.py` | Update translator credits |
| `update_translation.py` | Sync PO files with latest template |

## How the Game Uses These Files

At build time, PO files are compiled to binary MO format. At runtime, the game loads the appropriate MO file based on system locale settings. The `I18N` attribute in `.stkgui` files and `_()` macro in C++ code mark strings for translation lookup.
