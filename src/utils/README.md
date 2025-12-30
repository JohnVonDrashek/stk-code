# utils

Common utility classes and functions used throughout SuperTuxKart.

## Purpose

This module provides foundational utilities including string manipulation, logging, math helpers, memory management patterns, and platform abstractions. These utilities are used extensively by all other STK modules to avoid code duplication and ensure consistent behavior.

## Key Classes

| Class/Namespace | File | Purpose |
|-----------------|------|---------|
| StringUtils | string_utils.hpp | String conversion, formatting, and i18n helpers |
| Log | log.hpp | Logging system with levels (debug, info, warn, error, fatal) |
| Vec3 | vec3.hpp | 3D vector wrapper around Bullet's btVector3 |
| Singleton | singleton.hpp | Template for singleton pattern implementation |
| Synchronised | synchronised.hpp | Thread-safe wrapper using mutex |
| PtrVector | ptr_vector.hpp | Vector that manages pointer ownership |
| RandomGenerator | random_generator.hpp | Deterministic random number generation |
| Profiler | profiler.hpp | Performance profiling and timing |
| Translation | translation.hpp | Internationalization (i18n) support |
| Time | time.hpp | Time and date utilities |

## Additional Utilities

| File | Purpose |
|------|---------|
| aligned_array.hpp | Memory-aligned array for SIMD/physics |
| command_line.hpp | Command line argument parsing |
| crash_reporting.hpp | Crash dump and reporting utilities |
| interpolation_array.hpp | Value interpolation over time |
| leak_check.hpp | Memory leak detection in debug builds |
| no_copy.hpp | Base class to prevent copying |
| types.hpp | Common type definitions |

## Dependencies

- Irrlicht (irrString, vector types)
- Bullet Physics (btVector3 for Vec3)
- Standard library (STL containers, threading)
