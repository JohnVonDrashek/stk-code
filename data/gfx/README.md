# GFX (Graphics Effects)

Particle system definitions for visual effects like explosions, smoke, and environmental particles.

## Purpose

This directory contains XML definitions for the game's particle systems. Each file describes how particles are emitted, move, and render to create visual effects for gameplay events (explosions, nitro boost), kart interactions (skidding, exhaust), and environmental ambiance (rain, snow, bubbles).

## File Format

Files use `.xml` extension with a `<particles>` root element:

```xml
<particles emitter="sphere" radius="0.3">
    <spreading angle="180"/>
    <velocity x="0.0" y="0.0035" z="0.0"/>
    <material file="explode.png"/>
    <rate min="400" max="600"/>           <!-- Particles per second -->
    <lifetime min="1000" max="1200"/>     <!-- Milliseconds -->
    <size min="0.6" max="0.85"
          x-increase-factor="0.6"
          y-increase-factor="0.6"/>
    <color min="255 255 255" max="255 255 255"/>
</particles>
```

## Key Attributes

| Element | Description |
|---------|-------------|
| `emitter` | Shape: `sphere`, `box`, or `point` |
| `radius` / `box_*` | Emitter dimensions |
| `spreading angle` | Cone angle for particle direction (degrees) |
| `velocity` | Initial particle velocity vector |
| `material` | Texture file from `textures/` directory |
| `rate` | Emission rate range (particles/second) |
| `lifetime` | How long particles exist (milliseconds) |
| `size` | Particle scale with optional growth factors |
| `color` | RGB color range (min/max for variation) |

## Effect Categories

- **Explosions**: `explosion.xml`, `explosion_bomb.xml`, `explosion_cake.xml`
- **Kart effects**: `nitro.xml`, `kart_exhaust.xml`, `skid0-2.xml`
- **Weather**: `rain.xml`, `snow.xml`, `droplet.xml`
- **Environment**: `fire.xml`, `smoke.xml`, `waterfall.xml`, `gfx_bubble_a.xml`
- **Celebrations**: `confetti.xml`, `gfx_firework_a.xml`

## How the Game Uses These Files

The particle engine loads these definitions and instantiates emitters at runtime. Effects are triggered by game events (item hits, nitro activation) or attached to scene objects. The `material` textures are loaded from the textures directory.
