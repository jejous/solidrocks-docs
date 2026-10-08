# SolidRocks for Cycles

**Faster Cycles renders, without guessing the settings.**

SolidRocks replaces a dozen Cycles render settings with one **quality slider, from Draft to Ultra**. Each step sets samples, noise threshold, light bounces and anti-firefly clamps together, from presets built by a lighting teacher with 15 years of experience.

It is the Blender port of SolidRocks for 3ds Max / V-Ray.

## What it does

- **One slider, seven levels**: Draft, Low, Medium, Good, Very Good, Prod, Ultra.
- **Non-destructive**: your own settings are saved when SolidRocks is switched on, and restored when it is switched off.
- **Presets for typical scenes**: Studio, Interior, Exterior.
- **Diagnose Scene**: checks your scene and explains what slows it down, without changing anything.
- **Measuring tools**: Guess Optimal Level picks the fastest level that stays clean on *your* scene; Compare Visually renders the levels side by side.
- **Scene shortcuts**: HDRI, sky, camera, cyclorama and a 3-point light rig in one click.

## What it does not do

- It never overrides a setting whose right value depends on your scene (Light Tree, caustics, World sampling, Simplify, Persistent Data, Denoise): those buttons show and change Blender's own setting.
- It does not replace your judgment: the measuring tools only **propose**, nothing is applied without you.

## Requirements

- Blender **5.1.1** (the version SolidRocks is tested on). Later versions may work, but have not been tested.
- Cycles, rendering on **GPU**. SolidRocks is designed and tuned for GPU rendering.

[Install SolidRocks](installation.md){ .md-button .md-button--primary }
[Quick start](quick-start.md){ .md-button }
