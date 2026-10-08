# Tune tab

Tools that measure your scene. They render small test areas, change settings temporarily, and **restore everything at the end**. The SolidRocks button shows **TESTING...** while they run.

!!! tip "Before measuring"
    - Switch **Persistent** off (see [FAQ](faq.md#persistent-data)).
    - Switch **Clay** off.
    - Close any viewport in Rendered shading.

## Visual Comparison

Renders a band of the image at each level in the chosen range (**From**, **To**), side by side, with the estimated full-frame render time of each level.

- **Original** adds a band rendered with your own settings, for reference.
- **Position** chooses which part of the image is compared.
- **Burn Labels** writes the level name and time on each band.
- **Beauty** / **Heatmap** show the result again.

Your eye decides: pick the fastest level that looks good enough.

## Guess Optimal Level

Renders each level **twice with two different noise seeds** on small test zones, and measures the real noise left in the image. The difference between the two renders is pure noise, so textures are never mistaken for noise. It then recommends **the fastest level whose noise stays below the target**.

- It only recommends. Move the Level slider yourself.
- Denoiser off during the measurement: it measures raw noise.
- Can take a few minutes on complex scenes (volumes, subsurface scattering). It cannot be cancelled once started.

## Calibrate Scene

For advanced users who build their own presets. Measures how noise falls with samples **on this scene** and proposes a full ladder of noise thresholds and sample limits. Nothing is applied: use the **Prod** values it reports for this scene, and adjust your preset's Draft and Ultra values if needed.

## Measurement Settings

| Setting | Meaning |
|---|---|
| **Perceptual Noise Threshold** | The noise target used by Guess and Calibrate. Default 0.008, calibrated by eye on several scenes. |
| **Test Zone Size / Count** | Size and number of the automatic test zones (one in the center, the others on a circle around it). More zones = more reliable, but longer. Ignored when **Region** is on. |
| **Hardest Zone Weight** | 0 % = plain average of the zones. Higher values give more weight to the noisiest zone: cleaner hard areas, but higher sample counts everywhere. |

The report always says which zones were used: **Zones: 5 automatic** or **Zones: your Region (1 zone)**.

!!! tip "Measure where it matters"
    Automatic zones are placed geometrically, not on the content of your image. For a scene with one difficult area (glass, depth of field, a dark corner), draw a **Region** on it and turn Region on.
