# Audio Module

Manages all sound effects and music playback in SuperTuxKart.

## Purpose

This module provides a complete audio system using OpenAL for sound effects and OGG Vorbis for music. It runs audio processing in a separate thread, supports positional 3D audio for sound effects, and handles music transitions including fast/intense music variants during races.

## Key Classes

| Class | File | Purpose |
|-------|------|---------|
| `SFXManager` | sfx_manager.hpp | Singleton managing all sound effects with threaded command queue |
| `MusicManager` | music_manager.hpp | Controls background music playback, transitions, and volume |
| `SFXBuffer` | sfx_buffer.hpp | Stores audio data in OpenAL buffers (shared between SFX instances) |
| `SFXOpenAL` | sfx_openal.hpp | OpenAL implementation of sound effect playback |
| `SFXBase` | sfx_base.hpp | Abstract interface for sound effect sources |
| `MusicOgg` | music_ogg.hpp | OGG Vorbis music streaming implementation |
| `MusicInformation` | music_information.hpp | Metadata for music tracks (normal/fast variants, looping) |

## Dependencies

- **config/**: User settings for volume levels and audio enable/disable
- **io/**: Loading sound files from data directories
- **OpenAL**: External library for 3D audio playback
- **libogg/libvorbis**: External libraries for music decoding
