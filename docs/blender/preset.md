# Preset tab

The values behind the Level slider. Each setting has a **Draft** value and an **Ultra** value; the five levels in between are interpolated in a straight line.

The grey **Prod** column shows the value the Prod level will use. It is read-only. It can be hidden in the add-on preferences (**Show Production Column**).

!!! note
    These are preset values. The values Cycles really receives can differ after the resolution and denoise adjustments below. **Active Settings** (main controls) shows the applied values.

## Sampling

| Setting | Effect |
|---|---|
| **Samples** | Maximum samples per pixel. |
| **Noise Thr.** | Adaptive sampling threshold: a pixel stops when its noise is below this value. Lower = cleaner and slower. |
| **Adaptive Min Samples** | Samples every pixel gets before adaptive sampling may stop it. |

Samples and noise threshold work together: a pixel stops at whichever limit it reaches first. Raising one without the other often changes nothing.

## Resolution Dependent

Reference: 1920 × 1080. Above it, samples go down and the threshold goes up; below it (e.g. a Quick Preview), the reverse. **1.0** turns the adjustment off.

## Denoise Dependent Values

Only used when **Denoise** is on.

- **Samples Reduction Factor**: samples are divided by this value.
- **Noise Thr. Multiplier**: the noise threshold is multiplied by this value.

Keep the multiplier close to the **square root** of the reduction factor (1.5 → 1.22, 2 → 1.41), so both limits move together. The included presets use 1.5 / 1.22: on our test scenes, 20 to 40 % faster with no visible difference at 100 % zoom. 4 / 2 was clearly faster but lost detail.

## Anti-fireflies

| Setting | Effect |
|---|---|
| **Clamp direct / indirect** | Caps the brightness a single sample can add. Lower = fewer fireflies, but less energy in highlights. |
| **Filter glossy** | Blurs glossy reflections slightly to reduce noise and fireflies. |

## Bounce Depth

**Governed by Max Bounces (Total)**: Max bounces, Diffuse, Glossy, Transmission, Volume, Min Light. Max bounces is the overall limit; the others are limits per type.

**Not governed by Max Bounces**: Transparent and Min Transparent (a separate budget for transparent surfaces, e.g. alpha leaves or hair cards), and Fast GI.

!!! warning
    Transparent bounces too low make alpha-mapped surfaces render black where several layers overlap.

## Conditional

- **Light Threshold**: inactive while **Light Tree** is on.
- **Volume step rate / max steps**: need **Biased Volumes** (Optim tab).

## Presets

- **Name** + save icon: saves the current values as a preset (`.json`) in your presets folder.
- Folder icon: opens the presets folder.
- Presets are plain `.json` files: you can copy them to another machine or share them.
