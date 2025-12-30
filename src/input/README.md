# Input Module

Input management system handling keyboard, gamepad, touch, and Wiimote devices.

## Purpose

This module manages all player input from various devices including keyboards, gamepads (via SDL), touchscreens, and Wiimotes. It handles device detection, input binding configuration, input sensing for rebinding, and dispatching input events to the game or GUI systems based on the current mode.

## Key Classes

| Class | File | Purpose |
|-------|------|---------|
| InputManager | input_manager.hpp | Central input handler, dispatches events based on mode |
| DeviceManager | device_manager.hpp | Manages all connected input devices |
| DeviceConfig | device_config.hpp | Base configuration for input device bindings |
| InputDevice | input_device.hpp | Abstract base class for all input devices |
| KeyboardDevice | keyboard_device.hpp | Keyboard input handling |
| GamepadDevice | gamepad_device.hpp | Gamepad/joystick input handling |
| GamepadConfig | gamepad_config.hpp | Gamepad-specific binding configuration |
| MultitouchDevice | multitouch_device.hpp | Touch screen input for mobile platforms |
| SDLController | sdl_controller.hpp | SDL-based gamepad controller wrapper |
| Binding | binding.hpp | Maps physical inputs to game actions |
| WiimoteManager | wiimote_manager.hpp | Nintendo Wiimote support |

## Dependencies

- **guiengine/**: Sends events to EventHandler for menu navigation
- **karts/controller/**: Provides input to kart controllers during gameplay
- **config/**: Stores and loads input configurations
- **SDL2**: Gamepad input backend

## Input Modes

- MENU: UI navigation mode
- INGAME: Gameplay input mode
- INPUT_SENSE_KEYBOARD/GAMEPAD: Input binding detection
- BOOTSTRAP: Initial device assignment
