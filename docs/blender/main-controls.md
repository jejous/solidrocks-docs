# Main controls

The top of the panel is always visible, whatever tab is open.

## Resolution

- **Format**: choose a format family (HDTV 16:9, DCI Scope 2.39:1, DCI Flat 1.85:1...). The arrows step through the classic sizes of that family.
- Sizes marked with `*` exist in practice but are not an official industry standard.

## SolidRocks ON / OFF

- **OFF → ON**: your current Cycles settings are saved, then replaced by SolidRocks values for the chosen level.
- **ON → OFF**: your saved settings are restored exactly.
- **TESTING...**: shown while Guess, Calibrate or Compare are rendering. Those tools change the settings temporarily and restore them at the end.

The first time you switch on, SolidRocks lists the native settings it overrides.

## Level slider

Seven levels, from Draft to Ultra. Each level interpolates every setting between the preset's Draft and Ultra values. The dropdown next to the slider jumps straight to a level by name.

## Light Tree · Reflect · Refract

These three buttons are **Blender's own settings**, shown here for quick access. SolidRocks never changes them on its own: their best value depends on your scene.

- **Light Tree**: usually faster with many lights. Test ON and OFF on your scene.
- **Reflect / Refract**: reflective and refractive caustics.

## Region · Denoise · Anim Seed · Persistent

Settings you switch between two renders of the same scene.

| Button | What it does |
|---|---|
| **Region** | Uses Blender's render region (Ctrl+B) as the only test zone for Guess, Calibrate and Compare. The button turns **red** if Blender's own render border no longer matches it. The icon next to it lets you draw a new region in the viewport. |
| **Denoise** | Cycles denoiser. When on, the preset lowers samples and loosens the noise threshold (see [Preset tab](preset.md#denoise-dependent-values)). |
| **Anim Seed** | Changes the noise pattern on every frame (Cycles' Animated Seed). For animation. |
| **Persistent** | Keeps scene data in memory between renders (Persistent Data). Faster for repeated renders, but see the [FAQ](faq.md#persistent-data). |

Denoise, Anim Seed and Persistent copy the scene's own value the first time SolidRocks opens the scene.

## Clay · AO

**Clay** replaces every material with grey clay, using Blender's Material Override on the active View Layer. Your materials are not modified. **AO** sets the amount of ambient occlusion on the clay. Switch Clay off before final renders and measurements.

## Preset

- The dropdown lists the presets of your presets folder. Choosing one loads it immediately.
- A red **modified** mark means the scene's values no longer match the preset file (you edited a value, or the file changed).
- The `+` icon imports a `.json` preset from elsewhere.

## Save as Default

Saves the Level, Quick Preview settings, Compare zoom, noise target and the **name** of the active preset as defaults for **new** scenes. Existing scenes are never changed.

!!! warning
    Only the preset's name is saved. If the preset is marked **modified**, save it first in the Preset tab, or new scenes will load the file as it is on disk.

## Make Permanent

Shown when SolidRocks is ON. It detaches the scene from SolidRocks: the SolidRocks values become the scene's own values, and the backup is cleared. Use it before sending the file to someone, or to a render farm, without the add-on.

!!! danger
    Cannot be undone through SolidRocks (Ctrl+Z still works right after).

## Quick Preview

A fast, temporary render at Low quality and at the resolution set with **Res.**. Your settings are restored afterwards.

## Check Convergence

Renders the frame (or the active region) and reads how many samples each pixel actually needed. It shows a **heatmap** and a short report. It is a diagnostic only and changes nothing. Results go to the Render Result slots set in the add-on preferences.

## Auto-Exposure / Auto White Balance

- **Auto-Exposure** measures the scene and sets the exposure. Presets: Dark, Balanced, Bright for the target brightness; Multizone, Center-Weighted, Spot for where it measures. **Revert** goes back.
- **Auto White Balance** places a neutral grey card in front of the camera, measures it, and sets the white balance. The card is removed right after.

## Active Settings

Read-only summary of what Cycles will actually use: samples, noise threshold, clamps, bounces. These are the **applied** values, after resolution and denoise adjustments.
