# utf8

*Last Updated: 2025-12-30*

Third-party header-only UTF-8 library (UTF8-CPP) by Nemanja Trifunovic.

## Purpose

This module provides portable UTF-8 string handling utilities for C++. It enables conversion between UTF-8, UTF-16, and UTF-32 encodings, validation of UTF-8 sequences, and iteration over Unicode code points. Used throughout SuperTuxKart for internationalization and text processing.

## Key Classes/Functions

| Item | File | Purpose |
|------|------|---------|
| `utf8::append()` | checked.h | Encode a code point to UTF-8 with validation |
| `utf8::next()` | checked.h | Decode next code point, advancing iterator |
| `utf8::prior()` | checked.h | Decode previous code point, moving iterator back |
| `utf8::utf8to16()` | checked.h | Convert UTF-8 to UTF-16 |
| `utf8::utf16to8()` | checked.h | Convert UTF-16 to UTF-8 |
| `utf8::utf8to32()` | checked.h | Convert UTF-8 to UTF-32 |
| `utf8::utf32to8()` | checked.h | Convert UTF-32 to UTF-8 |
| `utf8::is_valid()` | core.h | Check if byte sequence is valid UTF-8 |
| `utf8::find_invalid()` | core.h | Find first invalid UTF-8 byte |
| `utf8::replace_invalid()` | checked.h | Replace invalid sequences with replacement char |
| `utf8::iterator` | checked.h | Bidirectional iterator over code points |
| `utf8::unchecked::*` | unchecked.h | Performance-optimized versions without validation |

## API Variants

- **Checked API** (`checked.h`): Throws exceptions on invalid input (`invalid_utf8`, `invalid_utf16`, `invalid_code_point`, `not_enough_room`)
- **Unchecked API** (`unchecked.h`): Assumes valid input for maximum performance

## License

Boost Software License (permissive, compatible with GPL)
