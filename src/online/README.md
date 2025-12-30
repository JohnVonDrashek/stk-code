# Online Module

HTTP request handling and online player profile management.

## Purpose

This module manages all HTTP-based communication with the STK online services. It handles user authentication, friend lists, achievements, and asynchronous request processing. The module uses a priority-based request queue executed in a background thread to avoid blocking the main game loop.

## Key Classes

| Class | File | Purpose |
|-------|------|---------|
| `RequestManager` | request_manager.hpp | Singleton managing async HTTP request queue with priority scheduling |
| `Request` | request.hpp | Base class for all network requests with priority and callbacks |
| `HTTPRequest` | http_request.hpp | HTTP request implementation using libcurl or NSURLSession |
| `XMLRequest` | xml_request.hpp | HTTP request that parses XML response data |
| `OnlineProfile` | online_profile.hpp | Represents a user profile with friends and achievements |
| `OnlinePlayerProfile` | online_player_profile.hpp | Current user's online profile with login state |
| `ProfileManager` | profile_manager.hpp | Cache and manager for online profiles |
| `LinkHelper` | link_helper.hpp | Platform-specific URL opening utilities |

## Dependencies

- **network/** - Network configuration and server information
- **config/** - User settings and player profiles
- **utils/** - XML parsing and synchronization primitives
- **libcurl** - HTTP client library (external dependency)
