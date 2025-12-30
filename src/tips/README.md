# tips

*Last Updated: 2025-12-29*

Loading screen tips management for SuperTuxKart.

## Purpose

This module manages gameplay tips displayed during loading screens. It reads tip content from `data/tips.xml` and provides localized tips organized by category (tip sets). Tips help players learn game mechanics, controls, and strategies while waiting for content to load.

## Key Classes

| Class | File | Purpose |
|-------|------|---------|
| TipsManager | tips_manager.hpp | Singleton that loads and serves tips by category |

## Usage

```cpp
// Get a random tip from a specific category
const irr::core::stringw& tip = TipsManager::get()->getTip("general");

// Check how many tips exist in a category
unsigned int count = TipsManager::get()->getTipCount("battle");
```

## Tip Sets

Tips are organized into sets identified by string IDs (e.g., "general", "battle", "soccer"). Each set contains multiple tips relevant to that game mode or topic. When requested, a random tip from the specified set is returned.

## Dependencies

- `io` - XML parsing for tips.xml
- `utils` - String handling utilities
